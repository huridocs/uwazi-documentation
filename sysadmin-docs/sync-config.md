# Sync Instances

Uwazi allows syncing specific data from one tenant to other tenants.

Configuration for this should be done manually on the origin tenant settings collection under the "sync" property.

Multiple syncs can be configured to different targets.


## Settings schema

| name | type | description | 
| -----| ----|------------|
| active| boolean | To activate/deactivate the sync|
| url| string | Target uwazi instance|
| username| string | Username of target instance|
| password| string | Password of target instance (plain)|
| name| string | Unique sync name|
| config| object | Configuration settings|
| config.template| object | Map where key is the template being synced and the value is the config for the specific template|
| config.template.properties| array | List of property ids to be synced|
| config.template.filter| string | Object represnting a mongo query|

## Example

The first config in the example will sync:
- All entities that belong to the template id configured with the base properties
- All the properties explicitly configured
- Only entities that match the configured filter

The filter should be in the same form as a mongodb filter, this is based on the [sift](https://github.com/crcn/sift.js) library

The second config in the example will sync all entities that belong to the template id configured with only the base properties (title, date added)

```
{
  "sync" : [
   {
        "active" : true,
        "url" : "https://example.uwazi.io",
        "username" : "sync",
        "password" : "6c2f1dbd9fa4be72587d5eb01cc94098f6728a88",
        "config" : {
          "templates" : {
            "5bfbb1a0471dd0fc16ada146" : {
              "filter" : "{\"title\": 'only this title will be synced'}",
              "properties" : [
                "6223be8d01f51b254b6f61ef",
                "62711a5ac469aa4039f90148"
              ]
            }
          }
        },
        "name" : "default"
    }
    {
        "active" : true,
        "url" : "https://another-example.uwazi.io",
        "username" : "sync",
        "password" : "6c2f1dbd9fa4be72587d5eb01cc94098f6728a88",
        "name" : "another sync"
        "config" : {
          "templates" : {
            "5bfbb1a0471dd0fc16ada146" : {}
          }
        },
    }
  ]
}

```

The Ts definitions for reference https://github.com/huridocs/uwazi/blob/production/app/shared/types/settingsType.d.ts#L117-L136

