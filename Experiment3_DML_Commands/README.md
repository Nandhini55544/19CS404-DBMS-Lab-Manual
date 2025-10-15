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
--
<img width="997" height="289" alt="image" src="https://github.com/user-attachments/assets/d1cc5185-96dc-44a1-8174-48274886686f" />

```sql
update sales
set sell_price=sell_price*1.05
where product_id=15 and sale_date='2023-01-31'
```

**Output:**

<img width="1318" height="341" alt="image" src="https://github.com/user-attachments/assets/0ed7db27-9290-406d-bc30-6f8aa0d17a69" />

**Question 2**
---
<img width="635" height="362" alt="image" src="https://github.com/user-attachments/assets/86c10b91-e09d-4c02-a844-5f660ce5383c" />

```sql
update PRODUCTS
set reorder_lvl=40
where category = 'Grocery'
```

**Output:**

<img width="1335" height="325" alt="image" src="https://github.com/user-attachments/assets/d351a6c6-9676-4b59-8393-93c85a07c902" />

**Question 3**
---
<img width="1070" height="579" alt="image" src="https://github.com/user-attachments/assets/3b56527b-c108-40a9-b561-0b859d16d137" />

```sql
update Employees
set salary=
case
when department_id=40 then salary*125/100
when department_id=90 then salary*115/100
when department_id=110 then salary*110/100
else salary
end
```

**Output:**

<img width="941" height="341" alt="image" src="https://github.com/user-attachments/assets/552c3cd5-06bf-46fe-b24b-93499a29028c" />

**Question 4**
---
<img width="576" height="359" alt="image" src="https://github.com/user-attachments/assets/b54580b6-45c3-4d62-bb66-2ff16c983846" />

```sql
update PRODUCTS
set sell_price=sell_price*110/100
where supplier_id=6
```

**Output:**

<img width="1307" height="420" alt="image" src="https://github.com/user-attachments/assets/bc0ec3d7-0628-46ae-a058-dbccc4d08da5" />

**Question 5**
---
<img width="704" height="223" alt="image" src="https://github.com/user-attachments/assets/cb03ea28-f1ad-4ab8-820f-d98fc5b905c0" />

```sql
update Products
set sell_price=sell_price*1.10
where category='Bakery'
```

**Output:**

<img width="1317" height="405" alt="image" src="https://github.com/user-attachments/assets/4d1163d4-1879-48a6-bac0-575dcacc1a06" />

**Question 6**
---
<img width="1243" height="466" alt="image" src="https://github.com/user-attachments/assets/575f9cd2-a14b-4f40-ae6e-d2384f1803b1" />

```sql
delete from customer
where OPENING_AMT between 4000 and 6000
```

**Output:**

<img width="1301" height="461" alt="image" src="https://github.com/user-attachments/assets/0580d063-6a1d-4f52-ae12-efb573a1fff9" />

**Question 7**
---
<img width="1328" height="460" alt="image" src="https://github.com/user-attachments/assets/1dd4648a-c5e5-49e4-88da-03ad88196e48" />

```sql
delete from customer
where grade=2
```

**Output:**

<img width="514" height="377" alt="image" src="https://github.com/user-attachments/assets/dbd46384-55c1-4ab5-b8ce-5f8290d7b882" />

**Question 8**
---
<img width="913" height="343" alt="image" src="https://github.com/user-attachments/assets/0f79880c-e500-422b-8f08-900e1bee6cb2" />

```sql
delete from Doctors
where (specialization = 'Pediatrics' or specialization = 'Cardiology')
and last_name ='Brown'
```

**Output:**

<img width="933" height="631" alt="image" src="https://github.com/user-attachments/assets/222750fd-7c99-41cb-befe-374d0c57e12c" />

**Question 9**
---
<img width="539" height="314" alt="image" src="https://github.com/user-attachments/assets/66230ced-9b79-4fb6-8dc8-8cc74688f988" />

```sql
delete from Doctors
where doctor_id between 2 and 4
```

**Output:**

<img width="919" height="619" alt="image" src="https://github.com/user-attachments/assets/f1089c17-2569-4c67-9a73-f739072baf96" />

**Question 10**
---
<img width="580" height="317" alt="image" src="https://github.com/user-attachments/assets/b191feda-d063-4986-81b0-ffbb5f4a7692" />

```sql
delete from Surgeries
where surgery_date = '2024-02-28'
```

**Output:**

<img width="864" height="293" alt="image" src="https://github.com/user-attachments/assets/ae4edec0-5547-4eda-89dc-3d58183494f3" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
