# API Reference - GPMD GET method

## Overview

Use the General Putnam Motel Diner (GPMD) APIs to access program functions for placing orders and requesting bills. The **GET** method is used to create a bill request. The other method available in this API is <a href="POST.md">POST</a> used to create a meal request.

### Base URL

```
https://api.gpmd.com
```

### Authorization

Authentication and authorization is required for requests to these APIs. Supported authentication methods are:
* OAuth with 2 Factor Authentication (2FA)


### Version

This is Version `0.01` of the API.


### HTTP status codes

The GPMD APIs use the following standard HTTP response codes:

| Status code                    | Message              | Description                                         |
|--------------------------------|----------------------|-----------------------------------------------------|
| `100 - OK`                       | Continue             | No errors reported but but awaiting further data.   |  
| `200 - OK`                       | Success              | Bill was successfully requested.                      |
| `400 - Bad Request`            | Request refused        | Bill request was not accepted. Check for invalid options.  |
| `401 - Unauthorized`           | Authorization failed | Authorization attempt failed. Check supplied values.|
| `500 - Internal Server Error`  | Server-side failure  | Contact server administrator.                       |



## GET /tableNo

Creates an request for a GPMD meal bill.

### Endpoint

```
https://api.gpmd.com/tableNo
```

#### Request body


| Field  | Data Type   | Required? | Description                      |
|--------|---------|-----------|----------------------------------|
| id   | integer | Required  | Table number of order  |

### Request example

```curl
curl -X GET "http://URL/tableNo?id=99"
```

### Response example

```JSON
{
   "orderNum":123,
   "timestamp":"2020-01-21T07:44:45-05:00",
   "Item1":{
  	"ItemOrdered":{
     	"type":"burgerMeal",
     	"Cost":10.99
  	}
   },
   "Item2":{
  	"ItemOrdered":{
     	"type":"pommeFritesMedium",
     	"Cost":9.50
  	}
   }
}
```
### Response explained

| Field  | Data Type   | Description                      |
|--------|--------|----------------------------------|
|orderNum|Integer|The number of the order for which this bill has been generated.
|timestamp|Date|The time the order was placed.
|Item1|JSON object|The first menu item ordered.
|ItemOrdered|Nested JSON object|Detail of Item1
|type|String|There's only one type for this POC
|Cost|Float|Cost of burgerMeal
|Item2|JSON object|The side order menu item ordered.
|ItemOrdered|Nested JSON object|Detail of Item2
|type|String|pommeFritesMedium
|Cost|Float|Cost of side order type


---

> Explore other templates from [The Good Docs Project](https://thegooddocsproject.dev/). Use our [feedback form](https://thegooddocsproject.dev/feedback/?template=API%20reference) to give feedback on this template.
