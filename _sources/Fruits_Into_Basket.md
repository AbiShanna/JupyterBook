# Fruits into Baskets

You are visiting a farm to collect fruits. The farm has a single row of fruit trees. You will be given two baskets, and your goal is to pick as many fruits as possible to be placed in the given baskets.
You will be given an array of characters where each character represents a fruit tree. 

The farm has following restrictions:
    1. Each basket can have only one type of fruit. There is no limit to how many fruit a basket can hold.
    2. You can start with any tree, but you can’t skip a tree once you have started.
    3. You will pick exactly one fruit from every tree until you cannot, i.e., you will stop when you have to pick from a third fruit type.

Write a function to return the maximum number of fruits in both baskets.


Implementation:

```
import math

def fruits_into_basket(arr):
  max_cnt = - math.inf
  window_start = 0
  cntr = {}
  for i in range(len(arr)):
    if arr[i] not in cntr:
      cntr[arr[i]] = 1
    else:
      cntr[arr[i]] += 1
    
    while len(cntr) > 2:
      if cntr[arr[window_start]] == 1:
        del cntr[arr[window_start]]
      else:
        cntr[arr[window_start]] -= 1
      window_start += 1

    max_cnt = max (max_cnt, i-window_start+1)

  return max_cnt

```

