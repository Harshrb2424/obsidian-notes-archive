x## IMPLEMENTATION OF QUEUE USING ARRAY

```C
#include <stdio.h>
#include <stdlib.h>
#define MAX 3
void insert();
void del();
void display();
int a[MAX], value, rear = -1, front = -1;
int main()
{
    int choice;
    clrscr();
    printf("MENU \n");
    printf("1.Insert an element to queue \n");
    printf("2.Delete element from queue \n");
    printf("3.Display all elements of queue \n");
    printf("4.Quit \n");
    while (1)
    {
        printf("\nEnter your choice : ");
        scanf("%d", &choice);
        switch (choice)
        {
        case 1:
            insert();
            break;
        case 2:
            del();
            break;
        case 3:
            display();
            break;
        case 4:
            printf("Thank You");
            getch();
            exit(1);
        default:
            printf("Wrong choice \n");
        }
    }
}
void insert()
{
    if (rear == MAX - 1)
        printf("Queue Overflow \n");
    else
    {
        if (front == -1)
            front = 0;
        printf("Enter the value to be inserted into queue : ");
        scanf("%d", &value);
        rear = rear + 1;
        a[rear] = value;
    }
}
void del()
{
    if (front == -1 || front > rear)
    {
        printf("Queue Underflow \n");
        front = rear = -1;
        return;
    }
    else
    {
        printf("Element deleted from queue is : %d \n", a[front]);
        front = front + 1;
    }
}
void display()
{
    int i;
    if (front > rear || rear == -1)
        printf("Queue is empty \n");
    else
    {
        printf("Queue is : \n");
        for (i = front; i <= rear; i++)
            printf("%d \t", a[i]);
        printf("\n");
    }
}
```

### Output

```
MENU
1.Insert an element to queue
2.Delete element from queue
3.Display all elements of queue
4.Quit

Enter your choice : 1
Enter the value to be inserted into queue : 5

Enter your choice : 1
Enter the value to be inserted into queue : 10

Enter your choice : 1
Enter the value to be inserted into queue : 15

Enter your choice : 1
Queue Overflow

Enter your choice : 3
Queue is :
5       10      15

Enter your choice : 2
Element deleted from queue is : 5

Enter your choice : 3
Queue is :
10      15

Enter your choice : 5
Wrong choice

Enter your choice : 4
Thank You
```

## IMPLEMENTATION OF QUEUE USING LINKED LIST

```C
#include <stdio.h>
#include <stdlib.h>
struct Node
{
    int data;
    struct Node *next;
} *front = NULL, *rear = NULL;
void insert(int);
void delete();
void display();
void main()
{
    int choice, value;
    clrscr();
    printf("\n:: Queue Implementation using Linked List ::\n");
    printf("\n****** MENU ******\n");
    printf(" 1. Insert\n 2. Delete\n 3. Display\n 4. Exit\n");
    while (1)
    {
        printf("\n Enter your choice: ");
        scanf("%d", &choice);
        switch (choice)
        {
        case 1:
            printf("Enter the value to be insert: ");
            scanf("%d", &value);
            insert(value);
            break;
        case 2:
            delete ();
            break;
        case 3:
            display();
            break;
        case 4:
            printf("\nThank you\n");
            getch();
            exit(0);
        default:
            printf("\n Wrong selection!!! Please Enter Correct Choice!!!\n");
        }
    }
}
void insert(int value)
{
    struct Node *p;
    p = malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;
    if (front == NULL)
        front = rear = p;
    else
    {
        rear->next = p;
        rear = p;
    }
    printf("\n Insertion is Success!!!\n");
}
void delete()
{
    if (front == NULL)
        printf("\n Queue is Underflow!!!\n");
    else
    {
        struct Node *temp = front;
        front = front->next;
        printf("\n Deleted element: %d\n", temp->data);
        free(temp);
    }
}
void display()
{
    if (front == NULL)
        printf("\n Queue is Empty!!!\n");
    else
    {
        struct Node *temp = front;
        while (temp->next != NULL)
        {
            printf("%d--->", temp->data);
            temp = temp->next;
        }
        printf("%d--->NULL\n", temp->data);
    }
}
```

### Output

```
:: Queue Implementation using Linked List ::

****** MENU ******
1. Insert
2. Delete
3. Display
4. Exit

Enter your choice: 1
Enter the value to be insert: 5
Insertion is Success!!!

Enter your choice: 1
Enter the value to be insert: 10
Insertion is Success!!!

Enter your choice: 1
Enter the value to be insert: 15
Insertion is Success!!!

Enter your choice: 1
Enter the value to be insert: 20
Insertion is Success!!!

Enter your choice: 3
5--->10--->15--->20--->NULL

Enter your choice: 2
Deleted element: 5

Enter your choice: 2
Deleted element: 10

Enter your choice: 3
15--->20--->NULL

Enter your choice: 5
Wrong selection!!! Please Enter Correct Choice!!!

Enter your choice: 4
Thank you
```
