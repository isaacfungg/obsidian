***
#### Opening a Database
```js
const { printQueryResults } = require('./utils');
const sqlite3 = require('sqlite3');
const db = new sqlite3.Databse('./db.sqlite');
```

#### Printing out the columns
```js
db.all('SELECT * FROM TemperatureData ORDER BY year' (error, rows) => {
	if (error) {
		throw error;
	}
	printQueryResults(rows);
});
```
**All:** Used when you expect to retrieve multiple rows from a query (SELECT)
* Callback parameters: **rows** and **error** 
* Returns an array of row objects that match the query
#### Using Placeholders
```js
const ids = [1, 25, 45, 325, 232, 43];
ids.forEach((id) => {
	db.get("SELECT * FROM TemperatureData WHERE id = $id"
	{
		$id: id
	},
	(error, rows) => {
		printQueryResults(rows)
	});
})
```
**Get:** Used to retrieve a single row matching the query
* Callback parameters: **row** and **error**
* Returns **undefined** if no rows matches
#### Inserting
```js
const newRow = {
	location: 'Turkey',
	year: 1976,
	tempAvg: 13.35,
}

db.run("INSERT INTO TemperatureData (location, year, temp_avg) VALUES ($location, $year, $tempAvg)", {
	$location = newRow.location,
	$year = newRow.year,
	$tempAvg: newRow.tempAvg,
} function(error) {
	if(error) {
		return console.log(error);
	}

	db.get("SELECT * FROM TemperatureData WHERE id = $id", {
		$id = this.lastID,
	}, function(error, row) {
		printQueryResults(row);
	});
});
```
**Run:** Best for executing an SQL query that doesn't return rows (INSERT, UPDATE, DELETE, CREATE TABLE)
* Callback parameters: **error**, on successful execution **this.lastID** provides the row ID of the last inserted row for **INSERT** operations and **this.changes** can provide the number of rows affected by **UPDATE** or **DELETE**

#### db.Each()
```js
db.each("SELECT name, email FROM Users", (err, row) => {
	if (err) {
		console.error(err.message);
	} else {
		console.log("${row.name}: ${row.email}");
	}
}, (err, count) => {
	if (err) {
		console.error(err.message);
	} else {
		console.log("Total users: ${count});
	}
});
```
**Each:** Processes each row of the result set individually through a callback function
* Row callback: For each row returned by the query, 'db.each' calls the provided row callback function, passing it the current row's data
* Completion callback: After all rows have been processed, or if an error occurs that stops the query execution, the completion callback function is called. 
