`Calling Convention`: The rules that callers and calles use to communicate information

###### Calling Conventions: Parameters
* Return value goes in %rax
* Arguments/parameters are passed in registers, in this order
	* %rdi, %rsi, %rdx, %rcx, $r8, $r9
	* Push the remaining ones in the stack in reverse order

**Caller Saved Registers**
* The callee is allowed to scribble over them, so if the caller cares about their contents, the caller must save them to the stack
* e.g. pushing the value before the call and then popping it back after

**Callee Saved Registers** 
* If the callee uses them, then the callee must restore the original values before returning
* e.g. push the original value to the stack then pop it back to the same register to restore the value