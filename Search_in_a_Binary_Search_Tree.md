#  Search in a Binary Search Tree

You are given the root of a binary search tree (BST) and an integer val.
Find the node in the BST that the node's value equals val and return the subtree rooted with that node. If such a node does not exist, return null.

Implementation:

```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

# 1 - Recursion

 class Solution:
     def searchBST(self, root: Optional[TreeNode], val: int) -> Optional[TreeNode]:
         if not root:
             return None
         if root.val == val:
             return root
         if root.val < val:
             return self.searchBST(root.right, val)
         return self.searchBST(root.left, val)


# 2 - Iteration
class Solution:
    def searchBST(self, root: Optional[TreeNode], val: int) -> Optional[TreeNode]:
        while root:
            if root.val == val:
                break
            if root.val < val:
                root = root.right
            else:
                root = root.left
        return root
            
```

