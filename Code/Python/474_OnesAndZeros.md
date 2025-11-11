# LeetCode Problem #474 — One's and Zero's

## Problem Description
You are given an array of binary strings strs and two integers m and n.

Return the size of the largest subset of strs such that there are at most m 0's and n 1's in the subset.

A set x is a subset of a set y if all elements of x are also elements of y.

---

## Solution (Python)

```python

class Solution(object):
    def findMaxForm(self, strs, m, n):
        """
        :type strs: List[str]
        :type m: int
        :type n: int
        :rtype: int
        """

        count = 0

        for binary in strs:
            a = 0
            b = 0
            if len(binary) < (m + n):
                for num in binary:
                    if num == "0":
                        a += 1
                    else:
                        b += 1

                if a <= m and b <= n:
                    count += 1

        return count
        


```
## Example

Input: strs = ["10","0001","111001","1","0"], m = 5, n = 3

Output: 4


Explanation: The largest subset with at most 5 0's and 3 1's is {"10", "0001", "1", "0"}, so the answer is 4.
Other valid but smaller subsets include {"0001", "1"} and {"10", "1", "0"}.
{"111001"} is an invalid subset because it contains 4 1's, greater than the maximum of 3.
