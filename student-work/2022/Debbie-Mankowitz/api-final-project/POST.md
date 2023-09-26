### POST

|Method     |  syntax        |
|POST       |URL/{burgermeal}|

### Description
Sends your order to the server in the kitchen.

### Query Parameters

Name              | Type        | Req  |     Description
mealType          | string	    |   Y  |     The meal type. For POC stage includes burgermeal.
mealCat           | string	    |   Y	 |     The meal category. For POC stage includes only "burgermeal".
{burger}          | object      |	  Y	 |     The burger object.
pattyType         | string      |	  Y	 |     The patty type. Can be "Beef" or "vegetarian".
pattyQty          | integer	    |   Y  |     The number of burger patties per meal. The maximum value is 2. The default value is 1.
pattyWeightG      |	float	      |   Y  |	    The weight of the burger patty in grams (kg). 
                                        The default value is 200gr. A kiddie burger meal value is 100gr


Name                  |  Type        | Req  |     Description
pattyCook	            | string	     |  Y	  |    The name of the cook who prepared your patty.
bunType	              | string	     |  Y	  |    The bun type. Can be "regular" or "gluten-free".
condimentn	          | string	     |  Y	  |    The nth condiment of your choice. 
                                                 Can be "ketchup," "mayonnaise," "barbecue Sauce," or "none." 
                                                 You can have up to 3 sauces (sauce1, sauce2 or sauce3). 
                                                 If you choose "none" for sauces, it is an empty string "".
toppingn              | string	      |   Y  |	     The topping of your choice. 
                                                Can be "onion", "lettuce", "pickles", "tomato", or "none". 
                                                If you choose "none" for toppingn, toppingn+1 is an empty string "".
{pattys}{pattyn}type  | string       |	 Y	 |    How many pattys. Can be 1 or 2.


### HTTP Status Codes
Status Code	| Status Text |	Description
200	        |     OK	    | The meal was successfully ordered.
413         | Too large   | The order is too large
503         | Unavailable | Service unavailable or overloaded

### Request
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

### Response
200 OK

