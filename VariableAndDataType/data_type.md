## Data Type

Variables in JavaScript can hold various types of data such as strings, numbers, booleans, objects, or even functions.

**Data types** define the types of values that can be used in the language. JavaScript has several data types that can be broadly categorized into two groups: primitive data types and reference data types.

### Primitive Data Types:

In programming languages are called "primitive" because they are fundamental, basic building blocks upon which more complex data types and structures are built. They are not composed of smaller parts and are not defined in terms of other data types.

**Simple Structure**:

-   Primitive data types are atomic and represent single values.
-   They are indivisible and do not have any methods or properties.
-   Examples include numbers, strings, booleans, null, undefined, and symbols (in some languages).

**Immutable**:

-   Primitive values are immutable, meaning they cannot be changed after they have been created.
-   Any operation that appears to modify a primitive value actually creates a new value.
-   For example, if you concatenate two strings, you create a new string rather than modifying the existing ones.

**Stored by Value**:

-   Primitive values are typically stored directly in memory locations known as stack memory.
-   When you assign a primitive value to a variable, a copy of that value is made and stored in the variable.
-   Operations on primitive values work directly with the actual value stored in memory.

In Java Script there are 6 Primitive Data Types:

-   **Number**: Represents both integer and floating-point numbers. Example: 42, 3.14

-   **String**: Represents sequences of characters, enclosed in either single quotes (') or double quotes ("). Example: 'Hello', "JavaScript"

-   **Boolean**: Represents a logical value indicating true or false.

-   **Null**: Represents the intentional absence of any object value. It's a special value indicating the absence of value or no object.\*

-   **Undefined**: Indicates a variable that has been declared but hasn’t been assigned a value. It's the default value of uninitialized variables.

-   **Symbol** (added in ECMAScript 2015): Represents a unique identifier.

```js
// Number
let age = 25;
let temperature = 98.6;

// String
let greeting = "Hello, World!";
let username = "Alice";

// Boolean
let isRaining = true;
let isValid = false;

// Null
let nullValue = null;

// Undefined
let undefinedValue;

// Symbol (ECMAScript 2015)
let uniqueID = Symbol("id");
```

### Non-Primitive (Reference) Data Types:

Object: Represents a collection of key-value pairs. Objects are more complex and can hold various data and functionalities. Examples include arrays, functions, and more. Objects are Reference Data Types - they hold references to values stored in memory. Manipulating a reference data type means manipulating reference to the value not the value itself.

**Complex Structure**:

-   Non-primitive data types are more complex and can represent collections of data or objects composed of multiple values and methods.
-   They are composed of primitive data types or other reference data types.
-   Examples include arrays, objects, functions, and dates.

**Mutable**:

-   Non-primitive values are mutable, meaning they can be modified after they have been created.
-   Operations on non-primitive values can change the internal state of the value without creating a new one.

**Stored by Reference**:

-   Non-primitive values are typically stored indirectly in memory locations known as heap memory.
-   When you assign a non-primitive value to a variable, you're actually assigning a reference (memory address) to that value, not the value itself.
-   Operations on non-primitive values work with the reference to the value stored in memory.

```js
// Object
let person = { name: "John", age: 30 };
let fruits = ["apple", "banana", "orange"];
let sayHello = function () {
    console.log("Hello!");
};
```

### Null

In JavaScript, `null` is often mistakenly identified as an object, but it's not truly an object.

The erroneous classification of `null` as an object is actually a long-standing bug in JavaScript, existing since its early days. This is due to how JavaScript internally represents the null value.

While typeof null returns 'object', it's actually a primitive value. The null value represents the **intentional absence** of any object value to indicate that it has no value or that it's intentionally empty - it's often considered a placeholder or an empty value signifying no value or no object. It is also often used to reset or clear the value of a variable or property.

This behavior of typeof `null` being 'object' is considered a quirk or historical bug in JavaScript, but `null` itself is not an object in the traditional sense. It's a unique primitive value in the language.

#### Null vs. Undefined

In JavaScript, `null`, `undefined` often sources of confusion due to their similar roles.

A valid value in JavaScript, `null` is a primitive data type explicitly assigned to a variable to indicate that it has no value or that it's intentionally empty.

Also an primitive data type `undefined` represents the absence of value due to variables being declared but not assigned, or accessing nonexistent properties or variables. It's also the default return value of functions if no return value is specified.

### `typeof` operator

JavaScript also provides features to check the data type of a variable or value using the `typeof` operator:

```js
typeof 42; // "number"
typeof "hello"; // "string"
typeof true; // "boolean"
typeof undefined; // "undefined"
typeof null; // "object"
typeof {}; // "object"
typeof []; // "object"
typeof function () {}; // "function"
typeof Symbol(); // "symbol" (ES6)
```
