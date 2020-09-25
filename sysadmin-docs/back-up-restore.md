# Backup

Backup and restoring operations are performed manually.

**Backup**

In order to have a full backup of your data, all you need to do is dump the whole collection in MongoDB, and keep a copy of everything contained in the "uploaded_documents" folder.

**Restore**

Follow these steps in a fresh Uwazi install:

1. Copy/extract the documents in the "uploaded_documents".
2. Restore the database.
3. Run "yarn migrate" in the uwazi directory. This will update your data if needed.
4. Run "yarn reindex".
5. Run the server and navigate to localhost:3000

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
