***
Fetch
* icode:ifun = M1[PC]
* rA:rB = M1[PC + 1]
* valC = M8[PC + 2]
* valP = PC + 10
Decode
* valB = R[rb]
Execute
* valE = valB + valC
* Cnd = cond(CC, ifun)
Memory
Write back
PC Update
* PC = cnd ? valM : valP


Need to add a logic so that when there's an indirect jump then it adds since ifun determines the operation in alu as well as the condition.


```
   0x000: 30f4600000000000	|   irmovq Stack, %rsp
   0x00a: 30f0380000000000	|   irmovq rtnp,%rax
   0x014: a00f                	|   pushq %rax       
   0x016: 6300                	|   xorq %rax,%rax   
   0x018: 742c000000000000 |   jne target       
   0x0??: 30f00100000000000000	|   irmovq $1,%rax 
   0x02b: ??                  	|   halt
   0x02c: ??                  	| target:   ret
   0x0??: 30f30200000000000000	|   irmovq $2,%rbx
   0x037: 00                  	|   halt
   0x038: 30f2????????????????	| rtnp: irmovq $3,%rdx
   0x0??: 00                	  |   halt
   0x0??: ????????????????????	| .pos 0x60
   0x060: ????????????????????	| Stack: 

```



Question 3:
irmovq 0x30,rsp


