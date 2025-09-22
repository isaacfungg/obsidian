***
**Arguments/parameters are passed in registers in this order:
* %rdi, %rsi, %rdx, %rcx, %r8, %r9

**Caller saved registers**
* The callee is allowed to scribble all over them
* %rax, %rdi, %rsi, %rdx, %rcx, %r8, %r9, %r10, %r11

**Callee saved registers
* If the callee uses them, then the callee must restore the original values before returning
* %rbx, %rbp, %r12, %r13, %r14