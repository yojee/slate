# Dispatcher

## Get current dispatcher user

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/info' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "socket_token": "{{SOCKET_TOKEN}}",
  "role": "Admin",
  "phone": "(+84)9039233232",
  "name": "John Doe",
  "id": 1,
  "email": "test@yojee.com",
  "device_token": "{{DEVICE_TOKEN}}",
  "company": "{{COMPANY}}"
}
```

This endpoint retrieves current dispatcher user.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/info`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Create new company user

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/users' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'phone: {{phone}}' \
  -d 'password: {{password}}' \
  -d 'name: {{name}}' \
  -d 'email: {{email}}'
```

> The above command returns JSON structured like this:

```json
{
  "user_profile": 1,
  "phone": "+987654330",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.638969Z",
  "email": "test@yojee.com",
  "company_id": 1
}
```

This endpoint creates a new company user.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/users`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
phone | {{phone}} | String
password  | {{password}} | String
name | {{name}} | Number
email | {{email}} | Number

## List company users

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/users' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "user_profile": 1,
  "phone": "+987654330",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.638805Z",
  "email": "test@yojee.com",
  "company_id": 1
}
```

This endpoint retrieves company users.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/users`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## List partners of a company

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/partners' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "postal_code": "111111",
  "partnership_type": "downstream",
  "country": "Singapore",
  "contact_phone": "+6599999999",
  "contact_name": "Yojee",
  "contact_email": "test@yojee.com",
  "company_name": "Yojee",
  "city": "Singapore",
  "cip": "{{CIP}}",
  "address": "144 Robinson road, Singapore."
}
```

This endpoint retrieves partners of a company.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/partners`

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

## Create a partner

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/partners' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'postal_code: {{postal_code}}' \
  -d 'partnership_type: {{partnership_type}}' \
  -d 'country: {{country}}' \
  -d 'contact_phone: {{contact_phone}}' \
  -d 'contact_name: {{contact_name}}' \
  -d 'contact_email: {{contact_email}}' \
  -d 'company_name: {{company_name}}' \
  -d 'city: {{city}}' \
  -d 'address: {{address}}'
```

> The above command returns JSON structured like this:

```json
{
  "postal_code": "111111",
  "partnership_type": "downstream",
  "country": "Singapore",
  "contact_phone": "+6599999999",
  "contact_name": "Yojee",
  "contact_email": "test@yojee.com",
  "company_name": "Yojee",
  "city": "Singapore",
  "cip": "{{CIP}}",
  "address": "144 Robinson road, Singapore."
}
```

This endpoint create a partner.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/partners`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
postal_code | {{postal_code}} | Number
partnership_type | {{partnership_type}} | String
country | {{country}} | String
contact_phone | {{contact_phone}} | String
contact_name | {{contact_name}} | String
contact_email  | {{contact_email}} | String
company_name | {{company_name}} | String
city | {{city}} | String
address | {{address}} | String

## Update company user

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/users/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'phone: {{phone}}' \
  -d 'password: {{password}}' \
  -d 'name: {{name}}'
```

> The above command returns JSON structured like this:

```json
{
  "user_profile": 1,
  "phone": "+987654330",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.638805Z",
  "email": "test@yojee.com",
  "company_id": 1
}
```

This endpoint updates a company user.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/users/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
phone | {{phone}} | String
password | {{password}} | String
name | {{name}} | Number

## Update company partner info

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/company_partner_info' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'contact_phone: {{contact_phone}}' \
  -d 'contact_name: {{contact_name}}' \
  -d 'contact_email: {{contact_email}}'
```

> The above command returns JSON structured like this:

```json
{
  "postal_code": "111111",
  "partnership_type": "downstream",
  "country": "Singapore",
  "contact_phone": "+6599999999",
  "contact_name": "Yojee",
  "contact_email": "test@yojee.com",
  "company_name": "Yojee",
  "city": "Singapore",
  "cip": "{{CIP}}",
  "address": "144 Robinson road, Singapore."
}
```

This endpoint updates company partner info.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/company_partner_info`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
contact_phone | {{contact_phone}} | String
contact_name  | {{contact_name}} | String
contact_email | {{contact_email}} | String

## Invite a partner company

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/send_invite' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint invites a partner company.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/send_invite`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
cip  | Partner CIP
partnership_type | Partnership type

## Get partner details

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "user_profile": 1,
  "phone": "+987654330",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.638805Z",
  "email": "test@yojee.com",
  "company_id": 1
}
```

This endpoint retrieves a partner details.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
cip  | Partner CIP

## Accept a partner company invite

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/accept_invite' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message" : "ok"
}
```

This endpoint accepts a partner company invite.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/accept_invite`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
cip  | Partner CIP

## Declines a partner company invite

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/reject_invite' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message" : "ok"
}
```

This endpoint declines a partner company invite.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/partners/{cip}/reject_invite`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
cip  | Partner CIP

## Create new individual sender

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/senders' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'sender_type: {{sender_type}}' \
  -d 'phone: {{phone}}' \
  -d 'password: {{password}}' \
  -d 'name: {{name}}' \
  -d 'email: {{email}}' \
  -d 'billing_address: {{billing_address}}'
```

> The above command returns JSON structured like this:

```json
{
  "sender_user_profile_id": 1,
  "sender_type": "individual",
  "phone": "+8412345611",
  "password": "{{PASSWORD}}",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.641243Z",
  "id": 5,
  "email": "test@yojee.com",
  "billing_address": "144 Robinson Road"
}
```

