# React Native useCallback Hook Stale Closures

This repository demonstrates a common error encountered when using the `useCallback` hook in React Native: stale closures. Stale closures occur when a memoized function (created with `useCallback`) references state variables that change between renders.  The memoized function retains the old values, leading to incorrect results.

## Problem
The provided `bug.js` file showcases a scenario where `useCallback` is used incorrectly. The function `incrementCount` uses the state variable `count`, but the dependency array for `useCallback` is incorrect, leading to a stale closure and the function always using the value of `count` from the first render.

## Solution
The `bugSolution.js` file provides the corrected code. The dependency array for `useCallback` is now correctly set to include `count`, ensuring that the function is re-created whenever `count` changes, avoiding the stale closure issue.

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `npx react-native run-android` or `npx react-native run-ios`.
4. Observe the incorrect behavior in `bug.js` and the correct behavior in `bugSolution.js`.