# E-commerce Database Management System

This script demonstrates the creation and management of a simple e-commerce database using MySQL.
 It includes database structure, sample data, and SQL queries for common operations.

---

## Features

- **Database Name**: `ecommerce`
- **Tables**:
  - `customers`: Stores customer information.
  - `products`: Stores product details.
  - `orders`: Tracks orders placed by customers.
  - `order_items`: (Normalized structure) Tracks the products and quantities in each order.

---

## Database Structure

### 1. **Customers Table**
| Column        | Type          | Description                       |
|---------------|---------------|-----------------------------------|
| `id`          | INT (PK)      | Auto-increment unique identifier. |
| `name`        | VARCHAR(100)  | Customer's name.                  |
| `email`       | VARCHAR(100)  | Customer's email (unique).        |
| `address`     | VARCHAR(255)  | Customer's address.               |

### 2. **Products Table**
| Column        | Type           | Description                     |
|---------------|----------------|---------------------------------|
| `id`          | INT (PK)       | Auto-increment unique identifier. |
| `name`        | VARCHAR(100)   | Product's name.                  |
| `price`       | DECIMAL(10, 2) | Product's price.                 |
| `description` | TEXT           | Product's description.           |
| `discount`    | DECIMAL(10, 2) | (Optional) Discount on the product. |

### 3. **Orders Table**
| Column        | Type           | Description                           |
|---------------|----------------|---------------------------------------|
| `id`          | INT (PK)       | Auto-increment unique identifier.     |
| `customer_id` | INT (FK)       | References `customers(id)`.           |
| `order_date`  | DATE           | Date the order was placed.            |
| `total_amount`| DECIMAL(10, 2) | Total amount of the order.            |

### 4. **Order Items Table** (Normalized Structure)
| Column        | Type           | Description                           |
|---------------|----------------|---------------------------------------|
| `id`          | INT (PK)       | Auto-increment unique identifier.     |
| `order_id`    | INT (FK)       | References `orders(id)`.              |
| `product_id`  | INT (FK)       | References `products(id)`.            |
| `quantity`    | INT            | Quantity of the product in the order. |

---

