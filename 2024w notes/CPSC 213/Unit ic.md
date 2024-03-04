***
#### Struct and Alignment
```C
# ---------- Case 1 --------------
struct A {
	char c;
	int i;
}
# c   size = 1 offset = 0
# pad size = 3 offset = 1
# i   size = 4 offset = 4
# Offset must be amultiple of the size (char, int)

# ---------- Case 2 --------------
struct B {
	int i;
	char c;
}
# i   size = 4 offset = 0
# c   size = 1 offset = 4
# pad size = 3 offset = 5
# Size of struct must be a multiple of size of largest base type

# ---------- Case 3 --------------
struct C {
	char c;
	int i;
}
# c   size = 1 offset = 0
# pad size = 3 offset = 1
# i   size = 4 offset = 4
struct D {
	char c;
	struct C;
}
# c     size = 1 offset = 0
# pad   size = 3 offset = 1    <- Added to make sure struct is aligned
# x.c   size = 1 offset = 4
# x.pad size = 3 offset = 5
# x.i   size = 4 offset = 8

# Include a struct inside of another, the offset to the first element of the included struct must be aligned to biggest basic type (char, int)

```


#### Count Memory References in Struct Access
```C
struct A {
	int a0[10];
	int *a1;
	struct B *a2;
}
struct B {
	struct A b0;
}
Struct B s;
Struct B *d;

# d->b0.a1->b0.a1[5]

```