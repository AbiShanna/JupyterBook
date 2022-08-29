# Pair With Target Sum

Given an array of sorted numbers and a target sum, find a pair in the array whose sum is equal to the given target.
Write a function to return the indices of the two numbers (i.e. the pair) such that they add up to the given target.


Implementation:

```
def pairWithTargetSum(arr, target_sum):
    left = 0
    right = len(arr)-1
    while left < right:
        current_sum = arr[left] + arr[right]
        if current_sum == target_sum:
            return left, right
        if current_sum < target_sum:
            left += 1
        elif current_sum > target_sum:
            right -= 1
        else:
            return -1, -1
            
```

