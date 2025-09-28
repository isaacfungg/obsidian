* Simple types are easier to partition than complex types
* Input and output partitioning serve as mechanisms for systematically creating test suites
* Output partitioning is more difficult in practice than input partitioning

```
CREATE TABLE D (
	d1 INT PRIMARY KEY,
	d2 INT
);

CREATE TABLE E (
	e1 INT PRIMARY KEY,
	e2 INT
);

CREATE TABLE F (
	f1 INT PRIMARY KEY,
	f2 INT
);

CREATE TABLE T (
	d1 INT,
	e1 INT,
	f1 INT,
	PRIMARY KEY (d1, e1),
	FOREIGN KEY (d1) REFERENCES D(d1),
	FOREIGN KEY (e1) REFERENCES E(e1),
	FOREIGN KEY (f1) REFERENCES F(f1),
);


```