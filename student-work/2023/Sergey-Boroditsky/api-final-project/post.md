# POST Documentation

### Description:
Utilize the GPMD APIs to access program functionalities for placing orders and requesting bills. Use the POST method to create a meal request and the GET method to retrieve a bill for a meal order. Refer to the README file for background information on this API.

### HTTP Method:
POST

### POST Parameters:
A 'burgerMeal' JSON object that encompasses all the items ordered in a meal, including other JSON objects, as illustrated below.

#### Burger Meal Definition

The parameters and values for the `burgerMeal` object are as follows:

| Property Name | Description | Data Type | Values | Default Value | Mandatory / Optional |
|---|---|---|---|---|---|
| burger | Type of the burger | 'burger' object | See [Burger Definition](#burger-definition) below. |   | Yes |
| sides | The two side dishes (two sides is the default option for this meal). | 'sides' object with 2 properties, both being also being JSON objects: side1 and side2. | See [Sides Definition](#sides-definition) below. If no sides are chosen, Null is passed for each of the 'side' objects. |  | Yes |
| drink | Type of drink | 'drink' object. | See [Drink Definition](#drink-definition) below |   | No |

#### Burger Definition

The parameters and values for the `burger` object are as follows:


| Property | Description | Data Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| pattyType | Patty type | string | beef, mutton, chicken, vegan | beef | No |
| pattyQty | Number of patties | int | 1 - 3 | 1 | No |
| pattyWeightG | Patty weight in grams | number | 150, 200, 300 | 150 | No |
| pattyCook | Patty doneness | string | R, M, MR, WD | M | No |
| bunType | Type of the bun | string | plain, sesameSeed, wholeWheat, brioche, pretzel, potato | Classic | No |
| condiment1, condiment2, condiment3 | Types of condiments. Up to 3 are allowed. | string | ketchup, secretSause, thousandIsland, hotSauce, dijonMustard |  | No |
| topping1, topping2, topping3 | Types of toppings. Up to 3 toppings are allowed. | string | lettuce, pickles, onion |  | NO |

#### Sides Definition

The parameters and values for the `sides` object are as follows:

| Property | Description | Data Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| side1 | 1st side dish | 'side' object | See [Sides Internal Objects](#sides-internal-objects) below. If this 'side' is not ordered, Null is passed for its "type" property. |  | Yes |
| side2 | 2nd side dish | 'side' object | See [Sides Internal Objects](#sides-internal-objects) below. If this 'side' is not ordered, Null is passed for its "type" property. |  | Yes |

#### Sides Internal Objects:

| Property | Desription | Data Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| type | Name of side dish. If "None" is passed, this side wil be ommited. | string | frenchFries, mashedPotatoes, rice, homeFries |  | Yes |
| size | Size of the dish | string | small, medium, large | medium | No |

#### Drink Definition:

| Property | Desription | Data Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| type | Name of the drink | string | coke, fanta, sprite |  | Yes |
| size | Size of the drink | string | small, medium, large | small | No |
| ice | With or without ice | boolean | TRUE, FALSE | TRUE | No |


### Request Example

`curl -H "Content-Type: application/json" -X POST -d`

### Response Example

``` JSON
{
	  "burger": {
		"pattyType": "vegan",		
		"pattyCook": "M",
		"bunType": "plain",
		"condiment1": "thousandIsland",
		"condiment2": "secretSause",
		"topping1": "lettuce",
		"topping2": "pickles",		
	},
	"sides": {
		"side1": {
			"type": "rice",
			"size": "null"
		},
		"side2": {
			"type": "none",
			"size": "null"
		}
	},
	"drink": {
		"type": "coke",
		"size": "medium",
		"ice": true
	}

}
```

### Response Codes:

| **Code** | **Status** | **Description** |
|---|---|---|
| 200 | OK | Meal successfully ordered. |
| 315 | Order modification required | The order has been processed, but it cannot be completed in its current state. This may happen if some items in the order are not currently in stock. |
| 400 | Bad request | Meal order request failed. Check for invalid options. |
| 535 | General error | Something else went wrong. Generic error. |
