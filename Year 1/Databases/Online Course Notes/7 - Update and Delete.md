Example: Want to change Biology to Bio in a student table

UPDATE student (specify student table)
SET course = 'Bio' (specify we want to change the course column )
WHERE course = 'Biology'; (only change this in table entries with Biology)

Other comparison ops
- = (equals)
- <> (not equals)
- > (greater than)
- < (less than)
- >= (greater than or equal)
- <= (less than or equal)

Make sure to place the semi colon at the end of the statement

OR can also be used in addition to the WHERE statement
If there is no WHERE statement, update will affect every entry

**Deletion**

DELETE FROM STUDENT; (would delete all rows from table)

DELETE FROM student
WHERE student_id = 5; (will delete entry of student ID 5)