# Find Pivot Index

Given an array of integers nums, calculate the pivot index of this array.

The pivot index is the index where the sum of all the numbers strictly to the left of the index is equal to the sum of all the numbers strictly to the index's right.
If the index is on the left edge of the array, then the left sum is 0 because there are no elements to the left. This also applies to the right edge of the array.
Return the leftmost pivot index. If no such index exists, return -1.

Implementation:

```
from itertools import accumulate
import operator
class Solution:
    def pivotIndex(self, nums: List[int]) -> int:
        left_sum = list(accumulate(nums, operator.add))
        left_sum.insert(0,0)
        del left_sum[-1]
        for i in range(len(nums)):
            if left_sum[i] == left_sum[-1]+nums[-1]-left_sum[i]-nums[i]:
                return i
        return -1
            
```

