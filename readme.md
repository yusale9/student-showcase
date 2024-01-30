## General Putnam Motel Diner - Orders  

# Introduction

The General Putnam Motel Diner API allows you to order for meals through their app.  
There are two main parts to this:  
* **GET** request - This is a call sent when the client asks for the bill. The GET request includes the Table number and order number.   
Takeout orders are table 99.  Documented in [Get.md](https://github.com/RinaSol/student-showcase/blob/API_Project/GET.md)   
* **POST** request - This command is to process the requested order and is sent to the kitchen.  
  On receiving an OK, the order is printed in the kitchen so that the cook can begin cooking. Documented in [POST.md](https://github.com/RinaSol/student-showcase/blob/API_Project/POST.md)

# Error Codes

The following are the HTTP status codes for success or failure of an API call. 

| Status | Code Description | 
| --- | --- |
| 200 - OK  | Your request was successful. |
| 400 - Bad Request | Error. Check your order for unsupported additions.|
| 401 - Unauthorized Request | Error. Is all information in the request correct?  |
| 402 - Request Failed | Your order was not received  |
| 404 - Not Found  | Page not found|

# Workflow  

```mermaid
   flowchart TD
   A((Start Order))-->B[Select Bread type]
   B-->C[Select Patty]
   C-->D[Select burger size]
   D-->E[Select cook level]
   E-->F{want topping}
   F--No-->H{want condiments}
   F--Yes-->G[choose topping]
   G-->H{want condiments}
   H--No-->J{want sides}
   H--Yes-->I[choose condiments]
   I-->J{want sides}
   J--Yes-->K[choose sides]
   K-->L{want drink}
   J--No-->L{want drink}
   L--Yes-->M[choose drink]
   M-->N[choose size]
   N-->O{want ice?}
   L--No-->P{want extras}
   O-->P{want extras}
   P--Yes-->Q[choose extras]
   P--No-->R[Order complete]
   Q-->R[Order complete]
   R-->S((Order sent to Kitchen))
```

# References
This exercise was borrowed and adapted from Alex Fiedler.  
Workflow was created with the help of Mermaid.  
Error Code was copied from the API Guide (Adapted from Alex Fiedler)




   
  
