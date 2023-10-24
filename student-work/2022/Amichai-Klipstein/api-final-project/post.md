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

<table>
  <tbody>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Req.</th>
      <th>Description</th>
      <th>Default Option</th>
      <th>Available Options</th>
    </tr>
    <tr>
      <td>pattyType</td>
      <td>string</td>
      <td>Y</td>
	<td>the patty you ordered</td>
	    <td>beef</td>
     <td>
	     <ul>
          <li>beef</li>
          <li>lamb</li>
	<li>vegan</li>
        </ul>
     </td>   
    </tr>
    <tr>
      <td>pattyQty</td>
      <td>int</td>
      <td>Y</td>
	    <td>the amount of patties per meal</td>
	    <td>1</td>
	    <td>1-3</td>
    </tr>
    <tr>
      <td>pattyWeightG</td>
      <td>int</td>
      <td>Y</td>
	    <td>patty size (grams)</td>
	    <td>220</td>
	    <td>
		     <ul>
          <li>220</li>
          <li>440</li>
        </ul>
	    </td>
    </tr>
    <tr>
	    <td>pattyCook</td>
	    <td>string</td>
	    <td>Y</td>
	    <td>level of cooking</td>
	    <td>well</td>
	    <td>
		     <ul>
          <li>rare</li>
          <li>mR</li>
	  <li>medium</li>
	<li>mW</li>
	<li>well</li>
	<li>well done</li>
        </ul>
	    </td>
    </tr>
	  <tr>
	  <td>bunType</td>
          <td>string</td>
          <td>Y</td>
          <td>bun type</td>
          <td>plain burger bun</td>
          <td>
          <ul>
            <li>none</li>
            <li>ruralButrgerBun</li>
            <li>plainBurgerBun</li>
            <li>glutenFree</li>
             <li>baguette</li>
            <li>ciabetta</li>
          </ul>
          </td>
	  </tr>
          <tr>
                  <td>condiment1</td>
                  <td>string</td>
                  <td>Y</td>
                  <td>first condiment</td>
                  <td>none</td>
                  <td>
                          <ul>
                                  <li>none</li>
                                  <li>ketchup</li>
                                  <li>chiliSauce</li>
                                  <li>BBQSauce</li>
                                  <li>hummus</li>
                                  <li>tahini</li>
                                  <li>mayonnaise</li>
                                  <li>garlicMayonnaise</li>
                                  <li>chipotleSauce</li>
                                  <li>secretSauce</li>
                                  <li>chimichuri</li>
                                  <li>pesto</li>
                                  <li>mustard</li>
                                  <li>viniagrette</li>
                          </ul>
                  </td>
          </tr>
          <tr>
                  <td>condiment2</td>
                  <td>string</td>
                  <td>N</td>
                  <td>second condiment</td>
                  <td>none</td>
                  <td>
                           <ul>
                                  <li>none</li>
                                  <li>ketchup</li>
                                  <li>chiliSauce</li>
                                  <li>BBQSauce</li>
                                  <li>hummus</li>
                                  <li>tahini</li>
                                  <li>mayonnaise</li>
                                  <li>garlicMayonnaise</li>
                                  <li>chipotleSauce</li>
                                  <li>secretSauce</li>
                                  <li>chimichuri</li>
                                  <li>pesto</li>
                                  <li>mustard</li>
                                  <li>viniagrette</li>
                          </ul>
                  </td>
          </tr>
          <tr>
                  <td>condiment3</td>
                  <td>string</td>
                  <td>N</td>
                  <td>third condiment</td>
                  <td>none</td>
                  <td>
                           <ul>
                                  <li>none</li>
                                  <li>ketchup</li>
                                  <li>chiliSauce</li>
                                  <li>BBQSauce</li>
                                  <li>hummus</li>
                                  <li>tahini</li>
                                  <li>mayonnaise</li>
                                  <li>garlicMayonnaise</li>
                                  <li>chipotleSauce</li>
                                  <li>secretSauce</li>
                                  <li>chimichuri</li>
                                  <li>pesto</li>
                                  <li>mustard</li>
                                  <li>viniagrette</li>
                          </ul>
                  </td>
          </tr>
          <tr>
                  <td>topping1</td>
                  <td>string</td>
                  <td>Y</td>
                  <td>first topping</td>
                  <td>none</td>
                  <td>
                          <ul>
                                <li>none</li>
                                <li>lettuce</li>
                                <li>tomato</li>
                                <li>pickles</li>
                                <li>redOnion</li>
                                <li>jalapenoPeppers</li>
                                <li>friedOnion</li>  
                          </ul>
                  </td>
          </tr>
          <tr>
                  <td>topping2</td>
                  <td>string</td>
                  <td>N</td>
                  <td>second topping</td>
                  <td>none</td>
                  <td>
                            <ul>
                                <li>none</li>
                                <li>lettuce</li>
                                <li>tomato</li>
                                <li>pickles</li>
                                <li>redOnion</li>
                                <li>jalapenoPeppers</li>
                                <li>friedOnion</li>  
                          </ul>
                  </td>
          </tr>
          <tr>
                  <td>topping3</td>
                  <td>string</td>
                  <td>N</td>
                  <td>third topping</td>
                  <td>none</td>
                  <td>
                            <ul>
                                <li>none</li>
                                <li>lettuce</li>
                                <li>tomato</li>
                                <li>pickles</li>
                                <li>redOnion</li>
                                <li>jalapenoPeppers</li>
                                <li>friedOnion</li>  
                          </ul>
                  </td>
          </tr>
        <tr>
          <td>specials1</td>
          <td>string</td>
          <td>Y</td>
                <td>first special topping</td>
                <td>none</td>
                <td>
                   <ul>
                           <li>none</li>
                           <li>finelyChoppedAsado</li>
                           <li>portobelloMushrooms</li>
                           <li>cornedBeef</li>
                           <li>avocado</li>
                   </ul>
                </td>
        </tr>
          <tr>
          <td>specials2</td>
          <td>string</td>
          <td>N</td>
                <td>second special topping</td>
                <td>none</td>
                <td>
                   <ul>
                           <li>none</li>
                           <li>finelyChoppedAsado</li>
                           <li>portobelloMushrooms</li>
                           <li>cornedBeef</li>
                           <li>avocado</li>
                   </ul>
                </td>
        </tr>
  </tbody>
