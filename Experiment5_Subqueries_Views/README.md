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
--
<img width="988" height="753" alt="image" src="https://github.com/user-attachments/assets/c6172855-b3e2-40e3-8c83-4242f0a9f1a4" />

```sql
select * from CUSTOMERS
where salary>1500;
```

**Output:**

<img width="1260" height="606" alt="image" src="https://github.com/user-attachments/assets/3950eb69-40ac-4f9b-91cd-0fc9aca5d258" />

**Question 2**
---
<img width="1053" height="575" alt="image" src="https://github.com/user-attachments/assets/65486147-eaa1-4d62-8726-b9b3833ae21a" />

```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(phone) = 1
);
```

**Output:**

<img width="610" height="477" alt="image" src="https://github.com/user-attachments/assets/8dfc4608-e961-4a24-88a5-6267ca751184" />

**Question 3**
---
<img width="1026" height="622" alt="image" src="https://github.com/user-attachments/assets/cac988ac-0dbb-40c3-b15d-0dbae378baca" />

```sql
SELECT * FROM CUSTOMERS 
WHERE ID in(
select ID 
from CUSTOMERS
where ADDRESS = 'Delhi' AND AGE < 30);
```

**Output:**

<img width="1270" height="377" alt="image" src="https://github.com/user-attachments/assets/71b89779-7123-4486-8223-0f7a5610e133" />

**Question 4**
---
<img width="962" height="670" alt="image" src="https://github.com/user-attachments/assets/b6da754c-d33f-446d-96e6-c728ed683c8b" />

```sql
select * from CUSTOMERS
where salary<2500;
```

**Output:**

<img width="1221" height="461" alt="image" src="https://github.com/user-attachments/assets/e6034f11-c908-4998-9634-32037cb7bbe0" />

**Question 5**
---
<img width="1173" height="762" alt="image" src="https://github.com/user-attachments/assets/c42bc516-37c7-45b8-a9af-1607cf0fd0e2" />

```sql
select ord_no,purch_amt,ord_date,customer_id,salesman_id
from orders
where salesman_id in(
select salesman_id
from salesman
where name='Paul Adam');
```

**Output:**

<img width="1250" height="374" alt="image" src="https://github.com/user-attachments/assets/204a6a7d-8c96-4641-a2f5-fd85247fda03" />

**Question 6**
---
<img width="1233" height="500" alt="image" src="https://github.com/user-attachments/assets/8b22d619-af33-4787-97c6-14371fb15e67" />

```sql
select grade, COUNT(*)
from customer
where grade>(
select avg(grade)
from customer
where city='New York')
group by grade;
```

**Output:**

<img width="594" height="331" alt="image" src="https://github.com/user-attachments/assets/ee2875c3-9700-4c07-bb11-79ac418fad35" />

**Question 7**
---
<img width="1071" height="547" alt="image" src="https://github.com/user-attachments/assets/4770f9b7-9ae5-41ac-a446-d189cf4c5f48" />

```sql
select name,city
from customer
where city in(
select city
from customer
where id in (3,7));
```

**Output:**

<img width="677" height="467" alt="image" src="https://github.com/user-attachments/assets/cd9f2067-3886-4e86-8378-0667cb5595f3" />

**Question 8**
---
<img width="1217" height="638" alt="image" src="https://github.com/user-attachments/assets/1c06ecaa-28fd-4200-a4e9-e98a5a34b13a" />

```sql
select ord_no,purch_amt,ord_date, customer_id,salesman_id
from ORDERS
where purch_amt>(
select avg(purch_amt)
from ORDERS
where ord_date='2012-10-10');
```

**Output:**

<img width="1238" height="454" alt="image" src="https://github.com/user-attachments/assets/dcf9b301-89e9-4e0a-891c-8e2bbce83de9" />

**Question 9**
---
<img width="930" height="748" alt="image" src="https://github.com/user-attachments/assets/459eb0df-ae94-4047-b2d7-c059e01c6340" />

```sql
SELECT *
FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**

<img width="1237" height="581" alt="image" src="https://github.com/user-attachments/assets/db413fb6-dcd1-448e-9765-adde2afa059a" />

**Question 10**
---
<img width="1239" height="815" alt="image" src="https://github.com/user-attachments/assets/07ca6ae5-b289-4598-90d7-892a4e427951" />

```sql
select ord_no,purch_amt,ord_date,salesman_id
from orders
where salesman_id in(
select salesman_id
from salesman
where commission=(select max(commission) from salesman));
```

**Output:**

<img width="1075" height="469" alt="image" src="https://github.com/user-attachments/assets/24aa1d8a-166d-4929-84e1-dea837e4045c" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
