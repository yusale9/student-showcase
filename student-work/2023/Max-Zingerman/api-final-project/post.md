# POST /meal/burgerMeal

### Description:
Send a new burger meal order to the kitchen.

### HTTP Method:
POST

### Parameters:
A single 'burgerMeal' JSON object.  
This object contains all the items ordered within this meal. It is composed of some other JSON objects, as listed below:

#### Burger Meal Definition

The parameters and values for the `burgerMeal` object are as follows:

| Property | Description | Data Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| burger | Type of the burger | 'burger' object | See burger object documentation. |   | Yes |
| sides | The two side dishes.   Two side dishes is the standard for this meal. | 'sides' object. It has two properties, both of them are 'side' objects:  side1 & side2. | See [Sides Definition](#sides-definition) documentation. If no sides are choosen, Null is passed for each 'side'   object. |  | Yes |
| drink | Type of drink | drink' object. | See 'drink' object documentation |   | No |

#### Burger Definition

The parameters and values for the `burger` object are as follows:


| Property | Description | Data Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| pattyType | Patty type of the   burger | string | beef, chicken, vaggie | beef | No |
| pattyQty | Number of patty units | int | 1 - 3 | 1 | No |
| pattyWeightG | Patty weight (Grams) | number | 150, 200, 300 | 150 | No |
| pattyCook | Patty cook level | string | R, M, MR, WD | M | No |
| bunType | Type of the bun | string | classisc,  sameSeed, wholeWheat, brioche | Classic | No |
| condiment1,   condiment2, condiment3 | Types of  condiments. Up to 3  are allowed. | string | ketchup, secretSause,   hotSauce, Dijon Mustard, salsa |  | No |
| topping1,   topping2, topping3 | Types of toppings. Up to 3   toppings are allowed. | string | lettuce, pickles, onion |  | NO |

#### Sides Definition

The parameters and values for the `sides` object are as follows:

| Property | Description | Data   Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| side1 | 1st side dish | side' object | See 'side' object   documentation. If this 'side' is not ordered, Null must be substituted in   it's "type" property. |  | Yes |
| side2 | 2cd side dish | side' object | See 'side'   object documentation. If this 'side' is not ordered, Null must be substituted   in it's "type" property. |  | Yes |

#### 'side' object:

| Property | Desription | Data Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| type | Name of side dish. If   "None" is passed, this side wil be ommited. | string | frenchFries,   smashedPotatoes, rice, homeFries |  | Yes |
| size | Size of the dish | string | small, medium, large | medium | No |

#### 'drink' object:

| Property | Desription | Data Type | Values | Default | Mandatory |
|---|---|---|---|---|---|
| type | Name of the drink | string | coke, fanta, kinley |  | Yes |
| size | Size of the drink | string | small, medium, large | small | No |
| ice | With or without ice | boolean | TRUE, FALSE | TRUE | No |


### Request Example

`curl -H "Content-Type: application/json" -X POST -d`

### Response Example

``` JSON
{
	  "burger": {
		"pattyType": "beef",		
		"pattyCook": "WD",
		"bunType": "sesameSeed",
		"condiment1": "ketchup",
		"condiment2": "salsa",
		"topping1": "lettuce",
		"topping2": "onion",		
	},
	"sides": {
		"side1": {
			"type": "homeFries",
			"size": "null"
		},
		"side2": {
			"type": "none",
			"size": "null"
		}
	},
	"drink": {
		"type": "coke",
		"size": "large",
		"ice": true
	}

}
```

### Response Codes:

| **Code** | **Status** | **Description** |
|---|---|---|
| 200 | OK | Meal successfully ordered  |
| 306 | Order modification required | The order was processed but cannot  be fulfilled as is. This may happen if some of the ordered items are missing from the inventory. |
| 400 | Bad request | There is an error in the request. It may be a syntax error or a violation of the burger meal specifications. |
| 501 | General error | Something else went wrong. Generic error. |




