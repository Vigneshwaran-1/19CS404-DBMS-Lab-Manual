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

<img width="572" height="234" alt="image" src="https://github.com/user-attachments/assets/314d1d61-089d-4a16-b04b-d04dab8ec83c" />


sql
```
CREATE TABLE Members(
  MemberID INTEGER,
  MemberName TEXT,
  JoinDate DATE
  );
```

**Output:**

<img width="594" height="286" alt="image" src="https://github.com/user-attachments/assets/7bce6bac-1dbf-4be2-b45d-6a43cc35c694" />



**Question 2**

<img width="575" height="221" alt="image" src="https://github.com/user-attachments/assets/b9b3a5f9-f1bf-4397-b220-3b9667b151ca" />


```sql
INSERT INTO Customers(CustomerId,Name,Address,Email)
SELECT CustomerId,Name,Address,Email
FROM Old_customers;
```

**Output:**

<img width="598" height="229" alt="image" src="https://github.com/user-attachments/assets/ef706d35-4c3f-4dd4-969d-7f0d60f25546" />


**Question 3**

<img width="589" height="218" alt="image" src="https://github.com/user-attachments/assets/b7333e4f-a2e7-4cb1-96c0-e2c208db027b" />


```sql
CREATE TABLE Products(
  ProductID INTEGER PRIMARY KEY,
  ProductName TEXT UNIQUE NOT NULL,
  Price REAL CHECK(Price>0),
  StockQuantity INTEGER CHECK(StockQuantity>=0)
    );
```

**Output:**

<img width="591" height="239" alt="image" src="https://github.com/user-attachments/assets/82a97225-92d9-43f1-9d4b-18605a4a6059" />


**Question 4**

<img width="587" height="295" alt="image" src="https://github.com/user-attachments/assets/4538d4b1-8a8b-48f2-bd0b-8799a10ed524" />

```sql

ALTER TABLE Companies RENAME COLUMN name TO
first_name;
ALTER TABLE Companies ADD COLUMN mobilenumber number;
ALTER TABLE Companies ADD COLUMN DOB Date;
```

**Output:**

<img width="595" height="298" alt="image" src="https://github.com/user-attachments/assets/4accac93-5596-4a14-802f-af6f20b25687" />


**Question 5**

<img width="580" height="292" alt="image" src="https://github.com/user-attachments/assets/8db54a54-8d7c-4253-a36c-113f3804f27e" />


```sql

INSERT INTO Student_details(RollNo,Name,Gender)
VALUES(205,'Olivia Green','F');


INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(207,'Liam Smith','M','Mathematics',85);

INSERT INTO Student_details(RollNo,Name,Gender,Subject)
VALUES(208,'Sophia Johnson','F','Science');
```

**Output:**

<img width="595" height="238" alt="image" src="https://github.com/user-attachments/assets/68e58b46-a0c6-4110-99f4-6b2b01a550f5" />


**Question 6**

<img width="584" height="362" alt="image" src="https://github.com/user-attachments/assets/bd0e9732-36bd-4dee-8b20-c762d7d1a80e" />


```sql
ALTER TABLE customer
ADD discount DECIMAL(5,2);
```

**Output:**

<img width="598" height="259" alt="image" src="https://github.com/user-attachments/assets/80933e9a-73e8-46f3-b642-6077552db1aa" />


**Question 7**

<img width="587" height="294" alt="image" src="https://github.com/user-attachments/assets/fb5264e2-2496-4311-a6bf-5fc94d70ae30" />


```sql
CREATE TABLE item (
 item_id TEXT PRIMARY KEY,
 item_desc TEXT NOT NULL,
 rate INTEGER NOT NULL,
 icom_id VARCHAR(4),
 FOREIGN KEY(icom_id)REFERENCES company(com_id)
  ON UPDATE SET NULL
  ON DELETE SET NULL
);
```

**Output:**

<img width="590" height="278" alt="image" src="https://github.com/user-attachments/assets/34fb0316-0ace-4574-b73e-292ae6d35c72" />

**Question 8**

<img width="582" height="269" alt="image" src="https://github.com/user-attachments/assets/6fbaf169-3abc-4a85-a471-3e65d5af8684" />


```sql
CREATE TABLE orders(
 ord_id TEXT NOT NULL CHECK(length(ord_id)=4),
 item_id TEXT NOT NULL,
 ord_date DATE,
 ord_qty INTEGER,
 cost INTEGER,
 PRIMARY KEY(item_id, ord_date)

);
```

**Output:**

<img width="588" height="257" alt="image" src="https://github.com/user-attachments/assets/42a78f21-7a8e-4c24-baa1-6b786d28bfb9" />

**Question 9**

<img width="593" height="296" alt="image" src="https://github.com/user-attachments/assets/c96e3de0-efa0-4b52-8cc8-b8c7a16a0a10" />


```sql
CREATE TABLE item (
 item_id TEXT PRIMARY KEY,
 item_desc TEXT NOT NULL,
 rate INTEGER NOT NULL,
 icom_id TEXT CHECK(length(icom_id)=4),
 FOREIGN KEY(icom_id)REFERENCES company(com_id)
   ON UPDATE CASCADE
   ON DELETE CASCADE

);
```

**Output:**

<img width="601" height="274" alt="image" src="https://github.com/user-attachments/assets/df12fdfe-b531-4d49-8a44-3b5d18f965b3" />

**Question 10**

<img width="592" height="188" alt="image" src="https://github.com/user-attachments/assets/7c53c669-403c-45f3-b3cc-5b330565d64f" />


```sql
INSERT INTO Products( ProductID,Name,Category)
VALUES(104,'Tablet','Electronics');
```

**Output:**

<img width="591" height="203" alt="image" src="https://github.com/user-attachments/assets/ebda4ece-33d4-4210-9abd-f19eb3be1137" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
