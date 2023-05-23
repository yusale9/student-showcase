# GET /meal


# HTTP Responses 

| Status          | Type     | Code Description                                      |
|----------------|----------|--------------------------------------------------|
| 200 - OK    | string  | Order is correct. |
| 400 - Bad Request | string | Meal ordered is incorrect |

## GET Retrieve the currently available meal 
Retrieves the meal that is available at the current time. 
## GET /meal 
Arguments (Query Parameters) 
There are no arguments. 

### Response Parameters

| Parameter name | Data type   | Required? | Description                          |
|------------------|--------|-----------|--------------------------------------|
| PattySize | string | Required  | "L", "M", or "S"|
| BurgerCook| string |  Required  |  "R", "MR", "M", or "WD" |
| BunType | string |  Required  |  "Seeded", "Plain", "ChiabattaBun", or "glutenFreeBun"|
| Fixing1| string |  Required  | "Lettuce", "Tomato", or "Pickle"|
| Fixing2| string |  Required  | "Lettuce", "Tomato", or "Pickle" |
| Fixing3| string |  Required  |  "Lettuce", "Tomato", or "Pickle"|
| FriesType| string |  Required  |  "RegularFries", "CurlyFries", or "SweetPotatoFries" |
| DrinkType| string |  Required  | "Cola", "Lemonade", or "RootBeer"|       
        

### Example

```
{Provide an example of the API request, filled with sample values.}
```
```
curl -X GET http://URL/tableNo?id=99
{
   "orderNum":123,
   "timestamp":"2023-02-12T07:44:45-05:00",
   "Item1":{
  	"ItemOrdered":{
     	"type":"mediumPatty",
        "type":"seedBun",
        "type":"mr",
        "type":"filling1",
        "type":"filling2",
        "type":"filling3",
     	"Cost":49.50
  	}
   },
   "Item2":{
  	"ItemOrdered":{
     	"type":"sweetPotatoFries",
     	"Cost":25.00
  	}
   }
 "Total":{
  	     	"Cost":74.50
  	}
   }




