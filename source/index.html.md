---
title: API Reference
language_tabs:
  - shell
  - java
  - php
  - python
toc_footers:
 - <a href='#'>Sign Up for a Developer Key</a>
includes:
    - errors
search: true
---
# Introduction

```
We have language bindings in java, php, python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.
```

An analytics platform API that lets you create your own analytics services.

### Version
Version: 0.5

## Contact Information
Email: contact@rakam.io

### License
License: Apache License 2.0

License url: http://www.apache.org/licenses/LICENSE-2.0.html

### URI scheme
Host: app.rakam.io
BasePath: /

# Event explorer


Event Explorer

## Perform simple query on event data
```shell
curl "app.rakam.io/event-explorer/analyze"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "measure" : {
    "column" : "str",
    "aggregation" : "str"
  },
  "grouping" : {
    "type" : "str",
    "value" : "str"
  },
  "segment" : {
    "type" : "str",
    "value" : "str"
  },
  "filterExpression" : "str",
  "startDate" : "2015-01-20",
  "endDate" : "2015-01-20",
  "collections" : [ "str" ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventexplorerApi();
api.analyze_events(analyze_request);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.EventexplorerApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventexplorerApi api = new EventexplorerApi(apiClient);
api.analyzeEvents(analyzeRequest);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventexplorerApi($api_client);
$api->analyzeEvents(analyze_request);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 1,
    "errorLine" : 1,
    "charPositionInLine" : 1
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : true
}
```

