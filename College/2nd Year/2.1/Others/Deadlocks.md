### DEADLOCK IN OPERATING SYSTEMS

In operating systems, a deadlock is a critical situation where a set of processes is blocked because each process is holding a resource and waiting for another resource acquired by some other process. This situation creates a standstill, much like two trains coming towards each other on the same track with only one track available.

#### Examples of Deadlock:

1. **Two Tape Drives:**
   - **Scenario:**
     - The system has two tape drives.
     - Processes P1 and P2 each hold one tape drive and need another one.
   
2. **Semaphores A and B:**
   - **Scenario:**
     - Semaphores A and B, initialized to 1.
     - P0 executes wait(A) and preempts.
     - P1 executes wait(B).
     - Now P0 and P1 enter a deadlock.

3. **Space Allocation:**
   - **Scenario:**
     - The space available for allocation is 200KB.
     - Processes P0 and P1 engage in a deadlock while making requests for space.

#### Necessary Conditions for Deadlock:

1. **Mutual Exclusion:**
   - Two or more resources are non-shareable, meaning only one process can use a resource at a time.

2. **Hold and Wait:**
   - A process is holding at least one resource and waiting for additional resources.

3. **No Pre-emption:**
   - A resource cannot be taken from a process unless the process willingly releases the resource.

4. **Circular Wait:**
   - A set of processes is waiting for each other in a circular form, creating a cycle of dependencies.


### METHODS FOR HANDLING DEADLOCK

There are three main ways to handle deadlocks:

1. **Deadlock Prevention or Avoidance:**
	### **Prevention:**
     - The goal is to ensure that the system does not enter a deadlock state.
     - This involves negating one of the four necessary conditions for deadlock.
     - *Eliminate Mutual Exclusion:* While not possible for all resources, sharing resources wherever feasible can prevent deadlock.
     - *Solve Hold and Wait:* Allocate all required resources to a process before its execution begins, reducing the chance of deadlock but potentially leading to low device utilization and starvation.
     - *Allow Preemption:* Preempt resources from a process when they are required by higher-priority processes.
     - *Circular Wait Solution:* Assign numerical numbers to resources, and only allow processes to request resources in an increasing or decreasing order of numbering.
	### **Avoidance:**
     - Assumes all information about resources a process will need is known in advance.
     - Uses techniques like the Resource Allocation Graph (RAG) and Banker's Algorithm for visualization and decision-making.
     - *Resource Allocation Graph (RAG):* Represents the system state as a graph, including processes, assigned resources, and requested resources.
     - *Banker's Algorithm:* Tests all process requests for resources, ensuring that granting a request leaves the system in a safe state.

2. **Deadlock Detection and Recovery:**
   - If prevention or avoidance is not applied, this method involves two phases:
     - *Detection:* Examines the system state to check for a deadlock.
     - *Recovery:* Applies an algorithm to recover from the deadlock, such as process termination or resource preemption.

3. **Deadlock Ignorance:**
   - If deadlocks are infrequent, the system may be allowed to deadlock occasionally, and recovery is achieved through rebooting.
   - Often employed by operating systems like Windows and UNIX.

**SAFE STATE:**
- A state in which there is no deadlock is termed a safe state.
- Achievable if:
  - A process waiting for a resource may wait until the resource is released by another process that holds it.
  - All requested resources are allocated to the process.

