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

**Select:**
```plsql
SELECT DISTINCT genre FROM movies LIMIT 10;
SELECT genre AS 'Genre' FROM movies;
SELECT * FROM movies WHERE name LIKE 'Se_en';   
SELECT * FROM movies WHERE IS NOT NULL;
SELECT * FROM movies WHERE year BETWEEN 1970 AND 1979;
SELECT * FROM movies WHERE year > 2014 OR genre = 'action' ORDER BY year;

SELECT name,
	CASE
		WHEN imdb_rating > 8 THEN 'Fantastic'
		WHEN imdb_rating > 6 THEN 'Poorly Received'
		ELSE 'Avoid at All Costs'
	END AS 'Rating'
FROM movies;
```
* _ is a wild card for one spot
* % is a wild card that matches zero or ore missing characters
* Distinct
	* Returns with no duplicates
* AS 
	* Changes the name
* LIKE
	* Gets values similar to param
* IS NOT/ IS
	* Filtering specific values
* BETWEEN
	* Lets you get values between a range (int or string both work)
* ORDER BY 
	* Sorts by descending order
* LIMIT
	* Limits the number of values returned

