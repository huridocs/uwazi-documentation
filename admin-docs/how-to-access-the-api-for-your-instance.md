# How to Access the API for Your Instance

> An API allows one program to request data from another. API stands for application programming interface. An API provides you with data its programmers have made available to outside users.


The server has the data and sets the language, while the client uses that language to ask for information from the server. To make some of data available to the public, programmers "expose endpoints," meaning they publish a portion of the language they’ve used to build their program. Endpoints return text that’s meant for computers to read.
There are four types of actions an API can take:

- GET: requests data from a server — can be status or specifics (like last_name)
- POST: sends changes from the client to the server; think of this as adding information to the server, like making a new entry
- PUT: revises or adds to existing information
- DELETE: deletes existing information

You can access the API instructions and options for your Uwazi instance by adding _/api_ to the end of your URL, like this:[ https://yourinstancename.uwazi.io/api](https://yourinstancename.uwazi.io/api). Uwazi requires **authorization** for POST and DELETE actions. Uwazi does not require authorization for GET actions. Uwazi currently does not use PUT actions via the API.

These are a few examples of some endpoints that Uwazi currently offers:

| /search | /entities | /attachments |
| ------- | --------- | ------------ |
|         |           |              |

Additional notes regarding the /**entities** endpoint:

- The templateId parameter sent in GET /entities/count_by_template is the mongo \_id for a particular template type. For the time being, you could ask the API for templates (you can use [https://yourinstancename.uwazi.io/api/templates](https://yourinstancename.uwazi.io/api/templates)) and then get the \_id from those results. Alternatively, the ID is shown in the URL if you et:dit a particular template.

Additional notes regarding the /**search** endpoint:

- There is currently no maximum amount of results returned by GET /search. The search can return anywhere from 0 to all the documents. The default is 30 but the LIMIT property (as you can check by selecting 'load more' in the library) can be set to any number you wish. Higher numbers will take longer, be bigger and put extra toll on the server, so be careful.

Uwazi provides a list of "models" that describe the objects you have access to via the API:

|     |     |
| --- | --- |
|     |     |
