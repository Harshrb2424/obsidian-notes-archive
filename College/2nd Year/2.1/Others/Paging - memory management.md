# Program
```C
#include <stdio.h>
#include <stdlib.h>
#define NUM_FRAMES 4
#define PAGE_SIZE 256
#define MEMORY_SIZE NUM_FRAMES * PAGE_SIZE
typedef struct 
{
 int valid;
 int frame;
} PageTableEntry;
int main() 
{
 PageTableEntry pageTable[16];
 char memory[MEMORY_SIZE];
 for (int i = 0; i < 16; i++) // Initialize page table
 {
 pageTable[i].valid = 0;
 pageTable[i].frame = -1;
 }
 for (int i = 0; i < 16; i++) // Simulate memory allocation
 {
 int pageNumber = i;
 int pageIndex = pageNumber * PAGE_SIZE;
 if (!pageTable[pageNumber].valid) 
 {
 for (int j = 0; j < NUM_FRAMES; j++) // Page fault
 {
 if (pageTable[j].frame == -1) 
 {
 pageTable[j].frame = pageIndex;
 pageTable[j].valid = 1;
 printf("Page %d loaded into Frame %d\n", pageNumber, j);
 break;
 }
 }
 }
// Access memory using the page table
 char value=memory[pageTable[pageNumber].frame+ (i % PAGE_SIZE)];
 printf("Accessing Memory at Page %d, Offset %d: Value = %d\n", 
pageNumber, i % PAGE_SIZE, value);
 }
 return 0;
}
```

# Output
```
PS E:\OS>gcc 00601.c
Page 0 loaded into Frame 0
Accessing Memory at Page 0, Offset 0: Value = -56
Page 1 loaded into Frame 1
Accessing Memory at Page 1, Offset 1: Value = -39
Page 2 loaded into Frame 2
Accessing Memory at Page 2, Offset 2: Value = 100
Page 3 loaded into Frame 3
Accessing Memory at Page 3, Offset 3: Value = 0
Accessing Memory at Page 4, Offset 4: Value = 0
Accessing Memory at Page 5, Offset 5: Value = -56
Accessing Memory at Page 6, Offset 6: Value = -6
Accessing Memory at Page 7, Offset 7: Value = 97
Accessing Memory at Page 8, Offset 8: Value = 0
Accessing Memory at Page 9, Offset 9: Value = 32
Accessing Memory at Page 10, Offset 10: Value = 0
Accessing Memory at Page 11, Offset 11: Value = 0
Accessing Memory at Page 12, Offset 12: Value = 0
Accessing Memory at Page 13, Offset 13: Value = 32
Accessing Memory at Page 14, Offset 14: Value = 0
Accessing Memory at Page 15, Offset 15: Value = 0
```