# boooo

--1. Write query to get employeenames with salaries >= 5000 and <= 10000

select first_name+' '+last_name as employeesnames, salary from tblemployee where salary betqwwn 5000 and 10000


--2. write query to get the no. of employee for each department in the descending order.

select count(employee_id) as no_of_employees ,department from tblemployee group by department order by no_of_employees desc


--3. Write query to get the details of the employee who are also managers.

select first_name+' '+last_name as employees_names, employee_id,salary,joining_date,department,employee_title from tblemployee e inner join tbltitle t on e.employee_id=t.employee_ref_id where employee_title='Manager';


--4. Write Query to get to fetch duplicate records having matching data in title table

Select employee_title, affected_from from tblTitle group by employee_title,affected_from having count(*)>1


--5. Write query to show only odd rows from employee table.

select * from tblemployee where (employee_id%2=1)


--6. Write query to show the top 2nd highest salary from employee table.

select max(salary) as second_highest_salary from tblemployee where salary not in (select Max(salary) from tblemployee)


--7. Write query to print the name of employee having the highest salary in each department.

select first_name+' '+last_name as employee_names, salary, department from tblemployee where salary in (select max(salary) from tblemployee group by department)
