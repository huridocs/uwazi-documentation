# Set up the Twitter crawler service

The twitter crawler service can be integrated in Uwazi to import tweets from Twitter.

To set up this service in Uwazi, follow these steps:

1. Set up the service: instructions [here](https://github.com/huridocs/twitter_crawler)
2. Set up a [Redis server](https://redis.io/)
3. Configure Redis in Uwazi using the following environment variables:

   ```
   export REDIS_HOST=[redis_host]
   export REDIS_PORT=[redis_port]
   ```
   
4. Activate the external services in Uwazi with the following environment variable:

   ```
   export EXTERNAL_SERVICES=true
   ```
   
5. Add to the Uwazi database the hashtags or user handles to crawl:

    ``` 
   In db.settings add
   {
      ...
     "features":{
           "twitterIntegration": {
           "searchQueries": [
                "#hashtag_example",
                "@user_handle_example",
           ],
           "tweetsTemplateName": "[Template name for the tweets]",
           "hashtagsTemplateName": "[Template name for the hashtaghs/user handlers]", 
           "language": "[Language to save the entities in Uwazi]",
           "tweetsLanguages": ["en"]
           }
     }
      ...
   }
   ```
   
   Do NOT use template names that already exists in Uwazi!
