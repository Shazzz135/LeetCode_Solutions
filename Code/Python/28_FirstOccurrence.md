# LeetCode Problem #28 — First Occurrence

## Problem Description
Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

---

## Solution (Python)

```python

class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """

        if not needle:
            return 0

        for i in range(len(haystack) - len(needle) + 1):

            if haystack[i:i + len(needle)] == needle:
                return i

        return -1


```
## Example

Input: haystack = "sadbutsad", needle = "sad"

Output: 0

Explanation: "sad" occurs at index 0 and 6.
The first occurrence is at index 0, so we return 0.
