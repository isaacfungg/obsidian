***
#### aluA
Parameters: icode, valA, valC
valA: OPq, rrmovq
valC: irmovq, rmmovq, mrmvoq
-8: pushq,  call
+8: popq, ret

#### srcB
Parameters: rB, icode
rsp: pushq, popq, call, ret
rb: OPq, rmmovq, mrmovq
R_NONE: jmp, halt, nop
