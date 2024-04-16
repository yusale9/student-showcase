# Get Bill

`GET /bill`

get bill from the poc

## Query parameters

This route lists the table id and order id

|name|type|description|required|
|---|---|---|---|
|table_id|number| the table id| true|
|order_id|string| the order id| false|

curl example

```sh
curl - X GET /bill?table_id=21&order_id=2376-438-490869
```

## responses

the server responds with either a 200 ok response if the bill is correct and 400-500 errors
with the general error type.

|name|type|description|required|default|
|---|---|---|---|---|
|order_id|string| order id| true| none|
|table_number|number| table number| true| none|
|total|number| total amount| true| 0|
|server|string| name of the one server| true| none|
|tip_perc|number| percentage amount to tip| true| 5|
|message|string| a custom message for customers| false| thanks & come back again!|

### 200 OK

the bill is correct

```json
{
    "order_id": "2376-438-490869",
    "total": "47.93CAD",
    "table_number": 21,
    "server": "stacy",
    "tip_perc": 0,
    "message": "thanks, and try to tip sometimes :)"
}
```

### 400 - 500 an error occured

"oops! an error occurred." Display this message to users accordingly

```json
{
    "message": "invalid table id",
    "code": "E890_5",
    "type": "ERR_BURGER_M"
}
```
