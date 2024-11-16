# Employee Management System

This project is a database-based application designed to manage employee, department, title and salary information. It includes SQL queries to retrieve various pieces of information about employees, such as their department, name, and other details, by interacting with a relational database system.

# Project Overview:

The project is divided into three main components: Data Modeling, Data Engineering, and Data Analysis.
1.	Data Modeling:
This phase involves examining the provided CSV files to understand the structure and relationships between the data. An Entity Relationship Diagram (ERD) is created to visually represent the tables and their relationships. The QuickDBD tool was used to design the ERD.
2.	Data Engineering:
In this phase, we focus on transforming the ERD into a functional database schema. For each of the six CSV files, a corresponding table schema is created. The ERD schema is exported from QuickDBD and used to create the necessary tables in PostgreSQL.
3.	Data Analysis:
The final phase involves writing SQL queries to extract valuable insights from the data. These queries focus on retrieving information about employees, departments, and other relevant data stored in the database tables.

# Key Features:

1. Retrieving employee details along with their department information.
2. Counting how many employees share the same last name.
3. Filtering and listing employees based on department, last name etc.
4. Listing the manager of each department and along with their information from the respective department and employee tables.
5. Retrieve employee details in specific departments (e.g., "Sales" and "Development").
6. Join multiple tables to extract related information (e.g., employees, departments, salaries etc)
   
# Database Schema
The project uses a database with the following key tables:

1. employees: Contains employee details such as emp_no, first_name, last_name, hire_date etc.
2. departments: Contains department details such as dept_no and dept_name.
3. dept_emp: Links employees to their respective departments. Contains details such as emp_no, dept_no.
4. dept_manager: Lists the managersand their respective departments.
5. titles: Contains details such as title_id and title.
6. salaries: Contains details such as emp_no and salary.

# Sample Queries:

select * from departments;

select * from dept_emp;

select * from dept_manager;

select * from employees;

select * from salaries;

select * from titles;

-> List the employee number, last name, first name, sex, and salary of each employee: 
  
select e.emp_no, e.last_name, e.first_name, e.sex, s.salary 
from employees as e
inner join salaries as s
on e.emp_no = s.emp_no
order by e.emp_no;

