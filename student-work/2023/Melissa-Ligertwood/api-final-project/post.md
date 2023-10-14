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
POST /lunch
```

### Description

Sends your lunch order. You can only send an order that is valid for the current time.  

### Request schema

| Parameter | Type | Required? | Description                             |
|-----------------|------|-----------|-----------------------------------------|
| mealType     | string | Required  | Lunch order. |
| mealCat    | string | Required | Lunch choice. Can be burgerMeal, saladMeal, or bowlMeal. Default is burgerMeal.|
| burger    | object | Required | Contains pattyQty, cheeseQTY, bunType, pattyType, and toppings.|
| pattyQty   | string | Required | Number of burger patties. Can be single, double, or triple. |
| cheeseQty  | string | Optional | Amount of cheese. Can be standard or extra. Null means no cheese.|
| bunType   | string | Optional | Type of bun. Can be regular or gluten free. Null means no bun. |
| pattyType    | string | Required | Type of patty. Can be angus, wagyu, or plant-based. Default is angus. |
| topping  | string | Optional | Burger toppings. Can be Msauce, lettuce, tomato, red onion, pickles, bacon, fried egg, or fried onions. Each topping is identified by a number. Null means no toppings. |
| sides | object | Optional | Contains a max of 2 sides. Null means no sides and does not change the burgerMeal cost. |
| side    | string | Required | Choice of side dishes. Each side is identifed by a number. Required if sides object is not null. Can be potato roll, fries, tots, poutine, onion rings, truffle parm fries, house salad, or gravy. Default is fries. |
| drink    | object | Optional | Contains type, size, and ice. Null means no drink and does not change the burgerMeal cost. |
| type    | string | Required  | Choice of drink. Required if drink is not null. Can be pop, iced tea, water, rockstar, gatorade, frappuccion, or milkshake. Default is pop. |
| size    | string | Required | Drink size. Required if drink is not null. Can be small, medium, or large. Default is large. |
| ice    | boolean | Required | Default is true. False means no ice. |

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
