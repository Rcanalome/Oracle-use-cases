# Oracle-use-cases

SELECT * FROM CONTACTS;

SELECT * FROM OT.CUSTOMERS;

SELECT * FROM ORDERS;

SELECT * FROM EMPLOYEES;

SELECT * FROM ORDDER_ITEMS;

SELECT * FROM PRODUCTS;

SELECT * FROM PRODUCT_CATEGORIES;

SELECT * FROM INVENTORIES;

SELECT * FROM WAREHOUSE;

SELECT * FROM LOCATIONS;

SELECT * FROM COUNTRIES;

SELECT * FROM REGIONS;



--- DEPARTMENTWISE TOP 3RD SALARY
SELECT A.*
FROM
(SELECT EMPLOYEE_ID,FIRST_NAME,LAST_NAME,DEPARTMENT_ID,SALARY,
DENSE_RANK() OVER (PARTITION BY DEPARTMENT_ID ORDER BY SALARY DESC)AS "RNK"
FROM EMPLOYEES ) A 
WHERE RNK=3;

---------------------------------------------------------------------------------

select * from contacts;


create table sample_emp 
(emp_id number, emp_name varchar2(20));


insert into sample_emp values (1,'a');
insert into sample_emp values (2,'a');
insert into sample_emp values (1,'a');
insert into sample_emp values (3,'a');
insert into sample_emp values (3,'a');


select * from sample_emp;

select emp_ID, count(*)
from sample_emp
group by emp_ID
HAVING COUNT(*) > 1;

--------------------------------------------------------------------------------------------------------------------------

SELECT DISTINCT (COUNT(*)) FROM customers;

SELECT * FROM employees;

SELECT EMPLOYEE_ID, FIRST_NAME, LAST_NAME, JOB_TITLE,
ROW_NUMBER() OVER(PARTITION BY JOB_TITLE  ORDER BY EMPLOYEE_ID) AS RNK
FROM EMPLOYEES;

SELECT * 
FROM EMPLOYEES
ORDER BY FIRST_NAME; 
