# React useEffect Hook Runs on Every Render

This repository demonstrates a common issue with the React `useEffect` hook where it runs on every render instead of only when the dependency array changes. This leads to unnecessary re-renders and potential performance problems.

## Bug

The `bug.js` file contains a component that uses `useEffect` to log the current count.  However, the dependency array is missing, causing it to run on every render.

## Solution

The `bugSolution.js` file shows the corrected code.  By adding `[count]` as a dependency array, `useEffect` only runs when the `count` variable changes.

## How to reproduce the bug:

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console output. You will see that the log message appears on every render.

## How to fix the bug:

1. Review the provided solution in `bugSolution.js`.
2.  Pay close attention to the dependency array in the `useEffect` hook.
3.  Make sure that any values from the component's scope that are used inside the effect are included in the dependency array.   Forgetting to include a dependency variable, even an indirectly referenced one, in the dependency array is a common cause of this kind of problem. 
4. If you don't need the effect to run based on any dependencies, you can use an empty array, `[]`, as the second argument to the `useEffect` hook.