This endpoint creates a new individual sender.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/senders`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
sender_type | {{sender_type}} | String
phone | {{phone}} | String
password  | {{password}} | String
name | {{name}} | String
email | {{email}} | String
billing_address  | {{billing_address}} | String

## List individual sender

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/senders' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "sender_user_profile_id": 1,
  "sender_type": "individual",
  "phone": "+8412345611",
  "password": "{{PASSWORD}}",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.641243Z",
  "id": 5,
  "email": "test@yojee.com",
  "billing_address": "144 Robinson Road"
}
```

This endpoint retrieves individual senders.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/senders`

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
sender_type | Sender type (individual/organisation) | optional
q | Search by sender name or organisation name | optional

## Update an individual sender

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'phone: {{phone}}' \
  -d 'name: {{name}}' \
  -d 'email: {{email}}' \
  -d 'billing_address: {{billing_address}}'
```

> The above command returns JSON structured like this:

```json
{
  "sender_user_profile_id": 1,
  "sender_type": "individual",
  "phone": "+8412345611",
  "password": "{{PASSWORD}}",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.641243Z",
  "id": 5,
  "email": "test@yojee.com",
  "billing_address": "144 Robinson Road"
}
```

This endpoint updates an individual sender.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
phone | {{phone}} | String
name | {{name}} | String
email | {{email}} | String
billing_address  | {{billing_address}} | String

## Update an individual sender

```shell
curl -X PATCH \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'phone: {{phone}}' \
  -d 'name: {{name}}' \
  -d 'email: {{email}}' \
  -d 'billing_address: {{billing_address}}'
```

> The above command returns JSON structured like this:

```json
{
  "sender_user_profile_id": 1,
  "sender_type": "individual",
  "phone": "+8412345611",
  "password": "{{PASSWORD}}",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.641243Z",
  "id": 5,
  "email": "test@yojee.com",
  "billing_address": "144 Robinson Road"
}
```

This endpoint updates an individual sender.

### HTTP Request

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
phone | {{phone}} | String
name | {{name}} | String
email | {{email}} | String
billing_address  | {{billing_address}} | String

### Parameters

Parameter | Description
--------- | -----------
id  | Sender ID

## Get an individual sender

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "sender_user_profile_id": 1,
  "sender_type": "individual",
  "phone": "+8412345611",
  "password": "{{PASSWORD}}",
  "name": "Yojee",
  "inserted_at": "2018-05-19 05:05:11.641243Z",
  "id": 5,
  "email": "test@yojee.com",
  "billing_address": "144 Robinson Road"
}
```

This endpoint retrieves an individual sender.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Sender ID

## Delete an individual sender

```shell
curl -X DELETE \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint deletes an individual sender.

### HTTP Request

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/senders/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Sender ID

## List sender admins

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/senders' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
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
```

This endpoint retrieves sender admins.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/senders`

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

## List organisation users (Primary and Secondary account) of a company

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/organisation_senders' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "user_profile_id": 1,
  "name": "ABC"
}
```

This endpoint retrieves organisation users (Primary and Secondary account) of a company.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/organisation_senders`

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

## Create new corporate sender

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/organisations/{id}/senders' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'title: {{title}}' \
  -d 'sender_type: {{sender_type}}' \
  -d 'phone: {{phone}}' \
  -d 'name: {{name}}' \
  -d 'email: {{email}}' \
  -d 'billing_address: {{billing_address}}'
