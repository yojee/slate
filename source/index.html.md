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

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


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


<h1 id="Yojee-APIs-[Auth]">[Auth]</h1>

## ApiWeb.V3.AuthController.signup

<a id="opIdApiWeb.V3.AuthController.signup"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/auth/signup \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella-demo.yojee.com/api/v3/auth/signup`

*Individual Sender Sign up*

> Body parameter

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

<h3 id="apiweb.v3.authcontroller.signup-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SignupRequest](#schemasignuprequest)|false|Account Info|

> Example responses

> 200 Response

<h3 id="apiweb.v3.authcontroller.signup-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthResponse](#schemaauthresponse)|



## ApiWeb.V3.AuthController.corporate_sender_signup

<a id="opIdApiWeb.V3.AuthController.corporate_sender_signup"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/auth/corporate_sender/signup \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella-demo.yojee.com/api/v3/auth/corporate_sender/signup`

*Corporate Sender Sign up*

> Body parameter

```json
{
  "uen_no": "ABC1235M",
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
  "billing_address": "77 Robinson road, Singapore."
}
```

<h3 id="apiweb.v3.authcontroller.corporate_sender_signup-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CorporateSenderSignupRequest](#schemacorporatesendersignuprequest)|false|Account Info|

> Example responses

> 200 Response

<h3 id="apiweb.v3.authcontroller.corporate_sender_signup-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthResponse](#schemaauthresponse)|



## ApiWeb.V3.AuthController.signin

<a id="opIdApiWeb.V3.AuthController.signin"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/auth/signin \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella-demo.yojee.com/api/v3/auth/signin`

*Sign in*

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
|body|body|[SigninRequest](#schemasigninrequest)|false|Account Info|

> Example responses

> 200 Response

<h3 id="apiweb.v3.authcontroller.signin-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthResponse](#schemaauthresponse)|


<h1 id="Yojee-APIs-[Map]">[Map]</h1>

## ApiWeb.V3.MapsController.geocode

<a id="opIdApiWeb.V3.MapsController.geocode"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/maps/geocode \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella-demo.yojee.com/api/v3/maps/geocode`

*Get geocode of an address*

> Body parameter

```json
{
  "query": "1 Anson Rd",
  "country_code": "SG"
}
```

<h3 id="apiweb.v3.mapscontroller.geocode-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MapsGeoCodeRequest](#schemamapsgeocoderequest)|false|Address information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.mapscontroller.geocode-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got geocode|[MapsGeoCodeResponse](#schemamapsgeocoderesponse)|



## ApiWeb.V3.MapsController.direction

<a id="opIdApiWeb.V3.MapsController.direction"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/maps/direction \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella-demo.yojee.com/api/v3/maps/direction`

*Get direction information*

> Body parameter

```json
{
  "origin": "1 Anson Rd, Singapore",
  "mode": "driving",
  "destination": "10 Anson Rd, Singapore",
  "country_iso": "sg"
}
```

<h3 id="apiweb.v3.mapscontroller.direction-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MapsDirectionRequest](#schemamapsdirectionrequest)|false|Address information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.mapscontroller.direction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got directions information|[MapsDirectionResponse](#schemamapsdirectionresponse)|



## ApiWeb.V3.MapsController.autocomplete

<a id="opIdApiWeb.V3.MapsController.autocomplete"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/maps/autocomplete \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella-demo.yojee.com/api/v3/maps/autocomplete`

*Get complete suggestions of an address*

> Body parameter

```json
{
  "query": "1 Anson Rd, Singapore",
  "country_iso": "sg"
}
```

<h3 id="apiweb.v3.mapscontroller.autocomplete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MapsAutoCompleteRequest](#schemamapsautocompleterequest)|false|Address information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.mapscontroller.autocomplete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Got geocode|[MapsAutoCompleteResponse](#schemamapsautocompleteresponse)|


<h1 id="Yojee-APIs-[Launcher]">[Launcher]</h1>

## ApiWeb.V3.Launcher.DispatcherController.create

<a id="opIdApiWeb.V3.Launcher.DispatcherController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/launcher/dispatchers \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella-demo.yojee.com/api/v3/launcher/dispatchers`

*Create new dispatcher*

> Body parameter

```json
{
  "phone": "+8412345678",
  "password": "passwd112233",
  "name": "Mike",
  "email": "michael@yojee.com",
  "company_id": 1
}
```

<h3 id="apiweb.v3.launcher.dispatchercontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[launcher_request](#schemalauncher_request)|false|Dispatcher information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.launcher.dispatchercontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|created|[launcher_response](#schemalauncher_response)|



## ApiWeb.V3.Launcher.CompanyController.create

<a id="opIdApiWeb.V3.Launcher.CompanyController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/launcher/companies \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST https://umbrella-demo.yojee.com/api/v3/launcher/companies`

*Create new company*

> Body parameter

```json
{
  "slug": "yojee",
  "name": "Yojee",
  "country": "Singapore"
}
```

<h3 id="apiweb.v3.launcher.companycontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[LauncherCreateCompanyRequest](#schemalaunchercreatecompanyrequest)|false|Company information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.launcher.companycontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created company|[LauncherCreateCompanyResponse](#schemalaunchercreatecompanyresponse)|


<h1 id="Yojee-APIs-[Sender]-Info">[Sender] Info</h1>

## ApiWeb.V3.Sender.InfoController.me

<a id="opIdApiWeb.V3.Sender.InfoController.me"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/sender/info \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/sender/info`

*Get sender infomation*

<h3 id="apiweb.v3.sender.infocontroller.me-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|


<h1 id="Yojee-APIs-[Sender]-Order">[Sender] Order</h1>

## ApiWeb.V3.Sender.OrderController.cancel

<a id="opIdApiWeb.V3.Sender.OrderController.cancel"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}/cancel \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}/cancel`

*Cancel an order*

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



## ApiWeb.V3.Sender.OrderController.completed

