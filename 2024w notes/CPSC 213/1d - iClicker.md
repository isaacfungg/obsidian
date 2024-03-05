#### 1d.1
```c
# Which of the following loops can we implement with our existing ISA?
# (assume n is a value provided by the user)

# 1
for (int i = 0; i < 42; i++)

# 2
for (int i = 42, i > 0; i--)

# 3
for (int i = 0; i < n; i++) 

# 4 
for (int i = 42; i > n; i--)

# 1 and 2
```



#### 1d.2
```r
# Convert the bgt instruction to machine code:
.pos 0x10
	bgt r0, L1
.pos 0x20
L1: halt

# pc = 0x12
# offset = 0x20 - 0x12 = 14 bytes
# p = 14 / 2 = 7
# 0xa0 0x07
```

#### 1d.3
```r
# Convert the br instruction to its machine code
loop:   mov r0, r5
		add r4, r5
		beq r5, end_loop
		inc r0
		br loop
```
