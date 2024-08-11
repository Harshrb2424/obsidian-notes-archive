# Quick sort
```C
#include <stdio.h>
#include <conio.h>
#define MAX 10
void printArray(int a[], int n)
{
    printf("[");
    for (int i = 0; i < n; i++)
        printf(" %d ", a[i]);
    printf("]\n");
}
void main()
{
    int a[MAX], n, i, j, temp;
    clrscr();
    printf("Enter the total number of elements in an array : \t ");
    scanf("%d", &n);
    printf("Enter %d elements one by one \n", n);
    for (i = 0; i < n; i++)
        scanf("%d", &a[i]);
    printf("\n Input Array : ");
    printArray(a, n);
    for (i = 0; i < n - 1; i++)
    {
        printf("\n Iteration %d: \n\n", (i + 1));
        for (j = 0; j < n - 1 - i; j++)
        {
            printf("\t\t Items compared: [%d, %d] ", a[j], a[j + 1]);
            if (a[j] > a[j + 1])
            {
                temp = a[j];
                a[j] = a[j + 1];
                a[j + 1] = temp;
                printf(" => swapped [%d, %d]\n", a[j], a[j + 1]);
            }
            else
                printf(" => not swapped\n");
        }
        printf("\n\t Array after this iteration: ");
        printArray(a, n);
    }
    printf("\nOutput Array: ");
    printArray(a, n);
    getch();
}
```
### Output
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> gcc 00601.c -o 00601 
Enter the total number of elements in an array :         6
Enter 6 elements one by one
45
10
99
18
7
93

 Input Array : [ 45  10  99  18  7  93 ]

 Iteration 1:

                 Items compared: [45, 10]  => swapped [10, 45]
                 Items compared: [45, 99]  => not swapped
                 Items compared: [99, 18]  => swapped [18, 99]
                 Items compared: [99, 7]  => swapped [7, 99]
                 Items compared: [99, 93]  => swapped [93, 99]

         Array after this iteration: [ 10  45  18  7  93  99 ]

 Iteration 2:

                 Items compared: [10, 45]  => not swapped
                 Items compared: [45, 18]  => swapped [18, 45]
                 Items compared: [45, 7]  => swapped [7, 45]
                 Items compared: [45, 93]  => not swapped

         Array after this iteration: [ 10  18  7  45  93  99 ]

 Iteration 3:

                 Items compared: [10, 18]  => not swapped
                 Items compared: [18, 7]  => swapped [7, 18]
                 Items compared: [18, 45]  => not swapped

         Array after this iteration: [ 10  7  18  45  93  99 ]

 Iteration 4:

                 Items compared: [10, 7]  => swapped [7, 10]
                 Items compared: [10, 18]  => not swapped

         Array after this iteration: [ 7  10  18  45  93  99 ]

 Iteration 5:

                 Items compared: [7, 10]  => not swapped

         Array after this iteration: [ 7  10  18  45  93  99 ]

Output Array: [ 7  10  18  45  93  99 ]
```
# Heap sort
```C
#include <stdio.h>
#include <conio.h>
void printArray(int arr[], int size)
{
    printf("[ ");
    for (int i = 0; i < size; i++)
        printf("%d ", arr[i]);
    printf("]\n");
}
int main()
{
    int a[20], i, j, n, min, t;
    clrscr();
    printf("Enter the total elements in the array \t");
    scanf("%d", &n);
    for (i = 0; i < n; i++)
    {
        printf("Enter the element%d \t: ", i + 1);
        scanf("%d", &a[i]);
    }
    printf("\n Input Array : ");
    printArray(a, n);
    for (i = 0; i < n - 1; i++)
    {
        printf("\n Iteration %d: \n", (i + 1));
        min = i;
        for (j = i + 1; j < n; j++)
            if (a[j] < a[min])
                min = j;
        if (i != min)
        {
            t = a[min];
            a[min] = a[i];
            a[i] = t;
            printf("\t Items compared: [%d, %d] & swapped ", a[min], a[i]);
        }
        else
            printf("\t Not swapped ");
    }
    printf("\n\n Output Array: ");
    printArray(a, n);
    getch();
    return 0;
}

```
### Output
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> gcc 00602.c -o 00602
Enter the total elements in the array   6
Enter the element1      : 45
Enter the element2      : 10
Enter the element3      : 99
Enter the element4      : 18
Enter the element5      : 7
Enter the element6      : 93

 Input Array : [ 45 10 99 18 7 93 ]

 Iteration 1:
         Items compared: [45, 7] & swapped
 Iteration 2:
         Not swapped
 Iteration 3:
         Items compared: [99, 18] & swapped
 Iteration 4:
         Items compared: [99, 45] & swapped
 Iteration 5:
         Items compared: [99, 93] & swapped

 Output Array: [ 7 10 18 45 93 99 ]
```
# Merge sort
```C
#include <stdio.h>
#include <conio.h>
void printArray(int arr[], int size)
{
    printf("[ ");
    for (int i = 0; i < size; i++)
        printf("%d ", arr[i]);
    printf("]\n");
}
int main()
{
    int a[20], i, j, n, NewElement, flag;
    clrscr();
    printf("Enter the total number of elements in an array : \t");
    scanf("%d", &n);
    for (i = 0; i < n; i++)
    {
        printf("Enter the element%d \t: ", i + 1);
        scanf("%d", &a[i]);
    }
    printf("\n\n Input Array : ");
    printArray(a, n);
    for (i = 1; i < n; i++)
    {
        NewElement = a[i];
        j = i - 1;
        flag = 0;
        while (j >= 0 && a[j] > NewElement)
        {
            a[j + 1] = a[j];
            j = j - 1;
            flag = 1;
        }
        a[j + 1] = NewElement;
        printf("\n Iteration %d : \n", i);
        if (flag == 1)
            printf("\t %d is taken & inserted \n", NewElement);
        else
            printf("\t %d is taken & kept at same position \n", NewElement);
        printf("\t\t Array after the iteration : ");
        printArray(a, n);
    }
    printf("\n Output Array: ");
    printArray(a, n);
    getch();
    return 0;
}

```
### Output
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> gcc 00603.c -o 00603
Enter the total number of elements in an array :        6
Enter the element1      : 45
Enter the element2      : 10
Enter the element3      : 99
Enter the element4      : 18
Enter the element5      : 7
Enter the element6      : 93


 Input Array : [ 45 10 99 18 7 93 ]

 Iteration 1 :
         10 is taken & inserted
                 Array after the iteration : [ 10 45 99 18 7 93 ]

 Iteration 2 :
         99 is taken & kept at same position
                 Array after the iteration : [ 10 45 99 18 7 93 ]

 Iteration 3 :
         18 is taken & inserted
                 Array after the iteration : [ 10 18 45 99 7 93 ]

 Iteration 4 :
         7 is taken & inserted
                 Array after the iteration : [ 7 10 18 45 99 93 ]

 Iteration 5 :
         93 is taken & inserted
                 Array after the iteration : [ 7 10 18 45 93 99 ]

 Output Array: [ 7 10 18 45 93 99 ]
```