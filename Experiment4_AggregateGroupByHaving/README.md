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

![Output1](output.png)

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

![Output2](output.png)

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

![Output3](output.png)

**Question 4**
---
Write a SQL query to return the total number of rows in the 'customer' table where the city is not Noida.

```
SELECT COUNT(*) AS COUNT FROM customer
WHERE city!='Noida';
```

**Output:**

![Output4](output.png)

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

![Output5](output.png)

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

![Output6](output.png)

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

![Output7](output.png)

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

![Output8](output.png)

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

![Output9](output.png)

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

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
