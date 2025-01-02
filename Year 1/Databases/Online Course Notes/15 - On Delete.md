On delete is used when declaring foreign keys, and it defines what should happen with the table entry should the attribute where the foreign key is being inherited from be deleted. 

There are two types of on delete
- On delete set null, the foreign key column in the table entry is set to null
- On delete cascade, this will delete the entire entry in the table should the foreign key be deleted.

Set null is ideal to use when a foreign key is just a foreign key and not a primary key. 
If a foreign key is also a primary key, then cascade must be used, as primary keys cannot be set to null.

