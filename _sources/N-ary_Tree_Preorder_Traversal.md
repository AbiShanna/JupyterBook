# N-ary Tree Preorder Traversal

Given the root of an n-ary tree, return the preorder traversal of its nodes' values.

Nary-Tree input serialization is represented in their level order traversal. Each group of children is separated by the null value 

Implementation:

```
"""
# Definition for a Node.
class Node:
    def __init__(self, val=None, children=None):
        self.val = val
        self.children = children
"""

class Solution:
    def preorder(self, root: 'Node') -> List[int]:
        if root is None:
            return []
        lst = [root]
        res = []
        while lst:
            # pop the first element of list
            tmp = lst.pop()
            # replace with it's children
            lst.extend(tmp.children[::-1])
            #add t output
            res.append(tmp.val)
        return res
        
            
```

