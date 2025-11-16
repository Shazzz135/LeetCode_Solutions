# LeetCode Problem #28 — Index of First Occurence In a String

## Problem Description
Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.
 

## Solution (Python)

```python


class Solution:
    def strStr(self, haystack: str, needle: str) -> int:

        lengthN = len(needle)
        lengthH = len(haystack)

        for i in range(0, (lengthH - lengthN) + 1, 1):
            if haystack[i:i+lengthN] == needle:
                return i

        return -1


```
## Examples

Example 1:

Input: haystack = "sadbutsad", needle = "sad"
Output: 0
Explanation: "sad" occurs at index 0 and 6.
The first occurrence is at index 0, so we return 0.

Example 2:

Input: haystack = "leetcode", needle = "leeto"
Output: -1
Explanation: "leeto" did not occur in "leetcode", so we return -1.
