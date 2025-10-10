## Shuffling instructions
Consider the following y86 program:

```assembly
A. irmovq 0x123, %rax
B. irmovq 0x456, %rbx
D. irmovq 0x789, %rsi
E. irmovq 0xABC, %rdi
C. addq %rax, %rbx
nop
nop
F. addq %rsi, %rdi
G. modq %rsi, %rax
nop
nop
H. divq %rbx, %rdi
```

1. In the unpipelined implementation of the y86 processor, **how many bubbles will this program produce?**
0
2. In a pipelined implementation without forwarding, **how many bubbles will this program produce?**
c, f, h
8
1. Assume a pipelined implementation without forwarding.
    - **Order the instructions so as to minimize the number of bubbles and produce the same result.** For example, if swapping the first two instructions were the correct answer (it is not), you would answer with the order: `BACDEFGH`
    - ABDECFGH
    - **How many bubbles does your order produce?**

    - In a pipelined implementation with forwarding, **how many bubbles will your program produce?**

```
sum:                      # long sum(long *a, long n)
  andq %rsi, %rsi
  je base                 # goto base if n == 0
  # 2 stalls

  mrmovq (%rdi), %r8
  pushq %r8               # save *a on stack

  irmovq $8, %r8
  addq %r8, %rdi
  irmovq $1, %r8
  subq %r8, %rsi
  call sum                # rax = sum(a+1, n-1)

  popq %r8
  addq %r8, %rax          # rax = *a + sum(a+1, n-1)
  ret

base:
  irmovq $0, %rax         # rax = 0
  ret
```