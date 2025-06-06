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
![image](https://github.com/user-attachments/assets/4adae88e-72ef-4d38-9f84-4092daf08d12)

```
SELECT Medication, count(*) as TotalPrescriptions from Prescriptions GROUP BY Medication;
```

**Output:**
![image](https://github.com/user-attachments/assets/0e6274f5-7f6d-4bf1-824a-c2d61057ed21)

**Question 2**
![image](https://github.com/user-attachments/assets/1cd5aa5a-cb0d-4560-81b3-3894b8695c9e)

```
select Gender, count(*) as TotalPatients from Patients group by Gender;
```

**Output:**

![image](https://github.com/user-attachments/assets/9fc1eeca-5ce7-4442-8164-928d9e1b1bde)


**Question 3**
![image](https://github.com/user-attachments/assets/a124e803-c672-4a32-99ea-e8afeffd49f1)

```
select date(AppointmentDateTime) as AppointmentDate,
count(*) as TotalAppointments from  Appointments group by date(AppointmentDateTime) order by AppointmentDate;
```


**Output:**
![image](https://github.com/user-attachments/assets/f5dc56b4-0a02-491e-8a63-4ef009a496fa)

**Question 4**
![image](https://github.com/user-attachments/assets/92d084b2-9901-473d-92b6-ac194de62641)

```
select count(*) as COUNT from customer where city = 'Noida';
```


**Output:**

![image](https://github.com/user-attachments/assets/3d6556d3-98a3-4c96-98ab-bdf70cd599cf)


**Question 5**
![image](https://github.com/user-attachments/assets/936524f5-aa2c-4bed-9ecd-8c4bbda46b0d)

```
select COUNT(*) as COUNT from customer where grade is not null;
```


**Output:**

![image](https://github.com/user-attachments/assets/f8630c8c-290a-4158-9099-9dc52f59adde)


**Question 6**
![image](https://github.com/user-attachments/assets/6b1466c4-2d04-4f9c-ac1d-29fb2732a0b0)

```
select SUM(income) as "total_income" from employee where age >= 40;
```


**Output:**
![image](https://github.com/user-attachments/assets/5fb022e5-fae1-443d-a49e-f02e48965f64)

**Question 7**
![image](https://github.com/user-attachments/assets/7ea40077-2115-4d35-88ee-73e26137ac80)

```
select address,SUM(salary) from customer1 group by address having sum(salary) > 2000;
```


**Output:**

![image](https://github.com/user-attachments/assets/1f37027f-5c69-4178-9b11-41c55af3a8b5)


**Question 8**
![image](https://github.com/user-attachments/assets/ec096f99-ee9e-4c66-b0aa-44f5f406617a)

```
select city, SUM(income) as Income from employee group by city having SUM(income) > 200000;
```


**Output:**
![image](https://github.com/user-attachments/assets/8f4b6b76-d033-4763-bc5e-e076453e2227)


**Question 9**
![image](https://github.com/user-attachments/assets/3046cf74-9d0b-44d3-a9d3-a469db7890e6)

```
select jdate, MAX(workhour) from employee1 group by jdate having MAX(workhour) > 12;
```


**Output:**
![image](https://github.com/user-attachments/assets/973db15a-1355-44d8-8519-ea90d37e6425)

**Question 10**

![image](https://github.com/user-attachments/assets/fc719711-05d2-41b7-a8a8-8d21b6056f76)

```
select DoctorID,count(*) as TotalPrescriptions from Prescriptions group by DoctorID
```


**Output:**
![image](https://github.com/user-attachments/assets/29007258-4aa3-4447-8a4c-5d6de05b21f3)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
