***
#### Processor Privilege Levels
**User mode**: How all "regular programs" run
**Kernel mode or supervisor mode**: How the OS run
**System Calls**: When a program wants to do something that it cannot do in user mode

###### POSIX File System API
**open**: takes a pathname and returns a file descriptor
**close**: takes an fd and frees up all the OS and library resource that have been allocated to it
**read**: Reads data from the file referenced by fd into a user-specified buffer
**write**: takes data from a buffer and writes it to the file referenced by fd

#### File Descriptors
