# LeetCode Problem #125 — Valid Palindrome

## Problem Description
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

## Solution (Python)

```python


class Solution:
    def isPalindrome(self, s: str) -> bool:

        string = ""
        
        for let in s:
            if let.isalpha() or let.isnumeric():
                if let.isalpha():
                    string += let.lower()
                else:
                    string += let

        for i in range(0, len(string) // 2, 1):
            if string[i] != string[-(i+1)]:
                return False

        return True


```
## Examples

Example 1:

Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.

Example 2:

Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.

Example 3:

Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.
