# Longest Substring with Same Letters after Replacement

Given a string with lowercase letters only, if you are allowed to replace no more than ‘k’ letters with any letter, find the length of the longest substring having the same letters after replacement.

Implementation:

```
import math
def longest_substring_with_same_letters_after_replacement(str1, k):
  max_len = - math.inf
  window_start = 0
  cntr = {}
  for i in range(len(str1)):
    if str1[i] not in cntr:
          cntr[str1[i]] = 0
    cntr[str1[i]] += 1
    max_len = max(max_len, i-window_start+1)

    if (i-window_start+1-cntr[str1[i]]) > k:
        cntr[str1[i]] -= 1
        window_start += 1

  return max_len

            
```