```

> The above command returns JSON structured like this:

```json
{
  "phone": "+6598765432",
  "email": "test@yojee.com",
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint creates a new corporate sender.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/organisations/{id}/senders`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
title | {{title}} | String
sender_type | {{sender_type}} | String
phone | {{phone}} | String
name | {{name}} | String
email | {{email}} | String
billing_address  | {{billing_address}} | String

### Parameters

Parameter | Description
--------- | -----------
id  | Organisation ID

## List client company users (CCUs) of an organisation

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/organisations/{id}/senders' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "user_profile_id": 1,
  "name": "ABC"
}
```

This endpoint retrieves client company users (CCUs) of an organisation.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/organisations/{id}/senders`

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
id  | Organisation ID | -

## Create new organisation

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'uen_no: {{uen_no}}' \
  -d 'title: {{title}}' \
  -d 'sender_type: {{sender_type}}' \
  -d 'phone: {{phone}}' \
  -d 'payment_option: {{payment_option}}' \
  -d 'organisation: {{organisation}}' \
  -d 'name: {{name}}' \
  -d 'gst_no: {{gst_no}}' \
  -d 'email: {{email}}' \
  -d 'organisation: {{organisation}}'
```

> The above command returns JSON structured like this:

```json
{
  "phone": "+6598765432",
  "email": "test@yojee.com",
  "access_token": "pCVPeEEUuKnM7geUOcSLY2imA5l6YUdjymkApBDAAGY="
}
```

This endpoint creates a new organisation.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/dispatcher/organisations`

### Body

Key | Value | Type
--------- | ------- | -------
uen_no | {{uen_no}} | String
title	| {{title}} | String
sender_type	| {{sender_type}} | String
phone	| {{phone}} | String
payment_option	| {{payment_option}} | String
organisation	| {{reg_address}} | String
 | {{postal_code}} | String
 | {{phone}}  | String
 | {{name}} | String
 | {{country}} | String
 | {{city}} | String
name | {{name}} | String
gst_no	| {{gst_no}} | String
email	| {{email}} | String
billing_address	| {{billing_address}} | String

## List organisations of a company

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
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
```

This endpoint retrieves organisations of a company.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations`

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

## Get organisation details

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

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

This endpoint retrieves organisation details.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/organisations/{id}`

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
id  | Organisation ID

## Create new worker

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'vehicle_type_ids: {{vehicle_type_ids}}' \
  -d 'tester: {{tester}}' \
  -d 'phone: {{phone}}' \
  -d 'password: {{password}}' \
  -d 'otp_token: {{otp_token}}' \
  -d 'name: {{name}}' \
  -d 'location: {{location}}' \
  -d 'email: {{email}}' \
  -d 'current_vehicle_type_id: {{current_vehicle_type_id}}'
```

> The above command returns JSON structured like this:

```json
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
  "password": "{{PASSWORD}}",
  "otp_token": "1122334455",
  "name": " Driver",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "inserted_at": "2018-05-19 05:05:11.640034Z",
  "email": "test@yojee.com",
  "distance_away": 1100,
  "current_vehicle_type_id": 1,
  "company_id": 1,
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint creates a new worker.

### HTTP Request

`POST https://umbrella-demo.yojee.com/v3/api/dispatcher/workers`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
vehicle_type_ids | {{vehicle_type_ids}} | Integer
tester	| {{tester}} | String
phone	| {{phone}} | String
password	| {{password}} | String
otp_token	| {{otp_token}} | String
name	 | {{name}} | String
location  | {{lng}} | Number
 | {{city}} | Number
email	| {{email}} | String
current_vehicle_type_id	| {{current_vehicle_type_id}} | Integer
billing_address	| {{billing_address}} | String

## List workers

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
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
  "password": "{{PASSWORD}}",
  "otp_token": "1122334455",
  "name": "Yojee",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "inserted_at": "2018-05-19 05:05:11.640034Z",
  "email": "test@yojee.com",
  "distance_away": 1100,
  "current_vehicle_type_id": 1,
  "company_id": 1,
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint retrieves a list of workers.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/workers`

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
sort | The field to sort (id/distance/etc.) | optional
order | Asc/Desc | optional
status | Driver status | optional
from | From timestamp | optional
to | To timestamp | optional
name | Worker name | optional
target_location | Geospatial coordinates of a location | optional
with_in | Length of range (with target_location at center) in meters | optional

## Update a worker

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
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
  "password": "{{PASSWORD}}",
  "otp_token": "1122334455",
  "name": "Yojee",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "inserted_at": "2018-05-19 05:05:11.640034Z",
  "email": "test@yojee.com",
  "distance_away": 1100,
  "current_vehicle_type_id": 1,
  "company_id": 1,
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint updates a worker.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/v3/api/dispatcher/workers`

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
sort | The field to sort (id/distance/etc.) | optional
order | Asc/Desc | optional
status | Driver status | optional
from | From timestamp | optional
to | To timestamp | optional
name | Worker name | optional
target_location | Geospatial coordinates of a location | optional
with_in | Length of range (with target_location at center) in meters | optional
id  | Worker ID | -

## Get a worker information

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
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
  "password": "{{PASSWORD}}",
  "otp_token": "1122334455",
  "name": "Yojee",
  "location": {
    "lng": 122.6428429677108,
    "lat": 65.67691234535297
  },
  "inserted_at": "2018-05-19 05:05:11.640034Z",
  "email": "test@yojee.com",
  "distance_away": 1100,
  "current_vehicle_type_id": 1,
  "company_id": 1,
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint retrieves a worker information.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Worker ID

## Delete a worker

```shell
curl -X DELETE \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint deletes a worker.

### HTTP Request

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Worker ID

## Approve a worker

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/approve' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint approves a worker.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/approve`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Worker ID

## Cancel an order

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}/cancel' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint cancels an order.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}/cancel`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
number  | Order number

## Update price, external_id, external_customer_id for order

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'\
  -d 'price_currency: {{price_currency}}' \
  -d 'price_amount: {{price_amount}}' \
  -d 'external_id: {{external_id}}' \
  -d 'external_customer_id: {{external_customer_id}}'

```

> The above command returns JSON structured like this:

```json
{
  "tracking_number": "{{TRACKING_NUMBER}}",
  "sender_id": 3,
  "price": "SGD 10",
  "placed_by_user_profile_id": 1,
  "number": "{{NUMBER}}",
  "inserted_at": "2018-02-07T09:38:38.233073",
  "id": 17
}
```

This endpoint updates price, external_id, external_customer_id for order.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
price_currency | {{price_currency}} | String
price_amount	| {{price_amount}} | Number
external_id	| {{external_id}} | Integer
external_customer_id	| {{external_customer_id}} | Integer

### Parameters

Parameter | Description
--------- | -----------
number  | Order number

## Show an order

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'price_currency: {{price_currency}}' \
  -d 'price_amount: {{price_amount}}' \
  -d 'external_id: {{external_id}}' \
  -d 'external_customer_id: {{external_customer_id}}'
```

> The above command returns JSON structured like this:

