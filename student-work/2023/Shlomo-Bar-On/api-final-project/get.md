# API Reference - GPMD GET method

## Overview

Use the General Putnam Motel Diner (GPMD) APIs to access program functions for placing orders and requesting bills. The **GET** method is used to create a bill request.

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
| `500 - Internal Server Error`  | Server side failure  | Contact server administrator.                       |



### Endpoints

Use the following endpoints to interact with the GPMD entities.

| Method | Endpoint name               | Description             |
|--------|-----------------------------|-------------------------|
| POST   | /lunch                      | Creates a burger meal order.   |
| GET    | /tableNo                    | Retrieves a bill. |
|        |                                          |                         |


## GET /tableNo

Creates an request for a GPMD meal bill.

### Endpoint

```
https://api.gpmd.com/tableNo
```

#### Request body

#### Request body



| Field  | Type   | Required? | Description                      |
|--------|--------|-----------|----------------------------------|
| {id}   | string | Required  | {Unique identifier of the user}  |
| {name} | string | Optional  | {Name of the user}               |

### Request example

```
{Provide an example of the API request, filled with sample values.}
```

### Response schema

| Status code | Schema                                  | Description          |
|-------------|-----------------------------------------|----------------------|
| `2xx`       | [{ExampleDataType}](#data-model)        | {Describe the result where the request succeeds.} |
| `4xx`       | [{ExampleErrorType}](#exampleerrortype) | {Describe the result where the request fails with the specified error code.} |

### Response example

```
{Provide an example of the API response, filled with sample values.}
```
---

> Explore other templates from [The Good Docs Project](https://thegooddocsproject.dev/). Use our [feedback form](https://thegooddocsproject.dev/feedback/?template=API%20reference) to give feedback on this template.
