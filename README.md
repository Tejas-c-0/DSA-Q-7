# Sqrt(x)

## Problem
Given a non-negative integer `x`, return the integer square root of `x`.  
The result should be the largest integer such that its square is less than or equal to `x`.

---

## Approach
- Use Binary Search on range [0, x]
- Find mid and check mid * mid
- If mid² ≤ x → move right
- Else → move left
- Continue until search space is reduced

---

## Complexity
- Time: O(log n)
- Space: O(1)

---

## Key Insight
We are searching for the largest number whose square is ≤ x using binary search.

---

## Example
Input: x = 8  
Output: 2  

Input: x = 16  
Output: 4  

---

## Code
```python
def mySqrt(x):
    left, right = 0, x

    while left <= right:
        mid = (left + right) // 2

        if mid * mid == x:
            return mid
        elif mid * mid < x:
            left = mid + 1
        else:
            right = mid - 1

    return right
