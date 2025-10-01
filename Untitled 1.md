```
1:	
2:		irmovq	9, %rax 
3:		irmovq	1, %rbx
4:		irmovq	1, %rcx
5:	
6:	loop_start:
7:		rrmovq	%rax, %rdi # rdi = rax
8:		subq	%rcx, %rax # rax -= rcx
9:		subq	%rbx, %rdi # rdi -= rbx
10:		jg	loop_start
11:	
12:	loop_end:
13:		subq   %r8, %r11
14:		subq   %r12, %r13
15:		xorq   %r9, %r10
16:		mulq   %r8, %r9
17:		rrmovq   %r9, %rbx
18:		rrmovq   %r11, %r8
19:
```