```json
{
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
  "number": "{{number}}",
  "inserted_at": "2018-05-19 05:05:11.636386Z",
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint retrieves an order.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/orders/{number}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
price_currency | {{price_currency}} | String
price_amount	| {{price_amount}} | Number
external_id	| {{external_id}} | String
external_customer_id	| {{external_customer_id}} | String

### Parameters

Parameter | Description
--------- | -----------
number  | Order number

## Create order request

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/orders' \
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
  "tracking_number": "{{TRACKING_NUMBER}}",
  "sender_id": 3,
  "price": "SGD 10",
  "placed_by_user_profile_id": 1,
  "number": "{{number}}",
  "inserted_at": "2018-02-07T09:38:38.233073",
  "id": 17
}
```

This endpoint creates order request.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/orders`

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

## List orders

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/orders' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "tracking_number": "O-M1RHTJHJZGKX",
  "status": "created",
  "sender_type": "organisation",
  "sender_id": 1,
  "price_currency": "SGD",
  "price_amount": 0,
  "number": "{{number}}",
  "inserted_at": "2018-05-19 05:05:11.636204Z",
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint retrieves a list of orders.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/v3/dispatcher/orders`

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
status | An array of status for order, ie: [initial, processing, paid, complete, cancelled] | optional
from | From timestamp | optional
to | To timestamp | optional
name | Worker name | optional
sender_id | Sender ID | optional
order | Asc/Desc | optional

## Update a task

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/tasks/{id}' \
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

This endpoint updates a task.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/tasks/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Task ID
task_group_id  | Task group ID

## Delete a TaskException associated with a task

```shell
curl -X DELETE \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/delete_task_exception' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint deletes a TaskException associated with a task.

### HTTP Request

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/delete_task_exception`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Task ID
task_group_id  | Task group ID

## Marks a task as failed by creating an associated task exception

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/mark_as_failed' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'description: {{description}}'
```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint marks a task as failed by creating an associated task exception.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/mark_as_failed`

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
id  | Task ID
task_group_id  | Task group ID

## Marks a task as completed by the dispatcher

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/complete' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "message": "ok"
}
```

This endpoint marks a task as completed by the dispatcher.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/complete`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Task ID
task_group_id  | Task group ID

## Show a task group

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint retrieves a task group.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
task_group_id  | Task group ID

## Assign multiple task groups to worker

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/assign_multiple' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint assigns multiple task groups to worker.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/assign_multiple`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description | Default Value
--------- | ----------- | -----------
id | An array of task_group_id for task group | optional
worker_id | Worker ID | optional

## Get detailed items about a step in task group

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/step_items/{step_id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint retrieves detailed items about a step in task group.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/step_items/{step_id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
type | Pickup/Dropoff
id  | Task group ID
step_id  | Step ID

## Get assigned task groups

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/assigned' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint retrieves assigned task groups.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/assigned`

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
status | An array of status for order, ie: [initial, processing, paid, complete, cancelled] | Assigned
worker_type | Worker contract type (employee/freelancer) | optional
current_vehicle_type_id | Worker vehicle type id | optional
task_group_ids | An array of task_group_id for task group | optional
from | From timestamp | optional
to | To timestamp | optional

## Unassign a worker from a task group

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/unassign_worker' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint unassigns a worker from a task group.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/unassign_worker`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Task group ID

## Add the dispatcher to a group chat

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/join_chat' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint adds the dispatcher to a group chat.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/join_chat`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Task group ID

## Show list of task_groups which is accepted by a worker

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/accepted' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint retrieves a list of task_groups which is accepted by a worker.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/accepted`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
worker_id | Worker ID

## Assign worker to a task group

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/assign_worker' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint assigns worker to a task group.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/{id}/assign_worker`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
worker_id | Worker ID
id  | Task group ID

## Groups unassigned tasks

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/regroup' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "accepted_time": "nil",
  "allocation_mode": "1",
  "assigned_time": "nil",
  "associated_task_group": "nil",
  "auto_accept": "false",
  "broadcast_state": "created",
  "calculated_description": "nil",
  "company": "company",
  "company_id": 34847,
  "completion_time": "nil",
  "estimation_time": "nil",
  "id": "19171",
  "inserted_at": "2018-05-21 16:23:59.052429",
  "price": "nil",
  "state": "unassigned",
  "tasks": {
    "{{order_item_step}}" :
    {
      "order_step" : "{{order_step}}"
    }
  },
  "updated_at": "2018-05-21 16:23:59.052429",
  "worker": "nil",
  "worker_id": "nil"
}
```

This endpoint groups unassigned tasks.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_groups/regroup`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
order | Group by Order
pickup | Group by Pickup
dropoff | Group by Dropoff

## Creates a TaskExceptionReason

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'description: {{description}}'
```

> The above command returns JSON structured like this:

```json
{
  "description": "Sender not available",
  "company_id": 1
}
```

This endpoint creates a TaskExceptionReason.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
description | {{description}} | String

## Get all task exception reasons for a specific company

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "description": "Sender not available",
  "company_id": 1
}
```

This endpoint retrieves all task exception reasons for a specific company.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Deletes a TaskExceptionReason

```shell
curl -X DELETE \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "description": "Sender not available",
  "company_id": 1
}
```

This endpoint deletes a TaskExceptionReason.

### HTTP Request

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/task_exception_reasons/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Task exception reason ID

## Get vehicle types which are available for current company

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/vehicle_types' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "name": "Pedestrian",
  "id": 1
},
{
  "name": "Bicycle",
  "id": 2
}
```

This endpoint retrieves vehicle types which are available for current company.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/vehicle_types`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Get company info

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/company' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
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
  "events": [
    "pickup_completed",
    "dropoff_completed"
  ],
  "actions": [
    "upload_photo",
    "upload_signature"
  ]
}
```

This endpoint retrieves company info.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/company`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Get transportation companies which works for current company

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/transportation_companies' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "id": 13,
  "external_id": "20600078098",
  "contact_name": "Katie Solis",
  "contact_email": "Ksolis@smk.com.pe",
  "company_id": 2
}
```

This endpoint retrieves transportation companies which works for current company.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/transportation_companies`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Upload company assets

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/company/assets' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -F 'file: {{file}}' \
  -F 'file_type: {{file_type}}'
