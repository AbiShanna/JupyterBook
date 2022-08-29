# Flood Fill

Any image can be represented by a 2D integer array (i.e., a matrix) where each cell represents the pixel value of the image.
Flood fill algorithm takes a starting cell (i.e., a pixel) and a color. The given color is applied to all horizontally and vertically connected cells with the same color as that of the starting cell. Recursively, the algorithm fills cells with the new color until it encounters a cell with a different color than the starting cell.
Given a matrix, a starting cell, and a color, flood fill the matrix.

Implementation:

```
def floodFill(mat, i, j, new_val):
    cntNeighbors(mat, i, j, mat[i][j], new_val)
    return mat

def cntNeighbors(mat, i, j, old, new):
    if i<0 or i >= len(mat) or j < 0 or j >= len(mat[0]):
        return mat
    if mat[i][j] != old:
        return mat
    mat[i][j] = new

    cntNeighbors(mat, i+1, j, old, new)
    cntNeighbors(mat, i-1, j, old, new)
    cntNeighbors(mat, i, j+1, old, new)
    cntNeighbors(mat, i, j-1, old, new)
            
```

