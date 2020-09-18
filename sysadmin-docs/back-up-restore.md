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

$ export DBHOST=localhost
$ export DATABASE_NAME=uwazi_development