```

> The above command returns JSON structured like this:

```json
{
  "data": "https://s3.us-east-1.amazonaws.com/test/uploads/companies/334/334_logo.png"
}
```

This endpoint uploads company assets.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/company/assetss`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
file | The file to upload
file_type | The file type

## Upload company settings

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/company/settings' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'settings: {{settings}}'
```

> The above command returns JSON structured like this:

```json
{
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
  "events": [
    "pickup_completed",
    "dropoff_completed"
  ],
  "actions": [
    "upload_photo",
    "upload_signature"
  ]
}
```

This endpoint uploads company settings.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/company/settings`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
settings | {{delivery_options}} : {{time_window}} : {{pickup}} | Timestamp
 | {{delivery_options}} : {{time_window}} : {{dropoff}} | Timestamp
 | {{pickup_allowance}} | Integer
 | {{max_weight}} | Integer
 | {{advance_bookings}} | Integer

## Creates a Region

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'tag: {{tag}}' \
  -d 'description: {{description}}' \
  -d 'coordinates: {{coordinates}}' \
  -d 'color: {{color}}'
```

> The above command returns JSON structured like this:

```json
{
  "tag": "poly5",
  "inserted_at": "2018-05-19 05:05:11.646174Z",
  "description": "Sample Region",
  "coordinates": [
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
```

This endpoint creates a Region.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
tag | {{tag}} | String
description | {{description}} | String
coordinates | {{lng}} | Number
 | {{lat}} | Number
color | {{color}} | String

## Get all regions

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "tag": "poly5",
  "inserted_at": "2018-05-19 05:05:11.646174Z",
  "description": "Sample Region",
  "coordinates": [
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
```

This endpoint gets all regions.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Updates a Region

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'tag: {{tag}}' \
  -d 'description: {{description}}' \
  -d 'coordinates: {{coordinates}}' \
  -d 'color: {{color}}'
```

> The above command returns JSON structured like this:

```json
{
  "tag": "poly5",
  "inserted_at": "2018-05-19 05:05:11.646174Z",
  "description": "Sample Region",
  "coordinates": [
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
```

This endpoint updates a Region.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
tag | {{tag}} | String
description | {{description}} | String
coordinates | {{lng}} | Number
 | {{lat}} | Number
color | {{color}} | String

### Parameters

Parameter | Description
--------- | -----------
id  | Region ID

## Updates a Region

```shell
curl -X PATCH \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'tag: {{tag}}' \
  -d 'description: {{description}}' \
  -d 'coordinates: {{coordinates}}' \
  -d 'color: {{color}}'
```

> The above command returns JSON structured like this:

```json
{
  "tag": "poly5",
  "inserted_at": "2018-05-19 05:05:11.646174Z",
  "description": "Sample Region",
  "coordinates": [
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
```

This endpoint updates a Region.

### HTTP Request

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
tag | {{tag}} | String
description | {{description}} | String
coordinates | {{lng}} | Number
 | {{lat}} | Number
color | {{color}} | String

### Parameters

Parameter | Description
--------- | -----------
id  | Region ID

## Get all regions

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "tag": "poly5",
  "inserted_at": "2018-05-19 05:05:11.646174Z",
  "description": "Sample Region",
  "coordinates": [
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
```

This endpoint gets all regions.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Region ID

## Delete all regions

```shell
curl -X DELETE \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "tag": "poly5",
  "inserted_at": "2018-05-19 05:05:11.646174Z",
  "description": "Sample Region",
  "coordinates": [
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
```

This endpoint deletes all regions.

### HTTP Request

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/regions/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Region ID

## Creates a Spoke

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'properties: {{properties}}' \
  -d 'pessimistic_estimated_duration: {{pessimistic_estimated_duration}}' \
  -d 'origin_hub_id: {{origin_hub_id}}' \
  -d 'optimistic_estimated_duration: {{optimistic_estimated_duration}}' \
  -d 'name: {{name}}' \
  -d 'modality: {{modality}}' \
  -d 'destination_hub_id: {{destination_hub_id}}'
```

> The above command returns JSON structured like this:

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "inserted_at": "2018-05-19 05:02:57.208315Z",
  "destination_hub_id": 2,
  "company_id": 1
}
```

This endpoint creates a Spoke.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
properties | {{properties}} | String
pessimistic_estimated_duration | {{pessimistic_estimated_duration}} | Integer
origin_hub_id | {{origin_hub_id}} | Integer
optimistic_estimated_duration | {{optimistic_estimated_duration}} | Integer
name | {{name}} | String
modality | {{modality}} | String
destination_hub_id | {{destination_hub_id}} | Integer

## Get all spokes

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "inserted_at": "2018-05-19 05:02:57.208315Z",
  "destination_hub_id": 2,
  "company_id": 1
}
```

This endpoint gets all spokes.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Updates a Spoke

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'properties: {{properties}}' \
  -d 'pessimistic_estimated_duration: {{pessimistic_estimated_duration}}' \
  -d 'origin_hub_id: {{origin_hub_id}}' \
  -d 'optimistic_estimated_duration: {{optimistic_estimated_duration}}' \
  -d 'name: {{name}}' \
  -d 'modality: {{modality}}' \
  -d 'destination_hub_id: {{destination_hub_id}}'

```

> The above command returns JSON structured like this:

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "inserted_at": "2018-05-19 05:02:57.208315Z",
  "destination_hub_id": 2,
  "company_id": 1
}
```

This endpoint updates a Spoke.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
properties | {{properties}} | String
pessimistic_estimated_duration | {{pessimistic_estimated_duration}} | Integer
origin_hub_id | {{origin_hub_id}} | Integer
optimistic_estimated_duration | {{optimistic_estimated_duration}} | Integer
name | {{name}} | String
modality | {{modality}} | String
destination_hub_id | {{destination_hub_id}} | Integer

### Parameters

Parameter | Description
--------- | -----------
id  | Spoke ID

## Updates a Spoke

```shell
curl -X PATCH \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'properties: {{properties}}' \
  -d 'pessimistic_estimated_duration: {{pessimistic_estimated_duration}}' \
  -d 'origin_hub_id: {{origin_hub_id}}' \
  -d 'optimistic_estimated_duration: {{optimistic_estimated_duration}}' \
  -d 'name: {{name}}' \
  -d 'modality: {{modality}}' \
  -d 'destination_hub_id: {{destination_hub_id}}'
```

> The above command returns JSON structured like this:

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "inserted_at": "2018-05-19 05:02:57.208315Z",
  "destination_hub_id": 2,
  "company_id": 1
}
```

This endpoint updates a Spoke.

### HTTP Request

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
properties | {{properties}} | String
pessimistic_estimated_duration | {{pessimistic_estimated_duration}} | Integer
origin_hub_id | {{origin_hub_id}} | Integer
optimistic_estimated_duration | {{optimistic_estimated_duration}} | Integer
name | {{name}} | String
modality | {{modality}} | String
destination_hub_id | {{destination_hub_id}} | Integer

### Parameters

Parameter | Description
--------- | -----------
id  | Spoke ID

## Get all spokes

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "inserted_at": "2018-05-19 05:02:57.208315Z",
  "destination_hub_id": 2,
  "company_id": 1
}
```

This endpoint gets all spokes.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Spoke ID

## Delete all spokes

```shell
curl -X DELETE \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "properties": {},
  "pessimistic_estimated_duration": 40,
  "origin_hub_id": 1,
  "optimistic_estimated_duration": 40,
  "name": "spoker",
  "modality": "road",
  "inserted_at": "2018-05-19 05:02:57.208315Z",
  "destination_hub_id": 2,
  "company_id": 1
}
```

This endpoint deletes all spokes.

### HTTP Request

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/spokes/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Spoke ID

## Creates a Hub

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'regions: {{regions}}' \
  -d 'properties: {{properties}}' \
  -d 'name: {{name}}' \
  -d 'location: {{location}}'
```

> The above command returns JSON structured like this:

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
  },
  "inserted_at": "2018-05-19 05:02:57.207612Z",
  "company_id": 1
}
```

This endpoint creates a Hub.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
regions | {{regions}} | String
properties | {{description}} | String
| {{address}} | String
name | {{name}} | String
location | {{lng}} | Number
| {{lat}} | Number

## Updates a Hub

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'regions: {{regions}}' \
  -d 'properties: {{properties}}' \
  -d 'name: {{name}}' \
  -d 'location: {{location}}'
```

