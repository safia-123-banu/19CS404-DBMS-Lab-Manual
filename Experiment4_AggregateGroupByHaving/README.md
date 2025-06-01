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
--
-- ![image](https://github.com/user-attachments/assets/ab1c44bc-7075-47f4-9e8f-aeadc4a3da64)

```sql
-- select InsuranceCompany, COUNT(DISTINCT PatientID) AS TotalPatients From Insurance GROUP BY InsuranceCompany; 
```

**Output:**

![image](https://github.com/user-attachments/assets/9a4fd066-e486-475e-a44e-91df56221571)

**Question 2**
---
--![image](https://github.com/user-attachments/assets/b17c8dca-c071-4580-b225-27cabf4306f1)

```sql
-- select DoctorID, COUNT(DISTINCT PatientID) AS TotalPrescriptions from Prescriptions group by DoctorID;
```

**Output:**

 ![image](https://github.com/user-attachments/assets/274fcba1-0de6-4bed-972e-89ac8ee8e4d0)

**Question 3**
---
--![image](https://github.com/user-attachments/assets/145cd93f-493e-437f-afed-daea37c22deb)

```sql
-- select DoctorID, count(DISTINCT PatientID) as TotalAppointments from Appointments group by DoctorID;
```

**Output:**

![image](https://github.com/user-attachments/assets/30d57a90-4e07-4b97-8a15-5e04dca1f324)

**Question 4**
---
--![image](https://github.com/user-attachments/assets/fd742d36-e1cc-4099-8ea7-43c7fe0b3992)

```sql
-- select COUNT(*) as COUNT from customer where city = 'Noida';
```

**Output:**

![image](https://github.com/user-attachments/assets/a63ab3c1-8b08-4dc5-8045-b0f71c8b992e)

**Question 5**
---
--![image](https://github.com/user-attachments/assets/4196d882-f6b1-4a4c-901e-62346e009a08)

```sql
-- select name as Employee_Name, MIN(age) as Age from employee;
```

**Output:**

![image](https://github.com/user-attachments/assets/67f41555-301f-400c-a616-35098bb690a5)

**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/745b7b7d-754e-4dcf-88de-36a5f8e36223)

```sql
-- select max(purch_amt) as MAXIMUM from orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/ee5a9c09-623f-4b6f-80da-b22b9aea633c)

**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/d8d83a38-ec4b-4cc8-a222-ff61a2b0e604)

```sql
-- select AVG(length(name)) as avg_name_length from customer where city='Chennai';
```

**Output:**

![image](https://github.com/user-attachments/assets/b423694a-bc20-4b29-b78b-320c5986fe01)

**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/e23b2d6e-70e6-4867-82f6-e2e45e96ccfe)

```sql
--select (age/5)*5 as age_group,SUM(salary) as 'SUM(salary)' from customer1 group by age_group having SUM(salary)>5000;
```

**Output:**

![image](https://github.com/user-attachments/assets/e22f5fde-13cd-4ec0-8996-681b984baa56)

**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/598c690f-d070-48c1-b680-d0e65cb07985)

```sql
-- select age,avg(income) as 'AVG(income)' from employee group by age having avg(income) between 300000 and 500000;
```

**Output:**

![image](https://github.com/user-attachments/assets/eb6e98dc-3dc9-49bb-b03d-c7c4083e898d)

**Question 10**
---
--![image](https://github.com/user-attachments/assets/e12e7f80-a3db-421e-839d-12000b4b3feb)

```sql
-- select jdate, max(workhour) as 'MAX(workhour)' from employee1 group by jdate having workhour >=12;
```

**Output:**

![image](https://github.com/user-attachments/assets/a0adb140-ad53-4b1f-838c-87e95908e7f1)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