<a id="opIdApiWeb.V3.Sender.OrderController.completed"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/sender/orders/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/sender/orders/completed`

Get all completed orders of a sender

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



## ApiWeb.V3.Sender.PaymentsController.create

<a id="opIdApiWeb.V3.Sender.PaymentsController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}/payments \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}/payments`

*Create payment request*

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Payment is executed|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Payment failed!|None|



## ApiWeb.V3.Sender.OrderController.create

<a id="opIdApiWeb.V3.Sender.OrderController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/sender/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/sender/orders`

*Create order request*

> Body parameter

```json
{
  "vehicle_type_id": 0,
  "sender_id": 0,
  "price_currency": "string",
  "price_amount": 0,
  "placed_by_user_profile_id": 0,
  "jobs": [
    null
  ],
  "items": [
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



## ApiWeb.V3.Sender.OrderController.show

<a id="opIdApiWeb.V3.Sender.OrderController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/sender/orders/{number} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/sender/orders/{number}`

*Get order detail*

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



## ApiWeb.V3.Sender.OrderController.ongoing

<a id="opIdApiWeb.V3.Sender.OrderController.ongoing"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/sender/orders/ongoing?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/sender/orders/ongoing`

Get all onging orders of a sender

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

## ApiWeb.V3.Sender.BatchController.check_status

<a id="opIdApiWeb.V3.Sender.BatchController.check_status"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/sender/batches/check_status \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/sender/batches/check_status`

*Check batch status*

<h3 id="apiweb.v3.sender.batchcontroller.check_status-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|batch_id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|


## ApiWeb.V3.Sender.BatchController.create

<a id="opIdApiWeb.V3.Sender.BatchController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/sender/batches \
  -H 'Content-Type: multipart/form-data' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/sender/batches`

*Uploads a file*

> Body parameter

```yaml
file: string

```

<h3 id="apiweb.v3.sender.batchcontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|uploader_id|query|integer|false|Uploader Id|
|company_id|query|integer|false|Company Id|
|body|body|[ApiWeb.V3.Dispatcher.BatchController.create](#schemaapiweb.v3.dispatcher.batchcontroller.create)|false|none|
|» file|body|string(binary)|false|The file to upload|


<h1 id="Yojee-APIs-[Worker]-Info">[Worker] Info</h1>

## ApiWeb.V3.Worker.InfoController.me

<a id="opIdApiWeb.V3.Worker.InfoController.me"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/info \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/info`

*Get worker infomation*

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

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/statistics \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/statistics`

Get statistics about task

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


<h1 id="Yojee-APIs-[Worker]-Location">[Worker] Location</h1>

## ApiWeb.V3.Worker.UserController.location

<a id="opIdApiWeb.V3.Worker.UserController.location"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/worker/location \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/worker/location`

*Update the location of worker*

Update the location of worker

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



<h1 id="Yojee-APIs-[Worker]-Device Token">[Worker] Device Token</h1>

## ApiWeb.V3.Worker.UserController.store_device_token

<a id="opIdApiWeb.V3.Worker.UserController.store_device_token"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/worker/store_device_token \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/worker/store_device_token`

*Stores the device token of a worker*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.worker.usercontroller.store_device_token-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|any|true|device token|

<h3 id="apiweb.v3.worker.usercontroller.store_device_token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Stored device token successfully|None|




<h1 id="Yojee-APIs-[Worker]-User">[Worker] User</h1>

## ApiWeb.V3.Worker.UserController.update

<a id="opIdApiWeb.V3.Worker.UserController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/worker/update \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/worker/update`

*Update worker infomation*

> Body parameter

```json
null
```

<h3 id="apiweb.v3.worker.usercontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|any|false|worker's status|

> Example responses

> 200 Response

<h3 id="apiweb.v3.worker.usercontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[WorkerResponse](#schemaworkerresponse)|


<h1 id="Yojee-APIs-[Worker]-Company">[Worker] Company</h1>

## ApiWeb.V3.Worker.CompanyController.config

<a id="opIdApiWeb.V3.Worker.CompanyController.config"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/companies/config \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/companies/config`

Get all configs for a specific company

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


<h1 id="Yojee-APIs-[Worker]-Vehicle">[Worker] Vehicle</h1>

## ApiWeb.V3.Worker.VehicleController.select

<a id="opIdApiWeb.V3.Worker.VehicleController.select"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/worker/vehicles/{id}/select \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/worker/vehicles/{id}/select`

Select a vehicle

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


<h1 id="Yojee-APIs-[Worker]-TaskGroup">[Worker] TaskGroup</h1>

## ApiWeb.V3.Worker.TaskGroupController.index

<a id="opIdApiWeb.V3.Worker.TaskGroupController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/task_groups \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/task_groups`

*List task group by statuses*

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

curl -X PUT https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}/reject \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}/reject`

*Reject a task group*

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

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}`

*Get a task groups*

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

curl -X PUT https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}/accept \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/worker/task_groups/{id}/accept`

*Accept a task group*

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

## ApiWeb.V3.Worker.TaskController.batch_complete_status

<a id="opIdApiWeb.V3.Worker.TaskController.batch_complete_status"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/batches/{id}/status \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/batches/{id}/status`

*Check status of bulk complete*

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

curl -X POST https://umbrella-demo.yojee.com/api/v3/worker/task/{id}/mark_as_failed \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/worker/task/{id}/mark_as_failed`

Marks a task as failed by creating an associated task exception

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

curl -X PUT https://umbrella-demo.yojee.com/api/v3/worker/tasks/bulk_complete \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/worker/tasks/bulk_complete`

*Complete a list of tasks*

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

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/ongoing?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/ongoing`

*List ongoing tasks*

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

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/completed`

*List completed tasks*

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

curl -X PUT https://umbrella-demo.yojee.com/api/v3/worker/tasks/{id}/complete \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/worker/tasks/{id}/complete`

*Complete a task*

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
|body|body|any|false|Completion Time|



## ApiWeb.V3.Worker.TaskController.history

