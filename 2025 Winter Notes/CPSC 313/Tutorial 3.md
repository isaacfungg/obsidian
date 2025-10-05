***
In this tutorial, we'll review pipeline timing, and then compare code of varying quality (in the form of solutions to previous course exercises).

## Pipeline Timing

[](https://github.students.cs.ubc.ca/cpsc313/CPSC313-2025W1/tree/main/tutorial/3#pipeline-timing)

Given a processor with the following performance:

- Stage 1 takes 100 ps
- Stage 2 takes 60 ps
- Stage 3 takes 90 ps
- Stage 4 takes 120 ps
- Each register adds 30 ps

_Assume that the PC is updated during Stage 4_

1. **Recall the definitions of latency and throughput of a processor**
2. For the sequential implementation of this processor...
    1. **What is the latency?** (in ps)
        1. 370 ps
        2. 490 ps
        3. **400 ps**
        4. 150 ps
        5. 600 ps
    2. **How much time does it take for an instruction to get retired?**
	    400ms
    3. **What is the throughput?** (in GIPS, 2 decimal places)
	    2.5GIPS
3. For the pipelined implementation of this processor...
    1. **What is the latency?** (in ps)
        1. 480 ps
        2. 490 ps
        3. 400 ps
        4. 150 ps
        5. **600 ps**
    2. **How much time does it take for an instruction to get retired?**
	    600 ps
    3. **What is the throughput?** (in GIPS, 2 decimal places)
	    6.67 GIPS
4. Suppose now that the company producing the processors decides that pipeline registers are too expensive to make. Thus, they decide to remove one of the pipeline registers to make production cheaper. However, we must now merge two **consecutive** stages of the processor to allow the pipelined implementation to still function properly. **Consider the following questions as being in a pipelined implementation:**
    1. **Which of the two stages should we merge?**
		Stage 2 and 3
    1. **What is the new latency of the processor, with those stages merged?**
	    540 ps
    2. **What is the new throughput?** (in GIPS, 2 decimal places)
	    5.56 GIPS
    3. **How much slower is our new processor, compared to before we merged two stages?** (as a percentage)
	    20% slower

**Ranking dstE**
1. dstE2
2. dstE1
3. dstE5
4. dstE4
5. dstE3

**Ranking inst_to_enum**
1. inst3
2. inst2
3. inst1
4. inst4

**Ranking


```
main:
	1:	irmovq  stack, %rsp
	2:	irmovq  b, %rdi
	3:	irmovq  f, %rsi
	4:	call swap
		nop
	5:	halt

	swap:
	6:	mrmovq  0(%rdi), %r10
	7:	mrmovq  0(%rsi), %r11
		nop
		nop
	8:	rmmovq  %r10, 0(%rsi)
	9:	rmmovq  %r11, 0(%rdi)
	10:	ret
		nop
		nop
		nop

	.pos 0x1000
	data:
	a:      .quad 0xCAFE
	b:      .quad 0xFACE
	c:      .quad 0xFEED
	d:      .quad 0xDECAF
	e:      .quad 0xBAD
	f:      .quad 0xBEAD
	g:      .quad 0xACE
	h:      .quad 0xFADE

	.pos 0x2000
		.quad 0
		.quad 0
		.quad 0
		.quad 0
		.quad 0
		.quad 0
	stack:
```

```
main:
	1:	irmovq  stack, %rsp
	2:	irmovq  b, %rdi
	3:	irmovq  f, %rsi
		nop
		nop
	4:	mrmovq  0(%rdi), %r10
	5:	mrmovq  0(%rsi), %r11
		nop
		nop
	6:	rmmovq  %r10, 0(%rsi)
	7:	rmmovq  %r11, 0(%rdi)
	8:	halt

	.pos 0x1000
	data:
	a:      .quad 0xCAFE
	b:      .quad 0xFACE
	c:      .quad 0xFEED
	d:      .quad 0xDECAF
	e:      .quad 0xBAD
	f:      .quad 0xBEAD
	g:      .quad 0xACE
	h:      .quad 0xFADE

	.pos 0x2000
		.quad 0
		.quad 0
		.quad 0
		.quad 0
		.quad 0
		.quad 0
	stack:
```