1.     Write a C program to simulate Bankers Algorithm for Deadlock Avoidance
# AIM:
Write a C program to simulate the Bankers Algorithm for Deadlock Avoidance. 
# ALGORITHM:
1. Start the program. 
2. Get or assign the values of resources allocated, max and available. 
3. Find the need value. 
4. Check whether it is possible to allocate. 
5. If it is possible then the system is in safe state. 
6. Else system is not in safety state. 
7. If the new request comes then check that the system is in safety or not.
8. Stop the program.

# PROGRAM:
```c
#include <stdio.h>
#define n 5
#define m 3
int main()
{
    int i, j, k, y=0, need[n][m], flag=1, f[n], ans[n], ind=0;
    int alloc[5][3] = { { 0, 1, 0 },
                        { 2, 0, 0 },
                        { 3, 0, 2 },
                        { 2, 1, 1 },
                        { 0, 0, 2 }
    };
    int max[5][3] = { { 7, 5, 3 },
                    { 3, 2, 2 },
                    { 9, 0, 2 },
                    { 2, 2, 2 }
                    { 4, 3, 3 }
    };
    int avail[3] = { 3, 3, 2 };
    
    for (k = 0; k < n; k++)
        f[k] = 0;
    for (i = 0; i < n; i++)
        for (j = 0; j < m; j++)
            need[i][j] = max[i][j] - alloc[i][j];
    for (k = 0; k < 5; k++)
        {
        for (i = 0; i < n; i++)
            {
            if (f[i] == 0)
                {
                int flag = 0;
                for (j = 0; j < m; j++)
                    {
                    if (need[i][j] > avail[j])
                        {
                        flag = 1;
                        break;
                        }
                    }
                    if (flag == 0)
                    {
                        ans[ind++] = i;
                        for (y = 0; y < m; y++)
                            avail[y] += alloc[i][y];
                        f[i] = 1;
                    }
                }   
            }
        }
    for(i=0;i<n;i++)
        {
        if(f[i]==0)
            {
            flag=0;
            printf("The system is UNSAFE state");
            break;
            }
        }
    if(flag==1)
    {
        printf("The system is SAFE and safe sequence is \t");
        for (i = 0; i < n - 1; i++)
            printf(" P%d ->", ans[i]);
        printf(" P%d", ans[n - 1]);
    }
    return (0);
 }
```

# Output:
```
C:\OS> gcc 00301.c
C:\OS> ./a.out
The system is SAFE and safe sequence is          P1 -> P3 -> P4 -> P0 -> P2
```
# RESULT:
Thus, the program of Bankers Algorithm for Deadlock Avoidance was 
executed and verified.

