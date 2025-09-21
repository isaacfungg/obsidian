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

#### nextPC
Parameters: valC, valM, valP, cond, icode
valM: ret
valP: halt, nop, rrmovq, irmovq, rrmovq, mrmovq, opq, pushq, popq, jxx
valC: jxx, call
#### Addr
Parameters: valB, valE, icode
valE: pushq, rmmovq, mrmovq, call
valB: popq, ret

#### Data
valA: rmmovq, pushq
valP: call
