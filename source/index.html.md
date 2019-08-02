---
title: GWS
language_tabs:
  - ruby: Ruby
  - python: Python
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<h1 id="gws">GWS v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

# Introduction
What does your API do?
ProductAvailability 
Product Catalog

# Overview
Things that the developers should know about

# Authentication
What is the preferred way of using the API?
Basic Authentication

# Error Codes
What errors and status codes can a user expect?

# Rate limit
Is there a limit to the number of requests an user can send?

Base URLs:

* <a href="http://ws.specialized.com/soa-infra/resources/GWS">http://ws.specialized.com/soa-infra/resources/GWS</a>

* <a href="https://ws.specialized.com/soa-infra/resources/GWS">https://ws.specialized.com/soa-infra/resources/GWS</a>

# Authentication

- HTTP Authentication, scheme: basic 

<h1 id="gws-product">product</h1>

## serial number search

<a id="opIdWSBC614119599N"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'string'
}

result = RestClient.get 'http://ws.specialized.com/soa-infra/resources/GWS/searchserial/product/v1/WSBC601079664N',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'string'
}

r = requests.get('http://ws.specialized.com/soa-infra/resources/GWS/searchserial/product/v1/WSBC601079664N', params={

}, headers = headers)

print r.json()

```

`GET /searchserial/product/v1/WSBC601079664N`

This is an OSB service

<h3 id="serial-number-search-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept|header|string|true|none|

<h3 id="serial-number-search-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
auth
</aside>

## product catalog

<a id="opIdProductCatalogGet"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'string'
}

result = RestClient.get 'http://ws.specialized.com/soa-infra/resources/GWS/Product/catalog',
  params: {
  'Lang' => 'string',
'ItemsPerPage' => 'integer(int32)',
'Username' => 'string',
'Country' => 'string',
'PageIndex' => 'integer(int32)',
'SourceApp' => 'string',
'IncludePrice' => 'string',
'ResultFormat' => 'string',
'Sku' => 'string',
'AccountNum' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'string'
}

r = requests.get('http://ws.specialized.com/soa-infra/resources/GWS/Product/catalog', params={
  'Lang': 'string',  'ItemsPerPage': '0',  'Username': 'string',  'Country': 'string',  'PageIndex': '0',  'SourceApp': 'string',  'IncludePrice': 'string',  'ResultFormat': 'string',  'Sku': 'string',  'AccountNum': 'string'
}, headers = headers)

print r.json()

```

`GET /Product/catalog`

TODO: Add Description

<h3 id="product-catalog-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Lang|query|string|true|none|
|ItemsPerPage|query|integer(int32)|true|none|
|Username|query|string|true|none|
|Country|query|string|true|none|
|PageIndex|query|integer(int32)|true|none|
|SourceApp|query|string|true|none|
|IncludePrice|query|string|true|none|
|ResultFormat|query|string|true|none|
|Sku|query|string|true|none|
|AccountNum|query|string|true|none|
|Accept|header|string|true|none|

<h3 id="product-catalog-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
auth
</aside>

## stock availability

<a id="opIdProductAvailabilityAvailabilityPost"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'string',
  'Content-Type' => 'string'
}

result = RestClient.post 'http://ws.specialized.com/soa-infra/resources/GWS/ProductAvailability/Availability',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'string',
  'Content-Type': 'string'
}

r = requests.post('http://ws.specialized.com/soa-infra/resources/GWS/ProductAvailability/Availability', params={

}, headers = headers)

print r.json()

