#2-1-OS #theorySubject 
# FCFS (First Come First Serve) CPU Scheduling Algorithm
## Aim
Write a C program to implement the FCFS CPU scheduling.
## Program
```C
#include <stdio.h>
void main()
{
    int bt[10], p[10], wt[10], tat[10], i, j, n, total = 0;
    float awt, atat;
    printf("Enter the total number of processes: ");
    scanf("%d", &n);
    printf("\n Enter Burst Time:\n");
    for (i = 0; i < n; i++)
    {
        printf("p%d : ", i + 1);
        scanf("%d", &bt[i]);
    }
    wt[0] = 0; // waiting time for first process will be zero
    // calculate waiting time for remaining process
    for (i = 1; i < n; i++)
    {
        wt[i] = 0;
        for (j = 0; j < i; j++)
            wt[i] += bt[j];
        total += wt[i];
    }
    awt = (float)total / n; // average waiting time
    total = 0;
    printf("\n Process\t Burst Time \t Waiting Time\t Turnaround Time");
    for (i = 0; i < n; i++)
    {
        tat[i] = bt[i] + wt[i]; // calculate turnaround time
        total += tat[i];
        printf("\n p%d \t\t %d \t\t %d\t\t %d", i + 1, bt[i], wt[i], tat[i]);
    }
    atat = (float)total / n; // average turnaround time
    printf("\n\n Average Waiting Time = %.2f", awt);
    printf("\n Average Turnaround Time = %.2f\n", atat);
}
```
### Output
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> gcc .\00101.c
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> .\a.exe
Enter the total number of processes: 5

 Enter Burst Time:
p1 : 10
p2 : 1
p3 : 2
p4 : 1
p5 : 5

 Process         Burst Time      Waiting Time    Turnaround Time
 p1              10              0               10
 p2              1               10              11
 p3              2               11              13
 p4              1               13              14
 p5              5               14              19

 Average Waiting Time = 9.60
 Average Turnaround Time = 13.40
```
## Result
Thus the program for FCFS (First Come First Serve) CPU scheduling was implemented and verified.
# SJF (Shortest Job First) CPU Scheduling Algorithm
## Aim
Write a C program to implement the SJF CPU scheduling.
## Program
```C
#include <stdio.h>
void main()
{
    int bt[10], p[10], wt[10], tat[10], i, j, n, total = 0, pos, temp;
    float awt, atat;
    printf(" Enter the number of process: ");
    scanf("%d", &n);
    printf("\nEnter Burst Time:\n");
    for (i = 0; i < n; i++)
    {
        printf("p%d:", i + 1);
        scanf("%d", &bt[i]);
        p[i] = i + 1; // contains process number
    }
    // sorting burst time in ascending order using selection sort
    for (i = 0; i < n; i++)
    {
        pos = i;
        for (j = i + 1; j < n; j++)
        {
            if (bt[j] < bt[pos])
                pos = j;
        }
        temp = bt[i];
        bt[i] = bt[pos];
        bt[pos] = temp;
        temp = p[i];
        p[i] = p[pos];
        p[pos] = temp;
    }
    wt[0] = 0; // waiting time for first process will be zero
    // calculate waiting time
    for (i = 1; i < n; i++)
    {
        wt[i] = 0;
        for (j = 0; j < i; j++)
            wt[i] += bt[j];
        total += wt[i];
    }
    awt = (float)total / n; // average waiting time
    total = 0;
    printf("\n Process \t Burst Time \t Waiting Time \t Turn Around Time");
    for (i = 0; i < n; i++)
    {
        tat[i] = bt[i] + wt[i]; // calculate turnaround time
        total += tat[i];
        printf("\n p%d \t\t %d \t\t %d \t\t %d", p[i], bt[i], wt[i], tat[i]);
    }
    atat = (float)total / n; // average turnaround time
    printf("\n\n Average Waiting Time =%.2f", awt);
    printf("\n Average Turnaround Time=%.2f\n", atat);
}
```
### Output
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> gcc .\00102.c
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> .\a.exe
 Enter the number of process: 5 

Enter Burst Time:
p1:10
p2:1
p3:2
p4:1
p5:5

 Process         Burst Time      Waiting Time    Turn Around Time
 p2              1               0               1
 p4              1               1               2
 p3              2               2               4
 p5              5               4               9
 p1              10              9               19

 Average Waiting Time =3.20
 Average Turnaround Time=7.00
```
## Result
Thus the program for SJF (Shortest Job First) CPU scheduling was implemented and verified.
# Round Robin CPU Scheduling Algorithm
## Aim
Write a C program to implement the Round Robin CPU scheduling.
## Program
```C
#include <stdio.h>
void main()
{
    int st[10], bt[10], wt[10], tat[10], n, tq, i, count = 0, swt = 0, stat = 0, temp, sq = 0;
    float awt, atat;
    printf("Enter the number of processes: ");
    scanf("%d", &n);
    printf("Enter the burst time of each process: \n");
    for (i = 0; i < n; i++)
    {
        printf("p%d : ", i + 1);
        scanf("%d", &bt[i]);
        st[i] = bt[i];
    }
    printf("Enter the time quantum: ");
    scanf("%d", &tq);
    while (1)
    {
        for (i = 0, count = 0; i < n; i++)
        {
            temp = tq;
            if (st[i] == 0)
            {
                count++;
                continue;
            }
            if (st[i] > tq)
                st[i] = st[i] - tq;
            else if (st[i] >= 0)
            {
                temp = st[i];
                st[i] = 0;
            }
            sq = sq + temp;
            tat[i] = sq;
        }
        if (n == count)
            break;
    }
    for (i = 0; i < n; i++)
    {
        wt[i] = tat[i] - bt[i];
        swt = swt + wt[i];
        stat = stat + tat[i];
    }
    awt = (float)swt / n;
    atat = (float)stat / n;
    printf("Process \t Burst Time \t Waiting Time \t Turn Around Time \n");
    for (i = 0; i < n; i++)
        printf(" %d \t\t %d \t\t %d \t\t %d \n", i + 1, bt[i], wt[i], tat[i]);
    printf("\n Average Waiting Time = %.2f", awt);
    printf("\n Average Turn Around Time = %.2f", atat);

}
```
### Output
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> gcc .\00103.c
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> .\a.exe
Enter the number of processes: 5
Enter the burst time of each process:
p1 : 10
p2 : 1
p3 : 2
p4 : 1
p5 : 5
Enter the time quantum: 1
Process          Burst Time      Waiting Time    Turn Around Time
 1               10              9               19
 2               1               1               2
 3               2               5               7
 4               1               3               4
 5               5               9               14

 Average Waiting Time = 5.40
 Average Turn Around Time = 9.20
