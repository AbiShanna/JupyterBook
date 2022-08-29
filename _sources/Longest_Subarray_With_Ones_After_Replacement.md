# Longest Subarray with Ones after Replacement

Given an array containing 0s and 1s, if you are allowed to replace no more than ‘k’ 0s with 1s, find the length of the longest contiguous subarray having all 1s.

Implementation:

```
import math
def longest_substring_with_ones_after_replacement(arr, k):
  max_len = - math.inf
  window_start = 0
  cntr = 0
  for i in range(len(arr)):
    if arr[i] == 1:
          cntr += 1
    max_len = max(max_len, i-window_start+1)

    if (i-window_start+1-cntr) > k:
        if arr[window_start] == 1:
            cntr -= 1
        window_start += 1

  return max_len

            
```

