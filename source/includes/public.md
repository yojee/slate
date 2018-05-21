# Public

## Get user information

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/users/info' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "order_schema": {
      "size_weight": {
        "package": {
          "required": [
            "size",
            "weight"
          ],
          "properties": "properties",
      "job_details": "job_details",
      "delivery_type": "delivery_type",
      "addresses": "addresses"
    },
    "customer_language": "en",
    "cs_phone": "+6531591335",
    "branding": {
      "text_color_highlighted": "#8ecb1b",
      "text_color": "#2c3e50",
      "pricing_url": "https://yojee.com/prices/",
      "logo": "logo.jpg",
      "generated_favicon": {},
      "favicon": {
        "original": "favicon.jpg",
        "96x96": ,
      "banner_text_line1": "MON TO SAT 10AM-10PM. BOOKINGS AFTER 4PM WILL BE PROCESSED THE FOLLOWING DAY.",
      "banner_text_color": "#ffffff",
      "banner_header": "SAME DAY, NEXT DAY, EXPRESS DELIVERY",
      "banner": "banner.jpg",
      "background_color": "#ffffff",
      "admin_primary_color": "#80c939"
      }
     }
    }
  }
}
```

This endpoint retrieves all user information.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/user/info`

### Headers

Key | Value
--------- | -------
COMPANY_SLUG | {{COMPANY_SLUG}}

## Get OTP code

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/otp/' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "otp_code": "123456"
}
```

This endpoint gets OTP code.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/otp/`

### Parameters

Parameter | Description
--------- | -----------
phone | Phone number

## Verify OTP code

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/verify_otp/' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
    "user_profile_id": 1,
    "phone": "+99999999999",
    "id": 1,
    "email": "test@yojee.com",
    "access_token": "T5P2rQrC6KbkPnLE9ebyjskMUTju3vKFBzlAr+bCUpc="
  }
```

This endpoint verifies OTP code.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/verify_otp/`

### Parameters

Parameter | Description
--------- | -----------
phone | Phone number
otp | OTP

## Get price estimate

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/public/orders/price' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'slug: {{slug}}' \
  -d 'item: {{item}}' \
  -d 'to_address: {{to_address}}' \
  -d 'from_address: {{from_address}}'
```

> The above command returns JSON structured like this:

```json
{
  "type": "express",
  "success": true,
  "msg": {
    "surcharges": {
      "CBD": 2
    },
    "price": 20,
    "pickup_zip": "068896",
    "dropoff_zip": "189703",
    "base_price": 18
  }
}
```

This endpoint gets a price estimate of a delivery request.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/public/orders/price`

### Body

Key | Value | Type
--------- | ------- | -------
slug | {{slug}} | String
item | {{weight}} | Integer
to_address | {{zipcode}} | String
 | {{location}} | String
 | {{lng}} | String
 | {{lat}} | String
 | {{country}} | String
from_address | {{zipcode}} | String
 | {{location}} | String
 | {{lng}} | String
 | {{lat}} | String
 | {{country}} | String

## Get tracking data of an order

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/track/{number}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "tracking_number": "O-SK1LAUPOQXJF",
  "status": "created",
  "price_currency": "SGD",
  "price_amount": 10,
  "order_items": [
    {
      "status": "scheduled_for_fulfilment",
      "service_type": "sameday",
      "order_item_logs": [
        {
          "inserted_at": "2018-03-20T15:18:38.770110",
          "description": "(pickup) Accepted by Miss Joanie Ullrich II ((528) 226-4679)"
        },
        {
          "inserted_at": "2018-03-20T15:18:38.772850",
          "description": "(dropoff) Accepted by Miss Joanie Ullrich II ((528) 226-4679)"
        }
      ],
      "item_id": 2673
    }
  ],
  "number": "bmFvQTA1c3dybS9sNWdnOUVSdEZlZz09",
  "inserted_at": "2018-03-20T15:18:38.613719",
  "description": "Gift",
  "currency": "SGD"
}
```

This endpoint gets tracking data of an order.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/track/{number}`

### Parameters

Parameter | Description
--------- | -----------
number | Order number

## Validate if reset password token is still valid

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/password/edit' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint validates if reset password token is still valid.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/password/edit`

### Parameters

Parameter | Description
--------- | -----------
reset_password_token | Reset password token

## Validate if reset password token is still valid to update password

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/public/password' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Password is updated!"
}
```

This endpoint validates if reset password token is still valid to update password.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/public/password`

### Parameters

Parameter | Description
--------- | -----------
password | New password
reset_password_token | Reset password token

## Create reset password token and send a password reset email

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/public/password' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "An email has been sent to [email] with further instructions."
}
```

This endpoint creates reset password token and sends a password reset email.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/public/password`

### Parameters

Parameter | Description
--------- | -----------
email | Email

## Validate if reset password token is still valid

```shell
curl -X PATCH \
  'https://umbrella-demo.yojee.com/api/v3/public/password' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "Password is updated!"
}
```

This endpoint validates if reset password token is still valid.

### HTTP Request

`PATCH https://umbrella-demo.yojee.com/api/v3/public/password`

### Parameters

Parameter | Description
--------- | -----------
password | New password
reset_password_token | Reset password token

## Generate an invoice on the fly

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/invoices/{order_number}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "Create label binary flow download"
}
```

This endpoint generates an invoice on the fly.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/invoices/{order_number}`

### Parameters

Parameter | Description
--------- | -----------
order_number | Order number

## Generate a label on the fly

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/labels/{tracking_number}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "Label to be downloaded."
}
```

This endpoint generates a label on the fly.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/labels/{tracking_number}`

### Parameters

Parameter | Description
--------- | -----------
tracking_number | Tracking_number
format | Output format

## Generate a label on the fly under order item

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/labels/order_item/{tracking_number}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "Label to be downloaded."
}
```

This endpoint generates a label on the fly under order item.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/labels/order_item/{tracking_number}`

### Parameters

Parameter | Description
--------- | -----------
tracking_number | Tracking_number
format | Output format

## Generate a label on the fly from order number

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/public/labels/order/{order_number}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "Label to be downloaded."
}
```

This endpoint generates a label on the fly from order number.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/public/labels/order/{order_number}`

### Parameters

Parameter | Description
--------- | -----------
order_number | Order_number
format | Output format
