# Burger meal API

This is the Api documentation for placing orders for a burger meal and getting the bill back. use [GET on `/bill`](./get.md) endpont for bills and [post on `/order/burgerMeal`](/post.md) for ordering a burger meal.

## Mermaid

```mermaid
---
title: Mermaid Burger Meal Flowchart
---
flowchart TD
    A[Start new order]-->B([Select burger options]):::opts
    B-->C{Want any side dishes?}
    C--yes-->D([Select side dishes]):::opts
    D-->E
    C--"no"-->E{Want any drinks?}
    E--yes-->F([Select drinks]):::opts
    F-->G{Confirm order}
    E--"no"-->G
    G--"correct"-->H[Order placed!]
    G--"nope"-->A

    classDef opts stroke:#3DFFC5;

```

## Credits

- Credits to [Alex Fiedler](linkedin.com/in/alexfiedler) for [this exercise](https://docs.google.com/document/d/11uNd8m5EorsLjGV84CjiJehiM8PxT2pdNbDFOnP3cDI/edit#).
- Credits to the [Good Docs Project](https://thegooddocsproject.dev/) for the [reference template](https://github.com/thegooddocsproject/templates/edit/master/api-reference/api-reference.md).
