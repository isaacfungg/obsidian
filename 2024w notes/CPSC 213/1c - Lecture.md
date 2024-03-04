***
#### Instance Variables
Variables that are an instance of a **class** or **struct**
* Created dynamically (usually)
* Many instances of the same class/struct can co-exist

Accessing an instance variable
* Requires a reference/pointer to a particular object/struct
* Then variable name chooses a variable in that object or struct

#### Structs in C
A struct is a collection of variables of arbitrary type
* allocated and accessed together
###### Declaration
* Similar to declaring a Java class without methods
* Name is "struct" plus name provided by programmer
* **static**: struct D d0;      <-- Global Variable
* **dynamic**: struct D* d1; <-- Global Pointer\
###### Access:
* **static**: d0.e = d0.f;
* **dynamic**: d1->e = d1->f;
###### Struct Allocation
**Static** structs are allocated by the computer
**Dynamic** structs are allocated at runtime
* The struct pointer may be static or dynamic
* The struct itself is allocated with a call to malloc
```C
void foo() {
	d1 = malloc(sizeof(struct D));
}
```

#### Struct Access in Assembly
* Struct members can be accessed using offset
	* Offset to each variable from base of struct is static
* As before, **static** and **dynamic** differ by extra memory access
```r
# d0.e = d0.f   (Static)
ld $d0, r0       # r0 = &d0
ld 4(r0), r1     # r1 = d0.f
st r1, (r0)      # d0 = d0.f

# d1->e = d1->f  (Dynamic)
ld $d1, r0       # r0 = &d1
ld (r0), r0      # r0 = d1  (d1 is an address)
ld 4(r0), r1     # r1 = d1.f
str r1, (r0)     # d1->e = d1->f
```

#### Memory Access 
**Scalars - ld (r1), r0**
* Access memory at address in register 
**Arrays - ld (r1, r2, 4), r0**
* Base address in register
* Dynamic index in register
* Access memory at base plus index time element-size (4) 
**Struct Members - ld x(r1), r0**
* Base address in register (start of struct)
* Static (constant) offset (bytes from start of struct)
* Access memory at base plus static offset
* Equivalent to access to array element with static index


#### Struct Size and Alignment
Alignment rules apply inside a struct
* Each instance variable will be aligned according to its type size
* Structs are usually aligned according to their largest member type


#### Arrays and Structs
```c
# Array in struct
struct S {
	int i;
	int j[10];
}

# Array of structs
struct S a[42];

# Array of pointers to structs 
struct S* b[42];

a[3].i = b[7]->j[4];
```


#### Dynamic Allocation
Programs can allocate memory dynamically
* allocation reserves a range of memory for a purpose (**heap**)
**Java**: Instances of classes are allocated by the *new* statement
**C**: Byte ranges are allocated by call to malloc procedure 
* These bytes can be used for any type that can fit in them
###### Memory Allocation
*void *malloc(unsigned long n);*
* **n** is the number of bytes to allocate
* returning type is void*
	* pointer to anything (no specified type assigned)
	* can be cast to/from any other pointer type
	* cannot be dereferenced directly
Use *sizeof* to determine number of bytes to allocate
 * *struct Foo *f = malloc(sizeof(struct Foo));*
 * **statically** computes number of bytes in type or variable
 * **Caution**: sizeof(pointer) gives the size of a pointer, not what it points to