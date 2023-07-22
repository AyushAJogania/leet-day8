# leet-day8

# Minimum Initial Health to Rescue Princess - LeetCode Solution

## Problem Description

You are given a 2D grid representing a dungeon with rooms, and the goal is to rescue the princess located in the bottom-right corner of the dungeon. The knight starts from the top-left room and can only move either right or down at any point. Each room has an integer value representing the health gain or loss when entering the room. Entering a room with a positive value increases the knight's health, and entering a room with a negative value decreases the knight's health. The knight must keep his health above zero at all times during the journey.

The task is to find the minimum initial health that the knight must have in order to successfully rescue the princess.

## Example

Input:
```
dungeon = [[-2,-3,3],
           [-5,-10,1],
           [10,30,-5]]
```

Output:
```
7
```

Explanation: The initial health of the knight must be at least 7 if he follows the optimal path: RIGHT -> RIGHT -> DOWN -> DOWN.

## Approach

To solve this problem, we can use dynamic programming. We start by initializing a 2D `dp` array of the same size as the input `dungeon` array. We then calculate the minimum initial health needed to reach the bottom-right room starting from each cell and store the result in the `dp` array.

We start from the bottom-right corner of the dungeon and work our way backward to the top-left corner. For each cell, we calculate the minimum health required to reach the princess from that cell, considering the possible paths to move either right or down.

We update the `dp` array as follows:
- For the bottom-right cell, the minimum health required is the maximum of 1 and 1 - the value of that cell.
- For the cells in the last row and last column, the minimum health required is the maximum of 1 and the difference between the minimum health of the cell below or to the right and the value of the current cell.
- For other cells, the minimum health required is the maximum of 1 and the minimum of the difference between the minimum health of the cell below and the value of the current cell and the difference between the minimum health of the cell to the right and the value of the current cell.

Finally, the answer is stored in `dp[0][0]`, which represents the minimum initial health required when starting from the top-left room.

## Complexity Analysis

The time complexity of the solution is O(m * n), where m and n are the dimensions of the input dungeon. We need to fill the dp array for each cell once.

The space complexity is also O(m * n) as we use the dp array to store the minimum health values for each cell.

## Summary

The solution uses dynamic programming to calculate the minimum initial health required for the knight to rescue the princess from the dungeon. It starts from the bottom-right corner of the dungeon and works its way backward to the top-left corner, updating the dp array to store the minimum health required for each cell. The final answer is stored in dp[0][0]. The time complexity is O(m * n), and the space complexity is O(m * n).