```

`POST /ProductAvailability/Availability`

TODO: Add Description

> Body parameter

```json
{
  "CredentialRequest": {
    "Username": "{{USERNAME}}",
    "Password": "null",
    "AccountNumber": "{{ACC_NUM}}",
    "Lang": "{{LANG}}",
    "Country": "{{CNTRY}}",
    "SourceApp": "POS"
  },
  "IncludePrice": "Y",
  "ShipTo": "null",
  "ItemIdentification": [
    {
      "ItemNumber": "2115-1030",
      "ItemType": "SKU",
      "RequestQuantity": 1
    },
    {
      "ItemNumber": "25516-1811",
      "ItemType": "SKU",
      "RequestQuantity": 1
    },
    {
      "ItemNumber": "60516-1202",
      "ItemType": "SKU",
      "RequestQuantity": 1
    }
  ]
}
```

<h3 id="stock-availability-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept|header|string|true|none|
|Content-Type|header|string|true|none|
|body|body|[stockavailabilityRequest](#schemastockavailabilityrequest)|true|none|

<h3 id="stock-availability-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
auth
</aside>

<h1 id="gws-order">order</h1>

## order creation with multiple sku

<a id="opIdProcessorderApiV1OrderPost"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'string',
  'Content-Type' => 'string'
}

result = RestClient.post 'http://ws.specialized.com/soa-infra/resources/GWS/processorder/api/v1/order',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'string',
  'Content-Type': 'string'
}

r = requests.post('http://ws.specialized.com/soa-infra/resources/GWS/processorder/api/v1/order', params={

}, headers = headers)

print r.json()

```

`POST /processorder/api/v1/order`

TODO: Add Description

> Body parameter

```json
"string"
```

<h3 id="order-creation-with-multiple-sku-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Accept|header|string|true|none|
|Content-Type|header|string|true|none|
|body|body|string|true|none|

<h3 id="order-creation-with-multiple-sku-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
auth
</aside>

## order details

<a id="opIdOrderDetailsRestApiV1Post"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Content-Type' => 'string',
  'Accept' => 'string'
}

result = RestClient.post 'http://ws.specialized.com/soa-infra/resources/GWS/OrderDetails/Rest/api/v1',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Content-Type': 'string',
  'Accept': 'string'
}

r = requests.post('http://ws.specialized.com/soa-infra/resources/GWS/OrderDetails/Rest/api/v1', params={

}, headers = headers)

print r.json()

```

`POST /OrderDetails/Rest/api/v1`

TODO: Add Description

> Body parameter

```json
{
  "CredentialRequest": {
    "Username": "HEFEI001@429415",
    "Password": "null",
    "AccountNumber": 429415,
    "Lang": "zhs",
    "Country": "CN",
    "SourceApp": "POS"
  },
  "OrderNumber": 501943,
  "CustPoNumber": "null",
  "PageIndex": 0,
  "OrdersPerPage": 2
}
```

<h3 id="order-details-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Content-Type|header|string|true|none|
|Accept|header|string|true|none|
|body|body|[orderdetailsRequest](#schemaorderdetailsrequest)|true|none|

<h3 id="order-details-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
auth
</aside>

## update order

<a id="opIdProcessorderApiV1OrderRND249328Put"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Content-Type' => 'string',
  'Accept' => 'string'
}

result = RestClient.put 'http://ws.specialized.com/soa-infra/resources/GWS/processorder/api/v1/order/RND249328',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Content-Type': 'string',
  'Accept': 'string'
}

r = requests.put('http://ws.specialized.com/soa-infra/resources/GWS/processorder/api/v1/order/RND249328', params={

}, headers = headers)

print r.json()

```

`PUT /processorder/api/v1/order/RND249328`

TODO: Add Description

> Body parameter

```json
{
  "CredentialRequest": {
    "Username": "HEFEI001@429415",
    "Password": "null",
    "AccountNumber": 429415,
    "Lang": "zhs",
    "Country": "CN",
    "SourceApp": "POS"
  },
  "OrderRequest": {
    "ExtOrderRef": "RND249328",
    "TransactionType": "UPDATE",
    "OrderLine": [
      {
        "ExtOrderLineRef": "GWS406",
        "SellersItemIdentification": {
          "ItemNumber": "43015-0120"
        },
        "Quantity": "1",
        "PreferredDeliveryDate": "null",
        "TransactionType": "UPDATE"
      }
    ]
  }
}
```

<h3 id="update-order-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Content-Type|header|string|true|none|
|Accept|header|string|true|none|
|body|body|[updateorderRequest](#schemaupdateorderrequest)|true|none|

<h3 id="update-order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
auth
</aside>

## transactions - orders

<a id="opIdSearchTransactionsRestApiV1Post"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Content-Type' => 'string',
  'Accept' => 'string'
}

result = RestClient.post 'http://ws.specialized.com/soa-infra/resources/GWS/SearchTransactions/Rest/api/v1',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Content-Type': 'string',
  'Accept': 'string'
}

