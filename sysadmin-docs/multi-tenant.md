# Multi-tenancy

Multi-tenancy is built-into Uwazi and allows for multiple databases/tenants to be served with a single node process.

The tenant object defines all specific configurations. Tenants should be created on a separated db 'uwazi_shared_db' in a 'tenants' collections with the following structure:

This is from app/api/tenants/tenantContext.ts

```
export type Tenant = {
  name: string; //should be unique
  dbName: string; //should be unique
  indexName: string; //should be unique
  uploadedDocuments: string;
  attachments: string;
  customUploads: string;
  temporalFiles: string;
  activityLogs: string;
};

```

Uwazi will use this config for requests that provide a tenant header corresponding with the tenant name, for requests that do not provide one Uwazi will use the defaultTenant from app/api/config.ts.

## The most basic working example

```
//setup tenants, no paths specified for simplicity but they SHOULD be specified in the config, there is no default.
mongo localhost/uwazi_shared_db --eval 'db.tenants.insert({ name : "tenant1", dbName : "tenant1", indexName: "tenant1" });'
mongo localhost/uwazi_shared_db --eval 'db.tenants.insert({ name : "tenant2", dbName : "tenant2", indexName: "tenant2" });'

//setup dbs for tenants
yarn blank-state tenant1
yarn blank-state tenant2

//add entity for tenant1 and reindex
mongo localhost/tenant1 --eval 'db.entities.insert({ title : "Test entity", template : "5bfbb1a0471dd0fc16ada146", published: true, language: "en" });'
INDEX_NAME=tenant1 DATABASE_NAME=tenant1 yarn reindex

//start uwazi server
MULTI_TENANT=true node server

//requests for specific tenant, tenant1 should return "Test entity" and tenant2 should return an empty result :)
curl -H "tenant: tenant1" localhost:3000/api/search
curl -H "tenant: tenant2" localhost:3000/api/search
```

As you can see a MULTI_TENANT env variable is set to true, Uwazi is multi-tenant by default but we need to set this variable to deactivate certain features that do not work with a multi-tenant approach for now. These are the features not supported for now:

- evidence vault
- sync
- semantic search
- topic classification

## Serving the web app

In order for this to work not only for the api but the web app, a proxy mapping the different tenants needs to be set up. We use nginx.

Here is a basic nginx config that maps different ports to the same Uwazi process, but with different tenant header:

```
server {
  server_name tenant1.localhost;
  listen       3001;
  location / {
                proxy_set_header tenant tenant1;
                proxy_set_header host $host;
                proxy_set_header x-forwarded-server $host;
                proxy_set_header x-forwarded-for $proxy_add_x_forwarded_for;
                proxy_pass http://localhost:3000;
                client_max_body_size 500M;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection "upgrade";
                proxy_connect_timeout 60s;
                proxy_read_timeout 60s;
  }
}

server {
  server_name tenant2.localhost;
  listen       3002;
  location / {
                proxy_set_header tenant tenant2;
                proxy_set_header host $host;
                proxy_set_header x-forwarded-server $host;
                proxy_set_header x-forwarded-for $proxy_add_x_forwarded_for;
                proxy_pass http://localhost:3000;
                client_max_body_size 500M;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection "upgrade";
                proxy_connect_timeout 60s;
                proxy_read_timeout 60s;
  }
}
```

Opening the browser on localhost:3001 will serve an app that will work with tenant1, localhost:3002 will work with tenant2.

## Maintenance scripts

Scripts such as yarn migrate, and yarn reindex use the defaultTenant to perform the task, defaultTenant is configured by setting appropiate environment variables, a full list of this variables is on the [install documentation](https://uwazi.readthedocs.io/en/latest/sysadmin-docs/install.html).

Example:

```
DATABASE_NAME=tenant1_db INDEX_NAME=tenant1_index yarn migrate
DATABASE_NAME=tenant2_db INDEX_NAME=tenant2_index yarn reindex
```
