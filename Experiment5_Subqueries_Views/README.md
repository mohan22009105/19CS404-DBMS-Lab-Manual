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
![image](https://github.com/user-attachments/assets/13c843ee-838f-410d-a0fe-86c7dd8ddbec)

```
SELECT * FROM CUSTOMERS WHERE AGE<30;
```



**Output:**

![image](https://github.com/user-attachments/assets/0b28be02-e510-4913-bcec-8fce12d16aa7)


**Question 2**
![image](https://github.com/user-attachments/assets/ec868d9f-ba8a-4c12-be05-2c60a6ffe63c)

```
SELECT * FROM ORDERS WHERE salesman_id in (SELECT salesman_id FROM SALESMAN WHERE city='New York');
```

**Output:**

![image](https://github.com/user-attachments/assets/451ec889-0e4f-48af-95e4-ccba776f17e3)


**Question 3**
![image](https://github.com/user-attachments/assets/1a4f2569-b798-4f37-ba80-e6c7163623c5)

```
SELECT salesman_id, name FROM salesman WHERE salesman_id IN (SELECT salesman_id FROM customer GROUP BY salesman_id HAVING COUNT(customer_id)>1);
```



**Output:**
![image](https://github.com/user-attachments/assets/68919018-bd35-425c-af06-d295b9d093c5)


**Question 4**
![image](https://github.com/user-attachments/assets/c90ab71b-7e77-4226-bbe0-6321d2eef528)

```
SELECT medication_id AS medic, medication_name, dosage FROM Medications WHERE dosage=(SELECT MAX(dosage) FROM Medications);
```



**Output:**
![image](https://github.com/user-attachments/assets/2cb75b8c-bd0f-4882-b42b-54e103573592)


**Question 5**
![image](https://github.com/user-attachments/assets/42bf82eb-1877-442b-8572-d39c8d6f229c)
```
SELECT * FROM orders WHERE salesman_id IN (SELECT salesman_id FROM salesman WHERE city='London');
```

**Output:**

![image](https://github.com/user-attachments/assets/2a5b9ec5-213e-490b-aa84-825cb0c04345)


**Question 6**
![image](https://github.com/user-attachments/assets/5f3f0253-80aa-489b-8b0d-b0c60ab7acff)

```
-- SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;
```


**Output:**

![image](https://github.com/user-attachments/assets/e249d2d6-7301-4353-992b-e88c45454249)

**Question 7**
![image](https://github.com/user-attachments/assets/aa987e11-9a24-44dd-aa18-68dfd0be11de)

```
-- SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';
```

**Output:**
![image](https://github.com/user-attachments/assets/4127be97-35d9-4471-8475-fb42bef9ec3f)


**Question 8**
![image](https://github.com/user-attachments/assets/0afa3842-4e7a-4e3c-813e-5442451ab24a)

```
-- SELECT name
FROM customer
WHERE phone NOT IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(phone) > 1
);
```

**Output:**
![image](https://github.com/user-attachments/assets/a9ff21db-1d8e-423f-8877-d37ce600229a)


**Question 9**
![image](https://github.com/user-attachments/assets/788b482c-2d33-499c-a3d9-97ef08731e87)

```
-- select  * from orders where salesman_id in (select salesman_id from salesman where name='Paul Adam');
```



**Output:**
![image](https://github.com/user-attachments/assets/06315b95-012c-41fd-9c8b-987846af3521)


**Question 10**
![image](https://github.com/user-attachments/assets/40a9cf19-ced3-4a76-804c-83923a6dbbfe)

```
-- select * from Employee where age<(select avg(age) from Employee where income>1000000);
```


**Output:**
![image](https://github.com/user-attachments/assets/048b81b2-a30f-4a4f-a5b6-1322e3c637b0)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
