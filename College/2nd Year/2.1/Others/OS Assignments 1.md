#2-1-OS 
## Working
# *1. what are the various components of operating System Structure and explain with a neat sketch.*
![[Pasted image 20231107213652.png]]
The operating system (OS) structure is typically organized into several components, each playing a specific role in managing and coordinating various aspects of the computer system. Here are the main components of an operating system structure:

1. **Kernel:**
    - The kernel is the core of the operating system. It provides essential services for all other parts of the OS.
    - Manages system resources, such as CPU, memory, and I/O devices.
    - Handles system calls and manages processes.
2. **Process Management:**
    - Manages processes, which are instances of executing programs.
    - Includes process creation, scheduling, termination, and communication.
3. **Memory Management:**
    - Allocates and deallocates memory space as needed by different processes.
    - Implements virtual memory to allow efficient use of physical memory.
4. **File System:**
    - Manages files on storage devices like hard drives.
    - Provides a hierarchical structure for organizing and storing data.
    - Implements file access controls and permissions.
5. **I/O System:**
    - Manages input and output operations between the computer and its peripherals.
    - Includes device drivers and I/O controllers.
6. **Security and Protection:**
    - Enforces security policies to protect the system and its resources.
    - Controls access to files, directories, and other system resources.
7. **Networking:**
    - Manages network communication, allowing processes on different machines to communicate.
    - Implements network protocols and services.
8. **User Interface:**
    - Provides interfaces for user interaction with the system.
    - Can be a command-line interface (CLI) or a graphical user interface (GUI).
9. **Shell:**
    - The shell is the interface between the user and the operating system.
    - Interprets user commands and executes them by interacting with the kernel.
10. **Device Drivers:**
    - Acts as an interface between the operating system and hardware devices.
    - Allows the OS to communicate with various hardware components.

# *2. What is a system call? explain the various types of system calls provided by an Operating system.*
# System Calls

A system call is a fundamental interface that allows user programs to interact with the operating system. These calls enable user programs to request services from the operating system's kernel. System calls are essential for various operations, such as file handling, network communication, process management, and hardware access. Here are some key points about system calls:
1. **User-OS Interaction**
2. **Programming Languages**
3. **Kernel Interaction**
4. **Interaction Method**
5. **Request Mechanism**
6. **Execution Time**
### Example of System Calls
- **File Copy:** One common use of system calls is to copy the contents of one file to another.
- **Standard C Library:** A C program might invoke functions from the standard C library (e.g., `printf()`), which, in turn, call underlying system calls (e.g., `write()`).

### Situations Requiring System Calls
Several situations necessitate the use of system calls within an operating system:
1. **File Operations**
2. **Network Communication**
3. **Hardware Access**
4. **Process Management**
## Types of System Calls

There are commonly five types of system calls. These are as follows:

1. Process Control
2. File Management
3. Device Management
4. Information Maintenance
5. Communication

### Process Control
Process control is the system call that is used to direct the processes. Some process control examples include creating, loading, aborting, ending, executing, processing, terminating the process, etc.

### File Management
File management is a system call that is used to handle files. Some file management examples include creating files, deleting files, opening, closing, reading, writing, etc.

### Device Management
Device management is a system call that is used to deal with devices. Some examples of device management include reading devices, writing, getting device attributes, releasing devices, etc.

### Information Maintenance
Information maintenance is a system call that is used to maintain information. Some examples of information maintenance include getting system data, setting time or date, getting time or date, setting system data, etc.

### Communication
Communication is a system call that is used for communication. Some examples of communication include creating, deleting communication connections, sending, receiving messages, etc.

# *3. List out the types of operating system and explain batch OS and time sharing OS in brief.*
   **Types of Operating Systems:**
