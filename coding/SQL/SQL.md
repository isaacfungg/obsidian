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

| student_id | name | major |
| ---- | ---- | ---- |
| 1 | Jack | Biology |
| 4 | Claire | NULL |
