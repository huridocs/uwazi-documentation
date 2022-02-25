# Set up the PDF Metadata Extraction

PDF Metadata Extraction is a Machine Learning service that connects to Uwazi. This service facilitates the
fulfillment of the Uwazi properties values that exist in the entities' PDFs.

To set up this service in Uwazi, follow these steps:

1. Set up the [PDF Paragraphs Extraction](https://uwazi.readthedocs.io/en/latest/sysadmin-docs/set-up-pdf-paragraphs-extraction.html)
2. Set up the PDF metadata extraction service: instructions [here](https://github.com/huridocs/pdf_metadata_extraction)
3. Add to the Uwazi database the URL to the PDF metadata extraction service:

    ``` 
   In db.settings add
   {
      ...
     "features":{
       ...
       "metadata-extraction": true,
       "metadataExtraction" :{
         "url":"http://[URL TO THE PDF METADATA EXTRACTION SERVICE]:5052"
       }
       ...
     }
      ...
   }
   ```

   Do NOT forget to put `http://` at the beginning of the URL.
