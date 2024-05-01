***
#### Instance Variables
* Variables that are an instance of a **class** or a **struct**
	* Created dynamically (usually)

*Java* vs *c*
* Java: **Objects** are instances of non-static variables of a **class**
* C: **Structs** are named variable group, or one of their instances


#### Struct Size and Alignment
* Alignment rules apply inside a struct
	* Each instance variable will be aligned according to its type size
	* Structs are usually aligned according to their largest member type

#### Memory Heap
* The **heap** os a large section of memory from which **malloc** allocates objects 
	* **malloc** finds unused space in the heap, marks as used and returns it
	* **free** marks space as unused
* Java: All objects are stored in the heap

