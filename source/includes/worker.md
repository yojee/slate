# Worker

## Get worker information

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/info' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "vehicles": [
    {
      "name": "Truck",
      "id": 1
    },
    {
      "name": "Boat",
      "id": 2
    }
  ],
  "status": "on_duty",
  "phone": "+849032230423",
  "name": "John Doe",
  "id": 1,
  "email": "test@yojee.com",
  "device_token": "{{DEVICE_TOKEN}}",
  "current_vehicle_type_id": 2,
  "avatar": "avatar.jpg"
}
```

This endpoint retrieves all worker information.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/info`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Get task statistics of a worker

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/statistics' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "tasks": {
    "failed": 0,
    "completed": 1,
    "assigned": 0,
    "accepted": 1
  },
  "income": "10.00",
  "date": "2018-03-31"
}
```

This endpoint gets task statistics of a worker.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/statistics`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
range | Time Range

## Update worker information

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/worker/update' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'status: {{status}}' \
  -d 'avatar: {{avatar}}'
```

> The above command returns JSON structured like this:

```json
{
  "status": "on_duty",
  "id": 1,
  "avatar": "https://s3-ap-southeast-1.amazonaws.com/signature.jpg"
}
```

This endpoint update worker information.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/worker/update`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
status | {{status}} | String
avatar | {{avatar}} | String

## Select a vehicle type

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/worker/vehicles/{id}/select' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Vehicle was selected."
}
```

This endpoint selects a vehicle type.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/worker/vehicles/{id}/select`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id | Vehicle ID

## Get all configurations for a specific company

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/companies/config' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "rules": {
    "pickup": [
      {
        "title": "Upload image of client",
        "id": 1478,
        "action": "upload_photo"
      }
    ],
    "dropoff": [
      {
        "title": "Upload image of client",
        "id": 1479,
        "action": "upload_photo"
      }
    ]
  },
  "reasons": [
    {
      "reason": "Address is wrong",
      "id": 2
    }
  ]
}
```

This endpoint gets all configurations for a specific company.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/companies/config`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Create a sub task

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/worker/sub_tasks' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'task_id: {{task_id}}' \
  -d 'sub_task_rule_id: {{sub_task_rule_id}}' \
  -d 'photo: {{photo}}' \
  -d 'meta: {{meta}}' \
  -d 'event: {{event}}' \
  -d 'completion_time: {{completion_time}}' \
  -d 'action: {{action}}'
```

> The above command returns JSON structured like this:

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

This endpoint creates a sub task.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/worker/sub_tasks`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
task_id | {{task_id}} | Integer
sub_task_rule_id | {{sub_task_rule_id}} | Integer
photo | {{photo}} | String
meta | {{photo_type}} | String
 | {{photo_title}} | String
event | {{event}} | String
completion_time | {{completion_time}} | String
action | {{action}} | String

## Update the location of worker

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/worker/location' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'lng: {{lng}}' \
  -d 'lat: {{lat}}'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Worker location updated"
}
```

This endpoint updates the location of worker.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/worker/location`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
lng | {{lng}} | Number
lat | {{lng}} | Number

## Stores the device token of a worker

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/worker/store_device_token' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'\
  -d 'device_token: {{device_token}}'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Stored device token successfully"
}
```

This endpoint stores the device token of a worker.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/worker/store_device_token`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
device_token | {{device_token}} | String

## Check status of bulk complete

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/tasks/batches/{id}/status' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "total": 100,
  "status": "completed",
  "processed": 100,
  "logs": []
}
```

This endpoint checks status of bulk complete.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/batches/{id}/status`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id | Batch ID

## Marks a task as failed by creating an associated task exception

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/worker/task/{id}/mark_as_failed' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'description: {{description}}'
```

> The above command returns JSON structured like this:

```json
{
  "message": "OK"
}
```

This endpoint marks a task as failed by creating an associated task exception.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/worker/task/{id}/mark_as_failed`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
description | {{description}} | String

### Parameters

Parameter | Description
--------- | -----------
id | Task ID

## Complete a list of tasks

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/worker/tasks/bulk_complete' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'type: {{type}}' \
  -d 'tracking_numbers: {{tracking_numbers}}' \
  -d 'location: {{location}}' \
  -d 'completion_time: {{completion_time}}'
```

> The above command returns JSON structured like this:

```json
{
  "message": "OK"
}
```

This endpoint completes a list of tasks.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/worker/tasks/bulk_complete`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
type | {{type}} | String
tracking_numbers  | {{tracking_numbers}} | String
location | {{lng}} | Number
 | {{lat}} | Number
completion_time | {{completion_time}} | Timestamp

## Get all ongoing tasks of a worker

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/tasks/ongoing' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

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

This endpoint retrieves all ongoing tasks of a worker.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/ongoing`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description | Default Value
--------- | ----------- | -----------
page | Page number | 1
page_size | Page size | 10

## Get all completed tasks of a worker

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/tasks/completed' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "task_id": 2,
  "sub_task_rule_id": 3,
  "photo": "signature.jpg",
  "meta": {
    "photo_type": "Proof",
    "photo_title": "Signature"
  },
  "event": "pickup_completed",
  "completion_time": "2018-03-10T03:37:08",
  "action": "upload_photo"
}
```

This endpoint retrieves all completed tasks of a worker.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/completed`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description | Default Value
--------- | ----------- | -----------
page | Page number | 1
page_size | Page size | 10

## List completed and failed tasks

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/tasks/history' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "task_id": 2,
  "sub_task_rule_id": 3,
  "photo": "signature.jpg",
  "meta": {
    "photo_type": "Proof",
    "photo_title": "Signature"
  },
  "event": "pickup_completed",
  "completion_time": "2018-03-10T03:37:08",
  "action": "upload_photo"
}
```

This endpoint retrieves all completed and failed tasks.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/history`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description | Default Value
--------- | ----------- | -----------
page | Page number | 1
page_size | Page size | 10
time_range | Time Range | -

## Complete a task

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/worker/tasks/{id}/complete' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'completion_time: {{completion_time}}' \
  -d 'location: {{location}}'
```

> The above command returns JSON structured like this:

```json
{
  "message": "OK"
}
```

This endpoint completes a task.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/worker/tasks/{id}/complete`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
completion_time | {{completion_time}} | Timestamp
location | {{lng}} | Number
 | {{lat}} | Number

### Parameters

Parameter | Description
--------- | -----------
id | Task ID

## List task group by statuses

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/task_groups' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "state": "created",
  "price": "SGD 10",
  "id": 1
}
```

This endpoint retrieves task group by statuses.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/task_groups`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
status | An array of statuses, e.g: [unassigned, assigned, accepted, completed, cancelled]

## Get a task group

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "state": "created",
  "price": "SGD 10",
  "id": 1
}
```

This endpoint retrieves a task group.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id | Task group ID

## Accept a task group

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}/accept' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "state": "created",
  "price": "SGD 10",
  "id": 1
}
```

This endpoint accepts a task group.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}/accept`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id | Task group ID

## Reject a task group

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}/reject' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Reject a task group successfully."
}
```

This endpoint rejects a task group.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}/reject`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id | Task group ID
