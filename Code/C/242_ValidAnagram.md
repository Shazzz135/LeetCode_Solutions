# LeetCode Problem #242 — Valid Anagram

## Problem Description
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

 

## Solution (C)

```c

bool isAnagram(char* s, char* t) {

    if (strlen(s) != strlen(t)) return false;

    int counts[26] = {0};
    for (int i = 0; i < strlen(s); i++) {
        counts[s[i] - 'a']++;
        counts[t[i] - 'a']--;
    }

    for (int i = 0; i < 26; i++) {
        if (counts[i] != 0) return false;
    }
    return true;
}


```
## Examples

Example 1:

Input: s = "anagram", t = "nagaram"

Output: true

Example 2:

Input: s = "rat", t = "car"

Output: false
