# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**

<img width="599" height="380" alt="image" src="https://github.com/user-attachments/assets/cea194fe-a4f7-4a5b-b97b-538473e4246c" />


```sql
SELECT 
    c.cust_name, 
    c.city AS city, 
    c.grade, 
    s.name AS Salesman, 
    s.city AS city
FROM 
    customer c
JOIN 
    salesman s 
ON 
    c.salesman_id = s.salesman_id
WHERE 
    c.grade < 300
ORDER BY 
    c.customer_id ASC;
```

**Output:**

<img width="625" height="455" alt="image" src="https://github.com/user-attachments/assets/5d039e3a-1e3f-4658-9bcf-db39c236f8e1" />


**Question 2**

<img width="601" height="457" alt="image" src="https://github.com/user-attachments/assets/728b0765-b5fc-46db-9cb6-88357f459293" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS 'Customer Name',
    c.grade,
    s.name AS Salesman,
    s.commission
FROM orders o
JOIN customer c 
    ON o.customer_id = c.customer_id
JOIN salesman s 
    ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="614" height="461" alt="image" src="https://github.com/user-attachments/assets/c336b70f-7cfa-40ce-9320-0520b446ec9d" />

**Question 3**

<img width="587" height="452" alt="image" src="https://github.com/user-attachments/assets/e1caea18-7c36-47e5-8b92-76102f0c80a7" />


```sql
SELECT 
    p.first_name AS patient_name,
    t.test_name
FROM patients p
INNER JOIN test_results t
    ON p.patient_id = t.patient_id;
```

**Output:**

<img width="586" height="383" alt="image" src="https://github.com/user-attachments/assets/063f2f3b-1193-4bee-9456-f6e64b7ef3d3" />

**Question 4**

<img width="596" height="381" alt="image" src="https://github.com/user-attachments/assets/9dd63a67-e56c-4188-a96a-7547d54d5530" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM customer c
JOIN salesman s
    ON c.salesman_id = s.salesman_id;
```

**Output:**

<img width="612" height="358" alt="image" src="https://github.com/user-attachments/assets/450874ed-98ff-4530-9976-232facbe48af" />

**Question 5**

<img width="622" height="421" alt="image" src="https://github.com/user-attachments/assets/0912f6dd-6837-4b1e-8a51-df5338e851dc" />


```sql
SELECT 
    n.*
FROM nurses n
INNER JOIN departments d
    ON n.department_id = d.department_id
WHERE d.department_name = 'Pediatrics';
```

**Output:**

<img width="617" height="296" alt="image" src="https://github.com/user-attachments/assets/c3478a1b-283f-4884-ba9d-9bba069639bf" />

**Question 6**

<img width="603" height="380" alt="image" src="https://github.com/user-attachments/assets/d240262a-73b4-49d9-b1fb-39265fc1cdf5" />


```sql
SELECT 
    s.name AS Salesman,
    c.cust_name,
    c.city
FROM salesman s
JOIN customer c
    ON s.city = c.city;
```

**Output:**

<img width="610" height="421" alt="image" src="https://github.com/user-attachments/assets/58abcd60-ee24-45e1-b4c9-050f2042213f" />

**Question 7**

<img width="589" height="440" alt="image" src="https://github.com/user-attachments/assets/ae9abe68-2a99-4188-9878-c6029a7a8162" />


```sql
SELECT 
    p.first_name AS patient_name,
    t.*
FROM patients p
INNER JOIN test_results t
    ON p.patient_id = t.patient_id
WHERE p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

<img width="613" height="305" alt="image" src="https://github.com/user-attachments/assets/d827d5a3-45c8-425b-b12f-6b47b5aef810" />

**Question 8**

<img width="583" height="443" alt="image" src="https://github.com/user-attachments/assets/951ee19c-8c28-4303-9df5-cc956dd745cd" />


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM orders o
JOIN customer c
    ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

<img width="610" height="340" alt="image" src="https://github.com/user-attachments/assets/bfbedcf8-bfa7-409f-b176-0a76d0cc45d9" />

**Question 9**

<img width="614" height="212" alt="image" src="https://github.com/user-attachments/assets/0d6f7268-eba4-42e7-888c-6718e732bb9e" />


```sql
SELECT 
    s.*
FROM salesman s
LEFT JOIN customer c
    ON s.salesman_id = c.salesman_id
WHERE c.cust_name = 'Fabian Johns';
```

**Output:**

<img width="616" height="305" alt="image" src="https://github.com/user-attachments/assets/722f8ed5-9e0f-4207-bc87-8c3c6cf5d808" />

**Question 10**

<img width="614" height="331" alt="image" src="https://github.com/user-attachments/assets/826325b2-ecac-4ba9-a747-839132cdb249" />


```sql
SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
WHERE o.purch_amt > 1000;
```

**Output:**

<img width="599" height="455" alt="image" src="https://github.com/user-attachments/assets/d40d265c-b9f0-4d91-abee-1b7c207418aa" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
