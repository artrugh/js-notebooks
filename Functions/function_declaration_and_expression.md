## Function Declaration and Expression

Function Declaration and Function Expression are two most common ways to define functions in JavaScript.

### Function Declaration:

A function declaration is a statement that defines a function using the function keyword followed by the function name, parameters, and function body enclosed in curly braces. Function declarations are **hoisted**, meaning they are moved to the top of their scope during the compilation phase. This allows them to be called anywhere within the scope, even before their actual declaration in the code.
Function declarations create named functions, making them easily identifiable in stack traces and debugging tools.

```js
function greet(name) {
    console.log(`Hello, ${name}!`);
}
```

### Function Expression:

A function expression defines a function as part of an expression. It typically involves assigning the function to a variable or passing it as an argument to another function.
Function expressions are **not hoisted**, meaning they cannot be called before their actual declaration in the code.
Function expressions can be named or anonymous, depending on whether a name is provided after the function keyword.

Example of named function expression:

```js
let greet = function sayHello(name) {
    console.log(`Hello, ${name}!`);
};
```

Example of anonymous function expression:

```js
let greet = function (name) {
    console.log(`Hello, ${name}!`);
};
```

#### Arrow Function Expression:

Introduced in ES6, providing a concise syntax for defining functions. Arrow functions can only be defined using function expressions. Unlike traditional function declarations, arrow functions cannot be declared using the function keyword.

```js
let greet = (name) => {
    console.log(`Hello, ${name}!`);
};
```

**NOTE**: Arrow function lexically binds the **this** value and does not have its own **this**, **arguments**, **super**, or **new.target**. This lexical binding means that an arrow function inherits the this value from its surrounding code, specifically the context in which it is defined. It doesn't have its own this binding. This behavior is particularly useful when working with object methods or callbacks where you want to retain the this value from the surrounding context.

Here's a simple example to illustrate the lexical binding of this in arrow functions:

```js
const obj = {
    name: "John",
    greet: function () {
        setTimeout(() => {
            console.log(`Hello, ${this.name}!`); // 'this' refers to the 'obj' object
        }, 1000);
    },
};

obj.greet(); // Outputs: Hello, John!
```

In the above example, the arrow function inside setTimeout preserves the this value from the greet method of the obj object, thanks to lexical scoping. Without arrow functions, the this value inside setTimeout would refer to the global object (or undefined in strict mode), which is not what we want in this case.

#### Immediately-invoked function expressions (IIFE)

IIFEs are commonly used to create functions that execute immediately. They are useful for encapsulating code and keeping variables within a local scope. Note the parentheses around the function expression, which are necessary to differentiate it from a function declaration.

```js
(function () {
    var a = 1;
    console.log(typeof a); //logs 'number'
})();

console.log(typeof a); //logs 'undefined'
```
