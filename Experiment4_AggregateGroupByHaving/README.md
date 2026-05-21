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
<img width="740" height="428" alt="image" src="https://github.com/user-attachments/assets/34f47186-c351-42af-bc1f-4989a1cd5776" />

```sql
select Medication, count(Medication) as  TotalPrescriptions
from Prescriptions
group by Medication;

```

**Output:**

<img width="851" height="567" alt="image" src="https://github.com/user-attachments/assets/df839792-3b76-4697-8ca3-3274e4bbaac6" />


**Question 2**
---
<img width="828" height="388" alt="image" src="https://github.com/user-attachments/assets/ee03918b-414e-41cb-ac22-d789d0fc2b10" />


```sql
select Specialty , count(Specialty) as TotalDocto
from Doctors
group by Specialty;
```

**Output:**

<img width="897" height="524" alt="image" src="https://github.com/user-attachments/assets/af688667-73e1-4a89-a7ac-ef8f95847458" />



**Question 3**
---
<img width="533" height="466" alt="image" src="https://github.com/user-attachments/assets/b94e7a6d-5362-4cc2-a723-ec388b61366f" />


```sql
select InsuranceCompany ,AVG(EndDate-StartDate) as AvgCoverageDurationDays
from Insurance
group by InsuranceCompany;
```

**Output:**

<img width="712" height="512" alt="image" src="https://github.com/user-attachments/assets/1d9b608c-764f-4177-8950-2529209b597a" />



**Question 4**
---
<img width="656" height="374" alt="image" src="https://github.com/user-attachments/assets/de5b2d0b-e1fa-4d69-bd59-9a2d2d087a4f" />

```sql
select SUM(inventory) as total
from fruits
where unit = 'LB';
```

**Output:**

<img width="603" height="269" alt="image" src="https://github.com/user-attachments/assets/2501c713-337f-47d9-b0b6-0a772c7c9d04" />



**Question 5**
---
<img width="639" height="351" alt="image" src="https://github.com/user-attachments/assets/9d71fbb9-afb2-44dd-83f8-5586201baaa6" />


```sql
select purch_amt as MAXIMUM
from orders order by
purch_amt desc limit 1;
```

**Output:**

<img width="551" height="271" alt="image" src="https://github.com/user-attachments/assets/fe03be26-96ba-4813-8767-f82c2c0422fe" />



**Question 6**
---
<img width="645" height="361" alt="image" src="https://github.com/user-attachments/assets/894464bb-213c-4387-bff5-9cf0b2790208" />


```sql
select Min(purch_amt) as MINIMUM from orders ;
```

**Output:**

<img width="636" height="266" alt="image" src="https://github.com/user-attachments/assets/0cb12efa-fd20-4fda-9c66-daf93391ef96" />



**Question 7**
---
<img width="1222" height="299" alt="image" src="https://github.com/user-attachments/assets/14efe420-caa8-4fbe-87ce-77f58cd1a909" />

```sql
select category_id, sum(price) as Total_Cost
from products
group by category_id having sum(price)>50;
```

**Output:**

<img width="645" height="289" alt="image" src="https://github.com/user-attachments/assets/febe58f5-1698-4be0-92ae-8123005d8434" />


**Question 8**
---
<img width="1299" height="278" alt="image" src="https://github.com/user-attachments/assets/ecf9455b-fa19-47ba-9107-a5ff8961d667" />


```sql
select (age/5)*5 as age_group  , MIN(age) from customer1
group by (age/5)*5 having MAX(age)<25;
```

**Output:**

<img width="584" height="274" alt="image" src="https://github.com/user-attachments/assets/c7cb831a-c253-4474-8187-832ad026efb2" />


**Question 9**
---
<img width="1371" height="322" alt="image" src="https://github.com/user-attachments/assets/fd2eaffe-4918-453d-a877-f5dffc6a82b1" />

```sql
select occupation ,AVG(workhour)
from employee1
group by occupation having AVG(workhour) between 10 and 12;
```

**Output:**

<img width="722" height="343" alt="image" src="https://github.com/user-attachments/assets/b824d2b5-8db0-4171-8444-60b76ee9bedd" />



**Question 10**
---
<img width="1261" height="320" alt="image" src="https://github.com/user-attachments/assets/54b4c457-98fa-4f6e-a007-e32681cb9680" />

```sql
SELECT occupation, SUM(workhour) 
FROM employee1
GROUP BY occupation
HAVING SUM(workhour) > 20;

```

**Output:**

<img width="782" height="372" alt="image" src="https://github.com/user-attachments/assets/3aff1dad-490d-4afd-a872-69bfb27c2459" />


## Grade

<img width="1083" height="60" alt="image" src="https://github.com/user-attachments/assets/3bc0e14c-65dc-451a-8c0c-e3fbaf357a68" />





## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
