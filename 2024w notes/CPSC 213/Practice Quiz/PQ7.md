***
#### PQ7.1 
`Load from 0x2000`: It reads from or writes to a global variable.
`Load base + offset`: It reads from or writes to a member of a dynamic struct. (Only if it isn't r5)
`Return Address`: Can be found through what has been loaded for the jump
`Ld/st r5 after ra offset`: Loading/Storing arguments

#### PQ7.2
`Caller Prologue`: Allocate space on the stack for the parameter variables of the function called
`Callee Prologue`: Store the return address onto the stack and push the stack to make room for local variables
`Caller Epilogue`: Deallocate space reserved for the parameter variables
`Callee Epilogue`: Pops the space allocated for the local variables and reads the return address


