## GET Documentation  

# GET/tableNo  
This request is sent when the client asks to receive the bill.  
GET reqest includes the table number. Order number is included in the GET response. Takeout orders are table 99.  


# Endpoint name

Method | syntax
----- | ----------
GET | base_url/endpoint/etc.

# GET Request  
NAME  | Type  | Description  
----- | ----| -----  
table | Integer | This includes the table number of the client. Table 99 is reserved for takeouts.  
Order  | string | This is the meal requested by the client.  
timestamp | timestamp | The time the meal was ordered.



# GET Request Curl
curl -X GET "http://URL/tableNo?id=99"  

# GET Response (JSON Object)  







