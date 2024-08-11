# OS Important Questions

## Multiple-Choice Questions:

1. To access the services of the operating system, the interface is provided by the ___________
   - [ ] a) Library 
   - [x] **b) System calls** 
   - [ ] c) Assembly instructions 
   - [ ] d) API

2. Network operating system runs on ___________
   - [ ] a) every system in the network 
   - [x] **b) server** 
   - [ ] c) both 
   - [ ] d) none

3. Which one of the following is not a real-time operating system?
   - [ ] a) RTLinux 
   - [x] **b) Palm OS** 
   - [ ] c) QNX 
   - [ ] d) VxWorks

4. Which of these doesn’t interrupt a running process?
   - [ ] a) Power failure 
   - [x] **b) Scheduler process** 
   - [ ] c) Timer 
   - [ ] d) A device

5. Which one of these statements about kernel-level threads and user-level threads is FALSE?
   - [ ] a) The context switch time is comparatively longer for the kernel-level threads, as compared to the ones for the user-level threads.
   - [ ] b) The user-level threads don’t require any support for hardware.
   - [ ] c) We can schedule the related kernel-level threads in a multi-processor system on different processors.
   - [x] **d) When one kernel-level thread is blocked, then all the related threads will be blocked.**

6. If a process fails, most operating systems write the error information to a ______
   - [ ] a) new file 
   - [ ] b) another running process 
   - [x] **c) log file** 
   - [ ] d) none

7. CPU scheduling is the basis of ___________
   - [x] **a) multiprogramming OS** 
   - [ ] b) larger memory-sized systems 
   - [ ] c) multiprocessor systems 
   - [ ] d) none of the mentioned

8. In a timeshare operating system, when the time slot assigned to a process is completed, the process switches from the current state to?
   - [ ] a) Suspended state 
   - [ ] b) Terminated state 
   - [x] **c) Ready state** 
   - [ ] d) Blocked state

9. Cascading termination refers to the termination of all child processes if the parent process terminates ______
   - [x] **a) Normally or abnormally** 
   - [ ] b) Abnormally 
   - [ ] c) Normally 
   - [ ] d) None of the mentioned

10. The FCFS algorithm is particularly troublesome for_______
   - [ ] a) operating systems 
   - [ ] b) multiprocessor systems 
   - [x] **c) time-sharing systems** 
   - [ ] d) multiprogramming systems

11. A deadlock avoidance algorithm dynamically examines the _ _ to ensure that a circular wait condition can never exist.
    - [ ] a) operating system 
    - [ ] b) resources 
    - [ ] c) system storage state 
    - [x] **d) resource allocation state**

12. Process synchronization can be done on
    - [x] **a) Hardware level** 
    - [x] **b) Software Level** 
    - [ ] c) Other 
    - [ ] d) None

13. Out of the following, which one needs a device driver?
    - [ ] a) Main memory 
    - [x] **b) Disk** 
    - [ ] c) Register 
    - [ ] d) Cache

14. What is the main function of the command interpreter?
    - [ ] a) to provide the interface between the API and application program
    - [ ] b) to handle the files in the operating system
    - [x] **c) to get and execute the next user-specified command**
    - [ ] d) none of the mentioned

15. In Unix, which system call creates the new process?
    - [ ] a) create 
    - [x] **b) fork** 
    - [ ] c) new 
    - [ ] d) none of the mentioned

16. The total time taken for switching between the user and the kernel modes of execution is t1, while the total time taken for switching between two processes is t2. Out of the following, which one is TRUE?
    - [x] **a) t2 > t1** 
    - [ ] b) t2 = t1 
    - [ ] c) t2 < t1 
    - [ ] d) We cannot say anything about the relation between t2 and t1

17. Process synchronization can be done on
    - [x] **a) Hardware level** 
    - [x] **b) Software Level** 
    - [ ] c) Other 
    - [ ] d) None

18. Which of the following is a synchronization tool
    - [ ] a) Thread 
    - [ ] b) Pipe 
    - [x] **c) Semaphore** 
    - [ ] d) Sockets

19. An **memory storage system** can be designed to be either volatile or non-volatile.

20. Multiprocessor is also called as **Parallel Processor or multicore processor**.

21.  **Load balancing** is usually used to provide high availability service.

22. Applications must be written specifically to take advantage of the cluster by using **clustering** technique.

23. No. of processes completed per unit time is known as **throughput**.

