## ACME APP COMPANY API 

### Introduction
This API has been created for General Putnam Motel Diner in order for their customers to order takeout from the diner.
This POC will only depict the lunch meal and the order of a burger meal.
Future plans include adding breakfast, dinner, and meals other than a burger meal, along with their accompaniments.
This API is already set up to be used for in-house orders. Below you will see a workflow chart of the API.

```mermaid
flowchart TD;
    A[Order a Burger Meal] --> B[Choose burger type, weight, doneness];
    B --> C[Choose bun type];
    C --> D{Condiments?};
    D -- Yes --> E[Order condiments];
    E --> F{Toppings?};
    D -- No --> F{Toppings?};
    F -- Yes --> G[Order toppings];
    G --> H{Sides?}
    F -- No --> H{Sides?};
    H -- Yes --> I[Order sides];
    I --> J{Drink?};
    J -- No --> N[Send order to kitchen];
    H -- No --> J{Drink?};
    J -- Yes --> K[Choose size];
    K --> L{Ice?};
    L -- Yes --> M[Order drink];
    L -- No --> M[Order drink];
    M --> N[Send order to kitchen];
```

### Additional Topics

[GET/tableNo](https://github.com/Laura-Novich-OBW/student-showcase/blob/main/student-work/felice-berk/API_Final_Project/GET.md)

[POST/lunch](https://github.com/Laura-Novich-OBW/student-showcase/blob/main/student-work/felice-berk/API_Final_Project/POST.md)

### Acknowledgements

* This exercise was borrowed and adapted from [Alex Fiedler](https://il.linkedin.com/in/alexfiedler?trk=public_post_share-update_actor-text).

* Templates for API Reference were borrowed from [The Good Docs](https://github.com/thegooddocsproject/templates/edit/master/api-reference/api-reference.md).

* Markdown workflow diagram was borrowed and adapted from [Mermaid](https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/).
