```
1:	
2:		irmovq	11, %rax
3:		irmovq	1, %rbx
4:		irmovq	1, %rcx
		Stall
5:	
6:	loop_start:
7:		rrmovq	%rax, %rdi
8:		subq	%rcx, %rax
9:		subq	%rbx, %rdi
10:		jle	loop_end
11:		jmp	loop_start
12:	
13:	loop_end:
14:		andq   %r13, %r11
15:		andq   %r9, %r10
16:		andq   %r13, %r12
17:		xorq   %r9, %r13
18:		mulq   %r11, %r9
19:		xorq   %rbp, %r9
20:
```

Line 7
* 1 stall due to rax

Line 8
* 1 stall due to rcx

Line 9
* 1 stall due to rdi (first iteration with line 8 stall)
* 2 stalls due to rdi (10 times)

Line 19
* 3 stalls on r9