</table>  

### sides
A customer can order up to two side dishes per burgerMeal. 
<table>
        <tbody>
                <tr>
                        <th>Name</th>
                        <th>Type</th>
                        <th>Req.</th>
                        <th>Description</th>
                </tr>
        <tr>
             <td>side1</td>
                <td>string</td>
                <td>Y</td>
                <td>first side dish</td>
        </tr>
        <tr>
             <td>side2</td>
                <td>string</td>
                <td>Y</td>
                <td>second side dish</td>
        </tr>
        </tbody>
</table>  

Every side dish requires a type and size. Parameters are the same for both side dishes.  
<table>
        <tbody>
        <tr>
                <th>Name</th>
                <th>Type</th>
                <th>Req.</th>
                <th>Description</th>
                <th>Default Option</th>
                <th>Availale Options</th>
           </tr>
                <tr>
                        <td>type</td>
                        <td>string</td>
                        <td>Y</td>
                        <td>type of side dish you ordered</td>
                        <td>none</td>
                        <td>
                         <ul>
                                 <li>none</li>
                                 <li>frenchFries</li>
                                 <li>israeliSalad</li>
                                 <li>caesarSalad</li>
                                 <li>shukSalad</li>
                                 <li>chickenNuggets</li>
                                 <li>chickenWings</li>
                         </ul>
                        </td>
                </tr>
                <tr>
                        <td>size</td>
                        <td>string</td>
                        <td>Y</td>
                        <td>side dish size</td>
                        <td>medium (n/a if type is "none")</td>
                        <td>
                                <ul>
                                        <li>small</li>
                                        <li>medium</li>
                                        <li>large</li>
                                </ul>
                        </td>
                </tr>
        </tbody>
</table>

### drinks
Each drink requires a type, size, and ice.
<table>
        <tbody>
                <tr>
                <th>Name</th>
                <th>Type</th>
                <th>Req.</th>
                <th>Description</th>
                <th>Default Option</th>
                <th>Availale Options</th>  
                </tr>
                <tr>
                        <td>type</td>
                        <td>string</td>
                        <td>Y</td>
                        <td>the drink you ordered</td>
                        <td>none</td>
                        <td>
                                <ul>
                                        <li>none</li>
                                        <li>mineralWater</li>
                                        <li>soda</li>
                                        <li>cocaCola</li>
                                        <li>cocaColaZero</li>
                                        <li>sprite</li>
                                        <li>spriteZero</li>
                                        <li>peachFlavoredWater</li>
                                        <li>appleFlavoredWater</li>
                                        <li>peachFuzeTea</li>
                                        <li>grapeJuice</li>
                                        <li>orangeJuice</li>
                                        <li>maltBeer</li>
                                        <li>tuborg</li>
                                        <li>carlsberg</li>
                                </ul>
                        </td>
                </tr>
                <tr>
                        <td>size</td>
                        <td>string</td>
                        <td>Y</td>
                        <td>drink size</td>
                        <td>medium</td>
                        <td>
                                <ul>
                                        <li>small</li>
                                        <li>medium</li>
                                        <li>large</li>
                                </ul>
                        </td>
                </tr>
                <tr>
                        <td>ice</td>
                        <td>boolean</td>
                        <td>Y</td>
                        <td>ice in the drink (optional)</td>
                        <td>false</td>
                        <td>true/false</td>
                </tr>
        </tbody>
</table>

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