r = requests.post('http://ws.specialized.com/soa-infra/resources/GWS/SearchTransactions/Rest/api/v1', params={

}, headers = headers)

print r.json()

```

`POST /SearchTransactions/Rest/api/v1`

TODO: Add Description

> Body parameter

```json
{
  "CredentialRequest": {
    "Username": "HEFEI001@429415",
    "AccountNumber": "429415",
    "Lang": "zhs",
    "Country": "CN",
    "SourceApp": "POS"
  },
  "StartDate": "2018-06-01",
  "EndDate": "2018-06-30",
  "Status": "ALL",
  "ItemGroup": "ALL",
  "TransactionType": "PURCHASE ORDER",
  "ShipAddress": null
}
```

<h3 id="transactions---orders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Content-Type|header|string|true|none|
|Accept|header|string|true|none|
|body|body|[transactions-ordersRequest](#schematransactions-ordersrequest)|true|none|

<h3 id="transactions---orders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
auth
</aside>

# Schemas

<h2 id="tocScredentialrequest">CredentialRequest</h2>

<a id="schemacredentialrequest"></a>

```json
{
  "Username": "string",
  "Password": "string",
  "AccountNumber": "string",
  "Lang": "string",
  "Country": "string",
  "SourceApp": "string"
}

```

*CredentialRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Username|string|true|none|none|
|Password|string|true|none|none|
|AccountNumber|string|true|none|none|
|Lang|string|true|none|none|
|Country|string|true|none|none|
|SourceApp|string|true|none|none|

<h2 id="tocScredentialrequest3">CredentialRequest3</h2>

<a id="schemacredentialrequest3"></a>

```json
{
  "Username": "string",
  "AccountNumber": "string",
  "Lang": "string",
  "Country": "string",
  "SourceApp": "string"
}

```

*CredentialRequest3*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Username|string|true|none|none|
|AccountNumber|string|true|none|none|
|Lang|string|true|none|none|
|Country|string|true|none|none|
|SourceApp|string|true|none|none|

<h2 id="tocSorderline">OrderLine</h2>

<a id="schemaorderline"></a>

```json
{
  "ExtOrderLineRef": "GWS406",
  "SellersItemIdentification": {
    "ItemNumber": "43015-0120"
  },
  "Quantity": "1",
  "PreferredDeliveryDate": "string",
  "TransactionType": "UPDATE"
}

```

*OrderLine*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ExtOrderLineRef|string|true|none|none|
|SellersItemIdentification|[SellersItemIdentification](#schemasellersitemidentification)|true|none|none|
|Quantity|string|true|none|none|
|PreferredDeliveryDate|string|true|none|none|
|TransactionType|string|true|none|none|

<h2 id="tocSorderrequest">OrderRequest</h2>

<a id="schemaorderrequest"></a>

```json
{
  "ExtOrderRef": "string",
  "TransactionType": "string",
  "OrderLine": [
    {
      "ExtOrderLineRef": "GWS406",
      "SellersItemIdentification": {
        "ItemNumber": "43015-0120"
      },
      "Quantity": "1",
      "PreferredDeliveryDate": "string",
      "TransactionType": "UPDATE"
    }
  ]
}

```

*OrderRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ExtOrderRef|string|true|none|none|
|TransactionType|string|true|none|none|
|OrderLine|[[OrderLine](#schemaorderline)]|true|none|none|

<h2 id="tocSupdateorderrequest">updateorderRequest</h2>

<a id="schemaupdateorderrequest"></a>

```json
{
  "CredentialRequest": {
    "Username": "HEFEI001@429415",
    "Password": "null",
    "AccountNumber": 429415,
    "Lang": "zhs",
    "Country": "CN",
    "SourceApp": "POS"
  },
  "OrderRequest": {
    "ExtOrderRef": "RND249328",
    "TransactionType": "UPDATE",
    "OrderLine": [
      {
        "ExtOrderLineRef": "GWS406",
        "SellersItemIdentification": {
          "ItemNumber": "43015-0120"
        },
        "Quantity": "1",
        "PreferredDeliveryDate": "null",
        "TransactionType": "UPDATE"
      }
    ]
  }
}

