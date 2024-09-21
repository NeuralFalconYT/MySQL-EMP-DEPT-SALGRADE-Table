# MySQL-EMP-DEPT-SALGRADE-Table

Use https://www.programiz.com/sql/online-compiler/ for practice
```
DROP TABLE IF EXISTS emp;

CREATE TABLE emp (
  empno decimal(4,0) NOT NULL,
  ename varchar(10) default NULL,
  job varchar(9) default NULL,
  mgr decimal(4,0) default NULL,
  hiredate date default NULL,
  sal decimal(7,2) default NULL,
  comm decimal(7,2) default NULL,
  deptno decimal(2,0) default NULL
);

DROP TABLE IF EXISTS dept;

CREATE TABLE dept (
  deptno decimal(2,0) default NULL,
  dname varchar(14) default NULL,
  loc varchar(13) default NULL
);

DROP TABLE IF EXISTS salgrade;
CREATE TABLE salgrade (
  grade NUMBER,
  losal NUMBER,
  hisal NUMBER
);

INSERT INTO emp VALUES ('7369','SMITH','CLERK','7902','1980-12-17','800.00',NULL,'20');
INSERT INTO emp VALUES ('7499','ALLEN','SALESMAN','7698','1981-02-20','1600.00','300.00','30');
INSERT INTO emp VALUES ('7521','WARD','SALESMAN','7698','1981-02-22','1250.00','500.00','30');
INSERT INTO emp VALUES ('7566','JONES','MANAGER','7839','1981-04-02','2975.00',NULL,'20');
INSERT INTO emp VALUES ('7654','MARTIN','SALESMAN','7698','1981-09-28','1250.00','1400.00','30');
INSERT INTO emp VALUES ('7698','BLAKE','MANAGER','7839','1981-05-01','2850.00',NULL,'30');
INSERT INTO emp VALUES ('7782','CLARK','MANAGER','7839','1981-06-09','2450.00',NULL,'10');
INSERT INTO emp VALUES ('7788','SCOTT','ANALYST','7566','1982-12-09','3000.00',NULL,'20');
INSERT INTO emp VALUES ('7839','KING','PRESIDENT',NULL,'1981-11-17','5000.00',NULL,'10');
INSERT INTO emp VALUES ('7844','TURNER','SALESMAN','7698','1981-09-08','1500.00','0.00','30');
INSERT INTO emp VALUES ('7876','ADAMS','CLERK','7788','1983-01-12','1100.00',NULL,'20');
INSERT INTO emp VALUES ('7900','JAMES','CLERK','7698','1981-12-03','950.00',NULL,'30');
INSERT INTO emp VALUES ('7902','FORD','ANALYST','7566','1981-12-03','3000.00',NULL,'20');
INSERT INTO emp VALUES ('7934','MILLER','CLERK','7782','1982-01-23','1300.00',NULL,'10');

INSERT INTO dept VALUES ('10','ACCOUNTING','NEW YORK');
INSERT INTO dept VALUES ('20','RESEARCH','DALLAS');
INSERT INTO dept VALUES ('30','SALES','CHICAGO');
INSERT INTO dept VALUES ('40','OPERATIONS','BOSTON');

INSERT INTO salgrade VALUES (1, 700, 1200);
INSERT INTO salgrade VALUES (2, 1201, 1400);
INSERT INTO salgrade VALUES (3, 1401, 2000);
INSERT INTO salgrade VALUES (4, 2001, 3000);
INSERT INTO salgrade VALUES (5, 3001, 9999);
```
```
SELECT * FROM emp;
```
```
SELECT * FROM dept;
```
```
SELECT * FROM salgrade;
```

