# React useEffect Infinite Loop Bug
This repository demonstrates a common React bug: an infinite loop caused by an incorrectly implemented `useEffect` hook. 

The `bug.js` file contains the buggy code. The `bugSolution.js` file shows the corrected version.

## Bug Description
The `useEffect` hook in `bug.js` attempts to update the state variable `count` inside the effect, causing an infinite loop. The `useEffect` hook is designed to run after every render, and since the `setCount` call causes re-render, an endless cycle is created. This is because `count` is not included in the dependency array.  Adding `count` to the dependency array, as demonstrated in the solution, fixes the problem. 

## Solution
The solution lies in correctly specifying the dependencies for the `useEffect` hook. By adding `count` to the dependency array, `useEffect` will only run when `count` changes (hence fixing the infinite loop).