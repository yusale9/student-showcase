# POST Request: BurgerMeal

## Table of Contents
1. [Description](#description)
2. [burgerMeal](#burgerMeal)  
2.1. [burger](#burger)  
2.2. [sides](#sides)  
2.3. [drinks](#drinks)
3. [Examples](#examples)  
3.1. [Request](#request)    
3.2. [Response](#response)  
3.3. [Errors](#errors)    

## Description

This POST request is for ordering a burger meal out of the meal categories. 

### burgerMeal 
Each burger meal consists of the burger, side dishes, and a drink.

### burger   
Each burger includes a patty, a bun, condiments, toppings, and specials. A customer can order up to 3 condiments, 3 toppings, and 2 specials.

Name | Type | Req. | Description | Default Option | Available Options
-----|------|------|-------------|----------------|------------------
pattyType | string | Y | the patty you ordered | beef | <ul><li>beef</li><li>lamb</li><li>vegan</li></ul>
pattyQty | int | Y | the amount of patties per meal | 1 |  1-3 |
pattyWeightG | int | Y | the size of the patty in grams | 220 | <ul><li>220</li><li>440</li></ul> 
pattyCook | string | Y | the level of cooking | well | <ul><li>rare</li><li>mR</li><li>medium</li><li>mW</li><li>well</li><li>wellDone</li></ul>
bunType | string | Y | the bun type | plain burger bun | <ul><li>none</li><li>ruralBurgerBun</li><li>plainBurgerBun</li><li>glutenFree</li><li>baguette</li><li>ciabetta</li></ul>
condiment1 | string | Y | the first condiment | none | <ul><li>none</li><li>ketchup</li><li>chiliSauce</li><li>BBQSauce</li><li>hummus</li><li>tahini</li><li>mayonnaise</li><li>garlicMayonnaise</li><li>chipotleSauce</li><li>secretSauce</li><li>chimichuri</li><li>pesto</li><li>mustard</li><li>viniagrette</li></ul>
condiment2 | string | N | the second condiment | none |
condiment3 | string | N | the third condiment | none |
topping1 | string | Y | the first topping | none | <ul><li>none</li><li>lettuce</li><li>tomato</li><li>pickles</li><li>redOnion</li><li>jalapenoPeppers</li><li>friedOnion</li></ul>
topping2 | string | N | the second topping | none | 
topping3 | string | N | the third topping | none |
specials1 | string | Y | the first special topping | none | <ul><li>none</li><li>finelyChoppedAsado</li><li>portobelloMushrooms</li><li>cornedBeef</li><li>avocado></li></ul>
specials2 | string | N | the second special topping | none

### sides
A customer can order up to two side dishes per burgerMeal. 
Name | Type | Req. | Description 
-----|------|------|--------------
side1| string | Y | the first side dish
side2| string | N | the second side dish  

Every side dish requires a type and size. Parameters are the same for both side dishes.
Name | Type | Req. | Description | Default Option | Available Options
-----|------|------|-------------|----------------|----------------
type| string |Y | the type of side dish | none | <ul><li>none</li><li>frenchFries</li><li>israeliSalad</li><li>caesarSalad</li><li>shukSalad</li><li>chickenNuggets</li><li>chickenWings</li></ul>
size| string | Y | the size of the side dish | medium (N/A if "type" is "none") | <ul><li>small</li><li>medium</li><li>large</li></ul>

### drinks
Each drink requires a type, size, and ice.
Name | Type | Req. | Description | Default Option | Available Options
-----|------|------|-------------|----------------|------------------
type | string | Y | the drink you ordered | none | <ul><li>none</li><li>mineralWater</li><li>soda</li><li>cocaCola</li><li>cocaColaZero</li><li>sprite</li><li>spriteZero</li><li>peachFlavoredWater</li><li>appleFlavoredWater</li><li>peachFuzeTea</li><li>grapeJuice</li><li>orangeJuice</li><li>maltBeer</li><li>tuborg</li><li>carlsberg</li></ul> 
size | string | Y | the size of the drink | medium | <ul><li>small</li><li>medium</li><li>large</li></ul>
ice | boolean | Y | option for ice in the drink | false | true/false

## Examples
### Request

```
curl -H "Content-Type: application/json" -X POST -d'
{
	"mealType": "lunch",
	"mealCat": "burgerMeal",
	"burger": {
		"pattyType": "beef",
		"pattyQty": 1,
		"pattyWeightG": 220,
		"pattyCook": "mR",
		"bunType": "plainBurgerBun",
		"condiment1": "ketchup",
		"condiment2": "secretSauce",
		"topping1": "lettuce",
		"topping2": "pickles",
		"topping3": "onion"
    "specials1": "none"
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
		"type": "Coke",
		"size": "large",
		"ice": true
	}

}



```

This was a POST request for a burgerMeal. The order included a single 220 gram medium-rare beef patty and a plain burger bun with 2 condiments, 2 toppings, and no specials. The order included a single side dish and an iced large coca cola. 

### Response

```
200 OK
```
# Errors
Status | Description
-------|------------
200 - OK | Order processed. Your lunch is on its way!
404 - Not Found | Where are we? Let's give it another try.
410 - Gone | Too late! We ran out earlier. Try something else or come back tomorrow.
500 - Internal Server Error | Our bad. It's the server. Try again.


