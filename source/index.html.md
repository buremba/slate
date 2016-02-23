---
title: API Reference
language_tabs:
  - shell
  - java
  - python
  - php
toc_footers:
 - <a href='#'>Sign Up for a Developer Key (Not ready yet)</a>
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
Version: 0.3

## Contact Information
Email: contact@rakam.com

### License
License: Apache License 2.0

License url: http://www.apache.org/licenses/LICENSE-2.0.html

### URI scheme
Host: app.getrakam.com
BasePath: /

# Ab testing


A/B Testing Module

## Create test
```shell
curl "app.getrakam.com/ab-testing/create"
  -H "master_key: mymaster_key"
-X POST -d '{"project" : "str"
, "name" : "str"
, "variants" : [
  "name" : "str", "weight" : 0, "data" : null
]
, "goal" : "collection" : "str", "filter" : "str"
, "options" : null
, "id" : 0
, "collectionName" : "str"
, "connectorField" : "str"
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AbtestingApi();
api.ab_testing_create(ab_testing_report);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AbtestingApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AbtestingApi api = new AbtestingApi();
api.abTestingCreate(aBTestingReport);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AbtestingApi($api_client);
$api->abTestingCreate(ab_testing_report);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /ab-testing/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|variants|false|[Variant](#variant) array||
|goal|false|[Goal](#goal)||
|options|false|object||
|id|false|integer (int32)||
|collectionName|false|string||
|connectorField|false|string||


## Delete report
```shell
curl "app.getrakam.com/ab-testing/delete"
  -H "master_key: mymaster_key"
-X POST -d '{"project" : "str", "id" : 0}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AbtestingApi();
api.ab_testing_delete(project, id);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AbtestingApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AbtestingApi api = new AbtestingApi();
api.abTestingDelete(project, id);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AbtestingApi($api_client);
$api->abTestingDelete(project, id);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /ab-testing/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|id|false|integer (int32)||


## Get report
```shell
curl "app.getrakam.com/ab-testing/get"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "id" : 0}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AbtestingApi();
api.ab_testing_get(project, id);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AbtestingApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AbtestingApi api = new AbtestingApi();
api.abTestingGet(project, id);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AbtestingApi($api_client);
$api->abTestingGet(project, id);


```

> The above command returns JSON structured like this:

```json
{
"project" : "str", "name" : "str", "variants" : [
  "name" : "str", "weight" : 0, "data" : null
], "goal" : "collection" : "str", "filter" : "str", "options" : null, "id" : 0, "collectionName" : "str", "connectorField" : "str"
}
```