<a id="opIdApiWeb.V3.Worker.TaskController.history"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/history?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/worker/tasks/history`

*List completed and failed tasks*

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

## ApiWeb.V3.Worker.SubTaskController.create

<a id="opIdApiWeb.V3.Worker.SubTaskController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/worker/sub_tasks \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/worker/sub_tasks`

Create a sub task

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


<h1 id="Yojee-APIs-[Dispatcher]-Info">[Dispatcher] Info</h1>

## ApiWeb.V3.Dispatcher.InfoController.me

<a id="opIdApiWeb.V3.Dispatcher.InfoController.me"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/info \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/info`

*Get current dispatcher user*

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



<h1 id="Yojee-APIs-[Dispatcher]-User">[Dispatcher] User</h1>

Dispatcher (aka User) management

## ApiWeb.V3.Dispatcher.UserController.create

<a id="opIdApiWeb.V3.Dispatcher.UserController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/users \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/users`

*Create new company user*

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



## ApiWeb.V3.Dispatcher.UserController.index

<a id="opIdApiWeb.V3.Dispatcher.UserController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/users \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/users`

*List company users*

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



## ApiWeb.V3.Dispatcher.UserController.update

<a id="opIdApiWeb.V3.Dispatcher.UserController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/users/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/users/{id}`

*Update company user*

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




<h1 id="Yojee-APIs-[Dispatcher]-Partner">[Dispatcher] Partner</h1>

Partner management

## ApiWeb.V3.Dispatcher.PartnerController.decline

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.decline"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/reject_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/reject_invite`

*Declines a partner company invite*

<h3 id="apiweb.v3.dispatcher.partnercontroller.decline-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|cip|path|string|true|Partner CIP|

<h3 id="apiweb.v3.dispatcher.partnercontroller.decline-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Partnership invite declined successfully|None|



## ApiWeb.V3.Dispatcher.PartnerController.update

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/company_partner_info \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/company_partner_info`

*Update company partner info*

> Body parameter

```json
{
  "contact_phone": "+6591245934",
  "contact_name": "Ralston",
  "contact_email": "ralston@xyz.com"
}
```

<h3 id="apiweb.v3.dispatcher.partnercontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherCompanyPartnerInfoUpdate](#schemadispatchercompanypartnerinfoupdate)|false|My info|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartnerResponse](#schemadispatcherpartnerresponse)|



## ApiWeb.V3.Dispatcher.PartnerController.send

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.send"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/send_invite?partnership_type=upstream \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/send_invite`

*Invite a partner company*

<h3 id="apiweb.v3.dispatcher.partnercontroller.send-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|cip|path|string|true|Partner CIP|
|partnership_type|query|array[string]|true|Partnership Type|

### Enumerated Values

|Parameter|Value|
|---|---|
|partnership_type|upstream|
|partnership_type|downstream|

<h3 id="apiweb.v3.dispatcher.partnercontroller.send-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Partnership invite sent successfully|None|



## ApiWeb.V3.Dispatcher.PartnerController.show

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{id}`

*Get partner details*

<h3 id="apiweb.v3.dispatcher.partnercontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|cip|path|string|true|Partner CIP|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartnerResponse](#schemadispatcherpartnerresponse)|



## ApiWeb.V3.Dispatcher.PartnerController.accept

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.accept"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/accept_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/accept_invite`

*Accepts a partner company invite*

<h3 id="apiweb.v3.dispatcher.partnercontroller.accept-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|cip|path|string|true|Partner CIP|

<h3 id="apiweb.v3.dispatcher.partnercontroller.accept-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Partnership invite accepted successfully|None|



## ApiWeb.V3.Dispatcher.PartnerController.create

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/partners \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/partners`

*Create a partner*

> Body parameter

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

<h3 id="apiweb.v3.dispatcher.partnercontroller.create-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|body|body|[DispatcherPartnerCreate](#schemadispatcherpartnercreate)|false|Partner information|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Created partner|[DispatcherPartnerResponse](#schemadispatcherpartnerresponse)|



## ApiWeb.V3.Dispatcher.PartnerController.index

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/partners?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/partners`

*List partners of a company*

<h3 id="apiweb.v3.dispatcher.partnercontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartners](#schemadispatcherpartners)|




<h1 id="Yojee-APIs-[Dispatcher]-Sender">[Dispatcher] Sender</h1>

Sender management

## ApiWeb.V3.Dispatcher.SenderController.create

<a id="opIdApiWeb.V3.Dispatcher.SenderController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/senders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/senders`

*Create new individual sender*

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



## ApiWeb.V3.Dispatcher.SenderController.index

<a id="opIdApiWeb.V3.Dispatcher.SenderController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/senders`

*List individual senders*

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



## ApiWeb.V3.Dispatcher.SenderController.update

<a id="opIdApiWeb.V3.Dispatcher.SenderController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}`

*Update an individual sender*

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



## ApiWeb.V3.Dispatcher.SenderController.show

<a id="opIdApiWeb.V3.Dispatcher.SenderController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}`

*Get an individual sender*

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



## ApiWeb.V3.Dispatcher.SenderController.delete

<a id="opIdApiWeb.V3.Dispatcher.SenderController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}`

*Delete an individual sender*

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

Corporate Sender management

## ApiWeb.V3.Dispatcher.DispatcherController.sender_admins

<a id="opIdApiWeb.V3.Dispatcher.DispatcherController.sender_admins"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/dispatchers/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/dispatchers/senders`

*List sender admins*

List sender admins

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



## ApiWeb.V3.Dispatcher.OrganisationController.organisation_senders

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.organisation_senders"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisation_senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisation_senders`

*List organisation users (Primary and Secondary account) of a company*

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



## ApiWeb.V3.Dispatcher.OrganisationController.create_corporate_sender

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.create_corporate_sender"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations/{id}/senders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations/{id}/senders`

*Create new corporate sender*

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



## ApiWeb.V3.Dispatcher.OrganisationController.corporate_senders

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.corporate_senders"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations/{id}/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations/{id}/senders`

*List client company users (CCUs) of an organisation*

List client company users (CCUs) of an organisation

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



