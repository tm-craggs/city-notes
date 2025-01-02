When creating a database with multiple tables, remember that tables that contain foreign keys cannot be declared as foreign keys until the table of which they will be borrowing from is also created. Placeholders must be put in place.

Start by creating tables for all entities on your schema

Foreign keys are declared as follows:

FOREIGN KEY(mgr_id) REFERENCES employee(emp_id)
- FOREIGN KEY - Declaration that this is a foreign key
- (mgr_id) this is the name of the attribute in the table
- REFERENCES employee - This name of the database that the foreign key comes from
- (emp_id) this is the name of the attribute in the foreign table

ON DELETE SET NULL - When creating a foreign key this is good practise

When adding to the tables it can be difficult, especially when tables rely on each other for a foreign key and have a circular relationship. 

The first table entry should have foreign keys added as NULL, then when the foreign key table has been created, the NULL values should be updated. 