### HTTP Request
`POST /event-explorer/analyze`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|measure|false|[Measure](#measure)||
|grouping|false|[Reference](#reference)||
|segment|false|[Reference](#reference)||
|filterExpression|false|string||
|startDate|false|string (date)||
|endDate|false|string (date)||
|collections|false|string array||


### Responses for status codes
|200|403|
|----|----|
|[QueryResult](#queryresult)|[ErrorMessage](#errormessage)|


## Event statistics
```shell
curl "app.rakam.io/event-explorer/extra_dimensions"
  -H "read_key: myread_key"-X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventexplorerApi();
api.get_extra_dimensions();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.EventexplorerApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventexplorerApi api = new EventexplorerApi(apiClient);
api.getExtraDimensions();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventexplorerApi($api_client);
$api->getExtraDimensions();


```

> The above command returns JSON structured like this:

```json
{
  "prop" : { }
}
```

### HTTP Request
`GET /event-explorer/extra_dimensions`
### Responses for status codes
|200|403|
|----|----|
|object|[ErrorMessage](#errormessage)|


## Create Pre-computed table
```shell
curl "app.rakam.io/event-explorer/pre_calculate"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "collections" : [ "str" ],
  "dimensions" : [ "str" ],
  "aggregations" : [ "str" ],
  "measures" : [ "str" ],
  "tableName" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.EventexplorerApi();
api.create_precomputed_table(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.EventexplorerApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
EventexplorerApi api = new EventexplorerApi(apiClient);
api.createPrecomputedTable(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\EventexplorerApi($api_client);
$api->createPrecomputedTable(body);


```

> The above command returns JSON structured like this:

```json
{
  "name" : "str",
  "tableName" : "str"
}
```

### HTTP Request
`POST /event-explorer/pre_calculate`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|collections|true|string array||
|dimensions|true|string array||
|aggregations|true|enum (COUNT, COUNT_UNIQUE, SUM, MINIMUM, MAXIMUM, AVERAGE, APPROXIMATE_UNIQUE) array||
|measures|true|string array||
|tableName|true|string||


### Responses for status codes
|200|403|
|----|----|
|[PrecalculatedTable](#precalculatedtable)|[ErrorMessage](#errormessage)|


## Event statistics
```shell
curl "app.rakam.io/event-explorer/statistics"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "collections" : [ "str" ],
  "dimension" : "str",
  "startDate" : "2015-01-20",
  "endDate" : "2015-01-20"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventexplorerApi();
api.get_event_statistics(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.EventexplorerApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventexplorerApi api = new EventexplorerApi(apiClient);
api.getEventStatistics(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventexplorerApi($api_client);
$api->getEventStatistics(body);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 1,
    "errorLine" : 1,
    "charPositionInLine" : 1
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : true
}
```

### HTTP Request
`POST /event-explorer/statistics`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|collections|false|string array||
|dimension|false|string||
|startDate|true|string (date)||
|endDate|true|string (date)||


### Responses for status codes
|200|403|
|----|----|
|[QueryResult](#queryresult)|[ErrorMessage](#errormessage)|


# Funnel


Funnel Analyzer

## Execute query
```shell
curl "app.rakam.io/funnel/analyze"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "steps" : [ {
    "collection" : "str"
  } ],
  "dimension" : "str",
  "startDate" : "2015-01-20",
  "window" : {
    "value" : 1,
    "type" : "str"
  },
  "endDate" : "2015-01-20"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.FunnelApi();
api.analyze_funnel(funnel_query);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.FunnelApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
FunnelApi api = new FunnelApi(apiClient);
api.analyzeFunnel(funnelQuery);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

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
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 1,
    "errorLine" : 1,
    "charPositionInLine" : 1
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : true
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


### Responses for status codes
|200|403|
|----|----|
|[QueryResult](#queryresult)|[ErrorMessage](#errormessage)|


# Realtime


Realtime

## Create report
```shell
curl "app.rakam.io/realtime/create"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "name" : "str",
  "measures" : [ {
    "column" : "str",
    "aggregation" : "str"
  } ],
  "table_name" : "str",
  "collections" : [ "str" ],
  "filter" : "str",
  "dimensions" : [ "str" ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.RealtimeApi();
api.create_table(real_time_report);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.createTable(realTimeReport);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->createTable(real_time_report);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
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


### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


## Delete report
```shell
curl "app.rakam.io/realtime/delete"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "table_name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.RealtimeApi();
api.delete_table(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.deleteTable(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->deleteTable(body);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`POST /realtime/delete`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|true|string||


### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


## Get report
```shell
curl "app.rakam.io/realtime/get"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "table_name" : "str",
  "filter" : "str",
  "measure" : {
    "column" : "str",
    "aggregation" : "str"
  },
  "dimensions" : [ "str" ],
  "aggregate" : true,
  "date_start" : "2016-03-03T10:15:30.00Z",
  "date_end" : "2016-03-03T10:15:30.00Z"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.query_table(realtime_query_table);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.queryTable(realtimeQueryTable);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->queryTable(realtime_query_table);


```

> The above command returns JSON structured like this:

```json
{
  "start" : 1,
  "end" : 1,
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


### Responses for status codes
|200|400|403|
|----|----|----|
|[RealTimeQueryResult](#realtimequeryresult)|[ErrorMessage](#errormessage)|[ErrorMessage](#errormessage)|


## List queries
```shell
curl "app.rakam.io/realtime/list"
  -H "read_key: myread_key"-X POST
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.list_tables();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.listTables();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

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
### Responses for status codes
|200|403|
|----|----|
|[ContinuousQuery](#continuousquery) array|[ErrorMessage](#errormessage)|


# Retention


Retention Analyzer module

## Execute query
```shell
curl "app.rakam.io/retention/analyze"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "first_action" : {
    "collection" : "str"
  },
  "returning_action" : {
    "collection" : "str"
  },
  "dimension" : "str",
  "date_unit" : "str",
  "period" : 1,
  "startDate" : "2015-01-20",
  "endDate" : "2015-01-20"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RetentionApi();
api.analyze_retention(retention_query);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RetentionApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RetentionApi api = new RetentionApi(apiClient);
api.analyzeRetention(retentionQuery);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

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
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 1,
    "errorLine" : 1,
    "charPositionInLine" : 1
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : true
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


### Responses for status codes
|200|403|
|----|----|
|[QueryResult](#queryresult)|[ErrorMessage](#errormessage)|


# User


User

## Create multiple new users
```shell
curl "app.rakam.io/user/batch/create"
  -H "write_key: mywrite_key"-X POST -d @- << EOF 
{
  "users" : [ {
    "id" : "object",
    "api" : {
      "api_key" : "str",
      "library" : {
        "name" : "str",
        "version" : "str"
      },
      "upload_time" : 1,
      "checksum" : "str"
    },
    "properties" : "object"
  } ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.UserApi();
api.create_users(user_create_users);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.createUsers(userCreateUsers);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

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


### Responses for status codes
|200|403|
|----|----|
|object array|[ErrorMessage](#errormessage)|



Returns user ids. User id may be string or numeric.

## Create new user
```shell
curl "app.rakam.io/user/create"
-X POST -d @- << EOF 
{
  "id" : "object",
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "upload_time" : 1,
    "checksum" : "str"
  },
  "properties" : "object"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.UserApi();
api.create_user(user);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.createUser(user);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\UserApi($api_client);
$api->createUser(user);


```

> The above command returns JSON structured like this:

```json
1
```

### HTTP Request
`POST /user/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|id|false|object||
|api|false|[UserContext](#usercontext)||
|properties|false|object||


### Responses for status codes
|200|
|----|
|integer (int32)|


## Get events of the user
```shell
curl "app.rakam.io/user/create_segment"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "name" : "str",
  "table_name" : "str",
  "filter_expression" : "str",
  "event_filters" : [ {
    "collection" : "str",
    "timeframe" : {
      "start" : "2016-03-03T10:15:30.00Z",
      "end" : "2016-03-03T10:15:30.00Z"
    },
    "aggregation" : {
      "field" : "str",
      "minimum" : 1,
      "maximum" : 1,
      "type" : "str"
    },
    "filterExpression" : "str"
  } ],
  "cache_eviction" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.create_segment(user_create_segment);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.createSegment(userCreateSegment);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->createSegment(user_create_segment);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
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


### Responses for status codes
|200|403|404|
|----|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|[ErrorMessage](#errormessage)|


## Get user
```shell
curl "app.rakam.io/user/get"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "user" : "object"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.get_user(user_get_user);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.getUser(userGetUser);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->getUser(user_get_user);


```

> The above command returns JSON structured like this:

```json
{
  "id" : "object",
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "upload_time" : 1,
    "checksum" : "str"
  },
  "properties" : "object"
}
```

### HTTP Request
`POST /user/get`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|user|false|object||


### Responses for status codes
|200|403|404|
|----|----|----|
|[User](#user)|[ErrorMessage](#errormessage)|[ErrorMessage](#errormessage)|


## Get events of the user
```shell
curl "app.rakam.io/user/get_events"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "user" : "str",
  "limit" : 1,
  "offset" : "2016-03-03T10:15:30.00Z"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.get_events(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.getEvents(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->getEvents(body);


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
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|user|true|string||
|limit|false|integer (int32)||
|offset|false|string (date-time)||


### Responses for status codes
|200|403|404|
|----|----|----|
|[CollectionEvent](#collectionevent) array|[ErrorMessage](#errormessage)|[ErrorMessage](#errormessage)|


## Set user property
```shell
curl "app.rakam.io/user/increment_property"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "upload_time" : 1,
    "checksum" : "str"
  },
  "id" : "str",
  "property" : "str",
  "value" : 1.0
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.UserApi();
api.increment_property(user_increment_property);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.incrementProperty(userIncrementProperty);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->incrementProperty(user_increment_property);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
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


### Responses for status codes
|200|403|404|
|----|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|[ErrorMessage](#errormessage)|


## Merge user with anonymous id
```shell
curl "app.rakam.io/user/merge"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "user" : "str",
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "upload_time" : 1,
    "checksum" : "str"
  },
  "anonymous_id" : "str",
  "created_at" : "2016-03-03T10:15:30.00Z",
  "merged_at" : "2016-03-03T10:15:30.00Z"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.merge_user(user_merge_user);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.mergeUser(userMergeUser);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->mergeUser(user_merge_user);


```

> The above command returns JSON structured like this:

```json
true
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


### Responses for status codes
|200|403|404|
|----|----|----|
|boolean|[ErrorMessage](#errormessage)|[ErrorMessage](#errormessage)|


## Get user storage metadata
```shell
curl "app.rakam.io/user/metadata"
  -H "read_key: myread_key"-X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.get_metadata();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.getMetadata();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UserApi($api_client);
$api->getMetadata();


```

> The above command returns JSON structured like this:

```json
{
  "columns" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "identifierColumn" : "str"
}
```

### HTTP Request
`GET /user/metadata`
### Responses for status codes
|200|403|
|----|----|
|[MetadataResponse](#metadataresponse)|[ErrorMessage](#errormessage)|


## Search users
```shell
curl "app.rakam.io/user/search"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "columns" : [ "str" ],
  "filter" : "str",
  "event_filters" : [ {
    "collection" : "str",
    "timeframe" : {
      "start" : "2016-03-03T10:15:30.00Z",
      "end" : "2016-03-03T10:15:30.00Z"
    },
    "aggregation" : {
      "field" : "str",
      "minimum" : 1,
      "maximum" : 1,
      "type" : "str"
    },
    "filterExpression" : "str"
  } ],
  "sorting" : {
    "column" : "str",
    "order" : "str"
  },
  "offset" : "str",
  "limit" : 1
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UserApi();
api.search_users(user_search_users);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UserApi api = new UserApi(apiClient);
api.searchUsers(userSearchUsers);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

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
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 1,
    "errorLine" : 1,
    "charPositionInLine" : 1
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : true
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


### Responses for status codes
|200|403|
|----|----|
|[QueryResult](#queryresult)|[ErrorMessage](#errormessage)|


## Set user properties
```shell
curl "app.rakam.io/user/set_properties"
-X POST -d @- << EOF 
{
  "id" : "object",
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "upload_time" : 1,
    "checksum" : "str"
  },
  "properties" : "object"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.UserApi();
api.set_properties(user);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.setProperties(user);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\UserApi($api_client);
$api->setProperties(user);


```

> The above command returns JSON structured like this:

```json
1
```

### HTTP Request
`POST /user/set_properties`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|id|false|object||
|api|false|[UserContext](#usercontext)||
|properties|false|object||


### Responses for status codes
|200|404|
|----|----|
|integer (int32)|[ErrorMessage](#errormessage)|


## Set user properties once
```shell
curl "app.rakam.io/user/set_properties_once"
-X POST -d @- << EOF 
{
  "id" : "object",
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "upload_time" : 1,
    "checksum" : "str"
  },
  "properties" : "object"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.UserApi();
api.set_properties_once(user);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.setPropertiesOnce(user);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\UserApi($api_client);
$api->setPropertiesOnce(user);


```

> The above command returns JSON structured like this:

```json
1
```

### HTTP Request
`POST /user/set_properties_once`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|id|false|object||
|api|false|[UserContext](#usercontext)||
|properties|false|object||


### Responses for status codes
|200|404|
|----|----|
|integer (int32)|[ErrorMessage](#errormessage)|


## Unset user property
```shell
curl "app.rakam.io/user/unset_properties"
-X POST -d @- << EOF 
{
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "upload_time" : 1,
    "checksum" : "str"
  },
  "id" : "object",
  "properties" : [ "str" ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.UserApi();
api.unset_property(user_unset_property);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.unsetProperty(userUnsetProperty);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\UserApi($api_client);
$api->unsetProperty(user_unset_property);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
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


### Responses for status codes
|200|404|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


# User action


User Action

## Apply batch operation
```shell
curl "app.rakam.io/user/action/email/batch"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "filter" : "str",
  "event_filters" : [ {
    "collection" : "str",
    "timeframe" : {
      "start" : "2016-03-03T10:15:30.00Z",
      "end" : "2016-03-03T10:15:30.00Z"
    },
    "aggregation" : {
      "field" : "str",
      "minimum" : 1,
      "maximum" : 1,
      "type" : "str"
    },
    "filterExpression" : "str"
  } ],
  "config" : {
    "title" : "str",
    "content" : "str",
    "columnName" : "str",
    "defaultValues" : {
      "prop" : { }
    },
    "richText" : true
  }
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UseractionApi();
api.batch(user_email_action_batch);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UseractionApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UseractionApi api = new UseractionApi(apiClient);
api.batch(userEmailActionBatch);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UseractionApi($api_client);
$api->batch(user_email_action_batch);


```

> The above command returns JSON structured like this:

```json
1
```

### HTTP Request
`POST /user/action/email/batch`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|filter|false|string||
|event_filters|false|[EventFilter](#eventfilter) array||
|config|false|[EmailActionConfig](#emailactionconfig)||


### Responses for status codes
|200|403|
|----|----|
|integer (int64)|[ErrorMessage](#errormessage)|


## Perform action for single user
```shell
curl "app.rakam.io/user/action/email/single"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "user" : "str",
  "config" : {
    "title" : "str",
    "content" : "str",
    "columnName" : "str",
    "defaultValues" : {
      "prop" : { }
    },
    "richText" : true
  }
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UseractionApi();
api.send(user_email_action_send);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.UseractionApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UseractionApi api = new UseractionApi(apiClient);
api.send(userEmailActionSend);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UseractionApi($api_client);
$api->send(user_email_action_send);


```

> The above command returns JSON structured like this:

```json
true
```

### HTTP Request
`POST /user/action/email/single`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|user|false|string||
|config|false|[EmailActionConfig](#emailactionconfig)||


### Responses for status codes
|200|403|
|----|----|
|boolean|[ErrorMessage](#errormessage)|


# Recipe


Recipe

## Export recipe
```shell
curl "app.rakam.io/recipe/export"
  -H "master_key: mymaster_key"-X GET -d @- << EOF 
{
  "type" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.RecipeApi();
api.export_recipe(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RecipeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
RecipeApi api = new RecipeApi(apiClient);
api.exportRecipe(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\RecipeApi($api_client);
$api->exportRecipe(body);


```

> The above command returns JSON structured like this:

```json
{
  "strategy" : "str",
  "collections" : {
    "prop" : { }
  },
  "materialized_views" : [ {
    "table_name" : "str",
    "name" : "str",
    "query" : "str",
    "update_interval" : "str",
    "incremental" : true,
    "options" : {
      "prop" : { }
    },
    "last_update" : "2016-03-03T10:15:30.00Z"
  } ],
  "continuous_queries" : [ {
    "name" : "str",
    "query" : "str",
    "options" : {
      "prop" : { }
    },
    "tableName" : "str",
    "partitionKeys" : [ "str" ]
  } ]
}
```

### HTTP Request
`GET /recipe/export`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|type|false|enum (JSON, YAML)||


### Responses for status codes
|200|403|
|----|----|
|[Recipe](#recipe)|[ErrorMessage](#errormessage)|


## Install recipe
```shell
curl "app.rakam.io/recipe/install"
  -H "master_key: mymaster_key"-X POST
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.RecipeApi();
api.install_recipe();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RecipeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
RecipeApi api = new RecipeApi(apiClient);
api.installRecipe();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\RecipeApi($api_client);
$api->installRecipe();


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`POST /recipe/install`
### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


## Export recipe
```shell
curl "app.rakam.io/ui/recipe/export"
  -H "master_key: mymaster_key"-X GET -d @- << EOF 
{
  "type" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.RecipeApi();
api.export_ui_recipe(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RecipeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
RecipeApi api = new RecipeApi(apiClient);
api.exportUIRecipe(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\RecipeApi($api_client);
$api->exportUIRecipe(body);


```

> The above command returns JSON structured like this:

```json
{
  "custom_reports" : [ {
    "name" : "str",
    "data" : "object",
    "reportType" : "str"
  } ],
  "custom_pages" : [ {
    "name" : "str",
    "slug" : "str",
    "category" : "str",
    "files" : {
      "prop" : { }
    }
  } ],
  "dashboards" : [ {
    "name" : "str",
    "items" : [ {
      "id" : 1,
      "name" : "str",
      "directive" : "str",
      "data" : {
        "prop" : { }
      }
    } ]
  } ],
  "reports" : [ {
    "slug" : "str",
    "category" : "str",
    "name" : "str",
    "query" : "str",
    "options" : {
      "prop" : { }
    },
    "shared" : true,
    "hasPermission" : true,
    "userId" : 1
  } ]
}
```

### HTTP Request
`GET /ui/recipe/export`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|type|false|enum (JSON, YAML)||


### Responses for status codes
|200|403|
|----|----|
|[UIRecipe](#uirecipe)|[ErrorMessage](#errormessage)|


## Install recipe
```shell
curl "app.rakam.io/ui/recipe/install"
  -H "master_key: mymaster_key"-X POST
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.RecipeApi();
api.install_ui_recipe();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.RecipeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
RecipeApi api = new RecipeApi(apiClient);
api.installUIRecipe();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\RecipeApi($api_client);
$api->installUIRecipe();


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`POST /ui/recipe/install`
### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


# Admin


System related actions

## List installed modules
```shell
curl "app.rakam.io/admin/configurations"
  -H "master_key: mymaster_key"-X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.get_configurations();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.getConfigurations();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->getConfigurations();


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "description" : "str",
  "className" : "str",
  "isActive" : true,
  "condition" : {
    "property" : "str",
    "expectedValue" : "str"
  },
  "properties" : [ {
    "property" : "str",
    "defaultValue" : "str",
    "description" : "str"
  } ]
} ]
```

### HTTP Request
`GET /admin/configurations`
### Responses for status codes
|200|403|
|----|----|
|[ModuleDescriptor](#moduledescriptor) array|[ErrorMessage](#errormessage)|


## Check lock key
```shell
curl "app.rakam.io/admin/lock_key"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "lock_key" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.check_lock_key(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.checkLockKey(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->checkLockKey(body);


```

> The above command returns JSON structured like this:

```json
true
```

### HTTP Request
`POST /admin/lock_key`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|lock_key|false|string||


### Responses for status codes
|200|403|
|----|----|
|boolean|[ErrorMessage](#errormessage)|


## Get types
```shell
curl "app.rakam.io/admin/types"
  -H "master_key: mymaster_key"-X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.get_types();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.getTypes();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->getTypes();


```

> The above command returns JSON structured like this:

```json
{
  "prop" : { }
}
```

### HTTP Request
`GET /admin/types`
### Responses for status codes
|200|403|
|----|----|
|object|[ErrorMessage](#errormessage)|


## Create API Keys
```shell
curl "app.rakam.io/project/check-api-keys"
-X POST -d @- << EOF 
{
  "keys" : [ {
    "master_key" : "str",
    "read_key" : "str",
    "write_key" : "str"
  } ],
  "project" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.AdminApi();
api.check_api_keys(project_check_api_keys);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();

AdminApi api = new AdminApi(apiClient);
api.checkApiKeys(projectCheckApiKeys);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\AdminApi($api_client);
$api->checkApiKeys(project_check_api_keys);


```

> The above command returns JSON structured like this:

```json
[ true ]
```

### HTTP Request
`POST /project/check-api-keys`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|keys|false|[ProjectApiKeys](#projectapikeys) array||
|project|false|string||


### Responses for status codes
|200|
|----|
|boolean array|


## Get collection names
```shell
curl "app.rakam.io/project/collection"
  -H "read_key: myread_key"-X POST
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.collections();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.collections();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

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
### Responses for status codes
|200|403|
|----|----|
|string array|[ErrorMessage](#errormessage)|


## Create project
```shell
curl "app.rakam.io/project/create"
-X POST -d @- << EOF 
{
  "lock_key" : "str",
  "name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.AdminApi();
api.create_project(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();

AdminApi api = new AdminApi(apiClient);
api.createProject(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\AdminApi($api_client);
$api->createProject(body);


```

> The above command returns JSON structured like this:

```json
{
  "master_key" : "str",
  "read_key" : "str",
  "write_key" : "str"
}
```

### HTTP Request
`POST /project/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|lock_key|false|string||
|name|true|string||


### Responses for status codes
|200|
|----|
|[ProjectApiKeys](#projectapikeys)|


## Create API Keys
```shell
curl "app.rakam.io/project/create-api-keys"
  -H "master_key: mymaster_key"-X POST
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.create_api_keys();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.createApiKeys();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->createApiKeys();


```

> The above command returns JSON structured like this:

```json
{
  "master_key" : "str",
  "read_key" : "str",
  "write_key" : "str"
}
```

### HTTP Request
`POST /project/create-api-keys`
### Responses for status codes
|200|403|
|----|----|
|[ProjectApiKeys](#projectapikeys)|[ErrorMessage](#errormessage)|


## Delete project
```shell
curl "app.rakam.io/project/delete"
  -H "master_key: mymaster_key"-X DELETE
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.delete_project();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.deleteProject();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->deleteProject();


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`DELETE /project/delete`
### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


## List created projects
```shell
curl "app.rakam.io/project/list"
  -H "read_key: myread_key"-X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.get_projects();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.getProjects();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->getProjects();


```

> The above command returns JSON structured like this:

```json
[ "str" ]
```

### HTTP Request
`GET /project/list`
### Responses for status codes
|200|403|
|----|----|
|string array|[ErrorMessage](#errormessage)|


## Revoke API Keys
```shell
curl "app.rakam.io/project/revoke-api-keys"
  -H "master_key: mymaster_key"-X DELETE
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.revoke_api_keys();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.revokeApiKeys();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->revokeApiKeys();


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`DELETE /project/revoke-api-keys`
### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


## Get collection schema
```shell
curl "app.rakam.io/project/schema"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "names" : [ "str" ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.schema(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.schema(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->schema(body);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "fields" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ]
} ]
```

### HTTP Request
`POST /project/schema`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|names|false|string array||


### Responses for status codes
|200|403|
|----|----|
|[Collection](#collection) array|[ErrorMessage](#errormessage)|


## Add fields to collections
```shell
curl "app.rakam.io/project/schema/add"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "collection" : "str",
  "fields" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.add_fields_to_schema(project_add_fields_to_schema);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.addFieldsToSchema(projectAddFieldsToSchema);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->addFieldsToSchema(project_add_fields_to_schema);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "type" : "str",
  "unique" : true,
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


### Responses for status codes
|200|403|
|----|----|
|[SchemaField](#schemafield) array|[ErrorMessage](#errormessage)|


## Add fields to collections by transforming other schemas
```shell
curl "app.rakam.io/project/schema/add/custom"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "collection" : "str",
  "schema_type" : "str",
  "schema" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.add_custom_fields_to_schema(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.addCustomFieldsToSchema(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->addCustomFieldsToSchema(body);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "type" : "str",
  "unique" : true,
  "descriptiveName" : "str",
  "description" : "str",
  "category" : "str"
} ]
```

### HTTP Request
`POST /project/schema/add/custom`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|collection|true|string||
|schema_type|true|enum (AVRO)||
|schema|true|string||


### Responses for status codes
|200|403|
|----|----|
|[SchemaField](#schemafield) array|[ErrorMessage](#errormessage)|


## Get project stats
```shell
curl "app.rakam.io/project/stats"
-X POST -d @- << EOF 
[ "object" ]
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.AdminApi();
api.get_stats(project_get_stats);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.AdminApi;

ApiClient apiClient = new ApiClient();

AdminApi api = new AdminApi(apiClient);
api.getStats(projectGetStats);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


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


### Responses for status codes
|200|
|----|
|object|


# Collect


Collect data

## Collect multiple events
```shell
curl "app.rakam.io/event/batch"
-X POST -d @- << EOF 
{
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "api_version" : "str",
    "upload_time" : 1,
    "checksum" : "str",
    "plugins" : [ {
      "name" : "str",
      "arguments" : {
        "prop" : { }
      }
    } ]
  },
  "events" : [ {
    "collection" : "str",
    "api" : {
      "api_key" : "str",
      "library" : {
        "name" : "str",
        "version" : "str"
      },
      "api_version" : "str",
      "upload_time" : 1,
      "checksum" : "str",
      "plugins" : [ {
        "name" : "str",
        "arguments" : {
          "prop" : { }
        }
      } ]
    },
    "properties" : "object"
  } ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.CollectApi();
api.batch_events(event_list);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.CollectApi;

ApiClient apiClient = new ApiClient();

CollectApi api = new CollectApi(apiClient);
api.batchEvents(eventList);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\CollectApi($api_client);
$api->batchEvents(event_list);


```

> The above command returns JSON structured like this:

```json
1
```

### HTTP Request
`POST /event/batch`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|api|false|[EventContext](#eventcontext)||
|events|false|[Event](#event) array||


### Responses for status codes
|200|409|
|----|----|
|integer (int32)|integer (int32) array|



Returns 1 if the events are collected.

## Collect Bulk events
```shell
curl "app.rakam.io/event/bulk"
-X POST -d @- << EOF 
{
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "api_version" : "str",
    "upload_time" : 1,
    "checksum" : "str",
    "plugins" : [ {
      "name" : "str",
      "arguments" : {
        "prop" : { }
      }
    } ]
  },
  "events" : [ {
    "collection" : "str",
    "api" : {
      "api_key" : "str",
      "library" : {
        "name" : "str",
        "version" : "str"
      },
      "api_version" : "str",
      "upload_time" : 1,
      "checksum" : "str",
      "plugins" : [ {
        "name" : "str",
        "arguments" : {
          "prop" : { }
        }
      } ]
    },
    "properties" : "object"
  } ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.CollectApi();
api.bulk_events(event_list);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.CollectApi;

ApiClient apiClient = new ApiClient();

CollectApi api = new CollectApi(apiClient);
api.bulkEvents(eventList);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\CollectApi($api_client);
$api->bulkEvents(event_list);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`POST /event/bulk`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|api|false|[EventContext](#eventcontext)||
|events|false|[Event](#event) array||


### Responses for status codes
|200|
|----|
|[SuccessMessage](#successmessage)|



Bulk API requires master_key as api key and designed to handle large value of data. The endpoint also accepts application/avro and text/csv formats. You need need to set 'collection' and 'master_key' query parameters if the content-type is not application/json.

## Commit Bulk events
```shell
curl "app.rakam.io/event/bulk/commit"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "collections" : [ "str" ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.CollectApi();
api.commit_bulk_events(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.CollectApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
CollectApi api = new CollectApi(apiClient);
api.commitBulkEvents(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\CollectApi($api_client);
$api->commitBulkEvents(body);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`POST /event/bulk/commit`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|collections|true|string array||


### Responses for status codes
|200|403|409|
|----|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|[ErrorMessage](#errormessage)|


## Collect bulk events from remote
```shell
curl "app.rakam.io/event/bulk/remote"
-X POST -d @- << EOF 
{
  "collection" : "str",
  "urls" : [ "str" ],
  "type" : "str",
  "compression" : "str",
  "options" : {
    "prop" : { }
  }
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.CollectApi();
api.bulk_events_remote(bulk_event_remote);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.CollectApi;

ApiClient apiClient = new ApiClient();

CollectApi api = new CollectApi(apiClient);
api.bulkEventsRemote(bulkEventRemote);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\CollectApi($api_client);
$api->bulkEventsRemote(bulk_event_remote);


```

> The above command returns JSON structured like this:

```json
1
```

### HTTP Request
`POST /event/bulk/remote`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|collection|false|string||
|urls|false|string array||
|type|false|enum (AVRO, CSV, JSON)||
|compression|false|enum (GZIP)||
|options|false|object||


### Responses for status codes
|200|409|
|----|----|
|integer (int32)|integer (int32) array|


## Collect event
```shell
curl "app.rakam.io/event/collect"
-X POST -d @- << EOF 
{
  "collection" : "str",
  "api" : {
    "api_key" : "str",
    "library" : {
      "name" : "str",
      "version" : "str"
    },
    "api_version" : "str",
    "upload_time" : 1,
    "checksum" : "str",
    "plugins" : [ {
      "name" : "str",
      "arguments" : {
        "prop" : { }
      }
    } ]
  },
  "properties" : "object"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")

api = client.CollectApi();
api.collect_event(event);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.CollectApi;

ApiClient apiClient = new ApiClient();

CollectApi api = new CollectApi(apiClient);
api.collectEvent(event);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');


$api = new Swagger\Client\CollectApi($api_client);
$api->collectEvent(event);


```

> The above command returns JSON structured like this:

```json
1
```

### HTTP Request
`POST /event/collect`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|collection|true|string||
|api|true|[EventContext](#eventcontext)||
|properties|true|object||


### Responses for status codes
|200|
|----|
|integer (int32)|


# Query


Analyze data

## Execute query on event data-set
```shell
curl "app.rakam.io/query/execute"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "query" : "str",
  "export_type" : "str",
  "limit" : 1
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.QueryApi();
api.execute(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.QueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
QueryApi api = new QueryApi(apiClient);
api.execute(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\QueryApi($api_client);
$api->execute(body);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 1,
    "errorLine" : 1,
    "charPositionInLine" : 1
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : true
}
```

### HTTP Request
`POST /query/execute`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|true|string||
|export_type|true|enum (AVRO, CSV, JSON)||
|limit|false|integer (int32)||


### Responses for status codes
|200|403|
|----|----|
|[QueryResult](#queryresult)|[ErrorMessage](#errormessage)|


## Explain query
```shell
curl "app.rakam.io/query/explain"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "query" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.QueryApi();
api.explain(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.QueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
QueryApi api = new QueryApi(apiClient);
api.explain(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\QueryApi($api_client);
$api->explain(body);


```

> The above command returns JSON structured like this:

```json
{
  "groupBy" : [ {
    "index" : 1,
    "expression" : "str"
  } ],
  "orderBy" : [ {
    "ordering" : "str",
    "index" : 1,
    "expression" : "str"
  } ],
  "limit" : 1
}
```

### HTTP Request
`POST /query/explain`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|true|string|Query|


### Responses for status codes
|200|403|
|----|----|
|[ResponseQuery](#responsequery)|[ErrorMessage](#errormessage)|


## Test query
```shell
curl "app.rakam.io/query/metadata"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "query" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.QueryApi();
api.metadata(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.QueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
QueryApi api = new QueryApi(apiClient);
api.metadata(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\QueryApi($api_client);
$api->metadata(body);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "type" : "str",
  "unique" : true,
  "descriptiveName" : "str",
  "description" : "str",
  "category" : "str"
} ]
```

### HTTP Request
`POST /query/metadata`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|true|string||


### Responses for status codes
|200|403|
|----|----|
|[SchemaField](#schemafield) array|[ErrorMessage](#errormessage)|


# Materialized view


Materialized view

## Create view
```shell
curl "app.rakam.io/materialized-view/create"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "table_name" : "str",
  "name" : "str",
  "query" : "str",
  "update_interval" : "str",
  "incremental" : true,
  "options" : {
    "prop" : { }
  },
  "last_update" : "2016-03-03T10:15:30.00Z"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.create_view(materialized_view);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.createView(materializedView);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->createView(materialized_view);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`POST /materialized-view/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|true|string||
|name|true|string||
|query|true|string||
|update_interval|false|string||
|incremental|false|boolean||
|options|false|object||
|last_update|false|string (date-time)||


### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


## Delete materialized view
```shell
curl "app.rakam.io/materialized-view/delete"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "table_name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.delete_view(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.deleteView(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->deleteView(body);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`POST /materialized-view/delete`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|true|string||


### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


## Get view
```shell
curl "app.rakam.io/materialized-view/get"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "table_name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.get_view(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.getView(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->getView(body);


```

> The above command returns JSON structured like this:

```json
{
  "table_name" : "str",
  "name" : "str",
  "query" : "str",
  "update_interval" : "str",
  "incremental" : true,
  "options" : {
    "prop" : { }
  },
  "last_update" : "2016-03-03T10:15:30.00Z"
}
```

### HTTP Request
`POST /materialized-view/get`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|true|string||


### Responses for status codes
|200|403|
|----|----|
|[MaterializedView](#materializedview)|[ErrorMessage](#errormessage)|


## List views
```shell
curl "app.rakam.io/materialized-view/list"
  -H "read_key: myread_key"-X POST
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.list_views();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.listViews();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->listViews();


```

> The above command returns JSON structured like this:

```json
[ {
  "table_name" : "str",
  "name" : "str",
  "query" : "str",
  "update_interval" : "str",
  "incremental" : true,
  "options" : {
    "prop" : { }
  },
  "last_update" : "2016-03-03T10:15:30.00Z"
} ]
```

### HTTP Request
`POST /materialized-view/list`
### Responses for status codes
|200|403|
|----|----|
|[MaterializedView](#materializedview) array|[ErrorMessage](#errormessage)|


## Get schemas
```shell
curl "app.rakam.io/materialized-view/schema"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "names" : [ "str" ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.get_schema_of_view(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.getSchemaOfView(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->getSchemaOfView(body);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "fields" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ]
} ]
```

### HTTP Request
`POST /materialized-view/schema`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|names|false|string array||


### Responses for status codes
|200|403|
|----|----|
|[MaterializedViewSchema](#materializedviewschema) array|[ErrorMessage](#errormessage)|


# Continuous query


Continuous query

## Create stream
```shell
curl "app.rakam.io/continuous-query/create"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "name" : "str",
  "query" : "str",
  "options" : {
    "prop" : { }
  },
  "tableName" : "str",
  "partitionKeys" : [ "str" ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.create_query(continuous_query);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.createQuery(continuousQuery);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->createQuery(continuous_query);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
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


### Responses for status codes
|200|400|403|
|----|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|[ErrorMessage](#errormessage)|



Creates a new continuous query for specified SQL query.
Rakam will process data in batches keep the result of query in-memory all the time.
Compared to reports, continuous queries continuously aggregate the data on the fly and the result is always available either in-memory or disk.

## Delete stream
```shell
curl "app.rakam.io/continuous-query/delete"
  -H "master_key: mymaster_key"-X POST -d @- << EOF 
{
  "table_name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.delete_query(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.deleteQuery(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->deleteQuery(body);


```

> The above command returns JSON structured like this:

```json
{
  "message" : "str",
  "success" : true
}
```

### HTTP Request
`POST /continuous-query/delete`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|true|string||


### Responses for status codes
|200|403|
|----|----|
|[SuccessMessage](#successmessage)|[ErrorMessage](#errormessage)|


## Get continuous query
```shell
curl "app.rakam.io/continuous-query/get"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "table_name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.get_query(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.getQuery(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->getQuery(body);


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
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|table_name|true|string||


### Responses for status codes
|200|403|
|----|----|
|[ContinuousQuery](#continuousquery)|[ErrorMessage](#errormessage)|


## List queries
```shell
curl "app.rakam.io/continuous-query/list"
  -H "read_key: myread_key"-X POST
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.list_queries();


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.listQueries();

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

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
### Responses for status codes
|200|403|
|----|----|
|[ContinuousQuery](#continuousquery) array|[ErrorMessage](#errormessage)|


## Get query schema
```shell
curl "app.rakam.io/continuous-query/schema"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "names" : [ "str" ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.get_schema_of_query(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.getSchemaOfQuery(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->getSchemaOfQuery(body);


```

> The above command returns JSON structured like this:

```json
[ {
  "name" : "str",
  "fields" : [ {
    "name" : "str",
    "type" : "str",
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ]
} ]
```

### HTTP Request
`POST /continuous-query/schema`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|names|false|string array||


### Responses for status codes
|200|403|
|----|----|
|[Collection](#collection) array|[ErrorMessage](#errormessage)|


## Test continuous query
```shell
curl "app.rakam.io/continuous-query/test"
  -H "read_key: myread_key"-X POST -d @- << EOF 
{
  "query" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("app.rakam.io")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.test_query(body);


```

```java
import io.rakam.client.api.ApiClient;
import io.rakam.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.testQuery(body);

```

```php


require_once('/path/to/io.rakam.client.api');

$api_client = new Swagger\Client\ApiClient('app.rakam.io');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->testQuery(body);


```

> The above command returns JSON structured like this:

```json
true
```

### HTTP Request
`POST /continuous-query/test`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|true|string||


### Responses for status codes
|200|403|
|----|----|
|boolean|[ErrorMessage](#errormessage)|



## Definitions
### User
|name|description|required|schema|default|
|----|----|----|----|----|
|id||false|object||
|api||false|[UserContext](#usercontext)||
|properties||false|object||


### Recipe
|name|description|required|schema|default|
|----|----|----|----|----|
|strategy||false|enum (DEFAULT, SPECIFIC)||
|collections||false|object||
|materialized_views||false|[MaterializedView](#materializedview) array||
|continuous_queries||false|[ContinuousQuery](#continuousquery) array||


### RealTimeQueryResult
|name|description|required|schema|default|
|----|----|----|----|----|
|start||false|integer (int64)||
|end||false|integer (int64)||
|result||false|object||


### FunnelWindow
|name|description|required|schema|default|
|----|----|----|----|----|
|value||false|integer (int32)||
|type||false|enum (DAY, WEEK, MONTH)||


### QueryResult
|name|description|required|schema|default|
|----|----|----|----|----|
|metadata||true|[SchemaField](#schemafield) array||
|result|Each row is an array that contains the values for the columns that are defined in metadata property.|false|object array array||
|error||true|[QueryError](#queryerror)||
|properties||true|object||
|failed||false|boolean|false|


### ContinuousQuery
|name|description|required|schema|default|
|----|----|----|----|----|
|name||true|string||
|query||true|string||
|options||false|object||
|tableName||false|string||
|partitionKeys||false|string array||


### UIRecipe
|name|description|required|schema|default|
|----|----|----|----|----|
|custom_reports||false|[CustomReport](#customreport) array||
|custom_pages||false|[Page](#page) array||
|dashboards||false|[DashboardBuilder](#dashboardbuilder) array||
|reports||false|[Report](#report) array||


### SuccessMessage
|name|description|required|schema|default|
|----|----|----|----|----|
|message||true|string||
|success||false|boolean|false|


### MetadataResponse
|name|description|required|schema|default|
|----|----|----|----|----|
|columns||false|[SchemaField](#schemafield) array||
|identifierColumn||false|string||


### Measure
|name|description|required|schema|default|
|----|----|----|----|----|
|column||true|string||
|aggregation||true|enum (COUNT, COUNT_UNIQUE, SUM, MINIMUM, MAXIMUM, AVERAGE, APPROXIMATE_UNIQUE)||


### UserContext
|name|description|required|schema|default|
|----|----|----|----|----|
|api_key||true|string||
|library||true|[Library](#library)||
|upload_time||true|integer (int64)||
|checksum||true|string||


### Reference
|name|description|required|schema|default|
|----|----|----|----|----|
|type||false|enum (COLUMN, REFERENCE)||
|value||false|string||


### CollectionEvent
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||
|properties||false|object||


### PrecalculatedTable
|name|description|required|schema|default|
|----|----|----|----|----|
|name||false|string||
|tableName||false|string||


### EmailActionConfig
|name|description|required|schema|default|
|----|----|----|----|----|
|title||false|string||
|content||false|string||
|columnName||false|string||
|defaultValues||false|object||
|richText||false|boolean|false|


### RetentionAction
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||


### ResponseQuery
|name|description|required|schema|default|
|----|----|----|----|----|
|groupBy||false|[GroupBy](#groupby) array||
|orderBy||false|[Ordering](#ordering) array||
|limit||false|integer (int64)||


### EventFilter
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||
|timeframe||false|[Timeframe](#timeframe)||
|aggregation||false|[EventFilterAggregation](#eventfilteraggregation)||
|filterExpression||false|string||


### ProjectApiKeys
|name|description|required|schema|default|
|----|----|----|----|----|
|master_key||false|string||
|read_key||false|string||
|write_key||false|string||


### Sorting
|name|description|required|schema|default|
|----|----|----|----|----|
|column||false|string||
|order||false|enum (asc, desc)||


### EventContext
|name|description|required|schema|default|
|----|----|----|----|----|
|api_key||true|string||
|library||true|[Library](#library)||
|api_version||true|string||
|upload_time||true|integer (int64)||
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


### ModuleDescriptor
|name|description|required|schema|default|
|----|----|----|----|----|
|name||false|string||
|description||false|string||
|className||false|string||
|isActive||false|boolean|false|
|condition||false|[Condition](#condition)||
|properties||false|[ConfigItem](#configitem) array||


### MaterializedViewSchema
|name|description|required|schema|default|
|----|----|----|----|----|
|name||false|string||
|fields||false|[SchemaField](#schemafield) array||


### Event
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||true|string||
|api||true|[EventContext](#eventcontext)||
|properties||true|object||


### Collection
|name|description|required|schema|default|
|----|----|----|----|----|
|name||false|string||
|fields||false|[SchemaField](#schemafield) array||


### MaterializedView
|name|description|required|schema|default|
|----|----|----|----|----|
|table_name||true|string||
|name||true|string||
|query||true|string||
|update_interval||false|string||
|incremental||false|boolean|false|
|options||false|object||
|last_update||false|string (date-time)||


### ErrorMessage
|name|description|required|schema|default|
|----|----|----|----|----|
|error||false|string||
|error_code||false|integer (int32)||


### FunnelStep
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||


