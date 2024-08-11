## IMPLEMENTATION OF STACK USING ARRAY

```C
#include <stdio.h>
#define max 10
int stack[max], choice, n, top=-1, x, i;
void push(void);
void pop(void);
void display(void);
int main()
{
clrscr();
    printf("\n Enter the size of STACK: ");
    scanf("%d",&n);
    printf("\n\t STACK IMPLEMENTATION USING ARRAY");
    printf("\n\t");
    printf("\n\t 1.PUSH \n\t 2.POP \n\t 3.DISPLAY \n\t 4.EXIT");
    do
    {
        printf("\n Enter the Choice:");
        scanf("%d",&choice);
        switch(choice)
        {
            case 1:
                push();
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("\n\t EXIT POINT - THANK YOU ");
               
                getch();
                break;
            default:
                printf ("\n\t Please Enter a Valid Choice(1/2/3/4)");
        }
    }   while(choice!=4);
    return 0;
}
void push()
{
    if(top==n-1)
        printf("\n STACK is over flow \n");
    else
    {
        printf(" Enter a value to be pushed: ");
        scanf("%d",&x);
        top++;
        stack[top]=x;
    }
}

void pop()
{
    if(top==-1)
        printf("\n\t Stack is under flow \n");
    else
    {
        printf("\n\t The popped elements is %d",stack[top]);
        top--;
    }
}

void display()
{
    if(top>=0)
    {
        printf("\n The elements in STACK ");
        for(i=top; i>=0; i--)
        printf("\n%d",stack[i]);
    }
    else
        printf("\n The STACK is empty \n");
}
```

### Output:

```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> gcc 004.c -o 004
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> .\004

Enter the size of STACK: 4

STACK IMPLEMENTATION USING ARRAY

1.PUSH
2.POP
3.DISPLAY
4.EXIT
Enter the Choice:1
Enter a value to be pushed: 5

Enter the Choice:1
Enter a value to be pushed: 10

Enter the Choice:1
Enter a value to be pushed: 15

Enter the Choice:1
Enter a value to be pushed: 20

Enter the Choice:1

STACK is over flow

Enter the Choice:2

The popped elements is 20
Enter the Choice:2

The popped elements is 15
Enter the Choice:3

The elements in STACK
10
5
Enter the Choice:2

The popped elements is 10
Enter the Choice:2

The popped elements is 5
Enter the Choice:2

Stack is under flow

Enter the Choice:3

The STACK is empty

Enter the Choice:5

Please Enter a Valid Choice(1/2/3/4)
Enter the Choice:4

EXIT POINT - THANK YOU
```

## IMPLEMENTATION OF STACK USING LINKED LIST

```C
#include <stdio.h>
#include <stdlib.h>
struct Node
{
    int data;
    struct Node *next;
};
struct Node *top = NULL;

void push(int value)
{
    struct Node *p;
    p = malloc(sizeof(struct Node));
    p->data = value;
    if (top == NULL)
        p->next = NULL;
    else
        p->next = top;
    top = p;
}

void pop()
{
    if (top == NULL)
        printf("\n Stack is Underflow \n");
    else
    {
        struct Node *t = top;
        printf("The Popped element is %d \n ", t->data);
        top = top->next;
        free(t);
    }
}

void display()
{
    if (top == NULL)
        printf("\nStack Underflow\n");
    else
    {
        printf("The stack is \n");
        struct Node *t = top;
        while (t->next != NULL)
        {
            printf("%d--->", t->data);
            t = t->next;
        }
        printf("%d--->NULL\n", t->data);
    }
}

int main()
{
    int choice, value;
    clrscr();
    printf("\n Implementation of Stack using Linked List ");
    printf("\n ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ \n");
    printf(" 1. Push \n 2. Pop \n 3. Display \n 4. Exit \n");
    while (1)
    {
        printf("Enter your choice : ");
        scanf("%d", &choice);
        switch (choice)
        {
        case 1:
            printf("\nEnter the value to insert: ");
            scanf("%d", &value);
            push(value);
            break;
        case 2:
            pop();
            break;
        case 3:
            display();
            break;
        case 4:
            printf("\n Thank You \n");
            getch();
            exit(0);
            break;
        default:
            printf("\n Wrong Choice \n");
        }
    }
}
```

### Output

```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> gcc 004.c -o 005
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> .\005


Implementation of Stack using Linked List
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
1. Push
2. Pop
3. Display
4. Exit

Enter your choice : 1
Enter the value to insert: 5

Enter your choice : 1
Enter the value to insert: 10

Enter your choice : 1
Enter the value to insert: 15

Enter your choice : 3
The stack is
15--->10--->5--->NULL

Enter your choice : 2
The Popped element is 15

Enter your choice : 3
The stack is
10--->5--->NULL

Enter your choice : 2
The Popped element is 10

Enter your choice : 2
The Popped element is 5

Enter your choice : 2
Stack is Underflow

Enter your choice : 3
Stack Underflow

Enter your choice : 5
Wrong Choice

Enter your choice : 4
Thank You
```
