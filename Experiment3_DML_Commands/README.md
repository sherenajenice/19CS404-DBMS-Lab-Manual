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
<img width="803" height="216" alt="image" src="https://github.com/user-attachments/assets/9e17068d-bf2e-4efb-a49f-e23c36412a9a" />

```sql
update suppliers
set supplier_name = 'A1 Suppliers' 
where supplier_id =8 ;
```

**Output:**

<img width="1616" height="334" alt="image" src="https://github.com/user-attachments/assets/cbb2b093-a3d4-4210-bcdc-44401da314af" />


**Question 2**
---
<img width="1100" height="520" alt="image" src="https://github.com/user-attachments/assets/9c0c1414-7b3e-4441-9b4a-55f377c1b548" />


```sql
update Products
set sell_price = cast(cost_price * 1.35 as int)
where ((sell_price - cost_price)/sell_price) < 0.30;

```

**Output:**

<img width="1659" height="367" alt="image" src="https://github.com/user-attachments/assets/7ec0f975-a32a-4b1c-8c31-1387910228af" />



**Question 3**
---
<img width="876" height="307" alt="image" src="https://github.com/user-attachments/assets/7123befa-2b98-4bee-87d4-0a557986b79d" />

```sql
update products
set reorder_lvl = 20
where quantity < 10
and category = 'Snacks';
```

**Output:**

<img width="1509" height="406" alt="image" src="https://github.com/user-attachments/assets/642610b8-b326-4580-acb6-5d1f42d9f922" />


**Question 4**
---
<img width="679" height="185" alt="image" src="https://github.com/user-attachments/assets/2d7d023a-ed72-4df3-b8f9-01bb31da3457" />

```sql
update sales
set sell_price = sell_price * 1.05
where product_id = 15
and sale_date =  '2023-01-31';`sql

```

**output:**

<img width="1244" height="336" alt="image" src="https://github.com/user-attachments/assets/19364fb6-064a-4a9a-b21e-eafa1ea598af" />


**Question 5**
---
<img width="852" height="524" alt="image" src="https://github.com/user-attachments/assets/da0b4cf9-8190-4516-88c2-e9e1516a5ffe" />


```sql
update sales
set sell_price = sell_price + 3
where product_id IN(SELECT product_id FROM PRODUCTS WHERE supplier_id = 4);
```

**Output:**

<img width="1259" height="282" alt="image" src="https://github.com/user-attachments/assets/4954c119-988e-43ad-b2fa-ab34c8a74b33" />


**Question 6**
---
<img width="1191" height="383" alt="image" src="https://github.com/user-attachments/assets/c9c1de80-b8f9-406d-9955-0fc52cbe77d1" />


```sql
delete from customer
where WORKING_AREA = 'New York';
```

**Output:**

<img width="1782" height="497" alt="image" src="https://github.com/user-attachments/assets/c00f7a6a-2b0d-47c0-9fb9-f9acacde7bc6" />



**Question 7**
---
<img width="1206" height="603" alt="image" src="https://github.com/user-attachments/assets/4e69e773-ce73-4455-9a5b-878fe2445b8e" />


```sql
delete from customer
where agent_code in ('A003','A008');
```

**Output:**

<img width="728" height="667" alt="image" src="https://github.com/user-attachments/assets/29e08aba-8519-4afb-9774-495fc1f51062" />


**Question 8**
---
<img width="1459" height="428" alt="image" src="https://github.com/user-attachments/assets/a9fc21a2-dff1-41dd-8de0-59ac654bf70d" />


```sql
delete from customer
where cust_city <>  'New York' 
and outstanding_amt >5000;
```

**Output:**

<img width="1783" height="398" alt="image" src="https://github.com/user-attachments/assets/900b4aa2-bb31-4f80-a61d-8ca1dff0045d" />


**Question 9**
---
<img width="1272" height="566" alt="image" src="https://github.com/user-attachments/assets/c2bc976e-3df3-4311-96aa-cd490cb053ed" />


```sql
delete from Doctors
where doctor_id between 2 and 4;
```

**Output:**

<img width="871" height="537" alt="image" src="https://github.com/user-attachments/assets/3d24973c-c973-44ed-89dd-3e6064134890" />



**Question 10**
---
<img width="1511" height="465" alt="image" src="https://github.com/user-attachments/assets/96dca5fc-b969-413b-8d51-98c4100695a5" />

```sql
delete from customer 
where CUST_COUNTRY NOT IN ('India','USA');
```

**Output:**

<img width="1774" height="375" alt="image" src="https://github.com/user-attachments/assets/205074ca-5b1c-4d81-ab9d-0f40bbd9ab75" />


## Grade

<img width="1078" height="55" alt="image" src="https://github.com/user-attachments/assets/6e219610-ca92-4949-98f7-71b3e2a1d424" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