Description of the table EMP: 
```
SQL> desc emp;
 Name                                                              Null?    Type
 ----------------------------------------------------------------- -------- --------------------------------------------
 EMPNO                                                             NOT NULL NUMBER(4)
 ENAME                                                                      VARCHAR2(10)
 JOB                                                                        VARCHAR2(9)
 MGR                                                                        NUMBER(4)
 HIREDATE                                                                   DATE
 SAL                                                                        NUMBER(7,2)
 COMM                                                                       NUMBER(7,2)
 DEPTNO                                                                     NUMBER(2)
```
Display EMP table:
```
SQL> select * from emp;
```
```
     EMPNO ENAME      JOB              MGR HIREDATE         SAL       COMM     DEPTNO
---------- ---------- --------- ---------- --------- ---------- ---------- ----------
      7369 SMITH      CLERK           7902 17-DEC-80        800                    20
      7499 ALLEN      SALESMAN        7698 20-FEB-81       1600        300         30
      7521 WARD       SALESMAN        7698 22-FEB-81       1250        500         30
      7566 JONES      MANAGER         7839 02-APR-81       2975                    20
      7654 MARTIN     SALESMAN        7698 28-SEP-81       1250       1400         30
      7698 BLAKE      MANAGER         7839 01-MAY-81       2850                    30
      7782 CLARK      MANAGER         7839 09-JUN-81       2450                    10
      7788 SCOTT      ANALYST         7566 19-APR-87       3000                    20
      7839 KING       PRESIDENT            17-NOV-81       5000                    10
      7844 TURNER     SALESMAN        7698 08-SEP-81       1500          0         30
      7876 ADAMS      CLERK           7788 23-MAY-87       1100                    20
      7900 JAMES      CLERK           7698 03-DEC-81        950                    30
      7902 FORD       ANALYST         7566 03-DEC-81       3000                    20
      7934 MILLER     CLERK           7782 23-JAN-82       1300                    10

14 rows selected.
```
Description of the table DEPT: 
```
SQL> desc dept;
```
```
 Name                                                              Null?    Type
 ----------------------------------------------------------------- -------- --------------------------------------------
 DEPTNO                                                            NOT NULL NUMBER(2)
 DNAME                                                                      VARCHAR2(14)
 LOC
Display DEPT table:
SQL> select * from dept;

    DEPTNO DNAME          LOC
---------- -------------- -------------
        10 ACCOUNTING     NEW YORK
        20 RESEARCH       DALLAS
        30 SALES          CHICAGO
        40 OPERATIONS     BOSTON
Display SALGRADE table: 
SQL> select * from salgrade;

     GRADE      LOSAL      HISAL
---------- ---------- ----------
         1        700       1200
         2       1201       1400
         3       1401       2000
         4       2001       3000
         5       3001       9999
```
Description of the table SALGRADE: 
```
SQL> desc salgrade;
```
```
 Name                                                              Null?    Type
 ----------------------------------------------------------------- -------- --------------------------------------------
 GRADE                                                                      NUMBER
 LOSAL                                                                      NUMBER
 HISAL
```
Description of the table BONUS: 
```
SQL> desc bonus;
 Name                                                              Null?    Type
 ----------------------------------------------------------------- -------- --------------------------------------------
 ENAME                                                                      VARCHAR2(10)
 JOB                                                                        VARCHAR2(9)
 SAL                                                                        NUMBER
 COMM                                                                       NUMBER
```
Experiment No. – 01
 Using the default table of Oracle given above. Write SQL queries for the following : 
(a) List the names and code of all employees. 
```
SQL> select ename,empno from emp;
```
```

ENAME           EMPNO
---------- ----------
SMITH            7369
ALLEN            7499
WARD             7521
JONES            7566
MARTIN           7654
BLAKE            7698
CLARK            7782
SCOTT            7788
KING             7839
TURNER           7844
ADAMS            7876
JAMES            7900
FORD             7902
MILLER           7934

14 rows selected.
```
(b) List the names, employee code and department code of all clerks. 
```
SQL> select ename,empno,deptno from emp where job='CLERK';
```
```
ENAME           EMPNO     DEPTNO
---------- ---------- ----------
SMITH            7369         20
ADAMS            7876         20
JAMES            7900         30
MILLER           7934         10
```
(c) List the names, employee code and salary of all managers. 
```
SQL> select ename,empno,sal from emp where job='MANAGER';
```
```
ENAME           EMPNO        SAL
---------- ---------- ----------
JONES            7566       2975
BLAKE            7698       2850
CLARK            7782       2450
```
(d) List the names, employee code and hiredate of all analysts. 
```
SQL> select ename,empno,hiredate from emp where job='ANALYST';
```
```

ENAME           EMPNO HIREDATE
---------- ---------- ---------
SCOTT            7788 19-APR-87
FORD             7902 03-DEC-81
```
(e) List the employees whose salary lies between 2000 and 3000.
```
SQL> select ename , sal from emp where sal between 2000 and 3000;
```
```
ENAME             SAL
---------- ----------
JONES            2975
BLAKE            2850
CLARK            2450
SCOTT            3000
FORD             3000
```
 (f) List the employees whose salary less than 1000.
 ```
SQL> select ename , sal from emp where sal <1000;
```
```

ENAME             SAL
---------- ----------
SMITH             800
JAMES             950
```

 (g) List the employees whose salary greater than 4000. 
```
SQL> select ename , sal from emp where sal >4000;
```
```
ENAME             SAL
---------- ----------
KING             5000
```
(h) List the employees whose salaries are 800, 1600 or 2450.
```
SQL> select ename,sal from emp where sal in (800,1600) or sal=2450;
```
```
ENAME             SAL
---------- ----------
SMITH             800
ALLEN            1600
CLARK            2450
```
 (i) List the names of all employees who are either clerks or salesman or analyst . 
```
SQL> select ename, job from emp where job in ('SALESMAN','CLERK','ANALYST');
```
```
ENAME      JOB
---------- ---------
SMITH      CLERK
ALLEN      SALESMAN
WARD       SALESMAN
MARTIN     SALESMAN
SCOTT      ANALYST
TURNER     SALESMAN
ADAMS      CLERK
JAMES      CLERK
FORD       ANALYST
MILLER     CLERK

10 rows selected.
```
(j) List the employee those who are not getting commission.
```
SQL> select ename from emp where comm is null;
```
```
ENAME
----------
SMITH
JONES
BLAKE
CLARK
SCOTT
KING
ADAMS
JAMES
FORD
MILLER

10 rows selected.
```
 (k) List the employee those who are getting commission.
