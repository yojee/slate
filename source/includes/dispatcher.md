<h1 id="Yojee-APIs-[Dispatcher]">[Dispatcher]</h1>

Dispatcher APIs

## ApiWeb.V3.Dispatcher.InfoController.me

<a id="opIdApiWeb.V3.Dispatcher.InfoController.me"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/info \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/info`

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


<h1 id="Yojee-APIs-[Dispatcher]-Search">[Dispatcher] Search</h1>

Dispatcher APIs for Search

## ApiWeb.V3.Dispatcher.SearchController.sender

<a id="opIdApiWeb.V3.Dispatcher.SearchController.sender"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/search/sender?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/search/sender`

*This endpoint is used to search for a Sender*

<h3 id="apiweb.v3.dispatcher.searchcontroller.sender-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|


## ApiWeb.V3.Dispatcher.SearchController.worker

<a id="opIdApiWeb.V3.Dispatcher.SearchController.worker"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/search/worker?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/search/worker`

*This endpoint is used to search for a Worker*

<h3 id="apiweb.v3.dispatcher.searchcontroller.worker-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|


## ApiWeb.V3.Dispatcher.SearchController.order

<a id="opIdApiWeb.V3.Dispatcher.SearchController.order"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/search/order?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/search/order`

*This endpoint is used to search for an Order*

<h3 id="apiweb.v3.dispatcher.searchcontroller.order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|


## ApiWeb.V3.Dispatcher.SearchController.order_item

<a id="opIdApiWeb.V3.Dispatcher.SearchController.order_item"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/search/order_item?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/search/order_item`

*This endpoint is used to search for an OrderItem*

<h3 id="apiweb.v3.dispatcher.searchcontroller.order_item-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|


## ApiWeb.V3.Dispatcher.SearchController.task

<a id="opIdApiWeb.V3.Dispatcher.SearchController.task"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/search/task?page=1&page_size=25&q=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/search/task`

*This endpoint is used to search for a Task*

<h3 id="apiweb.v3.dispatcher.searchcontroller.task-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|
|q|query|string|true|search query|


<h1 id="Yojee-APIs-[Dispatcher]-User">[Dispatcher] User</h1>

Dispatcher APIs for User Management

## ApiWeb.V3.Dispatcher.UserController.create

<a id="opIdApiWeb.V3.Dispatcher.UserController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/users \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/users`

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


## ApiWeb.V3.Dispatcher.UserController.index

<a id="opIdApiWeb.V3.Dispatcher.UserController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/users \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/users`

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


## ApiWeb.V3.Dispatcher.UserController.update

<a id="opIdApiWeb.V3.Dispatcher.UserController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/users/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/users/{id}`

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

## ApiWeb.V3.Dispatcher.CompanyController.vehicle_types

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.vehicle_types"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/vehicle_types \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/vehicle_types`

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


## ApiWeb.V3.Dispatcher.CompanyController.show

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/company \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/company`

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


## ApiWeb.V3.Dispatcher.CompanyController.transportation_companies

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.transportation_companies"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/transportation_companies \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/transportation_companies`

*This endpoint retrieves a list of TransportationCompanies which work for a Company*

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
# You can also use wget
curl -X POST ///api/v3/dispatcher/company/assets \
  -H 'Content-Type: multipart/form-data' \
  -H 'Accept: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/company/assets`

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


## ApiWeb.V3.Dispatcher.CompanyController.update_settings

<a id="opIdApiWeb.V3.Dispatcher.CompanyController.update_settings"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/company/settings \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/company/settings`

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

## ApiWeb.V3.Dispatcher.RoleController.create

<a id="opIdApiWeb.V3.Dispatcher.RoleController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/roles \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/roles`

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


## ApiWeb.V3.Dispatcher.RoleController.index

<a id="opIdApiWeb.V3.Dispatcher.RoleController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/roles \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/roles`

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


## ApiWeb.V3.Dispatcher.RoleController.update

<a id="opIdApiWeb.V3.Dispatcher.RoleController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH ///api/v3/dispatcher/roles/{id} \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH /api/v3/dispatcher/roles/{id}`

*This endpoint updates a Role*

> Body parameter

