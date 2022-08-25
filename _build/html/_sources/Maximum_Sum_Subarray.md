# Maximum Sum Subarray of Size K

Given an array of positive numbers and a positive number ‘k,’ find the maximum sum of any contiguous subarray of size ‘k’.

Implementation:

```
class Solution:
    
    def maxSumSubarray(self, arr, k) -> int:
        max_sum = 0
        window_sum = 0
        window_start = 0
        for i in range(len(arr)):
            window_sum += arr[i]
            if (i - window_start +1) == k:
                max_sum = max(max_sum, window_sum)
                window_sum -= arr[window_start]
                window_start +=1
        return max_sum 

```

