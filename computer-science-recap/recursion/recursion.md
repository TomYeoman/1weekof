# Recursion

Recursion is a form of iteration, where the function recalls itself in order to arrive at a result

Recursion is gernally a very expensive operation memory wise, as we have to build up a call stack in memory before unwinding it to arrive at a result.

### Base case

The first thing we should think of when performing any recursion is the base case for the function.

They should generally be agressive ( I.E prefer `n < 1` rather than `n === 0` within the fibonacci in order to prevent an infinite loop when provided a negative number )

> Example 1 - Fibonacci

`X - 1   2   3   4   5 `

`F - 1   1   2   3   5 `

```javascript

// Recursive version
const fibonacci_recursion = (n) => {
  if (n < 2) {
    return n;
  }
  return fibonacci_recursion(n-1) + fibonacci_recursion(n-2)
}
```