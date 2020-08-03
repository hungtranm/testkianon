This project for testing.

Task breakdown:
## API:

DHL Supply Chain Authenticate by username password and region

XPO Logistics Authenticate by email and password

Customer Send login token to email then user authenticate by email and token

Customer require login to:

Tracking product

Update in-stock product

## Tables to store data:

### users

| Columns | Type | Description |
| --- | --- | --- |
| Id | Int | Primary key |
| Email | String | Email to login |
| Password | String | Hashed password |
| Type | String | User type:
|      |        | DHL
|      |        |XPO
|      |        | Customer

### products
| Columns | Type | Description |
| --- | --- | --- |
| Id | Int | Primary key |
| Name | String | Product name |
| Quantity | Int | Product in-stock quantity |

### orders
| Columns | Type | Description |
| --- | --- | --- |
| Id | Int | Primary key |
| Created_at | Datetime | Order created at |

### order_detail
| Columns | Type | Description |
| --- | --- | --- |
| product_id | Int | Product id |
| order_id | Int | Order created at |

### order_histories
| Columns | Type | Description |
| --- | --- | --- |
| Id | Int | Primary key |
| order_id | Int | Order id |
| Date | Datetime | Date time order change status |
| Status | String | Status order:
|        |        | Processing
|        |        | Packed
|        |        | Product in transit
|        |        | Delivered
|        |        | Done 
| Location | String | Location where status changed:
|        |         | Warehouse
|        |         | Station Name
|        |         | Customer Home 
