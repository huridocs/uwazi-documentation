# Set up the PDF Paragraphs Extraction

PDF Paragraphs Extraction is a Machine Learning service that connects to Uwazi. 
This service receives PDFs and outputs the text and the positions of the PDFs' paragraphs. 

To set up this service in Uwazi follow these steps:

1. Set up the service: instructions [here](https://github.com/huridocs/pdf_paragraphs_extraction)
2. Set up a [Redis server](https://redis.io/)
3. Configure Redis in Uwazi using the following environment variables

   ```
   export REDIS_HOST=[redis_host]
   export REDIS_PORT=[redis_port]
   ```
   
4. Activate the external services in Uwazi with the following environment variable:

   ```
   export EXTERNAL_SERVICES=true
   ```
   
5. Add to the Uwazi database the URL to the PDF Paragraphs Extraction service:

    ``` 
   In db.settings add
   {
      ...
     "features":{
       "segmentation":{
         "url":"http://[URL TO THE PDF PARAGRAPHS EXTRACTION SERVICE]:5051/async_extraction"
       }
     }
      ...
   }
   ```
   
   Do NOT forget to put `http://` at the beginning of the URL 
   
   The following command can be used if no other features are set up

   ```
   mongo localhost/[UWAZI DB NAME] --eval 'db.settings.update({},{$set : {"features":{"segmentation":{"url":"http://[URL TO THE PDF PARAGRAPHS EXTRACTION SERVICE]:5051/async_extraction"}}}},{upsert:false,multi:true})'
   ```

