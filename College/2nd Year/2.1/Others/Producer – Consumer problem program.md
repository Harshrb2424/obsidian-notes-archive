```C
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
### Output
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