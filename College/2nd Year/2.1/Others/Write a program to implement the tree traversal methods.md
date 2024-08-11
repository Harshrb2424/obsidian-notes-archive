```C
#include <stdio.h>
#include <conio.h>
struct node
{
    int key;
    struct node *left;
    struct node *right;
};
// Create a node
struct node *newNode(int item)
{
    struct node *temp = malloc(sizeof(struct node));
    temp->key = item;
    temp->left = temp->right = NULL;
    return temp;
}
// Inorder Traversal
void inorder(struct node *root)
{
    if (root != NULL)
    {
        inorder(root->left);
        printf("%d ", root->key);
        inorder(root->right);
    }
}
// Postorder Traversal
void postorder(struct node *root)
{
    if (root != NULL)
    {
        postorder(root->left);
        postorder(root->right);
        printf("%d ", root->key);
    }
}
// Preorder Traversal
void preorder(struct node *root)
{
    if (root != NULL)
    {
        printf("%d ", root->key);
        preorder(root->left);
        preorder(root->right);
    }
}
// Insert a node
struct node *insert(struct node *node, int key)
{
    if (node == NULL)
        return newNode(key);
    if (key < node->key)
        node->left = insert(node->left, key);
    else
        node->right = insert(node->right, key);
    return node;
}
int main()
{
    int ch, data, n, i;
    struct node *root = NULL;
    clrscr();
    printf("\n 1.Create \n 2.In-order \n 3.Pre-order \n 4.Post-order \n 5.Exit ");
    do
    {
        printf("\n\n Enter the choice \t");
        scanf("%d", &ch);
        switch (ch)
        {
        case 1:
            printf("\n Enter the no. of nodes to be inserted : ");
            scanf("%d", &n);
            for (i = 0; i < n; i++)
            {
                printf("Enter the data %d : ", i + 1);
                scanf("%d", &data);
                root = insert(root, data);
            }
            break;
        case 2:
            printf("Inorder traversal: ");
            inorder(root);
            break;
        case 3:
            printf("Preorder traversal: ");
            preorder(root);
            break;
        case 4:
            printf("Postorder traversal: ");
            postorder(root);
            break;
        case 5:
            printf("End of Program - Thank you");
            getch();
            exit(0);
        default:
            printf("WRONG CHOICE : Enter correct choice ");
        }
    } while (1);
}
```

### Output
```
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\DS> gcc 00801.c -o 00801
 1.Create
 2.In-order
 3.Pre-order
 4.Post-order
 5.Exit

 Enter the choice       1

 Enter the no. of nodes to be inserted : 6
Enter the data 1 : 45
Enter the data 2 : 10
Enter the data 3 : 99
Enter the data 4 : 18
Enter the data 5 : 7
Enter the data 6 : 93


 Enter the choice       2
Inorder traversal: 7 10 18 45 93 99

 Enter the choice       3
Preorder traversal: 45 10 7 18 99 93

 Enter the choice       4
Postorder traversal: 7 18 10 93 99 45

 Enter the choice       5
End of Program - Thank you
```