###GET /meal

##HTTP Responses

#Status Type Code 
| Status            | Type   | Code Description          |
|-------------------|--------|---------------------------|
| 200 - OK          | string | Order is correct.         |
| 400 - Bad Request | string | Meal ordered is incorrect |

GET Retrieve the currently available meal Retrieves the meal that is available at the current time.

#GET /meal

Arguments (Query Parameters) There are no arguments.

#Response Parameters


| #Parameter   |#Data type| #Required? |#Description |
|--------------------------------------------------------------------------------
|                                                                                  
|                                  | 
| | PattySize  | string | Required | L, M, or S 
| | BurgerCook | string | Required | LE, Phil                                    | 
| | BunType    | string | Required | Seeded, Regular, or glutenFreeBun           | 
| | Fixing1    | string | Required | Lettuce, Tomato, Onion or “None”            | 
| | FriesType  | string | Required | RegularFries, “ SweetPotatoFries” or “None” | 
| | DrinkType  | string | Required | Coke, Sprite, Sprite Zero, “Ice Tea”        | 

curl -X GET http://URL/tableNo?id=99

```{ 
    "orderNum":854, "timestamp":"2023-10-15T08:00:50-05:00", 
"Item1":
{ 
    
 "ItemOrdered":
 "PattySize":"M", 
"BunType":"Regular", 
"BurgerCook":"LE", 
"Fixing1":"Lettuce",”Tomato”,”Onion”, 
“Cost”:35.00 } },

}
 "Total":{ "Cost":35.00 }

 }
 }```