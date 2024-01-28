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

### Request Status Code 

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

Property Type | Data Type| Value | Description | Default | Mandatory/Optional   
------------- | --------- | ----- | ---------- | ------- | ------------------   
pattyType | string | "beef" , "lamb" , "vegan" , "chicken" , "turkey" | Type of meat. | "beef" | Mandatory   
pattyQty | interger | 1, 2, 3 | Number of patties ordered. | 1 | Mandatory   
pattyWeightG | interger | 160, 220, 280 | Size of patties in grams. | 220 | Mandatory    
pattyCook | string | "R", "MR", "M", "MW", "W" | How well the meat is cooked. | MW | Mandatory    
bunType | string | "classicHamburgerBun", "sesameSeedBun", "wholeWheatBun", "ciabattaBun", "briocheBun", "pretzelBun", "potatoRoll", 'sourdoughBun", glutenFreeBun", "lettuceWrap" | Bun type. | "classicHamburgerBun" | Mandatory 
condiment1 | string | "Mayonaise", "garlicMayonaise", "spicyMayonaise", "ketchup", "barbequeSauce", "mustard" | Condiment options. | "mayonaise" | Optional     
condiment2 | string | "Mayonaise", "garlicMayonaise", "spicyMayonaise", "ketchup", "barbequeSauce", "mustard" | Condiment options. Limit of two.| "ketchup" | Optional  
topping1 | string | "lettuce", "tomato", "pickles", "slicedOnions", "choppedOnions", "friedOnions", "friedMushrooms", "freshMushrooms", "friedEgg", "roastedCornBeef", "onionJam", "veganCheddar", "garlicConfit", "jalepenoPepper"  | Topping options. Limit of three. | "ketchup" | Optional   
topping2 | string | "lettuce", "tomato", "pickles", "slicedOnions", "choppedOnions", "friedOnions", "friedMushrooms", "freshMushrooms", "friedEgg", "roastedCornBeef", "onionJam", "veganCheddar", "garlicConfit", "jalepenoPepper"  | Topping options. Limit of three. |  "slicedOnions" | Optional   
topping3 | string | "lettuce", "tomato", "pickles", "slicedOnions", "choppedOnions", "friedOnions", "friedMushrooms", "freshMushrooms", "friedEgg", "roastedCornBeef", "onionJam", "veganCheddar", "garlicConfit", "jalepenoPepper"  | Topping options. Limit of three. | "pickles" | Optional  

### Side Dish Options  

Property Type | Data Type| Value | Description | Default | Mandatory/Optional   
------------- | --------- | ----- | ---------- | ------- | ------------------  
side1 | string | "sweetPotatoFries", "traditionalFries", "greenSalad", "israeliSalad", "coleslaw", "puree", "onionRings", "guacamole" | Side dishes available.  Limit of 2. | "traditionalFries" | Mandatory   
side2 | string | "sweetPotatoFries", "traditionalFries", "greenSalad", "israeliSalad", "coleslaw", "puree", "onionRings", "guacamole" | Side dishes available.  Limit of 2. | "greenSalad" | Optional 
sideSize | string | "small", "medium", "large" | Size of side dish. | "medium"  

### Drink Options  

Property Type | Data Type| Value | Description | Default | Mandatory/Optional   
------------- | --------- | ----- | ---------- | ------- | ------------------   
drink | string | "coke", "cokeZero", "dietCoke", "sprite", "dietSprite", "orangeJuice", "lemonade", "appleCider", gingerAle" | Type of drink. | "coke" | Mandatory   
drinkSize | string | "small", "medium", "large" | Size of drink. | "medium"  
ice | boolean | true, false | Does the customer want the drin with ice? | true | Optional  


## Sample JSON Code Response Snippet  

```
{ 
“meal_type”: “lunch”, 
“timestamp”: “2020-01-21T07:44:45-05:00”, 
"mealCat": "burgerValueMeal", 
"pattyType": "beef", 
"pattyQty": 1,
"pattyWeightG": 220,
"pattycook": "MR",
 "bunType": "wholeWheat",
"condiment1": "barbeque",
"condiment2": "garlicMayonaise",
"topping1": "tomato",
"topping2": "pickles",
"topping3": "friedMushrooms"
"side1": :sweetPotatoFries",
"sideSize": "meidum",
"side2": "coleslaw",
"sidSize": "medium",
"drink": "coke",
"drinkSize": "meidum",
"ice": true, 
“server”: ”Poppy”,
“server_id”:“aslkw0923CAE”, 
“cook”: ”Sam”, 
“cook_id”: ”l2j23j9LKJsd”, “price_base”: “10.99” 
 “price_total”: “10.99” 
}
```

## Response Code Explanation  

Property Name | Data Type | 












































