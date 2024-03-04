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

###### Memory Deallocation
Wise management of memory requires deallocation
* Memory is a finite resource
* Deallocation frees previously allocated emory for re-use
 In **C**:
 * Dynamic memory must be deallocated explicitly by calling free
 * Memory is deallocated immediately, no checks if it's still in use

###### Memory Heap
The heap is a large section of memory from which malloc allocates objects
* **malloc** finds unused space in the heap, marks as used and returns it
* **free** marks space as unused
* heap may be increased if necessary

#### What malloc and free do
###### Organization of memory
* Statically allocated: code, static data
* The rest is unused or dynamically allocated
###### Malloc/free
* Implemented in library
* Manage a chunk of memory called the Heap
* Keep track of what's allocated or free
###### Malloc
*  Find a free chunk of memory of appropriate size
* Mark it allocated
* return pointer to it (keeping track of its size)
###### Free
* Use pointer to determine allocated size
* Mark referenced memory as free

###### What free(x) does
* Deallocates chunk of memory starting at address x
* This memory can be reused by subsequent call to malloc
###### What free(x) does **not** do
* After call to free, x still points at the freed object (does not change any pointers)
* Other variables may still point there too
* The data stored at address x is **not** erased

#### Memory Leaks
A **memory leak** is a dynamic memory object with **no pointers** pointing to it
* Usually happens if a program doesn't free object properly
* May also happen if a pointer to a valid object is changed to another value

Why is this a problem?
* If object had useful information, it can't be accessed anymore
* If object is large (or if many memory leaks happen in sequence), program will use too much memory



#### Avoiding Memory Problems in C
Understand the problem
* Where is the memory allocated?
* Where is the memory freed?

Avoid the program cases
* If possible, restrict dynamic allocation/free to single procedure
* If possible, don't write procedures that return pointers
* If possible, use local variables instead
	* Local variables are allocate on call and freed on return, automatically

Engineer for memory management
* Define rules for which procedure is responsible for deallocation
* Use explicit reference counting if multiple potential deallocators
* Define rules for which pointers can be stored in data structures
* Use coding conventions and documentation to ensure rules are followed

#### Strategies
##### Co-Locating Allocation and Deallocation
If a procedure returns the value of a dynamically allocated object
* Allocate that object in the caller and pass a pointer to it the callee
* Good if caller does both malloc/free itself
```c
void receive (struct MBuf* mBuf) {}

void foo() {
	struct MBuf* mb = malloc(sizeof(*mbuf));
	receive(mb);
	free(mb);
}
```

##### Using Local Variables
If a procedure does malloc and free
* Use a local variable instead of malloc
* Local variables are allocated on call and deallocated on return
```c
void receive (struct MBuf* mBuf) {}

void foo() {
	struct MBuf mb;
	receive(&mb);
}
# Do NOT return the address of a local variable (dangling pointer)
```
