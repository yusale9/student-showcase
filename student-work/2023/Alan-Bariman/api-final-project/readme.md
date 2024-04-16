# Burger meal API

This is the Api documentation for placing orders for a burger meal and getting the bill back. use [GET on `/bill`](./get.md) endpont for bills and [post on `/order/burgerMeal`](/post.md) for ordering a burger meal.

## flow diagram

```mermaid
---
title: order a burger meal
---
flowchart TD
    A[start new order]-->B([select burger options]):::opts
    B-->C{want any side dishes}
    C--yes-->D([select side dishes]):::opts
    D-->E
    C--"no"-->E{want any drinks}
    E--yes-->F([select drinks]):::opts
    F-->G{confirm order}
    E--"no"-->G
    G--"correct"-->H[order placed!]
    G--"nope"-->A

    classDef opts stroke:#3DFFC5;

```

## credits

- Credits to [Alex Fiedler](linkedin.com/in/alexfiedler) for [this exercise](https://docs.google.com/document/d/11uNd8m5EorsLjGV84CjiJehiM8PxT2pdNbDFOnP3cDI/edit#).
- Credits to the [Good Docs Project](https://thegooddocsproject.dev/) for the [reference template](https://github.com/thegooddocsproject/templates/edit/master/api-reference/api-reference.md).
