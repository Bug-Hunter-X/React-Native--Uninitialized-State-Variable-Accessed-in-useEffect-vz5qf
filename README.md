# React Native: Uninitialized State Variable Accessed in useEffect

This repository demonstrates a common error in React Native applications: accessing a state variable before it has been initialized within a `useEffect` hook.  This occurs because the state variable is undefined until the component has mounted and rendered at least once.

## Problem

The `bug.js` file contains code that attempts to log the state variable `count` inside a `useEffect` hook with an empty dependency array `[]`.  This means the effect runs only once after the component mounts. However, at this point, `count` is still undefined, resulting in an error.

## Solution

The `bugSolution.js` file provides a solution using the optional second parameter in `useEffect` to avoid the error. By adding `count` as a dependency, the effect only runs after the state variable is initialized and updated.