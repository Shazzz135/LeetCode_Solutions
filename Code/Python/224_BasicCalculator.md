# LeetCode Problem #224 — Basic Calculator

## Problem Description
Given a string s representing a valid expression, implement a basic calculator to evaluate it, and return the result of the evaluation.

Note: You are not allowed to use any built-in function which evaluates strings as mathematical expressions, such as eval().

---

## Solution (Python)

```python
class Solution:
    def calculate(self, s: str) -> int:
        stack = []
        result = 0
        number = 0
        sign = 1

        for c in s:
            if c.isdigit():
                number = number * 10 + int(c)

            elif c in "+-":
                result += sign * number
                number = 0
                sign = 1 if c == "+" else -1

            elif c == "(":
                stack.append(result)
                stack.append(sign)
                result = 0
                sign = 1

            elif c == ")":
                result += sign * number
                number = 0
                result *= stack.pop()
                result += stack.pop()

        result += sign * number
        return result
```

## Examples

**Example 1:**

Input: s = "1 + 1"

Output: 2

**Example 2:**

Input: s = " 2-1 + 2 "

Output: 3

**Example 3:**

Input: s = "(1+(4+5+2)-3)+(6+8)"

Output: 23

