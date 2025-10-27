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
Insert a book with ISBN 978-1234567890, Title Data Science Essentials, Author Jane Doe, Publisher TechBooks, and Year 2024 into the Books table.

```
INSERT INTO Books(ISBN,Title,Author,Publisher,Year)
VALUES("978-1234567890","Data Science Essentials","Jane Doe","TechBooks",2024);
```

**Output:**

<img width="1165" height="176" alt="image" src="https://github.com/user-attachments/assets/020aa555-4075-48e1-9013-252900c49278" />


**Question 2**
---
Insert all customers from Old_customers into Customers

Table attributes are CustomerID, Name, Address, Email

```
INSERT INTO Customers
VALUES('301',"Michael Johnson","123 Elm Street","michael.j@example.com");


INSERT INTO Customers
VALUES('302',"Sarah Lee","456 Oak Avenue","sarah.lee@example.com");


INSERT INTO Customers
VALUES('303',"David Wilson","789 Pine Road","david.w@example.com");
```

**Output:**

<img width="1008" height="148" alt="image" src="https://github.com/user-attachments/assets/dffc76ef-61d6-465d-b7fb-8f75c42e7a16" />


**Question 3**
---
Create a table named ProjectAssignments with the following constraints:
AssignmentID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
ProjectID as INTEGER should be a foreign key referencing Projects(ProjectID).
AssignmentDate as DATE should be NOT NULL.

```
CREATE TABLE ProjectAssignments
(
AssignmentID INTEGER primary key,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
foreign key (EmployeeID) references Employees(EmployeeID),
foreign key (ProjectID) references Projects(ProjectID)
);
```

**Output:**

<img width="820" height="174" alt="image" src="https://github.com/user-attachments/assets/4830f817-1ae5-4926-a4a8-609202621c23" />


**Question 4**
---
Create a table named Products with the following constraints:
ProductID as INTEGER should be the primary key.
ProductName as TEXT should be unique and not NULL.
Price as REAL should be greater than 0.
StockQuantity as INTEGER should be non-negative.

```
CREATE TABLE Products
(
ProductID INTEGER primary key,
ProductName TEXT UNIQUE NOT NULL,
Price REAL CHECK(Price>0),
StockQuantity INTEGER CHECK(StockQuantity>0)
);
```

**Output:**

<img width="832" height="195" alt="image" src="https://github.com/user-attachments/assets/5743ec1e-371e-4f1f-bcd4-32609962bd0b" />


**Question 5**
---
Write a SQL query to modify the Student_details table by adding a new column Email of type VARCHAR(50) and updating the column MARKS to have a default value of 0.


```
ALTER TABLE Student_details
ADD COLUMN Email VARCHAR(50);

ALTER TABLE Student_details
ADD COLUMN MARKS INTEGER DEFAULT 0;
```

**Output:**

<img width="1213" height="144" alt="image" src="https://github.com/user-attachments/assets/d506a75d-3f22-4a91-8e07-b7cf50d6f208" />


**Question 6**
---
Write a SQL query to Rename the "city" column to "location" in the "customer" table.

```
ALTER TABLE customer
RENAME COLUMN city to location;
```

**Output:**

<img width="1192" height="203" alt="image" src="https://github.com/user-attachments/assets/f40339da-ea13-4f55-a0a5-d85cf0ad3ab1" />

**Question 7**
---
Insert the following students into the Student_details table:

```
INSERT INTO Student_details
VALUES(202,"Ella King","F","Chemistry",87);


INSERT INTO Student_details
VALUES(203,"James Bond","M","Literature",78);
```

**Output:**

<img width="774" height="129" alt="image" src="https://github.com/user-attachments/assets/2c8a6c3d-6124-4b73-86df-80d6072ce551" />


**Question 8**
---
Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should cascade updates and deletes.
item_desc and rate should not accept NULL.

```
CREATE TABLE item
(
item_id TEXT primary key,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
foreign key (icom_id) references company(com_id) ON UPDATE CASCADE ON DELETE CASCADE
);

```

**Output:**

<img width="659" height="190" alt="image" src="https://github.com/user-attachments/assets/47857cb7-3cb6-448b-a417-2f07127c18d9" />


**Question 9**
---
Create a table named Orders with the following columns:

OrderID as INTEGER
OrderDate as TEXT
CustomerID as INTEGER

```
CREATE TABLE Orders
(
OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER
);
```

**Output:**

<img width="843" height="217" alt="image" src="https://github.com/user-attachments/assets/c4816b75-0c7a-4083-a26a-ead3cb665f80" />


**Question 10**
---
Create a table named Invoices with the following constraints:

InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
DueDate as DATE should be greater than the InvoiceDate.
Amount as REAL should be greater than 0.

```
CREATE TABLE Invoices
(
InvoiceID INTEGER primary key,
InvoiceDate DATE,
DueDate DATE CHECK(DueDate>InvoiceDate),
Amount REAL CHECK(Amount>0)
);
```

**Output:**

<img width="680" height="131" alt="image" src="https://github.com/user-attachments/assets/bf5bebdb-18f7-4b63-b211-1318ba17163f" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
