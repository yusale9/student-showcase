# POST Meal (Lunch)
This command is to process the order and is sent to the Kitchen. After an OK response is received, the client's order is printed in the kitchen, so the cook can begin cooking.  
This consists of a POST Request and POST Response

# List of Meal Items 
|Name|Value| Description|Default Value|Data Type|R/O*|
|---|---|---|---|---|---|
|Patty type|Beef, chicken, lamb or vegan|Choice of the patty|Beef|string|R|  
|Burger size|160g, 220g or 300gm|Weight of the Burger|220g|Integer|R|
|Bread type|White, whole wheat, multigrain or gluten free|Type of bread|white|string|R|
|Cook level|medium, rare or well done|how much the patty needs to be cooked|well done|string|R|
|Condiments|ketchup, mustard, Mayonnaise, barbeque sauce or hot sauce|what condiments the client would like|ketchup|string|O|
|Toppings|fried onions, fried mushrooms, fried egg or none|whether the client would like a topping on his burger|none|string|O|
|Sides|french fries, onion rings, salad, green beans, none|which sides would the client like|french fries|string|O|
|Side Size|medium, large and extra large|The size of the side dish|medium|string|O|
|Drinks|cola regular or zero, sprite, fanta, water, iced tea, soda, apple juice and grape juice|choice of the drink the client would like with his meal|cola regular|string|R|
|Drink size|medium, large or extra large|which size would the client like for his drink that is from the fountain and not a bottled drink|medium|string|O|
|Ice in drink|true,false|request for ice or no ice in the drink|True|boolean|O|
|Extras|fried cauliflower, sweet potato chips, chicken wings or chicken nuggets|if the client would like an extra side dish|none|string|O|

*R/O = Required/Optional

# POST Response 
When the placed order is correct, the server sends an acknowlegment reply to the app. 

200 OK  

# POST Request (JSON object)
curl -H "Content-Type: application/json" -X POST -d'  

```JSON

   "mealType":"lunch",
   "mealCat":{
  	"main":"burgerMeal",
  	"burger":{
     	"pattyType":"beef",
     	"pattyQty":1,
     	"pattyWeightG":220,
     	"pattyCook":"WD",
     	"bunType":"White",
     	"condiment1":"ketchup",
     	"condiment2":"Barbeque Sauce",
     	"topping1":"lettuce",
     	"topping2":"pickles",
     	"topping3":"Fried Onions",
     	"topping4":"None",
  	},
  	"sides":{
     	"side1":{
        	"type":"frenchFries",
        	"size":"large"
     	},
     	"side2":{
        	"type":"none",
        	"size":""
     	}
  	},
  	"drink":{
     	"type":"Coke",
     	"size":"large",
     	"ice":true
  	}
        "Extras":{
        	"type":"none",
        	"size":""
}
},

