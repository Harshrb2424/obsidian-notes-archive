### **Queue:**

A queue is a linear data structure that follows the First-In-First-Out (FIFO) order. This means that the item inserted first will be the first to be accessed or removed. Queues can be implemented using arrays or linked lists and are commonly used in scenarios where resources are shared among multiple users and served on a first-come, first-serve basis. Examples of queue usage include CPU scheduling and disk scheduling.



### **Types of Queues:**

1. **Simple Queue:**
   - In a simple queue, insertion (enqueue) occurs at the rear, and removal (dequeue) happens at the front.
   - It follows the FIFO principle.
   
   a) **Input Restricted Queue:**
   - Input is allowed from the rear only.
   - Deletion can occur from both ends (front and rear).
   - Doesn't strictly adhere to FIFO.
   
   b) **Output Restricted Queue:**
   - Input is allowed from both the rear and front.
   - Deletion occurs only from the front.
   - Also doesn't follow strict FIFO.

2. **Circular Queue:**
   - Circular queues have the last element connected to the first element, forming a circular structure.
   - Enqueue and dequeue operations are similar to a simple queue, with the added advantage of efficient memory utilization.
   
3. **Priority Queue:**
   - In a priority queue, elements are ordered based on their priority.
   - Two variations include descending priority (highest value has the highest priority) and ascending priority (lowest value has the highest priority).

4. **Dequeue (Double-Ended Queue):**
   - Dequeue allows elements to be inserted or removed from both ends of the queue.
   - It doesn't strictly follow the FIFO property.

The provided explanation outlines the array implementation of a queue, including the `enqueue()`, `deQueue()`, and `display()` functions. Here's a summary of each function for easy reference:

## **Basic Operations on Queue:**

1. `enqueue()`: Inserts an element at the end of the queue (rear).
2. `dequeue()`: Removes and returns an element from the front of the queue.
3. `front()`: Returns the element at the front without removing it.
4. `rear()`: Returns the element at the rear without removing it.
5. `isEmpty()`: Indicates whether the queue is empty or not.
6. `isFull()`: Indicates whether the queue is full or not.
7. `size()`: Returns the size of the queue, i.e., the total number of elements it contains.

# Array and Linked Representations
## Array implementation of Queue
### **Enqueue (Inserting a value into the Queue):**
- To insert an element into the queue, follow these steps:
  1. Check if the queue is full.
  2. If it's full, print "Queue Overflow" and exit.
  3. If the queue is not full, increment the `rear` and add the element.

```c
if (rear == MAX - 1)
    printf("Queue Overflow\n");
else
{
    if (front == -1)
        front = 0;
    printf("Enter the value to be inserted into the queue: ");
    scanf("%d", &value);
    rear = rear + 1;
    a[rear] = value;
}
```

### **Dequeue (Deleting a value from the Queue):**
- To delete an element from the queue, follow these steps:
  1. Check if the queue is empty.
  2. If it's empty, print "Queue Underflow" and reset `front` and `rear`.
  3. If it's not empty, print the element at the front and increment `front`.

```c
if (front == -1 || front > rear)
{
    printf("Queue Underflow\n");
    front = rear = -1;
}
else
{
    printf("Element deleted from the queue is: %d\n", a[front]);
    front = front + 1;
}
```

### **Display (Displaying the elements of the Queue):**
- To display the elements of the queue, follow these steps:
  1. Check if the queue is empty.
  2. If it's empty, print "Queue is empty."
  3. If it's not empty, use a loop to display the elements from `front` to `rear`.

```c
int i;
if (front > rear || rear == -1)
    printf("Queue is empty\n");
else
{
    for (i = front; i <= rear; i++)
        printf("%d \t", a[i]);
}
```


**Drawbacks of Queue Implementation Using Array:**
1. **Memory Wastage:** The array implementation may lead to memory wastage as the space allocated for the queue cannot be easily reutilized for new elements. The front may reach the end of the array, limiting further insertions. This can be addressed by using a circular manner to manage front and rear.

2. **Deciding Array Size:** In this method, you must determine the size of the array in advance. It's challenging to extend the array size at runtime.

**Queue Using Linked List:**
- The queue implemented using a linked list overcomes the limitations of fixed array size and allows the queue to work for an unlimited number of values. It is suitable for variable-sized data, and there's no need to fix the size at the beginning.



## Queue Using Linked List
### **Operations for Queue Using Linked List:**

1. **enQueue(value):** Inserting an element into the Queue:
   - Create a new node with the given value and set its `next` pointer to NULL.
   - Check if the queue is empty (`rear == NULL`).
   - If empty, set both `front` and `rear` to the new node.
   - If not empty, set `rear->next` to the new node and update `rear` to the new node.

1. `enQueue(int value)`: Inserts an element into the queue. The program creates a new node and adds it to the rear of the queue.

2. `deQueue()`: Deletes an element from the front of the queue. It checks if the queue is empty and, if not, removes the front element.

3. `display()`: Displays the elements in the queue from front to rear.

```c
case 1: // enQueue
    printf("Enter the value to be inserted: ");
    scanf("%d", &value);
    enQueue(value);
    break;

case 2: // deQueue
    deQueue();
    break;

case 3: // Display
    display();
    break;

case 4: // Exit
    printf("Exiting the program.\n");
    exit(0);
    break;

default:
    printf("Invalid choice. Please try again.\n");
}

return 0;
}
```


# Applications of Queue:

1. **Handling Website Traffic:** Queues are used to manage website traffic by handling incoming requests in the order they are received. This ensures fair access to web services.

2. **Playlist Management in Media Players:** Media players use queues to manage playlists. Songs are played in the order they are added to the queue.

3. **Operating Systems and Interrupts:** Queues are employed in operating systems to manage and prioritize interrupt requests from hardware devices, ensuring timely processing.

4. **Resource Scheduling:** Queues help in managing shared resources such as printers, CPUs, or other critical system resources. Tasks are queued and serviced based on priority.

5. **Asynchronous Data Transfer:** Queues are crucial for asynchronous data transfer in computer systems, including communication through pipes, file I/O, and sockets.

6. **Job Scheduling:** Operating systems use queues to schedule processes and jobs, ensuring that tasks are executed in a controlled and efficient manner.

7. **Social Media Uploads:** Social media platforms use queues to manage the upload of multiple photos or videos, ensuring a smooth and organized user experience.

8. **Email Transmission:** Email servers use queues to store and send email messages. Messages are queued and processed in the order they are received.

9. **Handling Website Traffic Simultaneously:** Queues are used to manage website traffic during periods of high load, ensuring that the server can handle multiple requests concurrently.

10. **Windows Operating System:** In Windows and other operating systems, queues are used to switch between multiple applications and manage tasks running on the computer.

### Real-Life Examples of Queue:

1. **One-Way Road:** In traffic management, a one-way road follows the queue principle, where vehicles that enter first will exit first. This ensures a smooth flow of traffic.

2. **Ticket Windows:** Ticket counters at various places, such as movie theaters, train stations, or bus terminals, operate on a first-come-first-served basis, resembling a queue.

3. **Cashier Lines:** In stores and supermarkets, customers form queues at cashier lines to complete their transactions. This system ensures fairness and order.

4. **Escalators:** People waiting to use escalators form queues. Those who arrive first board the escalator before those who arrive later.



