

### POST
| Method  | syntax       |
|---|---|
| POST  |URL/[burgermeal}|


### Description
Sends your order to the server in the kitchen.

### Query Parameters

| Name  | Type  | Req  | Description  |
|---|---|---|---|
|mealType | string  | Y  | The POC stage includesa burgermeal.  |
|mealCat  | string  | Y  | The POC stage includes only a burgermeal.  |
|{burger}  | object  | Y  | The burger object.  |
|pattytype  | string  | Y  | Can be beef or veg.  |
|pattyQty   | integer  | Y  | the number of burgers per meal. The maximum value is 2. The default value is 1.  |
|pattyWeight   | float  |Y   | The weight of the burger patty in grams (kg).The default value is 200gr.A kiddie's burger meal value is 100gr.  |


| Name  |Type   | Req  |Description   |
|---|---|---|---|
| pattycook  | string  | Y  |The name of the cook who prepared your patty.   |
| bunType  | string  | Y  | The bun type can be "regular" or "gluten-free".  |
| condimentn  | string  | Y  | The nth condiment of your choice. Can be "ketchup", "mayonnaise",, "barbeque sauce" or "none". One can choose up to three condiments (condiment1, condiment2 or condiment3). It will be an empty string if you choose "none"" |
|toppingn  | string  | Y  |The topping of your choice. Can be "onion", "lettuce", "tomato", or "none". Choosing"none" for "toppingn", toppingn+1 is an empty string ""    |
| {pattys}{pattyn}type  | string  | Y  | How many pattys. Can be 1 or 2  |


### HTTP Status Codes
|Status Code   | Status Text  | Description  |
|---|---|---|
| 200  | OK  |  Meal successfully ordered |
| 413  | too large  | Order is too large  |
| 503  | Unavailable  |Service unavailable   |

### Request
``` curl
curl -H "Content-Type: application/json" -X POST -d'
{
	"mealType": "burger",
	"mealCat": "burgerMeal",
	"burger": {
		"pattyType": "beef",
		"pattyQty": 1,
		"pattyWeightG": 200,
		"pattyCook": "LE",
		"bunType": "regular",
		"condiment1": "ketchup",
		"condiment2": "mayonnaise",
		"topping1": "lettuce",
		"topping2": "tomato",
		"topping3": "onion"
	},
	
	}
}
```

### Response
200 OK

