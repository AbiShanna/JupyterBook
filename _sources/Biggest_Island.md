# Biggest Island

Given a 2D array (i.e., a matrix) containing only 1s (land) and 0s (water), find the biggest island in it. Write a function to return the area of the biggest island.
An island is a connected set of 1s (land) and is surrounded by either an edge or 0s (water). Each cell is considered connected to other cells horizontally or vertically (not diagonally).

Implementation:

```
import math
class Solution:
    def biggestIsland(self, mat):
        cnt = -math.inf
        for i in range(len(mat)):
            for j in range(len(mat[0])):
                if mat[i][j] == 1:
                    cnt = max(cnt, self.cntNeighbors(mat, i, j))
        return cnt

    def cntNeighbors(self, mat, i, j):
        if i<0 or i >= len(mat) or j < 0 or j >= len(mat[0]):
            return 0
        if mat[i][j] == 0:
            return 0
        mat[i][j] = 0

        return (1+self.cntNeighbors(mat, i+1, j)+ self.cntNeighbors(mat, i-1, j) + self.cntNeighbors(mat, i, j+1) + self.cntNeighbors(mat, i, j-1))
            
```

