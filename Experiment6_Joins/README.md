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
--
<img width="1223" height="659" alt="image" src="https://github.com/user-attachments/assets/ad2efb17-553a-4a75-8178-57862c7b42eb" />

```sql
select cust_name, ord_no, ord_date, purch_amt
from customer as c
left join orders as o
on c.customer_id=o.customer_id;
```

**Output:**

<img width="1251" height="786" alt="image" src="https://github.com/user-attachments/assets/e8b81c46-48f7-4352-b96d-9507b8a88a68" />

**Question 2**
---
<img width="1202" height="788" alt="image" src="https://github.com/user-attachments/assets/a02c7103-a05b-4691-b38b-c4f1e6a35fba" />

<img width="1071" height="738" alt="image" src="https://github.com/user-attachments/assets/1ec77958-f7d7-40c3-82cc-de53a34dfa82" />


```sql
SELECT
  c.cust_name,
  c.city,
  o.ord_no,
  o.ord_date,
  o.purch_amt AS "Order Amount",
  s.name,
  s.commission
FROM
  customer c
LEFT JOIN
  orders o ON c.customer_id = o.customer_id
LEFT JOIN
  salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1229" height="770" alt="image" src="https://github.com/user-attachments/assets/7a0b7e14-f3c3-4ce5-a6d4-83aac3bb27fd" />

<img width="1050" height="765" alt="image" src="https://github.com/user-attachments/assets/89521691-be5d-4e54-8d7d-0997e593011f" />


**Question 3**
---
<img width="1265" height="742" alt="image" src="https://github.com/user-attachments/assets/8c689594-f7d2-453d-9523-8f1df934cf2d" />

```sql
select p.date_of_birth,a.appointment_id, p.patient_id, p.doctor_id, a.appointment_date
from patients as p
inner join appointments as a
on p.patient_id=a.patient_id
where first_name like "%Alice";
```

**Output:**

<img width="1277" height="423" alt="image" src="https://github.com/user-attachments/assets/f4ec0b2b-c5fb-4ba6-aa3f-1b2597f204d3" />

**Question 4**
---
<img width="1211" height="909" alt="image" src="https://github.com/user-attachments/assets/8effc94e-3780-45ba-af56-9bfff4f414d7" />

```sql
select o.ord_no,o.ord_date,o.purch_amt,
c.cust_name as "Customer Name",
c.grade,
s.name as "Salesman",
s.commission
from orders as o
inner join customer as c
on o.customer_id=c.customer_id
inner join salesman as s
on o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1233" height="781" alt="image" src="https://github.com/user-attachments/assets/2e248e2f-b2c3-4d67-88fd-2facb5d07310" />

<img width="993" height="778" alt="image" src="https://github.com/user-attachments/assets/c735a52e-7892-4020-9e0f-878126cef829" />


**Question 5**
---
<img width="1265" height="507" alt="image" src="https://github.com/user-attachments/assets/921b4872-86a7-4473-9fc0-da765ff0a232" />

```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';
```

**Output:**

<img width="1231" height="774" alt="image" src="https://github.com/user-attachments/assets/0d001fe7-4f22-4f8f-bcbc-42eb5a0efec7" />

**Question 6**
---
<img width="1266" height="914" alt="image" src="https://github.com/user-attachments/assets/6bb4d27a-0456-4cc6-ae14-3faa9c255f78" />

```sql
SELECT c.cust_name AS "Customer Name",
       c.city,
       s.name AS "Salesman",
       s.city,
       s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;
```

**Output:**

<img width="1228" height="548" alt="image" src="https://github.com/user-attachments/assets/b5858474-2952-4e1f-bbc1-a789d309c8c8" />

**Question 7**
---
<img width="1263" height="760" alt="image" src="https://github.com/user-attachments/assets/9b30ae8a-9e49-4b63-8d79-87d5a7682cb8" />

```sql
select p.first_name as "patient_name", a.appointment_id, a.patient_id, a.doctor_id, a.appointment_date
from patients as p
inner join appointments as a
on p.patient_id=a.patient_id;
```

**Output:**

<img width="1235" height="484" alt="image" src="https://github.com/user-attachments/assets/e15efd7e-1706-4f51-b8a3-3c3648f086cf" />

**Question 8**
---
<img width="1250" height="799" alt="image" src="https://github.com/user-attachments/assets/e809dbc6-3679-4398-ba0c-adc7b68d25ba" />

```sql
SELECT p.first_name, s.*
FROM patients p
INNER JOIN surgeries s ON p.patient_id = s.patient_id
WHERE p.discharge_date BETWEEN '2024-03-01' AND '2024-03-31'
  AND NOT (p.admission_date BETWEEN '2024-03-01' AND '2024-03-31');
```

**Output:**

<img width="1245" height="335" alt="image" src="https://github.com/user-attachments/assets/6fd3c3cc-f3f5-42a7-afe5-0964a24dc1da" />

**Question 9**
---
<img width="1206" height="890" alt="image" src="https://github.com/user-attachments/assets/b210d9dd-8831-4ab3-a643-14fcfa934be0" />

```sql
select c.cust_name as "Customer Name",
c.city,
s.name as "Salesman",
s.commission
from customer as c
inner join salesman as s
on c.salesman_id=s.salesman_id;
```

**Output:**

<img width="1211" height="815" alt="image" src="https://github.com/user-attachments/assets/8c5e3ccd-62a6-44f0-b426-59cf2be06e53" />

**Question 10**
---
<img width="1229" height="897" alt="image" src="https://github.com/user-attachments/assets/a4ab7b7b-fbfe-4c38-a6d9-ac4b687ca322" />

```sql
select c.cust_name, c.city, c.grade,
s.name as "Salesman",s.city
from customer as c
inner join salesman as s
on c.salesman_id=s.salesman_id
group by c.customer_id;
```

**Output:**

<img width="1238" height="822" alt="image" src="https://github.com/user-attachments/assets/c6ebed8f-5835-447c-8c05-56d14600c00b" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
