2.     Write a C program to implement the Producer – Consumer problem using semaphores using UNIX/LINUX system calls.
# AIM:
Write a C program to implement the Producer – Consumer problem (using 
semaphores) using UNIX/LINUX system calls. 
# ALGORITHM:
1. The Semaphore mutex, full & empty are initialized. 
2. In the case of producer process 
3. Produce an item in to temporary variable. 
	i. If there is empty space in the buffer check the mutex value for enter into 
	the critical section. 
	ii. If the mutex value is 0, allow the producer to add value in the temporary 
	variable to the buffer. 
1. In the case of consumer process 
	i) It should wait if the buffer is empty 
	ii) If there is any item in the buffer check for mutex value, if the 
	mutex == 0 , remove item from buffer 
	iii) Signal the mutex value and reduce the empty value by 1. 
	iv) Consume the item. 
1. Print the result 

# PROGRAM:
```c
#include<stdio.h> 
#include<stdlib.h> 
int mutex = 1, full = 0, empty = 3, x = 0; 
int main () 
{ 
    int n;
    void producer ();
    void consumer ();
    int wait (int);
    int signal (int);
    printf ("\n 1.Producer \n 2.Consumer \n 3.Exit");
    while (1)
    {
        printf ("\n\t Enter your choice: ");
        scanf ("%d", &n);
        switch (n)
        {
        case 1:
            if ((mutex == 1) && (empty != 0))
                producer ();
            else
                printf ("\t\t Buffer is FULL !!!");
            break;
        case 2:
            if ((mutex == 1) && (full != 0))
                consumer ();
            else
                printf ("\t\t Buffer is EMPTY !!!");
            break;
        case 3:
            exit (0);
        }
    }
    return 0;
}

int wait (int s)
{
    return (--s);
}

int signal (int s)
{
    return (++s);
}

void producer ()
{
    mutex = wait (mutex);
    full = signal (full);
    empty = wait (empty);
    x++;
    printf ("\n Producer produces the item %d", x);
    mutex = signal (mutex);
}

void consumer ()
{
    mutex = wait (mutex);
    full = wait (full);
    empty = signal (empty);
    printf ("\n Consumer consumes item %d", x);
    x--;
    mutex = signal (mutex);
}
```

# Output:
```
C:\OS> gcc 00401.c
C:\OS> ./a.out
 1.Producer
 2.Consumer
 3.Exit
         Enter your choice: 1
 Producer produces the item 1
 
         Enter your choice: 1
 Producer produces the item 2
 
         Enter your choice: 1
 Producer produces the item 3
 
         Enter your choice: 1
		 Buffer is FULL !!!
                 
         Enter your choice: 2
 Consumer consumes item 3
 
         Enter your choice: 2
 Consumer consumes item 2
 
         Enter your choice: 2
 Consumer consumes item 1
 
         Enter your choice: 2
		 Buffer is EMPTY !!!
                 
         Enter your choice: 1
 Producer produces the item 1
 
         Enter your choice: 3
```
# RESULT:
Thus, the program for Producer – Consumer problem using semaphores was executed and verified.