```
SQL> select ename from emp where comm is not  null;
```
```
ENAME
----------
ALLEN
WARD
MARTIN
TURNER
```
(l) List the employee name starts with ‘F’.
```
SQL> select ename from emp where ename like 'F%';
```
```
ENAME
----------
FORD
```
Experiment No. – 02 Write SQL queries for the following. 
(a) List the names and job of all employees who have names exactly 5 characters in length.
```
SQL> select ename from emp where length(ename)=5;
```
```
ENAME
----------
SMITH
ALLEN
JONES
BLAKE
CLARK
SCOTT
ADAMS
JAMES

8 rows selected.
```
(b) List all employees whose names start with ‘G’ . 
```
SQL> select ename from emp where ename like 'G%';
```
```
no rows selected
```
(c) List all employees who name ends with ‘N’.
```
SQL> select ename from emp where ename like '%N';
```
```
ENAME
----------
ALLEN
MARTIN
```
(d) List the names and job of all employees who have names exactly 5 characters in length and ends with ‘S’.
```
SQL> select ename from emp where length(ename)=5 and ename like '%S';
```
```
ENAME
----------
JONES
ADAMS
JAMES
```
 (e) List all employees who have not joined between 1/1/81 and 31/12/81.
```
SQL> select ename from emp where hiredate between '01-JAN-81' and '31-DEC-81';
```
```
ENAME
----------
ALLEN
WARD
JONES
MARTIN
BLAKE
CLARK
KING
TURNER
JAMES
FORD

10 rows selected.
```

 (f) List all employees whose job does not start will “CL”. 
```
SQL> select ename,job from emp where job not like 'CL%';
```
```
ENAME      JOB
---------- ---------
ALLEN      SALESMAN
WARD       SALESMAN
JONES      MANAGER
MARTIN     SALESMAN
BLAKE      MANAGER
CLARK      MANAGER
SCOTT      ANALYST
KING       PRESIDENT
TURNER     SALESMAN
FORD       ANALYST
```
10 rows selected.
(g) List all managers who earn more than Rs. 4000/-. 
```
SQL> select ename,job from emp where job='MANAGER' and sal>4000;
```
```
no rows selected
```
(h) List all clerks and salesman who earn more than Rs. 1600/- .
```
SQL> select ename,job,sal from emp where job in ('SALESMAN','CLERK') and sal>1600;
```
```
no rows selected
```
(i) List the names and salaries of all employees who were joined as manager during 1981. 
```
SQL> select ename,sal,hiredate from emp where to_char(hiredate,'yy')=81 and job='MANAGER';
```
```
ENAME             SAL HIREDATE
---------- ---------- ---------
JONES            2975 02-APR-81
BLAKE            2850 01-MAY-81
CLARK            2450 09-JUN-81
```
Experiment No. – 03 For the EMP relation, frame the following queries using SQL. 
(a) Calculate the average salary of all employees.
```
SQL> select avg(sal) from emp;
```
```
  AVG(SAL)
----------
2073.21429
```
 (b) Calculate the average salary of all Managers. 
```
SQL> select avg(sal) from emp where job='MANAGER';
```
```
  AVG(SAL)
----------
2758.33333
```
(c) Calculate the total salary of all employees.
```
SQL> select sum(sal) from emp ;
```
```
  SUM(SAL)
----------
     29025
```
 (d) Calculate the total salary of all managers. 
 ```
SQL> select sum(sal) from emp  where job='MANAGER';
```
```
  SUM(SAL)
----------
      8275
```
(e) Find the minimum salaries earned by the employees. 
```
SQL> select min(sal) from emp ;
```
```
  MIN(SAL)
----------
       800
```
(f) Find the maximum salaries earned by the employees. 
```
SQL> select max(sal) from emp ;
```
```
  MAX(SAL)
----------
      5000
```
(g) Find the minimum salaries earned by a clerks. 
```
SQL> select min(sal) from emp where job='CLERK';
```
```
  MIN(SAL)
----------
       800
```
(h) Find the maximum salaries earned by a salesman. 
```
SQL> select max(sal) from emp where job='SALESMAN';
```
```
  MAX(SAL)
----------
      1600
```
(i) Find the minimum and maximum and average salaries earned by a employees. 
```
SQL> select min(sal),max(Sal),avg(sal) from emp;
```
```
  MIN(SAL)   MAX(SAL)   AVG(SAL)
---------- ---------- ----------
       800       5000 2073.21429
```
(j) Find the minimum and maximum and average salaries earned by a clerks. 
```
SQL> select min(sal),max(Sal),avg(sal) from emp where job='CLERK';
```
```
  MIN(SAL)   MAX(SAL)   AVG(SAL)
---------- ---------- ----------
       800       1300     1037.5
```
(k) List the total number of employees and the average salaries of the different departments.
```
SQL> select count(empno),avg(sal) from emp group by deptno;
```
```
COUNT(EMPNO)   AVG(SAL)
------------ ----------
           6 1566.66667
           5       2175
           3 2916.66667
```
 (l) Calculate total number of employees. 
```
SQL> select count(empno) from  emp;
```
```
COUNT(EMPNO)
------------
          14
```
(m) Calculate total number of managers. 
```
SQL> select count(empno) from  emp  where job='MANAGER';
```
```
COUNT(EMPNO)
------------
           3
```
(n) Calculate the number of employees who are not getting any commission.
```
SQL> select count(empno) from  emp  where comm is NULL;
```
```
COUNT(EMPNO)
------------
          10
```
 (o) Calculate the number of employees who are getting any commission.
```
SQL> select count(empno) from  emp  where comm is not NULL;
```
```
COUNT(EMPNO)
------------
           4
```
 (p) List the details of all managers in ascending order of joining dates. 
