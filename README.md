# 🏥 Optics Store Database - "Cul d'Ampolla"

## 📄 Description

This project involves designing a **MySQL database** for managing suppliers, customers, employees, and sales of an optics store named **"Cul d'Ampolla"**.

---

## 🚀 Database Schema

The database consists of the following tables:

### 🌍 `country`
Stores country information.
- `idCountry` (Primary Key) – Unique country ID.
- `name` – Country name.
- `iso` – ISO code (Unique).

### 🏠 `address`
Stores address details.
- `idAddress` (Primary Key) – Unique address ID.
- `street`, `number`, `floor`, `door`, `city`, `postal_code`.
- `country_id` (Foreign Key) → `country.idCountry`.

### 🏭 `supplier`
Stores supplier details.
- `idSupplier` (Primary Key) – Unique supplier ID.
- `name`, `phone`, `fax`, `nif` (Unique).
- `address_id` (Foreign Key) → `address.idAddress`.

### 🎨 `mount_color`
Stores frame colors.
- `idmount_color` (Primary Key).
- `name` (Unique).

### 👓 `glass_color`
Stores glass colors.
- `idglass_color` (Primary Key).
- `name` (Unique).

### 🔧 `mount_type`
Stores frame types.
- `idmount_type` (Primary Key).
- `name` (Unique).

### 🕶️ `glasses`
Stores glasses inventory.
- `idGlasses` (Primary Key).
- `brand`, `graduation`, `price`.
- `supplier_id` (Foreign Key) → `supplier.idSupplier`.
- `mount_color_id` (Foreign Key) → `mount_color.idmount_color`.
- `glass_color_id` (Foreign Key) → `glass_color.idglass_color`.
- `mount_type_id` (Foreign Key) → `mount_type.idmount_type`.

### 🧑 `customer`
Stores customer details.
- `idcustomer` (Primary Key).
- `name`, `postal_code`, `phone`, `email`.
- `referredby_id` (Foreign Key, self-referencing) → `customer.idcustomer`.

### 👔 `employee`
Stores employee details.
- `idemployee` (Primary Key).
- `name`, `nif` (Unique).

### 🛒 `salesorder`
Tracks glasses sales.
- `idsalesorder` (Primary Key).
- `glasses_id` (Foreign Key) → `glasses.idGlasses`.
- `customer_id` (Foreign Key) → `customer.idcustomer`.
- `employee_id` (Foreign Key) → `employee.idemployee`.
- `sales_date`.

---

## 💾 Technologies Used
- **MySQL** for database management.
- **SQL Queries** for data manipulation.
- **Normalization** to ensure database efficiency.

```
