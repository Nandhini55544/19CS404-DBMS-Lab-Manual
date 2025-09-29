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
<img width="1294" height="257" alt="image" src="https://github.com/user-attachments/assets/0648df37-2476-41ba-bf03-68785efed981" />


```sql
INSERT INTO Products(ProductId,Name,Category,Price,Stock)
VALUES(101,'Laptop','Electronics',1500,50);
```

**Output:**

<img width="1205" height="213" alt="image" src="https://github.com/user-attachments/assets/0cd16525-9dac-4c1b-a226-7ef37ce0ee61" />

<img width="1188" height="192" alt="image" src="https://github.com/user-attachments/assets/94831e8e-2b2d-4303-baa1-1d3417c22bd1" />


**Question 2**
---
<img width="1318" height="373" alt="image" src="https://github.com/user-attachments/assets/a72470fe-c1c0-4219-9166-f3916538841d" />

```sql
CREATE TABLE Invoices(
    InvoiceID INTEGER PRIMARY KEY,
    InvoiceDate DATE,
    DueDate DATE,
    Amount REAL,
    CHECK(DueDate>InvoiceDate),
    CHECK(Amount>0)
);
```

**Output:**

<img width="1239" height="351" alt="image" src="https://github.com/user-attachments/assets/df8d7832-ee5f-49fd-9e71-a85cd8ea1739" />

<img width="1007" height="257" alt="image" src="https://github.com/user-attachments/assets/55c91548-c81c-4b72-b32d-a48d57f128e3" />


**Question 3**
---
<img width="1191" height="453" alt="image" src="https://github.com/user-attachments/assets/57100433-5a86-46c1-99fb-76e3a02eb974" />

```sql
ALTER TABLE Companies
RENAME COLUMN name TO first_name;
ALTER TABLE Companies
ADD mobilenumber number;
ALTER TABLE Companies
ADD DOB Date;
ALTER TABLE Companies
ADD State varchar(30);
```

**Output:**

<img width="1216" height="489" alt="image" src="https://github.com/user-attachments/assets/688a73e3-46b4-4eac-a998-f99e79048094" />

<img width="1227" height="501" alt="image" src="https://github.com/user-attachments/assets/045fb14a-4beb-43b1-89a0-5b2596b89ae7" />


**Question 4**
---
<img width="918" height="456" alt="image" src="https://github.com/user-attachments/assets/65f1b7a0-dfb0-4e7f-be29-a2e5434899b9" />

```sql
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(202,'Ella King','F','Chemistry',87);
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(203,'James Bond','M','Literature',78);
```

**Output:**

<img width="1222" height="342" alt="image" src="https://github.com/user-attachments/assets/e0c72907-0054-4630-b71f-9a392729f6bd" />

<img width="1220" height="329" alt="image" src="https://github.com/user-attachments/assets/50865e9c-fdf5-4614-8766-d4319bf6061d" />


**Question 5**
---
<img width="971" height="461" alt="image" src="https://github.com/user-attachments/assets/99da8a45-60cc-46b7-b5ba-605cb971822a" />

```sql
CREATE TABLE Products(
    ProductID INTEGER,
    ProductName TEXT,
    Price REAL,
    Stock INTEGER
);
```

**Output:**

<img width="1227" height="387" alt="image" src="https://github.com/user-attachments/assets/210c07d9-42b6-4149-b84d-db803cd01cf8" />

<img width="1225" height="363" alt="image" src="https://github.com/user-attachments/assets/4116e332-9aeb-4f92-a172-6a8a4df245d0" />


**Question 6**
---
<img width="1037" height="366" alt="image" src="https://github.com/user-attachments/assets/e0d870d7-2e7d-46d6-98ba-eabcd20f50f2" />

```sql
ALTER TABLE Student_details
ADD Date_of_birth Date;
```

**Output:**

<img width="1235" height="449" alt="image" src="https://github.com/user-attachments/assets/9ca34f11-f59a-4776-8398-52407735a701" />

<img width="1217" height="436" alt="image" src="https://github.com/user-attachments/assets/645fba50-7b1a-4686-a500-3717587c9a5b" />


**Question 7**
---
<img width="965" height="348" alt="image" src="https://github.com/user-attachments/assets/68fb32a5-396b-4554-b4f7-6cbc2eee7604" />

```sql
INSERT INTO Books(ISBN, Title, Author, Publisher,YearPublished)
SELECT ISBN, Title, Author, Publisher, YearPublished
FROM Out_of_print_books;
```

**Output:**

<img width="1224" height="371" alt="image" src="https://github.com/user-attachments/assets/37792252-7120-4159-a2c0-5126659e3262" />

<img width="1197" height="274" alt="image" src="https://github.com/user-attachments/assets/366ad4cc-317c-432b-9fc4-8473107b1c18" />


**Question 8**
---
<img width="1138" height="293" alt="image" src="https://github.com/user-attachments/assets/741b3a1c-3977-40cc-a096-76ffd27b7426" />

```sql
CREATE TABLE Department(
    DepartmentID INTEGER PRIMARY KEY,
    DepartmentName TEXT UNIQUE NOT NULL,
    Location TEXT
    );
```

**Output:**

<img width="1266" height="234" alt="image" src="https://github.com/user-attachments/assets/d2d70a26-8707-4197-b507-6882d69dbb73" />

<img width="915" height="230" alt="image" src="https://github.com/user-attachments/assets/c3929107-96c3-468c-b9b9-673dcf49a59f" />


**Question 9**
---
<img width="1203" height="283" alt="image" src="https://github.com/user-attachments/assets/c6af3fa2-8161-4428-be96-6851bab904b2" />

```sql
CREATE TABLE Orders(
    OrderID INTEGER PRIMARY KEY,
    OrderDate DATE NOT NULL,
    CustomerID INTEGER,
    FOREIGN KEY (CustomerID) REFERENCES
 Customers(CustomerID)
);
```

**Output:**

<img width="1286" height="295" alt="image" src="https://github.com/user-attachments/assets/c4f1bbfd-fd8e-4733-aabc-76d90a509a16" />

<img width="611" height="225" alt="image" src="https://github.com/user-attachments/assets/fc3b8a40-5285-413f-84ad-f6022a606b60" />


**Question 10**
---
<img width="827" height="396" alt="image" src="https://github.com/user-attachments/assets/c99ea84f-ab8c-47ce-b878-986870f809bb" />

```sql
CREATE TABLE item(
    item_id TEXT PRIMARY KEY,
    item_desc TEXT,
    rate INTEGER,
    icom_id TEXT(4),
    FOREIGN KEY(icom_id) REFERENCES
company(com_id)
    ON UPDATE CASCADE
    ON DELETE CASCADE
);
```

**Output:**

<img width="1273" height="327" alt="image" src="https://github.com/user-attachments/assets/64f2924b-d5ce-422b-a7d8-0e17fb3af806" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
