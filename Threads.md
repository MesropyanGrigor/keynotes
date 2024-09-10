A thread is a basic unit of CPU utilization

A thread has ID, program counter, register set, stack

Benefit of threads are responsiveness(interactivity), resource sharing, less costly compared with processes, utilization of multiprocessor architectures

There are two threads - user and kernel

user threads - Managed without kernel support, thread management is done in the user level by library
kernel threads - supported and managed directly by the operating system

exists relationship between user and kernel threads

There are the following relationships: Many-to-One, One-to-One, Many-to-many models

One-to-One model, when we will create a user thread, it will create a one kernel threads, it will costly 


- fork(): System call is used to duplicate the process
- exec(): System call will replace the entire process

Some Unix systems have chosen to have two versions of fork(), one that duplicates all threads and
another that duplicates only the thread that invoked the fork() system call.

If multiple threads are concurrently searching through a database and one thread
returns the result, the remaining threads might be canceled

**Cancellation of a target thread may occur in two different scenarios**

1. Asynchronous cancellation: One thread immediately terminates the target thread (ex: If multiple threads are concurrently searching through a database and one thread returns the result, the remaining threads might be canceled)
2. Deffered cancelation: The target thread periodically checks whether it should 
    terminate, allowing it an opportunity to terminate itself in an orderly fashion