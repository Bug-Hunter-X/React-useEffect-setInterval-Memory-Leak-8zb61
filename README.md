# React useEffect setInterval Memory Leak
This repository demonstrates a common React bug involving memory leaks due to improper use of `setInterval` within the `useEffect` hook. The problem arises when an interval is started inside `useEffect` without providing a mechanism to clear it when the component unmounts or the effect is updated.

## Bug Description:
The `MyComponent` uses `setInterval` to update a counter every second. However, the interval is never cleared.  This leads to the interval continuing to run even after the component is unmounted, causing a memory leak.   The solution demonstrates how to correctly use `setInterval` with `useEffect` by clearing the interval in the cleanup function to prevent memory leaks.

## How to reproduce the bug:
1. Clone the repository.
2. Run `npm install`
3. Run `npm start`
4. Observe that the counter continues to increment even after the component is unmounted (you'll need your browser's developer tools to confirm this, perhaps checking for memory usage over time).

## How to fix the bug:
The solution provided shows how to use the cleanup function to clear the interval when the component unmounts, preventing memory leaks.