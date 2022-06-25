# JavaScript

Documenting the rescuers and topics of JavaScript

## How JavaScript Executes code

- Everything in JavaScript happens inside execution context.
- Execution context has two components memory(variable environment) and code(thread of execution).
- Execution context works in two phases, memory creation/allocation phase and code execution phase.
- Call stack maintains the order of execution of execution context.
  
__References__

- [Namaste JavaScript Ep.2](https://youtu.be/iLWTnMzWtj4)

## Hoisting in JavaScript

- In JavaScript hoisting allows to access functions and variables before they are declared.
- JavaScript hoists declarations to the top of their containing scope before execution.

- ### Variable hoisting

  - Variables declared using `var` are hoisted and initialized with default `undefined` value.
  - Variables declared using `let` or `const` are hoisted partially(hoisted but not initialized with any default value).
  - TDZ(Temporal Dead Zone):
    - A let or const variable said to be in TDZ from the start of the block until the code execution reaches the line where the variable is declared.
    - TDZ is also present in default function parameters(which are evaluated left to right).
  - Variables initialized with out any declaration are not hoisted.

  > Variable hoisting is discouraged, since it can cause unwanted behavior in the code.

- ### Function hoisting

  - Only function declarations are hoisted. Function expressions or arrow functions are not.

  > Function hoisting is useful because we can hide function implementation farther down in the file and let the reader focus on what the code is doing.

__References__

- [Namaste JavaScript Ep.3](https://youtu.be/Fnlnw8uY6jo)
- [freeCodeCamp hoisting article](https://www.freecodecamp.org/news/what-is-hoisting-in-javascript/)
- [MDN hoisting article](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)