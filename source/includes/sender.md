<h1 id="Yojee-APIs-[Sender]">[Sender]</h1>

Sender APIs

## ApiWeb.V3.Sender.InfoController.me

<a id="opIdApiWeb.V3.Sender.InfoController.me"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/sender/info \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/sender/info`

*This endpoint retrieves a Sender's infomation*

<h3 id="apiweb.v3.sender.infocontroller.me-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|ACCESS_TOKEN|header|string|true|access token|
|COMPANY_SLUG|header|string|true|company slug|


<h1 id="Yojee-APIs-[Sender]-Order">[Sender] Order</h1>

Sender Order APIs

## ApiWeb.V3.Sender.OrderController.cancel

<a id="opIdApiWeb.V3.Sender.OrderController.cancel"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT ///api/v3/sender/orders/{number}/cancel \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`PUT /api/v3/sender/orders/{number}/cancel`

*This endpoint cancels an Order*

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
# You can also use wget
curl -X GET ///api/v3/sender/orders/completed?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/sender/orders/completed`

*This endpoint retrieves all completed Orders of a Sender*

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
# You can also use wget
curl -X POST ///api/v3/sender/orders/{number}/payments \
  -H 'Content-Type: application/json' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/sender/orders/{number}/payments`

*This endpoint creates a payment request*

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
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Payment successful|None|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Payment failed!|None|


## ApiWeb.V3.Sender.OrderController.create

<a id="opIdApiWeb.V3.Sender.OrderController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST ///api/v3/sender/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/sender/orders`

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
# You can also use wget
curl -X GET ///api/v3/sender/orders/{number} \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/sender/orders/{number}`

*This endpoint retrieves information about an Order*

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
# You can also use wget
curl -X GET ///api/v3/sender/orders/ongoing?page=1&page_size=10 \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/sender/orders/ongoing`

*This endpoint retrieves all ongoing Orders of a Sender*

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

Sender Batch APIs

## ApiWeb.V3.Sender.BatchController.check_status

<a id="opIdApiWeb.V3.Sender.BatchController.check_status"></a>

> Code samples

```shell
# You can also use wget
curl -X GET ///api/v3/sender/batches/check_status \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`GET /api/v3/sender/batches/check_status`

*This endpoint checks the status of a Batch*

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
# You can also use wget
curl -X POST ///api/v3/sender/batches \
  -H 'Content-Type: multipart/form-data' \
  -H 'ACCESS_TOKEN: string' \
  -H 'COMPANY_SLUG: string'

```

`POST /api/v3/sender/batches`

*This endpoint is used by a Sender to upload a batch file*

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
