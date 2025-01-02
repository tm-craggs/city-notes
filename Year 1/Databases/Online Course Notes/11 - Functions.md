Functions are a block of code which you can call
They can be useful for getting information about tables, such as counting numbers or calculating averages.

COUNT - A function which returns the number of times something occurs

SELECT COUNT(emp_id)
FROM employee; 

This will count the number of employees in the table, as emp_id is the primary key

AVG - A function which calculates the average
SUM - Adds up all entries

SELECT SUM(salary)
FROM employee; 
Will give you the sum of all salaries 

SELECT AVG(salary)
FROM employee
WHERE sex = 'M'
Will calculate the average male salary

GROUP BY - Sorts your returns into groups. Aggregation. For example:

SELECT COUNT(sex), sex
FROM employee
GROUP BY sex;

Will return:
COUNT(sex)  Sex
7                     M
8                     F


