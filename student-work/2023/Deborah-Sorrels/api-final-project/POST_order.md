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

Property Name | Data Type | Value | Description 
------------- | --------- | ----- | -----------  
mealType | string | "lunch" , "dinner" | Meal type.   
mealCat | string | burgerValueMeal | Meal category.  

### Burger Order 

Property Name | Data Type| Value | Description | Default | Mandatory/Optional   
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

Property Name | Data Type| Value | Description | Default | Mandatory/Optional   
------------- | --------- | ----- | ---------- | ------- | ------------------  
side1 | string | "sweetPotatoFries", "traditionalFries", "greenSalad", "israeliSalad", "coleslaw", "puree", "onionRings", "guacamole" | Side dishes available.  Limit of 2. | "traditionalFries" | Mandatory   
side2 | string | "sweetPotatoFries", "traditionalFries", "greenSalad", "israeliSalad", "coleslaw", "puree", "onionRings", "guacamole" | Side dishes available.  Limit of 2. | "greenSalad" | Optional 
sideSize | string | "small", "medium", "large" | Size of side dish. | "medium"  

### Drink Options  

Property Name | Data Type| Value | Description | Default | Mandatory/Optional   
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
"pattyCook": "MR",
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
“cook_id”: ”l2j23j9LKJsd”,
“priceBase”: “10.99”
"salesTax": "1.15
 “priceTotal”: “12.14” 
}
```

## Response Code Explanation  

Property Name | Data Type | Description  
------------- | --------- | -----------  
meal_type | string | Type of meal customer ordered, i.e., lunch or dinner.  
timestamp | date | The time that the meal was ordered.  
mealCat | string | Meal category. 
pattyType | string | Type of meat.  
pattyQty | interger | Number of patties ordered.  
pattyWeightG | integer | Size of patties in grams.  
pattyCook | string | How well the meat is cooked.  
bunType | string | Bun type.  
condiment1 | string | Condiment to add to the burger.  
condiment 2 | string | Condiment to add to the burger. 
topping1 | string | Topping to add to the burger.  
topping2 | string | Topping to add to the burger.  
topping3 | string | Topping to add to the burger.  
side1 | string | The side dish that was selected.  
side2 | string | The side dish that was selected.  
sideSize | string | The size of side dish that was selected.  
drink | string | The type of drink that was selected. 
drinkSize | string | The size of the drink that was selected. 
ice | boolean | Did the customer want ice or not?  
server | string | Name of waiter/waitress.  
server_id | uuid | The unique identifer of the waiter/waitress.  
cook | string | Name of the cook.  
cook_id | uuid | The unique identifer of the cook preparing the meal. 
priceBase | interger | The base price of the meal.  
salesTax | interger | Additional taxes added to the bill.  
priceTotal | interger | Total price of the meal.  


















































