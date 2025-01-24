# React useEffect Cleanup Function Missing Return Statement

This repository demonstrates a common error in React's `useEffect` hook: forgetting to return a cleanup function.  This can lead to memory leaks and unexpected behavior, particularly when dealing with asynchronous operations like `fetch` calls.

## The Problem

The `bug.js` file shows an example where a `fetch` call is made within a `useEffect` hook.  However, the code is missing a `return` statement within the `useEffect`'s callback.  This means that when the component unmounts, the in-flight fetch request isn't aborted, potentially leading to a memory leak.

## The Solution

The `bugSolution.js` file provides the corrected code.  A cleanup function is returned, which ensures that any ongoing asynchronous operations are cleaned up when the component unmounts.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the behavior in both the `bug.js` and `bugSolution.js` components.

## Learning Points

- Always remember to return a cleanup function from `useEffect` when dealing with asynchronous operations or subscriptions.
- Cleanup functions are essential for preventing memory leaks and ensuring components behave predictably.