```json
{
  "updated_at": "2018-05-23 07:16:40.139117Z",
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


<h1 id="Yojee-APIs-[Dispatcher]-Partner">[Dispatcher] Partner</h1>

Dispatcher APIs for Partner Management

## ApiWeb.V3.Dispatcher.PartnerController.reject_invite

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.reject_invite"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/partners/{cip}/reject_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/partners/{cip}/reject_invite`

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


## ApiWeb.V3.Dispatcher.PartnerController.sent_invites

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.sent_invites"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/partners/invites/sent?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/partners/invites/sent`

*This endpoint retrieves a list of sent partnership requests*

<h3 id="apiweb.v3.dispatcher.partnercontroller.sent_invites-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.sent_invites-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartners](#schemadispatcherpartners)|


## ApiWeb.V3.Dispatcher.PartnerController.cancel_invite

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.cancel_invite"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/partners/{cip}/cancel_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/partners/{cip}/cancel_invite`

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


## ApiWeb.V3.Dispatcher.PartnerController.update_partnership_info

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.update_partnership_info"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/partnership_info \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/partnership_info`

*This endpoint updates a Partner's information*

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


## ApiWeb.V3.Dispatcher.PartnerController.partnership_info

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.partnership_info"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/partnership_info \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/partnership_info`

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


## ApiWeb.V3.Dispatcher.PartnerController.send_invite

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.send_invite"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/partners/{cip}/send_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/partners/{cip}/send_invite`

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


## ApiWeb.V3.Dispatcher.PartnerController.received_invites

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.received_invites"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/partners/invites/received?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/partners/invites/received`

*This endpoint retrieves a list of received partnership requests*

<h3 id="apiweb.v3.dispatcher.partnercontroller.received_invites-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|

> Example responses

> 200 Response

<h3 id="apiweb.v3.dispatcher.partnercontroller.received_invites-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DispatcherPartners](#schemadispatcherpartners)|


## ApiWeb.V3.Dispatcher.PartnerController.accept_invite

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.accept_invite"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/partners/{cip}/accept_invite \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/partners/{cip}/accept_invite`

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


## ApiWeb.V3.Dispatcher.PartnerController.show

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/partners/{cip} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/partners/{cip}`

*This endpoint retrieves information about a Partner*

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


## ApiWeb.V3.Dispatcher.PartnerController.index

<a id="opIdApiWeb.V3.Dispatcher.PartnerController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/partners?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/partners`

*This endpoint retrieves a list of Partners belonging to a Company*

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


<h1 id="Yojee-APIs-[Dispatcher]-Network">[Dispatcher] Network</h1>

Dispatcher APIs for Network Management

## ApiWeb.V3.Dispatcher.Network.SpokeController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/network/spokes \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/network/spokes`

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


## ApiWeb.V3.Dispatcher.Network.SpokeController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/network/spokes \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/network/spokes`

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


## ApiWeb.V3.Dispatcher.Network.HubController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH ///api/v3/dispatcher/network/hubs/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH /api/v3/dispatcher/network/hubs/{id}`

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


## ApiWeb.V3.Dispatcher.Network.HubController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/network/hubs/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/network/hubs/{id}`

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


## ApiWeb.V3.Dispatcher.Network.HubController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE ///api/v3/dispatcher/network/hubs/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE /api/v3/dispatcher/network/hubs/{id}`

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


## ApiWeb.V3.Dispatcher.Network.HubController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/network/hubs \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/network/hubs`

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


## ApiWeb.V3.Dispatcher.Network.HubController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.HubController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/network/hubs \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/network/hubs`

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


## ApiWeb.V3.Dispatcher.Network.RegionController.create

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/network/regions \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/network/regions`

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


## ApiWeb.V3.Dispatcher.Network.RegionController.index

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/network/regions \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/network/regions`

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


## ApiWeb.V3.Dispatcher.Network.SpokeController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH ///api/v3/dispatcher/network/spokes/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH /api/v3/dispatcher/network/spokes/{id}`

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


## ApiWeb.V3.Dispatcher.Network.SpokeController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/network/spokes/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/network/spokes/{id}`

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


## ApiWeb.V3.Dispatcher.Network.SpokeController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.SpokeController.delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE ///api/v3/dispatcher/network/spokes/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE /api/v3/dispatcher/network/spokes/{id}`

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


