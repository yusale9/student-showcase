# General Putnam Motel Diner API Documentation for the Burger Meal

{Before using this template, read [the accompanying guide](api-reference-guide.md) to this template}.

## Overview

The General Putnam Motel Diner API allows patrons of the diner to order their meals in a touchless manner via an app. Due to time restraints and for the purposes of creating a POC by April, this API documentation is limited to ordering the Burger Meal at lunch time as a take-out order. In the future, the final product will include a full menu for different meal times.  
The API is used to interface between the app and the server in the diner kitchen. Two main functions are presented:  
* **A command is sent to the server:**  
  An order is submitted.
* **A command is retrieved from the server:**  
  A bill is generated.

### Base URL

https://api.generalputnammoteldiner.com

### Authorization

Standard methods of authentication apply.

### HTTP status codes

The General Putnam Motel Diner APIs use the following standard HTTP response codes:

| Status code | Type                   | Description                         |
|-------------|------------------------|-------------------------------------|  
| 100         | Informational response | Request received, proceeding.       |  
| 200         | Successful response    | No further action needed from user. |


### Errors

The General Putnam Motel Diner APIs use the following error types:

| Error code | Type                | Description                         |
|------------|---------------------|-------------------------------------|
| 401        | Successful response | No further action needed from user. |

## {Resource name}

The {resource name} is used to {functionality}.

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
