
```C
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node *next;
};
struct node *head = NULL, *p, *t;
void display(void);
int main()
{
    int ch, n, i, x;
    clrscr();
    printf("Enter the number of nodes:\t");
    scanf("%d", &n);
    for (i = 0; i < n; i++)
    {
        p = malloc(sizeof(struct node));
        printf("Enter the data of node%d \t", i + 1);
        scanf("%d", &p->data);
        p->next = NULL;
        if (head == NULL)
            head = p;
        else
            t->next = p;
        t = p;
    }
    display();
    printf("Menu");
    printf("\n 1.Insert at beginning \n 2.Insert after the given node \n 3.Insert at end
\n");
    printf(" 4.Delete at beginning \n 5.Delete the given node \n 6.Delete at last \n 7
Exit \n\n");
    do
    {
        printf("Enter the option \t");
        scanf("%d", &ch);
        t = head;
        switch (ch)
        {
        case 1:
            p = malloc(sizeof(struct node));
            printf("Enter the data to be inserted \t");
            scanf("%d", &p->data);
            p->next = head;
            head = p;
            display();
            break;
        case 2:
            printf("Enter the previous node value where the new node to be inserted \t");
            scanf("%d", &x);
            p = malloc(sizeof(struct node));
            printf("Enter the data to be inserted \t");
            scanf("%d", &p->data);
            t = head;
            while (x != t->data)
                t = t->next;
            p->next = t->next;
            t->next = p;
            display();
            break;
        case 3:
            p = malloc(sizeof(struct node));
            printf("Enter the data to be inserted \t");
            scanf("%d", &p->data);
            t = head;
            while (t->next != NULL)
                t = t->next;
            t->next = p;
            p->next = NULL;
            display();
            break;
        case 4:
            head = head->next;
            display();
            break;
        case 5:
            printf("Enter the node value to be deleted \t");
            scanf("%d", &x);
            t = head;
            while (x != t->data)
            {
                p = t;
                t = t->next;
            }
            if (t == head)
                head = head->next;
            else
                p->next = t->next;
            display();
            break;
        case 6:
            t = head;
            while (t->next != NULL)
            {
                p = t;
                t = t->next;
            }
            if (t == head)
                head = NULL;
            else
                p->next = NULL;
            display();
            break;
        case 7:
            printf("Thank You");
            getch();
        }
    } while (ch != 7);
    return 0;
}
void display()
{
    printf("The singly linked list is \n");
    t = head;
    while (t != NULL)
    {
        printf("%d-->", t->data);
        t = t->next;
    }
    printf("NULL\n\n");
}
```

### Output:
```

PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> .\a.exe
Enter the number of nodes:      5
Enter the data of node1         10
Enter the data of node2         20
Enter the data of node3         30
Enter the data of node4         40
Enter the data of node5         50
The singly linked list is
10-->20-->30-->40-->50-->NULL

Menu
 1.Insert at beginning
 2.Insert after the given node
 3.Insert at end
 4.Delete at beginning
 5.Delete the given node
 6.Delete at last
 7.Exit

Enter the option        1
Enter the data to be inserted   100
The singly linked list is
100-->10-->20-->30-->40-->50-->NULL

Enter the option        2
Enter the previous node value where the new node to be inserted         20
Enter the data to be inserted   200
The singly linked list is
100-->10-->20-->200-->30-->40-->50-->NULL

Enter the option        3
Enter the data to be inserted   300
The singly linked list is
100-->10-->20-->200-->30-->40-->50-->300-->NULL

Enter the option        4
The singly linked list is
10-->20-->200-->30-->40-->50-->300-->NULL

Enter the option        5
Enter the node value to be deleted      20
The singly linked list is
10-->200-->30-->40-->50-->300-->NULL

Enter the option        6
The singly linked list is
10-->200-->30-->40-->50-->NULL

Enter the option        7
Thank You
```