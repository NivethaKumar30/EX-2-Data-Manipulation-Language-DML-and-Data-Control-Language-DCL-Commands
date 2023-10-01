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

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/ddbf4ecf-4813-4c85-850f-519a94d53d33)


Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
QUERY:
```
update managers set salary=salary+(salary*10/100);
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/5f0eed65-1762-4085-85c9-8da68b9f1980)


Q2) Delete the records from manager table where the salary less than 2750.

QUERY:
```
delete managers where salary<2750;
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/5de83111-6ef4-448e-a45f-e832859674c3)


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

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/3ca81769-bb9a-4783-89fe-f847ba736c43)


Q4) List the names of Clerks from emp table.
QUERY:
```
select ename from managers where designation='clerk';
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/a84e6ca8-621b-4a86-b1d7-6d59700e771e)


Q5) List the names of employee who are not Managers.

QUERY:
```
select ename from managers where designation!='manager';
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/1ab4ad00-bfd8-46c2-89e1-0af5a305ae57)


Q6) List the names of employees not eligible for commission.

QUERY:
```
select ename from managers where commission=0;
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/e62e919e-0984-4cd1-8fe5-a6f88b6b9c2d)


Q7) List employees whose name either start or end with ‘s’.

QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/75970050-12d3-48e2-824f-108e97097ccc)


Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/91108c57-d16f-4bdb-94f0-882e862bbddb)


Q9) List the Details of Employees who have joined before 30 Sept 81.

QUERY:
```
select * from managers where hiredate < '30 SEP 81';
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/f4021c4f-d994-4935-9ea8-80d7b416c078)


Q10) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/c71046cd-3cdc-40b3-b900-d9a7409980e3)


Q11) List the names of employees not belonging to dept no 30,40 & 10

QUERY:
```
select ename from managers where deptno NOT IN (30,40,10);
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/e0018862-8dd0-41f6-b01b-da7554017000)


Q12) Find number of rows in the table EMP

QUERY:
```
select count(*) as rownumber from managers;
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/d1f125d1-b7b9-4cbc-87b9-08e0c051750f)


Q13) Find maximum, minimum and average salary in EMP table.
QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary)
as averagesal from managers;
```
OUTPUT:
![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/06eeca65-a626-49c6-aa6c-9af6fd47bec6)


Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```
OUTPUT:

![image](https://github.com/NivethaKumar30/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559844/777ba178-8ba2-4d66-970d-7f7eeae4e5fd)
