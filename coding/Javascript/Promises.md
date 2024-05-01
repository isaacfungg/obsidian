***
```js
const promise = new Promise((resolve, reject)) => {
	const res = true;
	if (res) {
		resolve('Resolved');
	} else {
		reject(Error('Error'));
	}
});

promise
.then((res) => console.log(res), (err) => (alert(err));

	  
promise
.then((res) =>console.log(res))
.catch((err) => alert(err))
```
* The first parameter holding a callback function of the `.then()` method will print the resolved value. The second argument to a `.then()` method of a promise object is used when the promise is rejected


