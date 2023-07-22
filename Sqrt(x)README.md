# leet-day8

# Square Root of an Integer

This is a C++ solution for the LeetCode problem "Square Root of an Integer."

## Problem Statement

Given a non-negative integer `x`, we need to find its square root and round it down to the nearest integer. The returned integer should be non-negative as well.

You are not allowed to use any built-in exponent function or operator, such as `pow(x, 0.5)` in C++ or `x ** 0.5` in Python.

## Example

```
Input: x = 4
Output: 2
Explanation: The square root of 4 is 2, so we return 2.

Input: x = 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since we round it down to the nearest integer, 2 is returned.
```

## Approach

The problem can be solved efficiently using binary search. We initialize a left pointer to 1 and a right pointer to the given number `x`. We then perform binary search between `left` and `right` to find the square root.

We calculate the middle value `mid` using `(left + right) / 2` and check if `mid * mid` is less than or equal to `x`. If true, we update the answer to `mid` and set `left = mid + 1` to search for a larger value. Otherwise, we set `right = mid - 1` to search for a smaller value.

We continue the binary search until `left` is greater than `right`. The final answer will be stored in the variable `ans`.

## Complexity Analysis

The time complexity of this approach is O(log(x)), where x is the given integer. The binary search reduces the search space by half in each iteration.

The space complexity is O(1) as we are using only a constant amount of extra space.

**Note:** The main function in the code provides some test cases to demonstrate the usage of the `mySqrt` function.
