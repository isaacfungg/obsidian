***
What is the difference between a list, set and tuple. Discuss tradeoffs
* List: Ordered collection, allows duplicates, mutable
* Set: Unordered collection, no duplicates, mutable, but elements must be immutable
* Tuple: Ordered collection, allows duplicates, immutable
Trade-offs
* List: Flexibility in modification but slower for searching elements and takes more memory
* Set: Fast for checking membership and eliminating duplicates but cannot have mutable items
* Tuple: Faster than lists for access, less memory use, but cannot be modified after creation

What is the definition of a mutex?
* A mutex is short for mutual exclusion and is a synchronization mechanism used to ensure only one thread can access s shared resource at a time, preventing race conditions.

What is a semaphore?
* Can control access to multiple instances of a resource, allowing several threads to access a set number of resources concurrently.

What is SQL injection and how do we avoid it?
* It is a security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.
* Solutions:
	* Limit privileges for users
	* Validate input 

TCP vs. UDP
* TCP
	* Connection-oriented protocol that ensures reliable, ordered, and error-checked delivery of a stream of bytes between applications.
	* It establishes a connection before data can be sent, guarantees the delivery of data
	* Uses for applications where reliability is crucial
* UDP
	* Connectionless protocol that sends messages without establishing a dedicated connection between the sending and receiving end
	* It does not guarantee delivery, order, or error checking, making it faster and more efficient for applications where speed is more critical than reliability.

Should you encrypt a file before compressing it?
* Yes, it i