# Post Call/Command 
The POST call is used to create and process a customer's order. It consists of two parts:  
* The POST request (JSON object)
* The POST response (HTTP)
 
## Post Request (JSON object)  
* The POST request consists of the actual meal burger order which the customer selects from the app.
* The request is sent to the kitchen.

### Code Snippet for POST Request  

  
curl -H "Content-Type: application/json" -X POST -d'  
{  
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

### Properties Table for POST Request  


| Property Name | Description | Default Value | Data Type | Mandatory / Optional |  
|---------------|-------------|---------------|-----------|----------------------|  


| Property Name | Description   | Default Value | Data Type | Mandatory/Optional |
|----------------|--------|-----------|------------------------------|
| {id}           | string | Required  | {Unique i            |
|                |        |           |                              |

## Post Response (HTPP)  
* When a correct order is placed, the server replies to the app with an acknowledgement.
* When an OK response is received, the order is printed in the kitchen so that the meal can be prepared.



