Unions combine multiple select statements into one statement

Example: Find a list of employee and branch names

**Regular Way**

SELECT first_name
FROM employee;

SELECT branch_name
FROM branch;

These statements will both return separate lists of all the employees or all the branches

**With Unions**

SELECT first_name
FROM employee
UNION
SELECT branch_name
FROM branch;

This will return one big list, with the first name column and the branch column combined into one. 

**Union rules**
- You must have the same amount of columns in each select statement in the union
- Must have a similar data type

Example: Find a list of all money spent or earned by the company 

SELECT salary
FROM employee
UNION
SELECT total_sales
FROM works_with;