## ApiWeb.V3.Dispatcher.Network.RegionController.update

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH ///api/v3/dispatcher/network/regions/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH /api/v3/dispatcher/network/regions/{id}`

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


## ApiWeb.V3.Dispatcher.Network.RegionController.show

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/network/regions/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/network/regions/{id}`

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


## ApiWeb.V3.Dispatcher.Network.RegionController.delete

<a id="opIdApiWeb.V3.Dispatcher.Network.RegionController.delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE ///api/v3/dispatcher/network/regions/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE /api/v3/dispatcher/network/regions/{id}`

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

## ApiWeb.V3.Dispatcher.SenderController.create

<a id="opIdApiWeb.V3.Dispatcher.SenderController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/senders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/senders`

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


## ApiWeb.V3.Dispatcher.SenderController.index

<a id="opIdApiWeb.V3.Dispatcher.SenderController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/senders`

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


## ApiWeb.V3.Dispatcher.SenderController.update

<a id="opIdApiWeb.V3.Dispatcher.SenderController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH ///api/v3/dispatcher/senders/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH /api/v3/dispatcher/senders/{id}`

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


## ApiWeb.V3.Dispatcher.SenderController.show

<a id="opIdApiWeb.V3.Dispatcher.SenderController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/senders/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/senders/{id}`

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


## ApiWeb.V3.Dispatcher.SenderController.delete

<a id="opIdApiWeb.V3.Dispatcher.SenderController.delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE ///api/v3/dispatcher/senders/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE /api/v3/dispatcher/senders/{id}`

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

## ApiWeb.V3.Dispatcher.DispatcherController.sender_admins

<a id="opIdApiWeb.V3.Dispatcher.DispatcherController.sender_admins"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/dispatchers/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/dispatchers/senders`

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


## ApiWeb.V3.Dispatcher.OrganisationController.organisation_senders

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.organisation_senders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/organisation_senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/organisation_senders`

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


## ApiWeb.V3.Dispatcher.OrganisationController.create_corporate_sender

<a id="opIdApiWeb.V3.Dispatcher.OrganisationController.create_corporate_sender"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/organisations/{id}/senders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/organisations/{id}/senders`

*This endpoint creates a new Corporate Sender*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/organisations/{id}/senders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/organisations/{id}/senders`

*This endpoint retrieves a list of Corporate Senders*

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
# You can also use wget
curl -X POST ///api/v3/dispatcher/organisations \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/organisations`

*This endpoint creates a new Organisation Sender*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/organisations?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/organisations`

*This endpoint retrieves a list of Organisations managed by a Dispatcher*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/organisations/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/organisations/{id}`

*This endpoint retrieves information about an Organisation*

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

Dispatcher APIs for Worker Management

## ApiWeb.V3.Dispatcher.WorkerController.failed

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.failed"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/workers/{id}/tasks/failed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/workers/{id}/tasks/failed`

*This endpoint retrieves a list of a Worker's failed Tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.failed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|


## ApiWeb.V3.Dispatcher.WorkerController.create

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/workers \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/workers`

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/workers?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/workers`

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


## ApiWeb.V3.Dispatcher.WorkerController.assigned

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.assigned"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/workers/{id}/tasks/assigned?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/workers/{id}/tasks/assigned`

*This endpoint retrieves a list of a Worker's assigned Tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.assigned-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|


## ApiWeb.V3.Dispatcher.WorkerController.update

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/workers/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/workers/{id}`

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/workers/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/workers/{id}`

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


## ApiWeb.V3.Dispatcher.WorkerController.delete

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE ///api/v3/dispatcher/workers/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE /api/v3/dispatcher/workers/{id}`

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


## ApiWeb.V3.Dispatcher.WorkerController.approve

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.approve"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/workers/{id}/approve \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/workers/{id}/approve`

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


## ApiWeb.V3.Dispatcher.WorkerController.completed

