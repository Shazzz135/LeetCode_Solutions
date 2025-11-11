# LeetCode Problem #19 — Remove Nth Node From End of List    

## Problem Description
Given the head of a linked list, remove the nth node from the end of the list and return its head.

 

## Solution (C)

```c

/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
struct ListNode* removeNthFromEnd(struct ListNode* head, int n) {
    
    int length = 0;
    struct ListNode* current = head;
    
    while (current != NULL) {
        length++;
        current = current->next;
    }

    if (n == length) {
        struct ListNode* temp = head->next;
        free(head);
        return temp;
    }

    current = head;
    for (int i = 1; i < length - n; i++) {
        current = current->next;
    }

    struct ListNode* temp = current->next;
    current->next = current->next->next;

    return head;
}



```
## Examples

Example 1:

Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]

Example 2:

Input: head = [1], n = 1
Output: []

Example 3:

Input: head = [1,2], n = 1
Output: [1]
