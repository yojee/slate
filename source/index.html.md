---
title: Yojee APIs
language_tabs:
  - shell: cURL
toc_footers:
  - <a href='https://yojee.com/consultation/'>Demo request form</a>
search: true
home: true

---

<h1 id="Yojee-APIs">Yojee APIs</h1>

Yojee provides more than hundreds of APIs for you to access Yojee API endpoints. You may find all of our API resources on this page.
 <aside class="notice">
Make sure to replace {{ACCESS_TOKEN}} with your API key
</aside>

> Scroll down for code samples, example requests and responses.

<h1 id="Yojee-APIs-[Public]">[Public]</h1>

Public APIs

## UserController.info

<a id="opIdApiWeb.V3.UserController.info"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/users/info?company_slug=string

```

`GET https://umbrella.yojee.com/api/v3/public/users/info`

*This endpoint retrieves infomation about a Company*

<h3 id="apiweb.v3.usercontroller.info-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|company_slug|query|string|true|Company slug|

<h3 id="apiweb.v3.usercontroller.info-responses">Responses</h3>

## ApiController.verify_otp

<a id="opIdApiWeb.V3.ApiController.verify_otp"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/verify_otp/ \
  -H 'Accept: */*'

```

`GET https://umbrella.yojee.com/api/v3/public/verify_otp/`

*This endpoint verifies the entered OTP code*

<h3 id="apiweb.v3.apicontroller.verify_otp-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|phone|query|string|false|Phone number|
|otp_code|query|string|false|OTP code|

> Example responses

> 200 Response

<h3 id="apiweb.v3.apicontroller.verify_otp-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OTP Verified|[VerifyOtpResponse](#schemaverifyotpresponse)|

## ApiController.get_otp

<a id="opIdApiWeb.V3.ApiController.get_otp"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/otp/ \
  -H 'Accept: */*'

```

`GET https://umbrella.yojee.com/api/v3/public/otp/`

*This endpoint requests an OTP code for logging in*

<h3 id="apiweb.v3.apicontroller.get_otp-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|phone|query|string|false|Phone number|

> Example responses

> 200 Response

<h3 id="apiweb.v3.apicontroller.get_otp-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got OTP|[GetOtpResponse](#schemagetotpresponse)|

<h1 id="Yojee-APIs-[Public]-Order">[Public] Order</h1>

Public APIs for Order Tracking

## ApiController.track_item

<a id="opIdApiWeb.V3.ApiController.track_item"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/track_item/{number} \
  -H 'Accept: */*'

```

`GET https://umbrella.yojee.com/api/v3/public/track_item/{number}`

*This endpoint retrieves tracking information for an Order Item*

<h3 id="apiweb.v3.apicontroller.track_item-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|number|path|string|true|Tracking number|

> Example responses

> 200 Response

<h3 id="apiweb.v3.apicontroller.track_item-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got tracking data|[TrackOrderItemResponse](#schematrackorderitemresponse)|

## Public.OrdersController.get_prices

<a id="opIdApiWeb.V3.Public.OrdersController.get_prices"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/public/orders/price \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

`POST https://umbrella.yojee.com/api/v3/public/orders/price`

*This endpoint obtains a price quote for an Order*

> Body parameter

```json
{
  "to_address": {
    "zipcode": "189703",
    "location": "1.2976764,103.85701760000006",
    "lng": "103.85701760000006",
    "lat": "1.2976764",
    "country": "Singpore"
  },
  "slug": "yojee",
  "item": {
    "weight": 4
  },
  "from_address": {
    "zipcode": "068896",
    "location": "1.2777689,103.84839149999993",
    "lng": "103.84839149999993",
    "lat": "1.2777689",
    "country": "Singpore"
  }
}
```

<h3 id="apiweb.v3.public.orderscontroller.get_prices-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[GetPricesRequest](#schemagetpricesrequest)|true|Order details|

> Example responses

> 200 Response

```json
{
  "data": [
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
    },
    {
      "type": "same_day",
      "success": true,
      "msg": {
        "surcharges": {
          "CBD": 2
        },
        "price": 12,
        "pickup_zip": "068896",
        "dropoff_zip": "189703",
        "base_price": 10
      }
    },
    {
      "type": "next_day",
      "success": true,
      "msg": {
        "surcharges": {
          "CBD": 2
        },
        "price": 9,
        "pickup_zip": "068896",
        "dropoff_zip": "189703",
        "base_price": 7
      }
    }
  ]
}
```

<h3 id="apiweb.v3.public.orderscontroller.get_prices-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get Prices Response|[GetPricesResponse](#schemagetpricesresponse)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|None|

## ApiController.track_order

<a id="opIdApiWeb.V3.ApiController.track_order"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/track/{number} \
  -H 'Accept: */*'

```

`GET https://umbrella.yojee.com/api/v3/public/track/{number}`

*This endpoint retrieves tracking information for an Order*

<h3 id="apiweb.v3.apicontroller.track_order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|number|path|string|true|Tracking number|

> Example responses

> 200 Response

<h3 id="apiweb.v3.apicontroller.track_order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got tracking data|[TrackOrderResponse](#schematrackorderresponse)|

## Public.OrdersController.download_sample

<a id="opIdApiWeb.V3.Public.OrdersController.download_sample"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/orders/download_sample?company_slug=string

```

`GET https://umbrella.yojee.com/api/v3/public/orders/download_sample`

*This endpoint downloads all sample batch files of a company*

<h3 id="apiweb.v3.public.orderscontroller.download_sample-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|company_slug|query|string|true|Company Slug|

<h3 id="apiweb.v3.public.orderscontroller.download_sample-responses">Responses</h3>

<h1 id="Yojee-APIs-[Public]-Password">[Public] Password</h1>

## Public.PasswordController.edit

<a id="opIdApiWeb.V3.Public.PasswordController.edit"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/password/edit

```

`GET https://umbrella.yojee.com/api/v3/public/password/edit`

*Validate if reset password token is still valid*

<h3 id="apiweb.v3.public.passwordcontroller.edit-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|reset_password_token|query|string|false|Reset password token|

<h3 id="apiweb.v3.public.passwordcontroller.edit-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

## Public.PasswordController.update

<a id="opIdApiWeb.V3.Public.PasswordController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella.yojee.com/api/v3/public/password

```

`PATCH https://umbrella.yojee.com/api/v3/public/password`

*Validate if reset password token is still valid*

<h3 id="apiweb.v3.public.passwordcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|password|query|string|false|New password|
|reset_password_token|query|string|false|Reset password token|

<h3 id="apiweb.v3.public.passwordcontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

## Public.PasswordController.create

<a id="opIdApiWeb.V3.Public.PasswordController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/public/password?email=string

```

`POST https://umbrella.yojee.com/api/v3/public/password`

*Create reset password token and send email*

<h3 id="apiweb.v3.public.passwordcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|email|query|string|true|Email of the account to reset password|
|company_slug|query|string|false|Company slug, default is yojee|
|portal|query|string|false|Portal, admin or order, default is admin|

<h3 id="apiweb.v3.public.passwordcontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

<h1 id="Yojee-APIs-[Public]-Docs">[Public] Docs</h1>

Public APIs for Waybills, Invoices, EPODs and other Documentation

## Public.InvoiceController.generate

<a id="opIdApiWeb.V3.Public.InvoiceController.generate"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/invoices/{order_number}?order_number=string

```

`GET https://umbrella.yojee.com/api/v3/public/invoices/{order_number}`

*This endpoint generates an Invoice from an Order number*

<h3 id="apiweb.v3.public.invoicecontroller.generate-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|order_number|query|string|true|Order number|
|format|query|string|false|Output format|

#### Enumerated Values

|Parameter|Value|
|---|---|
|format|html|
|format|pdf|

<h3 id="apiweb.v3.public.invoicecontroller.generate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Create invoice binary for download|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

## Public.LabelController.generate_from_tracking_number

<a id="opIdApiWeb.V3.Public.LabelController.generate_from_tracking_number"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/labels/{tracking_number}?tracking_number=string

```

`GET https://umbrella.yojee.com/api/v3/public/labels/{tracking_number}`

*This endpoint generates a Label from a tracking number*

<h3 id="apiweb.v3.public.labelcontroller.generate_from_tracking_number-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|tracking_number|query|string|true|Tracking number|
|format|query|string|false|Output format|

#### Enumerated Values

|Parameter|Value|
|---|---|
|format|html|
|format|pdf|

<h3 id="apiweb.v3.public.labelcontroller.generate_from_tracking_number-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Label to be downloaded.|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

## Public.PodController.generate_from_order_number

<a id="opIdApiWeb.V3.Public.PodController.generate_from_order_number"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/pods/order/{order_number}?order_number=string

```

`GET https://umbrella.yojee.com/api/v3/public/pods/order/{order_number}`

*This endpoint generates a Pod from an Order number*

<h3 id="apiweb.v3.public.podcontroller.generate_from_order_number-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|order_number|query|string|true|Order number|
|format|query|string|false|Output format|

#### Enumerated Values

|Parameter|Value|
|---|---|
|format|html|
|format|pdf|

<h3 id="apiweb.v3.public.podcontroller.generate_from_order_number-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Pod to be downloaded.|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

## Public.PodController.generate_from_tracking_number

<a id="opIdApiWeb.V3.Public.PodController.generate_from_tracking_number"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/pods/order_item/{tracking_number}?tracking_number=string

```

`GET https://umbrella.yojee.com/api/v3/public/pods/order_item/{tracking_number}`

*This endpoint generates a Pod from a tracking number*

<h3 id="apiweb.v3.public.podcontroller.generate_from_tracking_number-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|tracking_number|query|string|true|Tracking number|
|format|query|string|false|Output format|

#### Enumerated Values

|Parameter|Value|
|---|---|
|format|html|
|format|pdf|

<h3 id="apiweb.v3.public.podcontroller.generate_from_tracking_number-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Pod to be downloaded.|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

## Public.LabelController.generate_from_order_number

<a id="opIdApiWeb.V3.Public.LabelController.generate_from_order_number"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/public/labels/order/{order_number}?order_number=string

```

`GET https://umbrella.yojee.com/api/v3/public/labels/order/{order_number}`

*This endpoint generates a Label from an Order number*

<h3 id="apiweb.v3.public.labelcontroller.generate_from_order_number-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|order_number|query|string|true|Order number|
|format|query|string|false|Output format|

#### Enumerated Values

|Parameter|Value|
|---|---|
|format|html|
|format|pdf|

<h3 id="apiweb.v3.public.labelcontroller.generate_from_order_number-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Label to be downloaded.|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

<h1 id="Yojee-APIs-[Auth]">[Auth]</h1>

Authentication APIs

## AuthController.signin

<a id="opIdApiWeb.V3.AuthController.signin"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/auth/signin \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella.yojee.com/api/v3/auth/signin`

*This endpoint allows a registered user to log in*

> Body parameter

```json
{
  "password": "abc123$%^",
  "email": "long@yojee.com"
}
```

<h3 id="apiweb.v3.authcontroller.signin-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SigninRequest](#schemasigninrequest)|false|Account info|

> Example responses

> 200 Response

<h3 id="apiweb.v3.authcontroller.signin-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthResponse](#schemaauthresponse)|

<h1 id="Yojee-APIs-[Sender]">[Sender]</h1>

Sender APIs

## Sender.InfoController.me

<a id="opIdApiWeb.V3.Sender.InfoController.me"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/info \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/info`

*This endpoint retrieves a Sender's infomation*

<h3 id="apiweb.v3.sender.infocontroller.me-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.sender.infocontroller.me-responses">Responses</h3>

<h1 id="Yojee-APIs-[Sender]-Order">[Sender] Order</h1>

Sender Order APIs

## Sender.OrderController.cancel

<a id="opIdApiWeb.V3.Sender.OrderController.cancel"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/sender/orders/{number}/cancel \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/sender/orders/{number}/cancel`

*This endpoint cancels an Order*

<h3 id="apiweb.v3.sender.ordercontroller.cancel-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Order number|

<h3 id="apiweb.v3.sender.ordercontroller.cancel-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

## Sender.OrderController.completed

<a id="opIdApiWeb.V3.Sender.OrderController.completed"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/orders/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/orders/completed`

*This endpoint retrieves all completed Orders of a Sender*

<h3 id="apiweb.v3.sender.ordercontroller.completed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

<h3 id="apiweb.v3.sender.ordercontroller.completed-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

## Sender.PaymentsController.create

<a id="opIdApiWeb.V3.Sender.PaymentsController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/sender/orders/{number}/payments \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/sender/orders/{number}/payments`

*This endpoint creates a payment request*

> Body parameter

```json
{
  "payment_method": "stripe",
  "order_id": 1,
  "description": "This is a test description",
  "currency": "SGD",
  "credit_card": {
    "year": 22,
    "number": 4242424242424242,
    "name": "Jane Doe",
    "month": 11,
    "cvc": 111
  },
  "amount": 500
}
```

