##### Data Types
* INT
* DECIMAL (M, N)
	* M: total digits
	* N: # of decimal digits
* VARCHAR(L)
	* String of text of length L
* BLOB
	* Binary Large Object, used to store large data
* DATE
	* YYYY-MM-DD
* TIMESTAMP
	* YYYY-MM-DD HH:MM:SS

#### Constraints
* PRIMARY KEY
	* Used to uniquely identify the row. (non null and unique)
* UNIQUE
	* Columns have a different value for every row
* NOT NULL
	* Columns must have a value 
* DEFAULT
	* Takes an additional argument that will be assumed value if the new row does not specify a value for that column
#### Commands
**Creating a table:** 
``` plsql
CREATE TABLE student (
	student_id INT AUTO_INCREMENT,
	name VARCHAR(20) NOT NULL,
	major VARCHAR(20) UNIQUE,
	PRIMARY KEY(student_id)
);
```

**Inserting:**
```plsql
INSERT INTO student VALUES (1, 'Jack', 'Biology');
INSERT INTO student (student_id, name) VALUES (4, 'Claire')
```

**Adding a Column:**
```plsql
ALTER TABLE student ADD COLUMN lastname TEXT;
```

**Update:**
```plsql
UPDATE student SET lastname = 'x' WHERE student_id = 4;
```

**Delete:**
```plsql
DELETE FROM student WHERE lastname IS NULL;
```