<a id="opIdApiWeb.V3.Dispatcher.WorkerController.completed"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/workers/{id}/tasks/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/workers/{id}/tasks/completed`

*This endpoint retrieves a list of a Worker's completed Tasks*

<h3 id="apiweb.v3.dispatcher.workercontroller.completed-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|id|path|string|true|Worker ID|
|page|query|integer|true|Page number|
|page_size|query|integer|true|Page size|


<h1 id="Yojee-APIs-[Dispatcher]-Docs">[Dispatcher] Docs</h1>

## ApiWeb.V3.Dispatcher.ManifestController.generate_worker_manifest

<a id="opIdApiWeb.V3.Dispatcher.ManifestController.generate_worker_manifest"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/manifests/worker/{worker_id}

```

`GET /api/v3/dispatcher/manifests/worker/{worker_id}`

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


<h1 id="Yojee-APIs-[Dispatcher]-Order">[Dispatcher] Order</h1>

Dispatcher APIs for Order Management

## ApiWeb.V3.Dispatcher.OrderController.cancel

<a id="opIdApiWeb.V3.Dispatcher.OrderController.cancel"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/orders/{number}/cancel \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/orders/{number}/cancel`

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


## ApiWeb.V3.Dispatcher.OrderController.update

<a id="opIdApiWeb.V3.Dispatcher.OrderController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/orders/{number} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/orders/{number}`

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


## ApiWeb.V3.Dispatcher.OrderController.show

<a id="opIdApiWeb.V3.Dispatcher.OrderController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/orders/{number} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/orders/{number}`

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


## ApiWeb.V3.Dispatcher.OrderController.create

<a id="opIdApiWeb.V3.Dispatcher.OrderController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/orders`

*This endpoint creates an Order*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/orders?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/orders`

*This endpoint retrieves a list of Orders*

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


<h1 id="Yojee-APIs-[Dispatcher]-OrderItem">[Dispatcher] OrderItem</h1>

Dispatcher APIs for OrderItem Management

## ApiWeb.V3.Dispatcher.OrderItemController.update

<a id="opIdApiWeb.V3.Dispatcher.OrderItemController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH ///api/v3/dispatcher/order_items/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PATCH /api/v3/dispatcher/order_items/{id}`

*This endpoint is used by a Dispatcher to update an OrderItem*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/order_items/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/order_items/{id}`

*This endpoint retrieves information about an OrderItem*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/order_items?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/order_items`

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

## ApiWeb.V3.Dispatcher.BatchController.create

