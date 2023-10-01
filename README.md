#EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL

AIM:
To create a manager database and execute DML queries using SQL.

#DML(Data Manipulation Language)

The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

#List of DML commands:

INSERT: It is used to insert data into a table.

UPDATE: It is used to update existing data within a table.

DELETE: It is used to delete records from a database table.

Create the table as given below:
```
create table managers(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
insert the following values into the table
```
insert into managers values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into managers values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into managers values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into managers values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
Output:
Creating and inserting values into table

Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
QUERY:
```
update managers set salary=salary+(salary*10/100);
```
OUTPUT:
Updation

Q2) Delete the records from manager table where the salary less than 2750.
QUERY:
```
delete managers where salary<2750;
```
OUTPUT:
Deletion

Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
QUERY:
```
SELECT
ename AS "Name",
salary*12 AS "Annual Salary"
FROM
managers;
```
OUTPUT:
Updation

Q5) List the names of Clerks from emp table.
QUERY:
```
select ename from managers where designation='clerk';
```
OUTPUT:
Listing

Q6) List the names of employee who are not Managers.
QUERY:
```
select ename from managers where designation!='manager';
```
OUTPUT:
Listing

Q7) List the names of employees not eligible for commission.
QUERY:
```
select ename from managers where commission=0;
```
OUTPUT:
Listing

Q8) List employees whose name either start or end with ‘s’.
QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```
OUTPUT:
Listing

Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```
OUTPUT:
Sorting

Q10) List the Details of Employees who have joined before 30 Sept 81.
QUERY:
```
select * from managers where hiredate < '30 SEP 81';
```
OUTPUT:
Listing

Q11) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```
OUTPUT:
Listing

Q12) List the names of employees not belonging to dept no 30,40 & 10
QUERY:
select ename from managers where deptno NOT IN (30,40,10);
OUTPUT:
Listing

Q13) Find number of rows in the table EMP
QUERY:
```
select count(*) as rownumber from managers;
```
OUTPUT:

Count of rows

Q14) Find maximum, minimum and average salary in EMP table.
QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary)
as averagesal from managers;
```
OUTPUT:
Finding

Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
QUERY:
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
OUTPUT:
