***
**Condition Codes**
A collection of bits set by arithmetic and logical instructions
`ZF`: Zero-flag: The last ALU operation produced a 0
`SF`: Sign-flag: The last ALU operation produced a negative number
`OF`: Overflow-flag: The last ALU operation produced an overflow

**Program Counter (PC)**
Indicates the address of the next instruction to execute

**Memory**
* Byte-addressable storage array
* Words stored in Little Endian Order

**Simple Instructions
* Move (Reg -> Reg)
	* Instruction: RRMOVQ - %r8, %r9
* Move (Const -> Reg)
	* Instruction: IRMOVQ
* Move (Mem -> Reg)
	* Instruction: MRMOVQ
* Move (Reg -> Mem)
	* Instruction: RMMOVQ
	*