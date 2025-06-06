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

**Question 1**
![image](https://github.com/user-attachments/assets/c75386cf-2625-42ec-8544-744bc9ca9a84)

```
select o.ord_no,o.purch_amt,c.cust_name,c.city
from orders o inner join customer c 
on o.customer_id=c.customer_id
where o.purch_amt between 500 and 2000
```

**Output:**
![image](https://github.com/user-attachments/assets/9a544889-c983-4768-81f1-2b65c126f40a)

**Question 2**
![image](https://github.com/user-attachments/assets/9e9df38c-3424-4c90-8ac8-7513e2f0bf40)

```
select s.* from Salesman s left join Customer c on s.salesman_id=c.salesman_id where c.cust_name = 'Fabian Johns'
```

**Output:**
![image](https://github.com/user-attachments/assets/7fa2ac36-fedb-470b-8a63-bf575d99d8a3)


**Question 3**
![image](https://github.com/user-attachments/assets/d14bfa9a-49c5-4b46-b562-c70c82d08910)

```
select p.first_name as "patient_name" from PATIENTS p inner join TEST_RESULTS t 
on p.patient_id=t.patient_id 
where t.test_name = 'Blood Pressure'
```



**Output:**


![image](https://github.com/user-attachments/assets/aca606d4-5aa2-446a-b47b-c15f37b035b2)


**Question 4**
![image](https://github.com/user-attachments/assets/05cee7b7-8afe-4023-ad66-8d4b293c6daf)

```
select o.ord_no,o.purch_amt,o.ord_date,c.cust_name,c.city as "customer_city",c.grade,s.name as "salesman_name",s.city as "salesman_city",s.commission
from orders o join customer c on o.customer_id=c.customer_id
join salesman s on o.salesman_id=s.salesman_id
```


**Output:**

![image](https://github.com/user-attachments/assets/b25f8c45-53f9-4dda-a806-e65ec330f22d)

**Question 5**
![image](https://github.com/user-attachments/assets/2d3f2f2c-b07b-4381-86c6-9f26df24b1eb)

```
select t.* from TEST_RESULTS t inner join PATIENTS p on p.patient_id = t.patient_id where first_name = "Alice"
```



**Output:**

![image](https://github.com/user-attachments/assets/ad44e2ef-2eff-4b3c-a0af-00cd2244a317)


**Question 6**
![image](https://github.com/user-attachments/assets/2782ae57-b45d-4bb5-81a2-69f249daa8d1)

```
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

![image](https://github.com/user-attachments/assets/c30f14d1-fea2-40e5-8ef8-0e8d948ccaa4)


**Question 7**
![image](https://github.com/user-attachments/assets/431e5425-6f12-405a-acfc-73c447449c19)

```
SELECT 
    p.first_name AS patient_name,
    t.*
FROM 
    test_results t
INNER JOIN 
    patients p ON t.patient_id = p.patient_id
WHERE 
    p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';
```


**Output:**

![image](https://github.com/user-attachments/assets/215e3e16-f108-47a8-b20c-98c194ca20fc)


**Question 8**
![image](https://github.com/user-attachments/assets/6d7d328f-bb82-467e-932a-94331cbd6f58)

```
SELECT 
    c.cust_name,
    c.city ,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;
```


**Output:**

![image](https://github.com/user-attachments/assets/5b6f44f4-f33a-47b1-b7c4-f8672afefff2)

**Question 9**
![image](https://github.com/user-attachments/assets/2d1ba652-c92d-472e-96d0-60a1249bc8c2)

```
SELECT 
    c.cust_name,
    c.city ,
    c.grade,
    s.name AS Salesman,
    s.city
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    c.grade < 300
ORDER BY 
    c.customer_id ASC;

```


**Output:**

![image](https://github.com/user-attachments/assets/dafde5e5-51fc-475b-b9cf-e7a24b1f3933)


**Question 10**
![image](https://github.com/user-attachments/assets/4dca489d-275c-41bc-a9a2-d654aa9768fe)

```
SELECT DISTINCT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id
WHERE c.city = 'London';

```


**Output:**
![image](https://github.com/user-attachments/assets/75a65385-50d4-46cd-b74c-f77a451503d4)



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
