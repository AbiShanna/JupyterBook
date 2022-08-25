# Smallest Subarray with a Greater Sum

Given an array of positive numbers and a positive number ‘S,’ find the length of the smallest contiguous subarray whose sum is greater than or equal to ‘S’. 
Return 0 if no such subarray exists.

Implementation:

```
import math
class Solution:

    def SmallestSubarrayGreaterSum(self, arr, k) -> int:
        min_len = math.inf
        window_sum = 0
        window_start = 0
        for i in range(len(arr)):
            window_sum += arr[i]
            while window_sum >= k:
                min_len = min(min_len, i-window_start+1)
                window_sum -= arr[window_start]
                window_start += 1
        return min_len
            
```

