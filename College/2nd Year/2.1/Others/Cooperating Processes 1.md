### Cooperating Processes

- Concurrent processes executing in the operating system can be classified as either independent processes or cooperating processes.

#### Independent Processes:

- Independent processes cannot affect or be affected by the execution of another process.
  
#### Cooperating Processes:

- Cooperating processes can affect or be affected by the execution of another process.

**Advantages of Process Cooperation:**

1. **Information Sharing:** Several users may be interested in the same piece of information.

2. **Computation Speed-Up:** To make a particular task run faster, it must be broken into subtasks and executed in parallel.

3. **Modularity:** Constructing the system in a modular fashion by dividing system functions into separate processes.

4. **Convenience:** Users can work on many tasks in parallel (e.g., editing, compiling, printing).

Processes can communicate with each other through two main methods:

1. **Shared Memory**
2. **Message Passing**

#### (i) Shared Memory:

- Communication between processes using shared memory requires processes to share some variable, which depends on how the programmer implements it.

- Processes can use shared memory for extracting information from another process as well as for delivering specific information to other processes.

- **Example: Producer-Consumer Problem**
  - A producer process produces information consumed by a consumer process (e.g., a print program produces characters consumed by the printer driver).
  - The producer can produce one item while the consumer is consuming another item, but synchronization is necessary.
  - In the bounded-buffer problem, the buffer size is limited, and both the producer and consumer need to be synchronized.

  **Unbounded-Buffer**
  - No practical limit on the size of the buffer.
  - The producer can produce any number of items.
  - The consumer may have to wait.

  **Bounded-Buffer**
  - Assumes a fixed buffer size.
  - Shared data:
    ```c
    #define BUFFER_SIZE 10
    Typedef struct
    {
        . . .
    } item;
    item buffer[BUFFER_SIZE];
    int in = 0;
    int out = 0;
    ```

  **Bounded-Buffer – Producer Process**
    ```c
    item nextProduced;
    while (1)
    {
        while (((in + 1) % BUFFER_SIZE) == out);
        buffer[in] = nextProduced;
        in = (in + 1) % BUFFER_SIZE;
    }
    ```

  **Bounded-Buffer – Consumer Process**
    ```c
    item nextConsumed;
    while (1)
    {
        while (in == out);
        /* do nothing */
        /* do nothing */
        nextConsumed = buffer[out];
        out = (out + 1) % BUFFER_SIZE;
    }
    ```

#### (ii) Message Passing Method:

- In this method, processes communicate with each other without using shared memory.

- The communication process includes:
  - Establishing a communication link (if not already established).
  - Exchanging messages using basic primitives.
  - The message size can be fixed or variable, with trade-offs for the operating system designer and the programmer.
  - Cooperating processes communicate via Inter-Process Communication (IPC).
  - IPC provides a mechanism to allow processes to communicate and synchronize their actions.
  - The IPC facility provides two operations: Send (message) and Receive (message).
  - Implementation of the communication link can be physical (e.g., shared memory, hardware bus) or logical (e.g., logical properties).

