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

### Submission:
Pradaksha V - 212223020020

**Question 1**

![Q1]<img width="1050" height="655" alt="image" src="https://github.com/user-attachments/assets/9c1bfcd9-e04b-4738-b0ea-de930ab2a34f" />


```sql
select c.cust_name,    c.city,     c.grade ,   s.name as Salesman , s.city from customer as c 
left join salesman as s on c.salesman_id = s.salesman_id
order by customer_id asc;
```

**Output:**

![A1]<img width="1221" height="677" alt="image" src="https://github.com/user-attachments/assets/bfc24f9b-7310-4295-a4f7-c633838f4abc" />


**Question 2**

![Q2](https://github.com/user-attachments/assets/039b1231-5e4c-4a79-b72a-b7d75fefa618)

```sql
SELECT o.ord_no, o.purch_amt, c.cust_name, c.city
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

![A2](https://github.com/user-attachments/assets/2bee1d92-7d8a-4693-b624-4737f655a5f7)

**Question 3**

![Q3]<img width="1347" height="512" alt="image" src="https://github.com/user-attachments/assets/11509d75-51f3-4c11-9c45-6ecce59094a5" />


```sql
SELECT 
    p.first_name AS patient_name, 
    t.*
FROM 
    patients AS p
INNER JOIN 
    test_results AS t
ON 
    p.patient_id = t.patient_id;

```

**Output:**

![A3]<img width="1316" height="368" alt="image" src="https://github.com/user-attachments/assets/909e47b5-c783-4fa6-9c39-3ed5f541bc10" />


**Question 4**

![Q4]<img width="989" height="915" alt="image" src="https://github.com/user-attachments/assets/4a657f6c-edc1-4a5a-9670-64be99ac7906" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![A4]<img width="1355" height="760" alt="image" src="https://github.com/user-attachments/assets/596992b9-e99a-4f16-9b28-10c54fa1038c" />


**Question 5**

![Q5]<img width="1592" height="463" alt="image" src="https://github.com/user-attachments/assets/2b91c1db-505b-4dd3-8211-945938271b70" />


```sql
SELECT p.first_name, s.surgery_id, s.patient_id, s.surgeon_id, s.surgery_date
FROM PATIENTS p INNER JOIN SURGERIES s ON p.patient_id = s.patient_id
WHERE p.discharge_date BETWEEN '2024-03-01' AND '2024-03-31'
AND (p.admission_date < '2024-03-01' OR p.admission_date > '2024-03-31');
```

**Output:**

![A5]<img width="1106" height="233" alt="image" src="https://github.com/user-attachments/assets/efbcad93-2c95-4b97-8978-d1b8973efbff" />


**Question 6**

![Q6]<img width="1582" height="541" alt="image" src="https://github.com/user-attachments/assets/20687449-488d-4b8e-a509-ce019eadf72b" />


```sql
SELECT p.*
FROM PATIENTS p INNER JOIN TEST_RESULTS t
ON p.patient_id = t.patient_id
WHERE t.result != 'Normal' AND t.test_name = 'Blood Pressure' OR 'Blood Test';
```

**Output:**

![A6]<img width="1632" height="309" alt="image" src="https://github.com/user-attachments/assets/8c7f861d-7151-44f0-b24f-5d20f919b941" />


**Question 7**

![Q7]<img width="1658" height="276" alt="image" src="https://github.com/user-attachments/assets/4ec2edcf-7942-4fed-ac30-c084d02257bc" />


```sql
select o.customer_id, c.cust_name, c.city, c.grade, o.salesman_id from customer c
left join orders o on c.customer_id = o.customer_id where o.ord_date between '2012-07-01' and '2012-07-30'
```

**Output:**

![A7]<img width="1241" height="308" alt="image" src="https://github.com/user-attachments/assets/35d3a809-3c36-4340-93de-1a7aef45c25e" />


**Question 8**

![Q8]<img width="1383" height="863" alt="image" src="https://github.com/user-attachments/assets/cfe842a0-62d0-4c6d-916d-8c1cba96801a" />


```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount",
    s.name,
    s.commission
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
LEFT JOIN salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![A8]<img width="1282" height="770" alt="image" src="https://github.com/user-attachments/assets/c5c9c9c8-472c-472f-8a0b-3fa90b16ee36" />


**Question 9**

![Q9]<img width="1717" height="639" alt="image" src="https://github.com/user-attachments/assets/d3606225-f7f1-4eb6-9dc7-b72f61af173d" />


```sql
SELECT c.cust_name AS "Customer Name",
       c.city AS "city",
       s.name AS "Salesman",
       s.city AS "city",
       s.commission
FROM customer AS c
INNER JOIN salesman AS s
    ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;

```

**Output:**

![A9]<img width="1264" height="459" alt="image" src="https://github.com/user-attachments/assets/82776617-5d89-4d58-a1dc-6c5892d6195e" />


**Question 10**

![Q10]<img width="1743" height="279" alt="image" src="https://github.com/user-attachments/assets/b8886a0b-09d1-41de-8260-7d6a8ac1e96a" />


```sql
SELECT 
    c.*
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
WHERE 
    o.ord_date BETWEEN '2012-08-01' AND '2012-08-30';

```

**Output:**

![A10]<img width="1346" height="433" alt="image" src="https://github.com/user-attachments/assets/7491dd23-d390-44f8-84fe-81fe7945d6ad" />


### Module-5 Grade:

<img width="1736" height="86" alt="image" src="https://github.com/user-attachments/assets/a3716270-c804-42d1-bae0-e92dc341eb66" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