> The above command returns JSON structured like this:

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
  },
  "inserted_at": "2018-05-19 05:02:57.207612Z",
  "company_id": 1
}
```

This endpoint updates a Hub.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
regions | {{regions}} | String
properties | {{description}} | String
 | {{address}} | String
name | {{name}} | String
location | {{lng}} | Number
 | {{lat}} | Number

### Parameters

Parameter | Description
--------- | -----------
id  | Hub ID

## Get all hubs

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

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
  },
  "inserted_at": "2018-05-19 05:02:57.207612Z",
  "company_id": 1
}
```

This endpoint gets all hubs.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Updates a Hub

```shell
curl -X PATCH \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'regions: {{regions}}' \
  -d 'properties: {{properties}}' \
  -d 'name: {{name}}' \
  -d 'location: {{location}}'
```

> The above command returns JSON structured like this:

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
  },
  "inserted_at": "2018-05-19 05:02:57.207612Z",
  "company_id": 1
}
```

This endpoint updates a Hub.

### HTTP Request

`PATCH https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
regions | {{regions}} | String
properties | {{description}} | String
 | {{address}} | String
name | {{name}} | String
location | {{lng}} | Number
 | {{lat}} | Number

### Parameters

Parameter | Description
--------- | -----------
id  | Hub ID

