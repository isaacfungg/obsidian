216 version
```
main:
	irmovq	$stack, %rsp
	irmovq	$data, %rdi
	irmovq	$size, %rsi
	mrmovq	0(%rsi), %rsi
	call	smooth
	halt

smooth:
    irmovq	$2, %r9
    irmovq  $1, %r10        # incrementer
    irmovq	$8, %r11
    irmovq  $1, %rax        # rax holds i
test:
    rrmovq  %rsi, %rdx      # compute i < n - 1
	subq	%r10, %rdx
	subq	%rax, %rdx
	jle	done
    
    # ------------- avg function start -------------
    rrmovq  %rax, %r8       # array[i - 1] into %rbx
	subq	%r10, %r8       # array[i - 1] into %rbx
	mulq	%r11, %r8       # array[i - 1] into %rbx
	addq	%rdi, %r8       # array[i - 1] into %rbx
	mrmovq	0(%r8), %rbx    # array[i - 1] into %rbx

    rrmovq  %rax, %r13       # array[i] into %rcx
	mulq	%r11, %r13       # array[i] into %rcx
	addq	%rdi, %r13       # array[i] into %rcx
	mrmovq	0(%r13), %rcx    # array[i] into %rcx

	rrmovq	%rax, %r14       # array[i + 1] into %rdx
    addq    %r10, %r14       # array[i + 1] into %rdx
	mulq	%r11, %r14       # array[i + 1] into %rdx
	addq	%rdi, %r14       # array[i + 1] into %rdx
	mrmovq	0(%r14), %rdx    # array[i + 1] into %rdx

    rrmovq  %rbx, %r8      # compute %rbx + 2 * %rcx + %rdx in %r8
	irmovq  $4, %r12        # divide by 4
	mulq	%r9, %rcx       # compute %rbx + 2 * %rcx + %rdx in %r8
	addq	%rcx, %r8      # compute %rbx + 2 * %rcx + %rdx in %r8
	addq	%rdx, %r8      # compute %rbx + 2 * %rcx + %rdx in %r8
	
	divq    %r12, %r8
    # -------------- avg function end --------------

	rrmovq	%rax, %r13       # array[i] = avg(...)
	mulq	%r11, %r13
	addq	%rdi, %r13
    rmmovq  %r8, 0(%r13)

    addq    %r10, %rax      # increment i
	jmp	test
done:
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