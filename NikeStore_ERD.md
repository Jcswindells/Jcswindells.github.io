
# Nike Store Scenario
## Relationships
### 1. Customer and Sales
> * **Purpose:** Links customers to their purchases.
> * **Why It Matters:** Helps the store build customer loyalty and understand customer buying habits.
### 2. Products and Sales
> * **Purpose:** Tracks which products are sold in each sale.
> * **Why It Matters:** Helps the store know what products sell well and generate revenue.
### 3. Products and Inventory
> * **Purpose:** Keeps track of stock levels for each product.
> * **Why It Matters:** Ensures the store doesn’t run out of products and avoids overstocking.
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
