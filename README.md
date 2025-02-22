# React useEffect setInterval memory leak
This example demonstrates a common error in React when using the `useEffect` hook with `setInterval`.  Forgetting to clear the interval in the cleanup function leads to memory leaks and unexpected behavior. The `bug.js` file shows the incorrect implementation, while `bugSolution.js` provides the corrected version.

## Problem
The `setInterval` function, when used within `useEffect` without proper cleanup, continues to run even after the component unmounts. This results in unnecessary updates and potential memory leaks, which can negatively impact application performance and stability. 

## Solution
The solution involves using the return function provided by the `useEffect` hook to clear the interval using `clearInterval` before the component unmounts. This ensures that the interval is stopped, preventing resource wastage and resolving the memory leak.