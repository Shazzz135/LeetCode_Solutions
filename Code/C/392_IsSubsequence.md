# LeetCode Problem #392 — Is Subsequence  

## Problem Description
Given two strings s and t, return true if s is a subsequence of t, or false otherwise.

A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., "ace" is a subsequence of "abcde" while "aec" is not).

 

## Solution (C)

```c

bool isSubsequence(char* s, char* t) {

    if (strlen(s) == 0) {
        return true;
    }

    bool sub = false;
    int index = 0;

    for (int i = 0; i < strlen(t); i++) {
        if (s[index] == t[i]) {
            if (index == strlen(s) - 1) {
                return true;
            } else {
                index++;
            }
        }
    }

    return false;
}


```
## Examples

Example 1:

Input: s = "abc", t = "ahbgdc"
Output: true

Example 2:

Input: s = "axc", t = "ahbgdc"
Output: false
