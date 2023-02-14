# API for the General Putnam Motel Diner


#### ExampleErrorType

| Status          | Type     | Code Description                                      |
|----------------|----------|--------------------------------------------------|
| 200 - OK    | string  | Order is correct. |
| 400 - Bad Request | string | Meal ordered is incorrect |

## GET Retrieve the currently available meal 
Retrieves the meal that is available at the current time. 
## GET /meal 
Arguments (Query Parameters) 
There are no arguments. 

#### Header parameters

| Parameter name | Data type   | Required? | Description                          |
|------------------|--------|-----------|--------------------------------------|
| largePatty | string | Required  | Large beef patty. |
| mediumPatty | string |  Required  | Medium beef patty.|
| smallPatty | string |  Required  |  Small beef patty. |
| r | string |  Required  |  Cooked rare. |
| mr | string |  Required  |  Cooked medium rare. |
| m | string |  Required  |  Cooked medium. |
| wd | string |  Required  |  Cooked well done. |
| seedBun | string |  Required  |  Seeded bun. |
| regularBun  | string |  Required  |  Regular bun. |
| chiabattaBun | string |  Required  | Chiabatta bun. |
| glutenFreeBun | string |  Required  |  {Gluten free bun.} |
| filling1| string |  Required  | Lettuce filling. |
| filling2 | string |  Required  | Tomato filling. |
| filling3 | string |  Required  |  Pickle filling. |
| fries | string |  Required  |  Fries side. |
| curlyFries | string |  Required  | Curly fries side. |
| sweetPotatoFries  | string |  Required  |  Sweet potato fries side. |
| cola  | string |  Required  | Cola drink. |
| lemonade  | string |  Required  |  Lemonade drink. |
| rootBeer | string |  Required  |  Root beer drink. |
        

### Request example

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




