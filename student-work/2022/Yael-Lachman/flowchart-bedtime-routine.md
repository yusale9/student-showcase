### Putting kids to bed
```mermaid
  graph TD;
  A((Start))-->B[Eat supper]
  B-->C{Are they hungry?}
  C--Yes-->B
  C--No-->D{Do they have homework?}
  D--Yes-->E[Do homework]
  D--No-->F[Have a bath]
  E-->F
  F-->G{Are they clean?}
  G--Yes-->H[Pajamas]
  G--No-->F
  H-->I{Do they have clothes for tomorrow?}
  I--Yes-->J[Lay out tomorrow's clothes]
  I--No-->K[Put clothes in washing machine]
  K-->J
  J-->L[Brush teeth]
  L-->M[Shema]
  M-->N((End))