## ApiWeb.V3.Dispatcher.OrganisationController.create

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations`

*Create new organisation*

> Body parameter

```json
{
  "uen_no": "ABC1235M",
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



## ApiWeb.V3.Dispatcher.OrganisationController.index

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations`

*List organisations of a company*

<h3 id="apiweb.v3.dispatcher.organisationcontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.organisationcontroller.index-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherOrganisationsResponse](#schemadispatcherorganisationsresponse)|



## ApiWeb.V3.Dispatcher.OrganisationController.show

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations/{id}`

*Get organisation details*

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




<h1 id="Yojee-APIs-[Dispatcher]-Worker">[Dispatcher] Worker</h1>

Worker management

## ApiWeb.V3.Dispatcher.WorkerController.create

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/workers \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/workers`

*Create a worker*

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
  "name": "Mike Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "email": "mike-driver@yojee.com",
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



## ApiWeb.V3.Dispatcher.WorkerController.index

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers`

*List workers*

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



## ApiWeb.V3.Dispatcher.WorkerController.update

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}`

*Update a worker*

Update a worker

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
  "name": "Mike Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "email": "mike-driver@yojee.com",
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



## ApiWeb.V3.Dispatcher.WorkerController.show

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}`

*Get a worker*

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



## ApiWeb.V3.Dispatcher.WorkerController.delete

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}`

*Delete a worker*

Delete a worker

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



## ApiWeb.V3.Dispatcher.WorkerController.approve

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.approve"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/approve \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/approve`

*Approve a worker*

Approve a worker

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




<h1 id="Yojee-APIs-[Dispatcher]-Order">[Dispatcher] Order</h1>

Order management

## ApiWeb.V3.Dispatcher.OrderController.cancel

<a id="opIdApiWeb.V3.Dispatcher.OrderController.cancel"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}/cancel \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}/cancel`

Cancel an order

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



## ApiWeb.V3.Dispatcher.OrderController.update

<a id="opIdApiWeb.V3.Dispatcher.OrderController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}`

*Update price, external_id, for order*

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



## ApiWeb.V3.Dispatcher.OrderController.show

<a id="opIdApiWeb.V3.Dispatcher.OrderController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}`

*Show an order*

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



## ApiWeb.V3.Dispatcher.OrderController.create

<a id="opIdApiWeb.V3.Dispatcher.OrderController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/orders`

*Create order request*

> Body parameter

```json
{
  "vehicle_type_id": 0,
  "sender_id": 0,
  "price_currency": "string",
  "price_amount": 0,
  "placed_by_user_profile_id": 0,
  "jobs": [
    null
  ],
  "items": [
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



## ApiWeb.V3.Dispatcher.OrderController.index

<a id="opIdApiWeb.V3.Dispatcher.OrderController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/orders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/orders`

*List orders*

<h3 id="apiweb.v3.dispatcher.ordercontroller.index-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|status|query|string|false|an array of status for order, ie: [initial, processing, paid, complete, cancelled]|
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




<h1 id="Yojee-APIs-[Dispatcher]-Batch">[Dispatcher] Batch</h1>

## ApiWeb.V3.Dispatcher.BatchController.create

<a id="opIdApiWeb.V3.Dispatcher.BatchController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/batches \
  -H 'Content-Type: multipart/form-data' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/batches`

