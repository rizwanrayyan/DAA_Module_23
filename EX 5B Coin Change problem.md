# EX 5B Coin Change Problem
## DATE:29-10-2025
## AIM:
To compute the fewest number of coins that we need to make up the amount given.


## Algorithm

1. Input the number of coins `n` and the `target` amount.
2. Read the coin denominations into array `S` of size `n`.
3. Define a recursive function `count(S, n, target)` to compute ways to make `target` using first `n+1` coins (0 to n).
4. Base Case 1: If `target == 0`, return 1 (one valid way found).
5. Base Case 2: If `target < 0` or `n < 0`, return 0 (no valid way).
6. Recursive Case:
   * Include the current coin `S[n]` in the sum: call `count(S, n, target - S[n])`.
   * Exclude the current coin: call `count(S, n - 1, target)`.
7. Add the results of both recursive calls to get total ways for current state.
8. Return this total.
9. In `main`, call `count(S, len(S)-1, target)` and print the result.
10. Output: Total number of combinations to make up the given `target`.

## Program:
```
Create a python function to compute the fewest number of coins that we need to make up the amount given.
Developed by: RIZWAN T
Register Number:  212222040134
```
```PY
def count(S, n, target):
    if target == 0:
        return 1
    if target < 0 or n < 0:
        return 0
    incl = count(S, n, target - S[n])
    excl = count(S, n - 1, target)
    return incl + excl
    
    
    
if __name__ == '__main__':
    S = []#[1, 2, 3]
    n=int(input())
    target = int(input())
    for i in range(n):
        S.append(int(input()))
    print('The total number of ways to get the desired change is',
        count(S, len(S) - 1, target))
```

## Output:

![image](https://github.com/user-attachments/assets/eb651ba3-6899-4f9b-acef-875cf19fe5d7)



## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
