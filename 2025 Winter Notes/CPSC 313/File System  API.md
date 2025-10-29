***
#### Processor Privilege Levels
* Two main modes:
	* User mode (regular programs)
	* Kernel/Supervisor mode (OS)

#### System Calls
* A mechanism that asks the kernel to perform the activity that cannot be done in user mode

#### POSIX File System API
* The file system APIs are implemented as library functions that invoke system calls
* Open
	* Takes a pathname and returns a file descriptor which you will use to access that file
	* Takes flag as input that a
* Close
	* Takes an fd and frees up all the OS and library resource that have been allocated to it
* Read
	* Reads data from the file referenced by fd into a user-specified buffer
* Write
	* Takes data from a buffer and writes it to the file referenced by fd

#### Disk Structure
* Platters: Circular disks coated with magnetic material
* Surfaces: Each platter has two surfaces for data storage
* Tracks: Concentric circles on each surface
* Sectors: Smallest addressable unit of storage on a track

### Disk Heads & Arm Assembly
* Each surface has a read/write head
* Heads move together on an arm to access different tracks