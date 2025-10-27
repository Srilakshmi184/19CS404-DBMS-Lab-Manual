# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
-- Paste Question 1 here

```sql
-- Paste your SQL code below for Question 1
```

**Output:**

<img width="1233" height="387" alt="Screenshot 2025-10-27 153007" src="https://github.com/user-attachments/assets/b8beb20b-350f-41c3-82c7-146087a522cd" />


**Question 2**
---
-- Paste Question 2 here

```sql
-- Paste your SQL code below for Question 2
```

**Output:**

<img width="306" height="244" alt="Screenshot 2025-10-27 153013" src="https://github.com/user-attachments/assets/0b5aeaff-30e7-4514-b283-6055dade8883" />


**Question 3**
---
-- Paste Question 3 here

```sql
-- Paste your SQL code below for Question 3
```

**Output:**

<img width="1072" height="483" alt="Screenshot 2025-10-27 153027" src="https://github.com/user-attachments/assets/8f8f7f6b-e930-4c83-ae9f-edc11be8e328" />


**Question 4**
---
-- Paste Question 4 here

```sql
-- Paste your SQL code below for Question 4
```

**Output:**

<img width="1235" height="305" alt="Screenshot 2025-10-27 153042" src="https://github.com/user-attachments/assets/e3bfb06c-4e18-4be6-94bb-cf3667ed8c95" />


**Question 5**
---
-- Paste Question 5 here

```sql
-- Paste your SQL code below for Question 5
```

**Output:**

<img width="1103" height="304" alt="Screenshot 2025-10-27 153054" src="https://github.com/user-attachments/assets/8a912e23-ae1f-4a6f-9370-6b2d42aa0bf3" />


**Question 6**
---
-- Paste Question 6 here

```sql
-- Paste your SQL code below for Question 6
```

**Output:**

<img width="1075" height="320" alt="Screenshot 2025-10-27 153105" src="https://github.com/user-attachments/assets/704c0395-9c4f-42ad-828b-8ee5b51a931e" />


**Question 7**
---
-- Paste Question 7 here

```sql
-- Paste your SQL code below for Question 7
```

**Output:**

<img width="755" height="297" alt="Screenshot 2025-10-27 153115" src="https://github.com/user-attachments/assets/7fa2542e-62d6-4f01-bf0d-f2bab2933691" />


**Question 8**
---
-- Paste Question 8 here

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

<img width="488" height="354" alt="Screenshot 2025-10-27 153127" src="https://github.com/user-attachments/assets/53b48ed9-2361-4961-9c13-a1819d65cade" />


**Question 9**
---
-- Paste Question 9 here

```sql
-- Paste your SQL code below for Question 9
```

**Output:**

<img width="1181" height="317" alt="Screenshot 2025-10-27 153139" src="https://github.com/user-attachments/assets/2d96d236-d6ce-4c3d-a71e-bca67762339a" />


**Question 10**
---
-- Paste Question 10 here

```sql
-- Paste your SQL code below for Question 10
```

**Output:**

<img width="1111" height="334" alt="Screenshot 2025-10-27 153152" src="https://github.com/user-attachments/assets/34f76f5e-f941-4f4e-80ec-c5be310b33e7" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.

<img width="1261" height="70" alt="Screenshot 2025-10-27 150439" src="https://github.com/user-attachments/assets/b88e60e2-6c30-49f7-94fb-43b5abd565b7" />

