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
