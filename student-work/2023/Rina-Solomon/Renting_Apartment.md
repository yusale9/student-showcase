# Renting an Apartment without Agent

```mermaid
   sequenceDiagram
   Participant Tenant
   Participant Apartment Owner
   Participant Lawyer
   Participant Apartment

   Tenant->>Apartment Owner: Phones regarding advertisement in newspaper;
   Apartment Owner->>Tenant: Fixes date and time to see the Apartment;
   Tenant->>Apartment Owner: Goes to see the Apartment;
   Tenant->>Apartment Owner: Informs that he wants the Apartment on rent;
   Apartment Owner->>Lawyer: Draws the contract with the lawyer;
   Apartment Owner->>Tenant: Sends the contract for review;
   Tenant->>Apartment Owner: Accepts the contract and decides on date for signing contract;
   Tenant->>Lawyer: Signs the contract;
   Apartment Owner->>Lawyer: Signs the contract;
   Lawyer->>Tenant: Gives copy of signed contract;
   Lawyer->>Apartment Owner: Gives copy of signed contract;
   Apartment Owner->Tenant: Gives him the Apartment keys;
   Tenant->>Apartment: Moves into the Apartment;

   ```
