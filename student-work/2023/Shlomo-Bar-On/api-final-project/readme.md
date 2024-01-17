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
  



### HTTP status codes

The GPMD APIs use the following standard HTTP response codes:

| Status code                    | Message              | Description                                         |
|--------------------------------|----------------------|-----------------------------------------------------|
| `100 - OK`                       | Continue             | No errors reported but but awaiting further data.   |  
| `200 - OK`                       | Success              | Meal was successfully ordered.                      |
| `400 - Bad Request`            | Order refused        | Order was not accepted. Check for invalid options.  |
| `401 - Unauthorized`           | Authorization failed | Authorization attempt failed. Check supplied values.|
| `500 - Internal Server Error`  | Server side failure  | Contact server administrator.                       |
