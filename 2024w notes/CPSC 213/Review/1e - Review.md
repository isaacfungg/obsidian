***
#### Implementing Procedure Return
* **Return address** is:
	* The address a procedure jumps to when it completes
	* A **dynamic** property of the program
* Only the **caller** can provide the address
	* *Convention*: Caller will save the return address in r[6]
* We need a new instruction to read the PC (`gpc`)

#### Allocating and Deallocating Stack Frames
* The allocation of the stack is relatively simple:
	* `Decrement` the stack pointer to **allocate
	* `Increment` the stack pointer to **free
* Division of labour:
	* **Caller** allocates space for *arguments*
	* **Callee** allocates space for *the rest*

#### Stack Frame
`Procedure Prologue`: Code that executes just before procedure starts
* Part in `caller` before call
* Part in `callee` at beginning of call
**Allocates** activation frame and changes stack pointer
* Subtract frame size from stack pointer r5

`Procedure Epilogue`: Code than executes when procedure ends
* Part in `callee` just before return
* Part in `caller` just before returning
**Deallocates** activation frame and restores stack pointer
* Add frame size to stack pointer r5