# Apartment Rental Sequence Diagram
```mermaid
sequenceDiagram;
participant Lawyer
participant Tenant
participant Real Estate agent
participant Landlord
Tenant->>Real Estate agent: Asks about apartments to rent
Real Estate agent->>Tenant: Provides list of suitable apartments
Tenant->>Real Estate agent: Chooses Landlord's apartment
Landlord<<->>Tenant: Arrange viewing times

