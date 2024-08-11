3. Write C programs to illustrate the following IPC mechanisms
	1. Pipes
	2. FIFOs
# AIM:
Write C programs to illustrate the following IPC mechanisms 
a) Pipes 
b) FIFOs
# ALGORITHM:
1. Start the program.
2. Initialize IPC mechanism (create necessary data structures, semaphores, 
 etc.).
3. Process A (Sender):
	 a. Prepare the data/message to be sent.
	 b. Acquire a lock or semaphore to access the IPC channel.
	 c. Write the data/message to the shared IPC buffer or channel.
	 d. Release the lock or semaphore.
	 e. Signal or notify Process B about the availability of new data.
1. Process B (Receiver):
	 a. Wait for a signal or notification from Process A.
	 b. Acquire a lock or semaphore to access the IPC channel.
	 c. Read the data/message from the shared IPC buffer or channel.
	 d. Process or use the received data/message.
	 e. Release the lock or semaphore.
1. Clean up and terminate IPC mechanism.
2. Stop.
# a) Pipes PROGRAM:
```c
#include <stdio.h>
#include <unistd.h>
int main() 
{
	 int fd[2];
	 char buffer[50];
	 if (pipe(fd) == -1)
	 {
		 perror("pipe");
		 return 1;
	 }
	 if (fork() == 0) // Child process
	 { 
		 close(fd[0]); // Close read end
		 char msg[] = "Hello from child process!";
		 write(fd[1], msg, sizeof(msg));
		 close(fd[1]);
	 } 
	 else // Parent process
	 { 
		 close(fd[1]); // Close write end
		 read(fd[0], buffer, sizeof(buffer));
		 printf("Parent received: %s\n", buffer);
		 close(fd[0]);
	 }
	 return 0;
 }

```

# Output:
```
C:\OS> gcc 00501.c
C:\OS> ./a.out
Parent received: Hello from child process!
```
# b) FIFOs PROGRAM:
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
int main() 
{
	 const char *fifoFile = "/tmp/myfifo";
	 char buffer[50];
	 mkfifo(fifoFile, 0666);
	 int fd = open(fifoFile, O_RDWR);
	 if (fork() == 0)
	 {
		 char msg[] = "Hello from child process!";
		 write(fd, msg, sizeof(msg));
		 close(fd);
	 } 
	 else
	 {
		 read(fd, buffer, sizeof(buffer));
		 printf("Parent received: %s\n", buffer);
		 close(fd);
	 }
	 return 0;
 }

```

# Output:
```
C:\OS> gcc 00502.c
C:\OS> ./a.out
Parent received: Hello from child process!

```
# RESULT:

Thus the programs for IPC mechanisms (Pipes, FIFOs) was executed and verified.

---
---

3. Write C programs to illustrate the following IPC mechanisms
	1. Message Queues
	2. Shared Memory
# AIM:
Write C programs to illustrate the following IPC mechanisms 
a) Message Queues 
b) Shared Memory
# ALGORITHM:
1. Start the program.
2. Initialize IPC mechanism (create necessary data structures, semaphores, 
 etc.).
3. Process A (Sender):
	 a. Prepare the data/message to be sent.
	 b. Acquire a lock or semaphore to access the IPC channel.
	 c. Write the data/message to the shared IPC buffer or channel.
	 d. Release the lock or semaphore.
	 e. Signal or notify Process B about the availability of new data.
1. Process B (Receiver):
	 a. Wait for a signal or notification from Process A.
	 b. Acquire a lock or semaphore to access the IPC channel.
	 c. Read the data/message from the shared IPC buffer or channel.
	 d. Process or use the received data/message.
	 e. Release the lock or semaphore.
1. Clean up and terminate IPC mechanism.
2. Stop.
# a) Message Queues PROGRAM:
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/ipc.h>
#include <sys/msg.h>
struct message 
{
 long mtype;
 char mtext[50];
};
int main() 
{
	 key_t key;
	 int msgid;
	 struct message msg;
	 key = ftok("msgq_file", 'b');
	 msgid = msgget(key, 0666 | IPC_CREAT);
	 if (fork() == 0) // Child process
	 {
		 struct message childMsg;
		 childMsg.mtype = 1;
		 strcpy(childMsg.mtext, "Hello from child process!");
		 msgsnd(msgid, &childMsg, sizeof(childMsg.mtext), 0);
	 } 
	 else // Parent process
	 {
		 msgrcv(msgid, &msg, sizeof(msg.mtext), 1, 0);
		 printf("Parent received: %s\n", msg.mtext);
		 msgctl(msgid, IPC_RMID, NULL);
	 }
	 return 0;
}
```

# Output:
```
C:\OS> gcc 00503.c
C:\OS> ./a.out
Parent received: Hello from child process!
```
# b) Shared Memory PROGRAM:
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/ipc.h>
#include <sys/shm.h>
int main() 
{
	 key_t key;
	 int shmid;
	 char *shmaddr;
	 key = ftok("shm_file", 'b');
	 shmid = shmget(key, 1024, 0666 | IPC_CREAT);
	 shmaddr = shmat(shmid, (void *)0, 0);
	 if (fork() == 0) // Child process
	 {
		 strcpy(shmaddr, "Hello from child process!");
		 shmdt(shmaddr);
	 } 
	 else // Parent process
	 {
		 wait(NULL);
		 printf("Parent received: %s\n", shmaddr);
		 shmdt(shmaddr);
		 shmctl(shmid, IPC_RMID, NULL);
 }
 return 0;
}

```

# Output:
```
C:\OS> gcc 00504.c
C:\OS> ./a.out
Parent received: Hello from child process!

```
# RESULT:

Thus the programs for IPC mechanisms (Pipes, FIFOs) was executed and verified.

