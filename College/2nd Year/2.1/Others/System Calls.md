### System Calls

A system call is a fundamental interface that allows user programs to interact with the operating system. These calls enable user programs to request services from the operating system's kernel. System calls are essential for various operations, such as file handling, network communication, process management, and hardware access. Here are some key points about system calls:

1. **User-OS Interaction:**
   - A system call serves as a bridge between user programs and the operating system.
   - User programs request specific services, and the operating system responds by invoking a series of system calls to fulfill these requests.

2. **Programming Languages:**
   - System calls can be written in low-level languages like assembly or high-level languages such as C, C++, or Pascal.
   - When using high-level languages, system calls are often predefined functions that the operating system can directly invoke.

3. **Kernel Interaction:**
   - A system call allows a computer program to request a service from the kernel of the operating system.
   - These requests include tasks like file operations, process control, and hardware access.

4. **Interaction Method:**
   - System calls are a means of interacting with the operating system through user programs.
   - They provide a structured way for programs to access essential services provided by the OS.

5. **Request Mechanism:**
   - When software needs to access the kernel's services, it initiates a system call.
   - System calls rely on an Application Program Interface (API) to expose the operating system's services to user-level programs.

6. **Execution Time:**
   - System call execution time varies based on the complexity of the task.
   - Simple system calls, like retrieving the system date and time, can complete in a few nanoseconds.
   - More complex operations, such as connecting to a network device, may take a few seconds.
   - To avoid bottlenecks, most modern operating systems employ multi-threading to handle multiple system calls simultaneously.

### Example of System Calls
- **File Copy:** One common use of system calls is to copy the contents of one file to another.
- **Standard C Library:** A C program might invoke functions from the standard C library (e.g., `printf()`), which, in turn, call underlying system calls (e.g., `write()`).

### Situations Requiring System Calls
Several situations necessitate the use of system calls within an operating system:

1. **File Operations:**
   - Creating, deleting, reading, and writing files all require system calls.

2. **Network Communication:**
   - Establishing and managing network connections, including sending and receiving data packets, relies on system calls.

3. **Hardware Access:**
   - To interact with hardware devices such as printers and scanners, system calls are essential.

4. **Process Management:**
   - Creating, managing, and terminating processes is a core function that relies on system calls.


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

### Examples of Windows and Unix system calls

| Process       | Windows                      | Unix                             |
|---------------|------------------------------|---------------------------------|
| Process Control | CreateProcess()            | Fork()                          |
|               | ExitProcess()              | Exit()                          |
|               | WaitForSingleObject()      | Wait()                          |
| File Manipulation | CreateFile()              | Open()                          |
|               | ReadFile()                | Read()                          |
|               | WriteFile()               | Write()                         |
|               | CloseHandle()             | Close()                         |
| Device Management | SetConsoleMode()           | Ioctl()                         |
|               | ReadConsole()              | Read()                          |
|               | WriteConsole()             | Write()                         |
| Information Maintenance | GetCurrentProcessID()      | Getpid()                        |
|               | SetTimer()                 | Alarm()                         |
|               | Sleep()                    | Sleep()                         |
| Communication | CreatePipe()                | Pipe()                          |
|               | CreateFileMapping()        | Shmget()                         |
|               | MapViewOfFile()            | Mmap()                          |
| Protection    | SetFileSecurity()           | Chmod()                         |
|               | InitializeSecurityDescriptor() | Umask()                          |
|               | SetSecurityDescriptorgroup()  | Chown()                          |

## Additional System Calls

- **open()**
  - The `open()` system call allows you to access a file on a file system. It allocates resources to the file and provides a handle that the process may refer to. Many processes can open a file at once or by a single process only, depending on the file system's structure.

- **read()**
  - The `read()` system call is used to obtain data from a file on the file system. It accepts three arguments in general:
    - A file descriptor.
    - A buffer to store read data.
    - The number of bytes to read from the file. The file descriptor of the file to be read could be used to identify it and open it using `open()` before reading.

- **wait()**
  - In some systems, a process may have to wait for another process to complete its execution before proceeding. The `wait()` system call is used to suspend the parent process. Once the child process has completed its execution, control is returned to the parent process.

- **write()**
  - The `write()` system call is used to write data from a user buffer to a device like a file. It takes three arguments in general:
    - A file descriptor.
    - A pointer to the buffer in which data is saved.
    - The number of bytes to be written from the buffer.

- **fork()**
  - Processes generate clones of themselves using the `fork()` system call. It is one of the most common ways to create processes in operating systems. When a parent process spawns a child process, execution of the parent process is interrupted until the child process completes. Once the child process has completed its execution, control is returned to the parent process.

- **close()**
  - The `close()` system call is used to end file system access. It signifies that the program no longer requires the file, and the buffers are flushed, the file information is altered, and the file resources are deallocated as a result.

- **exec()**
  - When an executable file replaces an earlier executable file in an already executing process, the `exec()` system function is invoked. The old process identification stays, but the new process replaces data, stack, data, heap, etc.

- **exit()**
  - The `exit()` system call is used to end program execution. This call indicates that the thread execution is complete, which is especially useful in multi-threaded environments. The operating system reclaims resources spent by the process following the use of the `exit()` system function.
