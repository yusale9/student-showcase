# API Reference - GPMD POST method

## Overview

Use the General Putnam Motel Diner (GPMD) APIs to access program functions for placing orders and requesting bills. The **POST** method is used to create a meal request.

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
| `100 OK`                       | Continue             | No errors reported but but awaiting further data.   |  
| `200 OK`                       | Success              | Meal was successfully ordered.                      |
| `400 - Bad Request`            | Order refused        | Order was not accepted. Check for invalid options.  |
| `401 - Unauthorized`           | Authorization failed | Authorization attempt failed. Check supplied values.|
| `500 - Internal Server Error`  | Server side failure  | Contact server administrator.                       |



### Endpoints

Use the following endpoints to interact with the GPMD entities.

| Method | Endpoint name               | Description             |
|--------|-----------------------------|-------------------------|
| POST   | /lunch                      | Creates a burger meal order.   |
| GET    | /tableNo                    | Retrieves a bill. |
|        |                                          |                         |


## /lunch

Creates an order for a GPMD burger meal.

### Endpoint

```
POST /https://api.gpmd.com/lunch
```

#### Request body

|Menu Item|Options|Default|Comments|
|---------|-------|-------|--------|
|Burger|Beef||Choose one only
||Chicken
||Vegetarian
||Vegan|Beef
|Carnivorous Predilection|Well done||Choose one only
||Medium
||Rare
||Still twitching|Medium
Cooking type|Grilled||Choose one only
||Fried
||Baked|Grilled
Served in|White bun||Choose one only
||White slice
||Wholemeal bun
||Wholemeal slice
||Gluten free bun
||Gluten free slice
||No bread|White bun
Serving size|Large||Choose one only
||Extra large
||Double decker|Extra large
|Dressing|Honey mustard||Allow multiple selection
||Garlic mayo
||Thousand island
||Ketchup
||None|None
|Toppings|Lettuce||Allow multiple selection
||Pickle
||Tomato
||Pepper
||Relish
||None|None
|Side Dishes|Pomme frites||Allow multiple selection
||Sauted potatoes 
||Coleslaw
||Israeli salad
||Corn salad
||None|None
|Side Portion Size|Medium||Only if side order selected
||Large|Medium
|Wine (Glass)|House red||Allow multiple selection
||House white
||None|None
|Beer (Bottle)|Budweiser||Allow multiple selection
||Guinness
||Carlsberg
||None|None
|Soft Drink (Can)|Coke||Allow multiple selection
||Coke Zero
||Diet Coke
||Coke Caffeine Free
||Sprite
||Sprite Zero
||Fanta Orange
||Apple juice
||Orange juice
||None|None
|With Ice?|Yes||If soft drink selected
||No|No

### Request example

```JSON

curl -H "Content-Type: application/json" -X POST -d'
{
	"mealType": "lunch",
	"mealCat": "burgerMeal",
	  "burger": {
		"pattyType": "beef",
		"pattyCook": "Medium",
	        "pattySize": "large",
		"pattyCookType": "fried",
		"bunType": "whiteBun",
		"dressing1": "ketchup",
		"dressing2": "honeyMustard",
		"topping1": "lettuce",
		"topping2": "pickle",
		"topping3": "relish"
	},
	"sides": {
		"side1": {
			"type": "pommeFrites",
			"size": "large"
		},
		"side2": {
			"type": "coleslaw",
			"size": "medium"
		}
	},
	"softDrink": {
		"type": "coke",
		"size": "large",
		"ice": true
	}

}
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
