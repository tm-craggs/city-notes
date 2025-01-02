
You can use SELECT to select which column you want to get data from

For example:

SELECT *
FROM student; 

This would return each entry in its entirety. However,

SELECT name
FROM student;

This would only return the names of all students. 

You can also prepend these with the name of the table
For example:

SELECT student.name, student.major
FROM student;

This can help with making queries clearer in large databases with multiple tables. 

Another command is ORDER BY

SELECT student.name, student.major
FROM student
ORDER BY name;

This will return the names and majors, in alphabetical order by name. 
DESC can make the list in reverse order. 

ORDER BY can take numerous arguments. ORDER BY course, student_id will sort by course first, then any with the same course will then be order by student_id

LIMIT - Sets a limit on how many rows can be returned
IN - You can pass in a list of values

WHERE name IN ('Tom', 'Lee', 'Luca') will return if name is in this list

