# Hamburger POC API Guide
## Contents
[Getting started](#getting-started)
[Authentication](#authentication)
[API reference](#API-reference)

## Getting started

The General Putnam Motel Diner API is being developed to allow customers to order meals from the General Putnam Motel Diner menu and request their bill. This Hamburger API is to develop a proof-of-concept (POC) for the General Putnam Hotel Diner to use with an ordering app and their server. It is expected to expand to other menus, meals, and services over time. The final product will be a full application for ordering anything from the menu. For an overview of the workflow this app will provide see the [Customer Order Flowchart](#customer-order-flowchart).

### Customer Order Flowchart

```mermaid
   flowchart TD
   A((Start))-->B[Read API documentation.];
   B-->C[/Request authentication/];
   C-->D[Receive authentication information];
   D-->E[/Send API call/];
   E-->F[Recieve 200 code];
   F-->G((Transaction completed));
   E-->H[Receive error code];
   H--400 code-->J;
   H--500 code-->I[Contact server administrator];
   I-->J[Resolve problem];
   J-->E;
```

## Authentication

General Putnam Hotel Diner (GPHD) API uses bearer authentication (also known as token authentication). When a user authenticates to access the GPHD API, the authentication server generates the bearer token. This token should then be used in the Authorization header when making further requests.

You need an email address and password to get a bearer token. When you get started with GPHD orders app, we send you an email containing this information.

:::Info NOTE

Each customer can request up to ten additional sets of credentials.

:::

To receive an authentication token:

Send the POST /authenticate request with the following structure:

```
curl --request POST 'https://api.gphd.net/v2/authenticate'
--header 'Content-Type: application/json'
--data-raw '{

  "email": "email@email.com",
  "password": "123Abcd!"
}'
```

In the request body, enter the email address and password you received from General Putnam Hotel Diner app.

An authentication token is returned. This is the authentication token you will use for subsequent requests.

> [!NOTE]  
> The returned token is valid for twenty-four hours.

In any subsequent request, include the authorization header, using the following structure:

```--header 'Authorization: Bearer ImahFWLZWFdD8VVcUtIED2YuOjPFlZpldQTE5tUqKdv'```

## API reference

* [POST/lunch/burgermeal](https://github.com/Schnee18/student-showcase/blob/main/student-work/2023/Sharon-Schnee/api-final-project/post.md)
* [GET/tableNo](https://github.com/Schnee18/student-showcase/blob/main/student-work/2023/Sharon-Schnee/api-final-project/get.md)

#### Acknowledgements
Thank you to [Alex Fiedler](https://www.linkedin.com/in/alexfiedler/) for the inspiration for this assignment and the [Good Docs Project](https://thegooddocsproject.dev/) for [sample API reference templates](https://github.com/thegooddocsproject/templates/blob/master/api-reference/api-reference.md).
  



