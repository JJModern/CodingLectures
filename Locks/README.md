Locks, MUTEXs, Semaphores

Circular Key Space

only one server is responsible for the data. Two others are back up.
	Maximum can hold 1/3 of total capacity.

whispering

semaphore

mutex- mutual exclusion
	exclusive access to a single thread at a time
	-used to read from something. 
	- make a sensitive change to a data. 

lock the mutex
	- log / variable that locks the request. If the request is granted things are locked

	Then, check if the process is over. If it is, then unlock it. 


* Lock: Before accessing a shared resource, a thread or process will attempt to "lock" the mutex. If the mutex is already locked by another thread, the current thread will block (i.e., wait) until the mutex is available.
    * operating system grants you the lock
* 		Access Resource: Once a thread has locked the mutex, it can safely access the shared resource, knowing that no other threads will be accessing it at the same time.
* 		Unlock: After the thread has finished accessing the shared resource, it "unlocks" the mutex, making it available for other threads to lock.
* 
* Recursive Mutex: Some mutex implementations allow a thread to lock a mutex it has already locked (i.e., it can lock the mutex recursively). When unlocking, the thread has to release the lock the same number of times it acquired it.
* 
* Deadlocks: Care must be taken when using multiple mutexes. If two threads each lock a different mutex and then try to lock the other mutex, a deadlock can occur where each thread waits indefinitely for the other to release its mutex.
* one has A, the other has B. Neither of us can get it. 

Mutex - makes things a bit slower because locking/unlocking takes time
	Atomic - doesn't use a log, therefore this is faster


MVCC



semaphore

semaphore is a synchronization primitive used in concurrent programming
	more than one thread to access a resource, up to a specified limit.

	process - hardware event

	hardware event
		-getting data from a database, Interrupts, Error Events, 

		when you get a hardware event, you have to do something about this.

	This hardware event is not connected to a specific process. 

* 		P (proberen or "try" in Dutch) / Wait / Acquire: This operation decrecreases the semaphore's value. If the result is non-negative, the thread continues. Otherwise, the thread is blocked and put in a queue.
* 		V (verhogen or "increase" in Dutch) / Signal / Release: This operation increases the semaphore's value. If there are threads waiting in the queue due to a previous P operation that blocked them, one or more of them are unblocked and resumed.

	4 processes (not just one for mutex) 
	
increase - the number of semaphores (value) increases with the number of processes 	increases

release - goes up.

In parallel computing 

One computer - many processes
	-what limits me?
		processing power, memory, network

Multiple computers - they need to talk to each other
	what limits me?
		network

	how to partition task so that it is efficient
		limit the number of messages between computers.

Single Instruction Multiple Data 
Accelerators:
	you have a lot of threads doing the same task at the same time. 

	If control flow — try to avoid this.

	you will have half of the processes not working. 