- [[Batch Operating System 1]]
- [[Multi-Programming Operating System 1]]
- [[Multi-Processing Operating System 1]]
- [[Multi-Tasking Operating System 1]]
- [[Time-Sharing Operating Systems]]
- [[Personal Computer]]
- [[Parallel Operating System]]
- [[Distributed Operating System 1]]
- [[Network Operating System 1]]
  
  **Batch Operating System:**
   - **Description:** In this type of operating system, the computer doesn't interact directly with the user. Instead, an operator groups similar jobs with the same requirements into batches, and the operator is responsible for sorting these jobs.
   - **Advantages:**
     - Predictable job durations.
     - Multiple users can share the system.
     - Minimal idle time.
     - Efficient for handling repetitive tasks.
   - **Disadvantages:**
     - Requires knowledgeable operators.
     - Challenging to debug.
     - Can be costly.
     - If a job fails, other jobs have to wait.
     - Difficult to estimate job completion times.
   - **Examples:** Payroll systems, bank statements, etc.


**Time-Sharing Operating Systems:**
   - **Description:** Time-sharing operating systems allocate specific time slices (quantums) to each task, ensuring all tasks run smoothly. Each user gets a share of the CPU's time in these multitasking systems.
   - **Advantages:**
     - Equal opportunities for all tasks.
     - Reduced chances of software duplication.
     - Minimized CPU idle time.
     - Efficient resource sharing, reducing hardware costs.
     - Improved productivity and user experience.
   - **Disadvantages:**
     - Reliability issues.
     - Security and data integrity concerns.
     - Data communication problems.
     - Higher overhead and complexity.
     - Increased security risks.
   - **Examples:**
     - IBM VM/CMS.
     - TSO (Time Sharing Option) by IBM.
     - Windows Terminal Services.

# *4. Give Explanation about state process with diagram*
### Process State

When a process executes, it changes state. The process state is defined as the current activity of the process, and it contains five states. Each process is one of the following states:

- **New:** The process is being created.
- **Running:** Instructions are being executed.
- **Waiting:** The process is waiting for some event to occur.
- **Ready:** The process is waiting to be assigned to a processor.
- **Terminated:** The process has finished execution.

**Diagram of Process State**
![[Pasted image 20231107213350.png]]
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

# *5. Explain about operations on processes*
### Operations on Processes

Processes in the system can execute concurrently. The operating system must provide mechanisms for creating and terminating processes.

**Process Creation:**
- A process can create multiple new processes.
- Processes are created and deleted dynamically.
- The process that creates another process is known as the parent process, and the created process is called the child process.
- A child process may, in turn, create additional subprocesses.
- The syntax for creating a new process is: `CREATE(process ID, attributes)`.
- A process requires certain resources (CPU time, memory, files, I/O devices) to complete its task.
- When a process creates a subprocess, the subprocess may either obtain its resources directly from the operating system or be constrained to a subset of the parent process's resources.
- There are two possibilities in terms of resource sharing:
  1. Parent and children share all resources.
  2. Children share a subset of the parent's resources.
  3. Parent and child share no resources.
- There are two possibilities in terms of execution:
  1. Parent and children execute concurrently.
  2. Parent waits until children terminate.
- There are also two possibilities regarding the address space of the new process:
  1. The child process is a duplicate of the parent process.
  2. The child process has a program loaded into it.
- Example:
  - In UNIX:
    - Each process is identified by its process identifier.
    - The `fork` system call creates a new process.
    - The `exec` system call is used after a `fork` to replace the process's memory space with a new program.
    - The new process is a copy of the original process.
  - DEC VMS:
    - Creates a new process, loads a specified program into that process, and starts it running.
  - Windows NT supports both models:
    - The parent address space can be duplicated.
    - The parent can specify the name of a program for the OS to load into the address space of the new process.

**Process Termination:**
- A process executes its last statement and asks the operating system to terminate it (exit).
- Output data from a child process to a parent process is done via a `wait`.
- The process's resources are de-allocated by the operating system.
- A parent process may terminate the execution of child processes (abort).
- Reasons for termination include:
  1. Child has exceeded allocated resources.
  2. The task assigned to the child is no longer required.
  3. The parent is exiting, and the operating system does not allow the child to continue if its parent terminates.
- Termination can cascade, leading to the termination of all children processes.

