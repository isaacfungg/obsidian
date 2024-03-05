***
#### PQ5.1
```c
char * copy(char* from, char* to, int n) {
	for (int i=0; i<n; i++) 
		to[i] = from[i];
	return to;
}

void foo(char* x, int n) {
	char * y = malloc(n);
	copy(x, y, n);
}

#There is a possible memory leak that is best resolved by adding, removing or moving malloc or free in copy and/or foo
```

##### Cases

###### Multiple References
* If an **unspecified function is before another function and no free** it is unclear whether the unspecified function called free or not. This results in either a possible dangling pointer or memory leak that can be solved by reference counting. 
###### One Reference

###### Other
* If **free is placed before return** it causes a dangling pointer