```
SQL> select ename,job, hiredate from emp  where job='MANAGER' order by hiredate asc;
```
```
ENAME      JOB       HIREDATE
---------- --------- ---------
JONES      MANAGER   02-APR-81
BLAKE      MANAGER   01-MAY-81
CLARK      MANAGER   09-JUN-81
```
(q) List the average salaries for each different job. 
```
SQL> select avg(sal), job from  emp  group by job;
```
```
  AVG(SAL) JOB
---------- ---------
    1037.5 CLERK
      1400 SALESMAN
      5000 PRESIDENT
2758.33333 MANAGER
      3000 ANALYST
```
(r) Display the average salary for each different job.
```
SQL> select avg(sal), job from  emp  group by job;
```
```
  AVG(SAL) JOB
---------- ---------
    1037.5 CLERK
      1400 SALESMAN
      5000 PRESIDENT
2758.33333 MANAGER
      3000 ANALYST
  ```
 (s) Display the minimum, maximum, and average salaries for each job group.
```
SQL> select min(sal),max(Sal),avg(sal), job from  emp  group by job;
```
```
  MIN(SAL)   MAX(SAL)   AVG(SAL) JOB
---------- ---------- ---------- ---------
       800       1300     1037.5 CLERK
      1250       1600       1400 SALESMAN
      5000       5000       5000 PRESIDENT
      2450       2975 2758.33333 MANAGER
      3000       3000       3000 ANALYST
```
 (t) Find all departments which have less than 3 employees. 
```
SQL> select count(empno) , deptno from emp group by deptno having count(*)<3;
```
```
no rows selected
```
(u) List the details of the employees in ascending order of department number, and within each department, in descending order of salary.
```
SQL> select ename,sal, deptno from emp order by deptno asc, sal desc;
```
```
ENAME             SAL     DEPTNO
---------- ---------- ----------
KING             5000         10
CLARK            2450         10
MILLER           1300         10
SCOTT            3000         20
FORD             3000         20
JONES            2975         20
ADAMS            1100         20
SMITH             800         20
BLAKE            2850         30
ALLEN            1600         30
TURNER           1500         30
MARTIN           1250         30
WARD             1250         30
JAMES             950         30

14 rows selected.
```
 (v) Display the name, deptno and annual salary of each employee in order salary and deptno. 

```
SQL> select empno, ename ,sal*12 from emp order by sal, deptno;
```
```
     EMPNO ENAME          SAL*12
---------- ---------- ----------
      7369 SMITH            9600
      7900 JAMES           11400
      7876 ADAMS           13200
      7521 WARD            15000
      7654 MARTIN          15000
      7934 MILLER          15600
      7844 TURNER          18000
      7499 ALLEN           19200
      7782 CLARK           29400
      7698 BLAKE           34200
      7566 JONES           35700
      7788 SCOTT           36000
      7902 FORD            36000
      7839 KING            60000

14 rows selected.
```
(w) Display the name of employee who earns maximum salary.
```
SQL> select ename, sal from emp where sal=(select max(sal) from emp);
```
```
ENAME             SAL
---------- ----------
KING             5000
```
 (x) Display the name of employee who earns minimum salary.
```
SQL> select ename, sal from emp where sal=(select min(sal) from emp);
```
```
ENAME             SAL
---------- ----------
SMITH             800
```
 (y) Display the name of employee who earns maximum salary whose job is salesman.
```
SQL> select ename, sal from emp where sal=(select max(sal) from emp where job='SALESMAN');
```
```
ENAME             SAL
---------- ----------
ALLEN            1600
```
 (z) Display the name of employee who earns minimum salary whose job is clerk. 
 ```
SQL> select ename,job, sal from emp where sal=(select min(sal) from emp where job='CLERK');
```
```
ENAME      JOB              SAL
---------- --------- ----------
SMITH      CLERK            800
```
(aa) Display the department number whose average salary is maximum. 
```
SQL> SELECT deptno, AVG(sal) AS avg_salary
```
```
FROM emp
GROUP BY deptno
ORDER BY avg_salary DESC
LIMIT 1;
```
```
SQL> select dept,w from (select deptno as dept, avg(sal) as w from emp group by deptno) where w=(select max(w) from (select deptno as dept, avg(sal) as w from emp group by deptno));
```
```
      DEPT          W
---------- ----------
        10 2916.66667
```
Experiment No. – 04 Using the default table of Oracle, such as Emp and Dept. Write SQL queries for the following ? 

(a) List all employee names, dept name and the city, in department name order.
```
SQL> select ename, dname, loc as city from emp,dept where emp.deptno=dept.deptno;
```
```
ENAME      DNAME          CITY
---------- -------------- -------------
SMITH      RESEARCH       DALLAS
ALLEN      SALES          CHICAGO
WARD       SALES          CHICAGO
JONES      RESEARCH       DALLAS
MARTIN     SALES          CHICAGO
BLAKE      SALES          CHICAGO
CLARK      ACCOUNTING     NEW YORK
SCOTT      RESEARCH       DALLAS
KING       ACCOUNTING     NEW YORK
TURNER     SALES          CHICAGO
ADAMS      RESEARCH       DALLAS
JAMES      SALES          CHICAGO
FORD       RESEARCH       DALLAS
MILLER     ACCOUNTING     NEW YORK

14 rows selected.
```
 (b) List all employee name, dept number, dept name and salary. 