*Uploads a file*

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
|company_id|query|integer|false|Company Id|
|body|body|[ApiWeb.V3.Dispatcher.BatchController.create](#schemaapiweb.v3.dispatcher.batchcontroller.create)|false|none|
|» file|body|string(binary)|false|The file to upload|


## ApiWeb.V3.Dispatcher.BatchController.check_status

<a id="opIdApiWeb.V3.Dispatcher.BatchController.check_status"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/batches/check_status \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/batches/check_status`

*Check batch status*

<h3 id="apiweb.v3.dispatcher.batchcontroller.check_status-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|batch_id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|


## ApiWeb.V3.Dispatcher.BatchController.get_order

<a id="opIdApiWeb.V3.Dispatcher.BatchController.get_order"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/batches/get_order \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/batches/get_order`

*Get order detail of batch*

<h3 id="apiweb.v3.dispatcher.batchcontroller.get_order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|batch_id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|




<h1 id="Yojee-APIs-[Dispatcher]-Task">[Dispatcher] Task</h1>

## ApiWeb.V3.Dispatcher.TaskController.update

<a id="opIdApiWeb.V3.Dispatcher.TaskController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/tasks/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/tasks/{id}`

*Update a task*

<h3 id="apiweb.v3.dispatcher.taskcontroller.update-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task ID|
|task_group_id|path|integer|true|Task group ID|



## ApiWeb.V3.Dispatcher.TaskController.delete_task_exception

<a id="opIdApiWeb.V3.Dispatcher.TaskController.delete_task_exception"></a>

> Code samples

```shell

curl -X DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/delete_task_exception \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/delete_task_exception`

Deletes a TaskException associated with a task

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



## ApiWeb.V3.Dispatcher.TaskController.mark_as_failed

<a id="opIdApiWeb.V3.Dispatcher.TaskController.mark_as_failed"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/mark_as_failed \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/mark_as_failed`

Marks a task as failed by creating an associated task exception

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



## ApiWeb.V3.Dispatcher.TaskController.complete

<a id="opIdApiWeb.V3.Dispatcher.TaskController.complete"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/complete \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/complete`

Marks a task as completed by the dispatcher

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




<h1 id="Yojee-APIs-[Dispatcher]-Worker-tasks">[Dispatcher] Worker tasks</h1>

## ApiWeb.V3.Dispatcher.WorkerController.failed

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.failed"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/failed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/failed`

*List failed tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.failed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|



## ApiWeb.V3.Dispatcher.WorkerController.assigned

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.assigned"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/assigned?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/assigned`

*List assigned tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.assigned-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|



## ApiWeb.V3.Dispatcher.WorkerController.completed

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.completed"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/completed`

*List completed tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.completed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|


## ApiWeb.V3.Dispatcher.ManifestController.generate_worker_manifest

<a id="opIdApiWeb.V3.Dispatcher.ManifestController.generate_worker_manifest"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/manifests/worker/{worker_id}

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/manifests/worker/{worker_id}`

*Generate a label on the fly*

<h3 id="apiweb.v3.dispatcher.manifestcontroller.generate_worker_manifest-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|worker_id|query|integer|false|Worker ID|

<h3 id="apiweb.v3.dispatcher.manifestcontroller.generate_worker_manifest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Worker manifest to be downloaded.|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|none|None|



<h1 id="Yojee-APIs-[Dispatcher]-TaskGroup">[Dispatcher] TaskGroup</h1>

## ApiWeb.V3.Dispatcher.TaskGroupController.show

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}`

*Show a task group*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task group ID|



## ApiWeb.V3.Dispatcher.TaskGroupController.unassigned

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.unassigned"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/unassigned?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/unassigned`

*Get unassigned task groups*

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



## ApiWeb.V3.Dispatcher.TaskGroupController.assign_multiple

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.assign_multiple"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/assign_multiple \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/assign_multiple`

*Assign worker multiple task groups*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.assign_multiple-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|ids|query|array[any]|false|array of task_group ids|
|worker_id|query|integer|false|Worker ID|



## ApiWeb.V3.Dispatcher.TaskGroupController.step_items

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.step_items"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/step_items/{step_id}?type=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/step_items/{step_id}`

*Get detailed items about a step in task group*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.step_items-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task Group ID|
|step_id|path|integer|true|Step ID|
|type|query|string|true|Pickup/Dropoff|



## ApiWeb.V3.Dispatcher.TaskGroupController.assigned

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.assigned"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/assigned?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/assigned`

*Get assigned task groups*

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



## ApiWeb.V3.Dispatcher.TaskGroupController.unassign_worker

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.unassign_worker"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/unassign_worker \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/unassign_worker`

*Unassign a worker from a task group*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.unassign_worker-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task Group ID|



## ApiWeb.V3.Dispatcher.TaskGroupController.join_chat

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.join_chat"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/join_chat \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/join_chat`

*Add the dispatcher to a group chat*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.join_chat-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task Group ID|



## ApiWeb.V3.Dispatcher.TaskGroupController.accepted

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.accepted"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/accepted \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/accepted`

*show list of task_groups which is accepted by a worker*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.accepted-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|worker_id|query|integer|false|Worker ID|



## ApiWeb.V3.Dispatcher.TaskGroupController.assign_worker

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.assign_worker"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/assign_worker \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/assign_worker`

*Assign worker for a task group*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.assign_worker-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Task group ID|
|worker_id|query|integer|false|Worker ID|



## ApiWeb.V3.Dispatcher.TaskGroupController.regroup

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.regroup"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/regroup \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/regroup`

*Groups unassigned tasks*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.regroup-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|order|query|boolean|false|Group by Order|
|pickup|query|boolean|false|Group by Pickup|
|dropoff|query|boolean|false|Group by Dropoff|




<h1 id="Yojee-APIs-[Dispatcher]-TaskExceptionReason">[Dispatcher] TaskExceptionReason</h1>

## ApiWeb.V3.Dispatcher.TaskExceptionReasonController.delete

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons/{id}`

Deletes a TaskExceptionReason

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



## ApiWeb.V3.Dispatcher.TaskExceptionReasonController.create

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons`

Creates a TaskExceptionReason

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



## ApiWeb.V3.Dispatcher.TaskExceptionReasonController.index

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons`

Get all task exception reasons for a specific company

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




## ApiWeb.V3.Dispatcher.SearchController.order_item

<a id="opIdApiWeb.V3.Dispatcher.SearchController.order_item"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/order_item?q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/order_item`

*Search for an item*

<h3 id="apiweb.v3.dispatcher.searchcontroller.order_item-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|q|query|string|true|search query|



## ApiWeb.V3.Dispatcher.SearchController.task

<a id="opIdApiWeb.V3.Dispatcher.SearchController.task"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/task?q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/task`

*Search for a task*

<h3 id="apiweb.v3.dispatcher.searchcontroller.task-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|q|query|string|true|search query|



<h1 id="Yojee-APIs-[Dispatcher]-OrderItem">[Dispatcher] OrderItem</h1>

## ApiWeb.V3.Dispatcher.OrderItemController.update

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{id}`

*Update an order item*

> Body parameter

```json
{
  "payload_type": "Updated document",
  "external_customer_id": "changed_external_customer_id",
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



## ApiWeb.V3.Dispatcher.OrderItemController.show

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{id}`

*Show Detail of an Order_item*

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Order Item id|
|delivery_trial_sort|query|string|false|asc or desc for delivery trial sort|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.orderitemcontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OrderItemsShowResponse](#schemaorderitemsshowresponse)|



## ApiWeb.V3.Dispatcher.OrderItemController.index

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items`

*List order_items*

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



<h1 id="Yojee-APIs-[Dispatcher]-SubTask">[Dispatcher] SubTask</h1>

## ApiWeb.V3.Dispatcher.SubTaskController.index

<a id="opIdApiWeb.V3.Dispatcher.SubTaskController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks`

*List sub tasks*

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



## ApiWeb.V3.Dispatcher.SubTaskController.show

<a id="opIdApiWeb.V3.Dispatcher.SubTaskController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks/{id}`

*Get a sub task*

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

## ApiWeb.V3.Dispatcher.SubTaskRuleController.update

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.update"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id}`

*Update a sub task rule*

Update a sub task rule

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



## ApiWeb.V3.Dispatcher.SubTaskRuleController.show

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id}`

*Get a sub task rule*

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



## ApiWeb.V3.Dispatcher.SubTaskRuleController.delete

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id}`

*Delete a sub task rule*

Delete a sub task rule

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



## ApiWeb.V3.Dispatcher.SubTaskRuleController.create

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules`

*Create a sub task rule*

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



## ApiWeb.V3.Dispatcher.SubTaskRuleController.index

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules`

*List sub task rules*

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




