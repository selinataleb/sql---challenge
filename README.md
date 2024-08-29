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

  1) List the employee number, last name, first name, sex, and salary of each employee.


[q1 - challenge9.pdf](https://github.com/user-attachments/files/16790062/q1.-.challenge9.pdf)



2) List the first name, last name, and hire date for the employees who were hired in 1986.

[q2- challenge9.pdf](https://github.com/user-attachments/files/16790075/q2-.challenge9.pdf)


3) List the manager of each department along with their department number, department name, employee number, last name, and first name.

[q3 - challenge9.pdf](https://github.com/user-attachments/files/16790103/q3.-.challenge9.pdf)



4) List the department number for each employee along with that employee’s employee number, last name, first name, and department name.
   
<img width="764" alt="q4 - challenge9" src="https://github.com/user-attachments/assets/60de2191-6ad6-4456-b117-72e08b54f71c">


5) List first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B.
<img width="487" alt="q5 - challenge9" src="https://github.com/user-attachments/assets/210d5268-cb5d-4624-8584-47e0682a558e">


6) List each employee in the Sales department, including their employee number, last name, and first name.
<img width="477" alt="q6 - challenge9" src="https://github.com/user-attachments/assets/94c6bbea-6734-4386-8fce-98d9e36f8c95">



7) List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name.

<img width="598" alt="q7- challenge9" src="https://github.com/user-attachments/assets/099987c7-1547-4aea-830e-0219caa76cb0">


8) List the frequency counts, in descending order, of all the employee last names (that is, how many employees share each last name).
9) 
<img width="317" alt="q8 - challenge9" src="https://github.com/user-attachments/assets/9bae1ff5-266e-4603-883f-1fb5aacb40f9">


We can find this file in the EmployeeSQL folder, in the datanalysisq.sql file. 

DATA MODELING 

![QuickDBD-export](https://github.com/user-attachments/assets/7013a13c-3e2c-43a9-bf18-256fad93c6ab)

this diagram visually represents the relationship we have between tables. The <- signal means many to one relationships. 
The key logo represents our PRIMARY KEYS.
The arrows going from variable to another represent the link between the tables which means our FOREIGN KEYS. 


