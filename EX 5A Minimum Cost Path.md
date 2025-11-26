# EX 5A Minimum Cost Path
## DATE:29-10-2025
## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.

## Algorithm

1. Input dimensions `R` and `C`.
2. Initialize a 2D table `tc` of size `R x C`.
3. Set starting point `tc[0][0] = cost[0][0]`.
4. Fill first column of `tc` with cumulative vertical path sums.
5. Fill first row of `tc` with cumulative horizontal path sums.
6. Loop through remaining cells `(i, j)`.
7. For each cell, calculate minimum cost from top, left, and diagonal.
8. Add current cell's cost to that minimum.
9. Store the result in `tc[i][j]`.
10. Return `tc[m][n]` as the minimum cost to reach cell `(m, n)`.  

## Program:
```
A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.
Developed by: RIZWAN T
Register Number:  212222040134
```
```PY
R = int(input())
C = int(input())
def minCost(cost, m, n):
 
    tc = [[0 for x in range(C)] for x in range(R)]
    tc[0][0] = cost[0][0]
    for i in range(1, m+1):
        tc[i][0] = tc[i-1][0] + cost[i][0]
    for j in range(1, n+1):
        tc[0][j] = tc[0][j-1] + cost[0][j]
    for i in range(1, m+1):
        for j in range(1, n+1):
            tc[i][j] = min(tc[i-1][j-1], tc[i-1][j], tc[i][j-1]) + cost[i][j]
    return tc[m][n]
 
cost = [[1, 2, 3],
        [4, 8, 2],
        [1, 5, 3]]
print(minCost(cost,2,2))
```
## Output:

![image](https://github.com/user-attachments/assets/5b7ad7fb-cd5e-426f-bb66-55a327dba188)



## Result:
Thus the above program was executed successfully for finding the minimum cost.
