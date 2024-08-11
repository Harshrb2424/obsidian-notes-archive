### Operations on Processes and System Call Interface for Process Management

#### Process Creation:

**a. Fork System Call:**
- **Definition:** `fork()` system call is used to create a new process.
- **Description:**
  - A parent process creates a child process using `fork()`.
  - The child process is a copy of the parent process, and both processes continue execution from the instruction after `fork()`.
  - The child process gets a process identifier (pid) of 0 as the return value, while the parent process receives the non-zero pid of the child.
  - This mechanism enables easy communication between the parent and child processes.

**b. Exec System Call:**
- **Definition:** `exec()` system call is used to replace a process's memory space with a new program.
- **Description:**
  - After a `fork()`, one of the processes typically uses `exec()` to load a binary file into memory and start its execution.
  - This system call allows processes to communicate and then proceed independently.
  
**c. Wait System Call:**
- **Definition:** `wait()` system call is used by the parent process to wait for the termination of its child.
- **Description:**
  - After creating a child process, the parent can issue a `wait()` system call.
  - This moves the parent off the ready queue until the termination of the child.
  - The `exec()` system call does not return control unless an error occurs.

#### Process Termination:

**a. Exit System Call:**
- **Definition:** `exit()` system call is used by a process to terminate.
- **Description:**
  - A process terminates by executing its final statement and invoking the `exit()` system call.
  - The process may return a status value to its parent via the `wait()` system call.
  - All resources, including memory, open files, and I/O buffers, are deallocated by the operating system upon process termination.

**b. Termination by Another Process:**
- A process can terminate another process using an appropriate system call (e.g., `TerminateProcess()` in Windows).
- Typically, such a system call can only be invoked by the parent of the process to be terminated to prevent arbitrary termination by users.
![[Pasted image 20231112115855.png]]
#### Additional Information:

- **Process Tree:**
  - During execution, processes may create multiple new processes, forming a tree structure.
  - Parent processes create children, and each child can become a parent to subsequent processes.

- **Process Identifier (PID):**
  - Most operating systems assign a unique PID to each process.
  - The PID serves as an identifier for the process in system calls and management.

- **Resource Deallocation:**
  - When a process terminates, the operating system deallocates all resources associated with it, ensuring efficient system utilization.

