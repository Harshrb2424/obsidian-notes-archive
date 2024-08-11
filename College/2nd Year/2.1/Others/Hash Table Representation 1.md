# Hashing (all)
## Hashing
Hashing involves generating a fixed-size output from an input of variable size using mathematical formulas known as hash functions. This technique is used to determine an index or location for the storage of an item in a data structure.

## Components of Hashing

There are three major components of hashing:

### Key
A key can be anything, either a string or an integer, which is fed as input to the hash function. It determines an index or location for the storage of an item in a data structure.

### Hash Function
The hash function receives the input key and returns the index of an element in an array, often referred to as a hash table. This index is known as the hash index.

### Hash Table
A hash table is a data structure that maps keys to values using a special function called a hash function. It stores data in an associative manner in an array, where each data value has its own unique index.

## Example for the Working of Hashing

Consider a set of strings {"ab", "cd", "efg"} that we want to store in a table. The goal is to search or update values quickly in O(1) time without concern for the ordering of strings. The set of strings acts as keys, and the string itself serves as the value.
![[Pasted image 20231120195544.png]]
### Steps:
1. Assign numerical values to alphabetical characters.
2. Calculate the numerical value by summing all characters in the string.
3. Use a hash function, e.g., sum(string) mod Table size, to compute the location of the string in the array.
4. Store the strings in their respective locations.
![[Pasted image 20231120195556.png]]
## Problem with Hashing

While hashing is a powerful technique, it has its challenges, such as collisions. In the example above, using the sum of letters as a hash function resulted in collisions, where different strings produced the same hash value. For instance:
- {"ab", "ba"} have the same hash value.
- {"cd", "be"} also generate the same hash value.

Collisions pose problems in searching, insertion, deletion, and updating of values in a hash table.

# Hash Functions

The hash function establishes a mapping between a key and a value through the use of mathematical formulas. The result is known as a hash value or hash, representing the original string of characters but usually smaller.

## Types of Hash Functions

There are various hash functions for numeric or alphanumeric keys:

- **Division Method:**
  Involves dividing the element with the size of the hash table and using the remainder as the index. Formula: H(key) = k mod m, where m is the size of the hash table.
  
  ### Example
  If the size of the hash table (m) is 10 and the key is {99, 158, 295, 90, 6, 5092}:
  - H(99) = 99 % 10 = 9
  - H(158) = 158 % 10 = 8
  - H(295) = 295 % 10 = 5
  - H(90) = 90 % 10 = 0
  - H(6) = 6 % 10 = 6
  - H(5092) = 5092 % 10 = 2
![[Pasted image 20231120195608.png]]
- **Mid Square Method:**
  Squares the key value and extracts the middle r digits as the hash value, where r is determined by the size of the hash table.
  
  ### Example
  If the hash table has 100 memory locations, and r=2, then the hash value is derived by squaring the key.

- **Digit Folding Method:**
  Breaks the key into groups of digits, and the sum of these groups contributes to the hash code. Two folding methods are used: Fold Shift and Fold Boundary.

  - **Fold Shift:**
    Divides the key into parts matching the size of the required address, and the parts are added to get the address.

  - **Fold Boundary:**
    Divides the key into parts, applying folding, except for the middle part.

- **Multiplication Method:**
  Uses the formula h(k) = floor( m (kA mod 1) ). Both k and A are multiplied, and their fractional part is separated, then multiplied with m to get the hash value.

  ### Example
  If the key is multiplied by a constant value A between 0 and 1.

## Properties of a Good Hash Function

- Efficiently computable.
- Uniformly distributes keys.
- Minimizes collisions.
- Low load factor (number of items in the table divided by the size of the table).
# Collision

In hashing, the process of generating a small number for a large key may lead to the possibility of two keys producing the same value. This situation is known as a collision, and various techniques are used to handle it.
![[Pasted image 20231120195639.png]]
## Collision Resolution

There are two main methods to handle collisions:
![[Pasted image 20231120195645.png]]
### 1. Closed Addressing / Open Hashing / Separate Chaining

The idea here is to make each cell of the hash table point to a linked list of records that have the same hash function value. Chaining is simple but requires additional memory outside the table.

#### Example
Suppose we have a hash function (key % 5) and keys {12, 22, 15, 25}. The separate chaining method for collision resolution is illustrated below:

**Step 1:**
Draw the empty hash table, which will have a possible range of hash values from 0 to 4 according to the hash function provided.
![[Pasted image 20231120195654.png]]![[Pasted image 20231120195659.png]]
![[Pasted image 20231120195723.png]]
**Step 2:**
Insert all the keys into the hash table one by one. Each key is mapped to a specific bucket based on the hash function, and collision handling is done by creating linked lists.
![[Pasted image 20231120195732.png]]![[Pasted image 20231120195735.png]]

### 2. Open Addressing / Closed Hashing

In open addressing, all elements are stored in the hash table itself. Each table entry contains either a record or NIL. There are different techniques for open addressing, including Linear Probing, Quadratic Probing, and Double Hashing.

#### 2.a) Linear Probing

Linear probing involves searching the hash table sequentially starting from the original location of the hash. If the location is already occupied, the next location is checked.

##### Example
Consider a simple hash function as "key mod 5" and a sequence of keys {50, 70, 76, 93}. Detailed steps and examples provided for each key.
![[Pasted image 20231120195906.png]]
#### 2.b) Quadratic Probing

Quadratic probing operates by taking the original hash index and adding successive values of an arbitrary quadratic polynomial until an open slot is found.

##### Example
Consider table size = 7, hash function as Hash(x) = x % 7, and collision resolution strategy f(i) = i^2. Keys {22, 30, 50} are inserted with detailed steps and examples.
![[Pasted image 20231120195828.png]]
#### 2.c) Double Hashing

Double hashing uses two hash functions. The first hash function determines the initial location, and the second one is used if a collision occurs.

##### Example
Insert keys {27, 43, 692, 72} into a hash table of size 7 with first hash function h1(k) = k mod 7 and second hash function h2(k) = 1 + (k mod 5). Detailed steps and examples provided for each key.
![[Pasted image 20231120195838.png]]

