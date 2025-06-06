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

![image](https://github.com/user-attachments/assets/6e817b20-519b-42e1-b627-9a3e28c49969)

```
create table Events(
EventID INTEGER,
EventName TEXT,
EventDate  DATE);
```

**Output:**


![image](https://github.com/user-attachments/assets/da47908a-ec19-4b92-b7eb-f792ed895ce3)

**Question 2**``

![image](https://github.com/user-attachments/assets/5c2828a4-8b6a-4325-9af2-8b311539befa)

```
create table Shipments(
ShipmentID INTEGER primary key,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
foreign key (SupplierID) references Suppliers(SupplierID),
foreign key (OrderID) references  Orders(OrderID));
```



**Output:**


![image](https://github.com/user-attachments/assets/19ee4e59-a6c5-4f92-9afc-bf7dba07850c)


**Question 3**

![image](https://github.com/user-attachments/assets/f270a9a6-2e29-42fe-842a-0b00b2022248)

```
alter table employee add column first_name varchar(50);
alter table employee add column last_name varchar(50);
```


**Output:**

![image](https://github.com/user-attachments/assets/9c1b5440-ee89-4272-874c-e305a2d399e8)

**Question 4**

![image](https://github.com/user-attachments/assets/cb000533-397b-4b18-aaed-3c0ed554a3b6)

```
insert into Employee(EmployeeID,Name,Position) values (5,'George Clark','Consultant');
insert into Employee(EmployeeID,Name,Position,Department,Salary) values (7,'Noah Davis','Manager','HR', 60000);
insert into Employee(EmployeeID,Name,Position,Department)values (8,'Ava Miller','Consultant','IT');
```

**Output:**


![image](https://github.com/user-attachments/assets/850657d5-89eb-416c-9e74-780d8dbd2c59)


**Question 5**

![image](https://github.com/user-attachments/assets/a09d5f74-67df-44ba-baea-55e521bb3b8e)

```
alter table employee rename column id to employee_id;
```

**Output:**


![image](https://github.com/user-attachments/assets/32edb7a2-13ec-45fe-97b0-a14ddc802d46)

**Question 6**
![image](https://github.com/user-attachments/assets/da0cfe66-2112-443b-b213-110a689d39db)

```
create table Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE);
```



**Output:**


![image](https://github.com/user-attachments/assets/02be6854-be36-4cc2-8ccb-bc5506170f01)


**Question 7**
![image](https://github.com/user-attachments/assets/b4d2548e-eb29-483e-b3d3-b02c66df1c0b)

```
create table Invoices(
InvoiceID INTEGER primary key,
InvoiceDate DATE NOT NULL,
Amount REAL check(Amount >0),
DueDate DATE check(DueDate > InvoiceDate),
OrderID INTEGER ,
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID));
```


**Output:**
![image](https://github.com/user-attachments/assets/088ad864-82ba-483a-a012-2a296591f3d3)

**Question 8**
![image](https://github.com/user-attachments/assets/ee7549e0-ddb1-4fd1-92d7-b2757a7078fb)

```
alter table Companies ADD designation varchar(50);
alter table Companies ADD net_salary  number;
alter table Companies ADD dob date;
```


**Output:**

![image](https://github.com/user-attachments/assets/870a451d-a319-4421-835a-4022ef3e5ed7)


**Question 9**
![image](https://github.com/user-attachments/assets/5633ea07-6bf0-413a-a86e-1d035f345c97)

```
create table item(
item_id TEXT primary key,
item_desc TEXT,
rate INTEGER,
icom_id TEXT,
foreign key(icom_id) references company(com_id) on update cascade on delete cascade,
check(length(icom_id)=4)
);
```


**Output:**

![image](https://github.com/user-attachments/assets/51e48e4d-1382-4363-a7de-cd45ff80a95e)


**Question 10**
![image](https://github.com/user-attachments/assets/706ecc26-da4d-43ba-9a21-5b05255bbb6e)

```
alter table Student_details add ParentsNumber number;
alter table Student_details add Adhar_Number number;
```


**Output:**

![image](https://github.com/user-attachments/assets/76411eac-7c87-4a3f-bef7-aa346c202b86)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
