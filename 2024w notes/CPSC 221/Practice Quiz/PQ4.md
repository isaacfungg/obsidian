***

##### PQ4.1 Variation 1
```C
stuct U {
	int y[3];
	int* x;
};

struct T {
	struct S *g;
	struct U f;
};

struct S {
	int a;
	int b[3];
	struct T c;
}
struct S* s;
```
###### Memory Reads
**s->b[2]** - 2 reads (s value, ->b[2])
**s->a**  - 2 reads (s value, ->a)
**&s->c.f.y[2]** - 1 read (s value), we are not interested in the value of c.f.y[2] only the address
**s->c.g->a** - 3 reads (s value, ->g value, ->a)
**s->c.g->b[3]** - 3 reads(s value, c.g value, b[3])

##### PQ4.3
* The offset to a struct element from the start of the struct **can always be determined statically**
* The address of a struct element **can sometimes be determined statically and other times must be determined dynamically**

##### PQ4.4
```C
struct S {
	int* a;
	int b[4];
	struct T c;
	struct S* d;
};

struct T {
	int x[4];
	int* y;
};

struct S* s;
```
What is the SM213 translation for **s->c.x[3] = 0**
ld $0, r0
ld $s, r1
ld (r1), r2
st r0, 32(r2)

##### PQ4.5
```C
struct A {
	int x;
	int* y;
	struct B* b_struct;
};

struct B {
	int i;
	int j[2];
}

struct A* a;
struct B b;
```
###### Translate this code
**a->b_struct = &b**
```r
ld $a, r0
ld (r0), r0
ld $b, r1
st r1, 8(r0)
```

**a->y = b.j**
```r
ld $b, r0     # r0 = &b
ld $4, r1     # r1 = 4
add r1, r0    # r0 = &b.j
ld $a, r1     # r1 = &a
ld (r1), r1   # r1 = a
st r0, 4(r1). # a->y = b.j
```
* You have to add 4 to &b because if you use 4(r0) it uses r0 + 4 as a memory address 

**v0 = a->b_struct->j[1];**
```r
ld $a, r0     # r0 = &a
ld (r0), r0   # r0 = a
ld 8(r0), r1  # r1 = a->b_struct
ld 8(r1), r2  # r2 = a->b_struct->j[1]
ld $v0, r3    # r3 = &v0
st r2, (r3)   # v0 = a->b_struct->j[1] 
```