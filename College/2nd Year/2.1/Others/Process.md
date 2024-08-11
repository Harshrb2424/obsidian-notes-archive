### Process Concepts and Scheduling

The term "process" was first used by the designers of the Multics system in the 1960s. A process is a program in execution, and process execution must progress sequentially. Processes exist for a limited span of time.

Two or more processes could be executing the same program, each using their data and resources. The process memory is divided into four sections for efficient operation:

- **Text:** Composed of integrated program code, which is read from fixed storage when the program is launched.
- **Data:** Made up of global and static variables, distributed and executed before the main action.
- **Heap:** Used for flexible or dynamic memory allocation and managed by calls to new, delete, malloc, free, etc.
- **Stack:** Used for local variables, with space reserved for local variables when announced.

### Process State

When a process executes, it changes state. The process state is defined as the current activity of the process, and it contains five states. Each process is one of the following states:

- **New:** The process is being created.
- **Running:** Instructions are being executed.
- **Waiting:** The process is waiting for some event to occur.
- **Ready:** The process is waiting to be assigned to a processor.
- **Terminated:** The process has finished execution.

**Diagram of Process State**

### Dispatching

The assignment of the CPU to the first process on the ready list is called dispatching, and it's performed by a system entity called the Dispatcher.

### Process Control Block (PCB)

The manifestation of a process in the operating system is a PCB or Process descriptor. Each process contains a PCB, which is a data structure containing essential information about the process, including:

- Unique identification of the process.
- A pointer to the process's parent.
- Process state.
- Program counter.
- CPU registers.
- Memory management information.
- Accounting information.
- Pointer to another PCB used for maintaining the scheduling list.
- I/O status information.
- List of I/O devices allocated to this process and a list of open files, and more.

### CPU Switch From Process to Process

### Process Scheduling Queues

Scheduling is the process of deciding which process to execute and when. The objective of multi-programming is to have some process running at all times to maximize CPU utilization. In time-sharing systems, the CPU is switched frequently to allow users to interact with programs while they are running.

**Scheduling Queues:**

1. **Job Queue:** When processes enter the system, they are placed in a job queue, consisting of all processes in the system.
2. **Ready Queue:** This queue contains all processes residing in main memory, ready and waiting to execute. It is typically stored as a linked list.
3. **Device Queues:** Each I/O device has its own queue, consisting of processes waiting for that device.

### Representation of Process Scheduling

A new process is initially put in the ready queue and waits there until it is selected for execution. Once a process is allocated CPU time, several events may occur:

- A process may issue an I/O request and be placed in an I/O queue.
- A process may create a new process.
- The process may be removed forcibly from the CPU due to an interrupt and put back in the ready queue.
- When a process terminates, it is removed from all queues, and the PCB and its resources are deallocated.

### Schedulers

A process migrates between various scheduling queues throughout its lifetime. The operating system must select processes for scheduling, and this selection process is carried out by a scheduler. There are different types of schedulers:

**Long-term scheduler (or job scheduler):**
- Selects processes from a pool and loads them into memory for execution.
- May take a long time to decide.
- Executes less frequently.
- Controls the degree of multiprogramming.

**Short-term scheduler (or CPU scheduler):**
- Selects which process should be ready to execute and allocates the CPU.
- Must select a new process for the CPU frequently.
- Executed at least once every 100 milliseconds.
- Must be fast to avoid wasting CPU time on scheduling work.

**Medium-term scheduler:**
- Introduced in some operating systems using swapping.
- Removes processes from memory to reduce multiprogramming.
- Processes can be reintroduced into main memory later to continue execution.
- This scheme is called "Swapping."
- Improves the process mix (I/O and CPU) when main memory is unavailable.

The long-term scheduler should make a careful selection, as it has a longer interval between executions. It can afford to take more time to select a process for execution. The scheduler needs to consider the mix of I/O-bound and CPU-bound processes:

- An I/O-bound process spends more time doing I/O than computation.
- A CPU-bound process spends most of the time doing computation.
- The long-term scheduler should aim for a good mix of I/O-bound and CPU-bound processes.
- Having all processes I/O-bound will result in an empty ready queue.
- Having all processes CPU-bound will result in an empty I/O queue, unused devices, and an unbalanced system.
- The best performance is achieved through the right combination of CPU-bound and I/O-bound processes.

### Context Switch

- A context switch is the task of switching the CPU to another process by saving the state of the old process and loading the saved state for the new process.
- During a context switch, the kernel saves the context of the old process in its PCB (Process Control Block) and loads the saved context of the new process scheduled to run.
- Context-switch time is considered overhead, as the system does no useful work while switching.
- The time taken for a context switch is highly dependent on hardware support and can typically range from 1 to 1000 microseconds.

### Methods for Logical Implementation of a Link

#### Direct Communication

- In direct communication, each process must explicitly name each other to communicate.
  - `Send(P, message)` sends a message to process P.
  - `Receive(Q, message)` receives a message from process Q.
- Links are established automatically, and each link is associated with exactly one pair of communicating processes.
- A link may be unidirectional or bi-directional, exhibiting both symmetry and asymmetry in addressing.
  - Symmetry: Both the sender and receiver processes must name each other to communicate.
  - Asymmetry: Only the sender names the recipient; the recipient is not required to name the sender.
- Send and receive primitives for direct communication:
  - `Send(P, message)` sends a message to process P.
  - `Receive(id, message)` receives a message from any process.
- Disadvantage of direct communication: Changing the name of a process creates problems.

#### Indirect Communication

- Indirect communication involves sending and receiving messages via mailboxes or ports.
- A mailbox is an object where processes can place and remove messages. Two processes can communicate only if they have a shared mailbox.
- Primitives for indirect communication:
  - `Send(A, message)` sends a message to mailbox A.
  - `Receive(A, message)` receives a message from mailbox A.
- A mailbox may be owned by a process or the OS.
- Mailbox sharing problem: Multiple processes share a mailbox, leading to the question of which process gets a message.
  - Solutions:
    - Allow a link to be associated with at most two processes.
    - Allow only one process at a time to execute a receive operation.
    - Allow the system to select arbitrarily the receiver and identify the receiver to the sender.

#### Synchronization

- Message passing can be either blocking or non-blocking.
  - Blocking is considered synchronous, while non-blocking is considered asynchronous.
- Send and receive primitives can be either blocking or non-blocking.
- Types of primitives:
  - **Blocking send**: The sending process is blocked until the message is received by the receiver.
  - **Non-blocking send**: The sending process sends the message and resumes operation.
  - **Blocking receive**: The receiver blocks until a message is available.
  - **Non-blocking receive**: The receiver receives either a valid message or a null.

#### Buffering

- A link has a capacity that determines the number of messages that can temporarily reside in it.
- A queue of messages is attached to the link and can be implemented in one of three ways:
  - **Zero capacity**: The link cannot have any messages; the sender must wait for the receiver.
  - **Bounded capacity**: It has a finite length of n messages; the sender must wait if the link is full.
  - **Unbounded capacity**: It has an infinite length; the sender never waits.

