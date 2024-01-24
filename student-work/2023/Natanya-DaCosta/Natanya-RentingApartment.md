# Mermaid Sequence Diagram for Renting a House

```mermaid
   sequenceDiagram
   Participant Tenant
   Participant Real Estate Agent
   Participant Landlord
   Participant Lawyer
   Participant Credit Reference Agency
   Tenant->>Real Estate Agent: Confirm intention to apply for rental property;
   Tenant->>Real Estate Agent: Email rental application and list of required documents: ID, proof of employent, immigration status (if applicable), bank statements and references;
   Tenant->>Real Estate Agent: Return completed rental application along with requested documents;
   Tenant->>Real Estate Agent: Request permission for credit check;
   Tenant->>Real Estate Agent: Approve credit check;
   Real Estate Agent->>Credit Reference Agency: Request credit check;
   Credit Reference Agency->>Real Estate Agent: Confirm successful/positive credit check;
   Real Estate Agent->>Landlord: Submit application;
   Real Estate Agent->Landlord: Discuss application;
   Real Estate Agent->Landlord: Approve application;
   Real Estate Agent->>Tenant: Send notication of approved tenancy application;
   Real Estate Agent->>Tenant: Send lease agreement for signature;
   Tenant->>Lawyer: Forward lease agreement for review;
   Lawyer->>Tenant: Return reviewed agreement with approval;
   Tenant->>Real Estate Agent: Return signed lease agreement;
   Real Estate Agent->>Tenant: Hand-over keys, copies of tenancy agreement, tenancy rules & regulations, and entry inspection form;
   ```
