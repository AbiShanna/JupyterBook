# Longest Substring with K Distinct Characters

Given a string, find the length of the longest substring in it with no more than K distinct characters.
You can assume that K is less than or equal to the length of the given string.

Implementation:

```
import math
def longest_substring_with_k_distinct_chars(arr, k):
  max_len = - math.inf
  window_start = 0
  cntr = {}
  for i in range(len(arr)):
    if arr[i] not in cntr:
      cntr[arr[i]] = 1
    else:
      cntr[arr[i]] += 1
    if len(cntr) == k:
      max_len = max(max_len, i - window_start+1)
    while len(cntr) > k:
      if cntr[arr[window_start]] == 1:
        del cntr[arr[window_start]]
      else:
        cntr[arr[window_start]] -= 1
      window_start += 1
  return max_len

```

