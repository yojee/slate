<h1 id="Yojee-APIs-[Worker]">[Worker]</h1>

Worker APIs

## ApiWeb.V3.Worker.UserController.store_device_token

<a id="opIdApiWeb.V3.Worker.UserController.store_device_token"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/worker/store_device_token \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/worker/store_device_token`

*This endpoint stores a Worker's device token*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.worker.usercontroller.store_device_token-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|any|true|Device token|

<h3 id="apiweb.v3.worker.usercontroller.store_device_token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Stored device token successfully|None|


## ApiWeb.V3.Worker.UserController.update

<a id="opIdApiWeb.V3.Worker.UserController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/worker/update \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/worker/update`

*This endpoint updates a Worker's information*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.worker.usercontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|any|false|Worker's status|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.usercontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[WorkerResponse](#schemaworkerresponse)|


## ApiWeb.V3.Worker.VehicleController.select

<a id="opIdApiWeb.V3.Worker.VehicleController.select"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/worker/vehicles/{id}/select \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/worker/vehicles/{id}/select`

*This endpoint is used by a Worker to select a Vehicle*

<h3 id="apiweb.v3.worker.vehiclecontroller.select-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Vehicle ID|

<h3 id="apiweb.v3.worker.vehiclecontroller.select-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


## ApiWeb.V3.Worker.CompanyController.config

<a id="opIdApiWeb.V3.Worker.CompanyController.config"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/companies/config \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/companies/config`

*This endpoint retrieves configuration information about a Worker's Company*

<h3 id="apiweb.v3.worker.companycontroller.config-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.companycontroller.config-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CompanyConfigsResponse](#schemacompanyconfigsresponse)|


## ApiWeb.V3.Worker.InfoController.me

<a id="opIdApiWeb.V3.Worker.InfoController.me"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/info \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/info`

*This endpoint retrieves a Worker's infomation*

<h3 id="apiweb.v3.worker.infocontroller.me-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.infocontroller.me-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[InfoResponse](#schemainforesponse)|


## ApiWeb.V3.Worker.InfoController.statistics

<a id="opIdApiWeb.V3.Worker.InfoController.statistics"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/statistics \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/statistics`

*This endpoint retrieves a Worker's Task statistics*

<h3 id="apiweb.v3.worker.infocontroller.statistics-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|range|query|string|false|Time range|

### Enumerated Values

|Parameter|Value|
|---|---|
|range|today|
|range|last_week|
|range|last_four_weeks|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.infocontroller.statistics-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[StatisticsResponse](#schemastatisticsresponse)|


## ApiWeb.V3.Worker.UserController.location

<a id="opIdApiWeb.V3.Worker.UserController.location"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/worker/location \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/worker/location`

*This endpoint updates a Worker's location*

> Body parameter

```json
{
  "lng": 122.6428429677108,
  "lat": 65.67691234535297
}
```

<h3 id="apiweb.v3.worker.usercontroller.location-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[WorkerLocationUpdateRequest](#schemaworkerlocationupdaterequest)|false|Location information|

<h3 id="apiweb.v3.worker.usercontroller.location-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Worker location updated|None|


<h1 id="Yojee-APIs-[Worker]-TaskGroup">[Worker] TaskGroup</h1>

Worker TaskGroup APIs

## ApiWeb.V3.Worker.TaskGroupController.index

<a id="opIdApiWeb.V3.Worker.TaskGroupController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/task_groups \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/task_groups`

*This endpoint retrieves a list of a Worker's TaskGroups*

<h3 id="apiweb.v3.worker.taskgroupcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|status|query|array[any]|false|An array of statuses, e.g: [unassigned, assigned, accepted, completed, cancelled]|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.taskgroupcontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Filter task group by statuses|[TaskGroupResponse](#schemataskgroupresponse)|


## ApiWeb.V3.Worker.TaskGroupController.reject

<a id="opIdApiWeb.V3.Worker.TaskGroupController.reject"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/worker/task_groups/{id}/reject \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/worker/task_groups/{id}/reject`

*This endpoint is used by a Worker to reject an assigned TaskGroup*

<h3 id="apiweb.v3.worker.taskgroupcontroller.reject-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task group ID|

<h3 id="apiweb.v3.worker.taskgroupcontroller.reject-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Reject a task group successfully|None|


## ApiWeb.V3.Worker.TaskGroupController.show

<a id="opIdApiWeb.V3.Worker.TaskGroupController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/task_groups/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/task_groups/{id}`

*This endpoint retrieves information about a TaskGroup*

<h3 id="apiweb.v3.worker.taskgroupcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task group ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.taskgroupcontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Show a task group successfully|[TaskGroupResponse](#schemataskgroupresponse)|


## ApiWeb.V3.Worker.TaskGroupController.accept

<a id="opIdApiWeb.V3.Worker.TaskGroupController.accept"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/worker/task_groups/{id}/accept \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/worker/task_groups/{id}/accept`

*This endpoint is used by a Worker to accept an assigned TaskGroup*

<h3 id="apiweb.v3.worker.taskgroupcontroller.accept-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task group ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.taskgroupcontroller.accept-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Accept a task group successfully|[TaskGroupsResponse](#schemataskgroupsresponse)|


<h1 id="Yojee-APIs-[Worker]-Task">[Worker] Task</h1>

Worker Task APIs

## ApiWeb.V3.Worker.TaskController.batch_complete_status

<a id="opIdApiWeb.V3.Worker.TaskController.batch_complete_status"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/tasks/batches/{id}/status \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/tasks/batches/{id}/status`

*This endpoint checks the status of all Tasks in a Batch*

<h3 id="apiweb.v3.worker.taskcontroller.batch_complete_status-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Batch ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.taskcontroller.batch_complete_status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BulkCompletionStatus](#schemabulkcompletionstatus)|


## ApiWeb.V3.Worker.TaskController.mark_as_failed

<a id="opIdApiWeb.V3.Worker.TaskController.mark_as_failed"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/worker/task/{id}/mark_as_failed \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/worker/task/{id}/mark_as_failed`

*This endpoint marks a Task as failed by creating an associated TaskException*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.worker.taskcontroller.mark_as_failed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task Id|
|body|body|[ApiWeb.V3.Worker.TaskController.mark_as_failedDescriptions](#schemaapiweb.v3.worker.taskcontroller.mark_as_faileddescriptions)|true|Task Exception descriptions|

<h3 id="apiweb.v3.worker.taskcontroller.mark_as_failed-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|


## ApiWeb.V3.Worker.TaskController.bulk_complete

<a id="opIdApiWeb.V3.Worker.TaskController.bulk_complete"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/worker/tasks/bulk_complete \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/worker/tasks/bulk_complete`

*This endpoint is used by a Worker to complete multiple Tasks*

> Body parameter

```json
{
  "type": "pickup",
  "tracking_numbers": [
    "YOJ-YXFCYNNRPT0",
    "YOJ-YXFCYNNRPT8",
    "YOJ-YXFCYNNRPT0"
  ],
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "completion_time": "2018-03-10T03:37:08Z"
}
```

<h3 id="apiweb.v3.worker.taskcontroller.bulk_complete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[BulkTaskCompletionRequest](#schemabulktaskcompletionrequest)|false|Task Completion information|


## ApiWeb.V3.Worker.TaskController.ongoing

<a id="opIdApiWeb.V3.Worker.TaskController.ongoing"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/tasks/ongoing?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/tasks/ongoing`

*This endpoint retrieves a list of a Worker's ongoing Tasks*

<h3 id="apiweb.v3.worker.taskcontroller.ongoing-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|


## ApiWeb.V3.Worker.TaskController.completed

<a id="opIdApiWeb.V3.Worker.TaskController.completed"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/tasks/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/tasks/completed`

*This endpoint retrieves a list of a Worker's completed Tasks*

<h3 id="apiweb.v3.worker.taskcontroller.completed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|range|query|string|false|Time range|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

### Enumerated Values

|Parameter|Value|
|---|---|
|range|today|
|range|last_week|
|range|last_four_weeks|


## ApiWeb.V3.Worker.TaskController.complete

<a id="opIdApiWeb.V3.Worker.TaskController.complete"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/worker/tasks/{id}/complete \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/worker/tasks/{id}/complete`

*This endpoint is used by a Worker to complete a Task*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.worker.taskcontroller.complete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task ID|
|body|body|any|false|Completion time|


## ApiWeb.V3.Worker.TaskController.history

<a id="opIdApiWeb.V3.Worker.TaskController.history"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/worker/tasks/history?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/worker/tasks/history`

*This endpoint retrieves a Worker's Task history*

<h3 id="apiweb.v3.worker.taskcontroller.history-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|range|query|string|false|Time range|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

### Enumerated Values

|Parameter|Value|
|---|---|
|range|today|
|range|last_week|
|range|last_four_weeks|


<h1 id="Yojee-APIs-[Worker]-SubTask">[Worker] SubTask</h1>

Worker SubTask APIs

## ApiWeb.V3.Worker.SubTaskController.create

<a id="opIdApiWeb.V3.Worker.SubTaskController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/worker/sub_tasks \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/worker/sub_tasks`

*This endpoint creates a SubTask*

> Body parameter

```json
{
  "task_id": 2,
  "sub_task_rule_id": 3,
  "photo": "https://s3-ap-southeast-1.amazonaws.com/signature.jpg",
  "meta": {
    "photo_type": "Proof",
    "photo_title": "Signature"
  },
  "event": "pickup_completed",
  "completion_time": "2018-03-10T03:37:08",
  "action": "upload_photo"
}
```

<h3 id="apiweb.v3.worker.subtaskcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[SubTaskRequest](#schemasubtaskrequest)|false|SubTask|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.subtaskcontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SubTaskResponse](#schemasubtaskresponse)|
