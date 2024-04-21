***

#### CPU
* Execute **instructions**, not C or Java code
* Execution proceeds in **stages**
	* `Fetch`: Load the next instruction from memory
	* `Decode`: Figure out from instruction what needs to be done
	* `Execute`: Do what the instruction asks

#### Computation
* Anything the **compiler can compute** is called `static`
* Anything that can only be discovered during execution is called `dynamic`

#### Static Variables
**Java**
* Static data members are allocated to a **class**, not an object
* They can store built-in scalar types or references to arrays/objects

**C**
* **Global variables** and any other variables declared static
* They can be static scalars, arrays or structs, or pointers