```
SQL> select ename,dept.deptno, dname, sal from emp,dept where emp.deptno=dept.deptno;
```
```
ENAME          DEPTNO DNAME                 SAL
---------- ---------- -------------- ----------
SMITH              20 RESEARCH              800
ALLEN              30 SALES                1600
WARD               30 SALES                1250
JONES              20 RESEARCH             2975
MARTIN             30 SALES                1250
BLAKE              30 SALES                2850
CLARK              10 ACCOUNTING           2450
SCOTT              20 RESEARCH             3000
KING               10 ACCOUNTING           5000
TURNER             30 SALES                1500
ADAMS              20 RESEARCH             1100
JAMES              30 SALES                 950
FORD               20 RESEARCH             3000
MILLER             10 ACCOUNTING           1300

14 rows selected.
```
(c) List all employees working in Dallas in descending order of salary. 
```
SQL> select ename,loc as city,sal from emp,dept where emp.deptno=dept.deptno and loc='DALLAS' order by sal desc;
```
```
ENAME      CITY                 SAL
---------- ------------- ----------
SCOTT      DALLAS              3000
FORD       DALLAS              3000
JONES      DALLAS              2975
ADAMS      DALLAS              1100
SMITH      DALLAS               800
```
(d) List all employee’s name, job, salary and department name for everyone in the company except clerks. Sort the report with respect to job and salary. 
```
SQL> select ename,job,sal,dname from emp,dept where emp.deptno=dept.deptno and job !='CLERK' order by job, sal;
```
```
ENAME      JOB              SAL DNAME
---------- --------- ---------- --------------
SCOTT      ANALYST         3000 RESEARCH
FORD       ANALYST         3000 RESEARCH
CLARK      MANAGER         2450 ACCOUNTING
BLAKE      MANAGER         2850 SALES
JONES      MANAGER         2975 RESEARCH
KING       PRESIDENT       5000 ACCOUNTING
WARD       SALESMAN        1250 SALES
MARTIN     SALESMAN        1250 SALES
TURNER     SALESMAN        1500 SALES
ALLEN      SALESMAN        1600 SALES

10 rows selected.
```
(e) List all employee names who work in the same city as an employee named ‘FORD’.
```
SQL> select ename, loc from emp,dept where emp.deptno=dept.deptno and loc=(select loc from emp,dept where emp.deptno=dept.deptno and ename='FORD');
```
```
ENAME      LOC
---------- -------------
SMITH      DALLAS
JONES      DALLAS
SCOTT      DALLAS
ADAMS      DALLAS
FORD       DALLAS
```
 (f) Display the name of the dept that has no employee. 
 ```
SQL> select dname from dept where deptno=(select deptno from dept minus select deptno from emp);
```
```
DNAME
--------------
OPERATIONS
```
Experiment No. – 05
 a) List the employees belonging to the department 20. 
```
SQL> select ename, deptno from emp where deptno=20;
```
```
ENAME          DEPTNO
---------- ----------
SMITH              20
JONES              20
SCOTT              20
ADAMS              20
FORD               20
```
b) List the name and salary of the employees whose salary is more than 1000. 
```
SQL> select ename,sal from emp where sal>1000;
```
```
ENAME             SAL
---------- ----------
ALLEN            1600
WARD             1250
JONES            2975
MARTIN           1250
BLAKE            2850
CLARK            2450
SCOTT            3000
KING             5000
TURNER           1500
ADAMS            1100
FORD             3000
MILLER           1300

12 rows selected.
```
c) List the employee number and the name of the manager. 
```
SQL> select empno,ename,job from emp where job='MANAGER';
```
```
     EMPNO ENAME      JOB
---------- ---------- ---------
      7566 JONES      MANAGER
      7698 BLAKE      MANAGER
      7782 CLARK      MANAGER
```
d) List the names of the clerks working in the department 20. 
```
SQL> select ename,job, deptno from emp where deptno=20 and job='CLERK';
```
```
ENAME      JOB           DEPTNO
---------- --------- ----------
SMITH      CLERK             20
ADAMS      CLERK             20
```
e) List the name of the analysts and salesman.
```
SQL> select ename,job from emp where job in ('ANALYST','SALESMAN');
```
```
ENAME      JOB
---------- ---------
ALLEN      SALESMAN
WARD       SALESMAN
MARTIN     SALESMAN
SCOTT      ANALYST
TURNER     SALESMAN
FORD       ANALYST

6 rows selected.
```
 f) List the details of the employees who have joined before the end of September 81. 
