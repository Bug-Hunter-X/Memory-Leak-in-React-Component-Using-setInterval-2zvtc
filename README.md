# React setInterval Memory Leak
This repository demonstrates a common mistake in React applications: using `setInterval` within a `useEffect` hook without proper cleanup. This can lead to memory leaks and unexpected behavior.

## Problem
The `MyComponent` component uses `setInterval` to update the count every second. However, it lacks a cleanup function in the `useEffect` hook. This means that when the component unmounts, the interval continues to run, causing a memory leak.

## Solution
The solution involves using the return value of `useEffect` to implement a cleanup function that clears the interval when the component is unmounted.