# leet-day24

# Matrix Search

## Problem Description

You are given an m x n integer matrix `matrix` with the following two properties:

1. Each row is sorted in non-decreasing order.
2. The first integer of each row is greater than the last integer of the previous row.

Given an integer `target`, return `true` if `target` is in the matrix, or `false` otherwise.

You must write a solution in O(log(m * n)) time complexity.

## Example

### Input

```cpp
matrix = [
  [1, 3, 5, 7],
  [10, 11, 16, 20],
  [23, 30, 34, 60]
]
target = 3
```

### Output

```cpp
true
```

### Explanation

In the given matrix, the value `3` is present, so the function returns `true`.

## Constraints

- `m == matrix.length`
- `n == matrix[i].length`
- `1 <= m, n <= 100`
- `-10^4 <= matrix[i][j], target <= 10^4`

## Approach

To solve this problem in O(log(m * n)) time complexity, we can use a binary search approach. Since the matrix has the property that each row is sorted in non-decreasing order, we can treat the entire matrix as a single sorted array and perform a binary search on it to find the target element.

The key idea is to map the two-dimensional matrix indices to one-dimensional array indices to perform binary search. For an element at `matrix[i][j]`, the corresponding index in the one-dimensional array would be `index = i * n + j`, where `n` is the number of columns in the matrix.

## Complexity Analysis

- Time complexity: O(log(m * n)) - The binary search reduces the search space by half in each iteration, making it logarithmic in terms of the total number of elements in the matrix.
- Space complexity: O(1) - The binary search is performed in-place without using any additional space that scales with the input size.
