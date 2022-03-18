# General Putnam Motel Diner API

## Introduction

The General Putnam Motel Diner API has two main functions: 

- Let customers order and customize meals using an app.
- Let staff print out each table bill on request.

Completed orders are sent to the kitchen and printed on the in-house ticketing system.

## Content Type

Accept: application/json

Content-Type: application/json

## Resources

The General Putnam Motel Diner has the following resources: 

- [GET reference guide](https://github.com/JoeWainer/api-final-project/blob/main/get-reference-guide.md)
- [POST reference guide](https://github.com/JoeWainer/api-final-project/blob/main/post-reference-guide.md)

## Error Codes

The General Putnam Motel Diner follows HTTP status codes for success or failure. 

[See the list of error codes](https://github.com/JoeWainer/api-final-project/blob/main/error-codes.md). 

## API Workflow

```mermaid
  flowchart TD;
      A[Customer begins order]-->B[Choose pattyType];
      B-->C[Choose pattyQty];
      C-->D[Choose weight];
      D-->E[Choose pattyCook];
      E-->F[Choose bunType];
      F-->G[Condiment 1];
      G-->H[Condiment 2];
      H-->I[Topping 1];
      I-->J[Topping 2];
      J-->K[Topping 3];
      K-->L[Topping 4];
      L-->M{Want side dish?}
      M-->Yes-->N[Choose sides type];
      N-->O[Choose sides size];
      O-->P;
      M--No-->P{Want drink?};
      P--Yes-->Q[Choose drink];
      P--No-->S;
      Q-->R[Choose drink size];
      R-->S[Order complete - sent to kitchen];
```

```jsx

```

## References 
[The Good Docs Project](https://github.com/thegooddocsproject)
