### Array Iteration Methods

Build in Array iteration methods that operate on every array item:

| Method        | Description                                                                                                                  | Example Usage                                                                                                            |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| forEach()     | Executes a provided function once for each array element.                                                                    | `javascript array.forEach(element => console.log(element)); `                                                            |
| map()         | Creates a new array populated with the results of calling a provided function on every element in the calling array.         | `javascript const newArray = array.map(element => element * 2); `                                                        |
| flatMap()     | Maps each element using a mapping function, then flattens the result into a new array.                                       | `javascript const flatArray = array.flatMap(element => [element, element * 2]); `                                        |
| filter()      | Creates a new array with all elements that pass the test implemented by the provided function.                               | `javascript const filteredArray = array.filter(element => element > 5); `                                                |
| reduce()      | Applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value. | `javascript const result = array.reduce((accumulator, currentValue) => accumulator + currentValue, initialValue); `      |
| reduceRight() | Applies a function against an accumulator and each value of the array (from right to left) to reduce it to a single value.   | `javascript const result = array.reduceRight((accumulator, currentValue) => accumulator + currentValue, initialValue); ` |
| some()        | Checks if at least one element in the array passes the test implemented by the provided function.                            | `javascript const hasPositive = array.some(element => element > 0); `                                                    |
| from()        | Creates a new Array instance from an array-like or iterable object.                                                          | `javascript const newArray = Array.from(arrayLike); `                                                                    |
| keys()        | Returns a new Array Iterator that contains the keys for each index in the array.                                             | `javascript const keys = array.keys(); `                                                                                 |
| entries()     | Returns a new Array Iterator object that contains the key/value pairs for each index in the array.                           | `javascript const entries = array.entries(); `                                                                           |
| values()      | Returns a new Array Iterator object that contains the values for each index in the array.                                    | `javascript const values = array.values(); `                                                                             |
| with()        | Creates an array from a set of comma-separated values. (Deprecated)                                                          | `javascript const newArray = Array.with(1, 2, 3); `                                                                      |

**NOTE:**
Methods `Array.prototype.values()`, `Array.prototype.keys()` and `Array.prototype.entries()` return a new `Array Iterator` object. This iterator object provides a way to access elements of a collection (like an array) one by one, sequentially. It allows to loop through each element of the collection and perform operations on them. It keeps track of its current position, while accessing items in a collection one at a time and returns an object with two properties: `done` and `value`. In JavaScript, it also provides a `next()` method which returns the next item in the sequence. When the sequence completes, the `value` will equal undefined, and `done` will equal true.

### Array Spread (...)

An IE6 feature, spread syntax "expands" an array into its elements. The use cases are:

1. Copying an Array:

```js
const array = [1, 2, 3, 4];
const copyArray = [...array];
```

2. Concatenating Arrays:

```js
const array1 = [1, 2];
const array2 = [3, 4];
const concatenatedArray = [...array1, ...array2];
```

3. Passing Array Elements as Function Arguments:

```js
const array = [1, 2, 3, 4];
function myFunction(a, b, c, d) {
    console.log(a + b + c + d);
}
myFunction(...array);
```

### Iterating thorough array using loops

Arrays are ordered collections of elements, and they are one of the most common data types used with loops. Loops are frequently employed to iterate over the elements of an array, performing operations on each element as needed.

`FOR` loop is used when you know the number of iterations you need to perform. It consists of three parts: initialization, condition, and increment/decrement.

```js
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

`WHILE` loop repeats a block of code as long as a specified condition evaluates to true. Typically, while loops are used when you need to iterate over an array based on a condition that may not be directly related to the array's length:

```js
const array = [1, 2, 3, 4, 5];
let i = 0;

while (i < array.length) {
    console.log(array[i]);
    i++;
}
```

`DO...WHILE` loop similar to a while loop, but the block of code is executed once before the condition is checked. It ensures that the block of code executes at least once.

```js
const array = [1, 2, 3, 4, 5];
let i = 0;

do {
    console.log(array[i]);
    i++;
} while (i < array.length);
```

`FOR...OF` loops introduced in ES6, it iterates over iterable objects like arrays, strings, maps, sets, etc.

```js
const array = [1, 2, 3, 4];
for (const element of array) {
    console.log(element);
}
```

**NOTE:**
Using `for...in` loops with arrays in JavaScript is not recommended due to potential issues with the iteration order, unintended iteration over all enumerable properties including prototype properties, and performance overhead compared to other looping constructs.
