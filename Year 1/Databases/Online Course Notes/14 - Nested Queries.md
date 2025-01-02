Queries where multiple select statements are used. The results of one select statement inform the results of the next.

Example: Find names of all employees who have sold over 30,000 to a single client

SELECT employee.first_name, employee.last_name
FROM employee
WHERE employee.emp_id IN (
	SELECT works_with.emp_id
	FROM works_with
	WHERE works_with.total_sales > 3000
);

The works with tables stores an emp_id, a client_id and the amount of sales.

This query will tell you the first name and last name of the employees with over the amount of sales. Nesting is needed in this situation, as the works with table does not store employee names, only their ID. The names must be found from the ID in the employee table. 