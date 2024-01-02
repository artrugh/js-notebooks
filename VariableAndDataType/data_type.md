## Data Type

Variables in JavaScript can hold various types of data such as strings, numbers, booleans, objects, or even functions. 

**Data types** define the types of values that can be used in the language. JavaScript has several data types:

- Primitive Data Types:
Number: Represents both integer and floating-point numbers. Example: 42, 3.14

    - String: Represents sequences of characters, enclosed in either single quotes (') or double quotes ("). Example: 'Hello', "JavaScript"

    - Boolean: Represents a logical value indicating true or false.

    - Null: Represents the intentional absence of any object value. It's a special value indicating the absence of value or no object.*

    - Undefined: Indicates a variable that has been declared but hasn’t been assigned a value. It's the default value of uninitialized variables.

    - Symbol (added in ECMAScript 2015): Represents a unique identifier.

- Non-Primitive Data Types:
    - Object: Represents a collection of key-value pairs. Objects are more complex and can hold various data and functionalities. Examples include arrays, functions, and more.

```js
// Number
let age = 25;
let temperature = 98.6;

// String
let greeting = 'Hello, World!';
let username = "Alice";

// Boolean
let isRaining = true;
let isValid = false;

// Null
let nullValue = null;

// Undefined
let undefinedValue;

// Symbol (ECMAScript 2015)
let uniqueID = Symbol('id');

// Object
let person = { name: 'John', age: 30 };
let fruits = ['apple', 'banana', 'orange'];
let sayHello = function() {
  console.log('Hello!');
};
```

### Null

In JavaScript, null is often mistakenly identified as an object, but it's not truly an object.

The erroneous classification of null as an object is actually a long-standing bug in JavaScript, existing since its early days. This is due to how JavaScript internally represents the null value.

While typeof null returns 'object', it's actually a primitive value. The null value represents the intentional absence of any object value. It's often considered a placeholder or an empty value signifying no value or no object.

This behavior of typeof null being 'object' is considered a quirk or historical bug in JavaScript, but null itself is not an object in the traditional sense. It's a unique primitive value in the language.