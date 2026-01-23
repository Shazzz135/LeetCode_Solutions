# LeetCode Problem #149 — Max Points on a Line

## Problem Description
Given an array of points where `points[i] = [xi, yi]` represents a point on the X-Y plane, return the maximum number of points that lie on the same straight line.

---

## Solution (Python)

```python
class Solution:
    def maxPoints(self, points: List[List[int]]) -> int:
        if len(points) <= 2:
            return len(points)

        result = 0

        for i in range(len(points)):
            slopes = {}
            duplicates = 1
            current_max = 0
            x1, y1 = points[i]

            for j in range(i + 1, len(points)):
                x2, y2 = points[j]

                if x1 == x2 and y1 == y2:
                    duplicates += 1
                elif x1 == x2:
                    slope = 'inf'
                else:
                    slope = (y2 - y1) / (x2 - x1)

                if slope != 'inf':
                    slopes[slope] = slopes.get(slope, 0) + 1
                    current_max = max(current_max, slopes[slope])
                else:
                    slopes[slope] = slopes.get(slope, 0) + 1
                    current_max = max(current_max, slopes[slope])

            result = max(result, current_max + duplicates)

        return result
```

## Examples

**Example 1:**

Input: points = [[1,1],[2,2],[3,3]]

Output: 3

**Example 2:**

Input: points = [[1,1],[3,2],[5,3],[4,1],[2,3],[1,4]]

Output: 4
