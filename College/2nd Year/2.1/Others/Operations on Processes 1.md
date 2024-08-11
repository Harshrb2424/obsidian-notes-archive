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

