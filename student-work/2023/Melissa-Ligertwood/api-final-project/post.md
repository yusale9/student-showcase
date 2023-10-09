# AppCorp Meal Order API Reference

## Overview

This is an API to order take out meals.

### Base URL

```
https://api.acmo.com
```

## Place lunch order

### Endpoint

```
POST /lunch
```

### Description

Collects the customer's order and sends to the kitchen.  

### Request schema

#### Request body

{This section is optional.}

| Field  | Type   | Required? | Description                      |
|--------|--------|-----------|----------------------------------|
| {id}   | string | Required  | {Unique identifier of the user}  |
| {name} | string | Optional  | {Name of the user}               |


### Request example

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
