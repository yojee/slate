# Authorisation

## Sign up a new individual sender

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/auth/signup' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'sender_type: {{sender_type}}' \
  -d 'phone: {{phone}}' \
  -d 'password: {{password}}' \
  -d 'name: {{name}}' \
  -d 'email: {{email}}' \
  -d 'billing_address: {{billing_address}}' \
  -d 'account_type: {{account_type}}'
```

> The above command returns JSON structured like this:

```json
{
  "phone": "+6598765432",
  "email": "test@yojee.com",
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint signs up a new individual sender.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/auth/signup`

### Body

Key | Value | Type
--------- | ------- | -------
sender_type | {{sender_type}} | String
phone	| {{phone}} | String
password | {{password}} | String
name | {{name}} | String
email	| {{email}} | String
billing_address	| {{billing_address}} | String
account_type	| {{account_type}} | String

## Sign in as a sender

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/auth/signin' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'password: {{password}}' \
  -d 'email: {{email}}'
```

> The above command returns JSON structured like this:

```json
{
  "phone": "+6598765432",
  "email": "test@yojee.com",
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint signs up as a sender.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/auth/signin`

### Body

Key | Value | Type
--------- | ------- | -------
password | {{password}} | String
email	| {{email}} | String

## Sign up a new corporate sender

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/auth/corporate_sender/signup' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'uen_no: {{uen_no}}' \
  -d 'title: {{title}}' \
  -d 'sender_type: {{sender_type}}' \
  -d 'phone: {{phone}}' \
  -d 'payment_option: {{payment_option}}' \
  -d 'password: {{password}}' \
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
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint signs up a new corporate sender.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/auth/corporate_sender/signup`

### Body

Key | Value | Type
--------- | ------- | -------
uen_no | {{uen_no}} | String
title	| {{title}} | String
sender_type	| {{sender_type}} | String
phone	| {{phone}} | String
payment_option	| {{payment_option}} | String
password | {{password}} | String
organisation | {{reg_address}} | String
 | {{postal_code}} | String
 | {{phone}}  | String
 | {{name}} | String
 | {{country}} | String
 | {{city}} | String
name | {{name}} | String
gst_no | {{gst_no}} | String
email	| {{email}} | String
billing_address	| {{billing_address}} | String
