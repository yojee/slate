<h1 id="Yojee-APIs-[Public]-Info">[Public] Info</h1>

## ApiWeb.V3.UserController.info

<a id="opIdApiWeb.V3.UserController.info"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/public/users/info?company_slug=string

```

`GET https://umbrella-demo.yojee.com/api/v3/public/users/info`

*Get user infomation*

<h3 id="apiweb.v3.usercontroller.info-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|company_slug|query|string|true|Company slug|



## ApiWeb.V3.ApiController.verify_otp

<a id="opIdApiWeb.V3.ApiController.verify_otp"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/public/verify_otp/ \
  -H 'Accept: */*'

```

`GET https://umbrella-demo.yojee.com/api/v3/public/verify_otp/`

*Verify OTP code*

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



## ApiWeb.V3.Public.OrdersController.get_prices

<a id="opIdApiWeb.V3.Public.OrdersController.get_prices"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/public/orders/price \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

`POST https://umbrella-demo.yojee.com/api/v3/public/orders/price`

*Get price estimate*

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
|body|body|[GetPricesRequest](#schemagetpricesrequest)|false|Get Prices information|

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



## ApiWeb.V3.ApiController.track_order

<a id="opIdApiWeb.V3.ApiController.track_order"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/public/track/{number} \
  -H 'Accept: */*'

```

`GET https://umbrella-demo.yojee.com/api/v3/public/track/{number}`

*Get tracking data of an order*

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



## ApiWeb.V3.ApiController.get_otp

<a id="opIdApiWeb.V3.ApiController.get_otp"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/public/otp/ \
  -H 'Accept: */*'

```

`GET https://umbrella-demo.yojee.com/api/v3/public/otp/`

*Get OTP code*

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

<h1 id="Yojee-APIs-[Public]-Invoice">[Public] Invoice</h1>

## ApiWeb.V3.Public.InvoiceController.generate

<a id="opIdApiWeb.V3.Public.InvoiceController.generate"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/public/invoices/{order_number}

```

`GET https://umbrella-demo.yojee.com/api/v3/public/invoices/{order_number}`

*Generate an invoice on the fly*

<h3 id="apiweb.v3.public.invoicecontroller.generate-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|order_number|query|string|false|Order Number|

<h3 id="apiweb.v3.public.invoicecontroller.generate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Create label binary fow download|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

<h1 id="Yojee-APIs-[Public]-Label">[Public] Label</h1>

## ApiWeb.V3.Public.LabelController.generate_from_tracking_number

<a id="opIdApiWeb.V3.Public.LabelController.generate_from_tracking_number"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/public/labels/{tracking_number}

```

`GET https://umbrella-demo.yojee.com/api/v3/public/labels/{tracking_number}`

*Generate a label on the fly*

<h3 id="apiweb.v3.public.labelcontroller.generate_from_tracking_number-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|tracking_number|query|string|false|Tracking number|
|format|query|string|false|Output format|

### Enumerated Values

|Parameter|Value|
|---|---|
|format|html|
|format|pdf|

<h3 id="apiweb.v3.public.labelcontroller.generate_from_tracking_number-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Label to be downloaded.|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|



## ApiWeb.V3.Public.LabelController.generate_from_order_number

<a id="opIdApiWeb.V3.Public.LabelController.generate_from_order_number"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/public/labels/order/{order_number}

```

`GET https://umbrella-demo.yojee.com/api/v3/public/labels/order/{order_number}`

*Generate a label on the fly from order number*

<h3 id="apiweb.v3.public.labelcontroller.generate_from_order_number-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|order_number|query|string|false|Order number|
|format|query|string|false|Output format|

### Enumerated Values

|Parameter|Value|
|---|---|
|format|html|
|format|pdf|

<h3 id="apiweb.v3.public.labelcontroller.generate_from_order_number-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Label to be downloaded.|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|

<h1 id="Yojee-APIs-[Public]-Password">[Public] Password</h1>

## ApiWeb.V3.Public.PasswordController.edit

<a id="opIdApiWeb.V3.Public.PasswordController.edit"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/public/password/edit

```

`GET https://umbrella-demo.yojee.com/api/v3/public/password/edit`

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



## ApiWeb.V3.Public.PasswordController.update

<a id="opIdApiWeb.V3.Public.PasswordController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella-demo.yojee.com/api/v3/public/password

```

`PATCH https://umbrella-demo.yojee.com/api/v3/public/password`

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



## ApiWeb.V3.Public.PasswordController.create

<a id="opIdApiWeb.V3.Public.PasswordController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/public/password

```

`POST https://umbrella-demo.yojee.com/api/v3/public/password`

*Create reset password token and send email*

<h3 id="apiweb.v3.public.passwordcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|email|query|string|false|Email of the account to reset password|

<h3 id="apiweb.v3.public.passwordcontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|