```
SQL> select ename,hiredate from emp where hiredate <'1-SEP-81';
```
```
ENAME      HIREDATE
---------- ---------
SMITH      17-DEC-80
ALLEN      20-FEB-81
WARD       22-FEB-81
JONES      02-APR-81
BLAKE      01-MAY-81
CLARK      09-JUN-81

6 rows selected.
```
g) List the names of the employees who are not managers. 
```
SQL> select ename,job from emp where job!='MANAGER';
```
```
ENAME      JOB
---------- ---------
SMITH      CLERK
ALLEN      SALESMAN
WARD       SALESMAN
MARTIN     SALESMAN
SCOTT      ANALYST
KING       PRESIDENT
TURNER     SALESMAN
ADAMS      CLERK
JAMES      CLERK
FORD       ANALYST
MILLER     CLERK

11 rows selected.
```
h) List the name of the employees whose employee numbers 7369,7521,7839,7934,7788. 
```
SQL> select ename,empno from emp where empno in (7369,7521,7839,7934,7788);
```
```
ENAME           EMPNO
---------- ----------
SMITH            7369
WARD             7521
SCOTT            7788
KING             7839
MILLER           7934
```
i) List the employee details not belonging to the department 10,30 and 40.
```
SQL> select ename,deptno from emp where deptno not in (10,30,40);
```
```
ENAME          DEPTNO
---------- ----------
SMITH              20
JONES              20
SCOTT              20
ADAMS              20
FORD               20
```
 j) List the employee names who have joined before 30th June’81 and after December ’81. 
 ```
SQL> select ename,hiredate from emp where hiredate between  '30-JUN-81' and '31-DEC-81';
```
```
ENAME      HIREDATE
---------- ---------
MARTIN     28-SEP-81
KING       17-NOV-81
TURNER     08-SEP-81
JAMES      03-DEC-81
FORD       03-DEC-81
```
k) List the name of the employee and designation (job) of the employee who does not report to anybody (who doesn’t have manager).
```
SQL> select ename,job, mgr from emp where mgr is NULL;
```
```
ENAME      JOB              MGR
---------- --------- ----------
KING       PRESIDENT
```
 l) List the different jobs (designations) available in the emp table.
```
SQL> select job from emp group by job;
```
```
JOB
---------
CLERK
SALESMAN
PRESIDENT
MANAGER
ANALYST
```
 m) List the employees not assigned to any department. 
```
SQL> select ename ,deptno from emp where deptno not in (select deptno from emp);
```
```
no rows selected
```
n) List the details of the employees whose salary is greater than 2000 and not eligible for commission. 
```
SQL> select ename,sal, comm from emp where sal>2000 and comm is NULL;
```
```
ENAME             SAL       COMM
---------- ---------- ----------
JONES            2975
BLAKE            2850
CLARK            2450
SCOTT            3000
KING             5000
FORD             3000

6 rows selected.
```
o) List the employee names having ‘I’ as the second character.
```
SQL> select ename from emp where ename like '_I%';
```
```
ENAME
----------
KING
MILLER
 p) List the name, salary and PF amount of all the employees (PF is calculated as 10% of salary).
SQL> select ename,sal, sal*(10/100) as pf from emp;
ENAME             SAL         PF
---------- ---------- ----------
SMITH             800         80
ALLEN            1600        160
WARD             1250        125
JONES            2975      297.5
MARTIN           1250        125
BLAKE            2850        285
CLARK            2450        245
SCOTT            3000        300
KING             5000        500
TURNER           1500        150
ADAMS            1100        110
JAMES             950         95
FORD             3000        300
MILLER           1300        130

14 rows selected.
```
 q) List the employee number, name and salary in ascending order of salary.
 ```
SQL> select empno,ename, sal from emp order by sal asc;
```
```
     EMPNO ENAME             SAL
---------- ---------- ----------
      7369 SMITH             800
      7900 JAMES             950
      7876 ADAMS            1100
      7521 WARD             1250
      7654 MARTIN           1250
      7934 MILLER           1300
      7844 TURNER           1500
      7499 ALLEN            1600
      7782 CLARK            2450
      7698 BLAKE            2850
      7566 JONES            2975
      7788 SCOTT            3000
      7902 FORD             3000
      7839 KING             5000

14 rows selected.
```
 r) Lists the employee name and hiredate in descending order of hiredate. 
 ```
SQL> select ename, hiredate from emp order by hiredate desc;
```
```
ENAME      HIREDATE
---------- ---------
ADAMS      23-MAY-87
SCOTT      19-APR-87
MILLER     23-JAN-82
FORD       03-DEC-81
JAMES      03-DEC-81
KING       17-NOV-81
MARTIN     28-SEP-81
TURNER     08-SEP-81
CLARK      09-JUN-81
BLAKE      01-MAY-81
JONES      02-APR-81
WARD       22-FEB-81
ALLEN      20-FEB-81
SMITH      17-DEC-80

14 rows selected.
```
s) List the employee name, salary, PF, HRA, DA and gross salary;order the result in ascending order of gross.HRA is 50% of salary and DA is 30% of salary. 
```
SQL> select ename,sal,sal*0.1 as pf,sal*0.5 as hra, sal*0.3 as da, sal+(sal*0.9) as gross from emp order by (sal+pf+hra+da+gross) asc;
```
```
ENAME             SAL         PF        HRA         DA      GROSS
---------- ---------- ---------- ---------- ---------- ----------
SMITH             800         80        400        240       1520
JAMES             950         95        475        285       1805
ADAMS            1100        110        550        330       2090
WARD             1250        125        625        375       2375
MARTIN           1250        125        625        375       2375
MILLER           1300        130        650        390       2470
TURNER           1500        150        750        450       2850
ALLEN            1600        160        800        480       3040
CLARK            2450        245       1225        735       4655
BLAKE            2850        285       1425        855       5415
JONES            2975      297.5     1487.5      892.5     5652.5
SCOTT            3000        300       1500        900       5700
FORD             3000        300       1500        900       5700
KING             5000        500       2500       1500       9500

14 rows selected.
```
t) List the department number and the total salary payable in each department. 
```
SQL> select deptno,sum(sal) from emp group by deptno;
```
```
    DEPTNO   SUM(SAL)
---------- ----------
        30       9400
        20      10875
        10       8750
```
List the jobs and number of employees in each job.The result should be in descending order of the number of employees.
```
SQL> select deptno,count(empno) as total_emp from emp group by deptno order by (total_emp);
```
```
    DEPTNO  TOTAL_EMP
---------- ----------
        10          3
        20          5
        30          6
```
 u) List the total salary, maximum, minimum and average salary of the employee’s job wise. 
 ```
SQL> select  sum(sal), min(sal),max(sal) ,avg(sal), job from emp group by job;
```
```
  SUM(SAL)   MIN(SAL)   MAX(SAL)   AVG(SAL) JOB
---------- ---------- ---------- ---------- ---------
      4150        800       1300     1037.5 CLERK
      5600       1250       1600       1400 SALESMAN
      5000       5000       5000       5000 PRESIDENT
      8275       2450       2975 2758.33333 MANAGER
      6000       3000       3000       3000 ANALYST

```
v) List the average salary from each job excluding manager. 
```
SQL> select  job,avg(sal) from emp where job not in('MANAGER') group by job ;
```
```
JOB         AVG(SAL)
--------- ----------
CLERK         1037.5
SALESMAN        1400
PRESIDENT       5000
ANALYST         3000
```
w) List the average monthly salary for each job type within department.
```
SQL> select deptno, job,avg(sal) from emp group by deptno,job order by deptno;
```
```
    DEPTNO JOB         AVG(SAL)
---------- --------- ----------
        10 CLERK           1300
        10 MANAGER         2450
        10 PRESIDENT       5000
        20 ANALYST         3000
        20 CLERK            950
        20 MANAGER         2975
        30 CLERK            950
        30 MANAGER         2850
        30 SALESMAN        1400

9 rows selected.
```
 x) List average salary for all departments employing more than five people.
