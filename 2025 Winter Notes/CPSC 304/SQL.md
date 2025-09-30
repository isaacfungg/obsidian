***
`Creating Tables`
* The domain of each attribute is specified and enforced when tuples are added or modified
```sql
CREATE TABLE Student (
	sid INTEGER,
	name CHAR(20),
	address CHAR(30),
	phone CHAR(13), 
	major CHAR(4)
)
```

`Destroying Relations`
```sql
DROP TABLE Student
```

`Altering Relations`
```sql
ALTER TABLE Student
	ADD COLUMN gpa REAL;
```

`Adding and Deleting Tuples`
```sql
INSERT
INTO Student (sid, name, address, phone, major)
VALUES ('123', 'G. Chan', '1234', '604952347', 'CPSC')


DELETE
FROM Student
WHERE name = 'Smith'
```

`Key Constraints`
Can only have one primary key in sql.
```sql
CREATE TABLE Student (
	sid INTEGER PRIMARY KEY,
	name CHAR(20),
	address CHAR(30),
	phone CHAR(13), 
	major CHAR(4)
)

CREATE TABLE GRADE (
	sid INTEGER,
	FOREIGN KEY (sid) REFERENCES Student,
)
```

`Referential Integrity`
* Default is NO ACTION
* CASCADE updates/deletes all tuples that refer to the deleted tuple
* SET NULL / SET DEFAULT sets the foreign key value to null