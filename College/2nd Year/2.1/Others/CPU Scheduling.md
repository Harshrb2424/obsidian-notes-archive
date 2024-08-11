
CPU scheduling is the process of determining which process uses the CPU while others are suspended. Its main goal is to keep the CPU busy by selecting a process from the ready queue when the CPU is idle.

In Multiprogramming, effective scheduling is crucial to prevent CPU idle time caused by selecting I/O-bound processes. The objective is to enhance resource utilization and avoid system failures or deadlocks due to processes waiting excessively.

## Objectives of Process Scheduling Algorithm

- **Maximize CPU Utilization:** Keep the CPU as busy as possible.
- **Fair CPU Allocation:** Ensure fair distribution of CPU among processes.
- **Maximize Throughput:** Increase the number of completed processes per time unit.
- **Minimize Turnaround Time:** Reduce the time taken by a process to finish execution.
- **Minimize Waiting Time:** Prevent processes from starving in the ready queue.
- **Minimize Response Time:** Reduce the time for a process to produce its first response.

## Terminologies

- **Arrival Time:** Time when a process enters the ready queue.
- **Completion Time:** Time when a process finishes its execution.
- **Burst Time:** Time required for a process's CPU execution.
- **Turnaround Time:** Time difference between completion time and arrival time.
  - Turnaround Time = Completion Time - Arrival Time
- **Waiting Time (W.T):** Time difference between turnaround time and burst time.
  - Waiting Time = Turnaround Time - Burst Time