```
SQL> select deptno, avg(sal) from emp  wherer group by deptno having count(empno)>5;
```
```
    DEPTNO   AVG(SAL)
---------- ----------
        30 1566.66667
```
 y) List job of all the employees where salary will be equal to maximum salary.
```
SQL> select ename , sal from emp where sal=(select max(sal) from emp);
```
```
ENAME             SAL
---------- ----------
KING             5000
```
 z) List the total salary, maximum and minimum salary and the average salary of employees job wise for department number 20 and display only those rows having average salary greater than 1000. 
 ```
SQL> select min(sal), max(sal), avg(sal) from emp where deptno=20 group by job  having avg(sal)>1000;
```
```
  MIN(SAL)   MAX(SAL)   AVG(SAL)
---------- ---------- ----------
      2975       2975       2975
      3000       3000       3000
```
Experiment No. – 06 
a) List the employees earns more than any employee in CHICAGO.
```
SQL> select ename from emp where sal=(select max(max_sal) from (select  sal as max_sal from emp,dept where emp.deptno=dept.deptno and loc='CHICAGO') );
```
```
ENAME
----------
BLAKE
```
 b) List the name of the employee who works in the same department as SMITH.
```
SQL> select ename,dname from emp,dept where emp.deptno=dept.deptno and dname=(select dname from emp,dept where dept.deptno=emp.deptno and ename='SMITH');
```
```
ENAME      DNAME
---------- --------------
JONES      RESEARCH
FORD       RESEARCH
ADAMS      RESEARCH
SMITH      RESEARCH
SCOTT      RESEARCH
```
c) List the name, employee number ,their manager name and manager number. 
```
SQL> select e1.ename, e1.empno , e2.ename as manager, e1.mgr as mgr_no from emp e1, emp e2 where e1.mgr=e2.empno;
```
```
ENAME           EMPNO MANAGER        MGR_NO
---------- ---------- ---------- ----------
FORD             7902 JONES            7566
SCOTT            7788 JONES            7566
TURNER           7844 BLAKE            7698
ALLEN            7499 BLAKE            7698
WARD             7521 BLAKE            7698
JAMES            7900 BLAKE            7698
MARTIN           7654 BLAKE            7698
MILLER           7934 CLARK            7782
ADAMS            7876 SCOTT            7788
BLAKE            7698 KING             7839
JONES            7566 KING             7839
CLARK            7782 KING             7839
SMITH            7369 FORD             7902

13 rows selected.
```
d) List the name of the employee job is same as ‘CLARK’. 
```
SQL> select ename, job from emp where job=(select job from emp where ename='CLARK');
```
```
ENAME      JOB
---------- ---------
JONES      MANAGER
BLAKE      MANAGER
CLARK      MANAGER
```
e) List the name of employee whose salary is more than ‘TURNER’. 
```
SQL> select ename, sal from emp where sal>(select sal from emp where ename='TURNER');
```
```
ENAME             SAL
---------- ----------
ALLEN            1600
JONES            2975
BLAKE            2850
CLARK            2450
SCOTT            3000
KING             5000
FORD             3000

7 rows selected.
```
f) List the name of employee who joined after ‘ALLEN’. 
```
SQL> select ename, hiredate from emp where hiredate>(select hiredate from emp where ename='ALLEN');
```
```
ENAME      HIREDATE
---------- ---------
WARD       22-FEB-81
JONES      02-APR-81
MARTIN     28-SEP-81
BLAKE      01-MAY-81
CLARK      09-JUN-81
SCOTT      19-APR-87
KING       17-NOV-81
TURNER     08-SEP-81
ADAMS      23-MAY-87
JAMES      03-DEC-81
FORD       03-DEC-81
MILLER     23-JAN-82

12 rows selected.
```
g) Display the name of the department whose job is ‘SALESMAN’. 
```
SQL> select ename,deptno from emp where job='SALESMAN';
```
```
ENAME          DEPTNO
---------- ----------
ALLEN              30
WARD               30
MARTIN             30
TURNER             30
```
h) Display the name of the department in which ‘FORD’ works. 
```
SQL> select ename,dname from emp,dept where emp.deptno=dept.deptno and dname=(select dname from emp,dept where dept.deptno=emp.deptno and ename='FORD');
```
```
ENAME      DNAME
---------- --------------
JONES      RESEARCH
FORD       RESEARCH
ADAMS      RESEARCH
SMITH      RESEARCH
SCOTT      RESEARCH
```
i) Display the name of the department whose salary is maximum. 
```
SQL> select w from (select max(sal) as w from emp group by deptno) where w=(select max(w) from (select max(sal) as w from emp group by deptno));
```
```
SQL> select w,dept from (select max(sal) as w , deptno as dept from emp group by deptno) where w=(select max(w) from (select max(sal) as w from emp group by deptno));
```
```
         W       DEPT
---------- ----------
      5000         10
```
j) Display the name of the city(location) in which ‘SMITH’ works. 
```
SQL> select ename, loc as city from emp,dept where dept.deptno=emp.deptno and ename='SMITH';
```
```
ENAME      CITY
---------- -------------
SMITH      DALLAS
```
k) Display the name of the city in which the manager works. 
```
SQL> select ename, job,loc as city from emp,dept where dept.deptno=emp.deptno and job='MANAGER';
```
```
ENAME      JOB       CITY
---------- --------- -------------
CLARK      MANAGER   NEW YORK
JONES      MANAGER   DALLAS
BLAKE      MANAGER   CHICAGO
```
l) Display the grade of the employee named ‘MARTIN’. 
```
SQL> select ename, grade from emp,salgrade where (sal>=LOSAL and sal<=HISAL) and ename='MARTIN';
```
```
ENAME           GRADE
---------- ----------
MARTIN              2
```
m) List the employees earns more than every employee in ‘DALLAS’. 
```
SQL>  select ename,sal from emp where sal=(select max(max_sal) from (select  sal as max_sal from emp,dept where emp.deptno=dept.deptno and loc='DALLAS') );
```
```
ENAME             SAL
---------- ----------
SCOTT            3000
FORD             3000
```
n) Display the name of the department which has no employee. 
```
SQL> select dname from dept where deptno=(select deptno from dept minus select
  2  deptno from emp);
```
```
DNAME
--------------
OPERATIONS
```
o) List name, employee number and the name, employee number of their managers’ manager .
```
SQL> select e1.empno, e1.ename, e3.empno as mgrs_mgr_no, e3.ename as mgrs_mgr_name
  2  from emp e1, emp e2, emp e3 where e1.mgr=e2.empno and e2.mgr=e3.empno;
```
```
     EMPNO ENAME      MGRS_MGR_NO MGRS_MGR_N
---------- ---------- ----------- ----------
      7369 SMITH             7566 JONES
      7499 ALLEN             7839 KING
      7521 WARD              7839 KING
      7654 MARTIN            7839 KING
      7788 SCOTT             7839 KING
      7844 TURNER            7839 KING
      7876 ADAMS             7566 JONES
      7900 JAMES             7839 KING
      7902 FORD              7839 KING
      7934 MILLER            7839 KING

10 rows selected.
```
 p) list the name of the employee who joined in the same year of ‘ADAMS’. 
```
SQL> select ename, hiredate from emp where to_char(hiredate,'yy')= (select
  2  to_char(hiredate,'yy') from emp where ename ='ADAMS');
```
```
ENAME      HIREDATE
---------- ---------
SCOTT      19-APR-87
ADAMS      23-MAY-87
```
q) list the name of the employee who joined in the same month of ‘BLAKE’. 
```
SQL> select ename, hiredate from emp where to_char(hiredate,'mm')= (select
  2  to_char(hiredate,'mm') from emp where ename ='BLAKE');
```
```
ENAME      HIREDATE
---------- ---------
BLAKE      01-MAY-81
ADAMS      23-MAY-87
```
r) list the name of the employee who joined in the same date of ‘ADAMS’. 
```
SQL> select ename, hiredate from emp where to_char(hiredate,'dd')= (select
  2  to_char(hiredate,'dd') from emp where ename ='ADAMS');
```
```
ENAME      HIREDATE
---------- ---------
ADAMS      23-MAY-87
MILLER     23-JAN-82
```
s) List the name of the department who gets commission. 
```
SQL> select dname from dept where deptno in (select deptno from emp where comm is
  2  not NULL);
```
```
DNAME
--------------
SALES
```
