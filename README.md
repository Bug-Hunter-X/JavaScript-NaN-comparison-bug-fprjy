# JavaScript NaN Comparison Bug

This repository demonstrates a common JavaScript bug related to the comparison of NaN (Not a Number) using loose equality (==).  The `foo` function attempts to classify numbers as negative, zero, or positive. However, due to the peculiarities of NaN, the function incorrectly classifies NaN as positive.

## Bug Description

The issue lies in how JavaScript handles NaN in loose comparisons.  NaN is never equal to itself, nor is it equal to any other value (including NaN). Therefore, the `x === null` condition won't catch NaN. Instead, the `else` block executes, causing the function to incorrectly return 1.

## Solution

To correctly handle NaN, use the `Number.isNaN()` function, which explicitly checks for NaN.  This provides a robust solution that addresses the unexpected behavior.

## How to reproduce

1. Clone this repository.
2. Run `bug.js` using Node.js (or your preferred JavaScript runtime): `node bug.js`
3. Observe the incorrect output for the NaN input.
4. Then run `bugSolution.js` to see the corrected output.
