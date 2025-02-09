# TypeScript Closure Issue with setTimeout in Loop

This repository demonstrates a common closure issue in TypeScript when using `setTimeout` within a loop. The problem arises because the closure created by the `setTimeout` callback function captures the variable `i` by reference, not by value.  Therefore, by the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` holds its final value.

## Problem

The `printNumbers2` function intends to print numbers from 1 to `n` with a slight delay. However, due to the closure issue, it prints the final value of `i` (which is `n + 1`) multiple times.

## Solution

The solution involves creating a new immediately invoked function expression (IIFE) to capture the current value of `i` in a new scope for each iteration. This ensures that each callback function has its own copy of `i`. 