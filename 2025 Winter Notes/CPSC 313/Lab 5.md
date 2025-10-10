***
#### Registers Used
rsp: stack
rdi: data
rsi: size
r8, r9, r11, rax, rcx, rbx


Size: 8
Clock Count: 364 -> 340 -> 317 ->275->216
Retired Instructions: 319
Expected Result:
002000  08 00 00 00 00 00 00 00  
002008  0B 00 00 00 00 00 00 00  
002010  0B 00 00 00 00 00 00 00  
002018  09 00 00 00 00 00 00 00  
002020  05 00 00 00 00 00 00 00  
002028  03 00 00 00 00 00 00 00  
002030  08 00 00 00 00 00 00 00  
002038  09 00 00 00 00 00 00 00

Size: 32
Clock Count: 1732 -> 1043
Retired Instructions: 1543
Expected Result:


```
main:
	irmovq	$stack, %rsp
	irmovq	$data, %rdi
	irmovq	$size, %rsi
	mrmovq	0(%rsi), %rsi
	call	smooth
	halt

smooth:
    pushq   %rbx
    pushq   %r12
    pushq   %r13
    pushq   %r14
    irmovq  $1, %rax        # rax holds i
    irmovq  $1, %r10        # inc
    irmovq  $8, %r11        
    mrmovq  0(%rdi), %r12   # array[0]
    mrmovq  8(%rdi), %r13   # array[1]
    mrmovq  16(%rdi), %r14  # array[2]
    
test:
    rrmovq  %rsi, %rdx
	subq	%r10, %rdx
	subq	%r10, %rdx      # n - 2
	subq	%rax, %rdx
	jle	last             

	# ------ first iteration ------
	irmovq  $4, %rcx
	irmovq  $2, %r9
	mulq    %r13, %r9
	addq    %r12, %r9
	addq    %r14, %r9
	divq    %rcx, %r9

	rrmovq  %rax, %rbx
	mulq    %r11, %rbx
	addq    %rdi, %rbx
	rmmovq  %r9, 0(%rbx)

	rrmovq  %r9, %r12
	rrmovq  %r14, %r13
	mrmovq  16(%rbx), %r14
	addq    %r10, %rax

	# ------ second iteration ------
    rrmovq  %rsi, %rdx
	subq	%r10, %rdx
	subq	%rax, %rdx
	jle	done

	irmovq  $4, %rcx
	irmovq  $2, %r9
	mulq    %r13, %r9
	addq    %r12, %r9
	addq    %r14, %r9
	divq    %rcx, %r9

	rrmovq  %rax, %rbx
	mulq    %r11, %rbx
	addq    %rdi, %rbx
	rmmovq  %r9, 0(%rbx)

	rrmovq  %r9, %r12
	rrmovq  %r14, %r13
	mrmovq  16(%rbx), %r14
	addq    %r10, %rax
	jmp	test

last:
	irmovq  $4, %rcx
	irmovq  $2, %r9
	mulq    %r13, %r9
	addq    %r12, %r9
	addq    %r14, %r9
	divq    %rcx, %r9

	rrmovq  %rax, %rbx
	mulq    %r11, %rbx
	addq    %rdi, %rbx
	rmmovq  %r9, 0(%rbx)
done:
    popq %r14
    popq %r13
    popq %r12
    popq %rbx
    ret


# Array with 32 elements
.pos	0x2000
size:
.quad	8
data:
.quad	11
.quad	12
.quad	10
.quad	5
.quad	1
.quad	8
.quad	15
.quad	0
.quad	1
.quad	8
.quad	13
.quad	5
.quad	6
.quad	5
.quad	9
.quad	12
.quad	4
.quad	15
.quad	5
.quad	14
.quad	15
.quad	2
.quad	7
.quad	16
.quad	13
.quad	8
.quad	15
.quad	1
.quad	14
.quad	11
.quad	0
.quad	8

.pos 0x5000
stack:

```

