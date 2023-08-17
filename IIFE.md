# Immediate Invoke Function Exprection(IIFE)

IIFE stands for Immediately Invoked Function Expression. It is a common design pattern in JavaScript where a function is defined and executed immediately after its creation. IIFE is often used to create a private scope for variables, preventing them from polluting the global scope, and to encapsulate code to avoid naming conflicts.

## Syntax:

```javascript
(function () {
  // Your code here
})();
```

**Let's break down the components of an IIFE:**

1. (function() { ... }): This is an anonymous function expression enclosed in parentheses. It's not given a name because it's intended to be executed immediately and not reused elsewhere.

2. (): Following the function expression, an additional set of parentheses () is added. This set of parentheses is what triggers the immediate execution of the function.

### example:

```javascript
(function () {
  var privateVariable = "I am private";

  console.log("Inside IIFE:", privateVariable);
})();

// This would result in an error because privateVariable is not accessible here
// console.log("Outside IIFE:", privateVariable);
```

In this example, privateVariable is scoped within the IIFE, and attempting to access it outside the IIFE would result in an error. This demonstrates how IIFE can help encapsulate variables and prevent them from leaking into the global scope.