<h1 id="Yojee-APIs-[Dispatcher]-Company">[Dispatcher] Company</h1>

## ApiWeb.V3.Dispatcher.CompanyController.vehicle_types

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.vehicle_types"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/vehicle_types \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/vehicle_types`

Get vehicle types which are available for current company

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



## ApiWeb.V3.Dispatcher.CompanyController.show

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/company \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/company`

*Get company info*

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



## ApiWeb.V3.Dispatcher.CompanyController.transportation_companies

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.transportation_companies"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/transportation_companies \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/transportation_companies`

Get transportation companies which works for current company

<h3 id="apiweb.v3.dispatcher.companycontroller.transportation_companies-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.companycontroller.transportation_companies-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CompanyTransportationCompaniesResponse](#schemacompanytransportationcompaniesresponse)|



## ApiWeb.V3.Dispatcher.CompanyController.upload_assets

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.upload_assets"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/company/assets \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/company/assets`

*Upload company assets*

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



## ApiWeb.V3.Dispatcher.CompanyController.update_settings

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.update_settings"></a>

> Code samples

```shell

curl -X PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/company/settings \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/company/settings`

*Update company settings*

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

## ApiWeb.V3.Dispatcher.RoleController.create

<a id="opIdApiWeb.V3.Dispatcher.RoleController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/roles \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/roles`

*Create a role*

Create a role

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



## ApiWeb.V3.Dispatcher.RoleController.index

<a id="opIdApiWeb.V3.Dispatcher.RoleController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/roles \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/roles`

*List roles*

List roles

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



## ApiWeb.V3.Dispatcher.RoleController.update

<a id="opIdApiWeb.V3.Dispatcher.RoleController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/roles/{id} \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/roles/{id}`

*Update a role*

Update a role

> Body parameter

```json
{
  "updated_at": "2018-05-22 09:31:31.464265Z",
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




<h1 id="Yojee-APIs-[Dispatcher]-Region">[Dispatcher] Region</h1>

## ApiWeb.V3.Dispatcher.Network.RegionController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions`

*Create a Region*

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



## ApiWeb.V3.Dispatcher.Network.RegionController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions`

*Get all regions*

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



## ApiWeb.V3.Dispatcher.Network.RegionController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}`

