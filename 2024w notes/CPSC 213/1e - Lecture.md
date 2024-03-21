***
#### Static Procedure Calls 
```c
void ping() {}

void foo() {
	ping();
}
```

`Procedure/Funciton`: Subroutine with a name, argument, and local scope
`Procedure Call`: Calls the procedure to run with 


#### Implementing Procedure 
`Return Address`: 
* Location to jump back to after a procedure finishes.
- Determined by the call's location, making it dynamic.
- Allows for a procedure to be called by multiple others.

**Control Flow**: The process where a program's execution moves from one place to another.
**Calling**: When a procedure is invoked, the program's flow jumps to that procedure.
**Returning**: After a procedure finishes executing, the flow returns to the point right after where it was called.
**Dynamic Behaviour**: The return address is dynamic because procedures can be called from multiple points.


#### The Stack and Activation Frames
- **The Stack**: A data structure used for managing function calls. It works on a "last-in, first-out" basis. Activation frames (or call frames) are pushed onto the stack with each function call and popped off when a function returns.
    - **Activation Frame**: Contains all the information necessary for a function call, including local variables, arguments, and the return address.