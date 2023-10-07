# ABC Take Out Order API Reference

## Overview

Use the {product} APIs to {access | customize | program} the {features | functionality}.

### Base URL

```
https://api.gpmd.com
```

### Authorization

Authentication and authorization {is | is not} required for requests to these APIs. Supported authentication methods are:
{ Basic | Digest | OAuth | others}

```
{Provide an example request with {Basic | Digest | OAuth | others} authentication.}
```

### Version

The current API vesrion is 1.0

### Rate limits

Multiple orders allowed in a single request. Max three orders per request. 

### HTTP status codes

The ABC Take Out Order API uses the following standard HTTP response codes:

| Status code | Message           | Description   |
|-------------|-------------------|---------------|
| `200 OK`    | Successful request. | Correct order is placed. |
|             |                   |               |
|             |                   |               |

### Errors

The ABC Take Out Order API uses the following error types:

| Error                                   | Description      |
|-----------------------------------------|------------------|
| `400 Bad Request`| {Failure in ...} |
| `401 Unauthorized` |                  |
| `402 Request Failed` |                  |
| `403 Forbidden` |                  |
| `404 Not Found` |                  |
| `429 Too Many Requests` |                  |

#### ExampleErrorType

| Field          | Type     | Description                                      |
|----------------|----------|--------------------------------------------------|
| {errorType}    | {enum}   | {Predefined error codes. Possible enum values are x, y, ..., and z.} |
| {errorMessage} | {string} | {Additional information about why the error occurs.} |


## Meals

Meals are how you order food using this API.

### Data model

| Attribute | Type   | Required? | Description                  |
|-----------|--------|-----------|------------------------------|
| {id}      | string | Required  | {Unique identifier of user}  |
| {name}    | string | Optional  | {Name of user}               |
|           |        |           |                              |

### Example

```
{Provide an example of the data representation in the format that your project use.}
```

### Endpoints

Use the following endpoints to interact with the {resource name} entities.

| Method | Endpoint name                            | Description             |
|--------|------------------------------------------|-------------------------|
| POST   | {[Endpoint name A](#link_to_endpoint_a)} | Creates a {resource}.   |
| GET    | {[Endpoint name B](#link_to_endpoint_b)} | Retrieves a {resource}. |
|        |                                          |                         |


## {Endpoint name}

{Provide a one-line description of what the API does. Starts with a verb in the indicative mood. For example, "Retrieves a user by `userID`".}

### Endpoint

```
{METHOD} /{request-url}/{{path-parameter}}
```

### Description

{Explain what the endpoint does.}

{This paragraph is optional.} This endpoint has been deprecated. Use {the recommended endpoint} instead. For more information about how to migrate to {the recommended endpoint}, see [{the migration guide}](#link).

{This paragraph is optional.} The maximum number of calls to this API endpoint is {number} per minute. For more information about API rate limiting/throttling, see [{the topic}](#example).


### Authorization

The [{authorization method}](#authorization) is required for each API request.

{This paragraph is optional.} Calling this endpoint also requires the {permission-name} permission.


### Request schema

#### Path parameters

{This section is optional.}

| Path parameter | Type   | Required? | Description                  |
|----------------|--------|-----------|------------------------------|
| {id}           | string | Required  | {Unique identifier of user}  |
|                |        |           |                              |

#### Query parameters

{This section is optional.}

| Query parameter | Type | Required? | Description                             |
|-----------------|------|-----------|-----------------------------------------|
| {pageSize}      | int  | Optional  | {The number of items to be returned in a single request. The default value is N.} |
|                 |      |           |                                         |

#### Header parameters

{This section is optional.}

| Header parameter | Type   | Required? | Description                          |
|------------------|--------|-----------|--------------------------------------|
| {Content-Type}   | string | Required  | {Media type of the resource. Must be an object.} |
|                  |        |           |                                      |

#### Request body

{This section is optional.}

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
