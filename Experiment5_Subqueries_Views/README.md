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

<img width="629" height="405" alt="image" src="https://github.com/user-attachments/assets/90479528-d995-4451-b526-13ec909c7bfe" />


```sql
SELECT *
FROM GRADES
WHERE(subject,grade) IN(
 SELECT subject,MAX(grade)
 FROM GRADES
 GROUP BY subject
 );
```

**Output:**

<img width="629" height="335" alt="image" src="https://github.com/user-attachments/assets/93b4515a-0e43-4705-af26-6e648f14d70b" />

**Question 2**

<img width="1225" height="706" alt="image" src="https://github.com/user-attachments/assets/cbb7f6a1-ff90-489e-a083-df515490e3df" />


```sql

  SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);
```

**Output:**

<img width="476" height="325" alt="image" src="https://github.com/user-attachments/assets/0ddec337-3818-46ef-a117-af07902e7802" />

**Question 3**

<img width="616" height="401" alt="image" src="https://github.com/user-attachments/assets/cc80bf6f-1c2b-483a-8de9-1c5b1ee1514d" />


```sql
SELECT student_name,grade
FROM GRADES
WHERE (subject,grade) IN(
 SELECT subject,MIN(grade)
 FROM GRADES
 GROUP BY subject
 );
```

**Output:**

<img width="602" height="319" alt="image" src="https://github.com/user-attachments/assets/a392309c-6e4f-4faf-b509-1bb2422b23a2" />

**Question 4**

<img width="623" height="407" alt="image" src="https://github.com/user-attachments/assets/f5a96323-5d4c-4a79-b52b-7708e1c3b32a" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY>4500;
```

**Output:**

<img width="621" height="328" alt="image" src="https://github.com/user-attachments/assets/9e36c357-e77a-4a39-afc8-3a8cba0b7d52" />

**Question 5**

<img width="583" height="302" alt="image" src="https://github.com/user-attachments/assets/61dc7a4b-27ef-48b2-aebf-87706c429a80" />


```sql
SELECT *
FROM Medications
WHERE dosage=(
  SELECT MAX(dosage)
  FROM Medications
  );
```

**Output:**

<img width="622" height="292" alt="image" src="https://github.com/user-attachments/assets/f499586b-17f9-4624-8194-4b21e7dcc8b2" />

**Question 6**

<img width="628" height="347" alt="image" src="https://github.com/user-attachments/assets/3510332b-8828-4813-836e-1fad08980313" />


```sql
SELECT ord_no,
       purch_amt,
       ord_date,
       customer_id,
       salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM orders
    WHERE customer_id = 3007
);
```

**Output:**

<img width="634" height="329" alt="image" src="https://github.com/user-attachments/assets/ce23b696-4828-4d0a-8bf5-66c71a48ca0a" />

**Question 7**

<img width="596" height="385" alt="image" src="https://github.com/user-attachments/assets/2ab5892d-8841-4780-a21d-8bf27402b332" />


```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';
```

**Output:**

<img width="624" height="268" alt="image" src="https://github.com/user-attachments/assets/0504921e-d70d-46b0-b556-97418a363776" />

**Question 8**

<img width="611" height="436" alt="image" src="https://github.com/user-attachments/assets/8bfaea71-214d-43c8-ba01-ac935529a423" />


```sql
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
);
```

**Output:**

<img width="615" height="248" alt="image" src="https://github.com/user-attachments/assets/42e9754f-c541-40e6-a1af-61ac396abfd8" />

**Question 9**

<img width="613" height="302" alt="image" src="https://github.com/user-attachments/assets/1763eb42-2e37-4c70-a2b5-910731c690e0" />


```sql
SELECT grade, COUNT(*)
FROM customer
WHERE grade > (
    SELECT AVG(grade)
    FROM customer
    WHERE city = 'New York'
)
GROUP BY grade;
```

**Output:**

<img width="625" height="250" alt="image" src="https://github.com/user-attachments/assets/da859302-d7e1-4950-8d3e-3fa8f61a55a5" />

**Question 10**

<img width="607" height="443" alt="image" src="https://github.com/user-attachments/assets/f87633c5-37a1-4615-9d17-56d99381d3af" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;
```

**Output:**

<img width="629" height="420" alt="image" src="https://github.com/user-attachments/assets/b19a4224-4a79-4adf-aef8-ecf77db5f1c4" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
