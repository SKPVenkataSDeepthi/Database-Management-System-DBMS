# PostgreSQL 

* Capitalization matters
* If Virtual machine doesn't have postgresql installed in it, we can use the following command "psql --username=freecodecamp --dbname=postgres"
* If it is already installed use terminal application to interact with it


### Commands
1. \l --- to list the databases that are existing
2. CREATE DATABASE database_name; -- to craete a new database
3. \c database_name -----to connect to the database
4. \d --- to display the tables
5. CREATE TABLE table_name(); -- to create a table
6. ALTER TABLE table_name ADD COLUMN column_name DATATYPE; -- to create column
7. ALTER TABLE table_name DROP COLUMN column_name; --- drop a column
8. ALTER TABLE table_name RENAME COLUMN column_name TO new_name; -- renaming the column name to the new name
9. INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);   --- inserting rows into the table
10. SELECT columns FROM table_name; --- use * to see all the columns data
11. DELETE FROM table_name WHERE condition; --- for deleteing some record fromt the table
12. DROP TABLE table_name; --- to drop the table
13. ALTER DATABASE database_name RENAME TO new_database_name; --- renaming the database
14. UPDATE table_name SET column_name=new_value WHERE condition; --- update the table
15. SELECT columns FROM table_name ORDER BY column_name; --- view data by sorting..
16. ALTER TABLE table_name ADD PRIMARY KEY(column_name); --- add name primnary key that uniquely identifies
17. ALTER TABLE table_name DROP CONSTRAINT constraint_name; --- drop name primary key
18. ALTER TABLE table_name ADD COLUMN column_name DATATYPE REFERENCES referenced_table_name(referenced_column_name); --- setting up foreign key
19. ALTER TABLE table_name ADD UNIQUE(column_name); -- these tables have one-to-one relationship
20. ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL; --- you dont want to have a row that is for nobody
21. SELECT columns FROM table_name WHERE condition;  -- view a particular row with WHERE Condition
22. CREATE TABLE table_name(column_name DATATYPE CONSTRAINTS);
23. ALTER TABLE table_name ADD COLUMN column_name DATATYPE CONSTRAINT REFERENCES referenced_table_name(referenced_column_name); -- one to many relatioonship
24. ALTER TABLE table_name ADD FOREIGN KEY(column_name) REFERENCES referenced_table(referenced_column); --- The foreign keys you set before were added when you created the column. You can set an existing column as a foreign key like this command
25. ALTER TABLE table_name ADD PRIMARY KEY(column1, column2); -- creating a composite primary key(create a primary key from two columns, known as a composite primary key.)
26. SELECT columns FROM table_1 FULL JOIN table_2 ON table_1.primary_key_column = table_2.foreign_key_column; --- full join characters, we added a foreign key, that means we can get all the data from both tables with a JOIN command
27. SELECT columns FROM junction_table
FULL JOIN table_1 ON junction_table.foreign_key_column = table_1.primary_key_column
FULL JOIN table_2 ON junction_table.foreign_key_column = table_2.primary_key_column; --- This shows the "one-to-many" relationship.When you see the data, be sure to check the "many-to_many" relationship. Many characters will have many actions.