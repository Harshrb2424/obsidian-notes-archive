**Topic: Operating System - Introduction and Structures**

### **Introduction of a Computer System**

- A computer system consists of several key components, including:
  - **Hardware:** This includes memory, CPU (Central Processing Unit), ALU (Arithmetic Logic Unit), I/O devices, storage devices, and peripheral devices.
  - **System Programs:** These comprise compilers, loaders, editors, and the Operating System (OS) itself.
  - **Application Programs:** These encompass various software applications such as database programs and business programs.
- Every computer requires an Operating System to manage and run other programs.
- The OS controls and coordinates the utilization of hardware resources by system programs and applications for various tasks.
- Essentially, it provides an environment within which other programs can perform useful work.

### **Operating System (OS)**

**Definition:**
- In the 1960s, the OS was defined as "The software that controls the hardware."
- The OS functions as a resource manager, performing essential tasks like managing files, processes, and memory.
- It serves as the intermediary between the user and the hardware and is a crucial piece of software in any computing device.

**Concept of OS:**
- The OS is a collection of specialized programs that ensure a computer system functions correctly.
- It performs fundamental tasks such as input recognition, file and directory management, output to the display screen, and control of peripheral devices.
- The OS must support critical tasks, including:
  - Providing an editor for creating and modifying program and data files.
  - Offering access to a compiler for translating high-level language programs into machine code.
  - Using a loader program to move compiled code into computer memory for execution.

**OS as a Resource Allocator:**
- The OS is responsible for resource management:
  - It keeps track of the status of each resource (CPU time, memory, I/O devices, etc.) and allocates them to programs and users as needed.
  - It ensures that multiple programs and users running concurrently do not interfere with one another.
  - Security is another crucial aspect, preventing unauthorized access to the system.
  - The primary objective is to increase the productivity of the computer hardware or the user.

### **OS from Two Viewpoints:**

1. **User View:**
   - The user experience depends on the system interface they interact with. The OS caters to different needs:
     - Personal computers: Focus on user interaction and performance.
     - Mainframe or minicomputer users: Concentrate on resource utilization among multiple terminals.
     - Workstation users on networks: Balance individual resource usage and network sharing.
     - Handheld devices (e.g., mobiles): Manage device usability and battery life.
     - Devices with no user interaction (e.g., embedded computers).

2. **System View:**
   - The OS is the bridge between applications and hardware, with an intimate relationship with the hardware:
     - Resource Allocator: Manages resources like CPU time, memory, and I/O devices to ensure smooth operation.
     - Control Program: Manages processes and I/O devices to prevent errors and disruptions.
     - Simplifier: Makes it easier for users to interact with complex hardware.
     - Kernel: The core component of the OS, running in the background and handling all application programs.

### **Operating Systems (OS) and Their Classification**

Here are some examples of operating systems, followed by their classification:

#### **Operating Systems:**
1. **DOS**
2. **Windows 3**
3. **Windows 95/98**
4. **Windows NT/2000**
5. **Unix**
6. **Linux**
7. (and many more)

#### **Classification of OS:**

**1. Character User Interface (CUI) / Single-User OS:**
   - Users interact with the computer using text-based commands.
   - No use of a mouse; interaction is command-driven.
   - Less user-friendly, typically requires knowledge of specific commands.
   - Examples: DOS, Unix, Linux.

**2. Graphical User Interface (GUI) / Multi-User OS:**
   - User-friendly interface with graphical elements, including windows, icons, and a mouse.
   - Suitable for multiple users and is more intuitive.
   - Examples: Various versions of Windows.

### **Goals of Operating Systems:**

1. **Simplify User Program Execution:** Make it easier for users to run programs and solve their problems.
2. **Efficient Hardware Utilization:** Optimize the use of computer hardware resources.
3. **Application Software Portability:** Allow software to run on different hardware configurations.
4. **Isolation, Security, and Protection:** Ensure that user programs do not interfere with each other and provide security features.
5. **Improve System Reliability:** Enhance the overall stability and reliability of the system.

### **Why Study Operating Systems:**

- **Understanding Hardware-Application Interaction:** To comprehend how hardware and software applications interact with each other.
- **Basic Principles of Computer Systems:** Gain insight into the fundamental principles of computer system design.
- **Specialized Operating Systems:** Meet the increasing demand for specialized operating systems in various domains, e.g., real-time operating systems for aircraft control, embedded operating systems for devices like cell phones and sensors.

### **Computer System Organization:**

- A computer system is composed of several components, including peripheral devices, secondary memory, and the CPU.
- These components are interconnected through a network.
- I/O devices and the CPU can operate concurrently.
- Each device has its controller with a local buffer.
- Data moves between the CPU and main memory via these local buffers.
- I/O operations are performed from the device to the local buffer of the controller.
- Device controllers signal the CPU when an operation is complete by causing an interrupt.

### **Interrupt Handling:**

- Interrupts are vital in computer system organization as they are used to signal the OS to halt its current activities and attend to a more urgent task.
- Interrupts can be categorized into hardware and software interrupts.
- **Hardware Interrupts:** Triggered by hardware peripherals, further divided into maskable and non-maskable interrupts. Maskable interrupts can be ignored or disabled by the CPU, while non-maskable interrupts cannot be ignored.



## **Types of Operating Systems:**
- [[Batch Operating System 1]]
- [[Multi-Programming Operating System 1]]
- [[Multi-Processing Operating System 1]]
- [[Multi-Tasking Operating System 1]]
- [[Time-Sharing Operating Systems]]
- [[Personal Computer]]
- [[Parallel Operating System]]
- [[Distributed Operating System 1]]
- [[Network Operating System 1]]


   




