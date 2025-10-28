# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
Update the 'Selling_Price' to add 10% extra margin for all products supplied by the supplier with id 6.

PRODUCTS TABLE
```
name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT
```

```sql
UPDATE Products
SET sell_price=round(sell_price*1.10,0)
WHERE supplier_id=6;
```

**Output:**

![Output1](output.png)

**Question 2**
---
Write a SQL statement to Update the reorder level to 20 where the quantity in stock is less than 10 and product category is 'Snacks' in the products table.

Products table
```
---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id
```

```sql
UPDATE Products
SET reorder_lvl=20
WHERE quantity<10 and category='Snacks';

```

**Output:**

![Output2](output.png)

**Question 3**
---
For  Increase the selling price per unit by 3 for all products supplied by supplier ID 4 in the sales table.

PRODUCTS TABLE
```
name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT
```

```
SALES TABLE
name               type
-----------------  ---------------
sale_id            INT
sale_date          DATE
product_id         INT
quantity           INT
sell_price         DECIMAL(10,2)
total_sell_price   DECIMAL(10,2)
```

```sql
UPDATE SALES
SET sell_price=sell_price+3
WHERE product_id IN (SELECT product_id FROM PRODUCTS
WHERE supplier_id=4);
```

**Output:**

![Output3](output.png)

**Question 4**
---
Write a SQL statement to double the availability of the product with product_id 1.

products table
```
---------------
product_id
product_name
category_id
availability
```

```sql
UPDATE products
SET availability=availability*2
WHERE product_id=1;
```

**Output:**

![Output4](output.png)

**Question 5**
---
Write a SQL statement to Increase quantity of all products by 10% to adjust for surplus stock counted

Products table
```
---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id
```

```sql
UPDATE Products
set quantity=(quantity*1.10);
```

**Output:**

![Output5](output.png)

**Question 6**
---
Write a SQL query to Delete customers with 'GRADE' 3 or 'AGENT_CODE' 'A008' whose 'OUTSTANDING_AMT' is less than 5000

```sql
DELETE FROM Customer
WHERE (GRADE=3 OR AGENT_CODE='A008') AND OUTSTANDING_AMT < 5000;
```

**Output:**

![Output6](output.png)

**Question 7**
---
Write a SQL query to delete a specific doctor from Doctors table whose ID is 1.

Sample table: Doctors
attributes : doctor_id, first_name, last_name, specialization


```sql
DELETE FROM Doctors
WHERE doctor_id=1;
```

**Output:**

![Output7](output.png)

**Question 8**
---
Write a SQL query to Delete customers whose 'GRADE' is greater than 2 and have a 'PAYMENT_AMT' less than the average 'PAYMENT_AMT' for all customers, or whose 'OUTSTANDING_AMT' is greater than 8000:

```sql
DELETE FROM Customer
WHERE (GRADE >2 AND PAYMENT_AMT < (SELECT AVG(PAYMENT_AMT) FROM Customer)) OR OUTSTANDING_AMT>8000;
```

**Output:**

![Output8](output.png)

**Question 9**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.

```sql
DELETE FROM Customer
WHERE GRADE!=3;
```

**Output:**

![Output9](output.png)

**Question 10**
---
Write a SQL query to Delete All Doctors with a NULL Specialization

Sample table: Doctors
attributes : doctor_id, first_name, last_name, specialization

```sql
DELETE FROM Doctors
WHERE specialization IS NULL;
```

**Output:**

![Output10](output.png)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
