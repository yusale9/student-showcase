
# API Reference

{Before using this template, read [the accompanying guide](api-reference-guide.md) to this template}.

## Overview

Use the {product} APIs to {access | customize | program} the {features | functionality}.

### Base URL

```
{(https://github.com/jonathan-t-kemp/student-showcase/tree/main/student-work/2022/Jonathan-Kemp/api)}
```

### Authorization

Authentication and authorization {is | is not} required for requests to these APIs. Supported authentication methods are:
{ Basic | Digest | OAuth | others}

```
{Provide an example request with {Basic | Digest | OAuth | others} authentication.}
```

### Version

{This section is optional.}

{Provide the version number using semantic versioning or your product's API versioning scheme. For example: `0.0.1`}


The {product} APIs use the following error types:

| Error                                   | Description      |
|-----------------------------------------|------------------|
| [{ExampleErrorType}](#exampleerrortype) | {Failure in ...} |
|                                         |                  |
|                                         |                  |

#### ExampleErrorType

| Field          | Type     | Description                                      |
|----------------|----------|--------------------------------------------------|
| {errorType}    | {enum}   | {Predefined error codes. Possible enum values are x, y, ..., and z.} |
| {errorMessage} | {string} | {Additional information about why the error occurs.} |


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
| POST   | {[Order](https://github.com/jonathan-t-kemp/student-showcase/blob/main/student-work/2022/Jonathan-Kemp/api/POST.md)} | Creates a {resource}.   |
| GET    | {[Menu](https://github.com/jonathan-t-kemp/student-showcase/blob/main/student-work/2022/Jonathan-Kemp/api/GET.md)} | Retrieves a {resource}. |
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
```
curl -X GET http://URL/tableNo?id=99
{
   "orderNum":123,
   "timestamp":"2023-02-12T07:44:45-05:00",
   "Item1":{
  	"ItemOrdered":{
     	"type":"burger",
     	"Cost":49.50
  	}
   },
   "Item2":{
  	"ItemOrdered":{
     	"type":"salad",
     	"Cost":9.50
  	}




### Response schema

| Status code | Schema                                  | Description          |
|-------------|-----------------------------------------|----------------------|
| `2xx`       | [{ExampleDataType}](#data-model)        | {Describe the result where the request succeeds.} |
| `4xx`       | [{ExampleErrorType}](#exampleerrortype) | {Describe the result where the request fails with the specified error code.} |

### Response example

```
{Provide an example of the API response, filled with sample values.}
```
```
curl -H "Content-Type: application/json" -X POST -d'
{
	"mealType": "lunch",
	"mealCat": "burgerMeal",
	  "burger": {
		"pattyType": "beef",
		"pattyQty": 1,
		"pattyWeightG": 300,
		"pattyCook": "MR",
		"bunType": "wholeWheat",
		"condiment1": "ketchup",
		"condiment2": "secretSauce",
		"topping1": "lettuce",
		"topping2": "pickles",
		"topping3": "onion"
	},
	"sides": {
		"side1": {
			"type": "frenchFries",
			"size": "large"
		},
		"side2": {
			"type": "none",
			"size": ""
		}
	},
	"drink": {
		"type": "Coke",
		"size": "large",
		"ice": true
    }

}

   }
