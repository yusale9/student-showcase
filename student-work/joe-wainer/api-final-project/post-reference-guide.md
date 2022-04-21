# POST Reference Guide
POST is used to send commands to the server. The burger JSON object is included in the POST request which is sent to the kitchen. When an OK response is received, the order is printed in the kitchen so the kitchen staff can start cooking the order. 

# POST/burgerMeal/burger Query Parameters

| Name | Description | Default Value | Data Type | Required |
| --- | --- | --- | --- | --- |
| pattyType | The type of patty. Either “beef”, “chicken”, “vegetarian”. | beef | string | Yes |
| pattyQty | Number of patties. Either 1 or 2.  | 1 | integer | Yes |
| pattyWeightG | Weight of the patty in grams. Either 150, 200, or 300.  | 200 | integer | Yes |
| pattyCook | Degree of doneness. Either “R” (rare), "MR" (medium rare), "M" (medium), "D" (done), "WD" (well done). | “M” | string | Yes |
| bunType | Type of bun. Either “white”, “wholeWheat”, “glutenFree”. | “white” | string | Yes |
| condiment1 | First condiment. Either “none”, “ketchup”, “mayonnaise”, “secretSauce” | “none” | string | No |
| condiment2 | Second condiment. Either “none”, “ketchup”, “mayonnaise”, “secretSauce” | “none” | string | No |
| topping1 | First topping. Either “none”, “friedOnions”, “mushrooms”, “friedEgg”, “lettuce”, “tomato”, “pickles”. | “lettuce” | string | Yes |
| topping2 | Second topping. Either “none”, “friedOnions”, “mushrooms”, “friedEgg”, “lettuce”, “tomato”, “pickles”. | “tomato” | string | Yes |
| topping3 | Second topping. Either “none”, “friedOnions”, “mushrooms”, “friedEgg”, “lettuce”, “tomato”, “pickles”. | “Pickles” | string | Yes |
| topping4 | Second topping. Either “none”, “friedOnions”, “mushrooms”, “friedEgg”, “lettuce”, “tomato”, “pickles”. | “none” | string | No |

# POST/burgerMeal/sides Query Parameters

| Name | Description | Default Value | Data Type | Required |
| --- | --- | --- | --- | --- |
| type | The side order for the meal. Either “frenchFries”, “onionRings”, “salad”, “none”. | “none” | string | No |
| size | Size of the side order. Either “small”, medium”, “large”.  | “medium” | string | No |

# POST/burgerMeal/drink Query Parameters

| Name | Description | Default Value | Data Type | Required |
| --- | --- | --- | --- | --- |
| type | The drink for the meal. Either “waterBottle”, “coke”, “lemonade”. | “coke” | string | No |
| size | Size of the drink. Either “small”, medium”, “large”.  | “medium” | string | No |

## Example

### Request

```json
{
   "mealType":"lunch",
   "mealCat":{
      "main":"burgerMeal",
      "burger":{
         "pattyType":"”beef”",
         "pattyQty":1,
         "pattyWeightG":300,
         "pattyCook":"MR",
         "bunType":"wholeWheat",
         "condiment1":"ketchup",
         "condiment2":"secretSauce",
         "topping1":"lettuce",
         "topping2":"pickles",
         "topping3":"None",
         "topping4":"None"
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
         "ice":"yes"
      }
   }
}
```

### Response

```http
200 OK
```