## Get all hubs

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

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
  },
  "inserted_at": "2018-05-19 05:02:57.207612Z",
  "company_id": 1
}
```

This endpoint gets all hubs.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Hub ID

## Delete all hubs

```shell
curl -X DELETE \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

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
  },
  "inserted_at": "2018-05-19 05:02:57.207612Z",
  "company_id": 1
}
```

This endpoint deletes all hubs.

### HTTP Request

`DELETE https://umbrella-demo.yojee.com/api/v3/dispatcher/network/hubs/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id  | Hub ID

## Search for a sender

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/search/sender' \
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

This endpoint searches for a sender.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/sender`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
q | Search query

## Search for a worker

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/search/worker' \
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

This endpoint searches for a worker.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/worker`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
q | Search query

## Search for an order

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/search/order' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{
  "tracking_number": "O-ABCDEFGHIJKL",
  "sender_id": 1,
  "price": "SGD 10",
  "placed_by_user_profile_id": 1,
  "number": "ABc1DEF1ekRsa3JaKzRYUGFkMUhXQT09",
  "inserted_at": "2018-01-01T00:00:00.000000",
  "id": 17
}
```

This endpoint searches for an order.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/order`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
q | Search query

## Search for an order item

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/search/order_item' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
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
```

This endpoint searches for an order item.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/order_item`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
q | Search query

## Search for a task

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/search/task' \
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

This endpoint searches for a task.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/search/task`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
q | Search query

## List failed task

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/failed' \
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
  "event": "pickup_failed",
  "completion_time": "2018-03-10T03:37:08",
  "action": "upload_photo"
}
```

This endpoint retrieves a list of failed task.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/failed`

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
id | Worker ID | -

## List assigned task

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/assigned' \
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
  "event": "assigned",
  "completion_time": "2018-03-10T03:37:08",
  "action": "upload_photo"
}
```

This endpoint retrieves a list of assigned task.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/assigned`

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
id | Worker ID | -

## List completed task

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/completed' \
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
  "event": "delivered",
  "completion_time": "2018-03-10T03:37:08",
  "action": "upload_photo"
}
```

This endpoint retrieves a list of completed task.

### HTTP Request

`GET https://umbrella-demo.yojee.com/api/v3/dispatcher/workers/{id}/tasks/completed`

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
id | Worker ID | -

## List order items

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
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
```

This endpoint retrieves a list of order items.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/order_items`

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
status | Status of the order item | optional
service_type | Service type of the order item | optional
order_id | Order ID | optional
from | From timestamp | optional
to | To timestamp | optional

## Show detail of an order item

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

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

This endpoint retrieves a list of order items.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/order_items/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
delivery_trial_sort | Asc/Desc
id | Order item ID

## Update an order item

```shell
curl -X PATCH \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'payload_type: {{payload_type}}' \
  -d 'description: {{description}}'
```

> The above command returns JSON structured like this:

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

This endpoint updates an order item.

### HTTP Request

`PATCH https://umbrella-demo.yojee.com/v3/api/dispatcher/order_items/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
payload_type | {{payload_type}} | String
description | {{description}} | String

### Parameters

Parameter | Description
--------- | -----------
id | Order item ID

## Update an order item

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'payload_type: {{payload_type}}' \
  -d 'description: {{description}}'
```

> The above command returns JSON structured like this:

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

This endpoint updates an order item.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/v3/api/dispatcher/order_items/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
payload_type | {{payload_type}} | String
description | {{description}} | String

### Parameters

Parameter | Description
--------- | -----------
id | Order item ID

## List sub tasks

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "task_id": 103,
  "sub_task_rule_id": 21,
  "photo": "signature.jpg",
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

This endpoint retrieves a list of sub tasks.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/order_items/{order_item_id}/sub_tasks`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
order_item_id | Order item ID

## Get a sub task

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/{order_item_id}/sub_tasks/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "task_id": 103,
  "sub_task_rule_id": 21,
  "photo": "signature.jpg",
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

This endpoint retrieves a sub task.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/order_items/{order_item_id}/sub_tasks/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id | Sub task ID
order_item_id | Order item ID

## List sub task rules

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "photo_type": "signature",
  "photo_title": "Signature of client",
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}
```

This endpoint retrieves a list of sub task rules.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/sub_task_rules`

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

## Create a sub task rule

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'photo_type: {{photo_type}}' \
  -d 'photo_title: {{photo_title}}' \
  -d 'event: {{event}}' \
  -d 'company_id: {{company_id}}' \
  -d 'action: {{action}}'

```

> The above command returns JSON structured like this:

```json
{
  "photo_type": "signature",
  "photo_title": "Signature of client",
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}
```

This endpoint creates a sub task rule.

### HTTP Request

`POST https://umbrella-demo.yojee.com/v3/api/dispatcher/sub_task_rules`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
photo_type | {{photo_type}} | String
photo_title | {{photo_title}} | String
event | {{event}} | String
company_id | {{company_id}} | Integer
action | {{action}} | String

## Get a sub task rule

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "photo_type": "signature",
  "photo_title": "Signature of client",
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}
```

This endpoint retrieves a sub task rule.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/sub_task_rules/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id | Sub task rule ID

## Update a sub task rule

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'photo_type: {{photo_type}}' \
  -d 'photo_title: {{photo_title}}' \
  -d 'event: {{event}}' \
  -d 'company_id: {{company_id}}' \
  -d 'action: {{action}}'

```

> The above command returns JSON structured like this:

```json
{
  "photo_type": "signature",
  "photo_title": "Signature of client",
  "event": "pickup_completed",
  "company_id": 1,
  "action": "upload_photo"
}
```

