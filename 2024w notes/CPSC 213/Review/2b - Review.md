***
#### The Process
`Thread`
* A single stream of **synchronous execution** of a program
* Can be **stopped** and **resumed**
	* Stopped when waiting for an event
	* Resumed when the event fires
* Can **co-exist with other threads** sharing a single CPU

#### Thread Operations - Block and Unblock
* Blocking a thread
	* Save current thread's state
	* Thread cannot be rescheduled until explicitly unblocked
* Unblocking a thread
	* Move the thread from its queue of blocked threads into the runnable queue

#### Thread Operations - Join
* What happens when a thread finishes
	* Some other thread may want its output
	* We need to keep its information
* Joining with a thread
	* **Block current thread** until a target thread completes
	* Can obtain the return value of the target thread

#### Thread Operations - Detach
