## Definitions
### UserHttpService_search
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|filter||false|string||
|event_filters||false|[EventFilter](#eventfilter) array||
|sorting||false|[Sorting](#sorting)||
|offset||false|integer (int32)||
|limit||false|integer (int32)||


### User
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|id||false|object||
|properties||false|object||


### Message
|name|description|required|schema|default|
|----|----|----|----|----|
|id||false|integer (int32)||
|content||false|string||
|from_user||false|object||
|to_user||false|object||
|parentId||false|integer (int32)||
|seen||false|boolean|false|
|time||false|integer (int64)||
|project||false|string||


### Reference
|name|description|required|schema|default|
|----|----|----|----|----|
|type||false|enum (COLUMN, REFERENCE)||
|value||false|string||


### UserHttpService_create
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|properties||false|object||


### EventFilter
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||
|aggregation||false|[EventFilterAggregation](#eventfilteraggregation)||
|filterExpression||false|string||


### JsonResponse
|name|description|required|schema|default|
|----|----|----|----|----|
|success||false|boolean|false|
|message||false|string||


### Sorting
|name|description|required|schema|default|
|----|----|----|----|----|
|column||false|string||
|order||false|enum (asc, desc)||


### QueryResult
|name|description|required|schema|default|
|----|----|----|----|----|
|metadata||false|[SchemaField](#schemafield) array||
|result||false|object array array||
|error||false|[QueryError](#queryerror)||
|properties||false|object||
|failed||false|boolean|false|


### ContinuousQuery
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|name||false|string||
|query||false|string||
|table_name||false|string||
|collections||false|string array||
|partition_keys||false|string array||
|options||false|object||


### EventExplorerHttpService_execute
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|measure||false|[Measure](#measure)||
|grouping||false|[Reference](#reference)||
|segment||false|[Reference](#reference)||
|filterExpression||false|string||
|startDate||false|string (date)||
|endDate||false|string (date)||
|collections||false|string array||


### Measure
|name|description|required|schema|default|
|----|----|----|----|----|
|column||false|string||
|aggregation||false|enum (COUNT, COUNT_UNIQUE, SUM, MINIMUM, MAXIMUM, APPROXIMATE_UNIQUE, VARIANCE, POPULATION_VARIANCE, STANDARD_DEVIATION, AVERAGE)||


### CreateUserResponse
|name|description|required|schema|default|
|----|----|----|----|----|
|identifier||false|object||


### MetadataResponse
|name|description|required|schema|default|
|----|----|----|----|----|
|columns||false|[SchemaField](#schemafield) array||
|identifierColumn||false|string||


### org.rakam.collection.event.EventCollectionHttpService.collect
|name|description|required|schema|default|
|----|----|----|----|----|
|project||true|string||
|collection||true|string||
|properties||true|object||


### MaterializedView
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|name||false|string||
|table_name||false|string||
|query||false|string||
|update_interval||false|string||
|options||false|object||


### EventFilterAggregation
|name|description|required|schema|default|
|----|----|----|----|----|
|field||false|string||
|minimum||false|integer (int64)||
|maximum||false|integer (int64)||
|type||false|enum (COUNT, COUNT_UNIQUE, SUM, MINIMUM, MAXIMUM, APPROXIMATE_UNIQUE, VARIANCE, POPULATION_VARIANCE, STANDARD_DEVIATION, AVERAGE)||


### FunnelQuery
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|steps||false|[FunnelStep](#funnelstep) array||
|dimension||false|string||
|startDate||false|string (date)||
|endDate||false|string (date)||
|enableOtherGrouping||false|boolean||


### FunnelStep
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||
|filterExpression||false|string||


