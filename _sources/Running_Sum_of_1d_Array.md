# Running Sum of 1d Array

Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).
Return the running sum of nums.

Implementation:

```
from itertools import accumulate
import operator
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        return accumulate(nums, operator.add)
```

