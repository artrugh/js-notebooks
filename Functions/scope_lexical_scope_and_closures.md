## Scope

In JavaScript, scope refers to the visibility and accessibility of variables and functions within a particular portion of code during runtime. Understanding scope is crucial for writing organized, efficient, and bug-free JavaScript programs. There are 3 types of scope in JavaScript:

1. **Global Scope**:

-   Variables and functions declared outside of any function or block have global scope.
-   Global variables and functions are accessible from anywhere within the script, including inside functions and blocks.
-   Global variables can also be accessed from within nested functions and blocks.

```js
// Global scope
let globalVariable = "I am a global variable";

function globalFunction() {
    console.log("I am a global function");
}

globalFunction(); // Output: I am a global function
```

2. **Local Scope**:

-   Variables declared within a function or block have local scope.
-   Local variables are accessible only within the function or block in which they are declared, and they are not visible outside of their scope.
-   Each function or block creates its own scope, and nested functions or blocks have access to variables in their outer scopes.

```js
// Local scope
function outerFunction() {
    let localVariable = "I am a local variable";

    function innerFunction() {
        console.log(localVariable); // Accessible inside inner function
    }

    innerFunction();
}

outerFunction();
```

3. **Function Scope**

-   JavaScript has function scope: Each function creates a new scope.
-   Variables defined inside a function are not accessible (visible) from outside the function.
-   Variables declared with var, let and const are quite similar when declared inside a function.

#### Function Scope vs. Block Scope:

-   Introduction of let and const in ES6 brought block-level scoping.
-   let and const variables are block-scoped, unlike var which is function-scoped.

#### Scope Chain

Scope also follows a hierarchy known as the scope chain. When a variable is referenced in JavaScript, the JavaScript engine looks for that variable first in the current scope. If it's not found, it traverses up the scope chain until it finds the variable or reaches the global scope. This process ensures that variables are accessed in the correct scope.

Understanding scope is essential for writing maintainable and predictable JavaScript code. It helps prevent naming conflicts, promotes code organization, and improves code readability. Additionally, understanding scope is crucial for understanding closures, hoisting, and other advanced JavaScript concepts.

## Lexical context

**Lexical context**, also known as lexical scope, refers to the environment in which a piece of code is written or defined. In JavaScript, lexical scope is determined by the physical placement of code within the source code file. This means that variables and functions declared within a certain scope are accessible within that scope and any nested scopes.

When we talk about lexically binding the **this** value in JavaScript, it means that the value of this inside a function is determined by the function's lexical scope, rather than how the function is called. This behavior is particularly relevant when dealing with nested functions or functions used as callbacks, where the value of this might change depending on how the function is invoked.

In traditional functions (non-arrow functions), the value of this is dynamically determined at runtime based on how the function is called. This can lead to unexpected behavior, especially in nested functions or when passing functions as callbacks.

However, arrow functions in JavaScript lexically bind the this value, meaning that this inside an arrow function is determined by the surrounding lexical scope where the arrow function is defined. This behavior ensures that the this value inside an arrow function is always the same as the this value in the surrounding code.

Consider the following example to illustrate the difference:

```js
const obj = {
    name: "Alice",
    traditionalFunc: function () {
        console.log(this.name); // 'Alice'
        setTimeout(function () {
            console.log(this.name); // undefined (or error in strict mode)
        }, 1000);
    },
    arrowFunc: function () {
        console.log(this.name); // 'Alice'
        setTimeout(() => {
            console.log(this.name); // 'Alice'
        }, 1000);
    },
};

obj.traditionalFunc(); // Executes with traditional function
obj.arrowFunc(); // Executes with arrow function
```

## Closures

Closures are a fundamental concept related to the scope and the way functions work. A closure is created when a function is defined within another function (the outer function) and has access to the outer function's variables. Even after the outer function has finished executing, the inner function maintains access to the outer function's scope chain. In effect closures enable functions to remember and access variables of their parent scope.

Closures are widely used in JavaScript for various purposes like maintaining state in event handlers, implementing private variables and methods, and creating modules.

**Breakdown of closures:**

1. **Scope Chain**: In JavaScript, every function has access to variables defined in its outer scope. This access forms a scope chain. When a function is defined within another function, it has access to the variables of its outer function and all the scopes above it in the hierarchy.

2. **Access to Outer Variables**: The inner function has access to its own variables, variables in the outer function, and global variables. This access to outer variables, even after the outer function has finished executing, is what creates a closure.

3. **Encapsulation**: Closures allow for encapsulation and data privacy. You can define variables in the outer function that are inaccessible from outside, but can still be accessed and modified by the inner function. This is commonly used in JavaScript to create private variables and methods.

4. **Persistent Scope**: Closures "remember" their lexical environments. Even after the outer function has completed execution and its local variables have gone out of scope, the inner function maintains access to those variables.
