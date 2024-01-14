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
https://api.gpmd.com/lunch
```

#### Request body

|Menu Item|Valid Options|Default|Data Type|Comments|
|---------|-------------|-------|---------|--------|
|Meal Type|Lunch|Lunch|String|
|Meal Category|Burger Meal|Burger Meal|String|
|Patty Type|Beef|Beef|String|Choose one only
||Chicken
||Vegetarian
||Vegan|
|Patty Cook|Well done|Medium|String|Choose one only
||Medium
||Rare
||Still twitching|
|Patty Cook Type|Grilled|Grilled|String|Choose one only
||Fried
||Baked|
|Bun Type|White bun|White bun|String|Choose one only
||White slice
||Wholemeal bun
||Wholemeal slice
||Gluten free bun
||Gluten free slice
||No bread|
|Patty size|Large|Extra large|String|Choose one only
||Extra large
||Double decker|
|Dressing|Honey mustard|None|String|Allow multiple selection
||Garlic mayo
||Thousand island
||Ketchup
||None|
|Topping|Lettuce|None|String|Allow multiple selection
||Pickle
||Tomato
||Pepper
||Relish
||None|
|Side Dishes|Pomme frites|None|String|Allow multiple selection
||Sauted potatoes 
||Coleslaw
||Israeli salad
||Corn salad
||None|
|Side Portion Size|Medium|Medium|String|Per side order and only if side order selected
||Large|
|Wine (Glass)|House red|None|String|Allow multiple selection
||House white
||None|
|Beer (Bottle)|Budweiser|None|String|Allow multiple selection
||Guinness
||Carlsberg
||None|
|Soft Drink (Can)|Coke|None|String|Allow multiple selection
||Coke Zero
||Diet Coke
||Coke Caffeine Free
||Sprite
||Sprite Zero
||Fanta Orange
||Apple juice
||Orange juice
||None|
|With Ice?|True|False|Boolean|If soft drink selected
||False|

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

```JSON
{
meal_order {
	"order_number": 506321,
	{
	meal 	{	 
		"meal_type”: “lunch”, 
		“timestamp”: “2024-01-14T07:44:45-05:00”, 
		“mealCat”: “burgerMeal”, 
		“meal_quantity”: 1, 
		“side”: ”pommeFrites", 
		“side_quantity”: 1, 
		“side”: ”coleslaw”,
		“side_quantity”: 1, 
		“server”: ”Brenda”,
		“server_id”:“aslkw0923CAE”, 
		“cook”: ”Lou”, 
		“cook_id”: ”l2j23j9LKJsd”, “price_base”: “10.99” 
		“price_add”: “8.00” 
		“price_total”: “9.99” 
		}
	}
}
}

```
---

> Explore other templates from [The Good Docs Project](https://thegooddocsproject.dev/). Use our [feedback form](https://thegooddocsproject.dev/feedback/?template=API%20reference) to give feedback on this template.
