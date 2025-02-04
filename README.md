# SQL-DB-Assignment
This assignment focuses on setting up and managing an **EMPLOYEE** database, which consists of two tables: **EmployeeInfo** and **EmployeePosition**. It covers tasks such as database creation, table setup, data insertion, and executing a series of SQL queries.

## Database Schema

### Tables:

#### 1. **EmployeeInfo**


| Column Name   | Data Type     | 
| ------------- | ------------- |
| `EmpID`       | INT           | 
| `EmpFname`    | VARCHAR(50)    | 
| `EmpLname`    | VARCHAR(50)    | 
| `Department`  | VARCHAR(50)    | 
| `Project`     | VARCHAR(20)    | 
| `Address`     | VARCHAR(50)    | 
| `DOB`         | DATE          | 
| `Gender`      | VARCHAR(20)    | 


---

#### 2. **EmployeePosition**


| Column Name      | Data Type     | 
| ---------------- | ------------- | 
| `EmpID`          | INT           | 
| `EmpPosition`    | VARCHAR(50)    | 
| `DateOfJoining`  | DATE          | 
| `Salary`         | INT           |



---

## SQL Queries for Employee Database

This document contains SQL queries to perform various operations on the **Employee Database**, specifically on the **EmployeeInfo** and **EmployeePosition** tables.

## Queries

### 1. Fetch the number of employees working in the department 'Admin'

```sql
select count(*) as employee_count from employee_info where department = 'Admin';
```

### 2. Retrieve the first four characters of  EmpLname from the EmployeeInfo table.

```sql
select substring(emplname , 1,4) from employee_info;
```
### 3. Retrieve the first four characters of  EmpLname from the EmployeeInfo table.
```sql
select e.empfname,e.emplname,p.salary from employee_info e inner join employee_position p on e.empid = p.empid and p.salary between 50000 and 100000;
```

### 4. Find the names of employees that begin with ‘S’
```sql
select emplname,empfname from employee_info where empfname like 'S%';
```
### 5. Fetch top N records order by salary. (ex. top 5 records)
```sql
 select * from employee_position order by salary desc limit 5;

```
### 6. Fetch details of all employees excluding the employees with first names, “Sanjay” and “Sonia” from the EmployeeInfo table.
```sql
select * from employee_info where empfname not in ('Sanjay','Sonia');
```

### 7. Fetch the department-wise count of employees sorted by department’s count in ascending order.
```sql
select count(*),department from employee_info group by department order by count(*) desc;
```

### 8. Create indexing for any particular field and show the difference in data fetching before and after indexing

```sql
create index idx_fname on employee_info(empfname);

```


