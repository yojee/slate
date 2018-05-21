# Launcher

## Create new dispatcher

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/launcher/dispatchers' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
  -d 'phone: {{phone}}' \
  -d 'password: {{password}}' \
  -d 'name: {{name}}' \
  -d 'email: {{email}}' \
  -d 'company_id: {{company_id}}'
```

> The above command returns JSON structured like this:

```json
{
  "user_profile_id": 1,
  "phone": "+9999999999",
  "name": "Yojee",
  "inserted_at": "2018-01-24T08:54:54.204128",
  "id": 1,
  "email": "test@yojee.com",
  "access_token": "{{ACCESS_TOKEN}}"
}
```

This endpoint creates a new dispatcher.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/launcher/dispatchers`

### Body

Key | Value | Type
--------- | ------- | -------
phone	| {{phone}} | String
password | {{password}} | String
name | {{name}} | String
email	| {{email}} | String
company_id	| {{company_id}} | Integer

## Create new company

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/launcher/companies' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json'
  -d 'slug: {{slug}}' \
  -d 'name: {{name}}' \
  -d 'country: {{country}}'
```

> The above command returns JSON structured like this:

```json
{
  "organisation_id": 1,
  "inserted_at": "2018-01-24T08:54:54.204128",
  "id": 1
}
```

This endpoint creates a new company.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/launcher/companies`

### Body

Key | Value | Type
--------- | ------- | -------
slug	| {{slug}} | String
name	| {{name}} | String
country	| {{country}} | String
