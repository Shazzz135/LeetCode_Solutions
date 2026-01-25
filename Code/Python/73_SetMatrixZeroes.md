# LeetCode Problem #73 — Set Matrix Zeroes

## Problem Description
Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.

You must do it in place.

## Solution (Python)

```python
from typing import List

class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """

        w = len(matrix[0])
        h = len(matrix)

        zeros = []

        for x in range(h):
            for y in range(w):
                if matrix[x][y] == 0:
                    zeros.append([x,y])
        
        for coord in zeros:
            for i in range(h):
                for j in range(w):
                    if i == coord[0] or j == coord[1]:
                        matrix[i][j] = 0

```

## Examples

Example 1:

Input: matrix = [[1,1,1],[1,0,1],[1,1,1]]
Output: [[1,0,1],[0,0,0],[1,0,1]]

Example 2:

Input: matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
Output: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
