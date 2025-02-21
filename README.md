# Unexpected NaN with Loose Comparison and Undefined

This code demonstrates a common JavaScript error caused by using loose comparison (==) with null and undefined.  The `foo` function intends to return 0 if the input is null, but it incorrectly handles undefined, resulting in NaN.

## Bug

The primary issue is that `x === null` only checks for strict equality with null and does not catch undefined.  When `undefined` is passed, the addition `x + 1` attempts to add a number to undefined leading to NaN.

## Solution

The solution uses strict equality (`===`) to explicitly check for both `null` and `undefined` and handles them correctly.