# React setInterval Memory Leak

This repository demonstrates a common memory leak in React components that use `setInterval` without proper cleanup within the `useEffect` hook.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides the corrected version.

**Problem:** The original code uses `setInterval` to update a counter every second. However, it fails to clear the interval when the component unmounts, leading to a memory leak.  The interval continues to run even after the component is removed from the DOM, causing unnecessary updates and potentially impacting performance.

**Solution:** The corrected code includes a cleanup function within the `useEffect` hook. This function uses `clearInterval` to stop the interval when the component unmounts, preventing the memory leak.