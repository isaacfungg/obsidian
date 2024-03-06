***
What is SQL?
* SQL stands for Structured Query Language, and it is a domain specific language used for managing and manipulating relational databases

What is a database?
* A database is a structured collection of data that is organized and stored for efficient retrieval and manipulation

Explain the difference between SQL and MySQL
* SQL is a language used to manage and manipulate relational databases, while MySQL is an open-source relational database management system that uses SQL as its query language

What is a primary key?
* A primary key is a unique identifier for a record in a database table. It ensures that each record can be uniquely identified and helps maintain data integrity.

What is a foreign key?
* A foreign key is a field in a database table that is used to establish a link between the data in two tables. It creates a relationship between the tables by referencing the primary key of another table.

Explain the types of SQL commands
* SQL commands can be broadly categories into Data Definition Language (DDL), Data Manipulation Language (DML), Data Query Language (DQL), and Data control Language (DCL).

What is the difference between CHAR and VARCHAR data types?
* CHAR is a fixed-length character data type, while VARCHAR is a variable-length character data type. VARCHAR is more flexible as it only stores the characters entered, whereas CHAR pads the remaining spaces with blanks.

What is normalization?
* Normalization is the process of organizing data in a database to reduce redundancy and improve data integrity. It involves dividing large tables into smaller tables and defining relationships between them.

Explain the difference between INNER JOIN and LEFT JOIN
* INNER JOIN returns only the rows where there is a match in both tables, while LEFT JOIN returns all rows from the left table and the matched rows from the right table. If there is no match, NULL values are returned for columns from the right table

What is the purpose of the GROUP BY clause?
* The GROUP BY clause is used to group rows that have the same values in specified columns into summary rows, like finding the total or average for each group.

Explain the difference between UNION and UNION ALL
* UNION combines the result sets of two queries, eliminating duplicate rows, while UNIONS ALL combines the result sets including duplicates.

What is an index, and why is it used?
* An index is a data structure that improves the speed of data retrieval operations on a database table It is used to quickly locate and access the rows in a table based on the values in one or more columns

What is a stored procedure?
* A stored procedure is a precompiled collection of one or more SQL statements that can be executed as a single unit. it is stored in the database and can be called by name.

Explain the ACID properties of a transaction
* ACID stands for Atomicity, Consistency, isolation, and Durability. It is a set of properties that guarantee that database transactions are processed reliably.

What is the purpose of the HAVING clause?
* The HAVING clause is used in combination with the GROUP BY clause to filter the results of a group based on a specified condition

What is a view in SQL?
* A view is a virtual table derived from one or more tables. It does not store the data itself but provides a way to represent the result of a stored query.

What is the purpose of the SQL ORDER BY clause?
* The ORDER BY clause is used to sort the result set of a query in ascending or descending order based on one or more columns

What is a trigger?
* A trigger is a set of instructions that are automatically executed in response to certain events on a particular table or view in a database.
