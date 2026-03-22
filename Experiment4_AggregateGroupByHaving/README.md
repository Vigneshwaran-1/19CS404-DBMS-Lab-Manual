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

<img width="612" height="298" alt="image" src="https://github.com/user-attachments/assets/e4001350-09b7-4b03-997e-799b116b4730" />


```sql
SELECT Address, COUNT(*) AS TotalPatients
FROM Patients
GROUP BY Address;
```

**Output:**

<img width="593" height="294" alt="image" src="https://github.com/user-attachments/assets/8c633aee-d1ca-4513-82a0-3990e7698ca1" />

**Question 2**

<img width="604" height="341" alt="image" src="https://github.com/user-attachments/assets/ceff85a9-4c91-44d9-935d-edeaaaf525f7" />


```sql
SELECT Specialty, Gender, COUNT(*) AS TotalDoctors
FROM Doctors
GROUP BY Specialty ,Gender;
```

**Output:**

<img width="594" height="442" alt="image" src="https://github.com/user-attachments/assets/62e8e9d3-8313-46d6-aac0-b915a44ca754" />

**Question 3**

<img width="613" height="362" alt="image" src="https://github.com/user-attachments/assets/82951396-d677-4e79-8e46-0425117ce6f6" />


```sql
SELECT Specialty, COUNT(*) AS TotalDoctors
FROM Doctors
GROUP BY Specialty;
```

**Output:**

<img width="532" height="452" alt="image" src="https://github.com/user-attachments/assets/67bb3765-1231-43a9-9219-574cd315fd1d" />

**Question 4**

<img width="565" height="308" alt="image" src="https://github.com/user-attachments/assets/d98900e4-3d37-473d-934c-1214d6eff503" />


```sql
SELECT COUNT(*) AS COUNT
FROM customer;
```

**Output:**

<img width="404" height="236" alt="image" src="https://github.com/user-attachments/assets/cd62292e-8f50-44e2-a313-081fa8a19f3e" />

**Question 5**

<img width="503" height="289" alt="image" src="https://github.com/user-attachments/assets/282e31c2-9505-49fc-a3ec-70f61e178233" />


```sql
SELECT COUNT(*) AS employees_count
FROM employee
WHERE income > 50000;
```

**Output:**

<img width="482" height="245" alt="image" src="https://github.com/user-attachments/assets/70761ca5-0c1b-4c49-b269-03f698deef3e" />

**Question 6**

<img width="575" height="308" alt="image" src="https://github.com/user-attachments/assets/f6e9b965-5336-4436-beaf-da6ad0afdefe" />


```sql
SELECT COUNT(*) AS COUNT 
FROM customer
WHERE city!='Noida';
```

**Output:**

<img width="458" height="243" alt="image" src="https://github.com/user-attachments/assets/b8393530-9a0f-4d1d-aa72-afdeae65f025" />

**Question 7**

<img width="482" height="295" alt="image" src="https://github.com/user-attachments/assets/afe24870-bfb7-449d-8e9f-56ebea3874fc" />


```sql
SELECT SUM(income) AS total_income
FROM employee
WHERE age>=40;
```

**Output:**

<img width="583" height="235" alt="image" src="https://github.com/user-attachments/assets/5e2a6373-bbb5-4b4a-8d67-ca6b6a63c4ea" />

**Question 8**

<img width="580" height="281" alt="image" src="https://github.com/user-attachments/assets/37a301bb-cdc5-4be9-8561-0d0ebb77e5f8" />

```sql
SELECT(age/5) *5 AS age_group,MIN(salary)
FROM customer1
GROUP BY age_group
HAVING MIN(salary) <2000;
```

**Output:**

<img width="604" height="263" alt="image" src="https://github.com/user-attachments/assets/4c4d9243-4915-45c8-aded-1f18ce70adf2" />

**Question 9**

<img width="587" height="326" alt="image" src="https://github.com/user-attachments/assets/00dd0d2f-129b-4f76-8749-0cc91511ee0d" />


```sql
SELECT age,MIN(income)
FROM employee
GROUP BY age
HAVING MIN(income) <400000;
```

**Output:**

<img width="587" height="285" alt="image" src="https://github.com/user-attachments/assets/c3d0a966-e4ff-4a47-922c-49894872acda" />

**Question 10**

<img width="592" height="314" alt="image" src="https://github.com/user-attachments/assets/ce981899-be4b-47ab-ac8c-f1f986791470" />


```sql
SELECT address, AVG(salary)
FROM customer1
GROUP BY address
HAVING AVG(salary) > 5000;
```

**Output:**

<img width="548" height="323" alt="image" src="https://github.com/user-attachments/assets/c25a60ff-06dd-49d9-ac33-e400cf2d178d" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
