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
--
<img width="968" height="640" alt="image" src="https://github.com/user-attachments/assets/fec8158d-af48-4232-b94a-f808425176da" />

```sql
select Medication, count(*) as TotalPrescriptions
from Prescriptions
group by Medication;
```

**Output:**

<img width="824" height="841" alt="image" src="https://github.com/user-attachments/assets/6fd822ce-e27f-49d8-9615-28be435a4449" />

**Question 2**
---
<img width="615" height="609" alt="image" src="https://github.com/user-attachments/assets/d51dc21a-d830-4322-ae8e-aaf2d0c9b723" />

```sql
select strftime('%H',AppointmentDateTime) AS HourOfDay,
count(*) as TotalAppointments
from Appointments
group by HourOfDay
order by HourOfDay;
```

**Output:**

<img width="784" height="533" alt="image" src="https://github.com/user-attachments/assets/aa7b8cc9-1d81-4585-b81a-afef700ca7fe" />

**Question 3**
---
<img width="1012" height="661" alt="image" src="https://github.com/user-attachments/assets/864e3b45-6ae7-4cfa-8f4d-a39f82041531" />

```sql
select InsuranceCompany, count(DISTINCT PatientID) as TotalExpiredPatients
from Insurance
where substr(ValidityPeriod, instr(ValidityPeriod,'to')+3)<'2025-10-16'
group by InsuranceCompany
order by InsuranceCompany;
```

**Output:**

<img width="881" height="751" alt="image" src="https://github.com/user-attachments/assets/51535fd4-980a-40e5-bc06-9b6b4e48b5b1" />

**Question 4**
---
<img width="565" height="491" alt="image" src="https://github.com/user-attachments/assets/3aff047f-1983-432b-b353-31217edcb4ce" />

```sql
select Min(purch_amt) as MINIMUM
from orders;
```

**Output:**

<img width="433" height="316" alt="image" src="https://github.com/user-attachments/assets/5b5b3393-d213-4b4d-8441-d57dda105be3" />

**Question 5**
---
<img width="744" height="476" alt="image" src="https://github.com/user-attachments/assets/0981484c-4cd9-4fce-b0a2-12dd21613860" />

```sql
select count(distinct city) as
unique_cities
from customer;
```

**Output:**

<img width="532" height="317" alt="image" src="https://github.com/user-attachments/assets/b9ba6804-3cfe-4bec-95db-42f17c6c5dd6" />

**Question 6**
---
<img width="553" height="470" alt="image" src="https://github.com/user-attachments/assets/09199acd-4461-4586-88ec-e9ea7669910a" />

```sql
select name, length(name) as length
from customer
order by length desc
limit 1;
```

**Output:**

<img width="695" height="311" alt="image" src="https://github.com/user-attachments/assets/7da8676b-73eb-45bc-9851-583b5a2f4456" />

**Question 7**
---
<img width="826" height="474" alt="image" src="https://github.com/user-attachments/assets/06aebf7d-f163-4ef5-aa1e-8adb29614733" />

```sql
select avg(income) as avg_income
from employee
where name like 'A%';
```

**Output:**

<img width="409" height="305" alt="image" src="https://github.com/user-attachments/assets/34ffb92b-0ae6-4032-9639-90f0adaf1509" />

**Question 8**
---
<img width="1214" height="534" alt="image" src="https://github.com/user-attachments/assets/c94dcfb4-f554-47bf-96af-f4ac6e70f029" />

```sql
select category_id, 
sum(price*category_id) as Revenue
from products
group by category_id
having sum(price*category_id)>25;
```

**Output:**

<img width="655" height="429" alt="image" src="https://github.com/user-attachments/assets/dbb7778b-24d2-4392-b12d-a82613a11a32" />

**Question 9**
---
<img width="1206" height="507" alt="image" src="https://github.com/user-attachments/assets/8deb96ee-fabb-4790-9068-3bfb82cdd1aa" />

```sql
select age, min(income) as 'MIN(income)'
from employee
group by age
having income<400000;
```

**Output:**

<img width="640" height="384" alt="image" src="https://github.com/user-attachments/assets/407edac7-c06a-4f7b-a1f4-9df687435bd2" />

**Question 10**
---
<img width="1197" height="463" alt="image" src="https://github.com/user-attachments/assets/eae2bddb-2a83-4bff-802c-0fffcc1b1f9f" />

```sql
select (age/5)*5 as age_group,
AVG(age) from customer1
group by age_group 
having AVG(age)<24;
```

**Output:**
<img width="626" height="312" alt="image" src="https://github.com/user-attachments/assets/43ab7580-f440-4149-91bc-97e9dbe0b65e" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
