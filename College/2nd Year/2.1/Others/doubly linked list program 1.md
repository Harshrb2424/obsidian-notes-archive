
```C
#include <stdio.h>
#include <stdlib.h>
struct node
{
    int data;
    struct node *next;
    struct node *prev;
};

struct node *head = NULL, *p, *q, *t;
void display(void);
void insert_begin(void);
void insert_after(void);
void insert_end(void);
void del_begin(void);
void del(void);
void del_end(void);
int x;

int main()
{
    int ch, n, i;
    clrscr();
    printf("Enter the number of nodes:\t");
    scanf("%d", &n);
    for (i = 0; i < n; i++)
    {
        p = malloc(sizeof(struct node));
        printf("Enter the data of node%d \t", i + 1);
        scanf("%d", &p->data);
        p->next = NULL;
        p->prev = NULL;
        if (head == NULL)
            head = p;
        else
        {
            t->next = p;
            p->prev = t;
        }
        t = p;
    }
    display();
    printf("Menu:");
    printf("\n 1.Insert at beginning \n 2.Insert after the given node \n 3.Insert at end \n");
    printf(" 4.Delete at beginning \n 5.Delete the given node \n 6.Delete at last \n 7.Exit\n");

    do
    {
        printf("\nEnter the option \t");
        scanf("%d", &ch);
        t = head;
        switch (ch)
        {
        case 1:
            insert_begin();
            display();
            break;
        case 2:
            insert_after();
            display();
            break;
        case 3:
            insert_end();
            display();
            break;
        case 4:
            del_begin();
            display();
            break;
        case 5:
            del();
            display();
            break;
        case 6:
            del_end();
            display();
            break;
        case 7:
            printf("Thank You");
            getch();
        }
    } while (ch != 7);
    return 0;
}

void insert_begin()
{
    p = malloc(sizeof(struct node));
    printf("Enter the data to be inserted\t");
    scanf("%d", &p->data);
    p->next = head;
    p->prev = NULL;
    head = p;
}

void insert_after()
{
    printf("Enter the previous node value where the new node to be inserted \t");
    scanf("%d", &x);
    p = malloc(sizeof(struct node));
    printf("Enter the data to be inserted\t");
    scanf("%d", &p->data);
    t = head;
    while (x != t->data)
        t = t->next;
    q = t->next;
    p->next = q;
    p->prev = t;
    t->next = p;
    if (q != NULL)
        q->prev = p;
}

void insert_end()
{
    p = malloc(sizeof(struct node));
    printf("Enter the data to be inserted\t");
    scanf("%d", &p->data);
    p->prev = NULL;
    p->next = NULL;
    t = head;
    while (t->next != NULL)
        t = t->next;
    p->prev = t;
    t->next = p;
}

void del_begin()
{
    t = head;
    head = head->next;
    head->prev = NULL;
    t->next = NULL;
    free(t);
}

void del()
{
    printf("Enter the node value to be deleted \t");
    scanf("%d", &x);
    t = head;
    while (x != t->data)
    {
        p = t;
        t = t->next;
    }
    q = t->next;
    if (t == head)
        head = head->next;
    else if (t->next == NULL)
        p->next = NULL;
    else
    {
        p->next = q;
        q->prev = p;
    }
    free(t);
}

void del_end()
{
    t = head;
    while (t->next != NULL)
    {
        p = t;
        t = t->next;
    }
    if (t == head)
        head = NULL;
    else
    {
        p->next = NULL;
        t->prev = NULL;
        free(t);
    }
}

void display()
{
    printf("The doubly linked list is \n");
    t = head;
    printf("NULL<--");
    while (t != NULL)
    {
        printf("%d", t->data);
        t = t->next;
        if (t != NULL)
            printf("<->");
    }
    printf("-->NULL\n");
}

```

### Output:
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> gcc .\002.c
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> .\a.exe    
Enter the number of nodes:      5
Enter the data of node1         5
Enter the data of node2         6
Enter the data of node3         7
Enter the data of node4         8
Enter the data of node5         9
The doubly linked list is
NULL<--5<->6<->7<->8<->9-->NULL
Menu:
 1.Insert at beginning
 2.Insert after the given node
 3.Insert at end
 4.Delete at beginning
 5.Delete the given node
 6.Delete at last
 7.Exit

Enter the option        1
Enter the data to be inserted   2
The doubly linked list is
NULL<--2<->5<->6<->7<->8<->9-->NULL

Enter the option        2
Enter the previous node value where the new node to be inserted         6
Enter the data to be inserted   23
The doubly linked list is
NULL<--2<->5<->6<->23<->7<->8<->9-->NULL

Enter the option        3
Enter the data to be inserted   69
The doubly linked list is
NULL<--2<->5<->6<->23<->7<->8<->9<->69-->NULL

Enter the option        4
The doubly linked list is
NULL<--5<->6<->23<->7<->8<->9<->69-->NULL

Enter the option        5
Enter the node value to be deleted      8
The doubly linked list is
NULL<--5<->6<->23<->7<->9<->69-->NULL

Enter the option        6
The doubly linked list is
NULL<--5<->6<->23<->7<->9-->NULL

Enter the option        7
Thank You
```