This endpoint updates a sub task rule.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/v3/api/dispatcher/sub_task_rules/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
photo_type | {{photo_type}} | String
photo_title | {{photo_title}} | String
event | {{event}} | String
company_id | {{company_id}} | Integer
action | {{action}} | String

### Parameters

Parameter | Description
--------- | -----------
id | Sub task rule ID

## Delete a sub task rule

```shell
curl -X DELETE \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/sub_task_rules/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "message": "OK"
}
```

This endpoint deletes a sub task rule.

### HTTP Request

`DELETE https://umbrella-demo.yojee.com/v3/api/dispatcher/sub_task_rules/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
id | Sub task rule ID

## Get order detail of batch

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/batches/get_order' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

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

This endpoint retrieves order detail of batch.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/batches/get_order`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
batch_id | Batch ID

## Get batch status

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/order_items/batches/check_status' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'

```

> The above command returns JSON structured like this:

```json
{
  "id": "{{BATCH_ID}}",
  "company_id": "{{COMPANY_ID}}",
  "status": "{{STATUS}}",
  "tracking_number": "{{TRACKING_NUMBER}}",
  "uploader_id": "{{UPLOADER_ID}}",
  "file": "{{FILE}}"
}
```

This endpoint retrieves batch status.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/batches/check_status`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Parameters

Parameter | Description
--------- | -----------
batch_id | Batch ID

## Upload a file

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/batches' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -F 'file : {{FILE}}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "{{BATCH_ID}}",
  "company_id": "{{COMPANY_ID}}",
  "status": "{{STATUS}}",
  "tracking_number": "{{TRACKING_NUMBER}}",
  "uploader_id": "{{UPLOADER_ID}}",
  "file": "{{FILE}}"
}
```

This endpoint retrieves batch status.

### HTTP Request

`POST https://umbrella-demo.yojee.com/v3/api/dispatcher/batches`

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
company_id | Company ID

## Create a role

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/roles' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'name: {{name}}' \
  -d 'company_id: {{company_id}}' \
  -d 'access_map: {{access_map}}'
```

> The above command returns JSON structured like this:

```json
{  
  "name": "role_1",
  "inserted_at": "2018-05-19 05:02:57.206135Z",
  "company_id": 123,
  "access_map": {
    "sender": {
      "add": true
      }
    }
}
```

This endpoint creates a role.

### HTTP Request

`POST https://umbrella-demo.yojee.com/v3/api/dispatcher/roles`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
name | {{name}} | String
company_id | {{company_id}} | Integer
access_map | {{access_map}} | Array

## List roles

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/roles' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{  
  "name": "role_1",
  "inserted_at": "2018-05-19 05:02:57.206135Z",
  "company_id": 123,
  "access_map": {
    "sender": {
      "add": true
      }
    }
}
```

This endpoint retrieves a list of roles.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/roles`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

## Update a role

```shell
curl -X PUT \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/roles/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'name: {{name}}' \
  -d 'company_id: {{company_id}}' \
  -d 'access_map: {{access_map}}'
```

> The above command returns JSON structured like this:

```json
{  
  "name": "role_1",
  "inserted_at": "2018-05-19 05:02:57.206135Z",
  "company_id": 123,
  "access_map": {
    "sender": {
      "add": true
      }
    }
}
```

This endpoint updates a role.

### HTTP Request

`PUT https://umbrella-demo.yojee.com/v3/api/dispatcher/roles/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
name | {{name}} | String
company_id | {{company_id}} | Integer
access_map | {{access_map}} | Array

### Parameters

Parameter | Description
--------- | -----------
id | Role ID

## Update a role

```shell
curl -X PATCH \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/roles/{id}' \
  -H 'ACCESS_TOKEN: {{ACCESS_TOKEN}}' \
  -H 'COMPANY_SLUG: {{COMPANY_SLUG}}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'name: {{name}}' \
  -d 'company_id: {{company_id}}' \
  -d 'access_map: {{access_map}}'
```

> The above command returns JSON structured like this:

```json
{  
  "name": "role_1",
  "inserted_at": "2018-05-19 05:02:57.206135Z",
  "company_id": 123,
  "access_map": {
    "sender": {
      "add": true
      }
    }
}
```

This endpoint updates a role.

### HTTP Request

`PATCH https://umbrella-demo.yojee.com/v3/api/dispatcher/roles/{id}`

### Headers

Key | Value
--------- | -------
ACCESS_TOKEN | {{ACCESS_TOKEN}}
COMPANY_SLUG | {{COMPANY_SLUG}}

### Body

Key | Value | Type
--------- | ------- | -------
name | {{name}} | String
company_id | {{company_id}} | Integer
access_map | {{access_map}} | Array

### Parameters

Parameter | Description
--------- | -----------
id | Role ID

## Generate a label on the fly

```shell
curl -X GET \
  'https://umbrella-demo.yojee.com/api/v3/dispatcher/manifests/worker/{worker_id}' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
```

> The above command returns JSON structured like this:

```json
{  
  "message": "Worker manifest to be downloaded."
}
```

This endpoint generates a label on the fly.

### HTTP Request

`GET https://umbrella-demo.yojee.com/v3/api/dispatcher/manifests/worker/{worker_id}`

### Parameters

Parameter | Description
--------- | -----------
worker_id | Worker ID
