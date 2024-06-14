# POST /dinner/burgerMeal

## Overview

This HTTP request creates an order for the kitchen to make based on a customer's order. As a POC, the API can only take dinner orders for a burger meal. In the future, the API will be able to handle all kinds of meals throughout the day. For more information about the API in general, see the [readme file](readme.md).

## URL
```
https://api.gpmd.com/dinner/burgerMeal
```

## Request body parameters

The order is a JSON object containing 3-4 objects (depending on number of sides): the burger, the side(s), and the drink.

### Burger parameters

Here is a table showing the different burger parameters:

| Parameter    | Description             | Data type | Possible values                                                                          | Default     | Required? |
|-------------|-------------------------|-----------|------------------------------------------------------------------------------------------|-------------|-----------|
| pattyType   | Type of meat for burger | string    | beef, lamb, chicken, vegan                                                               | Beef        | Y         |
| pattyCook   | Burger doneness         | string    | rare, mediumRare, medium, mediumWell, wellDone                                           | Medium      | Y         |
| pattyWeight | Patty weight            | integer   | 160, 250, 300                                                                            | 160         | Y         |
| pattyQty    | Number of patties       | integer   | 1, 2, 3                                                                                  | 1           | Y         |
| bunType     | Bread of type for bun   | string    | white, rye, wholeWheat, glutenFree                                                       | White bread | Y         |
| topping1    | First burger topping    | string    | lettuce, tomato, friedOnions, redOnions, pickles, jalapenos, veganCheese, friedEgg, none | none        | N         |
| topping2    | Second burger topping   | string    | lettuce, tomato, friedOnions, redOnions, pickles, jalapenos, veganCheese, friedEgg, none | none        | N         |
| topping3    | Third burger topping    | string    | lettuce, tomato, friedOnions, redOnions, pickles, jalapenos, veganCheese, friedEgg, none | none        | N         |
| condiment1  | First condiment         | string    | ketchup, mustard, garlicMayo, thousandIsland, bbqSauce, mayonnaise, none                 | none        | N         |
| condiment2  | Second condiment        | string    | ketchup, mustard, garlicMayo, thousandIsland, bbqSauce, mayonnaise, none                 | none        | N         |

### Side parameters

Each side is its own object with its own parameters. The customer is limited to 2 sides. Here is a table showing the different parameters each side has:

| Parameter | Description  | Data type | Possible values                                                                               | Default | Required? |
|----------|--------------|-----------|-----------------------------------------------------------------------------------------------|---------|-----------|
| type     | Type of side | string    | fries, rice, mashedPotatoes, onionRings,<br>sweetPotatoFries, gardenSalad, israeliSalad, none | none    | N         |
| size     | Size of side | string    | small, medium, large, none                                                                    | none    | N         |

### Drink parameters

Here is a table showing the different drink parameters:

| Parameter | Description   | Data type | Possible values                                                         | Default | Required? |
|----------|---------------|-----------|-------------------------------------------------------------------------|---------|-----------|
| type     | Type of drink | string    | coke, cokeZero, sprite, spriteZero,<br>lemonade, icedTea, seltzer, none | none    | N         |
| size     | Size of drink | string    | small, medium, large, none                                              | none    | N         |
| ice      | Ice in drink  | boolean   | true or false                                                           | true    | N         |

## Example request

Here is an example of a POST request for a customer's order:
```
curl -H "Content-Type: application/json" -X POST -d'
```
{
"mealCat": "burgerMeal",
    "burger": {
		"pattyType": "beef",
		"pattyCook": "mediumRare",
		"pattyWeight": 250,
		"pattyQty": 1,
		"bunType": "wholeWheat",
		"topping1": "pickles",
		"topping2": "veganCheese",
		"topping3": "none"
		"condiment1": "ketchup",
		"condiment2": "garlicMayo",
  	},
    "sides": {
		"side1": {
			"type": "fries",
			"size": "large"
		},
		"side2": {
			"type": "none",
			"size": "none"
		},
  	},
    "drink": {
		"type": "cokeZero",
		"size": "large",
		"ice": true
  	}

}
```

## HTTP status codes

Here are the possible HTTP responses:

| Status code | Description    | Description                                            |
|-------------|----------------|--------------------------------------------------------|
| 200         | Success        | Meal request was successfully received and sent to the kitchen |
| 400         | Invalid order  | Improper input, such as too many toppings              |
| 500         | Server problem | API couldn't connect to the server                     |

<br>
<br>

> This API documentation is adapted from a template provided by <a href="https://thegooddocsproject.dev/">The Good Docs Project</a>. This project is based on an exercise created by <a href="https://www.linkedin.com/feed/update/urn:li:activity:6626465471241732096/">Alex Feidler</a>.
