# React useEffect Hook Memory Leak with setInterval

This repository demonstrates a common mistake when using the `setInterval` function within a React `useEffect` hook. The issue arises from forgetting to clear the interval when the component unmounts, which results in a memory leak.

## Bug Description
The `MyComponent` uses `setInterval` to update a counter every second. However, it lacks a cleanup function within the `useEffect` hook to clear the interval when the component is unmounted. This leads to a continuous update cycle even after the component is no longer rendered, causing a memory leak.

## Bug Solution
The solution is to use the return value of `useEffect` to perform cleanup. This allows us to `clearInterval` before the component unmounts, preventing any memory leaks.

## How to reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the counter in the browser, and then unmount the component by navigating away or closing the tab. The interval will still continue in the background.