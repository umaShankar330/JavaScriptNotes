# Execution Context and Call Stack In Js

### What really Happens When we run the js code

At first when we run the js code ,It basically creates a `globalcontext` and In that Global context There will be three Phases 
1. `Memory Creation Phase`.  
  &darr;       
2. `Code Execution Phase` [where the code is executed in a single thread meaning line by line].  
&darr;
3. `Deletion Phase` [Where the created execution context is deleted.]

---
### Types of execution Phase In Js

There are `two types` of execution Phases in Js:
1. `Global Execution Phase`.
2. `Function Execution Phase`.
---
### ->Let us Understand with an example

```javascript
let x =2;
function multiplyBy5(num){
  let result=num*5 
  return result 
}
let num1=multiplyBy5(x)
let num2=multiplyBy5(3)

```

In this above example when we run the file. At first The js engine creates\allocates a memory for  `globalexecution context`.  
**`Phase 1 In Memory creation`**:  
At first the data is stored in `key:value` pairs variable are declared and assigned with `undefined` value Look at below img  

<img src="https://res.cloudinary.com/dwux3vh4t/image/upload/v1692377514/firstPhase_k6e2tg.png" alt="Image" width="550" height="350">


**`phase 2 Code Execution`**:
Here the code is excuted `line by line` which means it is a single threaded. ANd the values to the variables are assigned.

But When a `function` is `Invoked` A new `Function excution Context` is **Opened or created**, And the code is stopped at that line and wait for the completion of function execution context all phases which includes creation,assigning and deletion and at last the value returned from function is assigned to the variable.

Now look at num1 and num2 both are invoking the function multiplyBy5 Which creates two function Execution context for both of them. Look at given images and understand.

<img src="https://res.cloudinary.com/dwux3vh4t/image/upload/v1692377522/func1Gec_h6tgjt.png" alt="Image" width="550" height="350">  

<img src="https://res.cloudinary.com/dwux3vh4t/image/upload/v1692377532/func1gecdelete_qywyv1.png" alt="Image" width="550" height="350">  

Here for `num1` FUnction Execution context is `created , assigned and deleted`.  

<img src="https://res.cloudinary.com/dwux3vh4t/image/upload/v1692377551/func2gec1_hdjscn.png" alt="Image" width="550" height="350">  

Same goes for `num2` also.  

And finally **code execution** is completed the **global execution context** is also **deleted** from **memory** of the **js engine**.  

<img src="https://res.cloudinary.com/dwux3vh4t/image/upload/v1692377560/Gec_Delete_wg8lga.png" alt="Image" width="550" height="350">  

This how execution context in js works .  

# Call stack in Js

The call stack is a fundamental concept in JavaScript (and many other programming languages) that helps manage the execution of functions and keeps track of their order. It plays a crucial role in understanding how function calls, execution, and control flow work in JavaScript.

The call stack is a data structure that operates like a stack (a last-in, first-out data structure). It keeps track of function calls and their corresponding execution contexts. Here's how the call stack works in JavaScript:

1. **Function Calls and Execution Contexts:**
   - When a function is called, a new execution context is created for that function. This context includes information about the function's local variables, arguments, and its own scope.
   - The newly created execution context is pushed onto the call stack.

2. **Stacking Function Calls:**
   - As more functions are called, their execution contexts are stacked on top of each other in the call stack.
   - The most recently called function's execution context is at the top of the stack, and the least recently called function's execution context is at the bottom.

3. **Execution of Functions:**
   - The JavaScript engine starts executing the code inside the currently active (topmost) execution context on the call stack.
   - If a function calls another function, a new execution context is created for the called function, and it is pushed onto the call stack on top of the current one.
   - This process continues as long as there are more function calls.

4. **Function Completion:**
   - When a function completes its execution, its execution context is popped off the call stack, and the control returns to the context below it.
   - The JavaScript engine moves to the next function in the call stack and continues execution.

5. **Recursion:**
   - Recursion is a scenario where a function calls itself. In this case, each recursive call creates a new execution context that is added to the call stack.
   - The call stack grows with each recursive call and shrinks as the recursive calls complete and their contexts are popped off.

6. **Stack Overflow:**
   - If the call stack becomes too large (e.g., due to excessive recursion), it can lead to a "stack overflow" error. This happens when the available stack space is exhausted.

It's important to manage the call stack effectively to avoid issues like stack overflow errors and to understand the sequence in which functions are executed. Asynchronous operations, like callbacks and promises, work in conjunction with the call stack and other components like the event loop to handle non-blocking behavior and keep the program responsive.

Remember that the call stack is just one part of JavaScript's runtime environment. Other components like the heap (for memory allocation) and the event loop (for managing asynchronous operations) are also critical for understanding the complete picture of how JavaScript code is executed.
