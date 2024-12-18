# React 19 useEffect Infinite Loop Bug

This repository demonstrates a common but subtle bug in React 19's `useEffect` hook. The bug arises from an incomplete dependency array, leading to an infinite render loop.

## Bug Description

The `useEffect` hook is used to perform side effects after a component renders.  If the dependency array is not correctly defined, the effect may run unexpectedly, leading to infinite loops or other unexpected behavior.  In this example, if the `count` variable is not included in the dependency array, the `useEffect` hook will run on every render, causing the `console.log` to print continuously and the component to re-render indefinitely. 

## Solution

The solution is simple: include all variables used within the effect in its dependency array. By adding `count` to the dependency array, the effect now only runs when `count` changes, preventing the infinite loop.