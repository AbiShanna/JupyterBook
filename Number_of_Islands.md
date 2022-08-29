# Number of Islands

Given a 2D array (i.e., a matrix) containing only 1s (land) and 0s (water), count the number of islands in it.
An island is a connected set of 1s (land) and is surrounded by either an edge or 0s (water). Each cell is considered connected to other cells horizontally or vertically (not diagonally).

Implementation:

```
def numberOfIslands(mat):
    cnt = 0
    for i in range(len(mat)):
        for j in range(len(mat[0])):
            if mat[i][j] == 1:
                cnt += 1
                findNeighbors(mat, i, j)
    return cnt

def findNeighbors(mat, i, j):
    if i < 0 or i >= len(mat) or j < 0 or j>= len(mat[0]):
        return
    if mat[i][j] == 0:
        return
    mat[i][j] = 0
    findNeighbors(mat, i+1, j)
    findNeighbors(mat, i-1, j)
    findNeighbors(mat, i, j+1)
    findNeighbors(mat, i, j-1)
            
```

