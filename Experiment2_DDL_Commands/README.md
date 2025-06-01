# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
![Screenshot 2025-05-17 131129](https://github.com/user-attachments/assets/651063cb-9c74-4ad4-b535-9ab32240f4e7)

```sql
-- Create a table named Bonuses with the following constraints:

    BonusID as INTEGER should be the primary key.
    EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
    BonusAmount as REAL should be greater than 0.
    BonusDate as DATE.
    Reason as TEXT should not be NULL.

```

**Output:**

![Screenshot 2025-05-17 131224](https://github.com/user-attachments/assets/c6e541cf-93ba-4f2f-a65f-2ab6a3c8339d)

**Question 2**
---
![Screenshot 2025-05-17 131251](https://github.com/user-attachments/assets/6a463166-49e7-4f11-ab0e-eb87b546bf3c)

```sql
-- Insert the below data into the Customers table, allowing the City and ZipCode columns to take their default values.

CustomerID  Name          Address
----------  ------------  ----------
304         Peter Parker  Spider St      

Note: The City and ZipCode columns will use their default values.
```

**Output:**

![Screenshot 2025-05-17 131318](https://github.com/user-attachments/assets/7e90cdaa-5b82-4509-af97-33fcf8e9c7f3)


**Question 3**
---
![Screenshot 2025-05-17 131353](https://github.com/user-attachments/assets/093bd344-d25a-44b8-aeb1-7b26575716f4)

```sql
-- Create a table named Reviews with the following columns:

    ReviewID as INTEGER
    ProductID as INTEGER
    Rating as REAL
    ReviewText as TEXT

```

**Output:**

![Screenshot 2025-05-17 131501](https://github.com/user-attachments/assets/776a443e-7bfe-464f-acfd-0dc425c26c9e)


**Question 4**
---
![Screenshot 2025-05-17 131530](https://github.com/user-attachments/assets/651df5c5-b347-4c45-9ef4-4b7749005638)

```sql
-- Write an SQL command can to add a column named email of type TEXT to the customers table
```

**Output:**

![Screenshot 2025-05-17 131603](https://github.com/user-attachments/assets/116eb9d9-3401-4ad1-b7b8-ea2266b8779c)

**Question 5**
---
![Screenshot 2025-05-17 131637](https://github.com/user-attachments/assets/af62451a-6cd5-4b33-adf0-bc9a7824c309)

```sql
-- Insert all products from Discontinued_products into Products.

Table attributes are ProductID, ProductName, Price, Stock
```

**Output:**

![Screenshot 2025-05-17 131704](https://github.com/user-attachments/assets/9545a8c3-334c-4e31-95d1-dd779240b51e)

**Question 6**
---
![Screenshot 2025-05-17 131737](https://github.com/user-attachments/assets/4d9410ae-1015-41c4-b360-cef9a79c1f66)

```sql
-- Create a new table named orders with the following specifications:

    ord_id as TEXT with a length of 4.
    item_id as TEXT.
    ord_date as DATE.
    ord_qty as INTEGER.
    cost as INTEGER.
    The primary key is a composite key consisting of item_id and ord_date.
    ord_id and item_id should not accept NULL

```

**Output:**

![Screenshot 2025-05-17 131758](https://github.com/user-attachments/assets/d6d46051-f479-4e2a-b4fa-e7aaded39fa8)

**Question 7**
---
![Screenshot 2025-05-17 131831](https://github.com/user-attachments/assets/6af9377f-76d1-4269-9918-5d02625cb2fa)

```sql
-- Create a table named Orders with the following constraints:

    OrderID as INTEGER should be the primary key.
    OrderDate as DATE should be not NULL.
    CustomerID as INTEGER should be a foreign key referencing Customers(CustomerID).

```

**Output:**

![Screenshot 2025-05-17 132930](https://github.com/user-attachments/assets/07eecffc-cb14-4b58-aac9-b1eb62bbe39b)

**Question 8**
---
![Screenshot 2025-05-17 133137](https://github.com/user-attachments/assets/0fc4ba49-6753-467a-a060-b841e3d476f6)

```sql
-- Write an SQL Query to add the attributes designation, net_salary, and dob to the Companies table with the following data types:

    designation as VARCHAR(50)
    net_salary as NUMBER
    dob as DATE

```

**Output:**

![Screenshot 2025-05-17 133200](https://github.com/user-attachments/assets/043103e8-25a0-4d4d-aab0-c03781caed32)

**Question 9**
---
![Screenshot 2025-05-17 133221](https://github.com/user-attachments/assets/47a56f93-73cf-41a6-b981-cc80303f06be)

```sql
-- Insert the following customers into the Customers table:

CustomerID  Name         Address     City        ZipCode
----------  -----------  ----------  ----------  ----------
302         Laura Croft  456 Elm St  Seattle     98101
303         Bruce Wayne  789 Oak St  Gotham      10001
```

**Output:**

![Screenshot 2025-05-17 133242](https://github.com/user-attachments/assets/724c95af-84d3-4182-b15f-6a9c6920d424)

**Question 10**
---
![Screenshot 2025-05-17 133301](https://github.com/user-attachments/assets/4be34083-3488-4a2e-88ea-5089cebe755f)

```sql
-- Create a table named Employees with the following constraints:

    EmployeeID should be the primary key.
    FirstName and LastName should be NOT NULL.
    Email should be unique.
    Salary should be greater than 0.
    DepartmentID should be a foreign key referencing the Departments table.

```

**Output:**

![Screenshot 2025-05-17 133319](https://github.com/user-attachments/assets/d4fe88d8-de4e-4f11-be6e-576de2779c01)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
