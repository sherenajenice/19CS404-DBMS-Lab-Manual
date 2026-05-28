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
<img width="1329" height="374" alt="image" src="https://github.com/user-attachments/assets/e9ddc7ac-538b-429a-995b-92b1cdfedaf2" />

```sql
CREATE TABLE Employees(
EmployeeID PRIMARY KEY,
FirstName NOT NULL,
LastName NOT NULL,
Email UNIQUE,
Salary DECIMAL CHECK(Salary > 0 ),
DepartmentID INTEGER,
FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**
<img width="1747" height="429" alt="image" src="https://github.com/user-attachments/assets/058bbd12-d34b-41d6-b01a-99f8fab01908" />


**Question 2**
---
<img width="1266" height="327" alt="image" src="https://github.com/user-attachments/assets/48181595-a884-44e0-9b98-1fc7ee37c766" />

```sql
ALTER TABLE Student_details
ADD Date_of_birth Date;

```

**Output:**
<img width="1629" height="401" alt="image" src="https://github.com/user-attachments/assets/bce12997-1b25-4529-a118-40df09a90428" />



**Question 3**
---
<img width="1019" height="373" alt="image" src="https://github.com/user-attachments/assets/086e7677-61b0-4891-85fa-78ac839970c4" />


```sql
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE);
```

**Output:**
<img width="1309" height="293" alt="image" src="https://github.com/user-attachments/assets/e3085658-9780-4a67-974f-ffed53f810a8" />


**Question 4**
---
<img width="892" height="247" alt="image" src="https://github.com/user-attachments/assets/fb865893-a909-44f7-8293-54417e874e03" />


```sql
CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
DueDate DATE CHECK(DueDate > InvoiceDate),
Amount REAL CHECK(Amount > 0)
);
```

**Output:**
<img width="1068" height="230" alt="image" src="https://github.com/user-attachments/assets/c0526fd9-e1c8-40e7-96f9-17d8dba87fa6" />



**Question 5**
---
<img width="798" height="164" alt="image" src="https://github.com/user-attachments/assets/2bccbacf-18a3-40db-a676-20e6c08b60fc" />

```sql
INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
VALUES (201, 'David Lee', 'M', 'Physics', 92)
```

**Output:**
<img width="1288" height="202" alt="image" src="https://github.com/user-attachments/assets/53b5c4fd-2527-40d9-8f2d-8eba88b229e1" />



**Question 6**
---
<img width="1321" height="286" alt="image" src="https://github.com/user-attachments/assets/a054ce0e-5904-46f1-97ff-2876fd386e7f" />


```sql
CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
BonusAmount REAL CHECK(BonusAmount > 0),
BonusDate DATE,
Reason TEXT NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES  Employees(EmployeeID)
);
```

**Output:**
<img width="1325" height="256" alt="image" src="https://github.com/user-attachments/assets/6211429a-b7b2-454e-bc35-f8b54f8e9f68" />


**Question 7**
---
<img width="916" height="424" alt="image" src="https://github.com/user-attachments/assets/2d10a8a1-ad46-4b2b-9b44-f5997c19f669" />


```sql
ALTER TABLE Student_details
ADD State TEXT;
```

**Output:**
<img width="1304" height="306" alt="image" src="https://github.com/user-attachments/assets/6bb01cb9-cf5d-4728-8e8c-e1ed78b88535" />


**Question 8**
---
<img width="1076" height="255" alt="image" src="https://github.com/user-attachments/assets/09cd2db1-dc51-460a-8e5a-c1f07b523da3" />

```sql
CREATE TABLE Orders(
OrderID INTEGER PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID INTEGER,
FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

**Output:**
<img width="1308" height="229" alt="image" src="https://github.com/user-attachments/assets/66f8425b-10ab-42f8-8ffd-2a3d482e59f8" />



**Question 9**
---
<img width="799" height="319" alt="image" src="https://github.com/user-attachments/assets/f4bf6e2e-b2d7-432f-b120-832d5b602e6d" />


```sql
INSERT INTO student_details(RollNo,Name,Gender,Subject,MARKS)

SELECT RollNo,Name,Gender,Subject,MARKS FROM Archived_students;
```

**Output:**
<img width="1168" height="253" alt="image" src="https://github.com/user-attachments/assets/3f3fcfbc-ec12-4aa3-8487-f40dbda7a890" />

  

**Question 10**
---
<img width="890" height="398" alt="image" src="https://github.com/user-attachments/assets/63e41f5c-71b6-446e-b243-caa218118c92" />



```sql
alter table Student_details
add mobilenumber  number 
     
```

**Output:**

<img width="1306" height="300" alt="image" src="https://github.com/user-attachments/assets/abb1bf7c-92a6-4071-b234-93ce8316f355" />


## Grade

<img width="1738" height="86" alt="image" src="https://github.com/user-attachments/assets/7aad7f94-4dea-4989-9d1d-f5f34066bd17" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
