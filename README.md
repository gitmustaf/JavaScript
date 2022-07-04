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

## Execution Context

- JavaScript engine creates a new context whenever it's about to execute a *function* or *script*. Every script/code starts with an execution
  context called **global execution context**. Every time we call a function, a new execution context is created and is put on top of the call/execution stack.
- Execution context has two phase:
- **Creation Phase:**
  - VariableEnvironment component is used for the initial storage for the variables, arguments and function declarations. The var declared variables
    are initialized with the value of *undefined*.
  - The value of *this* is determine.
  - LexicalEnvironment is just the copy of VariableEnvironment at this stage.
- **Execution Phase:**
  - Values are assigned.
  - LexicalEnvironment is used to resolve the bindings.

## Lexical Environment

- Whenever an execution context is created a lexical environment is also created.
- A lexical environment consist of two main components: the **environment record** and a **reference** to the outer(parent) lexical environment.
- Lexical environment is the local memory along with the reference of its parent's lexical environment.
  
## Identifier Resolution aka Scope chain

- The scope is where a variable is available in your code. Each block of code creates scope and a lexical environment.
- If identifiers are not resolved in the current environmentRecord, the resolution process will continue to the outer (parent) environment record table. 
  This pattern will continue until the identifier is resolved. If not found, a ReferenceError is thrown.
- Way of finding variables is called scope chain.

__References__

- [Namaste JavaScript Ep.7](https://youtu.be/uH-tVP8MUs8)
- [Medium Article](https://amnsingh.medium.com/lexical-environment-the-hidden-part-to-understand-closures-71d60efac0e0)