# Assignment-5-MySQL
DDL Commands and Constraints

The below queries has been used for the assignment:

Create Database employee;
USE employee;

CREATE TABLE departments
(department_id INT PRIMARY KEY auto_increment,
department_name VARCHAR(100) not null);

CREATE TABLE location
(location_id INT primary key auto_increment,
location_name varchar(30) unique not null);

create table employees
(employee_id INT primary key auto_increment,
employee_name varchar(50) not null,
gender enum('M', 'F'),
age  int check( Age>=18),
hire_date date default (current_date),
designation varchar(100),
department_id int, foreign key(department_id) references departments(department_id),
location_id int, foreign key(location_id) references location(location_id),
salary decimal (10,2));

Alter table employees add email varchar (150);
alter table employees modify designation varchar (300);
alter table employees drop column age;
alter table employees rename column hire_date to date_of_joining;

rename table departments to departments_info;
rename table location to locations;

truncate table employees;
drop table employees;
drop database employee;
