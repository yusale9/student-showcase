## How to order a burgerMeal

```mermaid
flowchart LR
  subgraph TOP
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
  A([START]) -->TOP
  PattySelection --> CheeseSelection
  CheeseSelection -->BunSelection
  BunSelection -->ToppingSelection
  ToppingSelection -->SideSelection
  SideSelection -->DrinkSelection
TOP -->Q[/Send Order/] -->B([END])

  
```
