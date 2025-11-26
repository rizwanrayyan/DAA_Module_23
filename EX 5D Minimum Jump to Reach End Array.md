# EX 5D Minimum Jump to Reach End Array
## DATE:29-10-2025
## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.

## Algorithm:
```
1. If start index `l` equals end index `h`, return 0.
2. If `arr[l]` is 0, return infinity (no further moves possible).
3. Initialize `min` to infinity.
4. For each reachable index `i` from `l + 1` to `l + arr[l]`, recursively find minimum jumps from `i` to `h`.
5. Update `min` if a smaller jump count is found.
6. Return the minimum jumps required from `l` to `h`.
```

## Program:
```
Developed by: RIZWAN T
Register Number:212222040134
```
```py
def minJumps(arr, l, h):
    if (h == l):
        return 0
    if (arr[l] == 0):
        return float('inf')
    min = float('inf')
    for i in range(l + 1, h + 1):
        if (i < l + arr[l] + 1):
            jumps = minJumps(arr, i, h)
            if (jumps != float('inf') and
                       jumps + 1 < min):
                min = jumps + 1
 
    return min
    
arr = []
n = int(input()) 
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr, 0, n-1))
 
```

## Output:
![image](https://github.com/user-attachments/assets/e30c1926-40da-456e-a088-9a0e5fc71b2f)


## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.
