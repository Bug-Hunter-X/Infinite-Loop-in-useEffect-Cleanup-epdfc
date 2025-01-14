# React useEffect Cleanup Bug

This repository demonstrates a common bug in React's `useEffect` hook where the cleanup function incorrectly updates component state, leading to an infinite loop.  The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected implementation.

## Problem
The issue arises from attempting to modify the component's state (`count`) within the cleanup function of the `useEffect` hook.  This causes a re-render, which then calls the cleanup function again, creating an infinite loop.

## Solution
The solution involves removing the state update from the cleanup function.  State updates should ideally be performed within the main body of the `useEffect` function, not during cleanup.