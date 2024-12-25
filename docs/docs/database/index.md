# Database architecture
The database is served by postgresql, the versioning is done with golang-migrate.

Here is the structure of the database:

```mermaid
---
title: Database structure
---
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER {
        string name
        string custNumber
        string sector
    }
    ORDER ||--|{ LINE-ITEM : contains
    ORDER {
        int orderNumber
        string deliveryAddress
    }
    LINE-ITEM {
        string productCode
        int quantity
        float pricePerUnit
    }
```

