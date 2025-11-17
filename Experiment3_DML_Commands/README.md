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
-- Update the 'Selling_Price' to add 10% extra margin for all products supplied by the supplier with id 6.

PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT

```sql
-- update products set sell_price=(sell_price+sell_price*0.10) where supplier_id=6
```

**Output:**

<img width="1187" height="544" alt="image" src="https://github.com/user-attachments/assets/0d6ff306-b31f-4c35-9019-2f54cc49ae9a" />


**Question 2**
---
-- Write a SQL statement to change the first_name column of employees table with 'John' for those employees whose department_id is 80 and gets a commission_pct below 0.35.

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id

```sql
-- update Employees set FIRST_NAME="John" where (DEPARTMENT_ID=80 and COMMISSION_PCT<0.35)
```

**Output:**

<img width="1184" height="527" alt="image" src="https://github.com/user-attachments/assets/cbdc5825-30c1-4801-bcb5-37e214eef4fe" />


**Question 3**
---
-- Write a SQL statement to change the email column of employees table with 'Unavailable' for all employees in employees table.

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id
 

```sql
-- UPDATE Employees SET Email="Unavailable" 
```

**Output:**

<img width="1188" height="428" alt="image" src="https://github.com/user-attachments/assets/a40549ac-3938-40f0-a75b-c79be456a34a" />


**Question 4**
---
-- Write a SQL statement to double the availability of the product with product_id 1.

products table

---------------
product_id
product_name
category_id
availability

```sql
-- update products set availability=availability*2 where product_id=1
```

**Output:**

<img width="1190" height="214" alt="image" src="https://github.com/user-attachments/assets/4c1127ad-c98e-4995-9e07-52eb9fe99131" />


**Question 5**
---
-- Write a SQL query to Delete a Specific Surgery whose ID is 3

Sample table: Surgeries

attributes: surgery_id, patient_id, surgeon_id, surgery_date

```sql
-- delete FROM Surgeries where surgery_id=3
```

**Output:**

<img width="1185" height="369" alt="image" src="https://github.com/user-attachments/assets/cfe5510a-a048-4047-ab77-9d73dfcd188f" />


**Question 6**
---
-- Write a SQL query to Delete customers whose 'GRADE' is greater than 2 and have a 'PAYMENT_AMT' less than the average 'PAYMENT_AMT' for all customers, or whose 'OUTSTANDING_AMT' is greater than 8000:

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000

```sql
-- delete FROM Customer where ((GRADE>2 AND PAYMENT_AMT<(SELECT AVG(PAYMENT_AMT) FROM Customer)) OR OUTSTANDING_AMT>8000)
```

**Output:**

<img width="1189" height="654" alt="Screenshot 2025-11-03 162400" src="https://github.com/user-attachments/assets/c535b308-a1e6-4c16-94fb-56308b995dd2" />


**Question 7**
---
-- Write a SQL query to Delete customers with 'CUST_COUNTRY' 'UK' and 'WORKING_AREA' 'London' whose 'GRADE' is less than 3

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.

```sql
-- delete FROM Customer where (CUST_COUNTRY="UK" AND WORKING_AREA="London" AND GRADE<3)
```

**Output:**
<img width="1184" height="445" alt="image" src="https://github.com/user-attachments/assets/77cea457-8ec2-4975-84e6-cbcb3b3b77c1" />


**Question 8**
---
--Write a SQL query to Delete customers from 'customer' table where 'CUST_COUNTRY' is neither 'India' nor 'USA'.

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000

```sql
-- delete from Customer where CUST_COUNTRY<>"India" and CUST_COUNTRY<>"USA" 
```

**Output:**

<img width="1183" height="534" alt="image" src="https://github.com/user-attachments/assets/d1c7dac2-7ce4-4ff0-a7e9-878a4635d545" />


**Question 9**
---
-- Write a query to fetch 3 top salaried records from EmployeePosition table.
EmpID

EmpPosition

DateOfJoining

Salary

1

Manager

01/05/2024

500000

2

Executive

02/05/2024

75000

```sql
-- SELECT * from EmployeePosition ORDER BY Salary DESC Limit 3
```

**Output:**
<img width="1180" height="250" alt="image" src="https://github.com/user-attachments/assets/de203b99-4681-402d-a217-f57c3e4ce0e0" />


**Question 10**
---
-- Write a query to find the names of employees that begin with ‘S’ from EmployeeInfo table.

EmpID

EmpFname

EmpLname

Department

Project

Address

DOB

Gender

1

Sanjay

Mehra

HR

P1

Hyderabad(HYD)

01/12/1976

M

2

Ananya

Mishra

Admin

P2

Delhi(DEL)

02/05/1968

F

```sql
-- Select * from Employeeinfo where EmpFname LIKE 'S%'
```

**Output:**

<img width="1194" height="246" alt="image" src="https://github.com/user-attachments/assets/6601c197-4342-4147-9fab-790782ab727f" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
