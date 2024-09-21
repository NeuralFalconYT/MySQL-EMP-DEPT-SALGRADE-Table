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
