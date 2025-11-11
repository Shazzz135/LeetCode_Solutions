# LeetCode Problem #226 — Invert Binary Tree

## Problem Description
Given the root of a binary tree, invert the tree, and return its root.

 

## Solution (C)

```c

/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     struct TreeNode *left;
 *     struct TreeNode *right;
 * };
 */
struct TreeNode* invertTree(struct TreeNode* root) {

    if (root == NULL) return NULL;

    if (root->left == NULL && root->right == NULL) {
        return root;
    } else {

        struct TreeNode* temp = root->right;
        root->right = root->left;
        root->left = temp;

        invertTree(root->left);
        invertTree(root->right);

        return root;
    }
}



```
## Examples

Example 1:

Input: root = [4,2,7,1,3,6,9]
Output: [4,7,2,9,6,3,1]

Example 2:

Input: root = [2,1,3]
Output: [2,3,1]
