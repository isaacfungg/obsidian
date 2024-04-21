***
#### Learning Goals
* Know the number of bits in a byte and the number of bytes in common integer types
* Determine whether an address is aligned to a given size
* Translate between integers and values stored in memory for both big-and- little-endian machines
* Evaluate and write Java expressions using bitwise operations (&, |, <<. >>, >>>)
* Determine when sign extension is unwanted and eliminate it in Java
* Evaluate and write C expressions that include type casting and the addressing operations
* Translate integer values by hand between binary and hexadecimal, subtract hexadecimal numbers and convert small numbers between binary and decimal

#### Memory
`Naming`
* Unit of addressing is a `byte` (8 bits)
* Every byte of memory has a unique address

`Access`
* Many things are too big to fit in a single byte
* Unsigned numbers > 255, signed numbers < -128 or > 127, most instructions
* CPU accesses memory in contiguous, power-of-two-size chunks of bytes
* Address of a chunk is address of its first byte

#### Storing
`Big Endian`
* Start from the "Big end"
* The first byte is the most significant one
* Used in old IBM servers, network connections

`Little Endian`
* Start from the "Little end"
* The first byte is the least significant one
* Used in most Intel-based systems

#### Address Alignment
* Address whose numeric value is a multiple of the object size
* You can fit two shorts inside an int
* Some CPUs don't support misaligned addresses
* Memory is organized internally into chunks (blocks)
* Every memory access requires accessing a whole block

#### Changing Data Types
