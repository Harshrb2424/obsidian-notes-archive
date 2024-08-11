1.     Write a C program to simulate Bankers Algorithm for Deadlock Avoidance
# AIM:
To write a C program to implement memory management using segmentation technique.
# ALGORITHM:
1. Start the program. 
2. Read/Assign the base address, number of segments, size of each segment, 
memory limit. 
3. If memory address is less than the base address display “invalid memory limit”. 
4. Create the segment table with the segment number and segment address and 
display it. 
5. Read the segment number and displacement. 
6. If the segment number and displacement is valid compute the real address and 
display the same. 
7. Stop the program.

# PROGRAM:
```c
#include <stdio.h>
#include <stdlib.h>
#define NUM_SEGMENTS 4
#define SEGMENT_SIZE 1024
#define MEMORY_SIZE NUM_SEGMENTS * SEGMENT_SIZE
typedef struct 
{
 int base;
 int limit;
} SegmentDescriptor;
int main() 
{
	SegmentDescriptor segmentTable[4];
	char memory[MEMORY_SIZE];
	for (int i = 0; i < 4; i++) // Initialize segment table
	{
        segmentTable[i].base = -1;
        segmentTable[i].limit = -1;
	}
	for (int i = 0; i < 4; i++) // Simulate memory allocation
	{
        int segmentNumber = i;
        if (segmentTable[segmentNumber].base == -1) 
        {
            segmentTable[segmentNumber].base = i * SEGMENT_SIZE;
            segmentTable[segmentNumber].limit = SEGMENT_SIZE;
            printf("Segment %d created at Base Address %d\n", segmentNumber, 
            segmentTable[segmentNumber].base);
        }
        // Access memory using the segment table
        int offset = i * 256; // Each segment has 256 bytes
        char value = memory[segmentTable[segmentNumber].base + offset];
        printf("Accessing Memory at Segment %d, Offset %d: Value = %d\n", 
        segmentNumber, offset, value);
	}
	return 0;
}
```

# Output:
```
PS E:\OS>gcc 00602.c
Segment 0 created at Base Address 0
Accessing Memory at Segment 0, Offset 0: Value = 116
Segment 1 created at Base Address 1024
Accessing Memory at Segment 1, Offset 256: Value = 76
Segment 2 created at Base Address 2048
Accessing Memory at Segment 2, Offset 512: Value = 28
Segment 3 created at Base Address 3072
Accessing Memory at Segment 3, Offset 768: Value = -128
```
# RESULT:
Thus the program for memory management using segmentation technique was executed and verified.
