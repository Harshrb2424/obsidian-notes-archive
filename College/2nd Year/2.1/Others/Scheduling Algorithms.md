# Types of CPU Scheduling Algorithms

## Preemptive Scheduling
- Process switches to ready state from running or waiting.
  
## Non-Preemptive Scheduling
- Process terminates or switches from running to waiting.

### 1. First Come First Serve (FCFS) Scheduling

**Characteristics:**
- Supports both non-preemptive and preemptive scheduling.
- Tasks executed in a first-come, first-serve order.
- Easy to implement but not highly efficient.

**Advantages:**
- Easy to implement.
- Follows a first-come, first-serve method.

**Disadvantages:**
- Suffers from Convoy effect.
- High average waiting time.
- Simplicity comes at the cost of efficiency.

### 2. Shortest Job First (SJF) Scheduling

**Characteristics:**
- Minimizes average waiting time.
- May or may not be preemptive.
- Associated with each task's time to complete.

**Advantages:**
- Better than FCFS in reducing average waiting time.
- Suitable for long-term scheduling.

**Disadvantages:**
- May lead to starvation.
- Difficult to predict upcoming CPU request lengths.

### 3. Longest Job First (LJF) Scheduling

**Characteristics:**
- Opposite of SJF, processes with the largest burst time are processed first.
- Non-preemptive, but can be both preemptive and non-preemptive.

**Advantages:**
- No other task schedules until the longest job finishes.
- All jobs finish approximately at the same time.

**Disadvantages:**
- High average waiting and turn-around time.
- May lead to convoy effect.

### 4. Priority Scheduling

- Preemptive method based on process priority.
- Editor assigns importance, higher priority executes first.
- Conflicts resolved using FCFS.
  
**Characteristics:**
- Schedules based on priority.
- Higher priority tasks replace lower priority ones.
- Priority level determined by a lower assigned number.

**Advantages:**
- Lower average waiting time compared to FCFS.
- Less complex.

**Disadvantages:**
- Prone to Starvation Problem.
- Processes may wait longer to get scheduled.

### 5. Round Robin Scheduling

- Each process cyclically assigned a fixed time slot.
- Preemptive version of FCFS, focuses on Time Sharing.

**Characteristics:**
- Simple, easy to use, and starvation-free.
- Widely used in CPU scheduling.
- Processes given limited time.

**Advantages:**
- Fair distribution of CPU.
- Newly created processes added to the end of the queue.

### 6. Shortest Remaining Time First Scheduling (SRTF)

- Preemptive version of SJF, allocates the processor to the job closest to completion.

**Characteristics:**
- Faster job processing than SJF.
- More context switches, consuming CPU time.
  
**Advantages:**
- Quick processing of short processes.
- Low overhead with decisions made on completion or new process addition.

**Disadvantages:**
- Potential for process starvation.
- Long processes delayed by continually adding short processes.

### 7. Longest Remaining Time First

- Preemptive version of LJF, schedules processes with the longest processing time remaining.

**Characteristics:**
- CPU assigned to the process with the largest burst time.
- FCFS used to break ties.

**Advantages:**
- No other process can execute until the longest task finishes.
- Jobs finish approximately at the same time.

**Disadvantages:**
- High average waiting and turn-around time.
- May lead to a convoy effect.

### 8. Highest Response Ratio Next

- Non-preemptive CPU Scheduling algorithm, selects the process with the highest Response Ratio.

**Characteristics:**
- Response Ratio criteria, non-preemptive mode.
- A modification of SJF to reduce starvation.
  
**Advantages:**
- Better performance than SJF.
- Reduces waiting time for longer jobs.

**Disadvantages:**
- Impossible implementation due to unknown burst times.
- May lead to CPU overload.

### 9. Multiple Queue Scheduling

- Processes divided into classes with different scheduling needs.

**Characteristics:**
- System, Interactive, and Batch processes.
  
**Advantages:**
- Low scheduling overhead.

**Disadvantages:**
- Starvation problem.
- Inflexible in nature.

### 10. Multilevel Feedback Queue Scheduling

- Similar to Multilevel Queue Scheduling, allows processes to move between queues.

**Characteristics:**
- Processes can move between queues.
- Balances low scheduling overhead with flexibility.
  
**Advantages:**
- More flexible than Multilevel Queue Scheduling.
- Allows processes to move between queues.

**Disadvantages:**
- Introduces CPU overhead.
- Most complex algorithm.


