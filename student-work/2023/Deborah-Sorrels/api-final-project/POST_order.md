# POST: Order Documentation 

## POST Burger Value Meal Order

The POST request processes orders for the burger value meal and sends the information to the cook for preparation.  

## Sample JSON Code Snippet  

The code confirms the order selections.  

### Request Command URL 

```
curl -H "Content-Type: application/json" -X POST -d'  
```
### Value Meal Code 
```
{
"mealType": "lunch",
"mealCat": "burgerValueMeal",
"burger": {
"pattyType": "beef",
"pattyQty": 1,
"pattyWeightG": 220,
"pattyCook": "MR",
"bunType": "wholeWheat",
"condiment1": "barbeque",
"condiment2": "garlicMayonaise",
"topping1": "tomato",
"topping2": "pickles",
"topping3": "friedMushrooms"
},
"sides": {
"side1": {
"sideType": "sweetPotatoFries",
"sideSize": "medium"
},
"side2": {
"sideType": "coleslaw",
"sideSize": "medium"
}
},
"drink": {
"drinkType": "coke",
"drinkSize": "large",
"ice": true
}
}
```

### Response Code 

```
200 OK  
400 Bad Request  
500 Internal Server Error   
503 Service Unavailable
```

## Code Explanation 

### Meal Type  

Property Type | Data Type | Value | Description 
------------- | --------- | ----- | -----------  
mealType | string | "lunch" , "dinner" | Meal type.   
mealCat | string | burgerValueMeal | Meal category.  

### Burger Order 

Property Type | Data Type| Value | Description | Default  
------------- | --------- | ----- | ---------- | -------  
pattyType | string | "beef" , "lamb" , "vegan" , "chicken" , "turkey" | Type of meat. | "beef"  
pattyQty | interger | 1, 2, 3 | Number of patties ordered. | 1  
pattyWeightG | interger | 160, 220, 280 | Size of patties in grams. | 220  
pattyCook | string | "R", "MR", "M", "MW", "W" | How well the meat is cooked. | MW  
bunType | string | "classicHamburgerBun", "sesameSeedBun", "wholeWheatBun", "ciabattaBun", "briocheBun", "pretzelBun", "potatoRoll", 'sourdoughBun", glutenFreeBun", "lettuceWrap" | Bun type. | "classicHamburgerBun"  
condiment1 | string | "Mayonaise", "garlicMayonaise", "spicyMayonaise", "ketchup", "barbequeSauce", "mustard" | Condiment options. | "mayonaise"  
condiment2 | string | "Mayonaise", "garlicMayonaise", "spicyMayonaise", "ketchup", "barbequeSauce", "mustard" | Condiment options. Limit of two.| "ketchup"
topping1 | string | "lettuce", "tomato", "pickles", "slicedOnions", "choppedOnions", "friedOnions", "friedMushrooms", "freshMushrooms", "friedEgg", "roastedCornBeef", "onionJam", "veganCheddar", "garlicConfit", "jalepenoPepper"  | Topping options. Limit of three. | "ketchup"   
topping2 | string | "lettuce", "tomato", "pickles", "slicedOnions", "choppedOnions", "friedOnions", "friedMushrooms", "freshMushrooms", "friedEgg", "roastedCornBeef", "onionJam", "veganCheddar", "garlicConfit", "jalepenoPepper"  | Topping options. Limit of three. |  "slicedOnions"  
topping3 | string | "lettuce", "tomato", "pickles", "slicedOnions", "choppedOnions", "friedOnions", "friedMushrooms", "freshMushrooms", "friedEgg", "roastedCornBeef", "onionJam", "veganCheddar", "garlicConfit", "jalepenoPepper"  | Topping options. Limit of three. | "pickles"   

### Side Dish Options  

Property Type | Data Type| Value | Description | Default  
------------- | --------- | ----- | ---------- | -------  
side1 | string | "sweetPotatoFries", "traditionalFries", "greenSalad", "israeliSalad", "coleslaw", "puree", "onionRings", "guacamole" | Side dishes available.  Limit of 2. | "traditionalFries"  
side2 | string | "sweetPotatoFries", "traditionalFries", "greenSalad", "israeliSalad", "coleslaw", "puree", "onionRings", "guacamole" | Side dishes available.  Limit of 2. | "greenSalad" 
sideSize | string | "small", "medium", "large" | Size of side dish. | "medium"  

### Drink Options  

Property Type | Data Type| Value | Description | Default  
------------- | --------- | ----- | ---------- | -------  
drink | string | "coke", "cokeZero", "dietCoke", "sprite", "dietSprite", "orangeJuice", "lemonade", "appleCider", gingerAle" | Type of drink. | "coke"  
drinkSize | string | "small", "medium", "large" | Size of drink. | "meidum"  
ice | boolean | true, false | Does the customer want the drin with ice? | true  












































