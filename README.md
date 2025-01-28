# React useEffect setInterval Memory Leak

This repository demonstrates a common memory leak in React applications caused by improper use of the `setInterval` function within the `useEffect` hook.  The provided `bug.js` file shows the incorrect implementation, while `bugSolution.js` offers the corrected version.

**Problem:**
The original code lacks a cleanup function in the `useEffect` hook, which prevents `setInterval` from being cleared when the component unmounts. This leads to the interval continuing to run indefinitely, consuming resources and potentially causing a memory leak.

**Solution:**
The `bugSolution.js` file demonstrates the correct approach.  A cleanup function is returned from the `useEffect` hook, allowing `clearInterval` to stop the interval when the component unmounts or when the dependency array changes.