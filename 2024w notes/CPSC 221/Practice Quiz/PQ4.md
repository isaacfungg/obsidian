***

##### PQ4.1
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
```
###### Memory Reads
**s->b[2]** - 2 reads (->, b[2] static)
**&s->c.f.y[2]** - 1 read (->), we are not interested in the value of c.f.y[2] only the address
**s->c.g->a** - 3 reads (->, g pointer, ->)