### HTTP Request
`POST /ab-testing/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|id|false|integer (int32)||


## List reports
```shell
curl "app.getrakam.com/ab-testing/list"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AbtestingApi();
api.ab_testing_list(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AbtestingApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AbtestingApi api = new AbtestingApi();
api.abTestingList(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AbtestingApi($api_client);
$api->abTestingList(project);


```

> The above command returns JSON structured like this:

```json
{
[
  "project" : "str", "name" : "str", "variants" : [
  "name" : "str", "weight" : 0, "data" : null
], "goal" : "collection" : "str", "filter" : "str", "options" : null, "id" : 0, "collectionName" : "str", "connectorField" : "str"
]
}
```

### HTTP Request
`POST /ab-testing/list`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


## Update report
```shell
curl "app.getrakam.com/ab-testing/update"
  -H "master_key: mymaster_key"
-X POST -d '{"project" : "str"
, "name" : "str"
, "variants" : [
  "name" : "str", "weight" : 0, "data" : null
]
, "goal" : "collection" : "str", "filter" : "str"
, "options" : null
, "id" : 0
, "collectionName" : "str"
, "connectorField" : "str"
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AbtestingApi();
api.ab_testing_update(ab_testing_report);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AbtestingApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AbtestingApi api = new AbtestingApi();
api.abTestingUpdate(aBTestingReport);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AbtestingApi($api_client);
$api->abTestingUpdate(ab_testing_report);


```

> The above command returns JSON structured like this:

```json
{
"project" : "str", "name" : "str", "variants" : [
  "name" : "str", "weight" : 0, "data" : null
], "goal" : "collection" : "str", "filter" : "str", "options" : null, "id" : 0, "collectionName" : "str", "connectorField" : "str"
}
```

### HTTP Request
`POST /ab-testing/update`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|variants|false|[Variant](#variant) array||
|goal|false|[Goal](#goal)||
|options|false|object||
|id|false|integer (int32)||
|collectionName|false|string||
|connectorField|false|string||


# Funnel


Funnel Analyzer module

## Execute query
```shell
curl "app.getrakam.com/funnel/analyze"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str"
, "connector_field" : "str"
, "steps" : [
  "collection" : "str", "filterExpression" : "str"
]
, "dimension" : "str"
, "startDate" : "2015-01-20"
, "endDate" : "2015-01-20"
, "enableOtherGrouping" : false
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.FunnelApi();
api.funnel_analyzer_analyze(funnel_query);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.FunnelApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
FunnelApi api = new FunnelApi();
api.funnelAnalyzerAnalyze(funnelQuery);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\FunnelApi($api_client);
$api->funnelAnalyzerAnalyze(funnel_query);


```

> The above command returns JSON structured like this:

```json
{
"metadata" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
], "result" : [
  [
  null
]
], "error" : "message" : "str", "sqlState" : "str", "errorCode" : 0, "errorLine" : 0, "charPositionInLine" : 0, "properties" : {"prop": value}, "failed" : false
}
```

### HTTP Request
`POST /funnel/analyze`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|connector_field|false|string||
|steps|false|[FunnelStep](#funnelstep) array||
|dimension|false|string||
|startDate|false|string (date)||
|endDate|false|string (date)||
|enableOtherGrouping|false|boolean||


# Realtime




## Create report
```shell
curl "app.getrakam.com/realtime/create"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "name" : "str", "aggregation" : "str", "table_name" : "str", "collections" : [
  "str"
], "filter" : "str", "measure" : "str", "dimensions" : [
  "str"
]}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.realtime_create(project, name, aggregation, table_name, collections, filter, measure, dimensions);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi();
api.realtimeCreate(project, name, aggregation, tableName, collections, filter, measure, dimensions);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->realtimeCreate(project, name, aggregation, table_name, collections, filter, measure, dimensions);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /realtime/create`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|aggregation|false|string||
|table_name|false|string||
|collections|false|multi string array||
|filter|false|string||
|measure|false|string||
|dimensions|false|multi string array||


## Delete report
```shell
curl "app.getrakam.com/realtime/delete"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "table_name" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.realtime_delete(project, table_name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi();
api.realtimeDelete(project, tableName);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->realtimeDelete(project, table_name);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /realtime/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|table_name|false|string||


## Get report
```shell
curl "app.getrakam.com/realtime/get"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "table_name" : "str", "filter" : "str", "dimensions" : [
  "str"
], "aggregate" : false, "date_start" : "str", "date_end" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.realtime_get(project, table_name, filter, dimensions, aggregate, date_start, date_end);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi();
api.realtimeGet(project, tableName, filter, dimensions, aggregate, dateStart, dateEnd);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->realtimeGet(project, table_name, filter, dimensions, aggregate, date_start, date_end);


```

> The above command returns JSON structured like this:

```json
{
"start" : 0, "end" : 0, "result" : null
}
```

### HTTP Request
`POST /realtime/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|table_name|false|string||
|filter|false|string||
|dimensions|false|multi string array||
|aggregate|false|boolean||
|date_start|false|string (date-time)||
|date_end|false|string (date-time)||


## List queries
```shell
curl "app.getrakam.com/realtime/list"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.realtime_list(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi();
api.realtimeList(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->realtimeList(project);


```

> The above command returns JSON structured like this:

```json
{
[
  "project" : "str", "name" : "str", "query" : "str", "options" : {"prop": value}, "tableName" : "str", "partitionKeys" : [
  "str"
]
]
}
```

### HTTP Request
`POST /realtime/list`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


# Retention


Retention Analyzer module

## Execute query
```shell
curl "app.getrakam.com/retention/analyze"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str"
, "connector_field" : "str"
, "first_action" : "collection" : "str"
, "returning_action" : "collection" : "str"
, "dimension" : "str"
, "date_unit" : "str"
, "startDate" : "2015-01-20"
, "endDate" : "2015-01-20"
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RetentionApi();
api.retention_analyzer_execute(retention_query);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RetentionApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RetentionApi api = new RetentionApi();
api.retentionAnalyzerExecute(retentionQuery);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RetentionApi($api_client);
$api->retentionAnalyzerExecute(retention_query);


```

> The above command returns JSON structured like this:

```json
{
"metadata" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
], "result" : [
  [
  null
]
], "error" : "message" : "str", "sqlState" : "str", "errorCode" : 0, "errorLine" : 0, "charPositionInLine" : 0, "properties" : {"prop": value}, "failed" : false
}
```

### HTTP Request
`POST /retention/analyze`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|connector_field|false|string||
|first_action|false|[RetentionAction](#retentionaction)||
|returning_action|false|[RetentionAction](#retentionaction)||
|dimension|false|string||
|date_unit|false|enum (DAY, WEEK, MONTH)||
|startDate|false|string (date)||
|endDate|false|string (date)||


# Event stream


Event Stream Module

# User


User module for Rakam

## Get events of the user
```shell
curl "app.getrakam.com/user/create_segment"
-X POST -d '{"project" : "str"
, "name" : "str"
, "table_name" : "str"
, "filter_expression" : "str"
, "event_filters" : [
  "collection" : "str", "timeframe" : "start" : null, "end" : null, "aggregation" : "field" : "str", "minimum" : 0, "maximum" : 0, "type" : "str", "filterExpression" : "str"
]
, "cache_eviction" : "str"
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_create_segment(user_create_segment);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userCreateSegment(userCreateSegment);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userCreateSegment(user_create_segment);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /user/create_segment`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|table_name|false|string||
|filter_expression|false|string||
|event_filters|false|[EventFilter](#eventfilter) array||
|cache_eviction|false|string||


## Get user
```shell
curl "app.getrakam.com/user/get"
-X POST -d '{"project" : "str", "user" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_get_user(project, user);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userGetUser(project, user);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userGetUser(project, user);


```

> The above command returns JSON structured like this:

```json
{
"project" : "str", "id" : "str", "api" : "writeKey" : "str", "apiVersion" : "str", "properties" : {"prop": value}
}
```

### HTTP Request
`POST /user/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||


## Get events of the user
```shell
curl "app.getrakam.com/user/get_events"
-X POST -d '{"project" : "str", "user" : "str", "limit" : 0, "offset" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_get_events(project, user, limit, offset);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userGetEvents(project, user, limit, offset);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userGetEvents(project, user, limit, offset);


```

> The above command returns JSON structured like this:

```json
{
[
  "collection" : "str", "properties" : {"prop": value}
]
}
```

### HTTP Request
`POST /user/get_events`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|limit|false|integer (int32)||
|offset|false|string (date-time)||


## Set user property
```shell
curl "app.getrakam.com/user/increment_property"
-X POST -d '{"project" : "str"
, "api" : "writeKey" : "str", "apiVersion" : "str"
, "user" : "str"
, "property" : "str"
, "" : 0.0
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_increment_property(user_increment_property);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userIncrementProperty(userIncrementProperty);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userIncrementProperty(user_increment_property);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /user/increment_property`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|api|false|[UserContext](#usercontext)||
|user|false|string||
|property|false|string||
||false|number (double)||


## Merge user with anonymous id
```shell
curl "app.getrakam.com/user/merge"
-X POST -d '{"project" : "str"
, "user" : "str"
, "api" : "writeKey" : "str", "apiVersion" : "str"
, "anonymous_id" : "str"
, "created_at" : null
, "merged_at" : null
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_merge_user(user_merge_user);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userMergeUser(userMergeUser);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userMergeUser(user_merge_user);


```

> The above command returns JSON structured like this:

```json
{
false
}
```

### HTTP Request
`POST /user/merge`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|api|false|[UserContext](#usercontext)||
|anonymous_id|false|string||
|created_at|false|string (date-time)||
|merged_at|false|string (date-time)||


## Get user storage metadata
```shell
curl "app.getrakam.com/user/metadata"
-X POST -d '{"project" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_get_metadata(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userGetMetadata(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userGetMetadata(project);


```

> The above command returns JSON structured like this:

```json
{
"columns" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
], "identifierColumn" : "str"
}
```

### HTTP Request
`POST /user/metadata`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


## Search users
```shell
curl "app.getrakam.com/user/search"
-X POST -d '{"project" : "str"
, "columns" : [
  "str"
]
, "filter" : "str"
, "event_filters" : [
  "collection" : "str", "timeframe" : "start" : null, "end" : null, "aggregation" : "field" : "str", "minimum" : 0, "maximum" : 0, "type" : "str", "filterExpression" : "str"
]
, "sorting" : "column" : "str", "order" : "str"
, "offset" : "str"
, "limit" : 0
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_search_users(user_search_users);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userSearchUsers(userSearchUsers);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userSearchUsers(user_search_users);


```

> The above command returns JSON structured like this:

```json
{
"metadata" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
], "result" : [
  [
  null
]
], "error" : "message" : "str", "sqlState" : "str", "errorCode" : 0, "errorLine" : 0, "charPositionInLine" : 0, "properties" : {"prop": value}, "failed" : false
}
```

### HTTP Request
`POST /user/search`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|columns|false|string array||
|filter|false|string||
|event_filters|false|[EventFilter](#eventfilter) array||
|sorting|false|[Sorting](#sorting)||
|offset|false|string||
|limit|false|integer (int32)||


## Set user properties
```shell
curl "app.getrakam.com/user/set_properties"
-X POST -d '{"project" : "str"
, "user" : "str"
, "api" : "writeKey" : "str", "apiVersion" : "str"
, "properties" : {"prop": value}
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_set_properties(set_user_properties);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userSetProperties(setUserProperties);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userSetProperties(set_user_properties);


```

> The above command returns JSON structured like this:

```json
{
0
}
```

### HTTP Request
`POST /user/set_properties`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|api|false|[UserContext](#usercontext)||
|properties|false|object||


## Set user properties once
```shell
curl "app.getrakam.com/user/set_properties_once"
-X POST -d '{"project" : "str"
, "user" : "str"
, "api" : "writeKey" : "str", "apiVersion" : "str"
, "properties" : {"prop": value}
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_set_properties_once(set_user_properties);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userSetPropertiesOnce(setUserProperties);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userSetPropertiesOnce(set_user_properties);


```

### HTTP Request
`POST /user/set_properties_once`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|api|false|[UserContext](#usercontext)||
|properties|false|object||


## Unset user property
```shell
curl "app.getrakam.com/user/unset_properties"
-X POST -d '{"project" : "str"
, "api" : "writeKey" : "str", "apiVersion" : "str"
, "user" : "str"
, "property" : [
  "str"
]
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.UserApi();
api.user_unset_property(user_unset_property);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi();
api.userUnsetProperty(userUnsetProperty);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->userUnsetProperty(user_unset_property);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /user/unset_properties`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|api|false|[UserContext](#usercontext)||
|user|false|string||
|property|false|string array||


# User mailbox




## Get user mailbox
```shell
curl "app.getrakam.com/user/mailbox/get"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "user" : "str", "parent" : 0, "limit" : 0, "offset" : 0}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UsermailboxApi();
api.user_mailbox_get(project, user, parent, limit, offset);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UsermailboxApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UsermailboxApi api = new UsermailboxApi();
api.userMailboxGet(project, user, parent, limit, offset);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UsermailboxApi($api_client);
$api->userMailboxGet(project, user, parent, limit, offset);


```

> The above command returns JSON structured like this:

```json
{
[
  [
  "id" : 0, "content" : "str", "from_user" : null, "to_user" : null, "parentId" : 0, "seen" : false, "time" : 0, "project" : "str"
]
]
}
```

### HTTP Request
`POST /user/mailbox/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|parent|false|integer (int32)||
|limit|false|integer (int32)||
|offset|false|integer (int64)||



Returns the last mails sent to the user

## Get connected users
```shell
curl "app.getrakam.com/user/mailbox/get_online_users"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UsermailboxApi();
api.user_mailbox_get_connected_users(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UsermailboxApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UsermailboxApi api = new UsermailboxApi();
api.userMailboxGetConnectedUsers(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UsermailboxApi($api_client);
$api->userMailboxGetConnectedUsers(project);


```

> The above command returns JSON structured like this:

```json
{
[
  {"prop": value}
]
}
```

### HTTP Request
`POST /user/mailbox/get_online_users`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


## Mark mail as read
```shell
curl "app.getrakam.com/user/mailbox/mark_as_read"
  -H "write_key: mywrite_key"
-X POST -d '{"project" : "str", "user" : "str", "message_ids" : [
  0
]}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.UsermailboxApi();
api.user_mailbox_mark_as_read(project, user, message_ids);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UsermailboxApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
UsermailboxApi api = new UsermailboxApi();
api.userMailboxMarkAsRead(project, user, messageIds);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\UsermailboxApi($api_client);
$api->userMailboxMarkAsRead(project, user, message_ids);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /user/mailbox/mark_as_read`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|message_ids|false|multi integer (int32) array||



Marks the specified mails as read.

# Admin


System related actions

## List installed modules
```shell
curl "app.getrakam.com/admin/modules"
  -H "master_key: mymaster_key"
-X POST -d '{}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.admin_get_modules();


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi();
api.adminGetModules();

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->adminGetModules();


```

### HTTP Request
`GET /admin/modules`
## Get types
```shell
curl "app.getrakam.com/admin/types"
  -H "master_key: mymaster_key"
-X POST -d '{}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.admin_get_types();


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi();
api.adminGetTypes();

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->adminGetTypes();


```

### HTTP Request
`GET /admin/types`
## Get collection names
```shell
curl "app.getrakam.com/project/collection"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.project_collections(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi();
api.projectCollections(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->projectCollections(project);


```

> The above command returns JSON structured like this:

```json
{
[
  "str"
]
}
```

### HTTP Request
`POST /project/collection`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


## Create project
```shell
curl "app.getrakam.com/project/create"
  -H "master_key: mymaster_key"
-X POST -d '{"name" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.project_create_project(name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi();
api.projectCreateProject(name);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->projectCreateProject(name);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /project/create`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|name|false|string||


## Delete project
```shell
curl "app.getrakam.com/project/delete"
  -H "master_key: mymaster_key"
-X POST -d '{"name" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.project_delete_project(name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi();
api.projectDeleteProject(name);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->projectDeleteProject(name);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /project/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|name|false|string||


## List created projects
```shell
curl "app.getrakam.com/project/list"
  -H "read_key: myread_key"
-X POST -d '{}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.project_get_projects();


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi();
api.projectGetProjects();

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->projectGetProjects();


```

### HTTP Request
`GET /project/list`
## Get collection schema
```shell
curl "app.getrakam.com/project/schema"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "names" : [
  "str"
]}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.AdminApi();
api.project_schema(project, names);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
AdminApi api = new AdminApi();
api.projectSchema(project, names);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->projectSchema(project, names);


```

> The above command returns JSON structured like this:

```json
{
[
  "name" : "str", "fields" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
]
]
}
```

### HTTP Request
`POST /project/schema`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|names|false|multi string array||


## Add fields to collections
```shell
curl "app.getrakam.com/project/schema/add"
  -H "master_key: mymaster_key"
-X POST -d '{"project" : "str"
, "collection" : "str"
, "fields" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
]
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.project_add_fields_to_schema(project_add_fields_to_schema);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi();
api.projectAddFieldsToSchema(projectAddFieldsToSchema);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->projectAddFieldsToSchema(project_add_fields_to_schema);


```

> The above command returns JSON structured like this:

```json
{
[
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
]
}
```

### HTTP Request
`POST /project/schema/add`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|collection|false|string||
|fields|false|[SchemaField](#schemafield) array||


# Event


Event Analyzer

## Collect multiple events
```shell
curl "app.getrakam.com/event/batch"
  -H "write_key: mywrite_key"
-X POST -d '{"api" : "writeKey" : "str", "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str"
, "project" : "str"
, "events" : [
  "project" : "str", "collection" : "str", "api" : "writeKey" : "str", "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str", "properties" : null
]
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.EventApi();
api.collect_event_batch_events(event_list);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
EventApi api = new EventApi();
api.collectEventBatchEvents(eventList);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->collectEventBatchEvents(event_list);


```

> The above command returns JSON structured like this:

```json
{
0
}
```

### HTTP Request
`POST /event/batch`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|api|false|[EventContext](#eventcontext)||
|project|false|string||
|events|false|[Event](#event) array||


## Collect event
```shell
curl "app.getrakam.com/event/collect"
  -H "write_key: mywrite_key"
-X POST -d '{"project" : "str"
, "collection" : "str"
, "api" : "writeKey" : "str", "apiVersion" : "str", "uploadTime" : 0, "checksum" : "str"
, "properties" : null
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.EventApi();
api.collect_event_collect_event(event);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
EventApi api = new EventApi();
api.collectEventCollectEvent(event);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->collectEventCollectEvent(event);


```

> The above command returns JSON structured like this:

```json
{
0
}
```

### HTTP Request
`POST /event/collect`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|collection|false|string||
|api|false|[EventContext](#eventcontext)||
|properties|false|object||


## Analyze events
```shell
curl "app.getrakam.com/query/execute"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "query" : "str", "limit" : 0}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventApi();
api.query_execute(project, query, limit);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventApi api = new EventApi();
api.queryExecute(project, query, limit);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->queryExecute(project, query, limit);


```

> The above command returns JSON structured like this:

```json
{
"metadata" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
], "result" : [
  [
  null
]
], "error" : "message" : "str", "sqlState" : "str", "errorCode" : 0, "errorLine" : 0, "charPositionInLine" : 0, "properties" : {"prop": value}, "failed" : false
}
```

### HTTP Request
`POST /query/execute`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|query|false|string||
|limit|false|integer (int32)||


## Explain query
```shell
curl "app.getrakam.com/query/explain"
  -H "read_key: myread_key"
-X POST -d '{"query" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventApi();
api.query_explain(query);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventApi api = new EventApi();
api.queryExplain(query);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->queryExplain(query);


```

> The above command returns JSON structured like this:

```json
{
null
}
```

### HTTP Request
`POST /query/explain`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|query|false|string||


## Test query
```shell
curl "app.getrakam.com/query/metadata"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "query" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventApi();
api.query_metadata(project, query);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventApi api = new EventApi();
api.queryMetadata(project, query);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->queryMetadata(project, query);


```

> The above command returns JSON structured like this:

```json
{
[
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
]
}
```

### HTTP Request
`POST /query/metadata`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|query|false|string||


# Materialized view


Materialized view

## Create view
```shell
curl "app.getrakam.com/materialized-view/create"
  -H "master_key: mymaster_key"
-X POST -d '{"project" : "str", "name" : "str", "table_name" : "str", "query" : "str", "update_interval" : "str", "incremental_field" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.materialized_view_create(project, name, table_name, query, update_interval, incremental_field);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi();
api.materializedViewCreate(project, name, tableName, query, updateInterval, incrementalField);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->materializedViewCreate(project, name, table_name, query, update_interval, incremental_field);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /materialized-view/create`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|table_name|false|string||
|query|false|string||
|update_interval|false|string||
|incremental_field|false|string||


## Delete materialized view
```shell
curl "app.getrakam.com/materialized-view/delete"
  -H "master_key: mymaster_key"
-X POST -d '{"project" : "str", "name" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.materialized_view_delete(project, name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi();
api.materializedViewDelete(project, name);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->materializedViewDelete(project, name);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /materialized-view/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||


## Get view
```shell
curl "app.getrakam.com/materialized-view/get"
-X POST -d '{"project" : "str", "table_name" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.MaterializedviewApi();
api.materialized_view_get(project, table_name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi();
api.materializedViewGet(project, tableName);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->materializedViewGet(project, table_name);


```

> The above command returns JSON structured like this:

```json
{
"project" : "str", "name" : "str", "query" : "str", "tableName" : "str", "updateInterval" : "str", "incrementalField" : "str", "lastUpdate" : null
}
```

### HTTP Request
`POST /materialized-view/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|table_name|false|string||


## List views
```shell
curl "app.getrakam.com/materialized-view/list"
-X POST -d '{"project" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.MaterializedviewApi();
api.materialized_view_list_views(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi();
api.materializedViewListViews(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->materializedViewListViews(project);


```

> The above command returns JSON structured like this:

```json
{
[
  "project" : "str", "name" : "str", "query" : "str", "tableName" : "str", "updateInterval" : "str", "incrementalField" : "str", "lastUpdate" : null
]
}
```

### HTTP Request
`POST /materialized-view/list`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


## Get schemas
```shell
curl "app.getrakam.com/materialized-view/schema"
-X POST -d '{"project" : "str", "names" : [
  "str"
]}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)

api = client.MaterializedviewApi();
api.materialized_view_schema(project, names);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi();
api.materializedViewSchema(project, names);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->materializedViewSchema(project, names);


```

> The above command returns JSON structured like this:

```json
{
[
  "name" : "str", "fields" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
]
]
}
```

### HTTP Request
`POST /materialized-view/schema`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|names|false|multi string array||


## Update view
```shell
curl "app.getrakam.com/materialized-view/update"
  -H "master_key: mymaster_key"
-X POST -d '{}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.MaterializedviewApi();
api.materialized_view_update();


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
MaterializedviewApi api = new MaterializedviewApi();
api.materializedViewUpdate();

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->materializedViewUpdate();


```

### HTTP Request
`GET /materialized-view/update`
# Continuous query


Continuous query

## Create stream
```shell
curl "app.getrakam.com/continuous-query/create"
  -H "master_key: mymaster_key"
-X POST -d '{"project" : "str"
, "name" : "str"
, "query" : "str"
, "options" : {"prop": value}
, "tableName" : "str"
, "partitionKeys" : [
  "str"
]
}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.continuous_query_create(continuous_query);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi();
api.continuousQueryCreate(continuousQuery);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->continuousQueryCreate(continuous_query);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /continuous-query/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|query|false|string||
|options|false|object||
|tableName|false|string||
|partitionKeys|false|string array||


## Delete stream
```shell
curl "app.getrakam.com/continuous-query/delete"
  -H "master_key: mymaster_key"
-X POST -d '{"project" : "str", "name" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.continuous_query_delete(project, name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi();
api.continuousQueryDelete(project, name);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->continuousQueryDelete(project, name);


```

> The above command returns JSON structured like this:

```json
{
"success" : false, "message" : "str"
}
```

### HTTP Request
`POST /continuous-query/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||


## Get continuous query
```shell
curl "app.getrakam.com/continuous-query/get"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "table_name" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.continuous_query_get(project, table_name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi();
api.continuousQueryGet(project, tableName);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->continuousQueryGet(project, table_name);


```

> The above command returns JSON structured like this:

```json
{
"project" : "str", "name" : "str", "query" : "str", "options" : {"prop": value}, "tableName" : "str", "partitionKeys" : [
  "str"
]
}
```

### HTTP Request
`POST /continuous-query/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|table_name|false|string||


## List queries
```shell
curl "app.getrakam.com/continuous-query/list"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.continuous_query_list_queries(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi();
api.continuousQueryListQueries(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->continuousQueryListQueries(project);


```

> The above command returns JSON structured like this:

```json
{
[
  "project" : "str", "name" : "str", "query" : "str", "options" : {"prop": value}, "tableName" : "str", "partitionKeys" : [
  "str"
]
]
}
```

### HTTP Request
`POST /continuous-query/list`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


## Get query schema
```shell
curl "app.getrakam.com/continuous-query/schema"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "names" : [
  "str"
]}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.continuous_query_schema(project, names);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi();
api.continuousQuerySchema(project, names);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->continuousQuerySchema(project, names);


```

> The above command returns JSON structured like this:

```json
{
[
  "name" : "str", "fields" : [
  "name" : "str", "type" : "str", "unique" : false, "descriptiveName" : "str", "description" : "str", "category" : "str"
]
]
}
```

### HTTP Request
`POST /continuous-query/schema`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|names|false|multi string array||


## Test continuous query
```shell
curl "app.getrakam.com/continuous-query/test"
  -H "read_key: myread_key"
-X POST -d '{"project" : "str", "query" : "str"}'
```

```python

from swagger_client/apis import ApiClient;
from swagger_client/apis.configuration import Configuration
import swagger_client/apis as client;

apiClient = client.ApiClient(HOST)
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.ContinuousqueryApi();
api.continuous_query_test(project, query);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
ContinuousqueryApi api = new ContinuousqueryApi();
api.continuousQueryTest(project, query);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.rakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->continuousQueryTest(project, query);


```

> The above command returns JSON structured like this:

```json
{
false
}
```

### HTTP Request
`POST /continuous-query/test`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|query|false|string||



## Definitions
### EventContext
|name|description|required|schema|default|
|----|----|----|----|----|
|writeKey||false|string||
|apiVersion||false|string||
|uploadTime||false|integer (int64)||
|checksum||false|string||


### SchemaField
|name|description|required|schema|default|
|----|----|----|----|----|
|name||false|string||
|type||false|enum (STRING, DOUBLE, LONG, BOOLEAN, DATE, TIME, TIMESTAMP, BINARY, ARRAY_STRING, ARRAY_DOUBLE, ARRAY_LONG, ARRAY_BOOLEAN, ARRAY_DATE, ARRAY_TIME, ARRAY_TIMESTAMP, ARRAY_BINARY, MAP_STRING, MAP_DOUBLE, MAP_LONG, MAP_BOOLEAN, MAP_DATE, MAP_TIME, MAP_TIMESTAMP, MAP_BINARY)||
|unique||false|boolean|false|
|descriptiveName||false|string||
|description||false|string||
|category||false|string||


### Variant
|name|description|required|schema|default|
|----|----|----|----|----|
|name||false|string||
|weight||false|integer (int32)||
|data||false|object||


### Goal
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||
|filter||false|string||


### UserContext
|name|description|required|schema|default|
|----|----|----|----|----|
|writeKey||false|string||
|apiVersion||false|string||


### Event
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|collection||false|string||
|api||false|[EventContext](#eventcontext)||
|properties||false|object||


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
|filterExpression||false|string||


