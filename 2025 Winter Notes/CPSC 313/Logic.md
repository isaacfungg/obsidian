***
Notes:
**`pushq` / `call` (decrement):*
1. **ALU:** computes `RSP - 8`.
2. **Memory:** write to `M[RSP - 8]`.
3. **Write-back:** update `RSP = RSP - 8`.

**`popq` / `ret` (increment):**
1. **ALU:** computes `RSP + 8`.
2. **Memory:** read from `M[RSP]` (old RSP).
3. **Write-back:** update `RSP = RSP + 8`.
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

#### AluB
0: rrmovq, irmovq
valB: pushq, popq, call, ret, rmmovq, mrmovq, opq

#### dstE
rsp: ret, call, push, pop
rB: rrmovq, irmovq, opq

#### dstM
rA: mrmovq, popq

#### memCntrl
4 (write): call, pushq, rmmovq
2 (read): ret, popq, mrmovq
