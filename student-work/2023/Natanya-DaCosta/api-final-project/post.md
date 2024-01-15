# Post Call/Command 
The POST call is used to create and process a customer's order. It consists of two parts:  
* The POST request (JSON object)
* The POST response (HTTP)
 
## Post Request (JSON object)  
* The POST request consists of the actual meal burger order which the customer selects from the app.
* The request is sent to the kitchen.
   
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
		"type": "coke",  
		"size": "large",  
		"ice": true  
	}

}

## Post Response (HTPP)  
* When a correct order is placed, the server replies to the app with an acknowledgement.
* When an OK response is received, the order is printed in the kitchen so that the meal can be prepared.



