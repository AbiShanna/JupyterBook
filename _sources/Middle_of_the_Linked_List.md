# Middle of the Linked List

Given the head of a singly linked list, return the middle node of the linked list.

If there are two middle nodes, return the second middle node.


Implementation:

```

import math
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next


# 1 - Using array to store entire list

class Solution:
     def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
         res = [head]
         print(res)
         while res[-1].next:
             res.append(res[-1].next)
         return res[len(res)//2]

# 2 - With only two variables
    
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        skip1 = head
        skip2 = head
        while skip2 and skip2.next:
            skip1 = skip1.next
            skip2 = skip2.next.next
        return skip1
            
```

