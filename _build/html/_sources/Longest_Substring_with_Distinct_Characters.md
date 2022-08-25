# Longest Substring with Distinct Characters

Given a string, find the length of the longest substring, which has all distinct characters.

Implementation:

```
import math
def longest_substring_with_distinct_chars(str1):
  max_len = - math.inf
  window_start = 0
  pos = {}
  for i in range(len(str1)):
    if str1[i] not in pos:
      pos[str1[i]] = i
    else:
      window_start = pos[str1[i]] + 1
      pos[str1[i]] = i

    max_len = max(max_len, i-window_start+1)

  return max_len

            
```

