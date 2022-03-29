# POST/lunch

The POST request is sent when an order is submitted. Current `"mealType"` is limited to lunch only for POC purposes and will be developed to include additional menu items. The burger meal JSON object is included in the below code snippet. 

```
curl -H "Content-Type: application/json" -X POST -d'{

"tableNumber":99,
"mealType":"lunch",
   "mealCat":{
  	"main":"burgerMeal",
  	"burger":{
     	"pattyType":"beef",
     	"pattyQty":1,
     	"pattyWeightG":100,
     	"pattyCook":"MR",
     	"bunType":"wholeWheat",
     	"condiment1":"ketchup",
     	"condiment2":"secretSauce",
     	"topping1":"lettuce",
     	"topping2":"pickles",
     	"topping3":"None",
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
```

## Code snippet explanation

The lunch burger meal consists of burger, bun, condiment, topping, side, and drink.
The take out orders are ordered on table `99` to differetciate them from eat-in customers. 
For the purpose of this POC the `"mealType"` is `"lunch"`, and the `"mealCat"` is `"burgerMeal"`. In the future, there will be variable values for breakfast and dinner, and for other type of meals.

| Property Name 	| Data Type 	| Values                 |Mandatory| Definition                           	|Value Variables|
|-----------------|-------------|------------------------|----------|--------------------------------------	|------------------|
| tableNumber     | int    	    | 99	                   |   Y   | Table number indicates take out option. Take out option is always ordered on table `99`.| This can be decided by the diner owners in the future.|
| mealType      	|  string    	|  "lunch"             	|  Y   	| Meal type depending on the hour. | "breakfast", "lunch", "dinner"|
| mealCat      	|  string    	|    "burgerMeal" |    Y   | Type of a meal ordered by a customer.| Future variables are set menu items.|

### Burger

`"burger"` is an object which is a part of the meal consisting of properties listed below. All properties are mandatory. All `"none"` values are valid wherever indicated in the Value Variables column. 


| Property Name 	| Data Type 	| Values                 |Mandatory | Definition                           	|Value Variables|
|-----------------|-------------|------------------------|----------|--------------------------------------	|----------------|
| pattyType       | string      | "beef"	               |   Y      | Type of patty. | "beef", "lamb", "chickenBreast", "fish", and "bean"|
| pattyQty        | int         | 1	                     |   Y      |Number of patties in the burger. Additional patties are at an extra cost. | 1, 2, and 3 |
| pattyWeightG    | int         | 100	                   |   Y      |Patty weight in grams. The price increases with weight.|100, 170, and 250|
| pattyCook       | string      | "MR"                   |   Y      |The way a patty is cooked.| "MR" medium-rare, "M" medium, "MW" medium-well, "WD" well-done. **Note:** chicken breast, fish and bean patty can only have "WD" well-done option.|
| bunType         | string      | "wholeWheat"	         |   Y      |Bun type to go with the burger.|"White", "wholeWheat", "Rye", "glutenFree", "None".|
| condiment1	| string 	| "ketchup"                |Y | Choice of 1st condiments (max 2 condiments)|  "mayo", "veganMayo","BBQ", "ketchup", "secretSauce". "none"|
| condiment2      | string      | "secretSauce"               |   Y      |Choice of the 2nd condiment (max 2 condiments)|  "mayo", "veganMayo","BBQ", "ketchup", "secretSauce". "none"|
| topping1        | string     | "lettuce"                 | Y           | Choice of 1st topping (max 4 toppings).| "lettuce", "pickles", "tomato", "cheese", "veganCheese", "friedEgg", "None".|
| topping2        | string     | "pickles"                 | Y           | Choice of 2nd topping (max 4 toppings) |"lettuce", "pickles", "tomato", "cheese", "veganCheese", "friedEgg", "None".|
| topping3        | string     | "None"                    | Y           | Choice of 3rd topping (max 4 toppings) |"lettuce", "pickles", "tomato", "cheese", "veganCheese", "friedEgg", "None".|
| topping4        | string     | "None"                    | Y           | Choice of 4th topping (max 4 toppings). Option ot add extra toppings at an extra cost.|"lettuce", "pickles", "tomato", "cheese", "veganCheese", "friedEgg","None".|

### Sides
Choice of 2 side orders per meal. When `"none"` is chosen for `"side1"`, the customer is not asked to choose `"side2"`. When `"none"` is chosen only for `"side2"`, string data shows size value as `"N/A"`.

| Property Name 	| Data Type 	| Values                 |Mandatory | Definition                           	|Value Variables|
|-----------------|-------------|------------------------|----------|--------------------------------------	|----------------|
| type            | string      | "frenchFries"	         |   Y      | Max 2 side orders. Extra can be orderd at an additional cost. | "frenchFries", "potatoWedges", "mashPotato", "salad", "onionRings", "none".|
| size            | string      | "large"                |  Y       | Size of the side order. Price vary depending on the size.| "small", "medium", "large".|

### Drink
Maximum 1 drink per meal with an option to order additional at an extra cost. If the value is `"none"` then string size data shows as `"N/A"`, and ice boolean data shows as `False`.

| Property Name 	| Data Type 	| Values                 |Mandatory | Definition                           	|Value Variables|
|-----------------|-------------|------------------------|----------|--------------------------------------	|----------------|
| type            | string      | "Coke"	          |   Y      |Drink to go with the meal. Max 1 drink per meal.| "Coke", "dietCoke", "Sprite", "orangeJuice", "appleJuice", "none"|
| size            | string      | "large"            | Y      | Size of the drink| "small", "medium", "large"|
| ice            | boolean      | true                | Y      |Option with or without ice in the drink. | true, false|
