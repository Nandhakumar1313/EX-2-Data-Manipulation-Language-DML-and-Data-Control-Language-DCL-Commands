# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```sql
update manager set salary=salary+(salary*0.10);
```


### OUTPUT:
![271218363-1d66948b-7919-4849-81d5-c2a58efa216c](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/4eff4551-fde9-4c71-8693-2610957c794d)


### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```sql
delete from manager where salary<2750;
```


### OUTPUT:
![271218422-70f3423a-36d3-485a-b4b6-f56fcccb2236](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/eff27463-6b14-484b-a5ed-754fcec9cc68)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```sql
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![271218480-5e34fa0e-672f-4860-ab8d-d6430226f451](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/646d4535-7386-49a4-9d53-d4b5661a6e66)



### Q4)	List the names of Clerks from emp table.


### QUERY:
```sql
select ename from manager where designation='clerk';
```

### OUTPUT:
![271218562-1d15721d-77df-4a22-9ecc-5e9ead999a60](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/e30259d3-9e06-4c2c-949f-8a11a6a3681f)


### Q5)	List the names of employee who are not Managers.


### QUERY:
```sql
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![271218602-db21a708-0df8-451e-abe2-abd3c132c438](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/1a19f171-f8fb-4542-8b67-cc603c8a7124)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```sql
select ename from manager where commission=0;
```

### OUTPUT:
![271218638-ff826474-3a2d-4ece-9176-10d3efd5f6c1](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/072f0871-a365-4fb6-9e7f-631032bcb90e)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```sql
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![271218671-25d6e637-c8e0-4d32-bd28-cb0e9f165e2e](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/0de78241-0e7b-4009-a14b-cce3c27c70ba)



### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```sql
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:

![271218714-d867d163-6acd-46a9-a509-3ae70ab45287](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/8bc5e27c-aba7-4350-b11d-4b0ec371b088)

### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```sql
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![271218808-e43e7182-4761-4e64-b432-0ae4ed69e8b4](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/220b24f7-6b37-473e-afce-cdfa50e02cdc)



### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```sql
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![271218897-29a7a7f2-b4e4-4d0c-a4d4-9b40d28953eb](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/358a8f4e-ad7a-482b-9801-4420f9252a97)


### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```sql
select ename from manager where deptno not in (30,40,10);
```


### OUTPUT:
![271219011-5c3e9892-e46f-40df-a083-040ae71c6ad3](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/09d6f5ef-8435-48ff-8deb-2c9bad2e24d7)


### Q12) Find number of rows in the table EMP

### QUERY:
```sql
select count(*) from manager;
```

### OUTPUT:
![271219036-7cf2d54d-b57a-44f4-a4c1-49c8fed11b79](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/0ff522e6-4f4d-4f5c-893d-70d4ccf57b28)


### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
### MAXIMUM
```sql
select max(salary) from manager;
```

### OUTPUT:
![271219098-753cec17-4df0-4ef1-a2aa-0ba6ae919bd3](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/e87c76cf-3756-4da6-b37d-2832d9193605)

### MINIMUM:
```sql
select min(salary) from manager;
```
### OUTPUT:
![271219144-35ae26d9-02fb-4f68-bb94-dbae7e3be808](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/28603dbe-e894-48b0-91d2-572b1570f100)

### AVERAGE:
```sql
select avg(salary) from manager;
```
### OUTPUT:
![271219191-284e827c-536f-4d74-998b-5e895f73030c](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/eff27be4-aabb-4eca-b9bf-2d9fd2f7c1ad)



### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;

```

### OUTPUT:
![271219234-df54174f-6bf2-4813-b72a-f350a2ca8b63](https://github.com/Nandhakumar1313/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120230694/85fa91aa-1cf6-4730-8139-d0eb21db1d55)

### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.

