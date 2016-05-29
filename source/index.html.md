---
title: API Reference
language_tabs:
  - shell
  - java
  - python
  - php
toc_footers:
 - <a href='#'>Sign Up for a Developer Key</a>
includes:
    - errors
search: true
---
# Introduction

```
We have language bindings in java, python, php! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.
```

An analytics platform API that lets you create your own analytics services.

### Version
Version: 0.5

## Contact Information
Email: contact@rakam.com

### License
License: Apache License 2.0

License url: http://www.apache.org/licenses/LICENSE-2.0.html

### URI scheme
Host: api.rakam.io
BasePath: /

# Funnel


Funnel Analyzer module

## Execute query
```shell
curl "api.rakam.io/funnel/analyze"
  -H "read_key: myread_key"
-X POST -d '{"steps" : [
	{"collection" : "str"}
]
, "dimension" : "str"
, "startDate" : "2015-01-20"
, "window" : {"value" : 0, "type" : "str"}
, "endDate" : "2015-01-20"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.FunnelApi();
api.analyze_funnel(funnel_query);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.FunnelApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
FunnelApi api = new FunnelApi(apiClient);
api.analyzeFunnel(funnelQuery);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\FunnelApi($api_client);
$api->analyzeFunnel(funnel_query);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : false,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 0,
    "errorLine" : 0,
    "charPositionInLine" : 0
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : false
}
```

