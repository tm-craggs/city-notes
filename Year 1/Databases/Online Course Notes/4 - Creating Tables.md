Creating tables is always the first step when defining a database schema, comes before populating the database.  

Datatypes: 

INT - Whole Number 

DECIMAL - Takes 2 parameters, first is number of digits, second is digits after the decimal place 

VARCHAR - String 

BLOB - Binary Large Object (images or other files) 

DATE - YYYY - MM - DD 

TIMESTAMP - YYYY-MM-DD HH:MM:SS 

Creating Table Query 

CREATE TABLE Student ( 

student_id INT PRIMARY KEY, 

name VARCHAR(20), 

course VARCHAR(20) 

); 

Reserved words should go in capitals, this is convention 

Each command should end in a semi colon.  

Columns in the command should be separated by a column.  

DROP TABLE - deletes a table 

ALTER TABLE student ADD - adds another column DROP COLUMN - deletes a column