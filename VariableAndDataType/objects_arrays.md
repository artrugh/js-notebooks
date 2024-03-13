## Objects and Arrays

In JavaScript, both objects and arrays are types of objects, but they have distinct characteristics and purposes:

### Objects

-   Key-Value Pairs: Objects are collections of key-value pairs where keys are strings (or Symbols) and values can be of any data type.

-   Use of Dot Notation or Bracket Notation: Accessing properties in an object can be done using dot notation (object.property) or bracket notation (object['property']).

-   Properties and Methods: Objects can contain properties (data) and methods (functions).

-   Unordered: The order of properties in an object is not guaranteed.

-   Usage: Objects are used for modeling real-world entities or concepts, such as a person, car, or any other complex structure.

Example:

```js
let person = {
    name: "Alice",
    age: 30,
    greet: function () {
        console.log("Hello!");
    },
};
```

In JavaScript, most objects inherit properties and methods from `Object.prototype`. This includes common methods like `toString()`, `hasOwnProperty()`, and `valueOf()`. Objects can override these inherited properties or methods with their own. However, objects created with a null prototype or descended from objects with a null prototype don't inherit from `Object.prototype`. Changes to `Object.prototype` affect all objects in the prototype chain, but if properties or methods are overridden further down the chain, they won't be affected. `Object.prototype` itself has an **immutable prototype**, always set to `null`, ensuring its properties cannot be changed. Understanding these concepts is important for working effectively with objects in JavaScript.

#### Creating Objects

Objects can be created using the `Object()` constructor with the `new` keyword, using the object initializer - a comma-delimited list of zero or more pairs of property names and associated values of an object, enclosed in curly braces ({}), or the `Object.create()` static method that creates a new object, using an existing object as the prototype of the newly created object.

```js
// Object constructor
new Object();
new Object(value);

// Object initializer
const object1 = {};
const object2 = {
    foo: "bar",
    age: 42,
    baz: { myProp: 12 },
};

// Object.create()
const developer = {
    isHired: false,
    printBio: function () {
        console.log(`My name is ${this.name}. Am I hired? ${this.isHired}`);
    },
};

const juniorDev = Object.create(developer);

juniorDev.name = "GPT_prompt_master"; // "name" is a property set on "juniorDev", but not on "developer"
juniorDev.isHired = true; // Inherited properties can be overwritten

juniorDev.printBio();
```

[Link documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

### Arrays

-   Ordered List: Arrays are ordered lists of values, accessed by numerical indices starting from zero.

-   Special Type of Object: In JavaScript, arrays are a specialized type of object specifically designed to store ordered data.

-   Length Property: Arrays have a length property that indicates the number of elements in the array.

-   JavaScript arrays are zero-indexed: the first element of an array is at index 0, the second is at index 1, and so on — and **the last element is at the value of the array's length property minus 1**.

-   JavaScript array-copy operations create shallow copies. (All standard built-in copy operations with any JavaScript objects create shallow copies, rather than deep copies).

-   Methods for Manipulation: Arrays have built-in methods (such as push, pop, splice, etc.) for manipulating their content.

-   Usage: Arrays are used when you need to store and work with a collection of similar items, such as a list of numbers, names, or any other data.

```js
let numbers = [1, 2, 3, 4, 5];
let fruits = ["apple", "banana", "orange"];
```

#### Creating Arrays

Since arrays are objects yoy can create an array using Array Literal square brackets [] and list the elements inside the brackets, separated by commas, or using the Array Constructor with the `new` keyword. Additionally you can create an array from an iterable object (like a string or array-like object) using the Array.from() method. Another way is to create an array by spreading elements from another iterable object, or using the static method `Array.of()`

```js
// Array literal
const myArray = [1, 2, 3, 4, 5];

// Using the Array Constructor:
const myArray = new Array(1, 2, 3, 4, 5);
const emptyArray1 = [];
const emptyArray2 = new Array();

Using Array.from():


//Array.from() method.
const strArray = Array.from('hello');
console.log(strArray); // ['h', 'e', 'l', 'l', 'o']

//Spread Syntax:
const newArray = [...oldArray];

//Array.of():
const myArray = Array.of(1, 2, 3, 4, 5);
```

#### Sparse arrays

Arrays can contain "empty slots", which are not the same as slots filled with the value undefined. Empty slots can be created in one of the following ways:

```js
// Array constructor:
const arr1 = Array(5); // [ <5 empty items> ]

// Consecutive commas in array literal:
const arr2 = [1, 2, , , 5]; // [ 1, 2, <2 empty items>, 5 ]

// Directly setting a slot with index greater than array.length:
const arr3 = [1, 2];
arr3[4] = 5; // [ 1, 2, <2 empty items>, 5 ]

// Elongating an array by directly setting .length:
const arr4 = [1, 2];
d.length = 5; // [ 1, 2, <3 empty items> ]

// Deleting an element:
const arr5 = [1, 2, 3, 4, 5];
delete arr5[2]; // [ 1, 2, <1 empty item>, 4, 5 ]
```

#### Copying methods and mutating methods

Some methods do not mutate the existing array that the method was called on, but instead return a new array. They do so by first constructing a new array and then populating it with elements. The copy always happens shallowly — the method never copies anything beyond the initially created array.

-   These methods create a new array with the same top-level elements as the original.
-   For objects, the reference is copied, so changes affect both arrays.
-   For primitive types, values are copied.

Other methods mutate the array -change the original array directly - that the method was called on, in which case their return value differs depending on the method: sometimes a reference to the same array, sometimes the length of the new array.

[Link documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

### Objects and Arrays - Key Difference

The key difference lies in how they organize and access their data: objects use named keys to access values, while arrays use numerical indices. Objects are more suitable for modeling entities with named properties, while arrays are useful for storing ordered collections of values.
