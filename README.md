## EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
### AIM:
To create a manager database and execute DML queries using SQL.

### DML(Data Manipulation Language)
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
### List of DML commands:
INSERT: It is used to insert data into a table.
UPDATE: It is used to update existing data within a table.
DELETE: It is used to delete records from a database table.
### Create the table as given below:
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
### Insert the following values into the table
```
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
#### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/3017411e-5608-47f6-9d2a-e48238086828)


### Q2) Delete the records from manager table where the salary less than 2750.
#### QUERY:
```
delete from manager where salary<2750;
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/bec4bfd5-6d8c-4b52-85a0-533f7437545d)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
#### QUERY:
```
select ename as "Name", salary*12 as "Annual salary" from manager;
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/356f7543-7547-4c55-8139-73d3829348f3)
### Q4) List the names of Clerks from emp table.
#### QUERY:
```
select ename from manager where designation='clerk';
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/142735ef-b757-442c-b242-8e333a36e6c8)

### Q5) List the names of employee who are not Managers.
#### QUERY:
```
select ename from manager where designation <> 'manager';
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/8ae02ce4-2479-4e7f-92bd-7850b3188b75)

### Q6) List the names of employees not eligible for commission.
#### QUERY:
```
select ename from manager where commission=0;
```
#### OUTPUT:

![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/365425c1-a254-4e61-ab4b-97b717f34422)


### Q7) List employees whose name either start or end with ‘s’.
#### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
#### OUTPUT:

![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/f95fc9d4-2044-4a79-a4f5-08bcae932f10)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
#### QUERY:
```
select ename, designation as "job", deptno, hiredate from manager order by hiredate asc;
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/f1f84707-d08c-4dc4-a8de-e7c783cd6de6)

### Q9) List the Details of Employees who have joined before 30 Sept 81.
#### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/00be118a-7545-4298-8a39-260f4c6960ad)

### Q10) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
#### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/9c3d8602-1a51-458b-a23f-3242962e959d)

### Q11) List the names of employees not belonging to dept no 30,40 & 10
#### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/9389061b-377c-465e-a1c7-c790c0854132)

### Q12) Find number of rows in the table EMP
#### QUERY:
```
select count(*) from manager;
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/d7deb371-bc52-4a3c-8da6-658f574a9f4f)

### Q13) Find maximum, minimum and average salary in EMP table.
#### MAXIMUM:
#### QUERY:
```
select max(salary) from manager;
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/a0ff5a22-6951-40cb-bc44-36ae3a859721)
#### MINIMUM:
#### QUERY:
```
select min(salary) from manager;
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/17b68d6b-9c10-45a8-9c52-75147951cf87)
#### AVERAGE:
#### QUERY:
```
select avg(salary) from manager;
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/ac9acb76-7733-4acf-b7e1-bf6c10c8a9c6)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
#### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
#### OUTPUT:
![image](https://github.com/harini1006/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497405/88f42bad-9ca3-4eb7-b3aa-d6c0ffdc580d)

