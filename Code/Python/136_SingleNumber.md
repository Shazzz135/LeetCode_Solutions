# LeetCode Problem #136 — Single Number

## Problem Description
Given a non-empty array of integers `nums`, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

---

## Solution (Python)

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        check = []
        for item in nums:
            if item not in check:
                check.append(item)
            else:
                check.remove(item)
        
        return check[0]
```

## Examples

**Example 1:**

Input: nums = [2,2,1]

Output: 1

**Example 2:**

Input: nums = [4,1,2,1,2]

Output: 4

**Example 3:**

Input: nums = [1]

Output: 1
