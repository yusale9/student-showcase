# General Putnam Motel Diner API - POC

## Overview

The General Putnam Motel Diner API POC illustrates two of many basic functions required for the Diner's operations:

* Takeout Order placement
* Bill Processing

The API POC will allow patrons to place a takeout order and get the bill. 

The API may be further developed to include features such digital orders for in-house patrons.

## Documentation

For details, refer to:

- [Takeout Order Documentation](https://github.com/solidoc365/student-showcase/blob/main/student-work/solidoc/api-final-project/Post-Order)
- [Bill Documentation](https://github.com/solidoc365/student-showcase/blob/main/student-work/solidoc/api-final-project/Get-Bill)

## General Response Codes

Code | Description
----- | ----------
100 | Request Received
200 | Request Successful
401 | Unauthorized
403 | Forbidden
404 | Page not Found
500 | Internal Server Error

## API Workflow

```mermaid
  flowchart TD;
  
      A[Place order]-->B(Choose patty type);
      B-->C(Choose patty quantity);
      C-->D(Choose patty weight);
      D-->E(Choose patty cook);
      E-->F(Choose bun type);
      F-->G{Condiments?};
      G--Yes-->H(Choose condiments);
      G--No-->J{Toppings?};
      H-->J;
      J--Yes-->K(Choose toppings);
      J--No-->L{Side dish?};
      K-->L;
      L--Yes-->N(Choose sides type);
      N-->O(Choose sides size);
      O-->P;
      L--No-->P{Drink?};
      P--Yes-->Q(Choose drink);
      P--No-->U;
      Q-->R(Choose drink size);
      R-->S{Ice?}
      S--Yes-->T(Ice)
      S--No-->U[Order Completed]
      T-->U;

```

## References 
[The Good Docs Project](https://github.com/thegooddocsproject/templates)

[Mermaid Live Editor](link)

[Laura Novich, Instructor Extraordinaire at OBW](https://github.com/Laura-Novich-OBW)
