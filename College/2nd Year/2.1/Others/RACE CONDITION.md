
A race condition occurs when multiple processes share data, access the data concurrently, and the output of execution depends on the specific sequence in which they share and access the data.

## Definition
When more than one process executes the same code or accesses the same memory or shared variable simultaneously, there is a possibility of incorrect output or value of the shared variable. In this condition, processes race to claim the correctness of their output.

## Example
Consider two processes, P1 and P2, sharing a common variable (shared = 10). Both processes are in the ready queue, waiting for execution. The processes manipulate the shared variable concurrently, and the outcome depends on the order of access.

1. Process P1 initializes X=10 and increments it by 1 (X=11). It then goes into waiting for 1 second.
2. CPU switches to Process P2, which initializes Y=10 and decrements it by 1 (Y=9). P2 goes into waiting for 1 second, leaving the CPU idle.
3. After 1 second, CPU resumes Process P1, increments X, and shared becomes 11.
4. After another second, CPU resumes Process P2, decrements Y, and shared becomes 9.

## Actual Meaning of Race-Condition
- If the order of execution is P1 first, then P2, the final shared value is 9.
- If the order of execution is P2 first, then P1, the final shared value is 11.

## Avoiding Race Conditions

To avoid race conditions, proper synchronization is essential. Two methods to avoid race conditions are:

### 1. Mutual Exclusion:
   - Ensure that only one process can access the shared data or resource at a time. This prevents simultaneous modifications and guarantees consistency.

### 2. Locks and Semaphores:
   - Use locks or semaphores to control access to shared resources. Processes acquire a lock before accessing the resource and release it afterward. This ensures exclusive access.

