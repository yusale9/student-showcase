# Apartment Rental Sequence Diagram
```mermaid
sequenceDiagram;
participant Lawyer
participant Tenant
participant Agent
participant Landlord
Tenant->>Agent: Asks about apartments to rent
Agent->>Tenant: Provides list of suitable apartments
Tenant->>Agent: Chooses Landlord's apartment
Landlord->Tenant: Arrange viewing times
par Tenant->>Landlord: Arrives at appointed time
and Agent->>Landlord: Arrives at appointed time
end

