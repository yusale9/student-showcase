# POST/lunch  

Method | syntax
----- | ----------
POST | URL/{lunch}


## Description
Sends your order to the server in the kitchen.


### Query Parameters

Name | type | Req. | Description
---- | ----- | ----- | --------------------
mealType | string | Y | The meal type. For POC stage, includes lunch and dinner. 
mealCat | string | Y | The meal category. For POC stage, includes only "burgermeal".
{burger} | object |  Y | The burger object.
pattyType | string |  Y | The patty type. Can be "Black angus beef", or "veggie".
pattyQty | integer |  Y | The number of burger patties per meal. The maximum value is 2. The default value is 1. 
pattyWeightG | float |  Y | The weight of you burger patty in pounds (lb). The default value is 0.5. If you order a kids burger meal the value is 0.3.
pattyCook | string |  Y | The  name of the cook who prepared your patty. 
bunType | string |  Y | The bun type. Can be "brioche", or "gluten-free". 
condimentn | string |  Y | The nth condiment of your choice. Can be "ketchup", "mustard", "mayonnaise", "Barbecue Sauce" or "none". You can have up to 2 condiments (condiment1 and condiment2). If you choose "none" for condiment1, condiment2 is an empty string "". 
toppingn | string |  Y | The nth topping of your choice. Can be "bacon", "cheddar", "onion", "lettuce", "pickles", "fried eggs", or "none".  If you choose "none" for toppingn, toppingn+1 is an empty string "". 
{sides} | object |  Y | Contains the side dishes that come with your burger. The maximum value is 2.
{siden} | object |  Y | The nth side. 
{sides}{siden)type | string | Y | The type of side. Can be "frenchFries", "sweetPotatoFries", "Coleslaw", "taterTots", "blackBeans", "coleslaw", "carrotsCelerySticks" or "none".
{sides}{siden}size | string |  Y | The size of the side. Your side dish can be "small" or "large". If you choose "none" for type, the default value is an empty string "". 
{drink} | object |  Y | Your drink of choice. 
{drink}type | string |  Y | The type of drink. Can be "Coke", "CokeZero", "7Up", "7UpZero", "CanadaDryGingerAle", "bottledWater", or "none".
{drink}size | string |  Y | side of the drink. Can be "small", "medium", or "large". If you choose "none" for a drink, the default value is an empty string "".

### HTTP Status Codes

Status Code | Status Text | Description
---- | ----- | ----- 
200 | OK |  Your meal was successfully ordered. 
413 | Content Too Large |  You ordered too many burgers. The cook cannot handle your request.
503 | Service Unavailable |  Our kitchen is overloaded with orders.


## Examples

### Request

```curl
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

### Response

```HTTP
200 OK
```



