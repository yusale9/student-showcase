# GPMD API POC Introduction

```mermaid
flowchart TD
A([Initiate App]);
   A-->B{Want a burger meal};
   B--Yes-->C([Choose burger options]);
   C-->D{Want a side order?};
   B--No-->D;
   D--Yes-->E([Choose side order]);
   E-->F([Choose side size]);
   F-->G{Want another side?};
   G--Yes-->E;
   G--No-->H{Want a drink?};
  