```

*updateorderRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CredentialRequest|[CredentialRequest1](#schemacredentialrequest1)|true|none|none|
|OrderRequest|[OrderRequest](#schemaorderrequest)|true|none|none|

<h2 id="tocSitemidentification">ItemIdentification</h2>

<a id="schemaitemidentification"></a>

```json
{
  "ItemNumber": "2115-1030",
  "ItemType": "SKU",
  "RequestQuantity": 1
}

```

*ItemIdentification*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ItemNumber|string|true|none|none|
|ItemType|string|true|none|none|
|RequestQuantity|integer(int32)|true|none|none|

<h2 id="tocSstockavailabilityrequest">stockavailabilityRequest</h2>

<a id="schemastockavailabilityrequest"></a>

```json
{
  "CredentialRequest": {
    "Username": "{{USERNAME}}",
    "Password": "null",
    "AccountNumber": "{{ACC_NUM}}",
    "Lang": "{{LANG}}",
    "Country": "{{CNTRY}}",
    "SourceApp": "POS"
  },
  "IncludePrice": "Y",
  "ShipTo": "null",
  "ItemIdentification": [
    {
      "ItemNumber": "2115-1030",
      "ItemType": "SKU",
      "RequestQuantity": 1
    },
    {
      "ItemNumber": "25516-1811",
      "ItemType": "SKU",
      "RequestQuantity": 1
    },
    {
      "ItemNumber": "60516-1202",
      "ItemType": "SKU",
      "RequestQuantity": 1
    }
  ]
}

```

*stockavailabilityRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CredentialRequest|[CredentialRequest](#schemacredentialrequest)|true|none|none|
|IncludePrice|string|true|none|none|
|ShipTo|string|true|none|none|
|ItemIdentification|[[ItemIdentification](#schemaitemidentification)]|true|none|none|

<h2 id="tocSsellersitemidentification">SellersItemIdentification</h2>

<a id="schemasellersitemidentification"></a>

```json
{
  "ItemNumber": "43015-0120"
}

```

*SellersItemIdentification*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ItemNumber|string|true|none|none|

<h2 id="tocSorderdetailsrequest">orderdetailsRequest</h2>

<a id="schemaorderdetailsrequest"></a>

```json
{
  "CredentialRequest": {
    "Username": "HEFEI001@429415",
    "Password": "null",
    "AccountNumber": 429415,
    "Lang": "zhs",
    "Country": "CN",
    "SourceApp": "POS"
  },
  "OrderNumber": 501943,
  "CustPoNumber": "null",
  "PageIndex": 0,
  "OrdersPerPage": 2
}

```

*orderdetailsRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CredentialRequest|[CredentialRequest1](#schemacredentialrequest1)|true|none|none|
|OrderNumber|integer(int32)|true|none|none|
|CustPoNumber|string|true|none|none|
|PageIndex|integer(int32)|true|none|none|
|OrdersPerPage|integer(int32)|true|none|none|

<h2 id="tocScredentialrequest1">CredentialRequest1</h2>

<a id="schemacredentialrequest1"></a>

```json
{
  "Username": "string",
  "Password": "string",
  "AccountNumber": 0,
  "Lang": "string",
  "Country": "string",
  "SourceApp": "string"
}

```

*CredentialRequest1*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Username|string|true|none|none|
|Password|string|true|none|none|
|AccountNumber|integer(int32)|true|none|none|
|Lang|string|true|none|none|
|Country|string|true|none|none|
|SourceApp|string|true|none|none|

<h2 id="tocStransactions-ordersrequest">transactions-ordersRequest</h2>

<a id="schematransactions-ordersrequest"></a>

```json
{
  "CredentialRequest": {
    "Username": "HEFEI001@429415",
    "AccountNumber": "429415",
    "Lang": "zhs",
    "Country": "CN",
    "SourceApp": "POS"
  },
  "StartDate": "2018-06-01",
  "EndDate": "2018-06-30",
  "Status": "ALL",
  "ItemGroup": "ALL",
  "TransactionType": "PURCHASE ORDER",
  "ShipAddress": null
}

```

*transactions-ordersRequest*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|CredentialRequest|[CredentialRequest3](#schemacredentialrequest3)|true|none|none|
|StartDate|string|true|none|none|
|EndDate|string|true|none|none|
|Status|string|true|none|none|
|ItemGroup|string|true|none|none|
|TransactionType|string|true|none|none|
|ShipAddress|string|true|none|none|

