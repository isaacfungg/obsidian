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








irmovq	2, %r10
	irmovq	3, %r11
	irmovq	0, %rax
loop:
	irmovq	1, %r12
	subq	%r12, %r11
	jl	end
	addq	%r10, %rax
	jmp	loop
end:
	irmovq	$result, %rcx
	rmmovq	%rax, 0(%rcx)
	halt

	.pos	1000
result:
	.quad	0x000000000




subq	%r12, %r11
* 1 stall (4 iterations)

1



addq ra, rb
addq, rb, rc