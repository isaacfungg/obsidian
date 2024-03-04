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