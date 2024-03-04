***
#### 1c.1
```c
struct X {
	int i;
	int j;
}

struct X s;

# How do you load s.j into r1?
# ld 4(r0), r1
```
#### 1c.2
```r
ld $b, r0
ld (r0), r0
ld $i, r1
ld (r1), r1

# How do you get r0 = b[i]?
shl $2, r1      # turns index into an offset
add r0, r1      # adds offset to the address
ld (r1), r0     # loads b[i]
```
#### 1c.3
```c
struct D {
	int e;
	int f;
};

struct X {
	int i;
	struct D d;
	int j;
};

# What is the offset of member j in struct x?
# x.i   | Size = 4 | Offset = 0
# x.d.e | Size = 4 | Offset = 4
# x.d.f | Size = 4 | Offset = 8
# x.j   | Size = 4 | Offset = 12
```
#### 1c.4
```c
struct D {
	int e;
	int f;
}

struct X {
	int i;
	struct D *d;
	int j;
}

# What is the offset of member j in struct X below?
# x.i | Size = 4 | Offset = 0
# pad | Size = 4 | Offset = 4
# x.d | Size = 8 | Offset = 8
# x.j | Size = 4 | Offset = 16
```


#### 1c.5
```c
struct D {
	int e;
	int f;
}

struct X {
	int i;
	struct D d[10];
	int j;
}

# What is the offset of member j in struct X below?
# x.i      | Size = 4 | Offset = 0
# x.d[0].e | Size = 4 | Offset = 4
# x.d[0].f | Size = 4 | Offset = 8
# ...
# x.d[9].e | Size = 4 | Offset = 76
# x.d[9].f | Size = 4 | Offset = 80
# x.j      | Size = 4 | Offset = 84
```

#### 1c.6
```c
struct Y {
	char c;
	short s;
}

struct X {
	int i;
	struct Y y[10];
	int j;
}

# What is the offset of member j ins truct X below?
# x.i      | Size = 4 | Offset = 0
# x.y[0].c | Size = 1 | Offset = 4
# padding  | Size = 1 | Offset = 5
# x.y[0].s | Size = 2 | Offset = 6
# ...
# x.y[9].c | Size = 1 | Offset = 38
# padding  | Size = 1 | Offset = 39
# x.y[9].s | Size = 2 | Offset = 40
# x.j      | Size = 4 | Offset = 44
``` 

#### 1c.7
```c
struct A {
	char a;
	int *b;
	int *p;
}

struct X {
	char c;
	struct A a;
	int j;
}

struct X s;

# How many memory reads to load s.a.b[2] into r1?
# 2 - (*b, b[2])
```