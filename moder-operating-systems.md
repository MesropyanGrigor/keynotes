## PROCESSES

- Processes are one of the oldest and most important abstractions that operating systems provide. They support the ability to have (pseudo) concurrent operation even when there is only one CPU available. They turn a single CPU into multiple virtual CPUs.


- This system call tells the operating system to create a new process and in- dicates, directly or indirectly, which program to run in it.
In UNIX, there is only one system call to create a new process: fork.

- A single Win32 function call, CreateProcess, handles both process creation and loading the correct program into the new process.

- In both UNIX and Windows systems, after a process is created, the parent and child have their own distinct address spaces. If either process changes a word in its address space, the change is not visible to the other process.

- Many algorithms have been devised to try to balance the competing demands of ef- ficiency for the system as a whole and fairness to individual processes.

- process scheduler, a part of the operating system, without the process even knowing about them.

- To implement the process model, the operating system maintains a table (an array of structures), called the process table, with one entry per process. (Some authors call these entries process control blocks.)


- The ability for the parallel entities to share an address space and all of its data among themselves. This ability is essential for certain applications, which is why having multiple processes (with their separate address spaces) will not work. A second argument for having threads is that since they are lighter weight than processes, they are easier (i.e., faster) to create and destroy than processes. In many systems, creating a thread goes 10–100 times faster than creating a process. When the number of threads needed changes dynamically and rapidly, this proper- ty is useful to have.

- Processes are used to group resources together; threads are the entities scheduled for execution on the CPU.

- The CPU switches rapidly back and forth among the threads, providing the illusion that the threads are running in parallel, albeit on a slower CPU than the real one. With three compute-bound threads in a process, the threads would appear to be running in parallel, each one on a CPU with one-third the speed of the real CPU.

- Since every thread can access every memory address within the process’ address space, one thread can read, write, or even wipe out another thread’s stack. There is no protection between threads because (1) it is impossible, and (2) it should not be necessary. Unlike different processes, which may be from different users and which may be hostile to one another, a process is always owned by a single user, who has presumably created multiple threads so that they can cooperate, not fight. In addition to sharing an address space, all the threads can share the same set of open files, child processes, alarms, and signals, an so on, as shown

| Per-process items | Per-thread items |
|:----------------  |-----------------|
| Address space     | Program counter Registers |
| Global variables  | Stack |
| Open files        | State |
| Child processes   |
| Pending alarms    |
| Signals and signal handlers Accounting information | 

**The first column lists some items shared by all threads in a process. The second one lists some items private to each thread.**



### Scheduling

The part of the operating system, which makes a choice which process to run next is called scheduler.
The algorithm is called scheduling algorithm.

Doing too many process swiyches per second can chew up a substantial amount of CPU time, so caution is advised


I/O in this sense is when a process enters the blocked state waiting for an external device to complete its work.



- **nonpreemptive** scheduling algorithm picks a process to run and then just lets it run it blocks
( either on I/O or waiting for another process) or voluntarily releases the CPU

- in contrast, a **preemptive** scheduling algorithm picks a process and lets it run for a maximum of some fixed time

All systems
    Fairness - giving each process a fair share of the CPU Policy enforcement - seeing that stated policy is carried out Balance - keeping all parts of the system busy
Batch systems
    Throughput - maximize jobs per hour
    Turnaround time - minimize time between submission and termination CPU utilization - keep the CPU busy all the time
Interactive systems
    Response time - respond to requests quickly Proportionality - meet users’ expectations
Real-time systems
    Meeting deadlines - avoid losing data
    Predictability - avoid quality degradation in multimedia systems

Some goals of the scheduling algorithm under different circumstances.

**Round-Robin Scheduling** - One of the oldest, simplest, fairest, and most widely used algorithms is round robin. Each process is assigned a time interval, called its quantum, during which it is allowed to run. If the process is still running at the end of the quantum, the CPU is preempted and given to another process. If the process has blocked or fin- ished before the quantum has elapsed, the CPU switching is done when the process blocks, of course. Round robin is easy to implement. 
<br>
In practice, round-robin scheduling and priority scheduling are most common. The only constraint is the absence of a clock to interrupt a thread that has run too long. Since threads cooperate, this is usually not an issue.






