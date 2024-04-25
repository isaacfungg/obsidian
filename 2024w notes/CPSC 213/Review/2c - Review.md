***
#### Synchronization
* Threads were invented to
	* Express **parallelism**: Do things at the same time on different processors
	* Manage **asynchrony**: Do something else while waiting

#### The Importance of Mutual Exclusion
* `Shared Data`
	* Data structure that could be accessed by multiple threads
* `Critical Sections`
	* Sections of code that access **shared data**
* `Race Condition`
	* Simultaneous access to critical section by multiple threads
* `Mutual Exclusion`
	* A mechanism implemented in software to ensure **critical sections** are executed by one thread at a time

#### Mutual Exclusion Using Locks
* Lock semantics
	* A lock is either held by a thread or available
	* At most one thread can hold a lock at a time
* Lock Operations
	* `Lock`: Aquire lock, wait if necessary
	* `Unlock`: Release lock; if another thread is waiting allow it to run

#### Spinlocks
`Spinlock`
* Lock where waiter spins, looping on memory read until lock is acquired