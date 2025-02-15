# React setInterval Memory Leak
This example demonstrates a common mistake in React: using `setInterval` within a `useEffect` hook without a cleanup function. This leads to memory leaks because the interval continues to run even after the component unmounts.

The `bug.js` file contains the problematic code, while `bugSolution.js` provides the correct implementation.

## How to reproduce:
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the counter increasing even when the component is unmounted.

## Solution:
The solution involves returning a cleanup function from the `useEffect` hook. This function will clear the interval when the component is unmounted, preventing memory leaks.