24. Entry of all the PCBS of the current process is in [**Process Table**](https://www.sanfoundry.com/operating-system-mcqs-process-control-block/).

25. The context of the process in PCB of a process doesn’t contain  **actual data and** [**context switch time**](https://www.sarthaks.com/2416495/the-context-of-a-process-in-the-pcb-of-a-process-does-not-contain).

26. A Parent process calling **wait()** system call will be suspended until the children process terminates.

27. The wait function **decreases** the semaphore value.

28. Semaphores are mostly used to implement **Critical Section, Solve the problem of race condition, mutual exclusion and process Synchronization**.

29. The link between processes P and Q to send and receive messages is called **communication link**.

30. Bounded capacity and Unbounded capacity queues are referred to as [**Automatic buffering**](https://www.sarthaks.com/2416621/bounded-capacity-and-unbounded-capacity-queues-are-referred-to-as).

31. An **operating system** halts the execution of the user to prevent errors and improper use of the computer.

32. The interaction between the user and hardware is called **The operating system (OS)**.

33. The operating System is one program running at all times on the computer usually called as **the kernel**.

34. The occurrence of an event is usually signaled by an **Interrupt** from either the hardware or the software.

35. General-purpose computers run most of their programs from rewritable memory called **random-access memory (RAM) [main memory]**.

36. **Time-sharing operating system** requires an interactive computer system that provides direct communication between the user and the system.

37. In UNIX each process is identified by its **Process Identifier (PID)**.

## PART – B

# **1. What are the various components of the operating system structure and explain with a neat sketch.**


1. **Kernel:**
   - The brain of the operating system.
   - Manages tasks like running programs, handling memory, and talking to devices.

2. **Process Management:**
   - Takes care of running programs.
   - Decides which program gets to use the computer's resources.

3. **Memory Management:**
   - Deals with computer memory (RAM).
   - Makes sure programs have enough space to run.

4. **File System Management:**
   - Organizes and keeps track of files.
   - Handles creating, deleting, and finding files.

5. **Device Drivers:**
   - Helps the operating system talk to hardware like printers or keyboards.
   - Manages input and output operations.

6. **Security and Protection:**
   - Keeps the system safe.
   - Controls who can access the computer and what they can do.

7. **User Interface:**
   - How you interact with the computer.
   - Can be graphical (with icons and windows) or text-based (using commands).

8. **Networking:**
   - Lets computers talk to each other.
   - Handles things like internet connections and data transfer.

9. **System Libraries:**
   - Pre-made tools for programs.
   - Helps programs do common tasks without starting from scratch.
![[Pasted image 20231127085123.png]]
# **2. Explain distributed OS and time-sharing OS in detail.**
![[Distributed Operating System 1]]
![[Time-Sharing Operating Systems]]
# **3. Consider 3 processes P1, P2, and P3, which require 5, 7, and 4 time units and arrive at times 0, 1, and 3.** 
   **Draw the Gantt chart, process completion sequence, and average waiting time for.** 
   **i) Round-robin scheduling with CPU quantum of 2 time units.** 
   **ii) FCFS**

### Round-Robin Scheduling
**Gantt chart**

| Time   | P1  | P2  | P3  | Burst Time P1  | Burst Time P2  | Burst Time P3  |
|--------|-----|-----|-----|-----|-----|-----|
|   0    |     |     |     |  5  |  7  |  4  |
|   0-2  | P1  |     |     |  3  |  7  |  4  |
|   2-4  |     | P2  |     |  3  |  5  |  4  |
|   4-6  | P1  |     |     |  1  |  5  |  4  |
|   6-8  |     |     | P3  |  1  |  5  |  2  |
|   8-10 |     | P2  |     |  1  |  3  |  2  |
| 10-11  | P1  |     |     |  0  |  3  |  2  |
| 11-13  |     |     | P3  |  -  |  3  |  0  |
| 13-15  |     | P2  |     |  -  |  1  |  -  |
| 15-16  |     | P2  |     |  -  |  0  |  -  |
$\text{Waiting Time} = \text{Completion Time} - \text{Arrival Time} - \text{Burst Time}$

| Process | Arrival | Burst Time | Completion Time | Waiting Time |
|---------|---------|------------|------------------|--------------|
|   P1    |    0    |      5     |        11        |      6       |
|   P2    |    1    |      7     |        13        |      5       |
|   P3    |    3    |      4     |        16        |      9       |

Now, let's calculate the average waiting time:

$\text{Average Waiting Time} = \frac{\text{Sum of Waiting Times}}{\text{Number of Processes}}$

$\text{Average Waiting Time} = \frac{6 + 5 + 9}{3} = \frac{20}{3}$

**Average Waiting Time (RR):** $\frac{20}{3}$ 

### FCFS (First-Come, First-Served) Scheduling
**Gantt chart**

| Time   | P1  | P2  | P3  |
|--------|-----|-----|-----|
|   0-5  | P1  |     |     |
|   5-12 |     | P2  |     |
| 12-16  |     |     | P3  |


$\text{Waiting Time} = \text{Completion Time} - \text{Arrival Time} - \text{Burst Time}$

| Process | Arrival | Burst Time | Completion Time | Waiting Time |
|---------|---------|------------|------------------|--------------|
|   P1    |    0    |      5     |        5         |      0       |
|   P2    |    1    |      7     |        12        |      4       |
|   P3    |    3    |      4     |        16        |      9       |

Now, let's calculate the average waiting time:

$\text{Average Waiting Time} = \frac{\text{Sum of Waiting Times}}{\text{Number of Processes}}$

$\text{Average Waiting Time} = \frac{0 + 4 + 9}{3} = \frac{13}{3}$

**Average Waiting Time (FCFS):**  $\frac{13}{3}$ time units

# **4. What is Deadlock? List the condition that leads to deadlock. How deadlock can be prevented.**
![[Deadlocks#DEADLOCK IN OPERATING SYSTEMS]]

# **5. Write short notes on the process. Explain various states of the process with a neat diagram.**
![[Process#Process Concepts and Scheduling]]
![[Process#Process State]]
![[Pasted image 20231126192324.png]]
# **6. Explain the concepts of semaphores and critical section problems?**
## CRITICAL SECTION PROBLEM

A critical section is a code segment accessible by only one process at a time. It contains shared variables that need synchronization to maintain data consistency. The critical section problem involves designing a way for cooperative processes to access shared resources without creating data inconsistencies.

## Entry Section
In the entry section, a process requests entry into the critical section.

Any solution to the critical section problem must satisfy three requirements:

1. **Mutual Exclusion:**
   - If a process is executing in its critical section, no other process is allowed to execute in the critical section.

2. **Progress:**
   - If no process is executing in the critical section, and other processes are waiting outside the critical section, only those processes not executing in their remainder section can participate in deciding who will enter the critical section next. The selection can't be postponed indefinitely.

3. **Bounded Waiting:**
   - A bound must exist on the number of times other processes are allowed to enter their critical sections after a process has made a request and before that request is granted.

## SEMAPHORES

Semaphore is a hardware solution given to the critical section problem, represented as a normal integer. It cannot be negative, with the minimum value being zero. Semaphores typically have two operations:

### Semaphore Operations:

1. **Wait ( ) Operation:**
   - If the Semaphore value is greater than zero, the process can enter the critical section.
   - If the Semaphore value is zero, the process has to wait.
   - The Semaphore value is reduced when the process exits the critical section.
![[Pasted image 20231127085536.png]]
2. **Signal ( ) Operation:**
   - Executed only when the process exits the critical section.
   - The Semaphore value cannot be incremented before the process exits the critical section.
![[Pasted image 20231127085543.png]]

# **7. Write about deadlock conditions and the banker's algorithm in detail.**
![[Deadlocks#Necessary Conditions for Deadlock]]

## BANKER'S ALGORITHM
![[BANKER'S ALGORITHM]]
# 8. Write short notes on PCB and context switching?

# 9. Explain about a race condition? How to avoid a race condition? Explain any two methods to avoid a race condition.
![[RACE CONDITION]]
# **10. List out the types of operating systems and explain batch OS and Real-time sharing OS in brief.**
![[Operating System - Introduction and Structures 1#**Types of Operating Systems **]]
![[Batch Operating System 1]]
![[Real-Time System (RTOS)]]

# **11. What is a System call? Explain the various types of system calls provided by an operating system.**
![[System Calls#System Calls]]

![[System Calls#Types of System Calls]]
# **12. Consider the following set of processes, with the length of the CPU burst given in milliseconds:** 

   | Process | Burst Time | Priority |
   | ------- | ---------- | -------- |
   | P1      | 27         | 5        |
   | P2      | 12         | 1        |
   | P3      | 37         | 2        |
   | P4      | 19         | 4        |
   | P5      | 10         | 3        |
The processes are assumed to have arrived in the order P1, P2, P3, P4, P5 all at time 0. 
Draw the Gantt charts that illustrate the execution of these processes using the following scheduling algorithms: FCFS, 
SJF, and Priority. Also, determine the average waiting time and average turnaround time for each of the algorithms.


### FCFS (First-Come, First-Served) Scheduling:

Gantt Chart:

| P1 | P2 | P3 | P4 | P5 |
|----|----|----|----|----|
| 0  | 27 | 39 | 76 | 95 |

| Process | Burst Time | Arrival Time | Completion Time | Turnaround Time | Waiting Time |
|---------|------------|--------------|------------------|------------------|--------------|
|   P1    |     27     |      0       |        27        |        27        |       0      |
|   P2    |     12     |      0       |        39        |        39        |      27      |
|   P3    |     37     |      0       |        76        |        76        |      39      |
|   P4    |     19     |      0       |        95        |        95        |      76      |
|   P5    |     10     |      0       |       105        |       105        |      95      |

Average Waiting Time:
$\text{Average Waiting Time} = \frac{0 + 27 + 39 + 76 + 95}{5} = \frac{237}{5} = 47.4$

Average Turnaround Time:
$\text{Average Turnaround Time} = \frac{105 + 12 + 49 + 78 + 59}{5} = \frac{303}{5} = 60.6$

### SJF (Shortest Job First) Scheduling:

Gantt Chart:

| P2 | P5 | P4 | P3 | P1 |
|----|----|----|----|----|
| 0  | 12 | 22 | 61 | 98 |

| Process | Burst Time | Arrival Time | Completion Time | Turnaround Time | Waiting Time |
|---------|------------|--------------|------------------|------------------|--------------|
|   P5    |     10     |      0       |        10        |        10        |       0      |
|   P2    |     12     |      0       |        22        |        22        |      10      |
|   P4    |     19     |      0       |        41        |        41        |      22      |
|   P1    |     27     |      0       |        68        |        68        |      41      |
|   P3    |     37     |      0       |       105        |       105        |      68      |


$\text{Average Waiting Time} = \frac{\text{Sum of Waiting Times}}{\text{Number of Processes}}$

$\text{Average Waiting Time} = \frac{0 + 10 + 22 + 41 + 68}{5} = \frac{141}{5} = 28.2$

$\text{Average Turnaround Time} = \frac{\text{Sum of Turnaround Times}}{\text{Number of Processes}}$
$\text{Average Turnaround Time} = \frac{10 + 22 + 41 + 68 + 105}{5} = \frac{246}{5} = 49.2$

So, the Average Waiting Time is 28.2 time units, and the Average Turnaround Time is 49.2 time units for SJF without priority.

### Priority Scheduling:

Assuming lower priority numbers indicate higher priority:

Gantt Chart:

| P2 | P3 | P5 | P4 | P1 |
|----|----|----|----|----|
| 0  | 12 | 49 | 88 | 105|

1. **P2 (Priority 1):**
   - Completion Time: 12 (Burst Time)
   - Turnaround Time: 12 - 0 = 12
   - Waiting Time: 12 - 12 = 0

2. **P3 (Priority 2):**
   - Completion Time: 12 + 37 = 49
   - Turnaround Time: 49 - 0 = 49
   - Waiting Time: 49 - 37 = 12

3. **P5 (Priority 3):**
   - Completion Time: 49 + 10 = 59
   - Turnaround Time: 59 - 0 = 59
   - Waiting Time: 59 - 10 = 49

4. **P4 (Priority 4):**
   - Completion Time: 59 + 19 = 78
   - Turnaround Time: 78 - 0 = 78
   - Waiting Time: 78 - 19 = 59

5. **P1 (Priority 5):**
   - Completion Time: 78 + 27 = 105
   - Turnaround Time: 105 - 0 = 105
   - Waiting Time: 105 - 27 = 78

| Process | Burst Time | Priority | Arrival Time | Completion Time | Turnaround Time | Waiting Time |
|---------|------------|----------|--------------|------------------|------------------|--------------|
|   P1    |     27     |    5     |      0       |       105        |       105        |      78      |
|   P2    |     12     |    1     |      0       |       12         |        12        |      0       |
|   P3    |     37     |    2     |      0       |       49         |        49        |      12      |
|   P4    |     19     |    4     |      0       |       78         |        78        |      59      |
|   P5    |     10     |    3     |      0       |       59         |        59        |      49      |

$\text{Average Waiting Time} = \frac{\text{Sum of Waiting Times}}{\text{Number of Processes}}$
$\text{Average Turnaround Time} = \frac{\text{Sum of Turnaround Times}}{\text{Number of Processes}}$

$\text{Average Waiting Time} = \frac{78 + 0 + 12 + 59 + 49}{5} = \frac{198}{5} = 39.6$
$\text{Average Turnaround Time} = \frac{105 + 12 + 49 + 78 + 59}{5} = \frac{303}{5} = 60.6$

So, the Average Waiting Time is $39.6$ time units, and the Average Turnaround Time is $60.6$ time units for the provided SJF table with priority.