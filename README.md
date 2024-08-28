In this project, first major task is to do a research project about people whom the company employed during the 1980s and 1990s. All that remains of the employee database from that period are six CSV files.

DATA ENGINEERING

we first had to create six different tables from CSV files in that specific order: 
  titles, departments, employees, salaries, dept_emp, and dept_manager. 
  We had to define different data types first to create each table: 
    VARCHAR was being used for letters, numbers and symbols. The number in the parenthesis defines the variable length.
    INT was being used for integers, full numbers with no decimals 
    NOT NULL values means that a column must always have a value and can never be left empty. 
    PRIMARY KEYS are unique keys, which means they cannot be repeated. In this case we used emp_no as a primary key, which means that each employee has a unique employee number. 
    FOREIGN KEYS were used to link tables together, here every emp_title_id in the employees table corresponds to a valid title_id in the titles table.

  After creating these tables, we imported the data as CSV file and made sure the data was imported correctly. 

  The first step would be found under EmployeeSQL folder, in the employee.sql file.

  DANA ANALYSIS

  In this part we had to answer a few questions. 

     -- List the employee number, last name, first name, sex, and salary of each employee.


[q1 - challenge9.pdf](https://github.com/user-attachments/files/16790062/q1.-.challenge9.pdf)





-- List the first name, last name, and hire date for the employees who were hired in 1986.

SELECT first_name, last_name, hire_date
FROM employees
WHERE hire_date BETWEEN '1986-01-01' AND '1986-12-31';

--List the manager of each department along with their department number, department name, employee number, last name, and first name.

SELECT dm.dept_no, d.dept_name, dm.emp_no, e.last_name, e.first_name
FROM dept_manager as dm
JOIN departments d ON dm.dept_no = d.dept_no
JOIN employees e ON dm.emp_no = e.emp_no;

--List the department number for each employee along with that employee’s employee number, last name, first name, and department name.

SELECT de.dept_no, de.emp_no, e.last_name, e.first_name, d.dept_name
FROM dept_emp de
JOIN employees e ON de.emp_no = e.emp_no
JOIN departments d ON de.dept_no = d.dept_no;

--List first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B.

SELECT first_name, last_name, sex
FROM employees
WHERE first_name = 'Hercules' AND last_name LIKE 'B%';


--List each employee in the Sales department, including their employee number, last name, and first name.

SELECT e.emp_no, e.last_name, e.first_name
FROM dept_emp de
JOIN employees e ON de.emp_no = e.emp_no
JOIN departments d ON de.dept_no = d.dept_no
WHERE d.dept_name = 'Sales';

--List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name.

SELECT e.emp_no, e.last_name, e.first_name, d.dept_name
FROM dept_emp de
JOIN employees e ON de.emp_no = e.emp_no
JOIN departments d ON de.dept_no = d.dept_no
WHERE d.dept_name IN ('Sales', 'Development');

--List the frequency counts, in descending order, of all the employee last names (that is, how many employees share each last name).

SELECT last_name, COUNT(*) AS frequency
FROM employees
GROUP BY last_name
ORDER BY frequency DESC;

We can find this file in the EmployeeSQL folder, in the datanalysisq.sql file. 
