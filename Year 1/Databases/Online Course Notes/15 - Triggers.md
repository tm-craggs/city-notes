A trigger is a block of SQL that will define a certain action that should take place when a certain operation is performed on the database.

For example, you can tell MySQL to do something every time a row is deleted. Such as create a new row in another table. 

Trigger code must be executed from the command line. 

DELIMITER $
CREATE TRIGGER my_trigger 
BEFORE INSERT ON EMPLOYEE
FOR EACH ROW 
BEGIN
    INSERT INTO trigger_test (message_column) 
    VALUES ('added new employee');
END $

DELIMITER ;

**How it Works:**

- **Before**: MySQL expects each SQL statement to end with a semicolon (`;`).
- **After `DELIMITER $$`**: MySQL will interpret `$$` as the end of a statement. So, the semicolons inside the `BEGIN...END` block are treated as normal statement separators within the block, not as end-of-statement markers.
- **After**: The delimiter is reset back to the default semicolon (`;`).

This is useful for writing complex stored routines or triggers that contain multiple statements and use semicolons within their body.
