# Map

## Get geocode of an address

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/maps/geocode' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'query: {{query}}' \
  -d 'country_code: {{country_code}}'
```

> The above command returns JSON structured like this:

```json
{
  "zipcode": "",
  "lng": 103.8462451,
  "lat": 1.2754876,
  "country": "Singapore",
  "address": "1 Anson Rd, Singapore"
}
```

This endpoint gets geocode of an address.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/maps/geocode`

### Body

Key | Value | Type
--------- | ------- | -------
query | {{query}} | String
country_code	| {{country_code}} | String

## Get direction information

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/maps/geocode' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'origin: {{origin}}' \
  -d 'mode: {{mode}}' \
  -d 'destination: {{destination}}' \
  -d 'country_iso: {{country_iso}}'
```

> The above command returns JSON structured like this:

```json
{
  "overview_polyline": "{{OVERVIEW_POLYLINE}}",
  "duration": 222,
  "distance": 968,
  "data": "{{DATA}}"
}
```

This endpoint gets direction information.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/maps/geocode`

### Body

Key | Value | Type
--------- | ------- | -------
origin | {{origin}} | String
mode | {{mode}} | String
destination	| {{destination}} | String
country_iso	| {{country_iso}} | String

## Get complete suggestions of an address

```shell
curl -X POST \
  'https://umbrella-demo.yojee.com/api/v3/maps/autocomplete' \
  -H 'Cache-Control: no-cache' \
  -H 'content-type: application/json' \
  -d 'query: {{query}}' \
  -d 'country_iso: {{country_iso}}'
```

> The above command returns JSON structured like this:

```json
{
  "name": "1 Anson Rd",
  "lng": 103.8462451,
  "lat": 1.2754876,
  "address": "1 Anson Rd, Singapore"
}
```

This endpoint gets complete suggestions of an address.

### HTTP Request

`POST https://umbrella-demo.yojee.com/api/v3/maps/autocomplete`

### Body

Key | Value | Type
--------- | ------- | -------
query	| {{query}} | String
country_iso	| {{country_iso}} | String
