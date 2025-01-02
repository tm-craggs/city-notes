A join is used to combine rows from 2 or more tables based on a related column

For example, a table of employees and a table of managers. They both share the employee ID as a primary/foreign key. You can use a table join to combine columns. For example, you want to see the branch location of each manager. 

There are 4 basic types of join

- General Join (inner join), combine rows whenever they have the shared row in common
- Left join, this will give you all of the first table in the results, but fill NULL in the second table
- Right join, opposite of left join
- Full outer join, left and right join combined. There is not functionality for this in MySQL. 

