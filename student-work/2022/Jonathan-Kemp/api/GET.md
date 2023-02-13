

#### Header parameters

| Parameter name | Data type   | Required? | Description                          |
|------------------|--------|-----------|--------------------------------------|
| {Large patty}   | 40 | Required  | {Large beef patty.} |
| {Medium patty}   | 30 |  Required  |  {Medium beef patty.} |
| {Small patty}   | 25 |  Required  |  {Small beef patty.} |
| {Seeded bun}   | 10 |  Required  |  {Seeded bun.} |
| {Regular bun}   | 8 |  Required  |  {Regular bun.} |
| {Chiabatta bun}   | 12 |  Required  |  {Chiabatta bun.} |
| {Gluten free bun}   | 10 |  Required  |  {Gluten free bun.} |
| {Lettuce}   | 9 |  Required  |  {Lettuce filling.} |
| {Tomato}   | 9 |  Required  |  {Tomato filling.} |
| {Pickle}   | 9 |  Required  |  {Pickle filling.} |
| {Fries}   | 25 |  Required  |  {Fries side.} |
| {Curly fries}   | 25 |  Required  |  {Curly fries side.} |
| {Sweet potato fries}   | 25 |  Required  |  {Sweet potato fries side.} |

        

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
     	"type":"burger",
     	"Cost":49.50
  	}
   },
   "Item2":{
  	"ItemOrdered":{
     	"type":"side",
     	"Cost":25.00
  	}
   }
 "Total":{
  	     	"Cost":74.50
  	}
   }