<a id="opIdApiWeb.V3.Dispatcher.BatchController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/batches \
  -H 'Content-Type: multipart/form-data' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/batches`

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
|company_id|query|integer|false|Company Id|
|body|body|[ApiWeb.V3.Dispatcher.BatchController.create](#schemaapiweb.v3.dispatcher.batchcontroller.create)|false|none|
|» file|body|string(binary)|false|The file to upload|


## ApiWeb.V3.Dispatcher.BatchController.check_status

<a id="opIdApiWeb.V3.Dispatcher.BatchController.check_status"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/batches/check_status \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/batches/check_status`

*This endpoint checks the status of a Batch*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/batches/get_order \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/batches/get_order`

*This endpoint retrieves detailed information about a Batch*

<h3 id="apiweb.v3.dispatcher.batchcontroller.get_order-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|batch_id|query|integer|false|Batch Id|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|


<h1 id="Yojee-APIs-[Dispatcher]-TaskGroup">[Dispatcher] TaskGroup</h1>

Dispatcher APIs for TaskGroup Management

## ApiWeb.V3.Dispatcher.TaskGroupController.show

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/task_groups/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/task_groups/{id}`

*This endpoint retrieves information about a TaskGroup*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/task_groups/unassigned?page=1&page_size=25 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/task_groups/unassigned`

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


## ApiWeb.V3.Dispatcher.TaskGroupController.assign_multiple

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.assign_multiple"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/task_groups/assign_multiple \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/task_groups/assign_multiple`

*This endpoint assigns multiple TaskGroups to a Worker*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/task_groups/{id}/step_items/{step_id}?type=string \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/task_groups/{id}/step_items/{step_id}`

*This endpoint retrieves detailed information for Items in a TaskGroup*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/task_groups/assigned?page=1&page_size=25 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/task_groups/assigned`

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


## ApiWeb.V3.Dispatcher.TaskGroupController.unassign_worker

<a id="opIdApiWeb.V3.Dispatcher.TaskGroupController.unassign_worker"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/task_groups/{id}/unassign_worker \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/task_groups/{id}/unassign_worker`

*This endpoint unassigns a TaskGroup from a Worker*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/task_groups/{id}/join_chat \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/task_groups/{id}/join_chat`

*This endpoint adds a Dispatcher to a chat group*

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
# You can also use wget
curl -X GET ///api/v3/dispatcher/task_groups/accepted \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/task_groups/accepted`

*This endpoint retrieves a Worker's list of accepted TaskGroups*

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
# You can also use wget
curl -X PUT ///api/v3/dispatcher/task_groups/{id}/assign_worker \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/task_groups/{id}/assign_worker`

*This endpoint assigns a TaskGroup to a Worker*

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
# You can also use wget
curl -X POST ///api/v3/dispatcher/task_groups/regroup \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/task_groups/regroup`

*This endpoint groups unassigned Tasks into TaskGroups*

<h3 id="apiweb.v3.dispatcher.taskgroupcontroller.regroup-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|
|order|query|boolean|false|Group by Order|
|pickup|query|boolean|false|Group by Pickup|
|dropoff|query|boolean|false|Group by Dropoff|



<h1 id="Yojee-APIs-[Dispatcher]-Task">[Dispatcher] Task</h1>

Dispatcher APIs for Task Management

## ApiWeb.V3.Dispatcher.TaskController.update

<a id="opIdApiWeb.V3.Dispatcher.TaskController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/task_groups/{task_group_id}/tasks/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/task_groups/{task_group_id}/tasks/{id}`

*This endpoint updates a Task's details*

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
# You can also use wget
curl -X DELETE ///api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/delete_task_exception \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE /api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/delete_task_exception`

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


## ApiWeb.V3.Dispatcher.TaskController.mark_as_failed

<a id="opIdApiWeb.V3.Dispatcher.TaskController.mark_as_failed"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/mark_as_failed \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/mark_as_failed`

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


## ApiWeb.V3.Dispatcher.TaskController.complete

<a id="opIdApiWeb.V3.Dispatcher.TaskController.complete"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/complete \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/task_groups/{task_group_id}/task/{id}/complete`

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

## ApiWeb.V3.Dispatcher.TaskExceptionReasonController.delete

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE ///api/v3/dispatcher/task_exception_reasons/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE /api/v3/dispatcher/task_exception_reasons/{id}`

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


## ApiWeb.V3.Dispatcher.TaskExceptionReasonController.create

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/dispatcher/task_exception_reasons \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/task_exception_reasons`

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


## ApiWeb.V3.Dispatcher.TaskExceptionReasonController.index

<a id="opIdApiWeb.V3.Dispatcher.TaskExceptionReasonController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/task_exception_reasons \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/task_exception_reasons`

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

## ApiWeb.V3.Dispatcher.SubTaskController.index

<a id="opIdApiWeb.V3.Dispatcher.SubTaskController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/order_items/{order_item_id}/sub_tasks \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/order_items/{order_item_id}/sub_tasks`

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


## ApiWeb.V3.Dispatcher.SubTaskController.show

<a id="opIdApiWeb.V3.Dispatcher.SubTaskController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/order_items/{order_item_id}/sub_tasks/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/order_items/{order_item_id}/sub_tasks/{id}`

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

## ApiWeb.V3.Dispatcher.SubTaskRuleController.update

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.update"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/dispatcher/sub_task_rules/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/dispatcher/sub_task_rules/{id}`

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


## ApiWeb.V3.Dispatcher.SubTaskRuleController.show

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.show"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/sub_task_rules/{id} \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/sub_task_rules/{id}`

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


## ApiWeb.V3.Dispatcher.SubTaskRuleController.delete

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE ///api/v3/dispatcher/sub_task_rules/{id} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`DELETE /api/v3/dispatcher/sub_task_rules/{id}`

*This endpoint deletes a SubTaskRule*

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
# You can also use wget
curl -X POST ///api/v3/dispatcher/sub_task_rules \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/dispatcher/sub_task_rules`

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


## ApiWeb.V3.Dispatcher.SubTaskRuleController.index

<a id="opIdApiWeb.V3.Dispatcher.SubTaskRuleController.index"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/dispatcher/sub_task_rules?page=1&page_size=10 \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/dispatcher/sub_task_rules`

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
