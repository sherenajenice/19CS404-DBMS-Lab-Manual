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
<img width="947" height="327" alt="image" src="https://github.com/user-attachments/assets/086cd18c-91ef-4d84-9917-32167d3d9fa9" />


```sql
SELECT grade, COUNT(*) 
FROM customer
GROUP BY grade
HAVING grade > (
    SELECT AVG(grade)
    FROM customer
    WHERE city = 'New York'
);

```

**Output:**

<img width="690" height="282" alt="image" src="https://github.com/user-attachments/assets/60637e7e-f8c2-4eba-ae94-1b54611d992d" />


**Question 2**
---
<img width="942" height="390" alt="image" src="https://github.com/user-attachments/assets/ff44f752-74dd-46dc-bfc2-f60ebe9a7d4c" />


```sql
SELECT name, city
FROM customer
WHERE city IN (SELECT city FROM customer WHERE id IN (3,7));
```

**Output:**

<img width="639" height="353" alt="image" src="https://github.com/user-attachments/assets/5d9354e0-2995-4e1a-8988-8b3766967dbf" />


**Question 3**
---
<img width="1127" height="369" alt="image" src="https://github.com/user-attachments/assets/d5d60e21-ceae-4d5f-9d1b-63d67a598d26" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM orders
    WHERE customer_id = 3007
);
```

**Output:**

<img width="1029" height="357" alt="image" src="https://github.com/user-attachments/assets/ee0a856a-5274-48b8-bd53-baa88a16d03e" />


**Question 4**
---
<img width="1239" height="418" alt="image" src="https://github.com/user-attachments/assets/b889d3fb-cbaf-446d-8fc0-ba414f77796b" />


```sql
select ord_no, purch_amt, ord_date, customer_id, salesman_id from orders where purch_amt > (select avg(purch_amt) 
from orders where ord_date = '2012-10-10');
```

**Output:**

<img width="1030" height="470" alt="image" src="https://github.com/user-attachments/assets/fab2169a-09ff-4402-9176-aa2c2b753188" />


**Question 5**
---
<img width="1003" height="369" alt="image" src="https://github.com/user-attachments/assets/722333dc-326a-4f15-ab18-3d3638cb8bdb" />


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';
```

**Output:**

<img width="867" height="314" alt="image" src="https://github.com/user-attachments/assets/0d429900-4cc9-41d8-8a8b-04bbab56b380" />


**Question 6**
---
<img width="900" height="410" alt="image" src="https://github.com/user-attachments/assets/ebef4b17-9ff7-4a92-b59c-347abb544e5e" />


```sql
select * from CUSTOMERS where ADDRESS like 'DELHI' and AGE < 30 order by ID asc;
```

**Output:**

<img width="985" height="291" alt="image" src="https://github.com/user-attachments/assets/f1aa631d-df9c-4e4e-bc1d-08bc9448e3f2" />


**Question 7**
---
<img width="871" height="453" alt="image" src="https://github.com/user-attachments/assets/60758b67-bc92-4ae3-8deb-8b2a13656682" />

```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY>4500;

```

**Output:**

<img width="980" height="358" alt="image" src="https://github.com/user-attachments/assets/0dafc7b6-d7a9-403c-9907-3930f85b9e1b" />


**Question 8**
---
<img width="999" height="491" alt="image" src="https://github.com/user-attachments/assets/c47d1a2a-9b92-4a74-a5f2-c05e208e6773" />


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city = 'London';
```

**Output:**

<img width="885" height="367" alt="image" src="https://github.com/user-attachments/assets/c1f6b847-1893-4f88-ab22-e9c7aa9db132" />


**Question 9**
---
<img width="978" height="548" alt="image" src="https://github.com/user-attachments/assets/3cd13f2d-6c19-4711-8ec0-7aff7969ae34" />


```sql
select o.ord_no, o.purch_amt, o.ord_date,  o.salesman_id from orders o join salesman s on o.salesman_id = s.salesman_id
where s.commission = ( select MAX(commission) from salesman );
```

**Output:**

<img width="784" height="382" alt="image" src="https://github.com/user-attachments/assets/733cec70-221f-4e8d-96f2-e4ebcd78f6ed" />


**Question 10**
---
<img width="981" height="506" alt="image" src="https://github.com/user-attachments/assets/1406423c-712d-4b46-ac17-8fe3d3fbaa8e" />

```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500
```

**Output:**

<img width="895" height="463" alt="image" src="https://github.com/user-attachments/assets/304f1dfb-d15b-4f74-9c08-9c1e67cf42fa" />


## Grade

<img width="1738" height="83" alt="image" src="https://github.com/user-attachments/assets/0424ca51-cf80-45ae-9168-b72852e7c3f7" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