# Comparison between various CPU Scheduling algorithms
| Algorithm                  | Allocation is                   | Complexity           | Average Waiting Time (AWT) | Preemption | Starvation | Performance |
|----------------------------|---------------------------------|-----------------------|-----------------------------|------------|------------|-------------|
| FCFS                       | Arrival time                     | Simple and easy       | Large                       | No         | No         | Slow        |
| SJF                        | Lowest CPU burst time (BT)       | More complex than FCFS| Smaller than FCFS           | No         | Yes        | Good        |
| SRTF                       | Lowest CPU burst time (BT), preemptive | More complex than FCFS| Depending on arrival time, process size | Yes        | Yes        | Good        |
| RR                         | Order of process arrival with fixed time quantum (TQ) | Complexity depends on TQ | Larger than SJF and Priority scheduling | Yes        | No         | Fair        |
| Priority (Preemptive)      | Priority                        | Less complex          | Smaller than FCFS           | Yes        | Yes        | Well        |
| Priority (Non-preemptive)  | Priority with monitoring new incoming higher priority jobs | Less complex than preemptive Priority | Smaller than FCFS           | No         | Yes        | Most beneficial with batch systems |
| MLQ                        | Process in the bigger queue priority | More complex than Priority | Smaller than FCFS           | No         | Yes        | Good        |
| MLFQ                       | Process of a bigger priority queue | Most complex          | Smaller than all scheduling  | No         | No         | Good        |

# Example 1: FCFS

## Process Table
| Process ID | Arrival Time | Burst Time (ms) |
|------------|--------------|-----------------|
| P1         | 0            | 6               |
| P2         | 2            | 2               |
| P3         | 3            | 1               |
| P4         | 4            | 9               |
| P5         | 5            | 8               |

## Gantt Chart

|   P1  |  P2  |  P3  |  P4  |  P5  |
|-------|------|------|------|------|
| 0 - 6 | 6 - 8| 8 - 9| 9 - 18 | 18 - 26|


| Process ID | Arrival Time (ms) | Burst Time (ms) | Completion Time (ms) | Turn Around Time (ms) | Waiting Time (ms) |
|------------|-------------------|-----------------|-----------------------|------------------------|-------------------|
| P1         | 0                 | 6               | 6                     | 6                      | 0                 |
| P2         | 2                 | 2               | 8                     | 6                      | 4                 |
| P3         | 3                 | 1               | 9                     | 6                      | 5                 |
| P4         | 4                 | 9               | 18                    | 14                     | 5                 |
| P5         | 5                 | 8               | 26                    | 21                     | 13                |

### Average Turn Around Time
$$  \frac{{6 + 8 + 9 + 18 + 26}}{5} = \frac{67}{5} = 13.4 \text{ ms} $$

### Average Waiting Time
$$ \frac{{0 + 6 + 8 + 9 + 18}}{5} = \frac{41}{5} = 8.2 \text{ ms} $$

# Example 2: FCFS

## Process Table
| Process ID | Process Name | Burst Time (BT) |
|------------|--------------|------------------|
| P1         | A            | 79               |
| P2         | B            | 2                |
| P3         | C            | 3                |
| P4         | D            | 1                |
| P5         | E            | 25               |
| P6         | F            | 3                |

## Gantt Chart

|   P1  |  P2  |  P3  |  P4  |  P5  |  P6  |
|-------|------|------|------|------|------|
| 0 - 79 | 79 - 81| 81 - 84| 84 - 85 | 85 - 110| 110 - 113|

| Process ID | Arrival Time (ms) | Burst Time (ms) | Completion Time (ms) | Turn Around Time (ms) | Waiting Time (ms) |
|------------|-------------------|-----------------|-----------------------|------------------------|-------------------|
| P1         | NA                | 79              | 79                    | 79                     | 0                 |
| P2         | NA                | 2               | 81                    | 81                     | 79                |
| P3         | NA                | 3               | 84                    | 84                     | 81                |
| P4         | NA                | 1               | 85                    | 85                     | 84                |
| P5         | NA                | 25              | 110                   | 110                    | 85                |
| P6         | NA                | 3               | 113                   | 113                    | 110               |

## Average Turn Around Time
$$ (79 + 81 + 84 + 85 + 110 + 113) / 6 = 552 / 6 = 92 \text{ ms} $$

## Average Waiting Time
$$ (0 + 79 + 81 + 84 + 85 + 110) / 6 = 439 / 6 = 73.17 \text{ ms} $$

# Example 3: SJF

## Process Table
| Process ID | Arrival Time | Burst Time |
|------------|--------------|------------|
| P0         | 1            | 3          |
| P1         | 2            | 6          |
| P2         | 0            | 2          |
| P3         | 3            | 7          |
| P4         | 2            | 4          |
| P5         | 5            | 5          |

### Non Pre-Emptive SJF
#### Gantt Chart

|   P2  |  P0  |  P4  |  P5  |  P1  |  P3  |
|-------|------|------|------|------|------|
| 0 - 2 | 2 - 5| 5 - 9| 9 - 14 | 14 - 20|20 - 27|



| Process ID | Arrival Time (ms) | Burst Time (ms) | Completion Time (ms) | Turn Around Time (ms) | Waiting Time (ms) |
|------------|-------------------|-----------------|-----------------------|------------------------|-------------------|
| P0         | 1                 | 3               | 5                     | 4                      | 1                 |
| P1         | 2                 | 6               | 20                    | 18                     | 12                |
| P2         | 0                 | 2               | 2                     | 2                      | 0                 |
| P3         | 3                 | 7               | 27                    | 24                     | 17                |
| P4         | 2                 | 4               | 9                     | 7                      | 4                 |
| P5         | 5                 | 5               | 14                    | 10                     | 5                 |

