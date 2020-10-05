# Multi-tenancy 

Multi-tenancy is built-in uwazi and allows for multiple databases/tenants to be served with a single node process.
the tenant object defines all specific configurations, tenants should be created on a separated db 'uwazi_shared_db' in a 'tenants' collections with the following structure:

this is from app/api/tenants/tenantContext.ts
```
export type Tenant = {
  name: string; //should be unique
  dbName: string; //should be unique
  indexName: string; //should be unique
  uploadedDocuments: string;
  attachments: string;
  customUploads: string;
  temporalFiles: string;
};

```

Uwazi will use this config for requests that provide a tenant header corresponding with the tenant name, for requests that do not provide one uwazi will use the defaultTenant from app/api/config.ts.

## the most basic example working

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

as you can see a MULTI_TENANT env variable is set to true, uwazi is multi tenant by default but we need to set this variable to deactivate certain features that do not work with a multi-tenant approach for now, this are the features not supported for now.

- evidence vault
- sync
- semantic search
- topic classification


## serving the web app

in order for this to work not only for the api but the web app, a proxy mapping the diferent tenants needs to be set up, we use nginx.
here is a basic nginx config that maps diferent ports the same uwazi process but with diferent tenant header:

```
server {
  listen       3001;

  location / {
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_set_header tenant tenant1;
    proxy_pass http://localhost:3000;
  }
}

server {
  listen       3002;

  location / {
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_set_header tenant tenant2;
    proxy_pass http://localhost:3000;
  }
}
```

opening the browser on localhost:3001 will serve an app that will work with tenant1, localhost:3002 will work with tenant2.

## maintenance scripts

scripts such as yarn migrate, and yarn reindex use the defaultTenant to perform the task, defaultTenant is configured by setting appropiate environment variables, a full list of this variables is on the [install documentation](https://uwazi.readthedocs.io/en/latest/sysadmin-docs/install.html)

example:
```
DATABASE_NAME=tenant1_db INDEX_NAME=tenant1_index yarn migrate
DATABASE_NAME=tenant2_db INDEX_NAME=tenant2_index yarn reindex
```
