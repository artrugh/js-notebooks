## Function Parameters

In JavaScript, functions can accept parameters, which are placeholders for values that are passed to the function when it's called.

-   Parameters are variables listed in the function definition.
-   They act as placeholders for values that will be passed to the function when it's called.
-   Parameters are specified within the parentheses following the function name.
-   Functions can have zero or more parameters.

In the example below, **name** is a parameter of the greet function:

```js
function greet(name) {
    console.log(`Hello, ${name}!`);
}
```

#### parameter default value

you can specify default values for function parameters. Default parameter values allow you to define a fallback value that will be used if the function is called without providing a value for that parameter. This feature is particularly useful for ensuring that functions behave predictably even when not all parameters are provided.

Here's how you can define default parameter values in JavaScript:

```js
function greet(name = "World") {
    console.log(`Hello, ${name}!`);
}

greet(); // Output: Hello, World!
greet("Alice"); // Output: Hello, Alice!
```

## Function Arguments:

Arguments are the actual values passed to a function when it's called. Arguments correspond to the parameters defined in the function declaration and number of arguments passed to a function must match the number of parameters declared in the function definition. Function arguments (parameters) work as local variables inside functions.

**NOTE**: Arguments are always passed by value and never passed by reference. This means that if a function reassigns a parameter, the value won't change outside the function. More precisely, object arguments are passed by sharing, which means if the object's properties are mutated, the change will impact the outside of the function.

#### The **arguments** object

When a function has been called and is running there is available to it in its local scope an arguments object. The arguments object is not an array but it is array-like. It has a length property whose value corresponds to the number of parameters that was passed to the function. It also has properties whose names are integers and hold the values that were passed as parameters.

```js
function fn(a, b, c) {
    console.log(arguments[0] == a); //logs 'true'
    console.log(arguments[1] == b); //logs 'true'
    console.log(arguments[2] == c); //logs 'true'
}
```

The arguments object is useful when the parameters passed to a function do not correspond to the parameters that were named and listed in the function definition.

```js
var exclaim = function (a) {
    var exclamation = a;
    if (arguments[1]) {
        exclamation = arguments[1];
    }
    return exclamation + "!!!";
};

exclaim("hello"); //'hello!!!'
exclaim("hello", "goodbye"); //'goodbye!!!
```

```js
function sum() {
    let total = 0;
    for (let i = 0; i < arguments.length; i++) {
        total += arguments[i];
    }
    return total;
}

sum(1, 2, 3); // Output: 6
```

It's important to note that while the **arguments** object provides flexibility for functions to accept varying numbers of arguments, it's generally recommended to use explicit parameters whenever possible for clarity and readability. Additionally, modern JavaScript introduces features like **rest parameters (...)** and the **spread operator (...)** for more concise and explicit handling of variable numbers of arguments. Rest parameters allow a function to accept an indefinite number of arguments as an array.

```js
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3)); // Output: 6
console.log(sum(1, 2, 3, 4, 5)); // Output: 15
```

## Return Value

In JavaScript, functions can return values using the **return** statement. The return statement ends the function execution and specifies the value to be returned. Functions can return any data type, including primitive types (e.g., numbers, strings, booleans) and complex types (e.g., objects, arrays, functions).

To return a value from a custom function, you need to use the return keyword.

By default, if a function's execution doesn't end at a return statement, or if the return keyword doesn't have an expression after it, then the return value is referenced as void or undefined.

The return statement allows you to return an arbitrary value from the function. One function call can only return one value, but you can simulate the effect of returning multiple values by returning an object or array and destructuring the result.

#### Functions as return values / passing functions as parameters

(**functions are first-class**)

Functions in Javascript can be returned from functions and can be passed to other functions as parameters. They can be assigned to variables and object properties and can be stored in arrays. They are **first-class** citizens.

Functions in Javascript are objects. Functions can have properties assigned to them, as we have already seen with the isArray method of the Array constructor. Functions are a special kind of object that can be called.