```
## Result
Thus the program for Round Robin CPU scheduling was implemented and verified.
# Priority CPU Scheduling Algorithm
## Aim
Write a C program to implement the Priority CPU scheduling.
## Program
```C
#include <stdio.h>
void main()
{
    int bt[10], p[10], wt[10], tat[10], pri[10], i, j, k, n, total = 0, pos, temp;
    float awt, atat;
    printf("Enter number of process: ");
    scanf("%d", &n);
    printf("\nEnter Burst Time:\n");
    for (i = 0; i < n; i++)
    {
        printf("p%d : ", i + 1);
        scanf("%d", &bt[i]);
        p[i] = i + 1; // contains process number
    }
    printf(" Enter priority of the process:\n");
    for (i = 0; i < n; i++)
    {
        p[i] = i + 1;
        printf("p%d : ", i + 1);
        scanf("%d", &pri[i]);
    }
    for (i = 0; i < n; i++)
        for (k = i + 1; k < n; k++)
            if (pri[i] > pri[k])
            {
                temp = p[i];
                p[i] = p[k];
                p[k] = temp;
                temp = bt[i];
                bt[i] = bt[k];
                bt[k] = temp;
                temp = pri[i];
                pri[i] = pri[k];
                pri[k] = temp;
            }
    wt[0] = 0; // waiting time for first process will be zero
    for (i = 1; i < n; i++)
    {
        wt[i] = 0;
        for (j = 0; j < i; j++)
            wt[i] += bt[j];
        total += wt[i];
    }
    awt = (float)total / n; // average waiting time
    total = 0;
    printf("\nProcess\t Burst Time \tPriority \tWaiting Time\tTurnaround Time");
    for (i = 0; i < n; i++)
    {
        tat[i] = bt[i] + wt[i]; // calculate turnaround time
        total += tat[i];
        printf("\n p%d \t\t %d \t\t %d \t\t %d \t\t %d", p[i], bt[i], pri[i], wt[i], tat[i]);
    }
    atat = (float)total / n; // average turnaround time
    printf("\n\n Average Waiting Time =%.2f", awt);
    printf("\n Average Turnaround Time=%.2f\n", atat);

}
```

### Output
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> gcc .\00104.c
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> .\a.exe
Enter number of process: 5

Enter Burst Time:
p1 : 10
p2 : 1
p3 : 2
p4 : 1
p5 : 5
 Enter priority of the process:
p1 : 3
p2 : 1
p3 : 3
p4 : 4
p5 : 2

Process  Burst Time     Priority        Waiting Time    Turnaround Time
 p2              1               1               0               1
 p5              5               2               1               6
 p3              2               3               6               8
 p1              10              3               8               18
 p4              1               4               18              19

 Average Waiting Time =6.60
 Average Turnaround Time=10.40
```
## Result
Thus the program for Priority CPU scheduling was implemented and verified.