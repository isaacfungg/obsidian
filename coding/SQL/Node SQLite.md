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
* this.lastID is a property that comes from the callback function's context when an 'INSERT' operation is executed successfully
* 