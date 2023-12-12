## ACME APP Co. Project Brief

#### Summary
ACME APP Co. is interested in working with General Putnam Motel Diner (GPMD) to build an app for its customers to place take out orders. Eventually, GPMD would like to use the app inside the diner, tableside, for customers to place their own orders via tablet. ACME APP Co. developers will build the meal order app on top of an existing REST API using GPMD's famous hamburger meal deal as a proof of concept (see [diagram](#customer-order-flow-diagram) below).

#### AppCorp Meal Order API
The AppCorp Meal Order API is an open source REST API available under GNU General Public License v3.0. The following endpoint documentation is available:
- [POST](https://github.com/TechWriterMelissa/student-showcase/blob/main/student-work/2023/Melissa-Ligertwood/api-final-project/get.md) - Place burger order
- [GET](student-work/2023/Melissa-Ligertwood/api-final-project/get.md) - Retrieve the bill

#### Customer Order Flow Diagram

```mermaid
flowchart LR
  subgraph CustomerOrderFlow
    direction LR
    subgraph PattySelection
        direction LR
        C[/Choose <br> pattyQty/] -->D[/Choose <br> pattyType/]
    end
    subgraph CheeseSelection
        direction TB
        E{Cheese?} --Yes-->F[/Select cheese <br> option/]
        E{Cheese?} --No-->W[Skip]

    end
    subgraph BunSelection
        direction TB
        G{Bun?} --Yes-->H[/Select bun <br> type/]
        G{Bun?} --No-->X[Skip]
    end
subgraph ToppingSelection
        direction TB
        I{Toppings?} --Yes-->J[/Select <br> toppings/]
        I{Toppings?} --No-->Y[Skip]
    end
subgraph SideSelection
        direction TB
        K{Sides?} --Yes-->L[/Select <br> sides/]
        K{Sides?} --No-->Z[Skip]
    end
subgraph DrinkSelection
        direction TB
        M{Drink?} --Yes-->N[/Select drink <br> type/] -->O[/Select size/] -->P[/Ice? Select <br> Y/N/]
        M{Drink?} --No-->ZZ[Skip]
        
    end 
  end
  A([START]) -->CustomerOrderFlow
  PattySelection --> CheeseSelection
  CheeseSelection -->BunSelection
  BunSelection -->ToppingSelection
  ToppingSelection -->SideSelection
  SideSelection -->DrinkSelection
  CustomerOrderFlow -->Q[/Send Order/] -->B([END])

  
```

*This work was completed as part of a Docs as Code course project at [Our Best Words](https://ourbestwords.com/training-courses/skills-courses/). We gratefully acknowledge use of [The Good Docs Project](https://gitlab.com/tgdp/templates/-/tree/main/api-reference?ref_type=heads) API template and reference materials, as well as supplemental API documentation provided by [Alex Fiedler](https://www.linkedin.com/feed/update/urn:li:activity:6626465471241732096/).* 
