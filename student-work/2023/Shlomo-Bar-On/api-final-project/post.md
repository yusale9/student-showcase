# API Reference - GPMD POST method

## Overview

Use the General Putnam Motel Diner (GPMD) APIs to access program functions for placing orders and requesting bills. The **POST** method is used to create a meal request. The other method available in theis API is <a href="GET.md">GET</a> used to retrieve a bill for a meal order.  Background information for this API is in the <a href="readme.md">README</a> file.


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
| `200 - OK`                       | Success              | Meal was successfully ordered.                      |
| `400 - Bad Request`            | Order refused        | Order was not accepted. Check for invalid options.  |
| `401 - Unauthorized`           | Authorization failed | Authorization attempt failed. Check supplied values.|
| `500 - Internal Server Error`  | Server side failure  | Contact server administrator.                       |


## POST /lunch

Creates an order for a GPMD burger meal.

### Endpoint

```
https://api.gpmd.com/lunch
```

#### Request body

> [!IMPORTANT]  
> All attributes are mandatory.

#### Main burger meal

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
|Dressing|Honey mustard|None|String|Allow up to 2 selections if not 'None'
||Garlic mayo
||Thousand island
||Ketchup
||None|
|Topping|Lettuce|None|String|Allow up to 3 selections if not 'None'
||Pickle
||Tomato
||Pepper
||Relish
||None|
|Meal Quantity|1-5|1|Integer|How many burger meals are required

#### Side dish
|Menu Item|Valid Options|Default|Data Type|Comments|
|---------|-------------|-------|---------|--------|
|Meal Type|Lunch|Lunch|String|
|Meal Category|Side Dish|1 x Pomme frites (mdm)|Integer|Choose side orders
||Pomme frites medium qty|0
||Pomme frites large qty|0
||Sauted potatoes medium qty |0
||Sauted potatoes large qty |0
||Coleslaw medium qty |0
||Coleslaw large qty |0
||Israeli salad medium qty |0
||Israeli salad large qty |0
||Corn salad medium qty |0
||Corn salad large qty |0

#### Drink
|Menu Item|Valid Options|Default|Data Type|Comments|
|---------|-------------|-------|---------|--------|
|Meal Type|Lunch|Lunch|String|
|Meal Category|Drink|1 x Mineral water|Integer|Choose drinks
|Wine |House red (glass)|0
||House white (glass)|0
||Mineral water|0
|Beer (bottle)|Budweiser|0
||Guinness|0
||Carlsberg|0
|Soft Drink (Can)|Coke w/ice|0
||Coke Zero|0
||Diet Coke|0
||Coke Caffeine Free |0
||Sprite|0
||Sprite Zero|0
||Fanta Orange|0
||Apple juice|0
||Orange juice|0
|With Ice?|True|False|Boolean|If soft drink selected
||False|

### Request example

```curl
curl -H "Content-Type: application/json" -X POST -d'
```
```JSON
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
	"sideDish": {
		"sideDish1": {
			"type": "pommeFritesMedium"
		},
		"sideDish2": {
			"type": "coleslawLarge",
		}
	},
	"softDrink": {
		"type": "coke",
		"ice": true
	}

}
```

### Response status codes

| Status code |  Description          |
|-------------|----------------------|
| `200-OK`       | Meal ordered successfully.|
| `400 - Bad Request`       | Meal order request failed. Check for invalid options. |
| `500 - Internal Server Error`  | Server side failure  | Contact server administrator.  |

### Response example

```JSON
{
"meal_order" {
	"order_number": 506321,
	"meal_type": "lunch", 
	"timestamp": "2024-01-14T07:44:45-05:00", 
	"mealCat": "burgerMeal",
	"dressing1": "ketchup",
	"dressing1": "honeyMustard",
	"topping1": "lettuce",
	"topping2": "pickle",
	"topping3": "relish",
	"sideDish": "pommeFritesMedium", 
	"sideDish": "coleslawLarge",
	"softDrink": "coke",
	"ice": true,
	"server": "Brenda",
	"server_id":"aslkw0923CAE", 
	"cook": "Lou", 
	"cook_id": "l2j23j9LKJsd",
	"price_base": "10.99", 
	"price_add": "8.00", 
	"price_total": "18.99" 
	}
}
```
---

> Explore other templates from [The Good Docs Project](https://thegooddocsproject.dev/). Use our [feedback form](https://thegooddocsproject.dev/feedback/?template=API%20reference) to give feedback on this template.
