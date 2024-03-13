# Order lunch
Sends the meal order to the kitchen. 

Method | syntax
----- | ----------
POST | "http://api.gphd.net/lunch/burgerMeal

### PATH PARAMETERS

Name | type | Required | Description | Default 
---- | ----- | ----- | -------------------- | ---
mealType | string | Y |  The type of meal. Currently, only lunch is available. 
mealCat | string  | Y | The meal category. Currently, only burgerMeal is available. 

### REQUEST BODY SCHEMA: application/json

#### Burger object
Name | type | Required | Description | Default 
---- | ----- | ----- | -------------------- | ---
pattyType | string | N | The type of patty. Options include beef, blackBean, chicken, and vegetarian. | beef | 
pattyWeightGr | int  | N | The patty weight in grams. Options include 100, 200, and 300. | 100 |
pattyCook | string | N |  How the patty is cooked. Options include rare, mediumRare, mediumWell, and wellDone.| mediumWell|
bunType | string  | N | The type of bun, or none, for no bun. Bun types include white, wholeWheat, sourdough, and glutenFree. | white | 
condiment1 | string | N |  First choice of condiment. Options include ketchup, bbqSauce, garlicMayonnaise, mayonnaise, mustard, honeyMustard, thousandIsland, ranchDressing, and none | ketchup |
condiment2 | string | N |  Second choice of condiment. Options include ketchup, bbqSauce, garlicMayonnaise, mayonnaise, mustard, honeyMustard, thousandIsland, ranchDressing, and none | none |
topping1 | string  | N | First choice of topping. Options include pickles, onion, lettuce, tomato, jalapeno, sauteedOnions, relish, and none | none |
topping2 | string  | N | Second choice of topping. Options include pickles, onion, lettuce, tomato, jalapeno, sauteedOnions, relish, and none | none |
topping3 | string  | N | Third choice of topping. Options include pickles, onion, lettuce, tomato, jalapeno, sauteedOnions, relish, and none | none |
extraTopping | string | N | Choice of extra topping. Options include cornBeef, pastrami, pulledeeBf, oneEgg, and twoEggs | none |

#### Side object
Name | type | Required | Description | Default 
---- | ----- | ----- | -------------------- | ---
type | string | N |  Choice of side. Options include frenchFries, onionRings, sweetPotatoFries, spicyFries, coleSlaw, sideSalad, and none. | frenchFries |
size | string | N |Size of side order. Options include medium and large. | medium |

#### Drink object
Name | type | Required | Description | Default 
---- | ----- | ----- | -------------------- | ---
type | string  | N | Type of drink. Options include coke, dietCoke, sprite, iceTea, orangeJuice, appleJuice, mangoNectar, peachNectar, and none | coke |
size | string | N |  Size of drink. Options include small, medium, large, and xLarge. | medium |
ice | boolean  | N | With or without ice. Options include true=with ice, false=without ice. | true |

<!-- Replace the two example rows and include rows for all your parameters. -->
<!-- If one of the parameters has a set of sub-parameters, create a table or bulleted list for that, but proceed with caution. If the API is complex, there might be an easier way to do your reference section than writing markup by hand. -->

## Examples

### Request

Include the authorization header using the following structure. For more information about Authentication, see the [ReadMe](https://github.com/Schnee18/student-showcase/blob/main/student-work/2023/Sharon-Schnee/api-final-project/readme.md) file.

```
curl --request GET https://api.gphd.net/lunch/burgermeal
--header 'Content-Type: application/json'
--header 'Authorization: Bearer ImahFWLZWFdD8VVcUtIED2YuOjPFlZpldQTE5tUqKdv'
```

``` JSON
{
	"mealType": "lunch",
	"mealCat": "burgerMeal",
	  "burger": {
		"pattyType": "beef",
		"pattyQty": 1,
		"pattyWeightG": 300,
		"pattyCook": "mediumRare",
		"bunType": "wholeWheat",
		"condiment1": "ketchup",
		"condiment2": "bbqSauce",
		"topping1": "tomato",
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
		"type": "coke",
		"size": "large",
		"ice": true
	}

}

```

### Response

When a correct order is placed, the server replies to the app with an acknowledgment. This is not displayed to the user. 

```
200 OK

```

### Response status codes

| Status code |  Description          |
|-------------|----------------------|
| `100 - Initial request received` | That's a good start, let's keep going. |
| `200 - OK` | Request successful. Enjoy your meal. |
| `400 - Bad Request`       | Request failed. Check your request and try again. |
| `500 - Internal Server Error`  | Server error. Please contact the server administrator.  |

