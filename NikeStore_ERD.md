# Nike Store Senario
```mermaid
erDiagram
    PRODUCT {
        int product_id PK
        string name
        string category
        float price
    }
    CUSTOMER {
        int customer_id PK
        string name
        string email
        string phone
    }
    SALE {
        int sale_id PK
        int product_id FK
        int customer_id FK
        date sale_date
        int quantity
        float total_price
    }
    INVENTORY {
        int inventory_id PK
        int product_id FK
        int stock_level
    }

    PRODUCT ||--o{ SALE : "sold in"
    CUSTOMER ||--o{ SALE : "makes"
    PRODUCT ||--o| INVENTORY : "tracked in" 
