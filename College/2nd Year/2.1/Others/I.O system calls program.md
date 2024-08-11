
# 2. (a) OPEN, READ, WRITE, CLOSE - I/O SYSTEM CALLS
## Aim
C program using open, read, write, close system calls
## Program
```C
#include<sys/stat.h> 
#include<stdio.h> 
#include<fcntl.h> 
#include<sys/types.h> 
int main() 
{ 
    int n,i=0; 
    int f1,f2; 
    char c,strin[100]; 
    f1=open("data.txt",O_RDWR|O_CREAT|O_TRUNC); 
    printf("Enter Data in data.txt: \n");
    while((c=getchar())!='\n') 
        strin[i++]=c; 
    strin[i]='\0'; 
    write(f1,strin,i); 
    close(f1); 
    f2=open("data.txt",O_RDONLY); 
    read(f2,strin,0); 
    printf("Data in data.txt:");
    printf("\n%s\n",strin); 
    close(f2); 
    return 0; 
} 
```
### Output
```
C:\OS> gcc 00201.c
C:\OS> ./a.out
Enter Data in data.txt: 
Hello World CSM B 22Q91A6691 Harsh RB
Data in data.txt:
Hello World CSM B 22Q91A6691 Harsh RB
```

## Result
Thus the program for system calls (such as open, read, write, close) was implemented and verified.
# 2. (b) LSEEK - I/O SYSTEM CALLS
## Aim
C program using lseek
## Program
```C
#include<stdio.h> 
#include <unistd.h> 
#include <fcntl.h> 
#include <sys/types.h> 
int main() 
{ 
    int file=0; 
    if((file=open("data.txt",O_RDONLY)) < -1) 
        return 1; 
    char buffer[19];
    if(read(file,buffer,19) != 19) 
        return 1; 
    printf("%s\n",buffer); 
    if(lseek(file,10,SEEK_SET) < 0) 
        return 1; 
    if(read(file,buffer,19) != 19) 
        return 1; 
    printf("%s\n",buffer); 
    return 0; 
}
```

### Output
```
C:\OS> gcc 00202.c
C:\OS> ./a.out
PS E:\Harsh {Laptop}\Backup 04 2023\Skills\Code\Exercise\2022-23\C\sem 2\OS> .\00202.exe
Hello World CSM B 2♥
d CSM B 22Q91A6691 ♥
```
## Result
Thus the program for lseek- system call was implemented and verified
# 2. (c) OPENDIR(), CLOSEDIR(), READDIR() - I/O SYSTEM CALLS
## Aim
C program using opendir(), closedir(), readdir()
## Program
```C
#include<stdio.h> 
#include<fcntl.h> 
#include<dirent.h> 
void main() 
{ 
    char d[10]; int c,op; DIR *e; 
    struct dirent *sd; 
    printf("**menu**\n1.create dir\n2.remove dir\n3.read dir\nEnter ur choice:\t"); 
    scanf("%d",&op); 
    switch(op) 
    { 
        case 1: 
            printf("enter dir name: \t"); scanf("%s",&d); 
            c=mkdir(d); 
            if(c==1) 
                printf("dir is not created"); 
            else 
                printf("dir is created"); 
            break; 
        case 2: 
            printf("enter dir name: \t"); scanf("%s",&d); 
            c=rmdir(d); 
            if(c==1) 
                printf("dir is not removed"); 
            else 
                printf("dir is removed"); 
            break; 
        case 3: 
            printf("enter dir name to open:\t"); 
            scanf("%s",&d); 
            e=opendir(d); 
            if(e==NULL) 
                printf("dir does not exist"); 
            else 
            { 
                printf("dir exist\n"); 
                while((sd=readdir(e))!=NULL) 
                    printf("%s\t",sd->d_name); 
            } 
            closedir(e); 
            break; 
    } 
} 

```
### Output
```    
C:\OS> gcc 00203.c
C:\OS> ./a.out
**menu**
1.create dir
2.remove dir
3.read dir
Enter ur choice:        1
enter dir name:         CSM
dir is created

OS> ./a.out
**menu**
1.create dir
2.remove dir
3.read dir
Enter ur choice:        3
enter dir name to open: CSM
dir exist
.       ..

OS> ./a.out
1.create dir
2.remove dir
3.read dir
Enter ur choice:        2
enter dir name:         CSM
dir is removed
```
## Result
Thus the program for opendir(), closedir(), readdir() - system calls was implemented and verified.