### HTTP Request
`POST /funnel/analyze`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|steps|false|[FunnelStep](#funnelstep) array||
|dimension|false|string||
|startDate|false|string (date)||
|window|false|[FunnelWindow](#funnelwindow)||
|endDate|false|string (date)||


# Realtime




## Create report
```shell
curl "api.rakam.io/realtime/create"
  -H "master_key: mymaster_key"
-X POST -d '{"name" : "str"
, "measures" : [
	{"column" : "str", "aggregation" : "str"}
]
, "table_name" : "str"
, "collections" : [
	"str"
]
, "filter" : "str"
, "dimensions" : [
	"str"
]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.RealtimeApi();
api.create_table(real_time_report);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.createTable(realTimeReport);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->createTable(real_time_report);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /realtime/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|name|false|string||
|measures|false|[Measure](#measure) array||
|table_name|false|string||
|collections|false|string array||
|filter|false|string||
|dimensions|false|string array||


## Delete report
```shell
curl "api.rakam.io/realtime/delete"
  -H "master_key: mymaster_key"
-X POST -d '{
  "table_name" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.RealtimeApi();
api.delete_table(table_name);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.deleteTable(tableName);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->deleteTable(table_name);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /realtime/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|false|string||


## Get report
```shell
curl "api.rakam.io/realtime/get"
  -H "read_key: myread_key"
-X POST -d '{"table_name" : "str"
, "filter" : "str"
, "measure" : {"column" : "str", "aggregation" : "str"}
, "dimensions" : [
	"str"
]
, "aggregate" : false
, "date_start" : 
, "date_end" : 
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.query_table(realtime_query_table);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.queryTable(realtimeQueryTable);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->queryTable(realtime_query_table);


```

> The above command returns JSON structured like this:

```json
{
  "start" : 0,
  "end" : 0,
  "result" : "object"
}
```

### HTTP Request
`POST /realtime/get`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|false|string||
|filter|false|string||
|measure|false|[Measure](#measure)||
|dimensions|false|string array||
|aggregate|false|boolean||
|date_start|false|string (date-time)||
|date_end|false|string (date-time)||


## List queries
```shell
curl "api.rakam.io/realtime/list"
  -H "read_key: myread_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.list_tables();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.listTables();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->listTables();


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "query" : "str",
  "options" : {
    "prop" : { }
  },
  "tableName" : "str",
  "partitionKeys" : [ "str" ]
} ]
```

### HTTP Request
`POST /realtime/list`
# Retention


Retention Analyzer module

## Execute query
```shell
curl "api.rakam.io/retention/analyze"
  -H "read_key: myread_key"
-X POST -d '{"first_action" : {"collection" : "str"}
, "returning_action" : {"collection" : "str"}
, "dimension" : "str"
, "date_unit" : "str"
, "period" : 0
, "startDate" : "2015-01-20"
, "endDate" : "2015-01-20"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RetentionApi();
api.analyze_retention(retention_query);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.RetentionApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RetentionApi api = new RetentionApi(apiClient);
api.analyzeRetention(retentionQuery);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RetentionApi($api_client);
$api->analyzeRetention(retention_query);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : false,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 0,
    "errorLine" : 0,
    "charPositionInLine" : 0
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : false
}
```

### HTTP Request
`POST /retention/analyze`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|first_action|false|[RetentionAction](#retentionaction)||
|returning_action|false|[RetentionAction](#retentionaction)||
|dimension|false|string||
|date_unit|false|enum (DAY, WEEK, MONTH)||
|period|false|integer (int32)||
|startDate|false|string (date)||
|endDate|false|string (date)||


# User


User module for Rakam

## Create new users
```shell
curl "api.rakam.io/user/batch/create"
  -H "write_key: mywrite_key"
-X POST -d '{"users" : [
	{"id" : "object", "api" : {"apiKey" : "str", "apiLibrary" : "str", "apiVersion" : "str"}, "properties" : {"prop": {}}}
]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.UserApi();
api.create_users(user_create_users);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.createUsers(userCreateUsers);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->createUsers(user_create_users);


```

> The above command returns JSON structured like this:

```json
[ "object" ]
```

### HTTP Request
`POST /user/batch/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|users|false|[User](#user) array||


## Create new user
```shell
curl "api.rakam.io/user/create"
-X POST -d '{"id" : "object"
, "api" : {"apiKey" : "str", "apiLibrary" : "str", "apiVersion" : "str"}
, "properties" : {"prop": {}}
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")

api = client.UserApi();
api.create_user(user);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.createUser(user);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');


$api = new Swagger\Client\UserApi($api_client);
$api->createUser(user);


```

> The above command returns JSON structured like this:

```json
"object"
```

### HTTP Request
`POST /user/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|id|true|object||
|api|true|[UserContext](#usercontext)||
|properties|true|object||


## Get events of the user
```shell
curl "api.rakam.io/user/create_segment"
  -H "read_key: myread_key"
-X POST -d '{"name" : "str"
, "table_name" : "str"
, "filter_expression" : "str"
, "event_filters" : [
	{"collection" : "str", "timeframe" : {"start" : , "end" : }, "aggregation" : {"field" : "str", "minimum" : 0, "maximum" : 0, "type" : "str"}, "filterExpression" : "str"}
]
, "cache_eviction" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.create_segment(user_create_segment);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.createSegment(userCreateSegment);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->createSegment(user_create_segment);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /user/create_segment`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|name|false|string||
|table_name|false|string||
|filter_expression|false|string||
|event_filters|false|[EventFilter](#eventfilter) array||
|cache_eviction|false|string||


## Get user
```shell
curl "api.rakam.io/user/get"
  -H "read_key: myread_key"
-X POST -d '{"user" : "object"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.get_user(user_get_user);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.getUser(userGetUser);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->getUser(user_get_user);


```

> The above command returns JSON structured like this:

```json
{
  "id" : "object",
  "api" : {
    "apiKey" : "str",
    "apiLibrary" : "str",
    "apiVersion" : "str"
  },
  "properties" : {
    "prop" : { }
  }
}
```

### HTTP Request
`POST /user/get`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|user|false|object||


## Get events of the user
```shell
curl "api.rakam.io/user/get_events"
  -H "read_key: myread_key"
-X POST -d '{
  "user" : "str",
  "limit" : 0,
  "offset" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.get_events(user, limit, offset);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.getEvents(user, limit, offset);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->getEvents(user, limit, offset);


```

> The above command returns JSON structured like this:

```json
[ {
  "collection" : "str",
  "properties" : {
    "prop" : { }
  }
} ]
```

### HTTP Request
`POST /user/get_events`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|user|false|string||
|limit|false|integer (int32)||
|offset|false|string (date-time)||


## Set user property
```shell
curl "api.rakam.io/user/increment_property"
  -H "master_key: mymaster_key"
-X POST -d '{"api" : {"apiKey" : "str", "apiLibrary" : "str", "apiVersion" : "str"}
, "id" : "str"
, "property" : "str"
, "value" : 0.0
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.UserApi();
api.increment_property(user_increment_property);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.incrementProperty(userIncrementProperty);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->incrementProperty(user_increment_property);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /user/increment_property`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|api|false|[UserContext](#usercontext)||
|id|false|string||
|property|false|string||
|value|false|number (double)||


## Merge user with anonymous id
```shell
curl "api.rakam.io/user/merge"
  -H "read_key: myread_key"
-X POST -d '{"user" : "str"
, "api" : {"apiKey" : "str", "apiLibrary" : "str", "apiVersion" : "str"}
, "anonymous_id" : "str"
, "created_at" : 
, "merged_at" : 
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.merge_user(user_merge_user);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.mergeUser(userMergeUser);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->mergeUser(user_merge_user);


```

> The above command returns JSON structured like this:

```json
false
```

### HTTP Request
`POST /user/merge`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|user|false|string||
|api|false|[UserContext](#usercontext)||
|anonymous_id|false|string||
|created_at|false|string (date-time)||
|merged_at|false|string (date-time)||


## Get user storage metadata
```shell
curl "api.rakam.io/user/metadata"
  -H "read_key: myread_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.get_metadata();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.getMetadata();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->getMetadata();


```

### HTTP Request
`GET /user/metadata`
## Search users
```shell
curl "api.rakam.io/user/search"
  -H "read_key: myread_key"
-X POST -d '{"columns" : [
	"str"
]
, "filter" : "str"
, "event_filters" : [
	{"collection" : "str", "timeframe" : {"start" : , "end" : }, "aggregation" : {"field" : "str", "minimum" : 0, "maximum" : 0, "type" : "str"}, "filterExpression" : "str"}
]
, "sorting" : {"column" : "str", "order" : "str"}
, "offset" : "str"
, "limit" : 0
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.search_users(user_search_users);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.searchUsers(userSearchUsers);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->searchUsers(user_search_users);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : false,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 0,
    "errorLine" : 0,
    "charPositionInLine" : 0
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : false
}
```

### HTTP Request
`POST /user/search`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|columns|false|string array||
|filter|false|string||
|event_filters|false|[EventFilter](#eventfilter) array||
|sorting|false|[Sorting](#sorting)||
|offset|false|string||
|limit|false|integer (int32)||


## Set user properties
```shell
curl "api.rakam.io/user/set_properties"
-X POST -d '{"id" : "object"
, "api" : {"apiKey" : "str", "apiLibrary" : "str", "apiVersion" : "str"}
, "properties" : {"prop": {}}
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")

api = client.UserApi();
api.set_properties(user);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.setProperties(user);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');


$api = new Swagger\Client\UserApi($api_client);
$api->setProperties(user);


```

> The above command returns JSON structured like this:

```json
0
```

### HTTP Request
`POST /user/set_properties`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|id|true|object||
|api|true|[UserContext](#usercontext)||
|properties|true|object||


## Set user properties once
```shell
curl "api.rakam.io/user/set_properties_once"
-X POST -d '{"id" : "object"
, "api" : {"apiKey" : "str", "apiLibrary" : "str", "apiVersion" : "str"}
, "properties" : {"prop": {}}
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")

api = client.UserApi();
api.set_properties_once(user);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.setPropertiesOnce(user);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');


$api = new Swagger\Client\UserApi($api_client);
$api->setPropertiesOnce(user);


```

### HTTP Request
`POST /user/set_properties_once`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|id|true|object||
|api|true|[UserContext](#usercontext)||
|properties|true|object||


## Unset user property
```shell
curl "api.rakam.io/user/unset_properties"
-X POST -d '{"api" : {"apiKey" : "str", "apiLibrary" : "str", "apiVersion" : "str"}
, "id" : "object"
, "properties" : [
	"str"
]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")

api = client.UserApi();
api.unset_property(user_unset_property);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.unsetProperty(userUnsetProperty);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');


$api = new Swagger\Client\UserApi($api_client);
$api->unsetProperty(user_unset_property);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /user/unset_properties`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|api|false|[UserContext](#usercontext)||
|id|false|object||
|properties|false|string array||


# Admin


System related actions

## List installed modules
```shell
curl "api.rakam.io/admin/configurations"
  -H "master_key: mymaster_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.get_configurations();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.getConfigurations();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->getConfigurations();


```

### HTTP Request
`GET /admin/configurations`
## Check lock key
```shell
curl "api.rakam.io/admin/lock_key"
  -H "master_key: mymaster_key"
-X POST -d '{
  "lock_key" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.check_lock_key(lock_key);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.checkLockKey(lockKey);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->checkLockKey(lock_key);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /admin/lock_key`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|lock_key|false|string||


## List installed modules for ui
```shell
curl "api.rakam.io/admin/modules"
  -H "master_key: mymaster_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.modules();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.modules();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->modules();


```

### HTTP Request
`GET /admin/modules`
## Get types
```shell
curl "api.rakam.io/admin/types"
  -H "master_key: mymaster_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.get_types();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.getTypes();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->getTypes();


```

### HTTP Request
`GET /admin/types`
## Get collection names
```shell
curl "api.rakam.io/project/collection"
  -H "read_key: myread_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.collections();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.collections();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->collections();


```

> The above command returns JSON structured like this:

```json
[ "str" ]
```

### HTTP Request
`POST /project/collection`
## Create project
```shell
curl "api.rakam.io/project/create"
-X POST -d '{
  "lock_key" : "str",
  "name" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")

api = client.AdminApi();
api.create_project(lock_key, name);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();

AdminApi api = new AdminApi(apiClient);
api.createProject(lockKey, name);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');


$api = new Swagger\Client\AdminApi($api_client);
$api->createProject(lock_key, name);


```

> The above command returns JSON structured like this:

```json
{
  "masterKey" : "str",
  "readKey" : "str",
  "writeKey" : "str"
}
```

### HTTP Request
`POST /project/create`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|lock_key|false|string||
|name|false|string||


## Create API Keys
```shell
curl "api.rakam.io/project/create-api-keys"
  -H "master_key: mymaster_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.create_api_keys();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.createApiKeys();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->createApiKeys();


```

> The above command returns JSON structured like this:

```json
{
  "masterKey" : "str",
  "readKey" : "str",
  "writeKey" : "str"
}
```

### HTTP Request
`POST /project/create-api-keys`
## Delete project
```shell
curl "api.rakam.io/project/delete"
  -H "master_key: mymaster_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.delete_project();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.deleteProject();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->deleteProject();


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /project/delete`
## List created projects
```shell
curl "api.rakam.io/project/list"
  -H "read_key: myread_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.get_projects();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.getProjects();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->getProjects();


```

### HTTP Request
`GET /project/list`
## Revoke API Keys
```shell
curl "api.rakam.io/project/revoke-api-keys"
  -H "master_key: mymaster_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.revoke_api_keys();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.revokeApiKeys();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->revokeApiKeys();


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /project/revoke-api-keys`
## Get collection schema
```shell
curl "api.rakam.io/project/schema"
  -H "read_key: myread_key"
-X POST -d '{
  "names" : [ "str" ]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.schema(names);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.schema(names);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->schema(names);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "fields" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : false,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ]
} ]
```

### HTTP Request
`POST /project/schema`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|names|false|multi string array||


## Add fields to collections
```shell
curl "api.rakam.io/project/schema/add"
  -H "master_key: mymaster_key"
-X POST -d '{"collection" : "str"
, "fields" : [
	{"name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"}
]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.add_fields_to_schema(project_add_fields_to_schema);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.addFieldsToSchema(projectAddFieldsToSchema);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->addFieldsToSchema(project_add_fields_to_schema);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "type" : "str",
  "unique" : false,
  "descriptiveName" : "str",
  "description" : "str",
  "category" : "str"
} ]
```

### HTTP Request
`POST /project/schema/add`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|collection|false|string||
|fields|false|[SchemaField](#schemafield) array||


## Add fields to collections by transforming other schemas
```shell
curl "api.rakam.io/project/schema/add/custom"
  -H "master_key: mymaster_key"
-X POST -d '{
  "collection" : "str",
  "schema_type" : "str",
  "schema" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.add_custom_fields_to_schema(collection, schema_type, schema);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.addCustomFieldsToSchema(collection, schemaType, schema);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->addCustomFieldsToSchema(collection, schema_type, schema);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "type" : "str",
  "unique" : false,
  "descriptiveName" : "str",
  "description" : "str",
  "category" : "str"
} ]
```

### HTTP Request
`POST /project/schema/add/custom`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|collection|false|string||
|schema_type|false|string||
|schema|false|string||


## Get project stats
```shell
curl "api.rakam.io/project/stats"
-X POST -d '["object"]'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")

api = client.AdminApi();
api.get_stats(project_get_stats);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.AdminApi;

ApiClient apiClient = new ApiClient();

AdminApi api = new AdminApi(apiClient);
api.getStats(projectGetStats);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');


$api = new Swagger\Client\AdminApi($api_client);
$api->getStats(project_get_stats);


```

> The above command returns JSON structured like this:

```json
{
  "prop" : { }
}
```

### HTTP Request
`POST /project/stats`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|array|false|object||


# Event


Event Analyzer

## Collect multiple events
```shell
curl "api.rakam.io/event/batch"
  -H "write_key: mywrite_key"
-X POST -d '{"api" : {"apiKey" : "str", "library" : {"name" : "str", "version" : "str"}, "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str", "plugins" : [
	{"name" : "str", "arguments" : {"prop": {}}}
]}
, "events" : [
	{"project" : "str", "collection" : "str", "api" : {"apiKey" : "str", "library" : {"name" : "str", "version" : "str"}, "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str", "plugins" : [
	{"name" : "str", "arguments" : {"prop": {}}}
]}, "properties" : "object"}
]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.EventApi();
api.batch_events(event_list);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.batchEvents(eventList);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->batchEvents(event_list);


```

> The above command returns JSON structured like this:

```json
0
```

### HTTP Request
`POST /event/batch`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|api|false|[EventContext](#eventcontext)||
|events|false|[Event](#event) array||



Returns 1 if the events are collected.

## Send Bulk events
```shell
curl "api.rakam.io/event/bulk"
  -H "master_key: mymaster_key"
-X POST -d '{"api" : {"apiKey" : "str", "library" : {"name" : "str", "version" : "str"}, "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str", "plugins" : [
	{"name" : "str", "arguments" : {"prop": {}}}
]}
, "events" : [
	{"project" : "str", "collection" : "str", "api" : {"apiKey" : "str", "library" : {"name" : "str", "version" : "str"}, "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str", "plugins" : [
	{"name" : "str", "arguments" : {"prop": {}}}
]}, "properties" : "object"}
]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.EventApi();
api.bulk_events(event_list);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.bulkEvents(eventList);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->bulkEvents(event_list);


```

> The above command returns JSON structured like this:

```json
0
```

### HTTP Request
`POST /event/bulk`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|api|false|[EventContext](#eventcontext)||
|events|false|[Event](#event) array||


## Send Bulk events
```shell
curl "api.rakam.io/event/bulk/remote"
  -H "master_key: mymaster_key"
-X POST -d '{"api" : {"apiKey" : "str", "library" : {"name" : "str", "version" : "str"}, "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str", "plugins" : [
	{"name" : "str", "arguments" : {"prop": {}}}
]}
, "events" : [
	{"project" : "str", "collection" : "str", "api" : {"apiKey" : "str", "library" : {"name" : "str", "version" : "str"}, "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str", "plugins" : [
	{"name" : "str", "arguments" : {"prop": {}}}
]}, "properties" : "object"}
]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.EventApi();
api.bulk_events_remote(event_list);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.bulkEventsRemote(eventList);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->bulkEventsRemote(event_list);


```

> The above command returns JSON structured like this:

```json
0
```

### HTTP Request
`POST /event/bulk/remote`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|api|false|[EventContext](#eventcontext)||
|events|false|[Event](#event) array||


## Collect event
```shell
curl "api.rakam.io/event/collect"
  -H "write_key: mywrite_key"
-X POST -d '{"project" : "str"
, "collection" : "str"
, "api" : {"apiKey" : "str", "library" : {"name" : "str", "version" : "str"}, "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str", "plugins" : [
	{"name" : "str", "arguments" : {"prop": {}}}
]}
, "properties" : "object"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.EventApi();
api.collect_event(event);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.collectEvent(event);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->collectEvent(event);


```

> The above command returns JSON structured like this:

```json
0
```

### HTTP Request
`POST /event/collect`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|collection|true|string||
|api|true|[EventContext](#eventcontext)||
|properties|true|object||


## Analyze events
```shell
curl "api.rakam.io/query/execute"
  -H "read_key: myread_key"
-X POST -d '{
  "query" : "str",
  "limit" : 0
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventApi();
api.execute(query, limit);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.execute(query, limit);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->execute(query, limit);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : false,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 0,
    "errorLine" : 0,
    "charPositionInLine" : 0
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : false
}
```

### HTTP Request
`POST /query/execute`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|false|string||
|limit|false|integer (int32)||


## Explain query
```shell
curl "api.rakam.io/query/explain"
  -H "read_key: myread_key"
-X POST -d '{
  "query" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventApi();
api.explain(query);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.explain(query);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->explain(query);


```

> The above command returns JSON structured like this:

```json
"object"
```

### HTTP Request
`POST /query/explain`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|false|string||


## Test query
```shell
curl "api.rakam.io/query/metadata"
  -H "read_key: myread_key"
-X POST -d '{
  "query" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventApi();
api.metadata(query);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.metadata(query);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->metadata(query);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "type" : "str",
  "unique" : false,
  "descriptiveName" : "str",
  "description" : "str",
  "category" : "str"
} ]
```

### HTTP Request
`POST /query/metadata`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|false|string||


# Materialized view


Materialized view

## Create view
```shell
curl "api.rakam.io/materialized-view/create"
  -H "master_key: mymaster_key"
-X POST -d '{"name" : "str"
, "query" : "str"
, "incremental" : false
, "options" : {"prop": {}}
, "tableName" : "str"
, "updateInterval" : "str"
, "lastUpdate" : 
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.create_view(materialized_view);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.createView(materializedView);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->createView(materialized_view);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /materialized-view/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|name|true|string||
|query|true|string||
|incremental|false|boolean||
|options|false|object||
|tableName|false|string||
|updateInterval|false|string||
|lastUpdate|false|string (date-time)||


## Delete materialized view
```shell
curl "api.rakam.io/materialized-view/delete"
  -H "master_key: mymaster_key"
-X POST -d '{
  "table_name" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.delete_view(table_name);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.deleteView(tableName);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->deleteView(table_name);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /materialized-view/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|false|string||


## Get view
```shell
curl "api.rakam.io/materialized-view/get"
  -H "read_key: myread_key"
-X POST -d '{
  "table_name" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.get_view(table_name);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.getView(tableName);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->getView(table_name);


```

> The above command returns JSON structured like this:

## List views
```shell
curl "api.rakam.io/materialized-view/list"
  -H "read_key: myread_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.list_views();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.listViews();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->listViews();


```

> The above command returns JSON structured like this:

## Get schemas
```shell
curl "api.rakam.io/materialized-view/schema"
  -H "read_key: myread_key"
-X POST -d '{
  "names" : [ "str" ]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.get_schema_of_view(names);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.getSchemaOfView(names);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->getSchemaOfView(names);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "fields" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : false,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ]
} ]
```

### HTTP Request
`POST /materialized-view/schema`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|names|false|multi string array||


## Update view
```shell
curl "api.rakam.io/materialized-view/update"
  -H "master_key: mymaster_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.update();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.update();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->update();


```

### HTTP Request
`GET /materialized-view/update`
# Continuous query


Continuous query

## Create stream
```shell
curl "api.rakam.io/continuous-query/create"
  -H "master_key: mymaster_key"
-X POST -d '{"name" : "str"
, "query" : "str"
, "options" : {"prop": {}}
, "tableName" : "str"
, "partitionKeys" : [
	"str"
]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.create_query(continuous_query);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.createQuery(continuousQuery);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->createQuery(continuous_query);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /continuous-query/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|name|true|string||
|query|true|string||
|options|false|object||
|tableName|false|string||
|partitionKeys|false|string array||


## Delete stream
```shell
curl "api.rakam.io/continuous-query/delete"
  -H "master_key: mymaster_key"
-X POST -d '{
  "table_name" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.delete_query(table_name);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.deleteQuery(tableName);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->deleteQuery(table_name);


```

> The above command returns JSON structured like this:

```json
{
  "success" : false,
  "message" : "str"
}
```

### HTTP Request
`POST /continuous-query/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|false|string||


## Get continuous query
```shell
curl "api.rakam.io/continuous-query/get"
  -H "read_key: myread_key"
-X POST -d '{
  "table_name" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.get_query(table_name);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.getQuery(tableName);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->getQuery(table_name);


```

> The above command returns JSON structured like this:

```json
{
  "name" : "str",
  "query" : "str",
  "options" : {
    "prop" : { }
  },
  "tableName" : "str",
  "partitionKeys" : [ "str" ]
}
```

### HTTP Request
`POST /continuous-query/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|false|string||


## List queries
```shell
curl "api.rakam.io/continuous-query/list"
  -H "read_key: myread_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.list_queries();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.listQueries();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->listQueries();


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "query" : "str",
  "options" : {
    "prop" : { }
  },
  "tableName" : "str",
  "partitionKeys" : [ "str" ]
} ]
```

### HTTP Request
`POST /continuous-query/list`
## Delete stream
```shell
curl "api.rakam.io/continuous-query/refresh"
  -H "master_key: mymaster_key"
-X POST -d '{ }'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.refresh_query();


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.refreshQuery();

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->refreshQuery();


```

### HTTP Request
`GET /continuous-query/refresh`
## Get query schema
```shell
curl "api.rakam.io/continuous-query/schema"
  -H "read_key: myread_key"
-X POST -d '{
  "names" : [ "str" ]
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.get_schema_of_query(names);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.getSchemaOfQuery(names);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->getSchemaOfQuery(names);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "fields" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : false,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ]
} ]
```

### HTTP Request
`POST /continuous-query/schema`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|names|false|multi string array||


## Test continuous query
```shell
curl "api.rakam.io/continuous-query/test"
  -H "read_key: myread_key"
-X POST -d '{
  "query" : "str"
}'
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("api.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.test_query(query);


```

```java
import org.rakam.client.ApiClient;
import org.rakam.client.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.testQuery(query);

```

```php


require_once('/path/to/org.rakam.client');

$api_client = new Swagger\Client\ApiClient('api.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->testQuery(query);


```

> The above command returns JSON structured like this:

```json
false
```

### HTTP Request
`POST /continuous-query/test`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|false|string||



## Definitions
### EventContext
|name|description|required|schema|default|
|----|----|----|----|----|
|apiKey||true|string||
|library||true|[Library](#library)||
|apiVersion||true|string||
|uploadTime||true|integer (int64)||
|checksum||true|string||
|plugins||true|[MappingPlugin](#mappingplugin) array||


### SchemaField
|name|description|required|schema|default|
|----|----|----|----|----|
|name||false|string||
|type||false|enum (STRING, INTEGER, DECIMAL, DOUBLE, LONG, BOOLEAN, DATE, TIME, TIMESTAMP, BINARY, ARRAY_STRING, ARRAY_INTEGER, ARRAY_DECIMAL, ARRAY_DOUBLE, ARRAY_LONG, ARRAY_BOOLEAN, ARRAY_DATE, ARRAY_TIME, ARRAY_TIMESTAMP, ARRAY_BINARY, MAP_STRING, MAP_INTEGER, MAP_DECIMAL, MAP_DOUBLE, MAP_LONG, MAP_BOOLEAN, MAP_DATE, MAP_TIME, MAP_TIMESTAMP, MAP_BINARY)||
|unique||false|boolean|false|
|descriptiveName||false|string||
|description||false|string||
|category||false|string||


### FunnelWindow
|name|description|required|schema|default|
|----|----|----|----|----|
|value||false|integer (int32)||
|type||false|enum (DAY, WEEK, MONTH)||


### User
|name|description|required|schema|default|
|----|----|----|----|----|
|id||true|object||
|api||true|[UserContext](#usercontext)||
|properties||true|object||


### UserContext
|name|description|required|schema|default|
|----|----|----|----|----|
|apiKey||true|string||
|apiLibrary||true|string||
|apiVersion||true|string||


### Measure
|name|description|required|schema|default|
|----|----|----|----|----|
|column||true|string||
|aggregation||true|enum (COUNT, COUNT_UNIQUE, SUM, MINIMUM, MAXIMUM, AVERAGE, APPROXIMATE_UNIQUE)||


### Event
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|collection||true|string||
|api||true|[EventContext](#eventcontext)||
|properties||true|object||


### RetentionAction
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||


### EventFilter
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||
|timeframe||false|[Timeframe](#timeframe)||
|aggregation||false|[EventFilterAggregation](#eventfilteraggregation)||
|filterExpression||false|string||


### Sorting
|name|description|required|schema|default|
|----|----|----|----|----|
|column||false|string||
|order||false|enum (asc, desc)||


### FunnelStep
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||


