# Systems administrator's guide

```eval_rst
.. toctree::
   :maxdepth: 2

   work-in-progress

```
# Install Uwazi on your server
You can download the latest version of Uwazi here on Github. Be sure you have everything configured on your server first - here is a list of Uwazi's dependencies.

**Production Configuration (advanced)**
Uwazi is configured to run correctly with its default values. There is no need to change or reconfigure these values.

However, if you require different database names, elastic indexes, etc. you can override those defaults by exporting one or more of the following environment variables:

```
$ export DBHOST=localhost
$ export DATABASE_NAME=uwazi_development
$ export ELASTICSEARCH_URL=http://localhost:9200
$ export INDEX_NAME=uwazi_development
$ export PORT=3000
$ export UPLOADS_FOLDER=/path/to/uploaded_documents
$ export LOGS_DIR=/path/to/log
$ export LOCALHOST_ONLY=true
$ export USE_GRAYLOG=false OR URL of Graylog server
$ export CUSTOM_UPLOADS_FOLDER=path
$ export TEMPORAL_FILES_FOLDER=path

```

Again, please notice that there is no need to export any value for a normal installation and only do so if you are certain you need different defaults. If these values are not correctly overridden, Uwazi will fail to run properly.

For production environments, you may need to activate your system's sendmail so user's receive sign up and password recovery notifications.

Alternatively, you can use a custom SMTP configuration to send these emails. Find this option in settings > collection.

Example of linux system service:

```
[Unit]
Description=uwazi backend service for your-instance
After=network.target

[Service]
Environment=DBHOST=localhost
Environment=NODE_ENV=production
Environment=DATABASE_NAME=your-instance
Environment=ELASTICSEARCH_URL=http://elasticsearch:9200
Environment=INDEX_NAME=your-instance
Environment=PORT=40002
Environment=UPLOADS_FOLDER=/path/to/uploaded_documents
Environment=LOGS_DIR=/path/to/log

WorkingDirectory=/path/to/uwazi/code
ExecStart=/usr/bin/node server.js

Restart=always
RestartSec=30s
TimeoutSec=60s
User=uwazi

[Install]
WantedBy=multi-user.target

```

You don't need to keep your Uwazi code along with your user data, meaning that by configuring these variables you can use the same Uwazi code for running multiple Uwazi instances.

**Note on enabling HTTPS** the best to do this at the moment is by using a reverse-proxy (ie. Nginx) while activating LOCALHOST_ONLY in the configuration.
