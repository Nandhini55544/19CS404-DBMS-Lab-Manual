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
<img width="527" height="272" alt="image" src="https://github.com/user-attachments/assets/5da5fc45-e010-44fe-8483-7471bd75d4d5" />

```sql
select CategoryName, Description from categories
order by CategoryName
```

**Output:**

<img width="849" height="349" alt="image" src="https://github.com/user-attachments/assets/0f70fb9b-d57d-4b37-8288-f54a7660bc55" />

**Question 3**
---
<img width="723" height="308" alt="image" src="https://github.com/user-attachments/assets/f70dc0e4-e041-4fd0-82a4-cfb6986f317c" />

```sql
select * from employeeposition
where Salary between 50000 and 100000
```

**Output:**

<img width="804" height="185" alt="image" src="https://github.com/user-attachments/assets/e5af5e33-22a9-4c0b-ac77-0c05c40c1165" />

**Question 4**
---
<img width="1071" height="405" alt="image" src="https://github.com/user-attachments/assets/930462d2-3cfe-4e46-a1a4-6478ecef3b61" />

```sql
select id,decimal, 
case
when decimal<50 then 'Below Average'
when decimal=50 then 'Average'
else 'Above Average'
end as status
from Calculations 
```

**Output:**

<img width="687" height="324" alt="image" src="https://github.com/user-attachments/assets/833a3d2f-5cfe-4035-b373-f57188ea6566" />

**Question 5**
---
<img width="1326" height="394" alt="image" src="https://github.com/user-attachments/assets/9ba9a21f-48ae-4c89-833f-d7f0ea827852" />

```sql
select * from salesman
where city not in('Paris','Rome')
```

**Output:**

<img width="712" height="311" alt="image" src="https://github.com/user-attachments/assets/b9b16852-a55f-4e23-a233-08a414b6a063" />

**Question 6**
---
<img width="609" height="390" alt="image" src="https://github.com/user-attachments/assets/5427d83c-42e7-4b9b-a551-f3369c2a44e2" />

```sql
select id,value1, ABS(value1) as absolute_value
from Calculations
```

**Output:**

<img width="670" height="246" alt="image" src="https://github.com/user-attachments/assets/f236ed2c-db04-46b2-9e50-2882f41dcf71" />

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
