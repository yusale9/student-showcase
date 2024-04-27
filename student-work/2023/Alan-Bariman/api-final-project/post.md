# create order

`POST /order/burgerMeal`

ordering a burger meal

## request body

Each burger meal contains a burger, side dishes and a drink.

|name|type|description|required|default|
|---|---|---|---|---|
|burger|[`Burger`](#burger)| the burger| true| none|
|sides|[`SideDish []`](#side-dish)| an array of side dishes| false| `[]`|
|drinks|[`Drink []`](#drinks)| an array of drinks| false| `[]`|

example

```json
{
    "burger":{
        "patty_type": "beef",
        "patty_quantity": 1,
        "patty_cook": "rare",
        "bun_type": "plain",
        "toppings":[
            "tomatoes","pickles"
        ]
    },
    "sides": [],
    "drinks": []
}
```

curl request

```sh
curl -X POST /order/burgerMeal \
    - H Accept: application/json \
    - H Content-Type: application/json \
     -d '{
        "burger":{
            "patty_type": "beef",
            "patty_quantity": 1,
            "patty_cook": "rare",
            "bun_type": "plain",
            "toppings":[
                "tomatoes","pickles"
            ]
        },
        "sides": [],
        "drinks": []
    }'

```

### Burger

customers have options to choose a bun type, patty(s) and various toppings and condiments for their burger.

|name|type|description|required|default|options|
|---|---|---|---|---|---|
|patty_type|string| patty type| true| beef|beef,lamb, vegan|
|patty_quantity|number| patty quantity| true| 1|N/A|
|patty_cook|string| patty cook| true| well|rare,medium,well,well done|
|bun_type|string|bun type| true| plain|rulal,plain,glutenFree|
|toppings|string[]| an array of toppings to include| false | []|none,lettuce,tomato,redOnion|

### side dish

|name|type|description|required|default|
|---|---|---|---|---|
|type|string| the type of side dish| true| none|
|size|number| size of side dish| true| medium|

### Drinks

|name|type|description|required|default|
|---|---|---|---|---|
|type|string| type of drink| true| none|
|size|number| size of the drink| true| medium|
|ice|boolean| whether to include ice| true| false|

## response

The server responds with either a 200 ok response when order has been placed and 400-500 errors
with the general error type.

### 200 OK

the order was placed succesfully

```json
{
    "order_id": "2376-438-490869",
    "message": "order was placed succesfully"
}
```

### 400 - 500 an error occured

"oops! an error occurred." use this to display to users accordingly

```json
{
    "message": "an error occurred while placing the order",
    "code": "E890_5",
    "type": "ERR_BURGER_M"
}
```
