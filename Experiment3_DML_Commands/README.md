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
![image](https://github.com/user-attachments/assets/b26fa6ac-61aa-4089-9f8a-2225730fe38a)

```
update employees
set first_name = 'John'
where department_id = 80 and 
commission_pct < 0.35 ;
```



**Output:**

![image](https://github.com/user-attachments/assets/6efdc7f4-fd6d-44f6-86d4-1440a87b6caa)


**Question 2**
![image](https://github.com/user-attachments/assets/cc066eed-b171-47fe-8ae9-50d1df0616f7)

```
update suppliers
set supplier_name = upper(supplier_name)
where contact_person like '%Singh%';
```


**Output:**

![image](https://github.com/user-attachments/assets/3c75c679-ca9b-435c-a031-f6a089a4c1ca)

**Question 3**
![image](https://github.com/user-attachments/assets/cb7655e4-1aee-4b62-9ee5-7fddba7b839e)

```
update products 
set reorder_lvl = reorder_lvl * 0.7
where cost_price > 50
and quantity < 100;
```



**Output:**

![image](https://github.com/user-attachments/assets/558126fa-8362-4339-a489-7b8b14a5f7bc)


**Question 4**
![image](https://github.com/user-attachments/assets/6b7c26ae-0cfc-4759-ba85-34e400e7d3bc)

```
update products 
set availability = availability * 2
where product_id =1;
```



**Output:**
![image](https://github.com/user-attachments/assets/3cdc3451-6737-4481-8420-aea835a600f5)


**Question 5**
![image](https://github.com/user-attachments/assets/0ccbd51a-4666-43e9-973c-05de58851389)

```
update employees
set email = 'not available',
commission_pct = 0.55
where department_id =110;
```


**Output:**
![image](https://github.com/user-attachments/assets/1d895147-cf68-41d7-a127-84faedfa5959)

**Question 6**
![image](https://github.com/user-attachments/assets/3f7d309f-453c-4697-89d5-b2d1fe4483b0)
```
delete from customer where cust_country not in ('UK','USA','Canada') and grade >= 3;
```



**Output:**

![image](https://github.com/user-attachments/assets/dc26fd0f-4877-41df-96d1-3eab8a23413c)


**Question 7**
![image](https://github.com/user-attachments/assets/cc1bdca0-ef34-4c10-a249-a43cfea4e1ff)

```
delete from Doctors where specialization = 'Cardiology';
```



**Output:**
![image](https://github.com/user-attachments/assets/45d366a8-a973-49b1-8e6c-b8253f235cc0)


**Question 8**
![image](https://github.com/user-attachments/assets/cf23dbff-c99b-43ee-80f2-33a6a835033a)

```
delete from Customer where (GRADE =3 or AGENT_CODE = 'A008')and OUTSTANDING_AMT < 5000;
```

**Output:**

![image](https://github.com/user-attachments/assets/07cfd4bd-6efb-47d2-80a0-4e9022e56224)


**Question 9**
![image](https://github.com/user-attachments/assets/23665ab7-6239-4f75-ad4f-2fbe44bd3e9c)\

```
delete from Customer where CUST_NAME like '%Holmes%';
```



**Output:**

![image](https://github.com/user-attachments/assets/b0bf1a01-2e57-44be-862d-307388bd21ea)


**Question 10**
![image](https://github.com/user-attachments/assets/ddb019a1-1287-4903-a0a7-3d5d09b053e8)

```
delete from Customer where AGENT_CODE in ('A003','A008');
```


**Output:**
![image](https://github.com/user-attachments/assets/239d6694-1493-49b9-959b-28e7d9fc2ef0)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
