# General Putnam Motel Diner API Documentation for the Burger Meal

## Introduction
The General Putnam Motel Diner API allows patrons of the diner to order their meals in a touchless manner via an app. Due to time restraints and for the purposes of creating a POC by April, this API documentation is limited to ordering the Burger Meal at lunch time as a take-out order. In the future, the final product will include a full menu for different meal times.  
### Workflow    
```mermaid


## Overview
The API is used to interface between the app and the server in the diner kitchen. Two main functions are presented:  
* **THE POST CALL:**
  * The app sends a command to the server: An order is submitted.
  * The server sends a response to the app acknowledging receipt of the request: The order is accepted and is printed in the kitchen for the meal to be prepared.  
* **THE GET CALL:**
  * The app requests information from the server: The bill is requested.
  * The server sends a response to the app: A bill is generated and a printout is given to the patron.
    
 ### Base URL

https://api.generalputnammoteldiner.com

### Authentication

Standard methods of authentication apply.

### HTTP status codes

The General Putnam Motel Diner APIs use the following standard HTTP response codes:

| Status code | Type                   | Description                         |
|-------------|------------------------|-------------------------------------|  
| 100         | Informational response | Request received, proceeding.       |  
| 200         | Successful response    | No further action needed from user. |

### Errors

The General Putnam Motel Diner APIs use the following error types:

| Error code | Type                  | Description                           |
|------------|-----------------------|---------------------------------------|
| 400        | Client error          | Erroneous error.                      |  
| 404        | Client error          | Page not found.                       |  
| 500        | Internal server error | Server is down.                       |              

## Workflow
