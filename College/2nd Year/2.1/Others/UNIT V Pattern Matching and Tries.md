
# Pattern Matching Algorithms

## Brute Force
- The Brute Force pattern matching algorithm is one of the simplest methods for searching a pattern within a text.
- It involves systematically comparing the pattern with all substrings of the text to find occurrences of the pattern.

**Algorithm Steps:**
1. Begin by aligning the pattern with the beginning of the text.
2. Slide the pattern one character at a time across the text.
3. Compare each character of the pattern with the corresponding character in the text.
4. If a mismatch occurs, shift the pattern one position to the right and continue comparing.
5. Repeat until the pattern matches a substring of the text or reaches the end of the text.

**Complexity Analysis:**
- Time Complexity: \(O((n - m + 1) \times m)\), where \(n\) is the length of the text and \(m\) is the length of the pattern.
  - In the worst case, every substring of length \(m\) in the text needs to be compared with the pattern.
- Space Complexity: \(O(1)\), as it doesn't require any extra space proportional to the input size.
![700](https://1.bp.blogspot.com/-YJDalyxz6XY/UFCYnd2_nBI/AAAAAAAAAB4/uewJpXgs9Mc/s1600/Brute+Force.jpg)
**Advantages:**
- Simple to implement and understand.
- Suitable for small to medium-sized texts and patterns.
- No preprocessing required.

**Disadvantages:**
- Inefficient for large texts and patterns due to its quadratic time complexity.
- Performs redundant comparisons, especially for patterns with frequent mismatches.
- Not suitable for real-time or performance-critical applications.

The Brute Force algorithm serves as a fundamental approach to pattern matching but may not be practical for large-scale applications due to its inefficiency. Despite its limitations, it provides a starting point for understanding more advanced pattern matching techniques.
## The Boyer–Moore Algorithm
- The Boyer-Moore algorithm is a powerful pattern matching algorithm known for its efficiency in searching for patterns within text.
- It works by scanning the text from right to left and employing heuristic rules to skip unnecessary comparisons.

**Algorithm Steps:**
1. Start matching the pattern against the text from the rightmost end of the pattern.
2. If a mismatch occurs:
   - Use the bad character rule to skip positions based on the last occurrence of the mismatched character in the pattern.
   - Use the good suffix rule to shift the pattern to align the matching suffix with the text.
3. Repeat steps 1 and 2 until a match is found or the pattern exhausts the text.
![700](https://image2.slideserve.com/4039711/boyer-moore-heuristics-l.jpg)
**Complexity Analysis:**
- Best Case Time Complexity: \(O(n/m)\), where \(n\) is the length of the text and \(m\) is the length of the pattern.
- Worst Case Time Complexity: \(O(n \times m)\).
- Space Complexity: \(O(m + k)\), where \(k\) is the size of the alphabet.

**Advantages:**
- Efficient for searching large texts, especially with relatively small patterns.
- Employs heuristic rules to skip unnecessary comparisons, reducing the number of shifts.
- Can achieve linear time complexity in certain scenarios, making it faster than many other algorithms.

**Disadvantages:**
- Requires preprocessing of the pattern, which can be time-consuming.
- Complexity increases with the size of the alphabet.
- May not be the most suitable algorithm for very small patterns or highly repetitive patterns.


The Boyer-Moore algorithm offers significant improvements over brute force algorithms by leveraging heuristic rules to optimize pattern matching.
Despite its preprocessing overhead, it is widely used in various applications, including text editors, search engines, and data processing systems.

## The Knuth-Morris-Pratt Algorithm
- The Knuth-Morris-Pratt (KMP) algorithm is a powerful string searching algorithm known for its efficiency and ability to avoid unnecessary character comparisons.
- It preprocesses the pattern to construct a partial match table, which helps determine shifts in the pattern during the matching process.

**Algorithm Steps:**
1. Preprocess the pattern to construct the partial match table, also known as the failure function.
2. Match the pattern against the text using the partial match table to guide the shifting of the pattern.
3. If a mismatch occurs, use the information from the partial match table to determine the next position to start comparing.
![700](https://media.geeksforgeeks.org/wp-content/uploads/20221125004358/image-660x398.png)
**Complexity Analysis:**
- Time Complexity: \(O(n + m)\), where \(n\) is the length of the text and \(m\) is the length of the pattern.
- Space Complexity: \(O(m)\) for storing the partial match table.

**Advantages:**
- Efficient for searching large texts, especially with relatively small patterns.
- Avoids unnecessary character comparisons by using the partial match table.
- Achieves linear time complexity in most practical cases.

**Disadvantages:**
- Requires preprocessing of the pattern, which increases the initial overhead.
- Space complexity for storing the partial match table can be a concern for very large patterns.
- May not be the most suitable algorithm for very small patterns or highly repetitive patterns.

The Knuth-Morris-Pratt algorithm offers significant improvements over brute force algorithms and even some other sophisticated algorithms by avoiding unnecessary comparisons.
Despite its preprocessing overhead, it is widely used in various applications where efficient pattern matching is required, such as text editors, search engines, and bioinformatics.
# Tries

## Standard Tries
- Tries, also known as prefix trees, are tree-like data structures used for storing a dynamic set of strings.
- They provide an efficient way to search for words or prefixes within a large collection of strings.

**Structure:**
- Each node in a trie represents a single character.
- The root node represents an empty string, and each subsequent node represents a prefix or a complete word.
- Nodes may have multiple children, each corresponding to a different character in the alphabet.

**Operations:**
1. **Insertion**: To insert a word into a trie, start from the root node and traverse the trie character by character. Create new nodes as needed.
2. **Search**: To search for a word or prefix, start from the root node and traverse the trie according to the characters in the word or prefix. If the traversal reaches a leaf node, the word is found.
3. **Deletion**: Deleting a word from a trie requires removing all nodes corresponding to that word. It may involve removing unnecessary nodes to optimize the trie's space complexity.

**Complexity Analysis:**
- Space Complexity: \(O(n \times m)\), where \(n\) is the number of words in the trie and \(m\) is the average length of the words.
- Time Complexity:
  - Insertion: \(O(m)\), where \(m\) is the length of the word being inserted.
  - Search: \(O(m)\), where \(m\) is the length of the word or prefix being searched.
  - Deletion: \(O(m)\), where \(m\) is the length of the word being deleted.
![500](https://lh3.googleusercontent.com/proxy/8tUs7U7nb_BqI_IOjfRp4U-_Xj88WQDA9uDT-oMiHFsOHtebruaHHdSuqQRkxB3d1nS6YxwU3hMvVWx4bCmnaTd5YXGoaIc8TLzhwTPAWo-52jiGlOKwmpcs8Twn24wwbA)
**Advantages:**
- Efficient for storing and searching large collections of strings.
- Supports operations like prefix search, autocomplete, and spell checking.
- Provides a compact representation for dictionaries and word lists.

**Disadvantages:**
- Consumes more memory compared to other data structures like hash tables for certain scenarios.
- May require additional optimizations for space efficiency, such as compressing common prefixes.

Standard tries are versatile data structures widely used in applications like dictionaries, spell checkers, and autocomplete features.
They offer efficient storage and retrieval of strings, making them a valuable tool for text processing and search applications.
## Compressed Tries
Compressed tries, also known as compact tries or radix trees, are a variation of standard tries optimized for space efficiency. They aim to reduce memory consumption by compressing common prefixes and eliminating unnecessary nodes.

### Structure:
1. **Nodes:**
   - Each node in a compressed trie represents a prefix or a complete word.
   - Unlike standard tries, nodes may have multiple characters associated with them.
   
2. **Compression:**
   - Common prefixes among words are compressed into shared nodes to reduce redundancy.
   - Compression occurs whenever possible to optimize memory usage.
   
3. **Leaf Nodes:**
   - Leaf nodes represent the end of a word and may contain additional information such as word frequency or metadata.

### Operations:
1. **Insertion:**
   - Inserting a word follows a similar process to standard tries but may involve compressing nodes and merging branches when possible.
   
2. **Search:**
   - Searching for a word or prefix involves traversing the trie, following edges corresponding to the characters in the word or prefix.
   
3. **Deletion:**
   - Deleting a word requires removing nodes associated with that word and potentially merging nodes to maintain trie structure and compactness.

### Complexity Analysis:
- **Space Complexity:** Generally more space-efficient than standard tries, especially for datasets with many common prefixes.
- **Time Complexity:** Similar to standard tries for insertion, search, and deletion operations.

![600](https://www.cs.emory.edu/~cheung/Courses/253/Syllabus/Text/FIGS/Trie/trie06.gif)
### Advantages:
- **Space Efficiency:** Compressed tries use less memory compared to standard tries, especially for datasets with significant redundancy or many shared prefixes.
- **Improved Performance:** The reduced memory footprint can lead to improved performance in memory-constrained environments or applications requiring rapid access to large datasets.

### Disadvantages:
- **Complexity:** Implementing and managing compressed tries may be more complex compared to standard tries due to compression and node merging algorithms.
- **Trade-offs:** While compressed tries offer space savings, they may incur additional overhead in terms of insertion, search, and deletion operations.

Compressed tries are a valuable variant of standard tries, offering space-efficient storage and retrieval of strings. They are particularly useful in applications with memory constraints or large datasets with repetitive patterns. Understanding the trade-offs between space efficiency and operational complexity is crucial when considering compressed tries for a given application.
## Suffix Tries

Suffix tries, also known as suffix trees, are a type of trie data structure specifically designed for string processing tasks, particularly pattern matching and string analysis. They store all the suffixes of a given string in a trie-like structure.

### Structure:
1. **Nodes:**
   - Each node in a suffix trie represents a substring of the original string.
   - Nodes may have multiple children, each corresponding to a different character in the alphabet.

2. **Suffixes:**
   - Suffixes of the original string are stored as paths from the root to leaf nodes.
   - Each leaf node represents the end of a suffix.

3. **Additional Information:**
   - Besides representing suffixes, suffix tries can also contain additional information such as indices or counts.

### Operations:
1. **Construction:**
   - Suffix tries are constructed by inserting all the suffixes of the original string into the trie.
   - This process typically involves iterating through the string and inserting each suffix into the trie.

2. **Search:**
   - Suffix tries can be searched to find occurrences of specific substrings within the original string.
   - Searching involves traversing the trie according to the characters in the substring being searched for.

3. **Pattern Matching:**
   - Suffix tries are commonly used for pattern matching tasks such as finding all occurrences of a pattern within the original string.

### Complexity Analysis:
- **Space Complexity:** Suffix tries require \(O(n^2)\) space in the worst case, where \(n\) is the length of the original string.
- **Time Complexity:** Construction of the suffix trie typically takes \(O(n^2)\) time, while searching and pattern matching operations take \(O(m)\) time, where \(m\) is the length of the substring being searched for.
![700](https://slideplayer.com/slide/4697047/15/images/8/Suffix+Tries+A+suffix+trie+is+a+compressed+trie+for+all+the+suffixes+of+a+text..jpg)
### Advantages:
- **Efficient Pattern Matching:** Suffix tries excel at pattern matching tasks, especially for finding all occurrences of a pattern within a string.
- **Versatility:** Suffix tries can be used for various string processing tasks, including substring search, longest common substring, and substring palindrome detection.

### Disadvantages:
- **Space Consumption:** Suffix tries can consume a significant amount of memory, particularly for large strings, due to the storage of all suffixes.
- **Construction Complexity:** Building the suffix trie can be computationally intensive, especially for long strings, resulting in longer construction times.

Suffix tries are a powerful data structure for string processing tasks, offering efficient pattern matching capabilities and versatility in string analysis. While they may require significant memory and time for construction, suffix tries provide valuable functionality for various applications, including text processing, bioinformatics, and data compression. Understanding the trade-offs involved in using suffix tries is essential for effectively leveraging their capabilities in different contexts.