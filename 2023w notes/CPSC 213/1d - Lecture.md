***
#### Index vs. Pointer Arithmetic
```c
# Copying an array using array syntax:
void intcpy(int *s, int *d, int n) {
	for (int i = 0; i < n; i++) {
		d[i] = s[i];
	}
}

# Copying an array using pointer arithmetic
void intcpy(int *s, int *d, int n) {
	while (n--) 
		*d++ = *s++;
}
```

#### Control Flow in the Machine
**Program Counter (PC)**
* Special CPU register that stores address of next instruction to execute

For sequential instructions, PC is updated in the fetch stage 
* Incremented by 2 or 6 depending on instruction size

So to implement a goto, all we need is to change the PC

Options for evaluating condition
* Unconditional (always jump)
* Conditional based on a register value
* Conditional based on result of last ALU instruction

#### Jump Instruction Size
**Problem**: memory addresses are big
* So, instructions that go to a specific address must be big
* Control-flow instructions are common

Jumps usually move a short distance (forward or backward)
* e.g. loops, if statements

**Solution**: Relative addressing
* Instead of specifying the destination address, specify the offset from current location in code
	* Use current value of PC (address of next instruction) as base address
	* Remember PC has already been updated in fetch
* Offset must be a signed number (can jump backward)
* Jumps using relative address are called **branches**
* Assembly still specifies actual address/label
* Converted to offset by assembler


#### New ISA Instructions
So we need the following instructions:
* At least one absolute jump
* At least one PC-relative jump (branch)
* Some form of conditional jumps
	* Make these relative
```r
# branch
br a

# branch if equal to 0
beq rc, a

# branch if greater than 0
bgt rc, a

# jump
j a
```