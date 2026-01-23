# LeetCode Problem #137 — Single Number II

## Problem Description
Given an integer array `nums` where every element appears three times except for one, which appears exactly once. Find the single element and return it.

You must implement a solution with a linear runtime complexity and use only constant extra space.

---

## Solution (Python)

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        check = []

        for item in nums:
            found = False
            for val in check:
                if val[0] == item:
                    val[1] += 1
                    found = True
                    break
            if not found:
                check.append([item, 1])

        for val in check:
            if val[1] == 1:
                return val[0]
```

## Examples

**Example 1:**

Input: nums = [2,2,3,2]

Output: 3

**Example 2:**

Input: nums = [0,1,0,1,0,1,99]

Output: 99
