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
#### Procedure Calls and Returns
- **Control Flow**: The process where a program's execution moves from one place to another.
    - **Calling**: When a procedure is invoked, the program's flow jumps to that procedure.
    - **Returning**: After a procedure finishes executing, the flow returns to the point right after where it was called.
    - **Dynamic Behaviour**: The return address is dynamic because procedures can be called from multiple points.
#### The Stack and Activation Frames
- **The Stack**: A data structure used for managing function calls. It works on a "last-in, first-out" basis. Activation frames (or call frames) are pushed onto the stack with each function call and popped off when a function returns.
    - **Activation Frame**: Contains all the information necessary for a function call, including local variables, arguments, and the return address.

#### Local Variables and the Stack
- **Local Variables**: Variables defined within a procedure. They are temporary and stored in the activation frame on the stack.
    - **Lifetime**: Allocated when a procedure is called and deallocated (freed) when the procedure returns.

#### Implementing Procedure Calls
- **Saving Return Address**: Before a procedure call, the return address (where the program should return after the procedure finishes) is saved. This is often done using a special register or on the stack itself.

#### Buffer Overflow and Security
- **Buffer Overflow**: A critical security vulnerability that occurs when more data is written to a buffer than it can hold, leading to adjacent memory locations being overwritten. This can be exploited to execute arbitrary code.
    - **Example**: A program that copies user input into a smaller buffer without checking the size can be vulnerable.

