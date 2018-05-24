<h1 id="Yojee-APIs-[Auth]">[Auth]</h1>

Authentication APIs

## ApiWeb.V3.AuthController.signup

<a id="opIdApiWeb.V3.AuthController.signup"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/auth/signup \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST /api/v3/auth/signup`

*This endpoint registers a new user*

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
|body|body|[SignupRequest](#schemasignuprequest)|false|Account info|

> Example responses

> 200 Response

<h3 id="apiweb.v3.authcontroller.signup-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthResponse](#schemaauthresponse)|


## ApiWeb.V3.AuthController.signin

<a id="opIdApiWeb.V3.AuthController.signin"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/auth/signin \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST /api/v3/auth/signin`

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


## ApiWeb.V3.AuthController.corporate_sender_signup

<a id="opIdApiWeb.V3.AuthController.corporate_sender_signup"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/auth/corporate_sender/signup \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST /api/v3/auth/corporate_sender/signup`

*This endpoint registers a new Corporate Sender*

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
|body|body|[CorporateSenderSignupRequest](#schemacorporatesendersignuprequest)|false|Account info|

> Example responses

> 200 Response

<h3 id="apiweb.v3.authcontroller.corporate_sender_signup-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthResponse](#schemaauthresponse)|
