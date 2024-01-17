# Post Call/Command 
The POST call is used to create and process a customer's order. It consists of two parts:  
* The POST request (JSON object)
* The POST response (HTTP)
 
## Post Request (JSON object)  
* The POST request specifies the customer's choices which have been selected from the menu on the app. 
* The POST request is sent to the kitchen when the order is submitted.

### Code Snippet for POST Request  
* For the purposes of the POC, the "mealType" is limited to "lunch".
* For the purposes of the POC, the "mealCategory" is limited to "burger meal".
* Both the above properties, will be expanded in the future to include additional meal times and order items.
* Take-out orders, by default, are set to appear as tableNumber 99, to differentiate them from customers dining in.  
 ```
JSON   
curl -H "Content-Type: application/json" -X POST -d'  
{  
        "tableNumber":99,  
	"mealType": "lunch",  
	"mealCat": "burgerMeal",  
	  "burger": {  
		"pattyType": "beef",  
		"pattyQty": 1,  
		"pattyWeightG": 85,  
		"pattyCook": "M",  
		"bunType": "classic",  
		"condiment1": "classicKetchup",  
		"condiment2": "chilliSauce",  
                "condiment3": "classicMustard",  
		"topping1": "caramelizedOnions",  
		"topping2": "pickledSweetPeppers",  
		"topping3": "friedMushrooms"  
	},  
	"sides": {  
		"side1": {  
			"type": "classicFries",  
			"size": "medium"  
		},  
		"side2": {  
			"type": "creamyColeslaw",  
			"size": "medium"  
		}  
	},  
	"drink": {  
		"type": "coke",  
		"size": "large",  
		"ice": "yes"   
	}

}
```

### Properties Table for POST Request Code Snippet  
The POST request consists of various properties.  These properties are listed below according to their objects. 
#### JSON Objects 1: **Table Number, Meal Type, and Meal Category**  

| Property Name | Default Value         | Data Type | Mandatory | Description                                               | 
|---------------|-----------------------|-----------|-----------|-----------------------------------------------------------|  
| tableNumber   | 99              	| integer   |     Y     | Take-out orders are always specified by table number 99.  |  							
| mealType	| "lunch"	        | string    |     Y	| The type of meal served depending on the time of day.     |  
| mealCat	| "burgerMeal"          | string    |     Y     | The category defining the ordered meal.                   |  

#### JSON Object 2: **Burger**  
The various properties of the JSON object "burger" is listed below.  

| Property Name | Default Value         | Data Type | Mandatory | Description                                               | 
|---------------|-----------------------|-----------|-----------|-----------------------------------------------------------|  
| pattyType     | "beef"                | string    |     Y     | The type of patty based on key ingredients.               |  							
| pattyQty	| 1     	        | integer   |     Y	| The type of meal served depending on the time of day.     |   
| pattyWeightG  | 85     	        | integer   |     Y     | The weight of a single patty.                             |  							
| pattyCook	| "M"  	                | string    |     Y	| The degree of doneness to which the patty is cooked.      |  
| bunType	| "classic"             | string    |     Y     | The type of bun based on ingredients.                     |  
| condiment     | "none"                | string    |     N     | Choice limit of 3 from listed condiments.                 |  							
| topping	| "lettuceTomato"     	| string    |     N	| Choice limit of 4 from listed toppings.                   |  

#### JSON Object 3: **Sides**   
The various properties of the JSON object "sides" is listed below.  

| Property Name | Default Value         | Data Type | Mandatory | Description                                               | 
|---------------|-----------------------|-----------|-----------|-----------------------------------------------------------|  
| type          | "classicFries"        | string    |     N     | Types of additional listed side foods.                    |  							
| size   	| "medium" 	        | string    |     N	| The size of the servings of additional listed side foods. |  

#### JSON Object 4: **Drinks**   
The various properties of the JSON object "drinks" is listed below.

| Property Name | Default Value         | Data Type | Mandatory | Description                                               | 
|---------------|-----------------------|-----------|-----------|-----------------------------------------------------------|  
| type          | "coke"              	| string    |     N     | Take-out orders are always specified by table number 99.  |  							
| size    	| "medium"	        | string    |     N	| The type of meal served depending on the time of day.     |  
| ice    	| "yes"                 | string    |     N     | The category defining the ordered meal.                   |  

## POST Response (HTPP)  
* The POST response confirms receipt of the POST request.
* This means that when a correct order is placed, the server replies to the app with an acknowledgement.
* The acknowledgement is an OK status response code.  
* The order can then be printed in the kitchen so that the meal can be prepared.

| 200           |OK                                                                                                         | 
|---------------|-----------------------------------------------------------------------------------------------------------|  

#### HTTP Error Codes  
Error codes appear if an order is incorrect.

| Status        | Description                                                                                                | 
|---------------|------------------------------------------------------------------------------------------------------------|  
| 404           | Page Not Found                                                                                             |  
| 500           | Internal Server Error                                                                                      |  






