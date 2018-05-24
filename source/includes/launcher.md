<h1 id="Yojee-APIs-[Launcher]">[Launcher]</h1>

Launcher APIs

## ApiWeb.V3.Launcher.DispatcherController.create

<a id="opIdApiWeb.V3.Launcher.DispatcherController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/launcher/dispatchers \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST /api/v3/launcher/dispatchers`

*This endpoint creates a new Dispatcher*

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
# You can also use wget
curl -X POST ///api/v3/launcher/companies \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

`POST /api/v3/launcher/companies`

*This endpoint creates a new Company*

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
