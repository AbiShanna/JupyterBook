# Binary Search

Given an array of integers nums which is sorted in ascending order, and an integer target, write a function to search target in nums. If target exists, then return its index. Otherwise, return -1.

You must write an algorithm with O(log n) runtime complexity.


Implementation:

```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left, right = 0, len(nums)-1
        while left <= right:
            pivot = left + (right-left)//2
            if nums[pivot] == target:
                return pivot
            if target < nums[pivot]:
                right = pivot-1
            else:
                left = pivot+1
        return -1
            
        
```

