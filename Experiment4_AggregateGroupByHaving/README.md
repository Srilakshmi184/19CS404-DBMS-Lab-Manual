# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
How many appointments are scheduled for each doctor?
```
SELECT DoctorID, COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID
ORDER BY DoctorID;
```

**Output:**

<img width="1233" height="387" alt="Screenshot 2025-10-27 153007" src="https://github.com/user-attachments/assets/2be6e39e-1258-44c7-be16-273003c1cd19" />

**Question 2**
---
What is the average dosage prescribed for each medication?

```
SELECT Medication,AVG(Dosage) AS AvgDosage
FROM Prescriptions
GROUP BY Medication
ORDER BY Medication;
```

**Output:**

<img width="306" height="244" alt="Screenshot 2025-10-27 153013" src="https://github.com/user-attachments/assets/7af62972-cf01-42ac-b220-7a64d0de1220" />


**Question 3**
---
How many patients are there in each city?

```
SELECT Address,COUNT(*) AS TotalPatients
FROM Patients
GROUP BY Address
ORDER BY Address;
```

**Output:**

<img width="1072" height="483" alt="Screenshot 2025-10-27 153027" src="https://github.com/user-attachments/assets/8fe26a4d-13c1-495f-8a1e-9be03fbc7139" />


**Question 4**
---
Write a SQL query to return the total number of rows in the 'customer' table where the city is not Noida.

```
SELECT COUNT(*) AS COUNT FROM customer
WHERE city!='Noida';
```

**Output:**

<img width="1235" height="305" alt="Screenshot 2025-10-27 153042" src="https://github.com/user-attachments/assets/59bd8b5a-2ca3-4d3e-942d-71d80fc7dcd9" />


**Question 5**
---
Write a SQL query to calculate the average purchase amount of all orders. Return average purchase amount.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001

```
SELECT AVG(purch_amt) AS AVERAGE
FROM orders;
```

**Output:**

<img width="1103" height="304" alt="Screenshot 2025-10-27 153054" src="https://github.com/user-attachments/assets/322b02b9-d1c3-4fb2-b836-8b243d7e60bf" />



**Question 6**
---
Write a SQL query to determine the number of customers who received at least one grade for their activity.

Sample table: customer

customer_id |   cust_name    |    city    | grade | salesman_id 

-------------+----------------+------------+-------+-------------

        3002 | Nick Rimando   | New York   |   100 |        5001

        3007 | Brad Davis     | New York   |   200 |        5001

        3005 | Graham Zusi    | California |   200 |        5002

```
SELECT COUNT(*) AS COUNT FROM customer
WHERE grade IS NOT NULL;
```

**Output:**

<img width="1075" height="320" alt="Screenshot 2025-10-27 153105" src="https://github.com/user-attachments/assets/0cf1a2cc-4e3f-498c-840e-9bf2597737ab" />


**Question 7**
---
Write a SQL query to find how many employees have an income greater than 50K?

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

```
SELECT COUNT(*) AS employees_count FROM employee
WHERE income>50000;
```

**Output:**

<img width="755" height="297" alt="Screenshot 2025-10-27 153115" src="https://github.com/user-attachments/assets/5853f749-f3c9-444a-8a1d-32bff1e06957" />


**Question 8**
---
Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the total salary sum for each group, and excludes groups where the total salary sum is not greater than 5000.

```
SELECT (age/5)*5 AS age_group,SUM(salary)
FROM customer1
GROUP BY age_group
HAVING SUM(salary)>5000;
```

**Output:**

<img width="488" height="354" alt="Screenshot 2025-10-27 153127" src="https://github.com/user-attachments/assets/1da149ef-dfc5-446d-8eaa-dec511feb757" />


**Question 9**
---
Write the SQL query that achieves the grouping of data by city, calculates the average income for each city, and includes only those cities where the average income is greater than 500,000.

```
SELECT city,AVG(income)
FROM employee
GROUP BY city
HAVING AVG(income)>500000;
```

**Output:**

<img width="1181" height="317" alt="Screenshot 2025-10-27 153139" src="https://github.com/user-attachments/assets/da4eda7f-8fdf-419b-a508-6a841865e25d" />


**Question 10**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the average work hours for each occupation, and includes only those occupations where the average work hour falls between 10 and 12.

```
SELECT occupation,AVG(workhour)
FROM employee1
GROUP BY occupation
HAVING AVG(workhour) BETWEEN 10 AND 12;
```

**Output:**


<img width="1111" height="334" alt="Screenshot 2025-10-27 153152" src="https://github.com/user-attachments/assets/ba70d746-05a4-4a49-8576-a8ef49191b00" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

<img width="1265" height="110" alt="Screenshot 2025-10-27 150429" src="https://github.com/user-attachments/assets/16bfef77-31ff-4028-a0fa-d20e79278cb1" />



