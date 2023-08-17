# Let And Var

Both `let` and `var` are primitive data types and their memory stored in stack. But their main difference is their scope [Block] and [Functional] Scope .

## <span style="color:#7df0ec">Scope</span>

### <span style="color:#ae72c2">Block Scope</span>

'Block scope refers to the area within curly braces {} that defines a block of code, such as within an if statement or a loop. Variables declared with let are block-scoped, which means they are confined to the block in which they are defined.

```javascript
{
  let blockScoped = "I am block-scoped";
  var functionScoped = "I am function-scoped";
}

console.log(blockScoped); // Error: blockScoped is not defined
console.log(functionScoped); // Outputs: "I am function-scoped"
```

In this example, functionScoped is accessible within the entire function, including inside the if block. However, blockScoped is limited to the block where it's defined and cannot be accessed outside that block.

### <span style="color:#ae72c2">Hoisting</span>:

Both let and var are hoisted, which means their declarations are moved to the top of their respective scope during compilation. However, let variables are not initialized before their declaration, leading to the concept of the "Temporal Dead Zone" (TDZ).

```javascript
console.log(hoistedVar); // Outputs: undefined
console.log(hoistedLet); // Throws: ReferenceError: Cannot access 'hoistedLet' before initialization

var hoistedVar = "I am hoisted using var";
let hoistedLet = "I am hoisted using let";
```

In this example, even though both hoistedVar and hoistedLet are hoisted, accessing hoistedLet before its declaration results in a TDZ error because let variables are not initialized until their declaration.

## <span style="color:#72dbc1">Conclusion</span>:

In general, it's recommended to use let and const for variable declarations due to their block scoping and better handling of hoisting. var is still used in some cases, but its behavior can sometimes lead to unintended consequences.
