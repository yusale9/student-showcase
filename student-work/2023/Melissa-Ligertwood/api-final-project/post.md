# AppCorp Meal Order API Reference

## Overview

This is an API to order take out meals.

### Base URL

```
https://api.acmo.com
```

## Place burger order

### Endpoint

```
POST /lunch/burgerMeal
```

### Description

Collects the customer's burger order and sends to the kitchen.  

### Request schema

| Parameter | Type | Required? | Description                             |
|-----------------|------|-----------|-----------------------------------------|
| mealType     | string | Required  |  |
| mealCat    | string | Required |                                         |
| burger    | object | Required |                                         |
| pattyQty   | string | Required |                                         |
| cheeseQty  | string | Optional |                                         |
| bunType   | string | Optional |                                         |
| pattyType    | string | Required |                                         |
| topping  | string | Optional |                                         |
| sides | object | Required |                                         |
| side    | object | Optional |                                         |
| drink    | object | Optional |                                         |
| type    | string | Required  |                                         |
| size    | string | Required |                                         |
| ice    | boolean | Required |                                         |

### Request example

```
curl -H "Content-Type: application/json" -X POST -d'
{
	"mealType": "lunch",
	"mealCat": "burgerMeal",
	  "burger": {
		"pattyQty": "single",
		"cheeseQty": "extra",
		"bunType": "regular",
		"pattyType": "angus",
		"topping1": "msauce",
		"topping2": "lettuce",
		"topping3": "tomato"
	},
	"sides": {
		"side1": "onionRings",
		"side2": "gravy"
	},
	"drink": {
		"type": "pop",
		"size": "small",
		"ice": true
	}

}
```

### Response Schema
| Status code | Schema                                  | Description          |
|-------------|-----------------------------------------|----------------------|
| `2xx`       | [{ExampleDataType}](#data-model)        | {Describe the result where the request succeeds.} |
| `4xx`       | [{ExampleErrorType}](#exampleerrortype) | {Describe the result where the request fails with the specified error code.} |

### Response example

```
200 OK
```
---
