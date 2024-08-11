Implement a Pattern matching algorithms using Boyer- Moore, Knuth-Morris-Prat

# Boyer- Moore Program:


```c
#include <stdio.h>
#include <string.h>

#define MAX_CHAR 256

void badCharHeuristic(char* pattern, int patternLength, int badChar[MAX_CHAR]) {
    for (int i = 0; i < MAX_CHAR; i++) {
        badChar[i] = -1;
    }
    for (int i = 0; i < patternLength; i++) {
        badChar[(int)pattern[i]] = i;
    }
}

void boyerMooreSearch(char* text, char* pattern) {
    int textLength = strlen(text);
    int patternLength = strlen(pattern);

    int badChar[MAX_CHAR];
    badCharHeuristic(pattern, patternLength, badChar);

    int shift = 0;
    while (shift <= (textLength - patternLength)) {
        int j = patternLength - 1;

        while (j >= 0 && pattern[j] == text[shift + j])
            j--;

        if (j < 0) {
            printf("Pattern found at index %d\n", shift);
            shift += (shift + patternLength < textLength) ? patternLength - badChar[text[shift + patternLength]] : 1;
        } else {
            shift += (j - badChar[text[shift + j]]) > 0 ? j - badChar[text[shift + j]] : 1;
        }
    }
}

int main() {
    char text[] = "ABAAABCD";
    char pattern[] = "ABC";
    printf("text: %s \n", text);
    printf("pattern: %s \n", pattern);
    boyerMooreSearch(text, pattern);
    return 0;
}
```
## Output:
```
text: ABAAABCD 
pattern: ABC
Pattern found at index 4
```

# Knuth-Morris-Prat Program:
```c
#include <stdio.h>
#include <string.h>

void computeLPSArray(char* pattern, int patternLength, int* lps) {
    int len = 0;
    int i = 1;
    lps[0] = 0;

    while (i < patternLength) {
        if (pattern[i] == pattern[len]) {
            len++;
            lps[i] = len;
            i++;
        } else {
            if (len != 0) {
                len = lps[len - 1];
            } else {
                lps[i] = 0;
                i++;
            }
        }
    }
}

void kmpSearch(char* text, char* pattern) {
    int textLength = strlen(text);
    int patternLength = strlen(pattern);

    int lps[patternLength];
    computeLPSArray(pattern, patternLength, lps);

    int i = 0;
    int j = 0;
    while (i < textLength) {
        if (pattern[j] == text[i]) {
            i++;
            j++;
        }

        if (j == patternLength) {
            printf("Pattern found at index %d\n", i - j);
            j = lps[j - 1];
        } else if (i < textLength && pattern[j] != text[i]) {
            if (j != 0) {
                j = lps[j - 1];
            } else {
                i++;
            }
        }
    }
}

int main() {
    char text[] = "ABABDABACDABABCABAB";
    char pattern[] = "ABABCABAB";
    printf("text: %s \n", text);
    printf("pattern: %s \n", pattern);
    kmpSearch(text, pattern);
    return 0;
}
```
## Output:
```
text: ABABDABACDABABCABAB 
pattern: ABABCABAB
Pattern found at index 10
```