#### Average Turn Around Time
$$ (4 + 15 + 21 + 24 + 36) / 5 = 100 / 5 = 20 \text{ ms} $$

#### Average Waiting Time
 $$(1 + 2 + 9 + 7 + 34) / 5 = 53 / 5 = 10.6 \text{ ms} $$
### Pre-Emptive SJF
#### Gantt Chart

|   P2  |  P0  |  P4  |  P5  |  P4  |  P1  |  P3  |
|-------|------|------|------|------|------|------|
| 0 - 2 | 2 - 5| 5 - 6| 6 - 8 | 8 - 11|11 - 17|17 - 24|


| Process ID | Arrival Time | Burst Time | Completion Time | Turn Around Time (TAT=CT-AT) | Waiting Time (WT=CT–BT) |
|------------|--------------|------------|------------------|-----------------------------|---------------------------|
| P0         | 1            | 3          | 5                | 4                           | 1                         |
| P1         | 2            | 6          | 17               | 15                          | 9                         |
| P2         | 0            | 2          | 2                | 2                           | 0                         |
| P3         | 3            | 7          | 24               | 21                          | 14                        |
| P4         | 2            | 4          | 11               | 9                           | 5                         |
| P5         | 6            | 2          | 8                | 2                           | 0                         |
#### Average Turn Around Time
$$(4 + 15 + 16 + 29 + 35) / 5 = 99 / 5 = 19.8 \text{ ms} $$

#### Average Waiting Time
$$ (1 + 2 + 0 + 15 + 30) / 5 = 48 / 5 = 9.6 \text{ ms} $$

# Example 4: Priority

## Process Table
| S. No | Process ID | Arrival Time | Burst Time | Priority |
|-------|------------|--------------|------------|----------|
| 1     | P1         | 0            | 5          | 5        |
| 2     | P2         | 1            | 6          | 4        |
| 3     | P3         | 2            | 2          | 0        |
| 4     | P4         | 3            | 1          | 2        |
| 5     | P5         | 4            | 7          | 1        |
| 6     | P6         | 4            | 6          | 3        |

## Gantt Chart

|   P1  |  P3  |  P5  |  P4  |  P6  |  P6  |
|-------|------|------|------|------|------|
| 0 - 5 | 5 - 7| 7 - 14| 14 - 15 | 15 - 21| 21 - 27|

| Process ID | Arrival Time | Burst Time | Priority | Completion Time | Turn Around Time (TAT=CT-AT) | Waiting Time (WT=TAT-BT) |
|------------|--------------|------------|----------|------------------|----------------------------------|-----------------------------|
| P1         | 0            | 5          | 5        | 5                | 5                                | 0                           |
| P2         | 1            | 6          | 4        | 27               | 26                               | 20                          |
| P3         | 2            | 2          | 0        | 7                | 5                                | 3                           |
| P4         | 3            | 1          | 2        | 15               | 12                               | 11                          |
| P5         | 4            | 7          | 1        | 14               | 10                               | 3                           |
| P6         | 4            | 6          | 3        | 21               | 17                               | 11                          |

## Average Waiting Time
$$ (0 + 5 + 18 + 21 + 19 + 26) / 6 = 89 / 6 = 14.83 \text{ ms} $$

## Average Turn Around Time
$$ (5 + 18 + 20 + 22 + 26 + 32) / 6 = 123 / 6 = 20.5 \text{ ms} $$

# Example 5: Round Robin

## Process Table
| Process ID | Arrival Time | Burst Time |
|------------|--------------|------------|
| P0         | 1            | 3          |
| P1         | 0            | 5          |
| P2         | 3            | 2          |
| P3         | 4            | 3          |
| P4         | 2            | 1          |

### Time Quantum: 1 ms

#### Gantt Chart

|   P1  |  P0  |  P4  |  P0  |  P2  |  P3  |  P1  |
|-------|------|------|------|------|------|------|
| 0 - 1 | 1 - 2| 2 - 3| 3 - 5| 5 - 7| 7 - 10|10 - 14|


| Process ID | Arrival Time (ms) | Burst Time (ms) | Completion Time (ms) | Turn Around Time (ms) | Waiting Time (ms) |
|------------|-------------------|-----------------|-----------------------|------------------------|-------------------|
| P0         | 1                 | 3               | 5                     | 4                      | 1                 |
| P1         | 0                 | 5               | 14                    | 14                     | 9                 |
| P2         | 3                 | 2               | 7                     | 4                      | 2                 |
| P3         | 4                 | 3               | 10                    | 6                      | 3                 |
| P4         | 2                 | 1               | 3                     | 1                      | 0                 |

#### Average Turn Around Time
$$ (4 + 14 + 4 + 6 + 1) / 5 = 5.8 \text{ ms} $$

#### Average Waiting Time
$$ (1 + 9 + 2 + 3 + 8) / 5 = 4.6 \text{ ms} $$
