# Sender

## Get sender information

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/sender/info' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "vehicle_types": [
      {
          "name": "Car",
          "id": 35
      }
  ],
  "sender_type": "organisation",
  "phone": "+65 3138 9076",
  "name": "Yojee",
  "id": 1,
  "email": "yojee@yojee.com",
  "billing_address": "144 Robinson Road, Singapore"
}
```

This endpoint retrieves all sender information.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/sender/info`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Create order request

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/sender/orders' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'vehicle_type_id: {{vehicle_type_id}}' \
  -d 'sender_id: {{sender_id}}' \
  -d 'price_currency: {{price_currency}}' \
  -d 'price_amount: {{price_amount}}' \
  -d 'placed_by_user_profile_id: {{placed_by_user_profile_id}}' \
  -d 'jobs: {{jobs}}' \
  -d 'items: {{items}}'
```

> The above command returns JSON structured like this:

```json
{
  "tracking_number": "O-ABCDEFGHIJKL",
  "sender_id": 1,
  "price": "SGD 10",
  "placed_by_user_profile_id": 1,
  "number": "{{NUMBER}}",
  "inserted_at": "2018-01-01T00:00:00.000000",
  "id": 17
}
```

This endpoint creates an order.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/sender/orders`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
vehicle_type_id | {{vehicle_type_id}} | Integer
sender_id | {{sender_id}} | Integer
price_currency | {{price_currency}} | String
price_amount | {{price_amount}} | Integer
placed_by_user_profile_id | {{placed_by_user_profile_id}} | Integer
jobs | {{jobs}} | Array
items | {{items}} | Array

## Get order detail

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "status": "paid",
  "sender_id": 1,
  "price": {
      "currency": "SGD",
      "amount": "1.00000000"
  },
  "placed_by_user_profile_id": 1,
  "number": "O-ABCDEFGHIJKL",
  "inserted_at": "2018-01-01T00:00:00.000000Z",
  "id": 1,
  "external_id": null,
  "external_customer_id": null,
  "display_price": "SGD 1",
  "description": "test"
}
```

This endpoint retrieves a specific order.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
number | Order number

## Get all ongoing orders of a sender

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/sender/orders/ongoing' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "status": "paid",
  "sender_id": 1,
  "price": {
      "currency": "SGD",
      "amount": "1.00000000"
  },
  "placed_by_user_profile_id": 1,
  "number": "O-ABCDEFGHIJKL",
  "inserted_at": "2018-01-01T00:00:00.000000Z",
  "id": 1,
  "external_id": null,
  "external_customer_id": null,
  "display_price": "SGD 1",
  "description": "test"
}
```

This endpoint retrieves all ongoing orders of a sender.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/sender/orders/ongoing`

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

## Get all completed orders of a sender

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/sender/orders/completed' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "status": "completed",
  "sender_id": 1,
  "price": {
      "currency": "SGD",
      "amount": "1.00000000"
  },
  "placed_by_user_profile_id": 1,
  "number": "O-ABCDEFGHIJKL",
  "inserted_at": "2018-01-01T00:00:00.000000Z",
  "id": 1,
  "external_id": null,
  "external_customer_id": null,
  "display_price": "SGD 1",
  "description": "test"
}
```

This endpoint retrieves all completed orders of a sender.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/sender/orders/completed`

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

## Create payment request

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}/payments' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'payment_method: {{payment_method}}' \
  -d 'sender_id: {{sender_id}}' \
  -d 'price_currency: {{price_currency}}' \
  -d 'price_amount: {{price_amount}}' \
  -d 'placed_by_user_profile_id: {{placed_by_user_profile_id}}' \
  -d 'jobs: {{jobs}}' \
  -d 'items: {{items}}'
```

> The above command returns JSON structured like this:

```json
{
  "status": "paid",
  "sender_id": 1,
  "price": {
      "currency": "SGD",
      "amount": "1.00000000"
  },
  "placed_by_user_profile_id": 1,
  "number": "O-ABCDEFGHIJKL",
  "inserted_at": "2018-01-01T00:00:00.000000Z",
  "id": 1,
  "external_id": null,
  "external_customer_id": null,
  "display_price": "SGD 1",
  "description": "test"
}
```

This endpoint creates payment request of an order.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}/payments`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
number | Order number

### Body

Key | Value | Type
--------- | ------- | -------
payment_method | {{payment_method}} | String
order_id | {{order_id}} | Integer
description | {{description}} | String
currency | {{currency}} | String
credit_card | {{year}} | Integer
 | {{number}} | String
 | {{name}}  | String
 | {{month}} | Integer
 | {{cvc}} | Integer
amount | {{amount}} | Number

## Cancel an order

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}/cancel' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Order cancelled."
}
```

This endpoint cancels an order.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}/cancel`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
number | Order number

## Batch upload multiple orders

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/sender/batches' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -F 'file: {{file}}' \
  -d 'uploader_id: {{uploader_id}}' \
  -d 'company_id: {{company_id}}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "batch id"
}
```

This endpoint uploads a csv file with multiple orders.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/sender/batches`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
file | File to be uploaded
uploader_id | Uploader ID
company_id  | Company ID

## Check batch status

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/sender/batches/check_status' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'batch_id: {{batch_id}}'
```

> The above command returns JSON structured like this:

```json
{
  "status": "status"
}
```

This endpoint checks batch status.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/sender/batches/check_status`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
batch_id  | Batch ID
