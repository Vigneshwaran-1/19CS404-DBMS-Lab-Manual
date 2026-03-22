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

<img width="579" height="352" alt="image" src="https://github.com/user-attachments/assets/4b63dfbb-dd07-41e4-9aa3-e9ae84212376" />


```sql

UPDATE products
SET category ='Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**

<img width="593" height="352" alt="image" src="https://github.com/user-attachments/assets/c0706f24-4c97-4d89-acbe-dbaaef7d0af9" />

**Question 2**

<img width="593" height="329" alt="image" src="https://github.com/user-attachments/assets/f975ef24-d775-4346-a7b2-74e44d158faf" />


```sql
UPDATE PRODUCTS
SET sell_price= sell_price + ( 0.1 *sell_price) 
WHERE supplier_id =6;
```

**Output:**

<img width="595" height="382" alt="image" src="https://github.com/user-attachments/assets/a6711ce8-d5e1-4d4a-8969-18660420b5fb" />

**Question 3**

<img width="589" height="305" alt="image" src="https://github.com/user-attachments/assets/9c51558a-ec41-45cd-b86d-1e95f2258ada" />


```sql
UPDATE Products
SET reorder_lvl==20
WHERE quantity < 10 
AND category LIKE '%Snacks%' ;
```

**Output:**

<img width="590" height="400" alt="image" src="https://github.com/user-attachments/assets/776c0065-53c8-423b-9f64-c2e45999cc82" />


**Question 4**

<img width="598" height="448" alt="image" src="https://github.com/user-attachments/assets/bcafc40e-4abf-486a-9f44-8169c827d8a2" />


```sql
UPDATE Employees
SET first_name = 'John'
WHERE department_id =80 
AND commission_pct <0.35 ;
```

**Output:**

<img width="587" height="385" alt="image" src="https://github.com/user-attachments/assets/58e0c587-e498-4cc0-8d2f-8df9b302c9e8" />

**Question 5**

<img width="583" height="350" alt="image" src="https://github.com/user-attachments/assets/cc19778e-9d5d-4aa3-a521-0c4a1c601b7d" />


```sql

UPDATE Products
SET reorder_lvl= reorder_lvl-(0.3*reorder_lvl)
WHERE cost_price > 50 
AND quantity < 100 ;
```

**Output:**

<img width="1179" height="655" alt="Screenshot 2026-03-22 153038" src="https://github.com/user-attachments/assets/8a9cefa0-f528-4e93-9750-7ef368812e61" />





**Question 6**

<img width="1161" height="653" alt="Screenshot 2026-03-22 153101" src="https://github.com/user-attachments/assets/a7391287-e1ec-445d-8e22-e0ab75ebd020" />


```sql
DELETE FROM Customer
WHERE CUST_COUNTRY IN( 'UK') AND WORKING_AREA IN ('London') AND GRADE <3;
```

**Output:**

<img width="602" height="358" alt="image" src="https://github.com/user-attachments/assets/860b6558-4463-467f-a31c-ca63090bdf16" />

**Question 7**

<img width="1155" height="793" alt="Screenshot 2026-03-22 153421" src="https://github.com/user-attachments/assets/7ea64c3b-14c9-46eb-866f-34cd9998168d" />


```sql
DELETE  FROM Surgeries
WHERE surgery_id = 3 
OR surgery_id =4;
```

**Output:**

<img width="578" height="341" alt="image" src="https://github.com/user-attachments/assets/519ce50a-a397-41c2-9221-10db6fa1c0ae" />

**Question 8**

<img width="594" height="419" alt="image" src="https://github.com/user-attachments/assets/ee6dfe2d-8373-4f65-9db9-75bb4dcbf7cb" />


```sql
DELETE FROM Customer
WHERE GRADE =2;
```

**Output:**

<img width="590" height="406" alt="image" src="https://github.com/user-attachments/assets/0b966efb-8a3e-42bc-ab75-4be8a5cf5de2" />


**Question 9**

<img width="593" height="320" alt="image" src="https://github.com/user-attachments/assets/170e1eb8-8e97-4f1d-8edc-72ccb5429165" />


```sql
DELETE FROM Customer
WHERE CUST_COUNTRY NOT IN ('India', 'USA');
```

**Output:**

<img width="592" height="378" alt="image" src="https://github.com/user-attachments/assets/8b1fbc70-0e5c-4645-919d-8c6a3c6525a5" />

**Question 10**

<img width="580" height="331" alt="image" src="https://github.com/user-attachments/assets/d8a85cba-50a4-4749-bf99-2438bd3590e9" />

```sql
DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="598" height="435" alt="image" src="https://github.com/user-attachments/assets/0b8c9e51-37e8-455c-ba3c-b991615f433a" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