<h3 id="apiweb.v3.sender.paymentscontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Order Number|
|body|body|[CreatePaymentRequest](#schemacreatepaymentrequest)|false|Payment information|

<h3 id="apiweb.v3.sender.paymentscontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Payment successful|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Payment failed!|None|

## Sender.OrderController.create

<a id="opIdApiWeb.V3.Sender.OrderController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/sender/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/sender/orders`

*This endpoint creates an Order*

> Body parameter

```json
{
  "steps": [
    null
  ],
  "sender_type": "string",
  "sender_id": 0,
  "price_currency": "string",
  "price_amount": 0,
  "items": [
    null
  ],
  "item_steps": [
    null
  ]
}
```

<h3 id="apiweb.v3.sender.ordercontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[CreateOrderRequest](#schemacreateorderrequest)|false|Order information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.sender.ordercontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Create order response success|[CreateOrderResponse](#schemacreateorderresponse)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

## Sender.OrderController.show

<a id="opIdApiWeb.V3.Sender.OrderController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/orders/{number} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/orders/{number}`

*This endpoint retrieves information about an Order*

<h3 id="apiweb.v3.sender.ordercontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Order Number|

<h3 id="apiweb.v3.sender.ordercontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|None|

## Sender.OrderController.ongoing

<a id="opIdApiWeb.V3.Sender.OrderController.ongoing"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/orders/ongoing?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/orders/ongoing`

*This endpoint retrieves all ongoing Orders of a Sender*

<h3 id="apiweb.v3.sender.ordercontroller.ongoing-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

<h3 id="apiweb.v3.sender.ordercontroller.ongoing-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<h1 id="Yojee-APIs-[Sender]-Batch">[Sender] Batch</h1>

Sender Batch APIs

## Sender.BatchController.check_status

<a id="opIdApiWeb.V3.Sender.BatchController.check_status"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/batches/check_status \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/batches/check_status`

*This endpoint checks the status of a Batch*

<h3 id="apiweb.v3.sender.batchcontroller.check_status-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|batch_id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.sender.batchcontroller.check_status-responses">Responses</h3>

## Sender.BatchController.create

<a id="opIdApiWeb.V3.Sender.BatchController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/sender/batches \
  -H 'Content-Type: multipart/form-data' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/sender/batches`

*This endpoint is used by a Sender to upload a batch file*

> Body parameter

```yaml
file: string

```

<h3 id="apiweb.v3.sender.batchcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[ApiWeb.V3.Dispatcher.BatchController.create](#schemaapiweb.v3.dispatcher.batchcontroller.create)|false|none|
|» file|body|string(binary)|false|The file to upload|

<h3 id="apiweb.v3.sender.batchcontroller.create-responses">Responses</h3>

## Sender.BatchController.get_order

<a id="opIdApiWeb.V3.Sender.BatchController.get_order"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/batches/get_order \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/batches/get_order`

*This endpoint retrieves detailed information about a Batch*

<h3 id="apiweb.v3.sender.batchcontroller.get_order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|batch_id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.sender.batchcontroller.get_order-responses">Responses</h3>

<h1 id="Yojee-APIs-[Sender]-Company">[Sender] Company</h1>

## Sender.CompanyController.service_types

<a id="opIdApiWeb.V3.Sender.CompanyController.service_types"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/Sender/company/service_types \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/Sender/company/service_types`

*This endpoint retrieves service types of a Company*

<h3 id="apiweb.v3.sender.companycontroller.service_types-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.sender.companycontroller.service_types-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got a complete list of the company's service types|[CompanyServiceTypesResponse](#schemacompanyservicetypesresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Docs">[Dispatcher] Docs</h1>

## Dispatcher.ManifestController.generate_worker_manifest

<a id="opIdApiWeb.V3.Dispatcher.ManifestController.generate_worker_manifest"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/manifests/worker/{worker_id}

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/manifests/worker/{worker_id}`

*This endpoint generates a Manifest for a Worker*

<h3 id="apiweb.v3.dispatcher.manifestcontroller.generate_worker_manifest-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|worker_id|query|integer|false|Worker ID|

<h3 id="apiweb.v3.dispatcher.manifestcontroller.generate_worker_manifest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Worker manifest to be downloaded.|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

<h1 id="Yojee-APIs-[Sender]-Addressbook">[Sender] Addressbook</h1>

## Sender.AddressbookController.search

<a id="opIdApiWeb.V3.Sender.AddressbookController.search"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/addressbook/search?query=string&page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/addressbook/search`

*This endpoint search address item of a company*

<h3 id="apiweb.v3.sender.addressbookcontroller.search-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|query|query|string|true|external_id/contact/address text query|
|category|query|string|false|category of address item|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

<h3 id="apiweb.v3.sender.addressbookcontroller.search-responses">Responses</h3>

<h1 id="Yojee-APIs-[Sender]-Track-Order-Item">[Sender] Track Order Item</h1>

## Sender.TrackController.track_item

<a id="opIdApiWeb.V3.Sender.TrackController.track_item"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/track_item/{number} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/track_item/{number}`

*This endpoint retrieves tracking information for an Order Item*

<h3 id="apiweb.v3.sender.trackcontroller.track_item-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Tracking number|

> Example responses

> 200 Response

<h3 id="apiweb.v3.sender.trackcontroller.track_item-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got tracking data|[TrackOrderItemResponse](#schematrackorderitemresponse)|

<h1 id="Yojee-APIs-[Sender]-Track-Order">[Sender] Track Order</h1>

## Sender.TrackController.track_order

<a id="opIdApiWeb.V3.Sender.TrackController.track_order"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/sender/track/{number} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/sender/track/{number}`

*This endpoint retrieves tracking information for an Order*

<h3 id="apiweb.v3.sender.trackcontroller.track_order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Tracking number|

> Example responses

> 200 Response

<h3 id="apiweb.v3.sender.trackcontroller.track_order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got tracking data|[TrackOrderResponse](#schematrackorderresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Track-Order-Item">[Dispatcher] Track Order Item</h1>

## Dispatcher.TrackController.track_item

<a id="opIdApiWeb.V3.Dispatcher.TrackController.track_item"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/track_item/{number} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/track_item/{number}`

*This endpoint retrieves tracking information for an Order Item*

<h3 id="apiweb.v3.dispatcher.trackcontroller.track_item-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Tracking number|
|sender_id|query|integer|false|sender id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.trackcontroller.track_item-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got tracking data|[TrackOrderItemResponse](#schematrackorderitemresponse)|

<h1 id="Yojee-APIs-[Worker]">[Worker]</h1>

Worker APIs

## Worker.InfoController.get_companies_theme

<a id="opIdApiWeb.V3.Worker.InfoController.get_companies_theme"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/get_companies_theme \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/get_companies_theme`

*This endpoint retrieves a list of all companies along with their theme info*

<h3 id="apiweb.v3.worker.infocontroller.get_companies_theme-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.infocontroller.get_companies_theme-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CompaniesThemeResponse](#schemacompaniesthemeresponse)|

## Worker.InfoController.check_for_updates

<a id="opIdApiWeb.V3.Worker.InfoController.check_for_updates"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/check_for_updates \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/check_for_updates`

*This endpoint checks if current installed app needs to be updated*

<h3 id="apiweb.v3.worker.infocontroller.check_for_updates-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|os|query|string|false|operating system|
|version|query|integer|false|version|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.infocontroller.check_for_updates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[VersionResponse](#schemaversionresponse)|

## Worker.UserController.store_device_token

<a id="opIdApiWeb.V3.Worker.UserController.store_device_token"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/store_device_token \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/store_device_token`

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

## Worker.UserController.update

<a id="opIdApiWeb.V3.Worker.UserController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/update \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/update`

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

## Worker.InfoController.companies

<a id="opIdApiWeb.V3.Worker.InfoController.companies"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/companies \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/companies`

*This endpoint retrieves a list of Companies that a phone number is registered as a Worker in*

<h3 id="apiweb.v3.worker.infocontroller.companies-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.infocontroller.companies-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CompaniesResponse](#schemacompaniesresponse)|

## Worker.VehicleController.select

<a id="opIdApiWeb.V3.Worker.VehicleController.select"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/vehicles/{id}/select \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/vehicles/{id}/select`

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

## Worker.CompanyController.config

<a id="opIdApiWeb.V3.Worker.CompanyController.config"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/companies/config \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/companies/config`

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

## Worker.InfoController.me

<a id="opIdApiWeb.V3.Worker.InfoController.me"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/info \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/info`

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

## Worker.InfoController.statistics

<a id="opIdApiWeb.V3.Worker.InfoController.statistics"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/statistics \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/statistics`

*This endpoint retrieves a Worker's Task statistics*

<h3 id="apiweb.v3.worker.infocontroller.statistics-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|range|query|string|false|Time range|

#### Enumerated Values

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

## Worker.UserController.location

<a id="opIdApiWeb.V3.Worker.UserController.location"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/location \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/location`

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

## Worker.WorkerSequenceController.show

<a id="opIdApiWeb.V3.Worker.WorkerSequenceController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/worker_sequence \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/worker_sequence`

*This endpoint is used by a Worker fetch worker sequence detail*

<h3 id="apiweb.v3.worker.workersequencecontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.worker.workersequencecontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<h1 id="Yojee-APIs-[Worker]-TaskGroup">[Worker] TaskGroup</h1>

Worker TaskGroup APIs

## Worker.TaskGroupController.index

<a id="opIdApiWeb.V3.Worker.TaskGroupController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/task_groups \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/task_groups`

*This endpoint retrieves a list of a Worker's TaskGroups*

<h3 id="apiweb.v3.worker.taskgroupcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|status|query|array[any]|false|An array of statuses, e.g: [broadcasted, assigned, accepted, completed, cancelled]|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.taskgroupcontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Filter task group by statuses|[TaskGroupResponse](#schemataskgroupresponse)|

## Worker.TaskGroupController.reject

<a id="opIdApiWeb.V3.Worker.TaskGroupController.reject"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/task_groups/{id}/reject \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/task_groups/{id}/reject`

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

## Worker.TaskGroupController.show

<a id="opIdApiWeb.V3.Worker.TaskGroupController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/task_groups/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/task_groups/{id}`

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

## Worker.TaskGroupController.accept

<a id="opIdApiWeb.V3.Worker.TaskGroupController.accept"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/task_groups/{id}/accept \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/task_groups/{id}/accept`

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

## Worker.TaskController.batch_complete_status

<a id="opIdApiWeb.V3.Worker.TaskController.batch_complete_status"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/tasks/batches/{id}/status \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/tasks/batches/{id}/status`

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

## Worker.TaskController.mark_as_failed

<a id="opIdApiWeb.V3.Worker.TaskController.mark_as_failed"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/worker/task/{id}/mark_as_failed \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/worker/task/{id}/mark_as_failed`

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

## Worker.TaskController.bulk_complete

<a id="opIdApiWeb.V3.Worker.TaskController.bulk_complete"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/tasks/bulk_complete \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/tasks/bulk_complete`

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

<h3 id="apiweb.v3.worker.taskcontroller.bulk_complete-responses">Responses</h3>

## Worker.TaskController.ongoing

<a id="opIdApiWeb.V3.Worker.TaskController.ongoing"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/tasks/ongoing?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/tasks/ongoing`

*This endpoint retrieves a list of a Worker's ongoing Tasks*

<h3 id="apiweb.v3.worker.taskcontroller.ongoing-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.taskcontroller.ongoing-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TasksResponse](#schematasksresponse)|

## Worker.TaskController.completed

<a id="opIdApiWeb.V3.Worker.TaskController.completed"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/tasks/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/tasks/completed`

*This endpoint retrieves a list of a Worker's completed Tasks*

<h3 id="apiweb.v3.worker.taskcontroller.completed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|range|query|string|false|Time range|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

#### Enumerated Values

|Parameter|Value|
|---|---|
|range|today|
|range|last_week|
|range|last_four_weeks|

<h3 id="apiweb.v3.worker.taskcontroller.completed-responses">Responses</h3>

## Worker.TaskController.complete

<a id="opIdApiWeb.V3.Worker.TaskController.complete"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/tasks/{id}/complete \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/tasks/{id}/complete`

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

<h3 id="apiweb.v3.worker.taskcontroller.complete-responses">Responses</h3>

## Worker.TaskController.history

<a id="opIdApiWeb.V3.Worker.TaskController.history"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/tasks/history?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/tasks/history`

*This endpoint retrieves a Worker's Task history*

<h3 id="apiweb.v3.worker.taskcontroller.history-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|range|query|string|false|Time range|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

#### Enumerated Values

|Parameter|Value|
|---|---|
|range|today|
|range|last_week|
|range|last_four_weeks|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.taskcontroller.history-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TasksHistoryResponse](#schemataskshistoryresponse)|

<h1 id="Yojee-APIs-[Worker]-SubTask">[Worker] SubTask</h1>

Worker SubTask APIs

## Worker.SubTaskController.update

<a id="opIdApiWeb.V3.Worker.SubTaskController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/sub_tasks \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/sub_tasks`

*This endpoint completes a SubTask*

> Body parameter

```json
{
  "task_id": 2,
  "sub_task_rule_id": 3,
  "photo": "https://s3-ap-southeast-1.amazonaws.com/signature.jpg",
  "completion_data": {
    "recipient_name": "recipient",
    "arrival_time": "2018-03-10T03:37:08"
  }
}
```

<h3 id="apiweb.v3.worker.subtaskcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[SubTaskRequest](#schemasubtaskrequest)|false|SubTask|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.subtaskcontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SubTaskResponse](#schemasubtaskresponse)|

## Worker.SubTaskController.create

<a id="opIdApiWeb.V3.Worker.SubTaskController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/worker/sub_tasks \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/worker/sub_tasks`

*This endpoint completes a SubTask*

> Body parameter

```json
{
  "task_id": 2,
  "sub_task_rule_id": 3,
  "photo": "https://s3-ap-southeast-1.amazonaws.com/signature.jpg",
  "completion_data": {
    "recipient_name": "recipient",
    "arrival_time": "2018-03-10T03:37:08"
  }
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

<h1 id="Yojee-APIs-[Worker]-Stop">[Worker] Stop</h1>

## Worker.StopController.stops

<a id="opIdApiWeb.V3.Worker.StopController.stops"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/stops?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/stops`

*This endpoint retrieves a list of a Worker's ongoing Stops*

<h3 id="apiweb.v3.worker.stopcontroller.stops-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.stopcontroller.stops-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[StopsResponse](#schemastopsresponse)|

## Worker.StopController.show

<a id="opIdApiWeb.V3.Worker.StopController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/stops/{id}?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/stops/{id}`

*This endpoint retrieves a list of a Worker's ongoing Tasks by Stop*

<h3 id="apiweb.v3.worker.stopcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Stop ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.stopcontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TasksResponse](#schematasksresponse)|


<h1 id="Yojee-APIs-[Worker]-Chat">[Worker] Chat</h1>

## Worker.ChatController.update

<a id="opIdApiWeb.V3.Worker.ChatController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/worker/chat/channel \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/worker/chat/channel`

*This endpoint returns update worker channel data*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.worker.chatcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|any|false|Last read on date in ISO8601 format|

<h3 id="apiweb.v3.worker.chatcontroller.update-responses">Responses</h3>

## Worker.ChatController.channel

<a id="opIdApiWeb.V3.Worker.ChatController.channel"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/worker/chat/channel \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/worker/chat/channel`

*This endpoint returns list of worker channels*

<h3 id="apiweb.v3.worker.chatcontroller.channel-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|last_message_date|query|string|false|Last Message date|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.chatcontroller.channel-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[WorkerChatMessagesResponse](#schemaworkerchatmessagesresponse)|

## Worker.ChatController.send_message

<a id="opIdApiWeb.V3.Worker.ChatController.send_message"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/worker/chat/send_message \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/worker/chat/send_message`

*This endpoint returns update worker channel data*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.worker.chatcontroller.send_message-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[ApiWeb.V3.Dispatcher.ChatController.send_messageMessage](#schemaapiweb.v3.dispatcher.chatcontroller.send_messagemessage)|false|Text Message|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.chatcontroller.send_message-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[WorkerChatMessageResponse](#schemaworkerchatmessageresponse)|

<h1 id="Yojee-APIs-[Dispatcher]">[Dispatcher]</h1>

Dispatcher APIs

## Dispatcher.InfoController.me

<a id="opIdApiWeb.V3.Dispatcher.InfoController.me"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/info \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/info`

*This endpoint retrieves a Dispatcher's infomation*

<h3 id="apiweb.v3.dispatcher.infocontroller.me-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.infocontroller.me-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherInfoResponse](#schemadispatcherinforesponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Plan">[Dispatcher] Plan</h1>

## Dispatcher.PlanController.show

<a id="opIdApiWeb.V3.Dispatcher.PlanController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/plans/:id \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/plans/:id`

*This endpoint retrieves a plan belonging to a Company*

<h3 id="apiweb.v3.dispatcher.plancontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Plan UUID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.plancontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got list of company plans|[DispatcherPlanResponse](#schemadispatcherplanresponse)|

## Dispatcher.PlanController.create

<a id="opIdApiWeb.V3.Dispatcher.PlanController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/plans \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/plans`

*This endpoint creates a new plan*

> Body parameter

```json
{
  "uuid": "123456789",
  "settings": {
    "sample settings": "sample value"
  },
  "output": {
    "sample output": "sample value"
  },
  "input": {
    "sample input": "sample value"
  }
}
```

<h3 id="apiweb.v3.dispatcher.plancontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCreatePlanRequest](#schemadispatchercreateplanrequest)|false|Company plan information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.plancontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created the company plan|[DispatcherPlanResponse](#schemadispatcherplanresponse)|

## Dispatcher.PlanController.index

<a id="opIdApiWeb.V3.Dispatcher.PlanController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/plans \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/plans`

*This endpoint retrieves a list of plans belonging to a Company*

<h3 id="apiweb.v3.dispatcher.plancontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|date|path|string|true|Filter date|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.plancontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got list of company plans|[DispatcherIndexPlanResponse](#schemadispatcherindexplanresponse)|

## Dispatcher.PlanController.update

<a id="opIdApiWeb.V3.Dispatcher.PlanController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/plans/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/plans/{id}`

*This endpoint updates a plan*

> Body parameter

```json
{
  "uuid": "123456789",
  "settings": {
    "sample settings": "sample value"
  },
  "output": {
    "sample output": "sample value"
  },
  "input": {
    "sample input": "sample value"
  }
}
```

<h3 id="apiweb.v3.dispatcher.plancontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Plan UUID|
|body|body|[DispatcherUpdatePlanRequest](#schemadispatcherupdateplanrequest)|false|Company plan information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.plancontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated the company plan|[DispatcherPlanResponse](#schemadispatcherplanresponse)|

## Dispatcher.PlanController.delete

<a id="opIdApiWeb.V3.Dispatcher.PlanController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/plans/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/plans/{id}`

*This endpoint deletes a plan*

<h3 id="apiweb.v3.dispatcher.plancontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Plan UUID|

<h3 id="apiweb.v3.dispatcher.plancontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<h1 id="Yojee-APIs-[Dispatcher]-Search">[Dispatcher] Search</h1>

Dispatcher APIs for Search

## Dispatcher.SearchController.sender

<a id="opIdApiWeb.V3.Dispatcher.SearchController.sender"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/search/sender?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/search/sender`

*This endpoint is used to search for a Sender*

<h3 id="apiweb.v3.dispatcher.searchcontroller.sender-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|

<h3 id="apiweb.v3.dispatcher.searchcontroller.sender-responses">Responses</h3>

## Dispatcher.SearchController.worker

<a id="opIdApiWeb.V3.Dispatcher.SearchController.worker"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/search/worker?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/search/worker`

*This endpoint is used to search for a Worker*

<h3 id="apiweb.v3.dispatcher.searchcontroller.worker-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|

<h3 id="apiweb.v3.dispatcher.searchcontroller.worker-responses">Responses</h3>

## Dispatcher.SearchController.index

<a id="opIdApiWeb.V3.Dispatcher.SearchController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/search?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/search`

*This endpoint is used for global search*

<h3 id="apiweb.v3.dispatcher.searchcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|

<h3 id="apiweb.v3.dispatcher.searchcontroller.index-responses">Responses</h3>

## Dispatcher.SearchController.dispatcher

<a id="opIdApiWeb.V3.Dispatcher.SearchController.dispatcher"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/search/dispatcher?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/search/dispatcher`

*This endpoint is used to search for a Sender Admins*

<h3 id="apiweb.v3.dispatcher.searchcontroller.dispatcher-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|

<h3 id="apiweb.v3.dispatcher.searchcontroller.dispatcher-responses">Responses</h3>

## Dispatcher.SearchController.order

<a id="opIdApiWeb.V3.Dispatcher.SearchController.order"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/search/order?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/search/order`

*This endpoint is used to search for an Order*

<h3 id="apiweb.v3.dispatcher.searchcontroller.order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|

<h3 id="apiweb.v3.dispatcher.searchcontroller.order-responses">Responses</h3>

## Dispatcher.SearchController.order_item

<a id="opIdApiWeb.V3.Dispatcher.SearchController.order_item"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/search/order_item?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/search/order_item`

*This endpoint is used to search for an OrderItem*

<h3 id="apiweb.v3.dispatcher.searchcontroller.order_item-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|

<h3 id="apiweb.v3.dispatcher.searchcontroller.order_item-responses">Responses</h3>

## Dispatcher.SearchController.task

<a id="opIdApiWeb.V3.Dispatcher.SearchController.task"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/search/task?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/search/task`

*This endpoint is used to search for a Task*

<h3 id="apiweb.v3.dispatcher.searchcontroller.task-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|
|status|query|string|false|filter by status (either 'unassigned' or 'assigned')|

<h3 id="apiweb.v3.dispatcher.searchcontroller.task-responses">Responses</h3>

<h1 id="Yojee-APIs-[Dispatcher]-User">[Dispatcher] User</h1>

Dispatcher APIs for User Management

## Dispatcher.UserController.create

<a id="opIdApiWeb.V3.Dispatcher.UserController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/users \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/users`

*This endpoint creates a new Dispatcher*

> Body parameter

```json
{
  "phone": "+987654330",
  "password": "passwd112233",
  "name": "Mike Dispatcher",
  "email": "mike-dispatcher-3@yojee.com"
}
```

<h3 id="apiweb.v3.dispatcher.usercontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCreateUserRequest](#schemadispatchercreateuserrequest)|false|Company user information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.usercontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created the company user|[DispatcherCreateUserResponse](#schemadispatchercreateuserresponse)|

## Dispatcher.UserController.index

<a id="opIdApiWeb.V3.Dispatcher.UserController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/users \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/users`

*This endpoint retrieves a list of Dispatchers belonging to a Company*

<h3 id="apiweb.v3.dispatcher.usercontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.usercontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got list of company users|[DispatcherIndexUserResponse](#schemadispatcherindexuserresponse)|

## Dispatcher.UserController.update

<a id="opIdApiWeb.V3.Dispatcher.UserController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/users/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/users/{id}`

*This endpoint updates a Dispatcher's information*

> Body parameter

```json
{
  "phone": "+987654330",
  "password": "passwd112233",
  "name": "Mike Dispatcher"
}
```

<h3 id="apiweb.v3.dispatcher.usercontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Dispatcher ID|
|body|body|[DispatcherUpdateUserRequest](#schemadispatcherupdateuserrequest)|false|Company user information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.usercontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated the company user|[DispatcherCreateUserResponse](#schemadispatchercreateuserresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Company">[Dispatcher] Company</h1>

Dispatcher APIs for Company Management

## Dispatcher.CompanyController.service_types

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.service_types"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/company/service_types \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/company/service_types`

*This endpoint retrieves service types of a Company*

<h3 id="apiweb.v3.dispatcher.companycontroller.service_types-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.companycontroller.service_types-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got a complete list of the company's service types|[CompanyServiceTypesResponse](#schemacompanyservicetypesresponse)|

## Dispatcher.CompanyController.vehicle_types

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.vehicle_types"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/vehicle_types \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/vehicle_types`

*This endpoint retrieves a list of VehicleTypes belonging to a Company*

<h3 id="apiweb.v3.dispatcher.companycontroller.vehicle_types-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.companycontroller.vehicle_types-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CompanyVehicleTypesResponse](#schemacompanyvehicletypesresponse)|

## Dispatcher.CompanyController.show

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/company \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/company`

*This endpoint retrieves infomation about a Company*

<h3 id="apiweb.v3.dispatcher.companycontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.companycontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got the company info|[CompanyInfoResponse](#schemacompanyinforesponse)|

## Dispatcher.CompanyController.upload_assets

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.upload_assets"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/company/assets \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/company/assets`

*This endpoint is used to upload branding assets for a Company*

> Body parameter

```yaml
file: string
file_type: string

```

<h3 id="apiweb.v3.dispatcher.companycontroller.upload_assets-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|object|false|none|
|» file|body|string(binary)|true|The file to upload.|
|» file_type|body|string|true|The file type|

> Example responses

> 200 Response

```json
{
  "data": "https://s3.us-east-1.amazonaws.com/test/uploads/companies/334/334_logo.png"
}
```

<h3 id="apiweb.v3.dispatcher.companycontroller.upload_assets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Uploaded the company asset|[CompanyUploadAssetsResponse](#schemacompanyuploadassetsresponse)|

## Dispatcher.CompanyController.update_settings

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.update_settings"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/company/settings \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/company/settings`

*This endpoint updates a Company's settings*

> Body parameter

```json
{
  "settings": {
    "delivery_options": {
      "time_window": {
        "pickup": {
          "to": 18,
          "from": 10
        },
        "dropoff": {
          "to": 22,
          "from": 14
        }
      },
      "pickup_allowance": 2,
      "max_weight": 50,
      "advance_bookings": 14
    }
  }
}
```

<h3 id="apiweb.v3.dispatcher.companycontroller.update_settings-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[CompanyUpdateSettingsRequest](#schemacompanyupdatesettingsrequest)|false|Company settings object|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.companycontroller.update_settings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated the company setting|[CompanyInfoResponse](#schemacompanyinforesponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Role">[Dispatcher] Role</h1>

Dispatcher APIs for Role Management

## Dispatcher.RoleController.create

<a id="opIdApiWeb.V3.Dispatcher.RoleController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/roles \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/roles`

*This endpoint creates a new Role*

> Body parameter

```json
{
  "name": "role_1",
  "company_id": 123,
  "access_map": {
    "sender": {
      "add": true
    }
  }
}
```

<h3 id="apiweb.v3.dispatcher.rolecontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCreateRoleRequest](#schemadispatchercreaterolerequest)|false|Role information|

<h3 id="apiweb.v3.dispatcher.rolecontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

## Dispatcher.RoleController.index

<a id="opIdApiWeb.V3.Dispatcher.RoleController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/roles \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/roles`

*This endpoint retrieves a list of Roles*

<h3 id="apiweb.v3.dispatcher.rolecontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.rolecontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got list of roles|[DispatcherIndexRoleResponse](#schemadispatcherindexroleresponse)|

## Dispatcher.RoleController.update

<a id="opIdApiWeb.V3.Dispatcher.RoleController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella.yojee.com/api/v3/dispatcher/roles/{id} \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella.yojee.com/api/v3/dispatcher/roles/{id}`

*This endpoint updates a Role*

> Body parameter

```json
{
  "updated_at": "2018-12-11 08:56:23.843283Z",
  "name": "role_1",
  "company_id": 123,
  "access_map": {
    "sender": {
      "add": true
    }
  }
}
```

<h3 id="apiweb.v3.dispatcher.rolecontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherUpdateRoleRequest](#schemadispatcherupdaterolerequest)|false|Role information|

<h3 id="apiweb.v3.dispatcher.rolecontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h1 id="Yojee-APIs-[Dispatcher]-Partner-Transfer-Order">[Dispatcher] Partner Transfer Order</h1>

## Dispatcher.PartnerTransferController.cancel_transfer

<a id="opIdApiWeb.V3.Dispatcher.PartnerTransferController.cancel_transfer"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/partner_transfer/sender/cancel_order/{order_number} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/partner_transfer/sender/cancel_order/{order_number}`

*This endpoint is used to cancel a Transfer Order*

<h3 id="apiweb.v3.dispatcher.partnertransfercontroller.cancel_transfer-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|order_number|path|string|true|Order number|

<h3 id="apiweb.v3.dispatcher.partnertransfercontroller.cancel_transfer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Transfer Order canceled successfully|None|

## Dispatcher.PartnerTransferController.reject_transfer

<a id="opIdApiWeb.V3.Dispatcher.PartnerTransferController.reject_transfer"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/partner_transfer/dispatcher/reject_order/{order_number} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/partner_transfer/dispatcher/reject_order/{order_number}`

*This endpoint is used to reject a Transfer Order*

<h3 id="apiweb.v3.dispatcher.partnertransfercontroller.reject_transfer-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|order_number|path|string|true|Order number|

<h3 id="apiweb.v3.dispatcher.partnertransfercontroller.reject_transfer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Transfer Order rejected successfully|None|

## Dispatcher.PartnerTransferController.create_transfer

<a id="opIdApiWeb.V3.Dispatcher.PartnerTransferController.create_transfer"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/partner_transfer/sender/create_order \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/partner_transfer/sender/create_order`

*This endpoint is used to create a Transfer Order*

> Body parameter

```json
{
  "tracking_numbers": [
    "YOJ-NHLZA0V3PT0"
  ],
  "price_currency": "USD",
  "price_amount": "1.00",
  "partner_cip": "CIP-RTNKAUJLQ3LWRGRA"
}
```

<h3 id="apiweb.v3.dispatcher.partnertransfercontroller.create_transfer-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherPartnerTransferCreate](#schemadispatcherpartnertransfercreate)|false|Transfer Order Information|

<h3 id="apiweb.v3.dispatcher.partnertransfercontroller.create_transfer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Transfer Order created successfully|None|

## Dispatcher.PartnerTransferController.accept_transfer

<a id="opIdApiWeb.V3.Dispatcher.PartnerTransferController.accept_transfer"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/partner_transfer/dispatcher/accept_order/{order_number} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/partner_transfer/dispatcher/accept_order/{order_number}`

*This endpoint is used to accept a Transfer Order*

<h3 id="apiweb.v3.dispatcher.partnertransfercontroller.accept_transfer-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|order_number|path|string|true|Order number|

<h3 id="apiweb.v3.dispatcher.partnertransfercontroller.accept_transfer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Transfer Order accepted successfully|None|

<h1 id="Yojee-APIs-[Dispatcher]-Partner">[Dispatcher] Partner</h1>

Dispatcher APIs for Partner Management

## Dispatcher.PartnerController.reject_invite

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.reject_invite"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/partners/{cip}/reject_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/partners/{cip}/reject_invite`

*This endpoint is used to decline a Partner invite*

<h3 id="apiweb.v3.dispatcher.partnercontroller.reject_invite-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|cip|path|string|true|Partner CIP|

<h3 id="apiweb.v3.dispatcher.partnercontroller.reject_invite-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Partnership invite declined successfully|None|

## Dispatcher.PartnerController.sent_invites

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.sent_invites"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/partners/invites/sent?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GEThttps://umbrella-demo.yojee.com/api/v3/dispatcher/partners/invites/sent`

*This endpoint retrieves a list of sent partnership requests*

<h3 id="apiweb.v3.dispatcher.partnercontroller.sent_invites-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|false|Search by company name|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.sent_invites-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartners](#schemadispatcherpartners)|

## Dispatcher.PartnerController.cancel_invite

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.cancel_invite"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/partners/{cip}/cancel_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUThttps://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/cancel_invite`

*This endpoint is used to cancel a sent Partner invite*

<h3 id="apiweb.v3.dispatcher.partnercontroller.cancel_invite-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|cip|path|string|true|Partner CIP|

<h3 id="apiweb.v3.dispatcher.partnercontroller.cancel_invite-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Partnership invite canceled successfully|None|

## Dispatcher.PartnerController.update_partnership_info

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.update_partnership_info"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/partnership_info \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/partnership_info`

*This endpoint updates a Company's partnership information*

> Body parameter

```json
{
  "contact_phone": "+6591245934",
  "contact_name": "Ralston",
  "contact_email": "ralston@xyz.com"
}
```

<h3 id="apiweb.v3.dispatcher.partnercontroller.update_partnership_info-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherPartnershipInfoUpdate](#schemadispatcherpartnershipinfoupdate)|false|Dispatcher company partnership info|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.update_partnership_info-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartnershipInfo](#schemadispatcherpartnershipinfo)|

## Dispatcher.PartnerController.partnership_info

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.partnership_info"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/partnership_info \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/partnership_info`

*This endpoint retrieves a Company's partnership information*

<h3 id="apiweb.v3.dispatcher.partnercontroller.partnership_info-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.partnership_info-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartnershipInfo](#schemadispatcherpartnershipinfo)|

## Dispatcher.PartnerController.send_invite

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.send_invite"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/partners/{cip}/send_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/partners/{cip}/send_invite`

*This endpoint is used to send a Partner invite*

<h3 id="apiweb.v3.dispatcher.partnercontroller.send_invite-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|cip|path|string|true|Partner CIP|

<h3 id="apiweb.v3.dispatcher.partnercontroller.send_invite-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Partnership invite sent successfully|None|

## Dispatcher.PartnerController.received_invites

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.received_invites"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/partners/invites/received?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/partners/invites/received`

*This endpoint retrieves a list of received partnership requests*

<h3 id="apiweb.v3.dispatcher.partnercontroller.received_invites-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|false|Search by company name|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.received_invites-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartners](#schemadispatcherpartners)|

## Dispatcher.PartnerController.accept_invite

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.accept_invite"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/partners/{cip}/accept_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/partners/{cip}/accept_invite`

*This endpoint is used to accept a Partner invite*

<h3 id="apiweb.v3.dispatcher.partnercontroller.accept_invite-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|cip|path|string|true|Partner CIP|

<h3 id="apiweb.v3.dispatcher.partnercontroller.accept_invite-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Partnership invite accepted successfully|None|

## Dispatcher.PartnerController.index

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/partners?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/partners`

*This endpoint retrieves a list of Partners belonging to a Company*

<h3 id="apiweb.v3.dispatcher.partnercontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|type|query|string|false|Partnership type|
|q|query|string|false|Search by company name|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartners](#schemadispatcherpartners)|

<h1 id="Yojee-APIs-[Dispatcher]-Network">[Dispatcher] Network</h1>

Dispatcher APIs for Network Management

## Dispatcher.Network.SpokeController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/network/spokes \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/network/spokes`

*This endpoint creates a new Spoke*

> Body parameter

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "destination_hub_id": 2
}
```

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[SpokeRequest](#schemaspokerequest)|false|Spoke|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SpokeResponse](#schemaspokeresponse)|

## Dispatcher.Network.SpokeController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/network/spokes \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/network/spokes`

*This endpoint retrieves a list of Spokes belonging to a Company*

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SpokesResponse](#schemaspokesresponse)|

## Dispatcher.Network.HubController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella.yojee.com/api/v3/dispatcher/network/hubs/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella.yojee.com/api/v3/dispatcher/network/hubs/{id}`

*This endpoint updates a Hub*

> Body parameter

```json
{
  "regions": [
    "poly5"
  ],
  "properties": {
    "description": "Sample description",
    "address": "Singapore"
  },
  "name": "Sample Hub",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  }
}
```

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Hub Id|
|body|body|[HubRequest](#schemahubrequest)|false|Hub|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[HubResponse](#schemahubresponse)|

## Dispatcher.Network.HubController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/network/hubs/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/network/hubs/{id}`

*This endpoint retrieves information about a Hub*

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Hub Id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[HubResponse](#schemahubresponse)|

## Dispatcher.Network.HubController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/network/hubs/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/network/hubs/{id}`

*This endpoint deletes a Hub*

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Hub Id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[HubResponse](#schemahubresponse)|

## Dispatcher.Network.HubController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/network/hubs \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/network/hubs`

*This endpoint creates a new Hub*

> Body parameter

```json
{
  "regions": [
    "poly5"
  ],
  "properties": {
    "description": "Sample description",
    "address": "Singapore"
  },
  "name": "Sample Hub",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  }
}
```

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[HubRequest](#schemahubrequest)|false|Hub|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[HubResponse](#schemahubresponse)|

## Dispatcher.Network.HubController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/network/hubs \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/network/hubs`

*This endpoint retrieves a list of Hubs belonging to a Company*

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.hubcontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[HubsResponse](#schemahubsresponse)|

## Dispatcher.Network.RegionController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/network/regions \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/network/regions`

*This endpoint creates a new Region*

> Body parameter

```json
{
  "tag": "poly5",
  "description": "Sample Region",
  "coordinates": [
    [
      {
        "lng": 10,
        "lat": 35
      },
      {
        "lng": 45,
        "lat": 45
      },
      {
        "lng": 40,
        "lat": 15
      },
      {
        "lng": 20,
        "lat": 10
      },
      {
        "lng": 10,
        "lat": 35
      }
    ],
    [
      {
        "lng": 30,
        "lat": 20
      },
      {
        "lng": 35,
        "lat": 35
      },
      {
        "lng": 20,
        "lat": 30
      },
      {
        "lng": 30,
        "lat": 20
      }
    ]
  ],
  "color": "red"
}
```

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[RegionRequest](#schemaregionrequest)|false|Region|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RegionResponse](#schemaregionresponse)|

## Dispatcher.Network.RegionController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/network/regions \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/network/regions`

*This endpoint retrieves a list of Regions belonging to a Company*

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RegionsResponse](#schemaregionsresponse)|

## Dispatcher.Network.SpokeController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella.yojee.com/api/v3/dispatcher/network/spokes/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella.yojee.com/api/v3/dispatcher/network/spokes/{id}`

*This endpoint updates a Spoke*

> Body parameter

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "destination_hub_id": 2
}
```

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Spoke Id|
|body|body|[SpokeRequest](#schemaspokerequest)|false|Spoke|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SpokeResponse](#schemaspokeresponse)|

## Dispatcher.Network.SpokeController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/network/spokes/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/network/spokes/{id}`

*This endpoint retrieves information about a Spoke*

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Spoke Id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SpokeResponse](#schemaspokeresponse)|

## Dispatcher.Network.SpokeController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/network/spokes/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/network/spokes/{id}`

*This endpoint deletes a Spoke*

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Spoke Id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.spokecontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SpokeResponse](#schemaspokeresponse)|

## Dispatcher.Network.RegionController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella.yojee.com/api/v3/dispatcher/network/regions/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella.yojee.com/api/v3/dispatcher/network/regions/{id}`

*This endpoint updates a Region*

> Body parameter

```json
{
  "tag": "poly5",
  "description": "Sample Region",
  "coordinates": [
    [
      {
        "lng": 10,
        "lat": 35
      },
      {
        "lng": 45,
        "lat": 45
      },
      {
        "lng": 40,
        "lat": 15
      },
      {
        "lng": 20,
        "lat": 10
      },
      {
        "lng": 10,
        "lat": 35
      }
    ],
    [
      {
        "lng": 30,
        "lat": 20
      },
      {
        "lng": 35,
        "lat": 35
      },
      {
        "lng": 20,
        "lat": 30
      },
      {
        "lng": 30,
        "lat": 20
      }
    ]
  ],
  "color": "red"
}
```

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Region ID|
|body|body|[RegionRequest](#schemaregionrequest)|false|Region|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RegionResponse](#schemaregionresponse)|

## Dispatcher.Network.RegionController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/network/regions/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/network/regions/{id}`

*This endpoint retrieves information about a Region*

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Region ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RegionResponse](#schemaregionresponse)|

## Dispatcher.Network.RegionController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/network/regions/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/network/regions/{id}`

*This endpoint deletes a Region*

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Region ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RegionResponse](#schemaregionresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Sender">[Dispatcher] Sender</h1>

Dispatcher APIs for Sender Management

## Dispatcher.SenderController.create

<a id="opIdApiWeb.V3.Dispatcher.SenderController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/senders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/senders`

*This endpoint creates a new Sender*

> Body parameter

```json
{
  "sender_type": "individual",
  "phone": "+8412345611",
  "password": "passwd112233",
  "name": "Mike Sender",
  "email": "michael@yojee.com",
  "billing_address": "144 Robinson Road"
}
```

<h3 id="apiweb.v3.dispatcher.sendercontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCreateSenderRequest](#schemadispatchercreatesenderrequest)|false|Sender information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.sendercontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCreateSenderResponse](#schemadispatchercreatesenderresponse)|

## Dispatcher.SenderController.index

<a id="opIdApiWeb.V3.Dispatcher.SenderController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/senders`

*This endpoint retrieves a list of Senders*

<h3 id="apiweb.v3.dispatcher.sendercontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|sender_type|query|string|false|Sender type (individual/organisation)|
|q|query|string|false|Search by sender name or organisation name|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.sendercontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherSendersResponse](#schemadispatchersendersresponse)|

## Dispatcher.SenderController.update

<a id="opIdApiWeb.V3.Dispatcher.SenderController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella.yojee.com/api/v3/dispatcher/senders/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella.yojee.com/api/v3/dispatcher/senders/{id}`

*This endpoint updates a Sender's information*

> Body parameter

```json
{
  "phone": "+8412345611",
  "name": "Mike Sender",
  "email": "michael@yojee.com",
  "billing_address": "144 Robinson Road"
}
```

<h3 id="apiweb.v3.dispatcher.sendercontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Sender ID|
|body|body|[DispatcherUpdateSenderRequest](#schemadispatcherupdatesenderrequest)|false|Sender information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.sendercontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCreateSenderResponse](#schemadispatchercreatesenderresponse)|

## Dispatcher.SenderController.show

<a id="opIdApiWeb.V3.Dispatcher.SenderController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/senders/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/senders/{id}`

*This endpoint retrieves information about a Sender*

<h3 id="apiweb.v3.dispatcher.sendercontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Sender ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.sendercontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCreateSenderResponse](#schemadispatchercreatesenderresponse)|

## Dispatcher.SenderController.delete

<a id="opIdApiWeb.V3.Dispatcher.SenderController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/senders/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/senders/{id}`

*This endpoint deletes a Sender*

<h3 id="apiweb.v3.dispatcher.sendercontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Sender ID|

<h3 id="apiweb.v3.dispatcher.sendercontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<h1 id="Yojee-APIs-[Dispatcher]-CorporateSender">[Dispatcher] CorporateSender</h1>

Dispatcher APIs for Corporate Sender Management

## Dispatcher.OrganisationController.update_corporate_sender

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.update_corporate_sender"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/organisations/{organisation_id}/senders/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/organisations/{organisation_id}/senders/{id}`

*This endpoint updates a Corporate User*

> Body parameter

```json
{
  "title": "Engineer",
  "sender_type": "organisation",
  "phone": "+6598765432",
  "name": "Ralston",
  "email": "secondary_account@abc.com",
  "billing_address": "77 Robinson road, Singapore."
}
```

<h3 id="apiweb.v3.dispatcher.organisationcontroller.update_corporate_sender-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|organisation_id|path|string|true|Organisation ID|
|id|path|string|true|Dispatcher ID|
|body|body|[DispatcherUpdateCorporateSenderRequest](#schemadispatcherupdatecorporatesenderrequest)|false|Corporate User information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.update_corporate_sender-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated the corporate user|[DispatcherUpdateCorporateSenderResponse](#schemadispatcherupdatecorporatesenderresponse)|

## Dispatcher.DispatcherController.sender_admins

<a id="opIdApiWeb.V3.Dispatcher.DispatcherController.sender_admins"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/dispatchers/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/dispatchers/senders`

*This endpoint retrieves a list of Sender Admins and the Organisations they manage*

<h3 id="apiweb.v3.dispatcher.dispatchercontroller.sender_admins-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.dispatchercontroller.sender_admins-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherSenderAdminsRequest](#schemadispatchersenderadminsrequest)|

## Dispatcher.OrganisationController.organisation_senders

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.organisation_senders"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/organisation_senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/organisation_senders`

*This endpoint retrieves a list of Organisation Senders*

<h3 id="apiweb.v3.dispatcher.organisationcontroller.organisation_senders-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.organisation_senders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCorporateSendersResponse](#schemadispatchercorporatesendersresponse)|

## Dispatcher.OrganisationController.create_corporate_sender

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.create_corporate_sender"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/organisations/{id}/senders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/organisations/{id}/senders`

*This endpoint creates a new Corporate User*

> Body parameter

```json
{
  "title": "Engineer",
  "sender_type": "organisation",
  "phone": "+6598765432",
  "name": "Ralston",
  "email": "secondary_account@abc.com",
  "billing_address": "77 Robinson road, Singapore."
}
```

<h3 id="apiweb.v3.dispatcher.organisationcontroller.create_corporate_sender-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Organisation ID|
|body|body|[DispatcherCreateCorporateSenderRequest](#schemadispatchercreatecorporatesenderrequest)|false|Corporate Sender information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.create_corporate_sender-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCreateCorporateSenderResponse](#schemadispatchercreatecorporatesenderresponse)|

## Dispatcher.OrganisationController.corporate_senders

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.corporate_senders"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/organisations/{id}/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/organisations/{id}/senders`

*This endpoint retrieves a list of Corporate Users*

<h3 id="apiweb.v3.dispatcher.organisationcontroller.corporate_senders-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Organisation ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.corporate_senders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCorporateSendersResponse](#schemadispatchercorporatesendersresponse)|

## Dispatcher.OrganisationController.create

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/organisations \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/organisations`

*This endpoint creates a new corporate*

> Body parameter

```json
{
  "title": "Engineer",
  "sender_type": "organisation",
  "phone": "+6598765432",
  "payment_option": "monthly_billing",
  "organisation": {
    "reg_address": "77 Robinson road, Singapore.",
    "postal_code": "321021",
    "phone": "+6591245934",
    "name": "ABC",
    "country": "Singapore",
    "city": "Singapore"
  },
  "name": "Ralston",
  "gst_no": "2AS9890",
  "email": "primary_account@abc.com",
  "business_reg_no": "ABC1235M",
  "billing_address": "77 Robinson road, Singapore."
}
```

<h3 id="apiweb.v3.dispatcher.organisationcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCreateOrganisationRequest](#schemadispatchercreateorganisationrequest)|false|Organisation information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCreateOrganisationResponse](#schemadispatchercreateorganisationresponse)|

## Dispatcher.OrganisationController.index

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/organisations?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/organisations`

*This endpoint retrieves a list of Corporates (aka Organisations) managed by a Dispatcher*

<h3 id="apiweb.v3.dispatcher.organisationcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|false|search by name|
|with_users|query|boolean|false|include users or not|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherOrganisationsResponse](#schemadispatcherorganisationsresponse)|

## Dispatcher.OrganisationController.update

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/organisations/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/organisations/{id}`

*This endpoint updates a Corporate*

> Body parameter

```json
{
  "user_profiles": [
    {
      "user_profile_id": 1,
      "phone": "Sender Phone",
      "name": "Sender Name",
      "email": "sender-email@example.com"
    },
    {
      "user_profile_id": 2,
      "phone": "+6533445566",
      "name": "Corporate User 2",
      "email": "corporate-user-2@example.com"
    }
  ],
  "sender": {
    "user_profile_id": 1,
    "phone": "Sender Phone",
    "name": "Sender Name",
    "email": "sender-email@example.com",
    "billing_address": "Sender billing address"
  },
  "reg_address": "77 Robinson road, Singapore.",
  "postal_code": "321021",
  "phone": "+6591240934",
  "name": "FEDEX",
  "id": 3,
  "country": "Singapore",
  "city": "Singapore"
}
```

<h3 id="apiweb.v3.dispatcher.organisationcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Organisation ID|
|body|body|[DispatcherUpdateOrganisationRequest](#schemadispatcherupdateorganisationrequest)|false|Organisation information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherOrganisationResponse](#schemadispatcherorganisationresponse)|

## Dispatcher.OrganisationController.show

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/organisations/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/organisations/{id}`

*This endpoint retrieves information about an Corporate (aka Organisation)*

<h3 id="apiweb.v3.dispatcher.organisationcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Organisation ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherOrganisationResponse](#schemadispatcherorganisationresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Track-Order">[Dispatcher] Track Order</h1>

## Dispatcher.TrackController.track_order

<a id="opIdApiWeb.V3.Dispatcher.TrackController.track_order"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/track/{number} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/track/{number}`

*This endpoint retrieves tracking information for an Order*

<h3 id="apiweb.v3.dispatcher.trackcontroller.track_order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Tracking number|
|sender_id|query|integer|false|sender id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.trackcontroller.track_order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got tracking data|[TrackOrderResponse](#schematrackorderresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Worker">[Dispatcher] Worker</h1>

Dispatcher APIs for Worker Management

## Dispatcher.WorkerController.location_history

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.location_history"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/location_history \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/location_history`

*This endpoint retrieves locations of the worker according to a time window*

<h3 id="apiweb.v3.dispatcher.workercontroller.location_history-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|from|path|string|true|starting time|
|to|path|string|true|ending time|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.workercontroller.location_history-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got worker|[DispatcherWorkersPathResponse](#schemadispatcherworkerspathresponse)|

## Dispatcher.WorkerController.failed

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.failed"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/tasks/failed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/tasks/failed`

*This endpoint retrieves a list of a Worker's failed Tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.failed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

<h3 id="apiweb.v3.dispatcher.workercontroller.failed-responses">Responses</h3>

## Dispatcher.WorkerController.create

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/workers \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/workers`

*This endpoint creates a new Worker*

> Body parameter

```json
{
  "vehicle_type_ids": [
    1,
    2
  ],
  "tester": false,
  "phone": "+987654322",
  "password": "passwd112233",
  "otp_token": "1122334455",
  "national_id": "11335577",
  "name": "Mike Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "email": "mike-driver@yojee.com",
  "driver_license": "22446688",
  "current_vehicle_type_id": 1
}
```

<h3 id="apiweb.v3.dispatcher.workercontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCreateWorkerRequest](#schemadispatchercreateworkerrequest)|false|Worker information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.workercontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created worker|[DispatcherCreateWorkerResponse](#schemadispatchercreateworkerresponse)|

## Dispatcher.WorkerController.index

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/workers?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/workers`

*This endpoint retrieves a list of Workers*

<h3 id="apiweb.v3.dispatcher.workercontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|sort|query|string|false|the field to sort (id/distance/etc.)|
|order|query|string|false|asc, or desc|
|status|query|string|false|driver status|
|from|query|string|false|from timestamp|
|to|query|string|false|to timestamp|
|name|query|string|false|worker name|
|target_location|query|string|false|Geospatial coordinates of a location|
|with_in|query|float|false|Length of range (with target_location at center) in meters|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.workercontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherWorkersResponse](#schemadispatcherworkersresponse)|

## Dispatcher.WorkerController.assigned

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.assigned"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/tasks/assigned?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/tasks/assigned`

*This endpoint retrieves a list of a Worker's assigned Tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.assigned-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

<h3 id="apiweb.v3.dispatcher.workercontroller.assigned-responses">Responses</h3>

## Dispatcher.WorkerController.update

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/workers/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}`

*This endpoint updates a Worker's information*

> Body parameter

```json
{
  "vehicle_type_ids": [
    1,
    2
  ],
  "tester": true,
  "phone": "+987654322",
  "otp_token": "TNUSTU2YF7BCDOYR",
  "national_id": "11335577",
  "name": "Mike Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "email": "mike-driver@yojee.com",
  "driver_license": "22446688",
  "current_vehicle_type_id": 1
}
```

<h3 id="apiweb.v3.dispatcher.workercontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|body|body|[DispatcherUpdateWorkerRequest](#schemadispatcherupdateworkerrequest)|false|Worker information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.workercontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCreateWorkerResponse](#schemadispatchercreateworkerresponse)|

## Dispatcher.WorkerController.show

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}`

*This endpoint retrieves information about a Worker*

<h3 id="apiweb.v3.dispatcher.workercontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.workercontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got worker|[DispatcherCreateWorkerResponse](#schemadispatchercreateworkerresponse)|

## Dispatcher.WorkerController.delete

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/workers/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}`

*This endpoint deletes a Worker*

<h3 id="apiweb.v3.dispatcher.workercontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|

<h3 id="apiweb.v3.dispatcher.workercontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

## Dispatcher.WorkerController.approve

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.approve"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/approve \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/approve`

*This endpoint is used by a Dispatcher to approve a Worker*

<h3 id="apiweb.v3.dispatcher.workercontroller.approve-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.workercontroller.approve-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCreateWorkerResponse](#schemadispatchercreateworkerresponse)|

## Dispatcher.WorkerController.completed

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.completed"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/tasks/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/workers/{id}/tasks/completed`

*This endpoint retrieves a list of a Worker's completed Tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.completed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

<h3 id="apiweb.v3.dispatcher.workercontroller.completed-responses">Responses</h3>

<h1 id="Yojee-APIs-[Dispatcher]-Order">[Dispatcher] Order</h1>

Dispatcher APIs for Order Management

## Dispatcher.OrderController.cancel

<a id="opIdApiWeb.V3.Dispatcher.OrderController.cancel"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/orders/{number}/cancel \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/orders/{number}/cancel`

*This endpoint cancels an Order*

<h3 id="apiweb.v3.dispatcher.ordercontroller.cancel-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Order number|

<h3 id="apiweb.v3.dispatcher.ordercontroller.cancel-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

## Dispatcher.OrderController.update

<a id="opIdApiWeb.V3.Dispatcher.OrderController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/orders/{number} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/orders/{number}`

*This endpoint is used by a Dispatcher to update an Order*

> Body parameter

```json
{
  "price_currency": "string",
  "price_amount": 0,
  "external_id": "string"
}
```

<h3 id="apiweb.v3.dispatcher.ordercontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Order number|
|body|body|[DispatcherUpdateOrderRequest](#schemadispatcherupdateorderrequest)|false|Order information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.ordercontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Create order response success|[CreateOrderResponse](#schemacreateorderresponse)|

## Dispatcher.OrderController.show

<a id="opIdApiWeb.V3.Dispatcher.OrderController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/orders/{number} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/orders/{number}`

*This endpoint retrieves information about an Order*

<h3 id="apiweb.v3.dispatcher.ordercontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|number|path|string|true|Order Number|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.ordercontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherOrderResponse](#schemadispatcherorderresponse)|

## Dispatcher.OrderController.create

<a id="opIdApiWeb.V3.Dispatcher.OrderController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/orders`

*This endpoint creates an Order*

> Body parameter

```json
{
  "steps": [
    null
  ],
  "sender_type": "string",
  "sender_id": 0,
  "price_currency": "string",
  "price_amount": 0,
  "items": [
    null
  ],
  "item_steps": [
    null
  ]
}
```

<h3 id="apiweb.v3.dispatcher.ordercontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[CreateOrderRequest](#schemacreateorderrequest)|false|Order information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.ordercontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Create order response success|[CreateOrderResponse](#schemacreateorderresponse)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

## Dispatcher.OrderController.index

<a id="opIdApiWeb.V3.Dispatcher.OrderController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/orders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/orders`

*This endpoint retrieves a list of Orders*

<h3 id="apiweb.v3.dispatcher.ordercontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|status|query|string|false|an array of status for order, ie: [created, accepted, completed, cancelled]|
|paid|query|boolean|false|whether the order is paid|
|from|query|string|false|from datetime in ISO8601 format|
|to|query|string|false|to datetime in ISO8601 format|
|sender_id|query|integer|false|Sender ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|order|query|string|false|asc, or desc|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.ordercontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherOrdersResponse](#schemadispatcherordersresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-OrderItem">[Dispatcher] OrderItem</h1>

Dispatcher APIs for OrderItem Management

## Dispatcher.OrderItemController.logs

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.logs"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/order_items/{number}/logs \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/order_items/{number}/logs`

*this endpoint is used by a Dispatcher to view the logs for a single order_item*

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.logs-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Order Item id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.logs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OrderItemsLogsResponse](#schemaorderitemslogsresponse)|

## Dispatcher.OrderItemController.cancel_multiple

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.cancel_multiple"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/order_items/cancel_multiple \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/order_items/cancel_multiple`

*This endpoint is used by a Dispatcher to cancel one or many OrderItems*

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.cancel_multiple-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|ids|path|array[any]|true|Order Item IDs|

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.cancel_multiple-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

## Dispatcher.OrderItemController.update

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella.yojee.com/api/v3/dispatcher/order_items/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella.yojee.com/api/v3/dispatcher/order_items/{id}`

*This endpoint is used by a Dispatcher to update an OrderItem*

> Body parameter

```json
{
  "width": 2,
  "weight": 2,
  "service_type": "same_day",
  "payload_type": "Updated document",
  "length": 2,
  "info": "info_test",
  "height": 2,
  "external_customer_id3": "changed_external_customer_id3",
  "external_customer_id2": "changed_external_customer_id2",
  "external_customer_id": "changed_external_customer_id",
  "dropoff": {
    "to_time": "2018-12-12T08:56:23.831230",
    "state": "Singapore",
    "postal_code": "332211",
    "lng": 103.8469761,
    "lat": 1.2880209,
    "from_time": "2018-12-12T00:56:23.831230",
    "country": "Singapore",
    "contact_phone": "+6581551123",
    "contact_name": "vivek",
    "contact_email": "recipient@example.com",
    "contact_company": "Nike",
    "address2": "#04-01",
    "address": "59 New Bridge Road"
  },
  "description": "Updated Gift"
}
```

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Order Item id|
|body|body|[OrderItemsUpdateRequest](#schemaorderitemsupdaterequest)|false|Order Item information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OrderItemsShowResponse](#schemaorderitemsshowresponse)|

## Dispatcher.OrderItemController.show

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/order_items/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/order_items/{id}`

*This endpoint retrieves information about an OrderItem*

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Order Item id|
|delivery_trail_sort|query|string|false|asc or desc for delivery trail sort|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OrderItemsShowResponse](#schemaorderitemsshowresponse)|

## Dispatcher.OrderItemController.index

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/order_items?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/order_items`

*This endpoint retrieves a list of OrderItems*

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|status|query|string|false|status of the order item, can be string or list|
|service_type|query|string|false|service type of the order item, can be string or list|
|order_id|query|string|false|order_id, can be string or an array|
|from|query|string|false|from timestamp|
|to|query|string|false|to timestamp|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OrderItemsIndexResponse](#schemaorderitemsindexresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Batch">[Dispatcher] Batch</h1>

Dispatcher APIs for Batch Management

## Dispatcher.BatchController.download_sample

<a id="opIdApiWeb.V3.Dispatcher.BatchController.download_sample"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/batches/download_sample?company_id=0&format=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/batches/download_sample`

*This endpoint downloads a sample batch file of a company*

<h3 id="apiweb.v3.dispatcher.batchcontroller.download_sample-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|company_id|query|integer|true|Company Id|
|format|query|string|true|Template format|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.dispatcher.batchcontroller.download_sample-responses">Responses</h3>

## Dispatcher.BatchController.create

<a id="opIdApiWeb.V3.Dispatcher.BatchController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/batches \
  -H 'Content-Type: multipart/form-data' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/batches`

*This endpoint is used by a Dispatcher to upload a batch file*

> Body parameter

```yaml
file: string

```

<h3 id="apiweb.v3.dispatcher.batchcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|uploader_id|query|integer|false|Uploader Id|
|external_id|query|string|false|External Id|
|container_no|query|string|false|Container Number|
|body|body|[ApiWeb.V3.Dispatcher.BatchController.create](#schemaapiweb.v3.dispatcher.batchcontroller.create)|false|none|
|» file|body|string(binary)|false|The file to upload|

<h3 id="apiweb.v3.dispatcher.batchcontroller.create-responses">Responses</h3>

## Dispatcher.BatchController.check_status

<a id="opIdApiWeb.V3.Dispatcher.BatchController.check_status"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/batches/check_status \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/batches/check_status`

*This endpoint checks the status of a Batch*

<h3 id="apiweb.v3.dispatcher.batchcontroller.check_status-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|batch_id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.dispatcher.batchcontroller.check_status-responses">Responses</h3>

## Dispatcher.BatchController.continue

<a id="opIdApiWeb.V3.Dispatcher.BatchController.continue"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/batches/{id}/continue \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/batches/{id}/continue`

*This endpoint continues submiting a Batch regardless of being given missing info*

> Body parameter

```yaml
file: string

```

<h3 id="apiweb.v3.dispatcher.batchcontroller.continue-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|query|integer|false|Batch Id|
|external_id|query|integer|false|[optional] External id|
|container_no|query|integer|false|[optional] Container no|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|object|false|none|
|» file|body|string(binary)|false|The file to upload|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.batchcontroller.continue-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Batch in progress|[BatchContinueResponse](#schemabatchcontinueresponse)|

## Dispatcher.BatchController.get_order

<a id="opIdApiWeb.V3.Dispatcher.BatchController.get_order"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/batches/get_order \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/batches/get_order`

*This endpoint retrieves detailed information about a Batch*

<h3 id="apiweb.v3.dispatcher.batchcontroller.get_order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|batch_id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.dispatcher.batchcontroller.get_order-responses">Responses</h3>

## Dispatcher.BatchController.cancel

<a id="opIdApiWeb.V3.Dispatcher.BatchController.cancel"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/batches/{id}/cancel \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/batches/{id}/cancel`

*This endpoint cancel a Batch*

<h3 id="apiweb.v3.dispatcher.batchcontroller.cancel-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.batchcontroller.cancel-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Batch cancelled|[BatchCancelledResponse](#schemabatchcancelledresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-TaskGroup">[Dispatcher] TaskGroup</h1>

Dispatcher APIs for TaskGroup Management

## Dispatcher.TaskController.index

<a id="opIdApiWeb.V3.Dispatcher.TaskController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/tasks?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/tasks`

*This endpoint list tasks of a company*

<h3 id="apiweb.v3.dispatcher.taskcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|from|query|string|false|from datetime in ISO8601 format|
|to|query|string|false|to datetime in ISO8601 format|
|include_transfer_properties|query|boolean|false|include info/properties on transfers - slower query, larger response|
|task_group_states[]|query|array[any]|false|task_group states|
|task_states[]|query|array[any]|false|task states|
|task_types[]|query|array[any]|false|task types|
|show_reported_tasks|query|boolean|false|show reported task - absence means ignore `reported` trait|
|cancelled|query|boolean|false|show cancelled task|
|broadcasted|query|boolean|false|show broadcasted tasks|
|accepted|query|boolean|false|show accepted tasks|
|show_incomplete_info_order_step|query|boolean|false|show incomplete info order_step - absence means ignore `incomplete info` trait|
|order_item_states[]|query|array[any]|false|order_item states|
|order_number|query|string|false|order number|
|order_item_tracking_number|query|string|false|order item tracking number|
|us_partner_company_ids[]|query|array[integer]|false|array of upstream partner company ids|
|ds_partner_company_ids[]|query|array[integer]|false|array of downstream partner company ids|
|task_group_ids[]|query|array[integer]|false|array of task_group ids|
|order_item_ids[]|query|array[integer]|false|array of order_item ids|
|worker_ids[]|query|array[integer]|false|array of worker ids|
|item_volume_range|query|string|false|item volume defined by min,max in integer|
|item_weight_range|query|string|false|item weight defined by min,max in integer|
|geo_circle|query|string|false|geo_circle defined by lat,lon,radius in float|
|region_ids[]|query|array[integer]|false|array of region ids|
|sort_by|query|string|false|Sorting By|
|service_type_keys[]|query|string|false|array of service types|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

#### Enumerated Values

|Parameter|Value|
|---|---|
|task_group_states[]|unassigned|
|task_group_states[]|assigned|
|task_group_states[]|completed|
|task_group_states[]|cancelled|
|task_states[]|created|
|task_states[]|completed|
|task_states[]|failed|
|task_types[]|pickup|
|task_types[]|dropoff|
|order_item_states[]|created|
|order_item_states[]|processing|
|order_item_states[]|completed|
|order_item_states[]|cancelled|
|sort_by|from_time|
|sort_by|to_time|
|sort_by|completion_time|
|sort_by|task_group|
|sort_by|order_item_inserted_at|
|sort_by|sequence|
|service_type_keys[]|same_day|
|service_type_keys[]|next_day|
|service_type_keys[]|express|
|service_type_keys[]|custom|

<h3 id="apiweb.v3.dispatcher.taskcontroller.index-responses">Responses</h3>

## Dispatcher.TaskGroupController.show

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}`

*This endpoint retrieves information about a TaskGroup*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task group ID|

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.show-responses">Responses</h3>

## Dispatcher.TaskGroupController.unassigned

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.unassigned"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/unassigned?page=1&page_size=25 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/unassigned`

*This endpoint retrieves a list of unassigned TaskGroups*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.unassigned-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|task_group_ids|query|string|false|an array of task_group_id for task group|
|from|query|string|false|from datetime in ISO8601 format|
|to|query|string|false|to datetime in ISO8601 format|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.unassigned-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UnassignedTaskGroupsIndexResponse](#schemaunassignedtaskgroupsindexresponse)|

## Dispatcher.TaskGroupController.assign_multiple

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.assign_multiple"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/task_groups/assign_multiple \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/task_groups/assign_multiple`

*This endpoint assigns multiple TaskGroups to a Worker*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.assign_multiple-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|ids|query|array[any]|false|array of task_group ids|
|worker_id|query|integer|false|Worker ID|
|price_currency|query|string|false|Price's currency|
|price_amount|query|number|false|Price's amount|

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.assign_multiple-responses">Responses</h3>

## Dispatcher.TaskGroupController.step_items

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.step_items"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}/step_items/{step_id}?type=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}/step_items/{step_id}`

*This endpoint retrieves detailed information for Items in a TaskGroup*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.step_items-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task Group ID|
|step_id|path|integer|true|Step ID|
|type|query|string|true|Pickup/Dropoff|

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.step_items-responses">Responses</h3>

## Dispatcher.TaskGroupController.assigned

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.assigned"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/assigned?page=1&page_size=25 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/assigned`

*This endpoint retrieves a list of assigned TaskGroups*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.assigned-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|status|query|string|false|an array of status for task group, ie: [assigned, accepted, completed, cancelled], defaults to [assigned]|
|worker_type|query|string|false|Worker contract type (employee/freelancer)|
|current_vehicle_type_id|query|integer|false|Worker vehicle type id|
|task_group_ids|query|string|false|an array of task_group_id for task group|
|from|query|string|false|from datetime in ISO8601 format|
|to|query|string|false|to datetime in ISO8601 format|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.assigned-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AssignedTaskGroupsIndexResponse](#schemaassignedtaskgroupsindexresponse)|

## Dispatcher.TaskGroupController.unassign_worker

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.unassign_worker"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}/unassign_worker \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}/unassign_worker`

*This endpoint unassigns a TaskGroup from a Worker*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.unassign_worker-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task Group ID|

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.unassign_worker-responses">Responses</h3>

## Dispatcher.TaskGroupController.join_chat

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.join_chat"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}/join_chat \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}/join_chat`

*This endpoint adds a Dispatcher to a chat group*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.join_chat-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task Group ID|

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.join_chat-responses">Responses</h3>

## Dispatcher.TaskGroupController.accepted

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.accepted"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/accepted \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/task_groups/accepted`

*This endpoint retrieves a Worker's list of accepted TaskGroups*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.accepted-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|worker_id|query|integer|false|Worker ID|

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.accepted-responses">Responses</h3>

## Dispatcher.TaskGroupController.assign_worker

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.assign_worker"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}/assign_worker \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{id}/assign_worker`

*This endpoint assigns a TaskGroup to a Worker*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.assign_worker-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task group ID|
|worker_id|query|integer|false|Worker ID|
|price_currency|query|string|false|Price's currency|
|price_amount|query|number|false|Price's amount|

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.assign_worker-responses">Responses</h3>

<h1 id="Yojee-APIs-[Dispatcher]-Addressbook">[Dispatcher] Addressbook</h1>

## Dispatcher.AddressbookController.search

<a id="opIdApiWeb.V3.Dispatcher.AddressbookController.search"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/addressbook/search?query=string&page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/addressbook/search`

*This endpoint search address item of a company*

<h3 id="apiweb.v3.dispatcher.addressbookcontroller.search-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|query|query|string|true|external_id/contact/address text query|
|category|query|string|false|category of address item|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

<h3 id="apiweb.v3.dispatcher.addressbookcontroller.search-responses">Responses</h3>

<h1 id="Yojee-APIs-[Dispatcher]-Task">[Dispatcher] Task</h1>

Dispatcher APIs for Task Management

## Dispatcher.TaskController.update

<a id="opIdApiWeb.V3.Dispatcher.TaskController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/tasks/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/tasks/{id}`

*This endpoint updates a Task's details*

<h3 id="apiweb.v3.dispatcher.taskcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task ID|
|task_group_id|path|integer|true|Task group ID|

<h3 id="apiweb.v3.dispatcher.taskcontroller.update-responses">Responses</h3>

## Dispatcher.TaskController.bulk_complete

<a id="opIdApiWeb.V3.Dispatcher.TaskController.bulk_complete"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/tasks/bulk_complete \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/tasks/bulk_complete`

*this endpoint is used by a dispatcher to complete multiple tasks*

> Body parameter

```json
{
  "task_ids": [
    1,
    2,
    3
  ]
}
```

<h3 id="apiweb.v3.dispatcher.taskcontroller.bulk_complete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[BulkTaskCompletionRequestByDispatcher](#schemabulktaskcompletionrequestbydispatcher)|false|Task Completion information|

<h3 id="apiweb.v3.dispatcher.taskcontroller.bulk_complete-responses">Responses</h3>

## Dispatcher.AllocationController.allocate

<a id="opIdApiWeb.V3.Dispatcher.AllocationController.allocate"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/tasks/allocate \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/tasks/allocate`

*This endpoint assigns a tasks from planner to a recommended worker*

> Body parameter

```json
{
  "_json": [
    {
      "worker_id": 2,
      "tasks": [
        {
          "id": "startFromDepot",
          "eta": "2018-08-20T16:00:00.000Z"
        },
        {
          "polyline": [
            [
              103.96689,
              1.330653
            ],
            [
              103.96689,
              1.330653
            ]
          ],
          "id": "46",
          "eta": "2018-08-20T23:45:00.000Z"
        }
      ],
      "polyline": [
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ]
      ],
      "commission": "23.00"
    },
    {
      "worker_id": 232,
      "tasks": [
        {
          "id": "startFromDepot",
          "eta": "2018-08-20T16:00:00.000Z"
        },
        {
          "polyline": [
            [
              103.96689,
              1.330653
            ],
            [
              103.96689,
              1.330653
            ]
          ],
          "id": "1223",
          "eta": "2018-08-20T23:45:00.000Z"
        }
      ],
      "polyline": [
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ]
      ],
      "commission": "43.00"
    }
  ]
}
```

<h3 id="apiweb.v3.dispatcher.allocationcontroller.allocate-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[AllocationRequest](#schemaallocationrequest)|false|Allocation request|

<h3 id="apiweb.v3.dispatcher.allocationcontroller.allocate-responses">Responses</h3>

## Dispatcher.TaskController.batch_complete_status

<a id="opIdApiWeb.V3.Dispatcher.TaskController.batch_complete_status"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/tasks/batches/{id}/status \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/tasks/batches/{id}/status`

*This endpoint checks the status of all Tasks in a Batch*

<h3 id="apiweb.v3.dispatcher.taskcontroller.batch_complete_status-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Batch ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.taskcontroller.batch_complete_status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BulkCompletionStatus](#schemabulkcompletionstatus)|

## Dispatcher.TaskController.delete_task_exception

<a id="opIdApiWeb.V3.Dispatcher.TaskController.delete_task_exception"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/delete_task_exception \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/delete_task_exception`

*This endpoint deletes a TaskException associated with a Task*

<h3 id="apiweb.v3.dispatcher.taskcontroller.delete_task_exception-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|task_group_id|path|integer|true|Task Group Id|
|id|path|integer|true|Task Exception Id|

<h3 id="apiweb.v3.dispatcher.taskcontroller.delete_task_exception-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

## Dispatcher.TaskController.mark_as_failed

<a id="opIdApiWeb.V3.Dispatcher.TaskController.mark_as_failed"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/mark_as_failed \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/mark_as_failed`

*This endpoint marks a Task as failed by creating an associated TaskException*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.dispatcher.taskcontroller.mark_as_failed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|task_group_id|path|integer|true|Task Group Id|
|id|path|integer|true|Task Id|
|body|body|[ApiWeb.V3.Worker.TaskController.mark_as_failedDescriptions](#schemaapiweb.v3.worker.taskcontroller.mark_as_faileddescriptions)|true|Task Exception descriptions|

<h3 id="apiweb.v3.dispatcher.taskcontroller.mark_as_failed-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|ok|None|

## Dispatcher.TaskController.complete

<a id="opIdApiWeb.V3.Dispatcher.TaskController.complete"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/complete \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/complete`

*This endpoint marks a Task as completed by a Dispatcher*

<h3 id="apiweb.v3.dispatcher.taskcontroller.complete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|task_group_id|path|integer|true|Task Group Id|
|id|path|integer|true|Task ID|

<h3 id="apiweb.v3.dispatcher.taskcontroller.complete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|ok|None|

<h1 id="Yojee-APIs-[Dispatcher]-TaskExceptionReason">[Dispatcher] TaskExceptionReason</h1>

Dispatcher APIs for TaskExceptionReason Management

## Dispatcher.TaskExceptionReasonController.delete

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/task_exception_reasons/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/task_exception_reasons/{id}`

*This endpoint deletes a TaskExceptionReason*

<h3 id="apiweb.v3.dispatcher.taskexceptionreasoncontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|TaskExceptionReason Id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.taskexceptionreasoncontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TaskExceptionReasonResponse](#schemataskexceptionreasonresponse)|

## Dispatcher.TaskExceptionReasonController.create

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/task_exception_reasons \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/task_exception_reasons`

*This endpoint creates a new TaskExceptionReason*

> Body parameter

```json
{
  "description": "Sender not available",
  "company_id": 1
}
```

<h3 id="apiweb.v3.dispatcher.taskexceptionreasoncontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[TaskExceptionReasonRequest](#schemataskexceptionreasonrequest)|false|TaskExceptionReason|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.taskexceptionreasoncontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TaskExceptionReasonResponse](#schemataskexceptionreasonresponse)|

## Dispatcher.TaskExceptionReasonController.index

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/task_exception_reasons \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/task_exception_reasons`

*This endpoint retrieves all TaskExceptionReasons for a Company*

<h3 id="apiweb.v3.dispatcher.taskexceptionreasoncontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.taskexceptionreasoncontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TaskExceptionReasonsResponse](#schemataskexceptionreasonsresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-SubTask">[Dispatcher] SubTask</h1>

Dispatcher APIs for SubTask Management

## Dispatcher.SubTaskController.index

<a id="opIdApiWeb.V3.Dispatcher.SubTaskController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks`

*This endpoint retrieves a list of SubTasks for an OrderItem*

<h3 id="apiweb.v3.dispatcher.subtaskcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|order_item_id|path|integer|true|Order Item ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.subtaskcontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherSubTasksResponse](#schemadispatchersubtasksresponse)|

## Dispatcher.SubTaskController.show

<a id="opIdApiWeb.V3.Dispatcher.SubTaskController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks/{id}`

*This endpoint retrieves information about a SubTask*

<h3 id="apiweb.v3.dispatcher.subtaskcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Sub Task ID|
|order_item_id|path|integer|true|Order Item ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.subtaskcontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got sub task|[DispatcherRuleResponse](#schemadispatcherruleresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-SubTaskRule">[Dispatcher] SubTaskRule</h1>

Dispatcher APIs for SubTaskRule Management

## Dispatcher.SubTaskRuleController.update

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules/{id}`

*This endpoint updates a SubTaskRule*

> Body parameter

```json
{
  "meta": {
    "photo_type": "signature",
    "photo_title": "Signature of client"
  },
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}
```

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Sub Task Rule ID|
|body|body|[DispatcherUpdateRuleRequest](#schemadispatcherupdaterulerequest)|false|Sub Task Rule information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherCreateRuleResponse](#schemadispatchercreateruleresponse)|

## Dispatcher.SubTaskRuleController.show

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules/{id}`

*This endpoint retrieves information about a SubTaskRule*

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Sub Task Rule ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got sub task rule|[DispatcherCreateRuleResponse](#schemadispatchercreateruleresponse)|

## Dispatcher.SubTaskRuleController.delete

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules/{id}`

*This endpoint marks a SubTaskRule as invalidated*

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Sub Task Rule ID|

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

## Dispatcher.SubTaskRuleController.create

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules`

*This endpoint creates a new SubTaskRule*

> Body parameter

```json
{
  "meta": {
    "photo_type": "signature",
    "photo_title": "Signature of client"
  },
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}
```

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCreateRuleRequest](#schemadispatchercreaterulerequest)|false|Sub Task Rule information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created sub task rule|[DispatcherCreateRuleResponse](#schemadispatchercreateruleresponse)|

## Dispatcher.SubTaskRuleController.index

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/sub_task_rules`

*This endpoint retrieves a list of SubTaskRules*

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.subtaskrulecontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherRulesResponse](#schemadispatcherrulesresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Planner-Setting">[Dispatcher] Planner Setting</h1>

## Dispatcher.PlanSettingsController.show

<a id="opIdApiWeb.V3.Dispatcher.PlanSettingsController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/settings/:id \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/settings/:id`

*This endpoint retrieves a setting belonging to a Company*

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Setting ID|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got list of company settings|[DispatcherSettingResponse](#schemadispatchersettingresponse)|

## Dispatcher.PlanSettingsController.delete

<a id="opIdApiWeb.V3.Dispatcher.PlanSettingsController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella.yojee.com/api/v3/dispatcher/plan_settings/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella.yojee.com/api/v3/dispatcher/plan_settings/{id}`

*This endpoint deletes a setting*

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Setting ID|

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

## Dispatcher.PlanSettingsController.update

<a id="opIdApiWeb.V3.Dispatcher.PlanSettingsController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/settings/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/settings/{id}`

*This endpoint updates a Dispatcher's information*

> Body parameter

```json
{
  "settings": {
    "sample settings": "sample value"
  },
  "name": "default"
}
```

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Setting ID|
|body|body|[DispatcherUpdateSettingRequest](#schemadispatcherupdatesettingrequest)|false|Company setting information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Updated the company setting|[DispatcherSettingResponse](#schemadispatchersettingresponse)|

## Dispatcher.PlanSettingsController.create

<a id="opIdApiWeb.V3.Dispatcher.PlanSettingsController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/settings \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/settings`

*This endpoint creates a new Dispatcher*

> Body parameter

```json
{
  "settings": {
    "sample settings": "sample value"
  },
  "name": "default"
}
```

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCreateSettingRequest](#schemadispatchercreatesettingrequest)|false|Company setting information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created the company setting|[DispatcherSettingResponse](#schemadispatchersettingresponse)|

## Dispatcher.PlanSettingsController.index

<a id="opIdApiWeb.V3.Dispatcher.PlanSettingsController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/settings \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/settings`

*This endpoint retrieves a list of settings belonging to a Company*

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.plansettingscontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got list of company settings|[DispatcherIndexSettingResponse](#schemadispatcherindexsettingresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Broadcast">[Dispatcher] Broadcast</h1>

Broadcast management

## Dispatcher.BroadcastController.create

<a id="opIdApiWeb.V3.Dispatcher.BroadcastController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/broadcasts \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/broadcasts`

*This endpoint creates a Broadcast for a TaskGroup*

> Body parameter

```json
{
  "timeout_in_minutes": 20,
  "task_group_ids": [
    1,
    2
  ],
  "price_currency": "SGD",
  "price_amount": 500
}
```

<h3 id="apiweb.v3.dispatcher.broadcastcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[BroadcastRequest](#schemabroadcastrequest)|false|Broadcast|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.broadcastcontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BroadcastResponse](#schemabroadcastresponse)|

<h1 id="Yojee-APIs-[Dispatcher]-Chat">[Dispatcher] Chat</h1>

## Dispatcher.ChatController.worker_channel

<a id="opIdApiWeb.V3.Dispatcher.ChatController.worker_channel"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/chat/worker_channel/{worker_id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/chat/worker_channel/{worker_id}`

*This endpoint returns list of worker channels*

<h3 id="apiweb.v3.dispatcher.chatcontroller.worker_channel-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|worker_id|path|integer|true|Worker ID|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.chatcontroller.worker_channel-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherChatMessagesResponse](#schemadispatcherchatmessagesresponse)|

## Dispatcher.ChatController.send_message

<a id="opIdApiWeb.V3.Dispatcher.ChatController.send_message"></a>

> Code samples

```shell

curl -X POST https://umbrella.yojee.com/api/v3/dispatcher/chat/send_message \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella.yojee.com/api/v3/dispatcher/chat/send_message`

*Dispatcher sends message*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.dispatcher.chatcontroller.send_message-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[ApiWeb.V3.Dispatcher.ChatController.send_messageMessage](#schemaapiweb.v3.dispatcher.chatcontroller.send_messagemessage)|false|Text Message|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.chatcontroller.send_message-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherChatMessageResponse](#schemadispatcherchatmessageresponse)|

## Dispatcher.ChatController.channel

<a id="opIdApiWeb.V3.Dispatcher.ChatController.channel"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/chat/channel/{channel_id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/chat/channel/{channel_id}`

*This endpoint return channel information*

<h3 id="apiweb.v3.dispatcher.chatcontroller.channel-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|channel_id|path|integer|true|Channel ID|
|last_message_date|query|string|false|Last Message date|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.dispatcher.chatcontroller.channel-responses">Responses</h3>

## Dispatcher.ChatController.channels

<a id="opIdApiWeb.V3.Dispatcher.ChatController.channels"></a>

> Code samples

```shell

curl -X GET https://umbrella.yojee.com/api/v3/dispatcher/chat/channels \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella.yojee.com/api/v3/dispatcher/chat/channels`

*This endpoint returns list of dispatcher channels*

<h3 id="apiweb.v3.dispatcher.chatcontroller.channels-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

<h3 id="apiweb.v3.dispatcher.chatcontroller.channels-responses">Responses</h3>

## Dispatcher.ChatController.update

<a id="opIdApiWeb.V3.Dispatcher.ChatController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella.yojee.com/api/v3/dispatcher/chat/channel \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella.yojee.com/api/v3/dispatcher/chat/channel`

*This endpoint returns update worker channel data*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.dispatcher.chatcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|any|false|Last read on date in ISO8601 format|

<h3 id="apiweb.v3.dispatcher.chatcontroller.update-responses">Responses</h3>

<h1 id="Yojee-APIs-[Dispatcher]-Webhook">Webhooks</h1>

Webhooks allow you to build or setup applications which subscribe to certain events on Yojee. This mechanism is also useful for services that are not directly responsible for making an API request, but still need to know the response from that request.

When one of those events is triggered, we'll send a HTTP POST payload to the webhook's configured URL.

## Events

When configuring a webhook, you can choose which events you would like to receive payloads for. You can change the list of subscribed events through the API or UI anytime.

Each event corresponds to a certain set of actions that can happen to your company. For example, if you subscribe to the `order.created` event you'll receive detailed payloads every time an order is created.

This is a list of all the types of events we currently send. We may add more at any time, so in developing and maintaining your code, you should not assume that only these types exist.

| Name              | Description                            |
|-------------------|----------------------------------------|
| order.created     | Occurs whenever an order is created    |
| sender.created    | Occurs whenever a sender is created    |
| payment.completed | Occurs whenever a payment is completed |

## Configuring your Webhooks settings

Webhooks are configured in the Dashboard's Webhooks settings section. Click Add endpoint to reveal a form where you can add a new URL for receiving webhooks.

## Delivery headers

HTTP POST payloads that are delivered to your webhook's configured URL endpoint will contain a header

| Header                | Description                                                                                                                                                                                                     |
|---------------------  |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| yojee-signature       | The HMAC hex digest of the response body. The HMAC hex digest is generated using the `sha256` hash function and the `secret` as the HMAC `key`.  |

## Responding to a webhook

To acknowledge receipt of a webhook, your endpoint should return a 2xx HTTP status code. All response codes outside this range, including 3xx codes, will indicate to Yojee that you did not receive the webhook.

We will attempt to deliver your webhooks for up to five times with an exponential back off.

| Retry | Seconds |
|-------|---------|
| 1     | 120     |
| 2     | 360     |
| 3     | 840     |
| 4     | 1800    |
| 5     | 3720    |

When viewing information about a specific event through the Dashboard, you can check how many times we've attempted to send an event to an endpoint by clicking on that endpoint URL in the Webhook details section. This will show you the latest response we received from your endpoint, along with a list of all attempted webhooks and the respective HTTP status codes we received.

## Best practices

If your webhook script performs complex logic, or makes network calls, it's possible that the script would time out before Yojee sees its complete execution. For that reason, you might want to have your webhook endpoint immediately acknowledge receipt by returning a 2xx HTTP status code, and then perform the rest of its duties.

## Checking Webhook Signatures

Yojee signs the webhook events it sends to your endpoints. We do so by including a signature using a hash-based message authentication code (HMAC) with SHA-256 in each event’s `yojee-signature` header. This allows you to validate that the events were sent by Yojee, not by a third party.

Before you can verify signatures, you need to retrieve your endpoint’s secret from your Dashboard’s Webhooks settings. Each secret is unique to the endpoint to which it corresponds.

**Step 1: Get timestamp and signature from the header**

Retrieve the `yojee-request-timestamp` and `yojee-signature` header on the HTTP request

**Step 2: Prepare the signed payload string**

You achieve this by concatenating:
  * The timestamp (as a string)
  * The character `.`
  * The actual JSON payload (i.e., the request’s body)

**Step 3: Determine the expected signature**

Compute an HMAC with the SHA256 hash function. Use the endpoint’s signing secret as the key, and use the signed payload string as the message.

**Step 4: Compare signatures**

Compare the signature in the header to the expected signature. If a signature matches, compute the difference between the current timestamp and the received timestamp, then decide if the difference is within your tolerance.


## Events

### The event object

| Attributes  | Description                                                                     |
|------------ |-------------------------------------------------------------------------------- |
| id          | Unique identifier for the event.                                                |
| event_type  | Description of the event (e.g. order.created or payment.completed).             |
| data        | Object containing data associated with the event.                               |
| webhook_id  | The id of webhook which subscribes the event                                    |
| created_at  | Time at which the event was created. Measured in seconds since the Unix epoch.  |


### order.created

<a id="opIdApiWeb.V3.Webhook.order-created"></a>

Data: [WebhookOrderResponse](#schema_webhook_order_response)

### sender.created

<a id="opIdApiWeb.V3.Webhook.sender-created"></a>

Data: [WebhookSenderResponse](#schema_webhook_sender_response)


### payment.completed

<a id="opIdApiWeb.V3.Webhook.payment-completed"></a>

Data: [WebhookPaymentResponse](#schema_webhook_payment_response)


# Schemas

<h2 id="tocSworkerresponse">WorkerResponse</h2>

<a id="schemaworkerresponse"></a>

```json
{
  "status": "on_duty",
  "id": 1,
  "avatar": "https://s3-ap-southeast-1.amazonaws.com/signature.jpg"
}

```

*Worker Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|string|false|none|none|
|id|integer|false|none|none|
|avatar|string|false|none|none|

<h2 id="tocSworkerchatmessagesresponse">WorkerChatMessagesResponse</h2>

<a id="schemaworkerchatmessagesresponse"></a>

```json
{
  "data": {
    "messages": [
      {
        "user_profile": {
          "user_profile_id": 299,
          "name": "Demond Terry"
        },
        "inserted_at": "2018-10-23T07:57:27.538169Z",
        "incoming": false,
        "id": 133,
        "created_at": "2018-10-23T07:56:00.0Z",
        "content": {
          "type": "image",
          "text": "it has value if it is not attachment and it's type is 'text'",
          "attachment": {
            "thumbnail": "https://s3-ap-southeast-1.amazonaws.com/thumbnail_signature.png",
            "original": "https://s3-ap-southeast-1.amazonaws.com/original_signature.png"
          }
        }
      }
    ],
    "channel": {
      "members": [],
      "id": 154
    }
  }
}

```

*Chat Messages Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSmapsautocompleterequest">MapsAutoCompleteRequest</h2>

<a id="schemamapsautocompleterequest"></a>

```json
{
  "query": "1 Anson Rd, Singapore",
  "country_iso": "sg"
}

```

*POST body for address autocomplete*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|string|true|none|Address|
|country_iso|string|false|none|Country ISO code|

<h2 id="tocSdispatcherrulesresponse">DispatcherRulesResponse</h2>

<a id="schemadispatcherrulesresponse"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 1,
    "current_page": 1
  },
  "data": [
    {
      "meta": {
        "photo_type": "signature",
        "photo_title": "Signature of client"
      },
      "event": "pickup_completed",
      "company_id": 1,
      "action": "upload_photo"
    }
  ]
}

```

*Sub Task Rules Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSmapsautocompleteresponse">MapsAutoCompleteResponse</h2>

<a id="schemamapsautocompleteresponse"></a>

```json
{
  "data": {
    "name": "1 Anson Rd",
    "lng": 103.8462451,
    "lat": 1.2754876,
    "address": "1 Anson Rd, Singapore"
  }
}

```

*Response schema for address autocomplete*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocStasksresponse">TasksResponse</h2>

<a id="schematasksresponse"></a>

```json
{
  "pagination": {
    "total_pages": 1,
    "total_count": 2,
    "limit_value": 10,
    "current_page": 1
  },
  "data": [
    {
      "type": "pickup",
      "to": "2018-03-22T16:14:06.000000Z",
      "task_group_id": 2353,
      "sub_tasks": {},
      "state": "failed",
      "start_time": "2018-03-22T16:14:06.000000Z",
      "service_type": "sameday",
      "postal_code": "12345",
      "position": 0,
      "order_item_tracking_number": "YOJ-UUXOUKPNPT0",
      "order_item_id": 303,
      "lng": 106.6913373,
      "lat": 10.785092,
      "item": {
        "width": 1,
        "weight": 1,
        "volumetric_weight": 10,
        "volume": 200,
        "length": 1,
        "height": 1,
        "global_tracking_number": "YOJ-UUXOUKPNPT0"
      },
      "id": 551,
      "from": "2018-03-22T15:14:06.000000Z",
      "external_id": "12345",
      "external_customer_id3": "10644",
      "external_customer_id2": "5854977",
      "external_customer_id": "415454",
      "description": "Gift",
      "country": "Singapore",
      "container_no": "123",
      "contact": {
        "phone": "+6581551123",
        "name": "jens"
      },
      "completion_time": "2018-03-22T16:14:06.000000Z",
      "address_state": "State",
      "address2": "Address 2",
      "address": "40 Pham Ngoc Thach P6, Q3, HCM 1",
      "additional_info": "info"
    }
  ]
}

```

*Tasks response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|object|false|none|none|
|data|[any]|false|none|none|

<h2 id="tocSdispatcherorderresponse">DispatcherOrderResponse</h2>

<a id="schemadispatcherorderresponse"></a>

```json
{
  "data": {
    "tracking_number": "O-M1RHTJHJZGKX",
    "status": "created",
    "sender_type": "organisation",
    "sender_id": 1,
    "price_currency": "SGD",
    "price_amount": 0,
    "order_items": [
      {
        "status": "assigned",
        "service_type": "next_day",
        "item": {
          "width": 53,
          "weight": 4,
          "volumetric_weight": 595508,
          "volume": 200,
          "tracking_number": "Y-CTBVPQ",
          "payload_type": "package",
          "length": 53,
          "height": 53,
          "description": ""
        },
        "inserted_at": "2018-03-08T08:45:38.632070"
      }
    ],
    "number": "Z1QxNVRKUWwvKzUzc00wUkJEeXZUUT09",
    "inserted_at": "2018-12-11 08:56:23.829530Z",
    "access_token": "4h/PrR5vu9uVevso3fNv2RPTLQJech3BJ/pNJhWBnfE="
  }
}

```

*Order Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatchercreateworkerrequest">DispatcherCreateWorkerRequest</h2>

<a id="schemadispatchercreateworkerrequest"></a>

```json
{
  "vehicle_type_ids": [
    1,
    2
  ],
  "tester": false,
  "phone": "+987654322",
  "password": "passwd112233",
  "otp_token": "1122334455",
  "national_id": "11335577",
  "name": "Mike Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "email": "mike-driver@yojee.com",
  "driver_license": "22446688",
  "current_vehicle_type_id": 1
}

```

*Worker Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|vehicle_type_ids|[any]|true|none|Worker's vehicle type ids|
|phone|string|true|none|Phone number|
|password|string|true|none|Password|
|name|string|true|none|Full name|
|email|string|true|none|Email|
|current_vehicle_type_id|integer|true|none|Default vehicle type id|

<h2 id="tocSbatchcontinueresponse">BatchContinueResponse</h2>

<a id="schemabatchcontinueresponse"></a>

```json
{
  "message": "Batch upload processing.",
  "data": {
    "id": 1
  }
}

```

*Batch Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSversionresponse">VersionResponse</h2>

<a id="schemaversionresponse"></a>

```json
{
  "data": {
    "message": "App version Response",
    "data": {
      "update_required": true,
      "minimum_installed_version": 500,
      "current_installed_version": 499
    }
  }
}

```

*Check if app update is required*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSdispatcherupdateorganisationrequest">DispatcherUpdateOrganisationRequest</h2>

<a id="schemadispatcherupdateorganisationrequest"></a>

```json
{
  "user_profiles": [
    {
      "user_profile_id": 1,
      "phone": "Sender Phone",
      "name": "Sender Name",
      "email": "sender-email@example.com"
    },
    {
      "user_profile_id": 2,
      "phone": "+6533445566",
      "name": "Corporate User 2",
      "email": "corporate-user-2@example.com"
    }
  ],
  "sender": {
    "user_profile_id": 1,
    "phone": "Sender Phone",
    "name": "Sender Name",
    "email": "sender-email@example.com",
    "billing_address": "Sender billing address"
  },
  "reg_address": "77 Robinson road, Singapore.",
  "postal_code": "321021",
  "phone": "+6591240934",
  "name": "FEDEX",
  "id": 3,
  "country": "Singapore",
  "city": "Singapore"
}

```

*Organisation Details*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user_profiles|[any]|false|none|none|
|sender|object|false|none|none|
|reg_address|string|false|none|none|
|postal_code|string|false|none|none|
|phone|string|false|none|none|
|name|string|false|none|none|
|id|integer|false|none|none|
|extension|object|false|none|none|
|country|string|false|none|none|
|city|string|false|none|none|

<h2 id="tocScompaniesthemeresponse">CompaniesThemeResponse</h2>

<a id="schemacompaniesthemeresponse"></a>

```json
{
  "message": "Got list of companies theme",
  "data": [
    {
      "logo": "https://yojee-uploads-dev.s3.amazonaws.com/uploads/companies/467/logo/467_original_scharff.png?v=63689286187",
      "company_slug": "scharff",
      "brand_color": "#FF7177"
    },
    {
      "logo": "https://s3-ap-southeast-1.amazonaws.com/yojee-public/order_logo.jpg",
      "company_slug": "testcorp-r1",
      "brand_color": "#80c939"
    },
    {
      "logo": "https://s3-ap-southeast-1.amazonaws.com/yojee-public/order_logo.jpg",
      "company_slug": "ups",
      "brand_color": "#301506"
    },
    {
      "logo": "https://s3-ap-southeast-1.amazonaws.com/yojee-public/order_logo.jpg",
      "company_slug": "yojee",
      "brand_color": "#80c939"
    },
    {
      "logo": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/companies/4/logo/4_original_TASMAN%20LOGO_330x60px.png?v=63692636534",
      "company_slug": "tasman",
      "brand_color": "#054875"
    },
    {
      "logo": "https://s3-ap-southeast-1.amazonaws.com/yojee-public/sila_logo.png",
      "company_slug": "sila",
      "brand_color": "#d2232a"
    }
  ]
}

```

*Driver's companies Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|[any]|false|none|none|

<h2 id="tocStaskgroupsresponse">TaskGroupsResponse</h2>

<a id="schemataskgroupsresponse"></a>

```json
{
  "data": [
    {
      "type": "pickup",
      "to": "2018-03-27T10:00:00.000000Z",
      "task_group_id": 4213,
      "state": "created",
      "start_time": "2018-03-27T10:00:00.000000Z",
      "service_type": "next_day",
      "price": "SGD 10",
      "postal_code": "84184",
      "order_item_tracking_number": "YOJ-229",
      "order_item_id": 229,
      "lng": 103.90331700000002,
      "lat": 1.329095,
      "item": {
        "width": 29,
        "weight": 5,
        "volumetric_weight": 121945,
        "volume": 200,
        "length": 29,
        "height": 29,
        "global_tracking_number": "Y-MEJZPQ"
      },
      "id": 1,
      "from": "2018-03-27T02 =>00 =>00.000000Z",
      "external_id": "ID-1",
      "external_customer_id3": "1345564",
      "external_customer_id2": "545415",
      "external_customer_id": "54418",
      "description": "TEST",
      "country": "Singapore",
      "container_no": "13",
      "contact": {
        "phone": "+6591234567",
        "name": "kris sender"
      },
      "completion_time": "2018-03-26T09 =>49 =>42.679519Z",
      "address_state": "State",
      "address2": "TESTAS",
      "address": "Singapore 400314",
      "additional_info": "Info"
    }
  ]
}

```

*TaskGroup Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|List of task group|

<h2 id="tocSorderitemslogsresponse">OrderItemsLogsResponse</h2>

<a id="schemaorderitemslogsresponse"></a>

```json
{
  "task_log": [
    {
      "inserted_at": "2018-08-25T04:29:05.931535Z",
      "event": "task_completed",
      "description": "Pickup completed by Hau Vo Worker 2 (+84979202707) at Thai An 3 Apartments, Đường Nguyễn Văn Quá, Đông Hưng Thuận, District 12, Ho Chi Minh City, Vietnam, at N.A."
    },
    {
      "inserted_at": "2018-08-25T04:30:55.413681Z",
      "event": "task_completed",
      "description": "Dropoff completed by Hau Vo Worker 2 (+84979202707) at Nhà Hát Thành Phố, Bến Nghé, District 1, Ho Chi Minh City, Vietnam, at N.A."
    }
  ],
  "task_group_log": [
    {
      "inserted_at": "2018-08-25T04:25:16.467462Z",
      "event": "assign_worker",
      "description": "Item assigned to Hau Vo Worker 2 (+84979202707) by Yojee Development for SGD10.00"
    },
    {
      "inserted_at": "2018-08-25T04:25:21.716739Z",
      "event": "worker_accepted_task_group",
      "description": "Item accepted by Hau Vo Worker 2 (+84979202707)"
    },
    {
      "inserted_at": "2018-08-25T04:30:55.453536Z",
      "event": "worker_completed_task_group",
      "description": "Item completed by Hau Vo Worker 2 (+84979202707)"
    }
  ],
  "order_log": [
    {
      "inserted_at": "2018-08-25T04:24:44.583929Z",
      "event": "order_created",
      "description": "Order created"
    },
    {
      "inserted_at": "2018-08-25T04:30:55.433057Z",
      "event": "order_completed",
      "description": "Order completed"
    }
  ],
  "order_item_log": [
    {
      "inserted_at": "2018-08-25T04:25:21.695050Z",
      "event": "worker_accepted_item",
      "description": "Dropoff at Nhà hát thành phố, bến nghé, district 1, ho chi minh city, vietnam accepted by Hau Vo Worker 2 (+84979202707)"
    },
    {
      "inserted_at": "2018-08-25T04:25:21.705880Z",
      "event": "worker_accepted_item",
      "description": "Pickup at Thai an 3 apartments, đường nguyễn văn quá, đông hưng thuận, district 12, ho chi minh city, vietnam accepted by Hau Vo Worker 2 (+84979202707)"
    },
    {
      "inserted_at": "2018-08-25T04:29:05.942288Z",
      "event": "pickup_completed",
      "description": "Pickup task completed by Hau Vo Worker 2 (+84979202707) at Thai An 3 Apartments, Đường Nguyễn Văn Quá, Đông Hưng Thuận, District 12, Ho Chi Minh City, Vietnam, at N.A."
    },
    {
      "inserted_at": "2018-08-25T04:30:55.436040Z",
      "event": "dropoff_completed",
      "description": "Dropoff task completed by Hau Vo Worker 2 (+84979202707) at Nhà Hát Thành Phố, Bến Nghé, District 1, Ho Chi Minh City, Vietnam, at N.A."
    }
  ]
}

```

*OrderItem logs Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|task_log|[any]|false|none|none|
|task_group_log|[any]|false|none|none|
|order_item_log|[any]|false|none|none|
|item_log|[any]|false|none|none|

<h2 id="tocSbulktaskcompletionrequestbydispatcher">BulkTaskCompletionRequestByDispatcher</h2>

<a id="schemabulktaskcompletionrequestbydispatcher"></a>

```json
{
  "task_ids": [
    1,
    2,
    3
  ]
}

```

*Task Completion Bulk Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|task_ids|[any]|false|none|none|

<h2 id="tocSdispatchersettingresponse">DispatcherSettingResponse</h2>

<a id="schemadispatchersettingresponse"></a>

```json
{
  "data": {
    "settings": {
      "sample settings": "sample value"
    },
    "name": "default",
    "id": 1,
    "company_id": 1
  }
}

```

*Setting Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatchercreateorganisationresponse">DispatcherCreateOrganisationResponse</h2>

<a id="schemadispatchercreateorganisationresponse"></a>

```json
{
  "data": {
    "phone": "+6598765432",
    "email": "bob@mail.com",
    "access_token": "pCVPeEEUuKnM7geUOcSLY2imA5l6YUdjymkApBDAAGY="
  }
}

```

*Organisation Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatchercreaterolerequest">DispatcherCreateRoleRequest</h2>

<a id="schemadispatchercreaterolerequest"></a>

```json
{
  "name": "role_1",
  "company_id": 123,
  "access_map": {
    "sender": {
      "add": true
    }
  }
}

```

*POST body for creating new role*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Role name|
|company_id|integer|false|none|Company ID|
|access_map|object|false|none|Access Map|

<h2 id="tocSgetpricesresponse">GetPricesResponse</h2>

<a id="schemagetpricesresponse"></a>

```json
{
  "data": [
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
    },
    {
      "type": "same_day",
      "success": true,
      "msg": {
        "surcharges": {
          "CBD": 2
        },
        "price": 12,
        "pickup_zip": "068896",
        "dropoff_zip": "189703",
        "base_price": 10
      }
    },
    {
      "type": "next_day",
      "success": true,
      "msg": {
        "surcharges": {
          "CBD": 2
        },
        "price": 9,
        "pickup_zip": "068896",
        "dropoff_zip": "189703",
        "base_price": 7
      }
    }
  ]
}

```

*Get price response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSspokerequest">SpokeRequest</h2>

<a id="schemaspokerequest"></a>

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "destination_hub_id": 2
}

```

*Spoke Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|properties|object|false|none|none|
|pessimistic_estimated_duration|integer|false|none|none|
|origin_hub_id|integer|false|none|none|
|optimistic_estimated_duration|integer|false|none|none|
|name|string|false|none|none|
|modality|string|false|none|none|
|destination_hub_id|integer|false|none|none|

<h2 id="tocScompanyvehicletypesresponse">CompanyVehicleTypesResponse</h2>

<a id="schemacompanyvehicletypesresponse"></a>

```json
{
  "message": "Got vehicle types",
  "data": [
    {
      "name": "Pedestrian",
      "id": 1
    },
    {
      "name": "Bicycle",
      "id": 2
    }
  ]
}

```

*Vehicle types info Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|[any]|false|none|none|

<h2 id="tocSgetpricesrequest">GetPricesRequest</h2>

<a id="schemagetpricesrequest"></a>

```json
{
  "to_address": {
    "zipcode": "189703",
    "location": "1.2976764,103.85701760000006",
    "lng": "103.85701760000006",
    "lat": "1.2976764",
    "country": "Singpore"
  },
  "slug": "yojee",
  "item": {
    "weight": 4
  },
  "from_address": {
    "zipcode": "068896",
    "location": "1.2777689,103.84839149999993",
    "lng": "103.84839149999993",
    "lat": "1.2777689",
    "country": "Singpore"
  }
}

```

*Get the price estimate*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|to_address|[OrderAddress](#schemaorderaddress)|false|none|none|
|slug|string|false|none|yojee|
|item|[OrderItem](#schemaorderitem)|false|none|none|
|from_address|[OrderAddress](#schemaorderaddress)|false|none|none|

<h2 id="tocSdispatchersendersresponse">DispatcherSendersResponse</h2>

<a id="schemadispatchersendersresponse"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 2,
    "current_page": 1
  },
  "data": [
    {
      "sender_user_profile_id": 1,
      "sender_type": "individual",
      "phone": "+8412345611",
      "password": "passwd112233",
      "name": "Mike Sender",
      "inserted_at": "2018-12-11 08:56:23.836813Z",
      "id": 5,
      "email": "michael@yojee.com",
      "billing_address": "144 Robinson Road"
    }
  ]
}

```

*Senders Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatcherupdatecorporatesenderrequest">DispatcherUpdateCorporateSenderRequest</h2>

<a id="schemadispatcherupdatecorporatesenderrequest"></a>

```json
{
  "title": "Engineer",
  "sender_type": "organisation",
  "phone": "+6598765432",
  "name": "Ralston",
  "email": "secondary_account@abc.com",
  "billing_address": "77 Robinson road, Singapore."
}

```

*Corporate Sender Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|sender_type|string|false|none|none|
|phone|string|false|none|none|
|name|string|false|none|none|
|email|string|false|none|none|
|billing_address|string|false|none|none|

<h2 id="tocStaskshistoryresponse">TasksHistoryResponse</h2>

<a id="schemataskshistoryresponse"></a>

```json
{
  "pagination": {
    "total_pages": 1,
    "total_count": 1,
    "limit_value": 10,
    "current_page": 1
  },
  "data": [
    {
      "type": "pickup",
      "to": "2018-08-10T21:25:29.621707Z",
      "task_group_id": 55612,
      "state": "completed",
      "service_type": "sameday",
      "order_item_tracking_number": "YOJ-NK5HEMFNPT0",
      "order_item_id": 46134,
      "lng": 103.7647132,
      "lat": 1.4630478,
      "item": {
        "width": 1,
        "weight": 1,
        "volumetric_weight": 10,
        "volume": 200,
        "length": 1,
        "height": 1,
        "global_tracking_number": "Y-QVK4PQ"
      },
      "id": 85945,
      "from": "2018-08-10T13:25:29.621707Z",
      "external_id": "External test #1",
      "external_customer_id3": "external_customer_id3_test",
      "external_customer_id2": "external_customer_id2_test",
      "external_customer_id": "external_customer_id_test",
      "description": "Gift",
      "container_no": "Container test #1",
      "contact": {
        "phone": "+6581551123",
        "name": "vivek",
        "email": "sender@example.com"
      },
      "completion_time": "2018-08-10T05:25:30.328366Z",
      "address": "144 Robinson Road"
    }
  ]
}

```

*Tasks History response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocShubsresponse">HubsResponse</h2>

<a id="schemahubsresponse"></a>

```json
{
  "data": [
    {
      "regions": [
        "poly5"
      ],
      "properties": {
        "description": "Sample description",
        "address": "Singapore"
      },
      "name": "Sample Hub",
      "location": {
        "lng": 122.6428429677108,
        "lat": 65.67691234535297
      },
      "inserted_at": "2018-12-11 08:56:23.844248Z",
      "company_id": 1
    }
  ]
}

```

*Hubs Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSworkerlocationupdaterequest">WorkerLocationUpdateRequest</h2>

<a id="schemaworkerlocationupdaterequest"></a>

```json
{
  "lng": 122.6428429677108,
  "lat": 65.67691234535297
}

```

*Location Update Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|lng|object|false|none|none|
|lat|object|false|none|none|

<h2 id="tocSdispatcherorganisationresponse">DispatcherOrganisationResponse</h2>

<a id="schemadispatcherorganisationresponse"></a>

```json
{
  "user_profiles": [
    {
      "user_profile_id": 1,
      "phone": "Sender Phone",
      "name": "Sender Name",
      "email": "sender-email@example.com"
    },
    {
      "user_profile_id": 2,
      "phone": "+6533445566",
      "name": "Corporate User 2",
      "email": "corporate-user-2@example.com"
    }
  ],
  "sender": {
    "user_profile_id": 1,
    "phone": "Sender Phone",
    "name": "Sender Name",
    "email": "sender-email@example.com",
    "billing_address": "Sender billing address"
  },
  "reg_address": "77 Robinson road, Singapore.",
  "postal_code": "321021",
  "phone": "+6591240934",
  "name": "FEDEX",
  "id": 3,
  "country": "Singapore",
  "city": "Singapore"
}

```

*Organisation Details*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user_profiles|[any]|false|none|none|
|sender|object|false|none|none|
|reg_address|string|false|none|none|
|postal_code|string|false|none|none|
|phone|string|false|none|none|
|name|string|false|none|none|
|id|integer|false|none|none|
|extension|object|false|none|none|
|country|string|false|none|none|
|city|string|false|none|none|

<h2 id="tocSdispatchercreateplanrequest">DispatcherCreatePlanRequest</h2>

<a id="schemadispatchercreateplanrequest"></a>

```json
{
  "uuid": "123456789",
  "settings": {
    "sample settings": "sample value"
  },
  "output": {
    "sample output": "sample value"
  },
  "input": {
    "sample input": "sample value"
  }
}

```

*POST body for creating new plan*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|string|true|none|Plan uuid|
|settings|object|true|none|Plan settings|
|output|object|false|none|Plan output|
|input|object|true|none|Plan input|

<h2 id="tocSdispatchercreateworkerresponse">DispatcherCreateWorkerResponse</h2>

<a id="schemadispatchercreateworkerresponse"></a>

```json
{
  "data": {
    "vehicle_type_registers": [
      {
        "name": "Bike",
        "id": 1
      },
      {
        "name": "Car",
        "id": 2
      }
    ],
    "vehicle_type_ids": [
      1
    ],
    "user_profile_id": 1,
    "tester": false,
    "phone": "+987654322",
    "password": "passwd112233",
    "otp_token": "1122334455",
    "national_id_photo_front": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/accounts/128817/national_id/128817_original_updated-national-id-front.png",
    "national_id_photo_back": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/accounts/128817/national_id/128817_original_updated-national-id-back.png",
    "national_id": "11335577",
    "name": "Mike Driver",
    "location": {
      "lng": 122.6428429677108,
      "lat": 65.67691234535297
    },
    "inserted_at": "2018-12-11 08:56:23.835006Z",
    "email": "mike-driver@yojee.com",
    "driver_license_photo_front": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/accounts/128817/driver_license/128817_original_updated-driver-license-front.png?v=63701553117",
    "driver_license_photo_back": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/accounts/128817/driver_license/128817_original_updated-driver-license-back.png?v=63701553117",
    "driver_license": "22446688",
    "distance_away": 1100,
    "current_vehicle_type_id": 1,
    "company_id": 1,
    "access_token": "4h/PrR5vu9uVevso3fNv2RPTLQJech3BJ/pNJhWBnfE="
  }
}

```

*Worker Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatcherindexuserresponse">DispatcherIndexUserResponse</h2>

<a id="schemadispatcherindexuserresponse"></a>

```json
{
  "data": [
    {
      "user_profile": 1,
      "phone": "+987654330",
      "name": "Mike Dispatcher",
      "inserted_at": "2018-12-11 08:56:23.833973Z",
      "email": "mike-dispatcher-3@yojee.com",
      "company_id": 1
    }
  ]
}

```

*Users Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSdispatchercreateuserresponse">DispatcherCreateUserResponse</h2>

<a id="schemadispatchercreateuserresponse"></a>

```json
{
  "data": {
    "user_profile": 1,
    "phone": "+987654330",
    "name": "Mike Dispatcher",
    "inserted_at": "2018-12-11 08:56:23.834124Z",
    "email": "mike-dispatcher-3@yojee.com",
    "company_id": 1
  }
}

```

*User Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatchercreatecorporatesenderresponse">DispatcherCreateCorporateSenderResponse</h2>

<a id="schemadispatchercreatecorporatesenderresponse"></a>

```json
{
  "data": {
    "phone": "+6598765432",
    "email": "bob@mail.com",
    "access_token": "pCVPeEEUuKnM7geUOcSLY2imA5l6YUdjymkApBDAAGY="
  }
}

```

*Corporate Sender Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSallocationrequest">AllocationRequest</h2>

<a id="schemaallocationrequest"></a>

```json
{
  "_json": [
    {
      "worker_id": 2,
      "tasks": [
        {
          "id": "startFromDepot",
          "eta": "2018-08-20T16:00:00.000Z"
        },
        {
          "polyline": [
            [
              103.96689,
              1.330653
            ],
            [
              103.96689,
              1.330653
            ]
          ],
          "id": "46",
          "eta": "2018-08-20T23:45:00.000Z"
        }
      ],
      "polyline": [
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ]
      ],
      "commission": "23.00"
    },
    {
      "worker_id": 232,
      "tasks": [
        {
          "id": "startFromDepot",
          "eta": "2018-08-20T16:00:00.000Z"
        },
        {
          "polyline": [
            [
              103.96689,
              1.330653
            ],
            [
              103.96689,
              1.330653
            ]
          ],
          "id": "1223",
          "eta": "2018-08-20T23:45:00.000Z"
        }
      ],
      "polyline": [
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ],
        [
          103.96689,
          1.330653
        ]
      ],
      "commission": "43.00"
    }
  ]
}

```

*Allocation Request*

### Properties

*None*

<h2 id="tocSdispatcherindexsettingresponse">DispatcherIndexSettingResponse</h2>

<a id="schemadispatcherindexsettingresponse"></a>

```json
{
  "data": [
    {
      "type": "object",
      "title": "Setting Response",
      "properties": {
        "data": {
          "type": "object"
        }
      },
      "example": {
        "data": {
          "settings": {
            "sample settings": "sample value"
          },
          "name": "default",
          "id": 1,
          "company_id": 1
        }
      }
    }
  ]
}

```

*Settings Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSdispatcherorganisationsresponse">DispatcherOrganisationsResponse</h2>

<a id="schemadispatcherorganisationsresponse"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 2,
    "current_page": 1
  },
  "data": [
    {
      "sender_id": 1,
      "reg_address": "77 Robinson road, Singapore.",
      "postal_code": "321021",
      "phone": "+6591245934",
      "name": "ABC",
      "id": 1,
      "country": "Singapore",
      "city": "Singapore"
    }
  ]
}

```

*Organisations Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocStaskexceptionreasonresponse">TaskExceptionReasonResponse</h2>

<a id="schemataskexceptionreasonresponse"></a>

```json
{
  "message": "ok",
  "data": {
    "description": "Sender not available",
    "company_id": 1
  }
}

```

*Task Exception Reason Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSdispatchercreateorganisationrequest">DispatcherCreateOrganisationRequest</h2>

<a id="schemadispatchercreateorganisationrequest"></a>

```json
{
  "title": "Engineer",
  "sender_type": "organisation",
  "phone": "+6598765432",
  "payment_option": "monthly_billing",
  "organisation": {
    "reg_address": "77 Robinson road, Singapore.",
    "postal_code": "321021",
    "phone": "+6591245934",
    "name": "ABC",
    "country": "Singapore",
    "city": "Singapore"
  },
  "name": "Ralston",
  "gst_no": "2AS9890",
  "email": "primary_account@abc.com",
  "business_reg_no": "ABC1235M",
  "billing_address": "77 Robinson road, Singapore."
}

```

*Organisation Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|sender_type|string|false|none|none|
|phone|string|false|none|none|
|payment_option|string|false|none|none|
|organisation|object|false|none|none|
|name|string|false|none|none|
|gst_no|string|false|none|none|
|email|string|false|none|none|
|business_reg_no|string|false|none|none|
|billing_address|string|false|none|none|

<h2 id="tocSworkerchatmessageresponse">WorkerChatMessageResponse</h2>

<a id="schemaworkerchatmessageresponse"></a>

```json
{
  "user_profile": {
    "user_profile_id": 299,
    "name": "Demond Terry"
  },
  "inserted_at": "2018-10-23T07:57:27.538169Z",
  "incoming": false,
  "id": 133,
  "created_at": "2018-10-23T07:56:00.0Z",
  "content": {
    "type": "image",
    "text": "it has value if it is not attachment and it's type is 'text'",
    "attachment": {
      "thumbnail": "https://s3-ap-southeast-1.amazonaws.com/thumbnail_signature.png",
      "original": "https://s3-ap-southeast-1.amazonaws.com/original_signature.png"
    }
  }
}

```

*Chat Message Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user_profile|object|false|none|none|
|inserted_at|string|false|none|none|
|incoming|object|false|none|none|
|id|integer|false|none|none|
|created_at|string|false|none|none|
|content|object|false|none|none|

<h2 id="tocSorderitemsindexresponse">OrderItemsIndexResponse</h2>

<a id="schemaorderitemsindexresponse"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 2,
    "current_page": 1
  },
  "data": [
    {
      "weight": 20,
      "volume": 300,
      "tracking_number": "yoyoyoyo",
      "to_address": "Airport Blvd, Changi Airport Singapore (SIN), Singapore",
      "status": "assigned",
      "service_type_id": 1,
      "service_type": "same_day",
      "sender_phone": "+6590050680",
      "sender_name": "champ",
      "receipient_phone": "+6598765432",
      "receipient_name": "test2",
      "order_number": "order_number",
      "order_id": 1,
      "item_number": 2,
      "id": 7,
      "from_address": "144 Robinson Road, Level 15, Singapore 068908",
      "description": "Gifts",
      "created_at": "2018-03-08T14:58:24.280533"
    }
  ]
}

```

*OrderItem index Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSassignedtaskgroupsindexresponse">AssignedTaskGroupsIndexResponse</h2>

<a id="schemaassignedtaskgroupsindexresponse"></a>

```json
{
  "pagination": {
    "total_pages": 1,
    "total_count": 2,
    "limit_value": 25,
    "current_page": 1
  },
  "data": [
    {
      "worker": {
        "status": "on_duty",
        "name": "Ms. Jamarcus Jones",
        "id": 33955,
        "contract": "employee"
      },
      "task_group_logs": [
        {
          "inserted_at": "2018-07-18T09:58:59.585437Z",
          "id": 26523,
          "event": "assign_worker",
          "description": "Task Group assigned to Ms. Jamarcus Jones (+447450913761) by Eldon Cormier"
        }
      ],
      "state": "assigned",
      "items": [
        {
          "width": 1,
          "tracking_number": "YOJ-NLNPME93PT0",
          "tasks": [
            {
              "type": "pickup",
              "to": "2018-07-18T17:58:58.565876Z",
              "task_logs": [],
              "task_group_id": 43771,
              "state": "created",
              "order_step_id": 65256,
              "order_item_step_sequence": 1,
              "order_item_id": 36311,
              "lng": 103.7647132,
              "lat": 1.4630478,
              "id": 67695,
              "from": "2018-07-18T09:58:58.565876Z",
              "description": "Gift",
              "contact": {
                "phone": "+6581551123",
                "name": "vivek",
                "email": "sender@example.com"
              },
              "address_details": {
                "state": "Singapore",
                "postal_code": "112233",
                "country": "Singapore",
                "address2": "160 Robinson Road",
                "address": "144 Robinson Road"
              },
              "address": "144 Robinson Road, 160 Robinson Road, Singapore, 112233, Singapore"
            },
            {
              "type": "dropoff",
              "to": "2018-07-19T01:58:58.565876Z",
              "task_logs": [],
              "task_group_id": 43771,
              "state": "created",
              "order_step_id": 65257,
              "order_item_step_sequence": 2,
              "order_item_id": 36311,
              "lng": 103.7647132,
              "lat": 1.4630478,
              "id": 67696,
              "from": "2018-07-18T17:58:58.565876Z",
              "description": "Gift",
              "contact": {
                "phone": "+6581551123",
                "name": "vivek",
                "email": "recipient@example.com"
              },
              "address_details": {
                "state": "Singapore",
                "postal_code": "332211",
                "country": "Singapore",
                "address2": "50 Boon Keng Rd",
                "address": "Boon Keng Rd"
              },
              "address": "Boon Keng Rd, 50 Boon Keng Rd, Singapore, 332211, Singapore"
            }
          ],
          "progress_session": [
            {
              "type": "assigned",
              "status": "blank"
            },
            {
              "type": "pickup",
              "status": "blank"
            },
            {
              "type": "dropoff",
              "status": "blank"
            }
          ],
          "order_item_id": 36311,
          "length": 1,
          "height": 1,
          "description": "Gift"
        }
      ],
      "id": 43771
    }
  ]
}

```

*Assigned TaskGroup index Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSinforesponse">InfoResponse</h2>

<a id="schemainforesponse"></a>

```json
{
  "message": "Got driver's info.",
  "data": {
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
    "email": "john@gmail.com",
    "device_token": "AI73LASYS93SDKD",
    "current_vehicle_type_id": 2,
    "avatar": "https://s3-ap-southeast-1.amazonaws.com/avatar.jpg"
  }
}

```

*Driver's info Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSbulkcompletionstatus">BulkCompletionStatus</h2>

<a id="schemabulkcompletionstatus"></a>

```json
{
  "data": {
    "total": 100,
    "status": "completed",
    "processed": 100,
    "logs": []
  }
}

```

*Bulk Completion Status*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|tracking_numbers|[any]|false|none|none|
|location|object|false|none|none|
|completion_time|string|false|none|none|

<h2 id="tocSdispatchersubtasksresponse">DispatcherSubTasksResponse</h2>

<a id="schemadispatchersubtasksresponse"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 1,
    "current_page": 1
  },
  "data": [
    {
      "task_id": 103,
      "sub_task_rule_id": 21,
      "photo": "https://s3-ap-southeast-1.amazonaws.com/signature.jpg",
      "meta": {
        "photo_type": "Proof",
        "photo_title": "Signature"
      },
      "id": 21,
      "event": "pickup_completed",
      "completion_time": "2018-03-10T03:37:08",
      "company_id": 136,
      "action": "upload_photo"
    }
  ]
}

```

*Sub Tasks Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSsubtaskresponse">SubTaskResponse</h2>

<a id="schemasubtaskresponse"></a>

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
  "completion_data": {
    "recipient_name": "recipient",
    "arrival_time": "2018-03-10T03:37:08"
  },
  "action": "upload_photo"
}

```

*SubTask Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|task_id|integer|false|none|none|
|sub_task_rule_id|integer|false|none|none|
|photo|string|false|none|none|
|meta|object|false|none|none|
|event|string|false|none|none|
|completion_data|object|false|none|none|
|action|string|false|none|none|

<h2 id="tocSjwtissueresponse">JwtIssueResponse</h2>

<a id="schemajwtissueresponse"></a>

```json
{
  "jwt": "dfksdfKJSGD*&*&(*DHKJGDHKJ"
}

```

*response from a JWT issue request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jwt|string|true|none|JWT token|

<h2 id="tocSspokesresponse">SpokesResponse</h2>

<a id="schemaspokesresponse"></a>

```json
{
  "data": [
    {
      "properties": {},
      "pessimistic_estimated_duration": 40,
      "origin_hub_id": 1,
      "optimistic_estimated_duration": 40,
      "name": "spoker",
      "modality": "road",
      "inserted_at": "2018-12-11 08:56:23.844815Z",
      "destination_hub_id": 2,
      "company_id": 1
    }
  ]
}

```

*Spokes Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocScompanyinforesponse">CompanyInfoResponse</h2>

<a id="schemacompanyinforesponse"></a>

```json
{
  "data": {
    "slug": "yojee",
    "settings": {
      "delivery_options": {
        "time_window": {
          "pickup": {
            "to": 18,
            "from": 10
          },
          "dropoff": {
            "to": 22,
            "from": 14
          }
        },
        "pickup_allowance": 2,
        "max_weight": 50,
        "advance_bookings": 14
      }
    },
    "organisation_id": 1,
    "name": "Yojee",
    "id": 1,
    "extension_schema": {
      "orders": {
        "required": [],
        "properties": {
          "load_type": {
            "type": "string",
            "title": "Load Type"
          }
        }
      }
    },
    "events": [
      "pickup_completed",
      "dropoff_completed"
    ],
    "display_settings": {
      "sender_access": {
        "invoice.show": true
      },
      "admin_copy": {
        "orders.show.external_id_title": "External Order ID",
        "orders.show.ccu_name_title": "Client company user name",
        "items.show.order_id_title": "Order ID",
        "default.unit": "cm"
      },
      "admin_access": {
        "workers.delete": false,
        "tracking.show_waybill": true,
        "order_items.index": true,
        "orders.update.price": false,
        "batches": false,
        "task_groups.broadcast": true,
        "items.show.service_type": true,
        "reports": true,
        "senders.show": true,
        "orders.update.external_id": false,
        "orders.create": true,
        "workers.update": true,
        "senders.index": true,
        "orders.show.price": true,
        "organisation_senders.create": true,
        "step_items.show.volume": false,
        "partners.create": true,
        "partners.update": true,
        "organisations.update": true,
        "orders.show.container_no": false,
        "orders.show.load_quantity": false,
        "task_groups.unassigned": true,
        "batches.create": false,
        "workers.index": true,
        "task_groups.assigned": true,
        "organisations.index": true,
        "invoices.show": true,
        "senders.create": true,
        "network": false,
        "orders": true,
        "workers.create": true,
        "partners.transfer": false,
        "items.update.external_customer_id": false,
        "partners.index": true,
        "orders.update": true,
        "items.show.external_customer_id2": false,
        "items.show.info": false,
        "orders.show.external_id": true,
        "dashboard": false,
        "task_groups": true,
        "partners.show": true,
        "senders.delete": false,
        "senders.update": true,
        "senders": true,
        "tracking.show_price": false,
        "orders.index": true,
        "order_items": true,
        "user_guide": false,
        "organisation_senders.index": true,
        "items.show.external_customer_id": false,
        "settings": true,
        "tracking.show_invoice": false,
        "manifests.show": false,
        "dispatchers.senders": true,
        "items.show.external_customer_id3": false,
        "settings.show.driver_management": false,
        "settings.show.create_new_user": false,
        "workers": true,
        "workers.show": true,
        "partners.delete": false,
        "items.update": false,
        "partners": true
      }
    },
    "actions": [
      "upload_photo",
      "upload_signature"
    ]
  }
}

```

*Company Settings Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatcherpartnershipinfoupdate">DispatcherPartnershipInfoUpdate</h2>

<a id="schemadispatcherpartnershipinfoupdate"></a>

```json
{
  "contact_phone": "+6591245934",
  "contact_name": "Ralston",
  "contact_email": "ralston@xyz.com"
}

```

*Partnership Info Update Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|contact_phone|string|false|none|none|
|contact_name|string|false|none|none|
|contact_email|string|false|none|none|

<h2 id="tocSdispatcherindexplanresponse">DispatcherIndexPlanResponse</h2>

<a id="schemadispatcherindexplanresponse"></a>

```json
{
  "data": [
    {
      "type": "object",
      "title": "Plan Response",
      "properties": {
        "data": {
          "type": "object"
        }
      },
      "example": {
        "data": {
          "uuid": "123456789",
          "settings": {
            "sample settings": "sample value"
          },
          "output": {
            "sample output": "sample value"
          },
          "input": {
            "sample input": "sample value"
          },
          "id": 1,
          "company_id": 1
        }
      }
    }
  ]
}

```

*Plans Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSdispatchercreatesenderresponse">DispatcherCreateSenderResponse</h2>

<a id="schemadispatchercreatesenderresponse"></a>

```json
{
  "data": {
    "sender_user_profile_id": 1,
    "sender_type": "individual",
    "phone": "+8412345611",
    "password": "passwd112233",
    "name": "Mike Sender",
    "inserted_at": "2018-12-11 08:56:23.836483Z",
    "id": 5,
    "email": "michael@yojee.com",
    "billing_address": "144 Robinson Road"
  }
}

```

*Sender Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatcherupdatesenderrequest">DispatcherUpdateSenderRequest</h2>

<a id="schemadispatcherupdatesenderrequest"></a>

```json
{
  "phone": "+8412345611",
  "name": "Mike Sender",
  "email": "michael@yojee.com",
  "billing_address": "144 Robinson Road"
}

```

*Sender Update Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|phone|string|false|none|none|
|name|string|false|none|none|
|email|string|false|none|none|
|billing_address|string|false|none|none|

<h2 id="tocSmapsgeocoderequest">MapsGeoCodeRequest</h2>

<a id="schemamapsgeocoderequest"></a>

```json
{
  "query": "1 Anson Rd",
  "country_code": "SG"
}

```

*POST body for querying geocode of an address*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|string|true|none|Address|
|country_code|string|false|none|Country code ISO 3166 alpha2|

<h2 id="tocSdispatchercreateuserrequest">DispatcherCreateUserRequest</h2>

<a id="schemadispatchercreateuserrequest"></a>

```json
{
  "phone": "+987654330",
  "password": "passwd112233",
  "name": "Mike Dispatcher",
  "email": "mike-dispatcher-3@yojee.com"
}

```

*POST body for creating new dispatcher user*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|phone|string|true|none|Phone number|
|password|string|true|none|Password|
|name|string|true|none|Full name|
|email|string|true|none|Email|

<h2 id="tocStaskexceptionreasonsresponse">TaskExceptionReasonsResponse</h2>

<a id="schemataskexceptionreasonsresponse"></a>

```json
{
  "message": "Got company task exception reasons",
  "data": [
    {
      "description": "Sender not available",
      "company_id": 1
    }
  ]
}

```

*Task Exception Reasons Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|[any]|false|none|none|

<h2 id="tocSbulktaskcompletionrequest">BulkTaskCompletionRequest</h2>

<a id="schemabulktaskcompletionrequest"></a>

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

*Task Completion Bulk Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|tracking_numbers|[any]|false|none|none|
|location|object|false|none|none|
|completion_time|string|false|none|none|

<h2 id="tocShubresponse">HubResponse</h2>

<a id="schemahubresponse"></a>

```json
{
  "data": {
    "regions": [
      "poly5"
    ],
    "properties": {
      "description": "Sample description",
      "address": "Singapore"
    },
    "name": "Sample Hub",
    "location": {
      "lng": 122.6428429677108,
      "lat": 65.67691234535297
    },
    "inserted_at": "2018-12-11 08:56:23.844145Z",
    "company_id": 1
  }
}

```

*Hub Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatcherpartners">DispatcherPartners</h2>

<a id="schemadispatcherpartners"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 2,
    "current_page": 1
  },
  "data": [
    {
      "state": "pending",
      "requested_at": "2018-05-22T14:33:57.131041Z",
      "postal_code": "321021",
      "partnership_type": "downstream",
      "country": "Singapore",
      "contact_phone": "+6591245934",
      "contact_name": "Ralston",
      "contact_email": "ralston@xyz.com",
      "company_name": "XYZ",
      "city": "Singapore",
      "cip": "CIP-XJSI232KGTDYTDT",
      "address": "77 Robinson road, Singapore."
    }
  ]
}

```

*Partners Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSdispatcherchatmessagesresponse">DispatcherChatMessagesResponse</h2>

<a id="schemadispatcherchatmessagesresponse"></a>

```json
{
  "data": {
    "messages": [
      {
        "user_profile": {
          "user_profile_id": 299,
          "name": "Demond Terry"
        },
        "inserted_at": "2018-10-23T07:57:27.538169Z",
        "incoming": false,
        "id": 133,
        "created_at": "2018-10-23T07:56:00.0Z",
        "content": {
          "type": "image",
          "text": "it has value if it is not attachment and it's type is 'text'",
          "attachment": {
            "thumbnail": "https://s3-ap-southeast-1.amazonaws.com/thumbnail_signature.png",
            "original": "https://s3-ap-southeast-1.amazonaws.com/original_signature.png"
          }
        }
      }
    ],
    "channel": {
      "members": [],
      "id": 154
    }
  }
}

```

*Chat Messages Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatchercreatesenderrequest">DispatcherCreateSenderRequest</h2>

<a id="schemadispatchercreatesenderrequest"></a>

```json
{
  "sender_type": "individual",
  "phone": "+8412345611",
  "password": "passwd112233",
  "name": "Mike Sender",
  "email": "michael@yojee.com",
  "billing_address": "144 Robinson Road"
}

```

*Sender Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sender_type|string|false|none|none|
|phone|string|false|none|none|
|password|string|false|none|none|
|name|string|false|none|none|
|email|string|false|none|none|
|billing_address|string|false|none|none|

<h2 id="tocSdispatcherupdatesettingrequest">DispatcherUpdateSettingRequest</h2>

<a id="schemadispatcherupdatesettingrequest"></a>

```json
{
  "settings": {
    "sample settings": "sample value"
  },
  "name": "default"
}

```

*POST body for updating setting*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|settings|object|true|none|Setting settings|
|name|string|true|none|Setting name|

<h2 id="tocSbatchcancelledresponse">BatchCancelledResponse</h2>

<a id="schemabatchcancelledresponse"></a>

```json
{
  "message": "Batch cancelled.",
  "data": {
    "id": 1
  }
}

```

*Batch Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSbroadcastrequest">BroadcastRequest</h2>

<a id="schemabroadcastrequest"></a>

```json
{
  "timeout_in_minutes": 20,
  "task_group_ids": [
    1,
    2
  ],
  "price_currency": "SGD",
  "price_amount": 500
}

```

*Broadcast Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|timeout_in_minutes|integer|false|none|none|
|task_group_ids|[any]|false|none|none|
|price_currency|string|false|none|none|
|price_amount|integer|false|none|none|

<h2 id="tocSregionresponse">RegionResponse</h2>

<a id="schemaregionresponse"></a>

```json
{
  "data": {
    "tag": "poly5",
    "inserted_at": "2018-12-11 08:56:23.843706Z",
    "description": "Sample Region",
    "coordinates": [
      [
        {
          "lng": 10,
          "lat": 35
        },
        {
          "lng": 45,
          "lat": 45
        },
        {
          "lng": 40,
          "lat": 15
        },
        {
          "lng": 20,
          "lat": 10
        },
        {
          "lng": 10,
          "lat": 35
        }
      ],
      [
        {
          "lng": 30,
          "lat": 20
        },
        {
          "lng": 35,
          "lat": 35
        },
        {
          "lng": 20,
          "lat": 30
        },
        {
          "lng": 30,
          "lat": 20
        }
      ]
    ],
    "company_id": 1,
    "color": "red"
  }
}

```

*Region Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatcherupdatecorporatesenderresponse">DispatcherUpdateCorporateSenderResponse</h2>

<a id="schemadispatcherupdatecorporatesenderresponse"></a>

```json
{
  "data": {
    "user_profile_id": 123,
    "phone": "+6598765432",
    "name": "Bob",
    "email": "bob@mail.com"
  }
}

```

*Corporate Sender Updated Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocScreatepaymentrequest">CreatePaymentRequest</h2>

<a id="schemacreatepaymentrequest"></a>

```json
{
  "payment_method": "stripe",
  "order_id": 1,
  "description": "This is a test description",
  "currency": "SGD",
  "credit_card": {
    "year": 22,
    "number": 4242424242424242,
    "name": "Jane Doe",
    "month": 11,
    "cvc": 111
  },
  "amount": 500
}

```

*POST body for making payment*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payment_method|string|false|none|Payment method|
|order_id|integer|false|none|Order ID|
|description|string|false|none|Description|
|currency|string|false|none|Currency|
|credit_card|object|false|none|none|
|» year|integer|false|none|Year|
|» number|string|false|none|Credit card number|
|» name|string|false|none|Full name|
|» month|integer|false|none|Month|
|» cvc|integer|false|none|CVC Number|
|amount|number|false|none|Amount in cents|

<h2 id="tocSunassignedtaskgroupsindexresponse">UnassignedTaskGroupsIndexResponse</h2>

<a id="schemaunassignedtaskgroupsindexresponse"></a>

```json
{
  "pagination": {
    "total_pages": 1,
    "total_count": 2,
    "limit_value": 25,
    "current_page": 1
  },
  "data": [
    {
      "task_group_logs": [],
      "state": "unassigned",
      "order_steps": [
        {
          "type": "pickup",
          "to_time": "2018-07-18T17:57:06.698170Z",
          "sequence": 1,
          "lng": 103.7647132,
          "lat": 1.4630478,
          "item_count": 1,
          "id": 65254,
          "from_time": "2018-07-18T09:57:06.698170Z",
          "first_item": {
            "width": 1,
            "tracking_number": "YOJ-C3JHBZLRPT0",
            "order_item_id": 36310,
            "length": 1,
            "height": 1,
            "external_id": "External test #1",
            "external_customer_id3": "external_customer_id3_test",
            "external_customer_id2": "external_customer_id2_test",
            "external_customer_id": "external_customer_id_test",
            "description": "Gift",
            "container_no": "Container test #1"
          },
          "contact": {
            "phone": "+6581551123",
            "name": "vivek",
            "email": "sender@example.com"
          },
          "address_details": {
            "state": "Singapore",
            "postal_code": "112233",
            "country": "Singapore",
            "address2": "160 Robinson Road",
            "address": "144 Robinson Road"
          },
          "address": "144 Robinson Road, 160 Robinson Road, Singapore, 112233, Singapore"
        },
        {
          "type": "dropoff",
          "to_time": "2018-07-19T01:57:06.698170Z",
          "sequence": 2,
          "lng": 103.7647132,
          "lat": 1.4630478,
          "item_count": 1,
          "id": 65255,
          "from_time": "2018-07-18T17:57:06.698170Z",
          "first_item": {
            "width": 1,
            "tracking_number": "YOJ-C3JHBZLRPT0",
            "order_item_id": 36310,
            "length": 1,
            "height": 1,
            "external_id": "External test #1",
            "external_customer_id3": "external_customer_id3_test",
            "external_customer_id2": "external_customer_id2_test",
            "external_customer_id": "external_customer_id_test",
            "description": "Gift",
            "container_no": "Container test #1"
          },
          "contact": {
            "phone": "+6581551123",
            "name": "vivek",
            "email": "recipient@example.com"
          },
          "address_details": {
            "state": "Singapore",
            "postal_code": "332211",
            "country": "Singapore",
            "address2": "50 Boon Keng Rd",
            "address": "Boon Keng Rd"
          },
          "address": "Boon Keng Rd, 50 Boon Keng Rd, Singapore, 332211, Singapore"
        }
      ],
      "id": 43770
    }
  ]
}

```

*Unassigned TaskGroup index Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSdispatchercreaterulerequest">DispatcherCreateRuleRequest</h2>

<a id="schemadispatchercreaterulerequest"></a>

```json
{
  "meta": {
    "photo_type": "signature",
    "photo_title": "Signature of client"
  },
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}

```

*Sub Task Rule Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|meta|object|false|none|none|
|event|string|false|none|none|
|deleted_at|object|false|none|none|
|company_id|integer|false|none|none|
|action|string|false|none|none|

<h2 id="tocSdispatcherinforesponse">DispatcherInfoResponse</h2>

<a id="schemadispatcherinforesponse"></a>

```json
{
  "socket_token": "ISO32ADFSANFSKSL",
  "role": "Admin",
  "phone": "+849039233232",
  "name": "John Doe",
  "id": 1,
  "email": "dispatcher@yojee.com",
  "device_token": "AJKS13JD322OAFS",
  "company": {}
}

```

*Dispatcher info*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|socket_token|string|false|none|none|
|role|string|false|none|none|
|phone|string|false|none|none|
|name|string|false|none|none|
|id|integer|false|none|none|
|email|string|false|none|none|
|device_token|string|false|none|none|
|company|object|false|none|none|

<h2 id="tocSdispatcherruleresponse">DispatcherRuleResponse</h2>

<a id="schemadispatcherruleresponse"></a>

```json
{
  "task_id": 103,
  "sub_task_rule_id": 21,
  "photo": "https://s3-ap-southeast-1.amazonaws.com/signature.jpg",
  "meta": {
    "photo_type": "Proof",
    "photo_title": "Signature"
  },
  "id": 21,
  "event": "pickup_completed",
  "completion_time": "2018-03-10T03:37:08",
  "company_id": 136,
  "action": "upload_photo"
}

```

*Sub Task Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|task_id|integer|false|none|none|
|sub_task_rule_id|integer|false|none|none|
|photo|string|false|none|none|
|meta|object|false|none|none|
|id|integer|false|none|none|
|event|string|false|none|none|
|completion_time|string|false|none|none|
|company_id|integer|false|none|none|
|action|string|false|none|none|

<h2 id="tocSdispatchersenderadminsrequest">DispatcherSenderAdminsRequest</h2>

<a id="schemadispatchersenderadminsrequest"></a>

```json
{
  "pagination": {
    "total_pages": 1,
    "total_count": 2,
    "limit_value": 10,
    "current_page": 1
  },
  "data": [
    {
      "title": "Software Engineer",
      "organisations": [
        {
          "slug": "yojee",
          "reg_address": "144 Robinson Road",
          "postal_code": "068908",
          "phone": "+6591245934",
          "name": "Organisation 1",
          "id": 1,
          "country": "Singapore",
          "city": "Singapore"
        },
        {
          "slug": "yojee",
          "postal_code": "068908",
          "phone": "+6591245936",
          "name": "Organisation 2",
          "id": 2,
          "country": "Singapore",
          "city": "Singapore"
        }
      ],
      "name": "Ralston",
      "id": 1
    },
    {
      "title": "Account Manager",
      "organisations": [
        {
          "slug": "yojee",
          "reg_address": "St George's Rd",
          "postal_code": "068908",
          "phone": "+6591245736",
          "name": "Organisation 3",
          "id": 2,
          "country": "Singapore",
          "city": "Singapore"
        }
      ],
      "name": "Sam",
      "id": 16
    }
  ]
}

```

*Sender Admins Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSverifyotpresponse">VerifyOtpResponse</h2>

<a id="schemaverifyotpresponse"></a>

```json
{
  "data": {
    "user_profile_id": 1,
    "phone": "+84936362488",
    "id": 1,
    "email": "bob@mail.com",
    "access_token": "T5P2rQrC6KbkPnLE9ebyjskMUTju3vKFBzlAr+bCUpc="
  }
}

```

*Response schema for Verify OTP*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatchercorporatesendersresponse">DispatcherCorporateSendersResponse</h2>

<a id="schemadispatchercorporatesendersresponse"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 2,
    "current_page": 1
  },
  "data": [
    {
      "user_profile_id": 1,
      "name": "ABC"
    }
  ]
}

```

*Corporate Senders Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSlauncher_response">launcher_response</h2>

<a id="schemalauncher_response"></a>

```json
{
  "message": "Dispatcher account created.",
  "data": {
    "user_profile_id": 60,
    "phone": "",
    "name": "Mike",
    "inserted_at": "2018-01-24T08:54:54.204128",
    "id": 1,
    "email": "michael@yojee.com",
    "access_token": "65Mivav6HcJIvkFbxxrjFYg1mK6TIruz+iAs1fFDNlw="
  }
}

```

*Response schema for creating new dispatcher*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSdispatcherupdaterulerequest">DispatcherUpdateRuleRequest</h2>

<a id="schemadispatcherupdaterulerequest"></a>

```json
{
  "meta": {
    "photo_type": "signature",
    "photo_title": "Signature of client"
  },
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}

```

*Sub Task Rule Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|meta|object|false|none|none|
|event|string|false|none|none|
|deleted_at|object|false|none|none|
|company_id|integer|false|none|none|
|action|string|false|none|none|

<h2 id="tocSgetotpresponse">GetOtpResponse</h2>

<a id="schemagetotpresponse"></a>

```json
{
  "data": {
    "otp_code": "123456"
  }
}

```

*Response schema for querying OTP*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocScorporatesendersignuprequest">CorporateSenderSignupRequest</h2>

<a id="schemacorporatesendersignuprequest"></a>

```json
{
  "title": "Engineer",
  "sender_type": "organisation",
  "phone": "+6598765432",
  "payment_option": "monthly_billing",
  "password": "abc123$%^",
  "organisation": {
    "reg_address": "77 Robinson road, Singapore.",
    "postal_code": "321021",
    "phone": "+6591245934",
    "name": "ABC",
    "country": "Singapore",
    "city": "Singapore"
  },
  "name": "Ralston",
  "gst_no": "2AS9890",
  "email": "primary@abc.com",
  "business_reg_no": "ABC1235M",
  "billing_address": "77 Robinson road, Singapore."
}

```

*CorporateSenderSignupRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|sender_type|string|false|none|none|
|phone|string|false|none|none|
|payment_option|string|false|none|none|
|password|string|false|none|none|
|organisation|object|false|none|none|
|name|string|false|none|none|
|gst_no|string|false|none|none|
|email|string|false|none|none|
|business_reg_no|string|false|none|none|
|billing_address|string|false|none|none|

<h2 id="tocSmapsgeocoderesponse">MapsGeoCodeResponse</h2>

<a id="schemamapsgeocoderesponse"></a>

```json
{
  "data": {
    "zipcode": "",
    "lng": 103.8462451,
    "lat": 1.2754876,
    "country": "Singapore",
    "address": "1 Anson Rd, Singapore"
  }
}

```

*Response schema for querying geocode of an address*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSsignuprequest">SignupRequest</h2>

<a id="schemasignuprequest"></a>

```json
{
  "sender_type": "individual",
  "phone": "+6598765432",
  "password": "abc123$%^",
  "name": "Alex",
  "email": "long@yojee.com",
  "billing_address": "77 Robinson road, Singapore.",
  "account_type": "sender"
}

```

*SignupRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sender_type|string|false|none|none|
|phone|string|false|none|none|
|password|string|false|none|none|
|name|string|false|none|none|
|email|string|false|none|none|
|billing_address|string|false|none|none|
|account_type|string|false|none|none|

<h2 id="tocSorderitemsshowresponse">OrderItemsShowResponse</h2>

<a id="schemaorderitemsshowresponse"></a>

```json
{
  "progress_session": [
    {
      "type": "assigned",
      "status": "success"
    },
    {
      "type": "pickup",
      "status": "blank"
    },
    {
      "type": "dropoff",
      "status": "blank"
    }
  ],
  "item_session": {
    "width": 1,
    "weight": 1,
    "status": "scheduled_for_fulfilment",
    "service_type_id": 1,
    "service_type": "same_day",
    "price": "SGD 10",
    "pickup": {
      "time_to": "2018-07-18T12:04:24.205427Z",
      "time_from": "2018-07-18T04:04:24.205427Z",
      "task_id": 65584,
      "state": "Singapore",
      "postal_code": "112233",
      "lng": 103.8481705,
      "lat": 1.2782636,
      "country": "Singapore",
      "contact_phone": "+6581551123",
      "contact_name": "vivek",
      "contact_email": "sender@example.com",
      "contact_company": "Adidas",
      "address2": "160 Robinson Road",
      "address": "144 Robinson Road"
    },
    "payload_type": "Package",
    "order_reference_number": "O-OEZRQLL1ADLU",
    "length": 1,
    "item_id": 33867,
    "is_from_transfer": false,
    "info": "info_test",
    "height": 1,
    "external_id": "External test #1",
    "external_customer_id3": "external_customer_id3_test",
    "external_customer_id2": "external_customer_id2_test",
    "external_customer_id": "external_customer_id_test",
    "editable": false,
    "dropoff": {
      "time_to": "2018-07-18T20:04:24.205427Z",
      "time_from": "2018-07-18T12:04:24.205427Z",
      "task_id": 65585,
      "state": "Singapore",
      "postal_code": "332211",
      "lng": 103.8645118,
      "lat": 1.3153658,
      "country": "Singapore",
      "contact_phone": "+6581551123",
      "contact_name": "vivek",
      "contact_email": "recipient@example.com",
      "contact_company": "Nike",
      "address2": "50 Boon Keng Rd",
      "address": "Boon Keng Rd"
    },
    "description": "Gift",
    "allow_transfer": false
  },
  "delivery_trail": [
    {
      "task_group_id": 42402,
      "state": "accepted",
      "log": [
        {
          "type": "worker_accepted_task_group",
          "logs": [
            {
              "inserted_at": "2018-07-18T04:04:24.256048Z",
              "description": "Item accepted by Mrs. Antone Krajcik (07618671299)"
            }
          ]
        }
      ]
    }
  ]
}

```

*OrderItem Show Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|progress_session|object|false|none|none|
|item_session|object|false|none|none|
|delivery_trail|[any]|false|none|none|

<h2 id="tocSsigninrequest">SigninRequest</h2>

<a id="schemasigninrequest"></a>

```json
{
  "password": "abc123$%^",
  "email": "long@yojee.com"
}

```

*SigninRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|password|string|false|none|none|
|email|string|false|none|none|

<h2 id="tocSstatisticsresponse">StatisticsResponse</h2>

<a id="schemastatisticsresponse"></a>

```json
{
  "data": [
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
  ]
}

```

*Statistics Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSdispatcherupdateworkerrequest">DispatcherUpdateWorkerRequest</h2>

<a id="schemadispatcherupdateworkerrequest"></a>

```json
{
  "vehicle_type_ids": [
    1,
    2
  ],
  "tester": true,
  "phone": "+987654322",
  "otp_token": "TNUSTU2YF7BCDOYR",
  "national_id": "11335577",
  "name": "Mike Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "email": "mike-driver@yojee.com",
  "driver_license": "22446688",
  "current_vehicle_type_id": 1
}

```

*Worker Update Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|vehicle_type_ids|[any]|false|none|none|
|tester|object|false|none|none|
|phone|string|false|none|none|
|otp_token|string|false|none|none|
|national_id_photo_front|object|false|none|none|
|national_id_photo_back|object|false|none|none|
|national_id|string|false|none|none|
|name|string|false|none|none|
|location|object|false|none|none|
|email|string|false|none|none|
|driver_license_photo_front|object|false|none|none|
|driver_license|string|false|none|none|
|current_vehicle_type_id|integer|false|none|none|

<h2 id="tocSdispatcherupdaterolerequest">DispatcherUpdateRoleRequest</h2>

<a id="schemadispatcherupdaterolerequest"></a>

```json
{
  "updated_at": "2018-12-11 08:56:23.843283Z",
  "name": "role_1",
  "company_id": 123,
  "access_map": {
    "sender": {
      "add": true
    }
  }
}

```

*POST body for updating roles*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Role name|
|company_id|integer|false|none|Company ID|
|access_map|object|false|none|Access Map|

<h2 id="tocSauthresponse">AuthResponse</h2>

<a id="schemaauthresponse"></a>

```json
{
  "phone": "+6598765432",
  "email": "bob@mail.com",
  "access_token": "pCVPeEEUuKnM7geUOcSLY2imA5l6YUdjymkApBDAAGY="
}

```

*AuthResponse*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|phone|string|false|none|none|
|email|string|false|none|none|
|access_token|string|false|none|none|

<h2 id="tocScompanyuploadassetsresponse">CompanyUploadAssetsResponse</h2>

<a id="schemacompanyuploadassetsresponse"></a>

```json
{
  "data": "https://s3.us-east-1.amazonaws.com/test/uploads/companies/334/334_logo.png"
}

```

*Company Assets Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocScreateorderrequest">CreateOrderRequest</h2>

<a id="schemacreateorderrequest"></a>

```json
{
  "steps": [
    null
  ],
  "sender_type": "string",
  "sender_id": 0,
  "price_currency": "string",
  "price_amount": 0,
  "items": [
    null
  ],
  "item_steps": [
    null
  ]
}

```

*POST body for dispatcher to create an order*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|steps|[any]|false|none|List of delivery details for pick up and drop off steps|
|sender_type|string|false|none|Sender Type|
|sender_id|integer|false|none|Sender ID|
|price_currency|string|false|none|Order currency|
|price_amount|number|false|none|Order price|
|items|[any]|false|none|List of items to be sent|
|item_steps|[any]|false|none|List of item steps|

<h2 id="tocSdispatchercreatecorporatesenderrequest">DispatcherCreateCorporateSenderRequest</h2>

<a id="schemadispatchercreatecorporatesenderrequest"></a>

```json
{
  "title": "Engineer",
  "sender_type": "organisation",
  "phone": "+6598765432",
  "name": "Ralston",
  "email": "secondary_account@abc.com",
  "billing_address": "77 Robinson road, Singapore."
}

```

*Corporate Sender Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|sender_type|string|false|none|none|
|phone|string|false|none|none|
|name|string|false|none|none|
|email|string|false|none|none|
|billing_address|string|false|none|none|

<h2 id="tocSorderitem">OrderItem</h2>

<a id="schemaorderitem"></a>

```json
{
  "weight": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|weight|integer|false|none|none|

<h2 id="tocSdispatcherindexroleresponse">DispatcherIndexRoleResponse</h2>

<a id="schemadispatcherindexroleresponse"></a>

```json
{
  "data": [
    {
      "name": "role_1",
      "inserted_at": "2018-12-11 08:56:23.842887Z",
      "company_id": 123,
      "access_map": {
        "sender": {
          "add": true
        }
      }
    }
  ]
}

```

*Role Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSlaunchercreatecompanyresponse">LauncherCreateCompanyResponse</h2>

<a id="schemalaunchercreatecompanyresponse"></a>

```json
{
  "message": "Dispatcher account created.",
  "data": {
    "organisation_id": 1,
    "inserted_at": "2018-01-24T08:54:54.204128",
    "id": 1
  }
}

```

*Response schema for creating new company*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSdispatchercreateruleresponse">DispatcherCreateRuleResponse</h2>

<a id="schemadispatchercreateruleresponse"></a>

```json
{
  "meta": {
    "photo_type": "signature",
    "photo_title": "Signature of client"
  },
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}

```

*Sub Task Rule Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|meta|object|false|none|none|
|event|string|false|none|none|
|deleted_at|object|false|none|none|
|company_id|integer|false|none|none|
|action|string|false|none|none|

<h2 id="tocSregionsresponse">RegionsResponse</h2>

<a id="schemaregionsresponse"></a>

```json
{
  "data": [
    {
      "tag": "poly5",
      "inserted_at": "2018-12-11 08:56:23.843812Z",
      "description": "Sample Region",
      "coordinates": [
        [
          {
            "lng": 10,
            "lat": 35
          },
          {
            "lng": 45,
            "lat": 45
          },
          {
            "lng": 40,
            "lat": 15
          },
          {
            "lng": 20,
            "lat": 10
          },
          {
            "lng": 10,
            "lat": 35
          }
        ],
        [
          {
            "lng": 30,
            "lat": 20
          },
          {
            "lng": 35,
            "lat": 35
          },
          {
            "lng": 20,
            "lat": 30
          },
          {
            "lng": 30,
            "lat": 20
          }
        ]
      ],
      "company_id": 1,
      "color": "red"
    }
  ]
}

```

*Regions Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSspokeresponse">SpokeResponse</h2>

<a id="schemaspokeresponse"></a>

```json
{
  "data": {
    "properties": {},
    "pessimistic_estimated_duration": 40,
    "origin_hub_id": 1,
    "optimistic_estimated_duration": 40,
    "name": "spoker",
    "modality": "road",
    "inserted_at": "2018-12-11 08:56:23.844712Z",
    "destination_hub_id": 2,
    "company_id": 1
  }
}

```

*Spoke Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatcherupdateuserrequest">DispatcherUpdateUserRequest</h2>

<a id="schemadispatcherupdateuserrequest"></a>

```json
{
  "phone": "+987654330",
  "password": "passwd112233",
  "name": "Mike Dispatcher"
}

```

*POST body for updating dispatcher user*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|phone|string|true|none|Phone number|
|password|string|false|none|Password|
|name|string|true|none|Full name|

<h2 id="tocSstopsresponse">StopsResponse</h2>

<a id="schemastopsresponse"></a>

```json
{
  "pagination": {
    "total_pages": 1,
    "total_count": 2,
    "limit_value": 10,
    "current_page": 1
  },
  "data": [
    {
      "to": "2018-11-14T06:00:00.000000Z",
      "postal_code": "068896",
      "order_number": "O-D3VHSKDORDNM",
      "lng": 103.8209837,
      "lat": 1.2942236,
      "id": 3586,
      "from": "2018-11-14T02:00:00.000000Z",
      "country": "Singapore",
      "contact": {
        "phone": "+6531591335",
        "name": "Yojee Ops",
        "email": "ralston@yojee.com",
        "company": "yojee"
      },
      "address_state": "Singapore",
      "address2": "#03-01",
      "address": "59 South Park Road"
    }
  ]
}

```

*Stops response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pagination|object|false|none|none|
|data|[any]|false|none|none|

<h2 id="tocSdispatcherpartnertransfercreate">DispatcherPartnerTransferCreate</h2>

<a id="schemadispatcherpartnertransfercreate"></a>

```json
{
  "tracking_numbers": [
    "YOJ-NHLZA0V3PT0"
  ],
  "price_currency": "USD",
  "price_amount": "1.00",
  "partner_cip": "CIP-RTNKAUJLQ3LWRGRA"
}

```

*Partner Transfer Order Create Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|state|string|true|none|State|
|postal_code|number|true|none|Postal code|
|partnership_type|string|true|none|Partnership type|
|contact_phone|string|true|none|Phone number|
|contact_name|string|true|none|Contact name|
|contact_email|string|true|none|Email|
|company_name|string|true|none|Company name|
|address|string|true|none|Registration address|

<h2 id="tocSbroadcastresponse">BroadcastResponse</h2>

<a id="schemabroadcastresponse"></a>

```json
{
  "timeout_in_minutes": 20,
  "task_group_id": 2,
  "status": "sent",
  "price": "SGD 500",
  "id": 1,
  "expires_at": "2018-05-28T08:45:38.632070"
}

```

*Broadcast Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|timeout_in_minutes|integer|false|none|none|
|task_group_id|integer|false|none|none|
|status|string|false|none|none|
|price|string|false|none|none|
|id|integer|false|none|none|
|expires_at|string|false|none|none|
|accepted_at|object|false|none|none|

<h2 id="tocSdispatcherchatmessageresponse">DispatcherChatMessageResponse</h2>

<a id="schemadispatcherchatmessageresponse"></a>

```json
{
  "user_profile": {
    "user_profile_id": 299,
    "name": "Demond Terry"
  },
  "inserted_at": "2018-10-23T07:57:27.538169Z",
  "incoming": false,
  "id": 133,
  "created_at": "2018-10-23T07:56:00.0Z",
  "content": {
    "type": "image",
    "text": "it has value if it is not attachment and it's type is 'text'",
    "attachment": {
      "thumbnail": "https://s3-ap-southeast-1.amazonaws.com/thumbnail_signature.png",
      "original": "https://s3-ap-southeast-1.amazonaws.com/original_signature.png"
    }
  }
}

```

*Chat Message Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user_profile|object|false|none|none|
|inserted_at|string|false|none|none|
|incoming|object|false|none|none|
|id|integer|false|none|none|
|created_at|string|false|none|none|
|content|object|false|none|none|

<h2 id="tocSdispatchercreatesettingrequest">DispatcherCreateSettingRequest</h2>

<a id="schemadispatchercreatesettingrequest"></a>

```json
{
  "settings": {
    "sample settings": "sample value"
  },
  "name": "default"
}

```

*POST body for creating new setting*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|settings|object|true|none|Setting settings|
|name|string|true|none|Setting name|

<h2 id="tocSversionrequest">VersionRequest</h2>

<a id="schemaversionrequest"></a>

```json
{
  "current_installed_version": 500
}

```

*Check if app update is required*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|current_installed_version|integer|false|none|none|

<h2 id="tocSdispatcherpartnershipinfo">DispatcherPartnershipInfo</h2>

<a id="schemadispatcherpartnershipinfo"></a>

```json
{
  "discovery_mode": false,
  "contact_phone": "+6591245934",
  "contact_name": "Ralston",
  "contact_email": "ralston@xyz.com",
  "cip": "CIP-JSUUWH907EOOE"
}

```

*Partnership Info*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|discovery_mode|object|false|none|none|
|contact_phone|string|false|none|none|
|contact_name|string|false|none|none|
|contact_email|string|false|none|none|
|cip|string|false|none|none|

<h2 id="tocStaskgroupresponse">TaskGroupResponse</h2>

<a id="schemataskgroupresponse"></a>

```json
{
  "type": "pickup",
  "to": "2018-03-27T10:00:00.000000Z",
  "task_group_id": 4213,
  "state": "created",
  "start_time": "2018-03-27T10:00:00.000000Z",
  "service_type": "next_day",
  "price": "SGD 10",
  "postal_code": "84184",
  "order_item_tracking_number": "YOJ-229",
  "order_item_id": 229,
  "lng": 103.90331700000002,
  "lat": 1.329095,
  "item": {
    "width": 29,
    "weight": 5,
    "volumetric_weight": 121945,
    "volume": 200,
    "length": 29,
    "height": 29,
    "global_tracking_number": "Y-MEJZPQ"
  },
  "id": 1,
  "from": "2018-03-27T02 =>00 =>00.000000Z",
  "external_id": "ID-1",
  "external_customer_id3": "1345564",
  "external_customer_id2": "545415",
  "external_customer_id": "54418",
  "description": "TEST",
  "country": "Singapore",
  "container_no": "13",
  "contact": {
    "phone": "+6591234567",
    "name": "kris sender"
  },
  "completion_time": "2018-03-26T09 =>49 =>42.679519Z",
  "address_state": "State",
  "address2": "TESTAS",
  "address": "Singapore 400314",
  "additional_info": "Info"
}

```

*TaskGroup Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|to|string|false|none|none|
|task_group_id|integer|false|none|none|
|state|string|false|none|none|
|start_time|string|false|none|none|
|service_type|string|false|none|none|
|price|string|false|none|none|
|postal_code|string|false|none|none|
|order_item_tracking_number|string|false|none|none|
|order_item_id|integer|false|none|none|
|lng|object|false|none|none|
|lat|object|false|none|none|
|item|object|false|none|none|
|id|integer|false|none|none|
|from|string|false|none|none|
|external_id|string|false|none|none|
|external_customer_id3|string|false|none|none|
|external_customer_id2|string|false|none|none|
|external_customer_id|string|false|none|none|
|description|string|false|none|none|
|country|string|false|none|none|
|container_no|string|false|none|none|
|contact|object|false|none|none|
|completion_time|string|false|none|none|
|address_state|string|false|none|none|
|address2|string|false|none|none|
|address|string|false|none|none|
|additional_info|string|false|none|none|

<h2 id="tocSdispatcherworkerspathresponse">DispatcherWorkersPathResponse</h2>

<a id="schemadispatcherworkerspathresponse"></a>

```json
{
  "to": "2019-01-27 23:50:07",
  "ployline_string": "kjlfhsdklfhlksdhf",
  "id": "2",
  "from": "2017-01-27 23:50:07"
}

```

*Worker Path History Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|to|string|false|none|none|
|polyline_string|string\|null|false|none|none|
|id|string|false|none|none|
|from|string|false|none|none|

<h2 id="tocSdispatchercreateroleresponse">DispatcherCreateRoleResponse</h2>

<a id="schemadispatchercreateroleresponse"></a>

```json
{
  "data": {
    "name": "role_1",
    "inserted_at": "2018-12-11 08:56:23.842993Z",
    "company_id": 123,
    "access_map": {
      "sender": {
        "add": true
      }
    }
  }
}

```

*Role Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocScompanyservicetypesresponse">CompanyServiceTypesResponse</h2>

<a id="schemacompanyservicetypesresponse"></a>

```json
{
  "message": "Got company service types",
  "data": {
    "name": "Same Day",
    "key": "same_day",
    "id": 1024,
    "company_id": 601
  }
}

```

*Company Service Types Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocScompletionlocation">CompletionLocation</h2>

<a id="schemacompletionlocation"></a>

```json
{
  "location": {
    "lng": 122.64,
    "lat": 65.676
  }
}

```

*Task Completion Location Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|location|object|false|none|none|

<h2 id="tocShubrequest">HubRequest</h2>

<a id="schemahubrequest"></a>

```json
{
  "regions": [
    "poly5"
  ],
  "properties": {
    "description": "Sample description",
    "address": "Singapore"
  },
  "name": "Sample Hub",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  }
}

```

*Hub Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|regions|[any]|false|none|none|
|properties|object|false|none|none|
|name|string|false|none|none|
|location|object|false|none|none|

<h2 id="tocSdispatcherworkersresponse">DispatcherWorkersResponse</h2>

<a id="schemadispatcherworkersresponse"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 2,
    "current_page": 1
  },
  "data": [
    {
      "vehicle_type_registers": [
        {
          "name": "Bike",
          "id": 1
        },
        {
          "name": "Car",
          "id": 2
        }
      ],
      "vehicle_type_ids": [
        1
      ],
      "user_profile_id": 1,
      "tester": false,
      "phone": "+987654322",
      "password": "passwd112233",
      "otp_token": "1122334455",
      "national_id_photo_front": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/accounts/128817/national_id/128817_original_updated-national-id-front.png",
      "national_id_photo_back": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/accounts/128817/national_id/128817_original_updated-national-id-back.png",
      "national_id": "11335577",
      "name": "Mike Driver",
      "location": {
        "lng": 122.6428429677108,
        "lat": 65.67691234535297
      },
      "inserted_at": "2018-12-11 08:56:23.835796Z",
      "email": "mike-driver@yojee.com",
      "driver_license_photo_front": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/accounts/128817/driver_license/128817_original_updated-driver-license-front.png?v=63701553117",
      "driver_license_photo_back": "https://yojee-uploads-demo.s3.amazonaws.com/uploads/accounts/128817/driver_license/128817_original_updated-driver-license-back.png?v=63701553117",
      "driver_license": "22446688",
      "distance_away": 1100,
      "current_vehicle_type_id": 1,
      "company_id": 1,
      "access_token": "4h/PrR5vu9uVevso3fNv2RPTLQJech3BJ/pNJhWBnfE="
    }
  ]
}

```

*Workers Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocSmapsdirectionrequest">MapsDirectionRequest</h2>

<a id="schemamapsdirectionrequest"></a>

```json
{
  "origin": "1 Anson Rd, Singapore",
  "mode": "driving",
  "destination": "10 Anson Rd, Singapore",
  "country_iso": "sg"
}

```

*POST body for querying map direction*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|origin|string|true|none|Origin|
|mode|string|true|none|Mode|
|destination|string|true|none|Destination|
|country_iso|string|false|none|Country ISO code|

<h2 id="tocSdispatcherpartnercreate">DispatcherPartnerCreate</h2>

<a id="schemadispatcherpartnercreate"></a>

```json
{
  "postal_code": "321021",
  "partnership_type": "downstream",
  "country": "Singapore",
  "contact_phone": "+6591245934",
  "contact_name": "Ralston",
  "contact_email": "ralston@xyz.com",
  "company_name": "XYZ",
  "city": "Singapore",
  "address": "77 Robinson road, Singapore."
}

```

*Partner Create Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|state|string|true|none|State|
|postal_code|number|true|none|Postal code|
|partnership_type|string|true|none|Partnership type|
|contact_phone|string|true|none|Phone number|
|contact_name|string|true|none|Contact name|
|contact_email|string|true|none|Email|
|company_name|string|true|none|Company name|
|address|string|true|none|Registration address|

<h2 id="tocScreateorderresponse">CreateOrderResponse</h2>

<a id="schemacreateorderresponse"></a>

```json
{
  "data": {
    "status": "created",
    "sender_id": 471,
    "price": {
      "currency": "SGD",
      "amount": "10"
    },
    "placed_by_user_profile_id": 1313,
    "paid": false,
    "order_items": {
      "tracking_number": "YOJ-WC9DC3V3PT0",
      "id": 17258
    },
    "number": "O-VWJ1WE5KAW5U",
    "inserted_at": "2018-09-26T14: 55: 40.781628Z",
    "id": 3472,
    "display_price": "SGD 10"
  }
}

```

*Create order response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSorderitemsupdaterequest">OrderItemsUpdateRequest</h2>

<a id="schemaorderitemsupdaterequest"></a>

```json
{
  "width": 2,
  "weight": 2,
  "service_type": "same_day",
  "payload_type": "Updated document",
  "length": 2,
  "info": "info_test",
  "height": 2,
  "external_customer_id3": "changed_external_customer_id3",
  "external_customer_id2": "changed_external_customer_id2",
  "external_customer_id": "changed_external_customer_id",
  "dropoff": {
    "to_time": "2018-12-12T08:56:23.831230",
    "state": "Singapore",
    "postal_code": "332211",
    "lng": 103.8469761,
    "lat": 1.2880209,
    "from_time": "2018-12-12T00:56:23.831230",
    "country": "Singapore",
    "contact_phone": "+6581551123",
    "contact_name": "vivek",
    "contact_email": "recipient@example.com",
    "contact_company": "Nike",
    "address2": "#04-01",
    "address": "59 New Bridge Road"
  },
  "description": "Updated Gift"
}

```

*Order Item Update Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|width|integer|false|none|none|
|weight|integer|false|none|none|
|service_type|string|false|none|none|
|payload_type|string|false|none|none|
|length|integer|false|none|none|
|info|string|false|none|none|
|height|integer|false|none|none|
|external_customer_id3|string|false|none|none|
|external_customer_id2|string|false|none|none|
|external_customer_id|string|false|none|none|
|dropoff|object|false|none|none|
|description|string|false|none|none|

<h2 id="tocSdispatcherpartnerresponse">DispatcherPartnerResponse</h2>

<a id="schemadispatcherpartnerresponse"></a>

```json
{
  "data": {
    "state": "pending",
    "requested_at": "2018-05-22T14:33:57.131041Z",
    "postal_code": "321021",
    "partnership_type": "downstream",
    "country": "Singapore",
    "contact_phone": "+6591245934",
    "contact_name": "Ralston",
    "contact_email": "ralston@xyz.com",
    "company_name": "XYZ",
    "city": "Singapore",
    "cip": "CIP-XJSI232KGTDYTDT",
    "address": "77 Robinson road, Singapore."
  }
}

```

*Partner Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSlaunchercreatecompanyrequest">LauncherCreateCompanyRequest</h2>

<a id="schemalaunchercreatecompanyrequest"></a>

```json
{
  "slug": "yojee",
  "name": "Yojee",
  "country": "Singapore"
}

```

*POST body for creating new company*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|slug|string|false|none|Slug|
|name|string|true|none|Company name|

<h2 id="tocSdispatcherupdateorderrequest">DispatcherUpdateOrderRequest</h2>

<a id="schemadispatcherupdateorderrequest"></a>

```json
{
  "price_currency": "string",
  "price_amount": 0,
  "external_id": "string"
}

```

*Dispathcer update order request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|price_currency|string|false|none|ISO 4217 code currency, e.g: USD|
|price_amount|number|false|none|Price amount of order, e.g: for 10.12 USD, amount should be 10.|
|external_id|string|false|none|External Order Reference Number|

<h2 id="tocSorderaddress">OrderAddress</h2>

<a id="schemaorderaddress"></a>

```json
{
  "zipcode": "string",
  "location": "string",
  "lng": "string",
  "lat": "string",
  "country": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|zipcode|string|false|none|none|
|location|string|false|none|none|
|lng|string|false|none|none|
|lat|string|false|none|none|
|country|string|false|none|none|

<h2 id="tocScompanyupdatesettingsrequest">CompanyUpdateSettingsRequest</h2>

<a id="schemacompanyupdatesettingsrequest"></a>

```json
{
  "settings": {
    "delivery_options": {
      "time_window": {
        "pickup": {
          "to": 18,
          "from": 10
        },
        "dropoff": {
          "to": 22,
          "from": 14
        }
      },
      "pickup_allowance": 2,
      "max_weight": 50,
      "advance_bookings": 14
    }
  }
}

```

*PUT body for updating company settings*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|settings|object|true|none|Settings object|

<h2 id="tocSdispatcherupdateplanrequest">DispatcherUpdatePlanRequest</h2>

<a id="schemadispatcherupdateplanrequest"></a>

```json
{
  "uuid": "123456789",
  "settings": {
    "sample settings": "sample value"
  },
  "output": {
    "sample output": "sample value"
  },
  "input": {
    "sample input": "sample value"
  }
}

```

*POST body for updating plan*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|string|true|none|Plan uuid|
|settings|object|false|none|Plan settings|
|output|object|true|none|Plan output|
|input|object|false|none|Plan input|

<h2 id="tocScompanyconfigsresponse">CompanyConfigsResponse</h2>

<a id="schemacompanyconfigsresponse"></a>

```json
{
  "data": {
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
    ],
    "currency": "SGD",
    "company_slug": "yojee"
  }
}

```

*Config Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSlauncher_request">launcher_request</h2>

<a id="schemalauncher_request"></a>

```json
{
  "phone": "+8412345678",
  "password": "passwd112233",
  "name": "Mike",
  "email": "michael@yojee.com",
  "company_id": 1
}

```

*POST body for creating new dispatcher*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user_profile|object|false|none|none|
|» password|string|true|none|Password|
|» name|string|true|none|Full name|
|» email|string|true|none|Email|
|company_id|integer|true|none|Company ID|

<h2 id="tocSmapsdirectionresponse">MapsDirectionResponse</h2>

<a id="schemamapsdirectionresponse"></a>

```json
{
  "data": {
    "overview_polyline": "ybxFanyxRkAy@eA_AqAuAMQPST_@Xc@t@iAPJ`Ah@pBz@bAr@lCbC|@t@LHR`@DL@JAVWZiApAk@f@_CsBeBmA",
    "duration": 222,
    "distance": 968,
    "data": [
      [
        "ybxFanyxRkAy@eA_A",
        "kgxF{qyxRe@c@k@q@",
        "}ixFqtyxRMQPSJQHMDER]t@iA",
        "sfxFezyxRPJ\\Tb@RRH|Ap@`@T`@\\t@p@vApA`@\\ZVLH",
        "owwF{nyxRR`@BF@D@D?DAVWZw@`AQNYVQN",
        "c{wFqgyxRuBiBIIeBmA"
      ]
    ]
  }
}

```

*Response schema for querying map direction*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocStrackorderitemresponse">TrackOrderItemResponse</h2>

<a id="schematrackorderitemresponse"></a>

```json
{
  "data": [
    {
      "status": "accepted",
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
      "inserted_at": "2018-03-20T15:18:38.613719"
    }
  ]
}

```

*Response schema for tracking an order item*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocStaskexceptionreasonrequest">TaskExceptionReasonRequest</h2>

<a id="schemataskexceptionreasonrequest"></a>

```json
{
  "description": "Sender not available",
  "company_id": 1
}

```

*Task Exception Reason Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|description|string|false|none|none|
|company_id|integer|false|none|none|

<h2 id="tocSdispatcherordersresponse">DispatcherOrdersResponse</h2>

<a id="schemadispatcherordersresponse"></a>

```json
{
  "pagination": {
    "total_pages": 2,
    "total_count": 1,
    "limit_value": 2,
    "current_page": 1
  },
  "data": [
    {
      "tracking_number": "O-M1RHTJHJZGKX",
      "status": "created",
      "sender_type": "organisation",
      "sender_id": 1,
      "price_currency": "SGD",
      "price_amount": 0,
      "number": "Z1QxNVRKUWwvKzUzc00wUkJEeXZUUT09",
      "inserted_at": "2018-12-11 08:56:23.829311Z",
      "access_token": "4h/PrR5vu9uVevso3fNv2RPTLQJech3BJ/pNJhWBnfE="
    }
  ]
}

```

*Orders Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|none|

<h2 id="tocScompaniesresponse">CompaniesResponse</h2>

<a id="schemacompaniesresponse"></a>

```json
{
  "message": "Got list of worker's companies",
  "data": {
    "companies": [
      {
        "title": "yojee",
        "theme": "yojee",
        "show_service_type": 1,
        "default_lang": "en",
        "company_slug": "yojee"
      }
    ]
  }
}

```

*Driver's companies Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSsubtaskrequest">SubTaskRequest</h2>

<a id="schemasubtaskrequest"></a>

```json
{
  "task_id": 2,
  "sub_task_rule_id": 3,
  "photo": "https://s3-ap-southeast-1.amazonaws.com/signature.jpg",
  "completion_data": {
    "recipient_name": "recipient",
    "arrival_time": "2018-03-10T03:37:08"
  }
}

```

*SubTask Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|task_id|integer|false|none|none|
|sub_task_rule_id|integer|false|none|none|
|photo|string|false|none|none|
|completion_data|object|false|none|none|

<h2 id="tocStrackorderresponse">TrackOrderResponse</h2>

<a id="schematrackorderresponse"></a>

```json
{
  "data": [
    {
      "tracking_number": "O-SK1LAUPOQXJF",
      "status": "created",
      "price": "SGD 10",
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
      "external_id": "EXT-21382093",
      "description": "Gift",
      "container_no": "CON-83773878"
    }
  ]
}

```

*Response schema for tracking an order*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSdispatcherplanresponse">DispatcherPlanResponse</h2>

<a id="schemadispatcherplanresponse"></a>

```json
{
  "data": {
    "uuid": "123456789",
    "settings": {
      "sample settings": "sample value"
    },
    "output": {
      "sample output": "sample value"
    },
    "input": {
      "sample input": "sample value"
    },
    "id": 1,
    "company_id": 1
  }
}

```

*Plan Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSregionrequest">RegionRequest</h2>

<a id="schemaregionrequest"></a>

```json
{
  "tag": "poly5",
  "description": "Sample Region",
  "coordinates": [
    [
      {
        "lng": 10,
        "lat": 35
      },
      {
        "lng": 45,
        "lat": 45
      },
      {
        "lng": 40,
        "lat": 15
      },
      {
        "lng": 20,
        "lat": 10
      },
      {
        "lng": 10,
        "lat": 35
      }
    ],
    [
      {
        "lng": 30,
        "lat": 20
      },
      {
        "lng": 35,
        "lat": 35
      },
      {
        "lng": 20,
        "lat": 30
      },
      {
        "lng": 30,
        "lat": 20
      }
    ]
  ],
  "color": "red"
}

```

*Region Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tag|string|false|none|none|
|description|string|false|none|none|
|coordinates|[any]|false|none|none|
|color|string|false|none|none|

<h2 id="tocSwebhook_order_response">Webhook Order Response</h2>

<a id="schema_webhook_order_response"></a>

```json
{
  "cancelled_at": null,
  "external_id": null,
  "id": 5395,
  "inserted_at": "2019-02-20T04:38:14.681548Z",
  "number": "O-A2ROU1DHCJZH",
  "order_items": [
    {
      "id": 37669,
      "inserted_at": "2019-02-20T04:38:18.934173Z",
      "item": {
        "description": "1 package",
        "global_tracking_number": "Y-ZKTVPQ",
        "height": 40,
        "id": 43271,
        "length": 50,
        "payload_type": "Package",
        "quantity": 1,
        "volume": 80000,
        "volumetric_weight": 16,
        "weight": 5,
        "width": 40
      },
      "service_type": "same_day",
      "status": "created",
      "tracking_number": "YOJ-CMHWDJZ3PT0",
      "transfer_info": null
    }
  ],
  "price": {
    "amount": "0.00000000",
    "currency": "SGD"
  },
  "sender": {
    "id": 488,
    "name": null,
    "organisation_name": "Test corporate yojee",
    "type": "organisation"
  },
  "status": "accepted"
}

```

### Properties

| Name            | Type      | Description                                                                               |
|---------------- |---------  |------------------------------------------------------------------------------------------ |
| id              | integer   | order's id                                                                                |
| number          | string    | order's number                                                                            |
| price           | map       | price's information                                                                       |
| price.amount    | string    | amount of money price                                                                     |
| price.currency  | string    | currency name                                                                             |
| status          | string    | id of webhook which subscribes the event                                                  |
| order_items     | array     | an array containing the information of [order item](#schema_webhook_order_item_response)  |
| sender          | map       | [sender's information](#schema_webhook_sender_response)                                   |
| external_id     | string    | order's custom id                                                                         |
| inserted_at     | string    | order creation date time                                                                  |
| cancelled_at    | string    | order cancellation date time                                                              |


<h2 id="tocSwebhook_order_item_response">Webhook Order Item Response</h2>

<a id="schema_webhook_order_item_response"></a>

```json
{
  "id": 37669,
  "inserted_at": "2019-02-20T04:38:18.934173Z",
  "item": {
    "description": "1 package",
    "global_tracking_number": "Y-ZKTVPQ",
    "height": 40,
    "id": 43271,
    "length": 50,
    "payload_type": "Package",
    "quantity": 1,
    "volume": 80000,
    "volumetric_weight": 16,
    "weight": 5,
    "width": 40
  },
  "service_type": "same_day",
  "status": "created",
  "tracking_number": "YOJ-CMHWDJZ3PT0"
}
```

### Properties

| Name              | Type      | Description                                           |
|-----------------  |---------  |-----------------------------------------------------  |
| id                | integer   | order item's id                                       |
| inserted_at       | string    | order item creation date time                         |
| item              | map       | [item's information](#schema_webhook_item_response)   |
| service_type      | string    | order item's service type                             |
| status            | string    | order item's status                                   |
| tracking_number   | string    | order item's tracking number                          |


<h2 id="tocSwebhook_item_response">Webhook Item Response</h2>

<a id="schema_webhook_item_response"></a>

```json
{
  "description": "1 package",
  "global_tracking_number": "Y-ZKTVPQ",
  "height": 40,
  "id": 43271,
  "length": 50,
  "payload_type": "Package",
  "quantity": 1,
  "volume": 80000,
  "volumetric_weight": 16,
  "weight": 5,
  "width": 40
}
```

### Properties

| Name                    | Type      | Description               |
|------------------------ |---------  |-------------------------- |
| id                      | integer   | item's id                 |
| description             | string    | item's description        |
| global_tracking_number  | string    | item's tracking number    |
| height                  | double    | item's height             |
| length                  | double    | item's length             |
| weight                  | double    | item's weight             |
| width                   | double    | item's width              |
| quantity                | integer   | the number of quantity    |
| volume                  | double    | item's volume             |
| volumetric_weight       | double    | item's volumetric weight  |

<h2 id="tocSwebhook_sender_response">Webhook Sender Response</h2>

<a id="schema_webhook_sender_response"></a>

```json
{
  "id": 1,
  "email": "mike@gmail.com",
  "name": "Mike",
  "phone": "+8499999999",
  "billing_address": "123 Robinson Road",
  "sender_type": "individual",
  "inserted_at": "2019-02-20T04:38:18.934173Z",
  "updated_at": "2019-02-20T04:38:18.934173Z"
}
```

### Properties

| Name              | Type      | Description                                 |
|-----------------  |---------  |-------------------------------------------- |
| id                | integer   | sender's id                                 |
| description       | string    | the description of sender                   |
| name              | string    | sender's name                               |
| phone             | string    | phone number                                |
| billing_address   | string    | the sender's address                        |
| sender_type       | string    | type of sender: organisation or individual  |
| inserted_at       | string    | sender creation date time                   |


<h2 id="tocSwebhook_payment_response">Webhook Payment Response</h2>

<a id="schema_webhook_payment_response"></a>

```json
{
  "payment_data": {"id":"ch_1E7dnMEW8RIiGRid9COJH1Qk","object":"charge","amount":100,"amount_refunded":0,"application":null,"application_fee":null,"application_fee_amount":null,"balance_transaction":"txn_1E56OLEW8RIiGRid1eMRotPF","captured":false,"created":1551079356,"currency":"usd","customer":null,"description":"My First Test Charge (created for API docs)","destination":null,"dispute":null,"failure_code":null,"failure_message":null,"fraud_details":{},"invoice":null,"livemode":false,"metadata":{},"on_behalf_of":null,"order":null,"outcome":null,"paid":true,"payment_intent":null,"receipt_email":null,"receipt_number":null,"receipt_url":"https://pay.stripe.com/receipts/acct_1E2woUEW8RIiGRid/ch_1E7dnMEW8RIiGRid9COJH1Qk/rcpt_EapSCV0vOBLfqRG5wFODSX21oNdTiFw","refunded":false,"refunds":{"object":"list","data":[],"has_more":false,"total_count":0,"url":"/v1/charges/ch_1E7dnMEW8RIiGRid9COJH1Qk/refunds"},"review":null,"shipping":null,"source":{"id":"card_1E5BhNEW8RIiGRidtWxWUKSU","object":"card","address_city":null,"address_country":null,"address_line1":null,"address_line1_check":null,"address_line2":null,"address_state":null,"address_zip":null,"address_zip_check":null,"brand":"Visa","country":"US","customer":null,"cvc_check":null,"dynamic_last4":null,"exp_month":8,"exp_year":2020,"fingerprint":"muLJgjDWsgQDqh6c","funding":"credit","last4":"4242","metadata":{},"name":"Jenny Rosen","tokenization_method":null},"source_transfer":null,"statement_descriptor":null,"status":"succeeded","transfer_data":null,"transfer_group":null},
  "order": {
    "cancelled_at": null,
    "external_id": null,
    "id": 5395,
    "inserted_at": "2019-02-20T04:38:14.681548Z",
    "number": "O-A2ROU1DHCJZH",
    "order_items": [
      {
        "id": 37669,
        "inserted_at": "2019-02-20T04:38:18.934173Z",
        "item": {
          "description": "1 package",
          "global_tracking_number": "Y-ZKTVPQ",
          "height": 40,
          "id": 43271,
          "length": 50,
          "payload_type": "Package",
          "quantity": 1,
          "volume": 80000,
          "volumetric_weight": 16,
          "weight": 5,
          "width": 40
        },
        "service_type": "same_day",
        "status": "created",
        "tracking_number": "YOJ-CMHWDJZ3PT0",
        "transfer_info": null
      }
    ],
    "price": {
      "amount": "0.00000000",
      "currency": "SGD"
    },
    "sender": {
      "id": 488,
      "name": null,
      "organisation_name": "Test corporate yojee",
      "type": "organisation"
    },
    "status": "accepted"
  }
}
```

### Properties

| Name          | Type    | Description                                                                 |
|-------------- |-------- |---------------------------------------------------------------------------  |
| payment_data  | string  | [the response is returned by Stripe](https://stripe.com/docs/api/charges)   |
| order         | map     | [WebhookOrderResponse](#schema_webhook_order_response)                      |