*Updates a Region*

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
|id|path|integer|true|Region Id|
|body|body|[RegionRequest](#schemaregionrequest)|false|Region|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RegionResponse](#schemaregionresponse)|



## ApiWeb.V3.Dispatcher.Network.RegionController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}`

*Gets a Region*

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.show-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Region Id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.show-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RegionResponse](#schemaregionresponse)|



## ApiWeb.V3.Dispatcher.Network.RegionController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}`

*Delete a Region*

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.delete-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|integer|true|Region Id|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.network.regioncontroller.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RegionResponse](#schemaregionresponse)|




<h1 id="Yojee-APIs-[Dispatcher]-Hub">[Dispatcher] Hub</h1>

## ApiWeb.V3.Dispatcher.Network.HubController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}`

*Update a Hub*

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



## ApiWeb.V3.Dispatcher.Network.HubController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}`

*Get a Hub*

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



## ApiWeb.V3.Dispatcher.Network.HubController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}`

*Delete a Hub*

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



## ApiWeb.V3.Dispatcher.Network.HubController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs`

*Create a Hub*

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



## ApiWeb.V3.Dispatcher.Network.HubController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs`

*Get all hubs*

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




<h1 id="Yojee-APIs-[Dispatcher]-Spoke">[Dispatcher] Spoke</h1>

## ApiWeb.V3.Dispatcher.Network.SpokeController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.create"></a>

> Code samples

```shell

curl -X POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes`

*Create a Spoke*

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



## ApiWeb.V3.Dispatcher.Network.SpokeController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.index"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes`

*Get all spokes*

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



## ApiWeb.V3.Dispatcher.Network.SpokeController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.update"></a>

> Code samples

```shell

curl -X PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}`

*Update a Spoke*

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



## ApiWeb.V3.Dispatcher.Network.SpokeController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.show"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}`

*Get a Spoke*

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



## ApiWeb.V3.Dispatcher.Network.SpokeController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.delete"></a>

> Code samples

```shell

curl -X DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}`

*Delete a Spoke*

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




<h1 id="Yojee-APIs-[Dispatcher]-Search">[Dispatcher] Search</h1>

Search

## ApiWeb.V3.Dispatcher.SearchController.sender

<a id="opIdApiWeb.V3.Dispatcher.SearchController.sender"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/sender?q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/sender`

*Search for a sender*

<h3 id="apiweb.v3.dispatcher.searchcontroller.sender-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|q|query|string|true|search query|



## ApiWeb.V3.Dispatcher.SearchController.worker

<a id="opIdApiWeb.V3.Dispatcher.SearchController.worker"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/worker?q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/worker`

*Search for a worker*

<h3 id="apiweb.v3.dispatcher.searchcontroller.worker-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|q|query|string|true|search query|



## ApiWeb.V3.Dispatcher.SearchController.order

<a id="opIdApiWeb.V3.Dispatcher.SearchController.order"></a>

> Code samples

```shell

curl -X GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/order?q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/order`

*Search for an order*

<h3 id="apiweb.v3.dispatcher.searchcontroller.order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|q|query|string|true|search query|


# Schemas

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

<h2 id="tocSdispatcherupdateorderrequest">DispatcherUpdateOrderRequest</h2>

<a id="schemadispatcherupdateorderrequest"></a>

```json
{
  "price_currency": "string",
  "price_amount": 0,
  "external_id": "string"
}

```

*Dispatcher update order request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|price_currency|string|false|none|ISO 4217 code currency, e.g: USD|
|price_amount|number|false|none|Price amount of order, e.g: for 10.12 USD, amount should be 10.|
|external_id|string|false|none|External Order Reference Number|

<h2 id="tocSorderitemsupdaterequest">OrderItemsUpdateRequest</h2>

<a id="schemaorderitemsupdaterequest"></a>

```json
{
  "payload_type": "Updated document",
  "external_customer_id": "changed_external_customer_id",
  "description": "Updated Gift"
}

```

*Order Item Update Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload_type|string|false|none|none|
|external_customer_id|string|false|none|none|
|description|string|false|none|none|

<h2 id="tocSregionresponse">RegionResponse</h2>

<a id="schemaregionresponse"></a>

```json
{
  "data": {
    "tag": "poly5",
    "inserted_at": "2018-05-22 09:31:31.464800Z",
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

<h2 id="tocSauthresponse">AuthResponse</h2>

<a id="schemaauthresponse"></a>

```json
{
  "phone": "+6598765432",
  "email": "bob@mail.com",
  "access_token": "pCVPeEEUuKnM7geUOcSLY2imA5l6YUdjymkApBDAAGY="
}

```

*Auth Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|phone|string|false|none|none|
|email|string|false|none|none|
|access_token|string|false|none|none|

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

<h2 id="tocScreateorderrequest">CreateOrderRequest</h2>

<a id="schemacreateorderrequest"></a>

```json
{
  "vehicle_type_id": 0,
  "sender_id": 0,
  "price_currency": "string",
  "price_amount": 0,
  "placed_by_user_profile_id": 0,
  "jobs": [
    null
  ],
  "items": [
    null
  ]
}

```

*POST body for sender create an order*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|vehicle_type_id|integer|false|none|Id of vehicle type|
|sender_id|integer|false|none|Sender ID|
|price_currency|string|false|none|Order currency|
|price_amount|number|false|none|Order price|
|placed_by_user_profile_id|integer|false|none|user profile id that places the order|
|jobs|[any]|false|none|List of jobs need to be done|
|items|[any]|false|none|List of items to be sent|

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
      "inserted_at": "2018-05-22 09:31:31.458645Z",
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
    "inserted_at": "2018-05-22 09:31:31.465344Z",
    "company_id": 1
  }
}

```

*Hub Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

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
    "name": "Mike Driver",
    "location": {
      "lng": 122.6428429677108,
      "lat": 65.67691234535297
    },
    "inserted_at": "2018-05-22 09:31:31.456895Z",
    "email": "mike-driver@yojee.com",
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
      "inserted_at": "2018-05-22 09:31:31.465464Z",
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
      "inserted_at": "2018-05-22 09:31:31.452439Z",
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
  "name": "Mike Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "email": "mike-driver@yojee.com",
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

<h2 id="tocSdispatchercreateorganisationrequest">DispatcherCreateOrganisationRequest</h2>

<a id="schemadispatchercreateorganisationrequest"></a>

```json
{
  "uen_no": "ABC1235M",
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
  "billing_address": "77 Robinson road, Singapore."
}

```

*Organisation Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uen_no|string|false|none|none|
|title|string|false|none|none|
|sender_type|string|false|none|none|
|phone|string|false|none|none|
|payment_option|string|false|none|none|
|organisation|object|false|none|none|
|name|string|false|none|none|
|gst_no|string|false|none|none|
|email|string|false|none|none|
|billing_address|string|false|none|none|

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
    "inserted_at": "2018-05-22 09:31:31.466022Z",
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

<h2 id="tocSdispatcherupdaterolerequest">DispatcherUpdateRoleRequest</h2>

<a id="schemadispatcherupdaterolerequest"></a>

```json
{
  "updated_at": "2018-05-22 09:31:31.464265Z",
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

<h2 id="tocSdispatcherindexuserresponse">DispatcherIndexUserResponse</h2>

<a id="schemadispatcherindexuserresponse"></a>

```json
{
  "data": [
    {
      "user_profile": 1,
      "phone": "+987654330",
      "name": "Mike Dispatcher",
      "inserted_at": "2018-05-22 09:31:31.455545Z",
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

<h2 id="tocSdispatcherindexroleresponse">DispatcherIndexRoleResponse</h2>

<a id="schemadispatcherindexroleresponse"></a>

```json
{
  "data": [
    {
      "name": "role_1",
      "inserted_at": "2018-05-22 09:31:31.463583Z",
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

<h2 id="tocSdispatcherorganisationresponse">DispatcherOrganisationResponse</h2>

<a id="schemadispatcherorganisationresponse"></a>

```json
{
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
|reg_address|string|false|none|none|
|postal_code|string|false|none|none|
|phone|string|false|none|none|
|name|string|false|none|none|
|id|integer|false|none|none|
|extension|object|false|none|none|
|country|string|false|none|none|
|city|string|false|none|none|

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

<h2 id="tocSdispatcherpartnerresponse">DispatcherPartnerResponse</h2>

<a id="schemadispatcherpartnerresponse"></a>

```json
{
  "data": {
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
  "completion_time": "2018-03-10T03:37:08",
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
|completion_time|string|false|none|none|
|action|string|false|none|none|

<h2 id="tocSorderitemsshowresponse">OrderItemsShowResponse</h2>

<a id="schemaorderitemsshowresponse"></a>

```json
{
  "progress_session": [
    {
      "type": "assigned",
      "status": "blank"
    },
    {
      "type": "started",
      "status": "blank"
    },
    {
      "type": "pickup",
      "status": "blank"
    },
    {
      "type": "dropoff",
      "status": "blank"
    },
    {
      "type": "completed",
      "status": "blank"
    }
  ],
  "message": "detail of an order_item",
  "item_session": {
    "weight": 12,
    "service_type": "same_day",
    "price": "SGD 4",
    "pickup": {
      "worker_phone": "+8469331112302",
      "worker_name": "Khoa Worker",
      "address": "144 Robinson Rd, Singapore 068908"
    },
    "payload_type": "Package",
    "order_reference_number": "N3hqZHZrN2dUYUs0dmVJUUZpeUVpQT09",
    "item_id": 1,
    "dropoff": {
      "worker_phone": "+8469331112302",
      "worker_name": "Khoa Worker",
      "address": "Boon Keng Rd, Singapore"
    },
    "description": "Gift",
    "can_edit": true
  },
  "delivery_trial": [
    {
      "type": "dropoff",
      "task_id": 2,
      "logs": [
        {
          "inserted_at": "2018-03-22T07:52:30.181011",
          "description": "Task created"
        }
      ]
    },
    {
      "type": "pickup",
      "task_id": 1,
      "logs": [
        {
          "inserted_at": "2018-03-22T07:52:30.178729",
          "description": "Task created"
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
|delivery_trial|[any]|false|none|none|

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
  "name": "Mike Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "email": "mike-driver@yojee.com",
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
|name|string|false|none|none|
|location|object|false|none|none|
|email|string|false|none|none|
|current_vehicle_type_id|integer|false|none|none|

<h2 id="tocStaskgroupresponse">TaskGroupResponse</h2>

<a id="schemataskgroupresponse"></a>

```json
{
  "state": "created",
  "price": "SGD 10",
  "id": 1
}

```

*TaskGroup Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|state|string|false|none|none|
|price|string|false|none|none|
|id|integer|false|none|none|

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

<h2 id="tocSdispatchercreateroleresponse">DispatcherCreateRoleResponse</h2>

<a id="schemadispatchercreateroleresponse"></a>

```json
{
  "data": {
    "name": "role_1",
    "inserted_at": "2018-05-22 09:31:31.463811Z",
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

<h2 id="tocSsubtaskrequest">SubTaskRequest</h2>

<a id="schemasubtaskrequest"></a>

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

*SubTask Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|task_id|integer|false|none|none|
|sub_task_rule_id|integer|false|none|none|
|photo|string|false|none|none|
|meta|object|false|none|none|
|event|string|false|none|none|
|completion_time|string|false|none|none|
|action|string|false|none|none|

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
    "inserted_at": "2018-05-22 09:31:31.458251Z",
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

<h2 id="tocSdispatchercreateuserresponse">DispatcherCreateUserResponse</h2>

<a id="schemadispatchercreateuserresponse"></a>

```json
{
  "data": {
    "user_profile": 1,
    "phone": "+987654330",
    "name": "Mike Dispatcher",
    "inserted_at": "2018-05-22 09:31:31.455690Z",
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
    "inserted_at": "2018-05-22 09:31:31.452752Z",
    "access_token": "4h/PrR5vu9uVevso3fNv2RPTLQJech3BJ/pNJhWBnfE="
  }
}

```

*Order Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocSregionsresponse">RegionsResponse</h2>

<a id="schemaregionsresponse"></a>

```json
{
  "data": [
    {
      "tag": "poly5",
      "inserted_at": "2018-05-22 09:31:31.464926Z",
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
      "inserted_at": "2018-05-22 09:31:31.466154Z",
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

<h2 id="tocSdispatcherinforesponse">DispatcherInfoResponse</h2>

<a id="schemadispatcherinforesponse"></a>

```json
{
  "socket_token": "ISO32ADFSANFSKSL",
  "role": "Admin",
  "phone": "(+84)9039233232",
  "name": "John Doe",
  "id": 1,
  "email": "dispatcher@yojee.com",
  "device_token": "AJKS13JD322OAFS",
  "company": {}
}

```

*Sub Task Rule Response*

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

<h2 id="tocScreateorderresponse">CreateOrderResponse</h2>

<a id="schemacreateorderresponse"></a>

```json
{
  "data": {
    "tracking_number": "O-SKGVN25LNEDR",
    "sender_id": 3,
    "price": "SGD 10",
    "placed_by_user_profile_id": 1,
    "number": "TEd1UHI1ekRsa3JaKzRYUGFkMUhXQT09",
    "inserted_at": "2018-02-07T09:38:38.233073",
    "id": 17
  }
}

```

*Create order response*

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

<h2 id="tocScorporatesendersignuprequest">CorporateSenderSignupRequest</h2>

<a id="schemacorporatesendersignuprequest"></a>

```json
{
  "uen_no": "ABC1235M",
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
  "billing_address": "77 Robinson road, Singapore."
}

```

*CorporateSenderSignupRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uen_no|string|false|none|none|
|title|string|false|none|none|
|sender_type|string|false|none|none|
|phone|string|false|none|none|
|payment_option|string|false|none|none|
|password|string|false|none|none|
|organisation|object|false|none|none|
|name|string|false|none|none|
|gst_no|string|false|none|none|
|email|string|false|none|none|
|billing_address|string|false|none|none|

<h2 id="tocScompanytransportationcompaniesresponse">CompanyTransportationCompaniesResponse</h2>

<a id="schemacompanytransportationcompaniesresponse"></a>

```json
{
  "data": [
    {
      "id": 13,
      "external_id": "20600078098",
      "contact_name": "Katie Solis",
      "contact_email": "Ksolis@smk.com.pe",
      "company_id": 2
    }
  ]
}

```

*Transportation Companies Response*

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

<h2 id="tocSdispatchercompanypartnerinfoupdate">DispatcherCompanyPartnerInfoUpdate</h2>

<a id="schemadispatchercompanypartnerinfoupdate"></a>

```json
{
  "contact_phone": "+6591245934",
  "contact_name": "Ralston",
  "contact_email": "ralston@xyz.com"
}

```

*Company Partner Info Update Request*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|contact_phone|string|false|none|none|
|contact_name|string|false|none|none|
|contact_email|string|false|none|none|

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
      "name": "Mike Driver",
      "location": {
        "lng": 122.6428429677108,
        "lat": 65.67691234535297
      },
      "inserted_at": "2018-05-22 09:31:31.457704Z",
      "email": "mike-driver@yojee.com",
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

<h2 id="tocStrackorderresponse">TrackOrderResponse</h2>

<a id="schematrackorderresponse"></a>

```json
{
  "data": {
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
}

```

*Response schema for tracking an order*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|object|false|none|none|

<h2 id="tocStaskgroupsresponse">TaskGroupsResponse</h2>

<a id="schemataskgroupsresponse"></a>

```json
{
  "data": [
    {
      "state": "created",
      "price": "SGD 10",
      "id": 1
    }
  ]
}

```

*TaskGroup Response*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[any]|false|none|List of task group|
