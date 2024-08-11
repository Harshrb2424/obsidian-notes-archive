#year2 #sem3 #2-1-OS #theorySubject
## **Overview**
#### [[UNIT I Introduction to Operating Systems and Process Concepts]]

- Operating System - Introduction and Structures
	- Simple Batch
	- Multiprogrammed 
	- Time-shared 
	- Personal Computer 
	- Parallel
	- Distributed Systems 
	- Real-Time Systems 

- System Components and Operating System Services
	- Operating System Services
	- System Calls
		- System calls facilitate communication between user programs and the operating system.
		- They can be written in assembly language or high-level languages such as C, C++, or Pascal.
		- System calls are predefined functions invoked by the operating system to fulfill user program requests.
		- They serve as a method for programs to request services from the kernel of the operating system.
		- System calls range from simple operations (e.g., retrieving system date and time) to complex tasks (e.g., connecting to network devices).
		- Modern operating systems utilize distinct kernel threads for each system call to prevent bottlenecks and handle multiple calls simultaneously.
		- The Application Program Interface (API) acts as a link between the operating system's functions and user programs, enabling the request for OS services.
		- System calls are necessary for any program requiring access to system resources and serve as the exclusive means to interact with the kernel.

- Process
	- Process Concepts and Scheduling 
		- structure
		- process status
		- scheduling queues
		- scheduling types
	- Operations on Processes
		- Process creation
			- fork
			- exec
		- Process termination
			- wait
			- exit
	- Cooperating Processes
		- memory sharing
		- message passing
	- Threads

#### UNIT II: CPU Scheduling, System Call Interface, and Deadlocks

- [[CPU Scheduling]]
	- [[Scheduling Criteria]]
	- [[Scheduling Algorithms]]
	- [[Multiple-Processor Scheduling]]

- [[System Call Interface for Process Management]]
	- fork
	- exit
	- wait
	- waitpid
	- exec

- [[Deadlocks]]
	- System Model
	- Deadlocks Characterization [[Deadlocks#Necessary Conditions for Deadlock]]
	- Methods for Handling Deadlocks [[Deadlocks#METHODS FOR HANDLING DEADLOCK]]
		- Deadlock Prevention 
		- Deadlock Avoidance
		- Deadlock Detection and Recovery
	- [[BANKER'S ALGORITHM]]

#### [[UNIT III Process Management, Synchronization, and Interprocess Communication]]

- Process Management and Synchronization

	- The Critical Section Problem
	- Synchronization Hardware
	- Semaphores and Classical Problems of Synchronization
	- Critical Regions
	- Monitors
- [[RACE CONDITION]]

- Interprocess Communication Mechanisms

	- IPC between Processes on a Single Computer System
	- IPC between Processes on Different Systems
	- Using Pipes, FIFOs, Message Queues, Shared Memory

#### [[UNIT IV Memory Management and Virtual Memory]]

- Memory Management

	- Logical versus Physical Address Space
		- Static, dynamic loading and linking
			- routes, stub
	- Swapping
	- Contiguous Allocation
	- Paging
	- Segmentation
	- Segmentation with Paging

- Virtual Memory

	- Demand Paging
	- Page Replacement
	- Page Replacement Algorithms

#### [[UNIT V File System Interface, Operations, and Usage of System Calls]]

- File System Interface and Operations

	- Access Methods
	- Directory Structure
	- Protection
	- File System Structure
	- Allocation Methods
	- Free-Space Management

- Usage of System Calls

	- open
	- create
	- read
	- write
	- close
	- lseek
	- stat
	- ioctl


## **Lecture notes**
[OS U1 PDF](https://harshrb2424.github.io/Jntuh-R22-Notes/public/resources/2nd%20Year/OS-Unit1.pdf)
[OS U2 PDF](https://harshrb2424.github.io/Jntuh-R22-Notes/public/resources/2nd%20Year/OS-Unit2.pdf)
[OS U3 PDF](https://harshrb2424.github.io/Jntuh-R22-Notes/public/resources/2nd%20Year/OS-Unit3.pdf)
[OS U4 PDF](https://harshrb2424.github.io/Jntuh-R22-Notes/public/resources/2nd%20Year/OS-Unit4.pdf)
[OS U5 PDF](https://harshrb2424.github.io/Jntuh-R22-Notes/public/resources/2nd%20Year/OS-Unit5.pdf)
## [[OS Assignments 1]]
[[OS Mid 1 1]]
[[OS mid 1 Bits 1]]
[[OS Mid 2 QnA]]