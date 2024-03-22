## Array Methods

Array methods can be effectively categorized based on their behaviors and effects, which can be helpful for understanding their usage and selecting the appropriate method for a specific task.

### Modification Methods

#### Destructive (Mutating) Modification Methods:

The modification methods below are **"Mutating Methods"** that directly alter the original array.

`Array.prototype.push()` - adds elements to the end of an array.

```js
let city = ["New York", "Madrid", "Kathmandu"];
// add "London" to the array
city.push("London");
console.log(city);
// Output: [ 'New York', 'Madrid', 'Kathmandu', 'London' ]
```

`Array.prototype.pop()` method removes the last element from an array and returns that element.

```js
let cities = ["Madrid", "New York", "Kathmandu", "Paris"];
// remove the last element
let removedCity = cities.pop();
console.log(cities); // ["Madrid", "New York", "Kathmandu"]
console.log(removedCity); // Paris
```

`Array.prototype.shift()` removes the first element from an array and returns that element.

```js
let languages = ["English", "Java", "Python", "JavaScript"];

// remove the first element of the array
let first = languages.shift();
console.log(first); // Output: English
console.log(languages); // Output: [ 'Java', 'Python', 'JavaScript' ]
```

`Array.prototype.unshift()` adds one or more elements to the beginning of an array and returns the new length of the array.

```js
let languages = ["Java", "Python", "C"];
// add "JavaScript" at the beginning of the array
languages.unshift("JavaScript");
console.log(languages); // Output: [ 'JavaScript', 'Java', 'Python', 'C' ]
```

`Array.prototype.splice()`: method modifies an array (adds, removes or replaces elements)

```js
let prime_numbers = [2, 3, 5, 7, 9, 11];
// replace 1 element from index 4 by 13
let removedElement = prime_numbers.splice(4, 1, 13);
console.log(removedElement); // Output: [ 9 ]
console.log(prime_numbers); // Output: [ 2, 3, 5, 7, 13, 11 ]
```

#### Non-Destructive Modification Methods:

These methods create a new array without modifying the original:

`Array.prototype.concat()` this method merges two or more arrays.

```js
const array1 = ["a", "b", "c"];
const array2 = ["d", "e", "f"];
const array3 = array1.concat(array2);
console.log(array3); // Expected output: Array ["a", "b", "c", "d", "e", "f"]
```

`Array.prototype,slice()` extracts a portion of an array into a new array, returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included) where start and end represent the index of items in that array. The original array will not be modified.

```js
let numbers = [2, 3, 5, 7, 11, 13, 17];
// create another array by slicing numbers from index 3 to 5
let newArray = numbers.slice(3, 6);
console.log(newArray); // Output: [ 7, 11, 13 ]
```

### Iteration Methods:

These methods iterate through the array and perform an operation:

`Array.prototype.forEach()`: Execute a provided function once for each array element. Its return value is discarded.

```js
const array1 = ["a", "b", "c"];
array1.forEach((element) => console.log(element.toUpperCase()));
// Expected output: "A"
// Expected output: "B"
// Expected output: "C"
```

`Array.prototype.map()` creates a new array populated with the results of calling a provided function on every element in the calling array.

```js
const arr1 = [1, 2, 3, 4];
const mappedArr = arr1.map((element) => element * 100);
console.log(mappedArr)[(100, 200, 300, 400)];
// use Number function to  convert a string or to Number value
console.log(["1", "2", "3", "4"].map(Number)); // [1, 2, 3, 4]
```

`Array.prototype.filter()` method creates a new array with elements filtered down to just the elements from the given array that pass the test implemented by the provided function.

```js
let numbersArr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
// function to check even numbers
function checkEven(number) {
    if (number % 2 == 0) return true;
    else return false;
}
// create a new array by filter even numbers from the numbers array
let evenNumbers = numbersArr.filter(checkEven);
console.log(evenNumbers); // Output: [ 2, 4, 6, 8, 10 ]
```

`Array.prototype.reduce()` and `Array.prototype.reduceRight()` methods execute a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.

The first time that the callback is run there is no "return value of the previous calculation". If supplied, an initial value may be used in its place. Otherwise the array element at index 0 is used as the initial value and iteration starts from the next element (index 1 instead of index 0).

```js
const message = ["JavaScript ", "is ", "fun"];
// function to join each string elements
function joinStrings(accumulator, currentValue) {
    return accumulator + currentValue;
}
// reduce join each element of the string
let joinedString = message.reduce(joinStrings);
console.log(joinedString); // Output: JavaScript is fun
let joinedToTheRight = message.reduceRight(joinStrings); // Output:  fun is JavaScript
```

`Array.prototype.every()` tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.

```js
const array1 = [1, "30", "number1", 39, 29, 10, 13];
// Function to check if an element is a number
const checkIfNum = (element) => !isNaN(element);
console.log(array1.every(checkIfNum)); // false
```

`Array.prototype.some()` methods to check if at least one element passes a test.

```js
let numbers = [1, 3, 2, 5, 4];
// function to check even number - number that can be exactly divided by 2
function isEven(element) {
    return element % 2 === 0;
}
console.log(numbers.some(isEven)); // Output: true
```

`Array.prototype.find()` Find the first element passing a test.

```js
let numbers = [1, 3, 4, 9, 8];
// function to check even number - number that can be exactly divided by 2
function isEven(element) {
    return element % 2 == 0;
}
// get the first even number
let evenNumber = numbers.find(isEven);
console.log(evenNumber); // Output: 4
```

`Array.prototype.findIndex()` method returns the index of the first array element that satisfies the provided test function or else returns -1.

```js
let numbers = [2, 8, 1, 3, 4];
// function that returns odd number - a number which is not divisible by “2”
function isOdd(element) {
    return element % 2 !== 0;
}
// returns the index of the first odd number in the array
let firstOdd = numbers.findIndex(isOdd);
console.log(firstOdd); // Output: 2
```

`Array.prototype.toSpliced()` method returns a new array with some elements removed and/or replaced at a given index.

```js
const months = ["Jan", "Mar", "Apr", "May"];

// Inserting an element at index 1
const months2 = months.toSpliced(1, 0, "Feb");
console.log(months2); // ["Jan", "Feb", "Mar", "Apr", "May"]

// Deleting two elements starting from index 2
const months3 = months2.toSpliced(2, 2);
console.log(months3); // ["Jan", "Feb", "May"]

// Replacing one element at index 1 with two new elements
const months4 = months3.toSpliced(1, 1, "Feb", "Mar");
console.log(months4); // ["Jan", "Feb", "Mar", "May"]

// Original array is not modified
console.log(months); // ["Jan", "Mar", "Apr", "May"]
```

### Searching and Indexing Methods:

These methods search for elements or their indices:

`Array.prototype.indexOf()` method returns the first index of occurrence of an array element, or -1 if it is not found.

```js
let languages = ["Java", "JavaScript", "Python", "JavaScript"];
// get the index of the first occurrence of "JavaScript"
let index = languages.indexOf("JavaScript");
console.log(index); // Output: 1
```

`Array.prototype.lastIndexOf()`: method returns the index of the last occurrence of a specified element value in the array.

```js
let priceList = [10, 8, 2, 31, 10, 31, 65];
// finding the index of the last occurrence of 31
let lastIndex = priceList.lastIndexOf(31);
console.log(lastIndex); // Output: 5
```

`Array.prototype.includes()`: method checks if an array contains a specified element, returning true or false as appropriate.

```js
// defining an array
let languages = ["JavaScript", "Java", "C"];
// checking whether the array contains 'Java'
let checkIfIncludes = languages.includes("Java");
console.log(checkIfIncludes); // Output: true
```

`Array.isArray()`: static method determines whether the passed value is an `Array`.

```js
console.log(Array.isArray([1, 3, 5]));
// Expected output: true
console.log(Array.isArray("[]"));
// Expected output: false
console.log(Array.isArray(new Array(5)));
// Expected output: true
console.log(Array.isArray(new Int16Array([15, 33])));
// Expected output: false
```

### Ordering and Reversal Methods

#### Destructive Ordering and Reversals Methods

These methods rearrange the elements in the original array:

`Array.prototype.reverse()` method of Array instances reverses an array in place and returns the reference to the **same array**, the first array element now becoming the last, and the last array element becoming the first.

```js
let numbers = [1, 2, 3, 4, 5];
// reversing the numbers array
let reversedArray = numbers.reverse();
console.log(reversedArray); // Output: [ 5, 4, 3, 2, 1 ]
```

`Array.prototype.sort()` method sorts the items of an array in a specific order (ascending or descending). The default sort order is ascending.Method takes and optional compere function that determines the order of the elements. If omitted, the array elements are converted to strings, then sorted according to each character's Unicode code point value

```js
const months = ["March", "Jan", "Feb", "Dec"];
months.sort();
console.log(months); // Expected output: Array ["Dec", "Feb", "Jan", "March"]
const numbers = [1, 30, 4, 21, 100000];
numbers.sort();
console.log(numbers); // 1, 100000, 21, 30, 4 converts the elements to string and sorts by characters Unicode point value

// define compare function
function compareFn(a, b) {
    if (a < b) {
        return -1; // a should come before b
    } else if (a > b) {
        return 1; // a should come after b
    }
    // a and b are equal
    return 0;
}

// sort the array using the compare function
numbers.sort(compareFn);
console.log(numbers); // Output: [1, 4, 21, 30, 100000]
```

#### Non-Destructive Ordering and Reversals Methods

To sort the elements in an array without mutating the original array, use `toSorted()`
To reverse the elements in an array without mutating the original array, use `toReversed()`.

## Conversion and Joining Methods:

These methods convert arrays to strings or vice versa:

`Array.prototype.join()` creates and returns a new string by concatenating all of the elements in this array, separated by commas or a specified separator string. If the array has only one item, then that item will be returned without using the separator.

```js
const elements = ["Chocolate", "Bubble", "Gum"];

console.log(elements.join());
// Expected output: "Chocolate,Bubble,Gum"

console.log(elements.join(""));
// Expected output: "ChocolateBubbleGum"

console.log(elements.join("-"));
// Expected output: "Chocolate-Bubble-Gum"
```

`Array.prototype.toString()` converts an array to a string.

```js
// defining an array
let items = ["JavaScript", 1, "2", 3];

// returns a string with elements of the array separated by commas
let itemsString = items.toString();
console.log(itemsString); // Output: "JavaScript,1,2,3"
```

## Miscellaneous Methods:

These methods perform various other operations:

`Array.prototype.with()` method of Array instances is the copying version of using the bracket notation to change the value of a given index. It returns a new array with the element at the given index replaced with the given value.

```js
const nums = [1, 2, 3, 4, 5, 6];
console.log(nums.with(2, 6)); // [1, 2, 6, 4, 5]
console.log(nums); // [1, 2, 3, 4, 5] // original remains intact
```

`Array.prototype.copyWithin()` method of Array instances shallow copies part of this array to another location in the same array and returns this array without modifying its length.

```js
let fruits = ["apple", "banana", "cherry", "date", "elderberry"];

// Copy the sequence from index 0 to 3 (exclusive!) to index 3
fruits.copyWithin(3, 0, 3);
console.log(fruits); // Output: ['apple', 'banana', 'cherry', 'apple', 'banana']

// Copy the sequence from index 2 to 5 (exclusive!) to index 0
fruits.copyWithin(0, 2, 5);
console.log(fruits); // Output: ['cherry', 'apple', 'banana', 'apple', 'banana']
```

`Array.prototype.fill()` method fills all the elements of an array from a start index to an end index with a static value.It modifies the original array and returns the modified array.

```js
let arr = [1, 2, 3, 4, 5];

// Fill the array with value 0 from index 2 to 5 (exclusive)
arr.fill(0, 2, 5);
console.log(arr); // Output: [1, 2, 0, 0, 0]

// Fill the entire array with value 10
arr.fill(10);
console.log(arr); // Output: [10, 10, 10, 10, 10]
```

`Array.prototype.flat()` flattens nested arrays.

```js
// 3 nested arrays
let numbers = [1, 2, [3, 4, [5, 6, [7, 8]]]];

// reducing nesting by flattening the array to depth 2
let flattenArray = numbers.flat(2); // arr.flat(depth)

// new flatten array
console.log(flattenArray); // Output: [ 1, 2, 3, 4, 5, 6, [ 7, 8 ] ]
```

`Array.prototype.flatMap()` returns a new array formed by applying a given callback function to each element of the array, and then flattening the result by one level. It is identical to a `map()` followed by a `flat(`) of depth 1 `(arr.map(...args).flat())`, but slightly more efficient than calling those two methods separately.

```js
// defining an array
let numbers = [1, 2, 3, 4, 5];
// each element of the array is squared and later flattened
const resultingArray = numbers.flatMap((x) => [x ** 2]);
console.log(resultingArray); // Output: [ 1, 4, 9, 16, 25 ]
```

`Array.prototype.keys()` method returns a new Array Iterator object that contains the keys (indices) for each element in the array. It doesn't change the original array.

```js
const array1 = ["a", "b", "c"];
const iterator = array1.keys();

for (const key of iterator) {
    console.log(key);
}
```

`Array.prototype.values()` method returns a new Array Iterator object that contains the values for each element in the array in the same order as they appear in the array. It does not change the original array.

```js
const arr = ["a", "b", "c"];
const iterator = arr.values();

for (const value of iterator) {
    console.log(value); // Output: 'a', 'b', 'c'
}
```

`Array.prototype.entries()`: Returns an iterator containing key-value pairs of the array.

```js
const arr = ["a", "b", "c"];
const iterator = arr.entries();

for (const entry of iterator) {
    console.log(entry); // Output: [0, 'a'], [1, 'b'], [2, 'c']
}
```

### Array static methods

Static methods can only be called with the prefix `Array`. They relate directly to an `Array` as a whole, rather than a specific array that you have created or are working with. Examples of some static methods are below:

`Array.from()` will take another JS iterable and turn it into a proper arrayArray.isArray()
`Array.fromAsync()` static method creates a new, shallow-copied Array instance from an async iterable, iterable, or array-like object.
`Array.isArray()` will return a bool based on if the passed argument is an array or not
`Array.of()` provides an alternative method for creating arrays compared to using the `array literal []`

### Array prototypal methods (instance)

Instance methods (or prototypal methods) are quite the opposite of static methods- you cannot call any of them with the Array prefix, rather only an instance that you have declared.

#### Array static methods vs. prototype

The key difference lies in how these methods are called and what they operate on. Prototype methods operate on instances of the class, whereas static methods do not require instances and are defined at the class level. a prototype method expects to be called on an instance, i.e. to have an instance passed as the this argument, whereas the static method does not require an instance and expects none.

#### Array methods and empty slots

Array methods have different behaviors when encountering empty slots in sparse arrays. In general, older methods (e.g. forEach) treat empty slots differently from indices that contain undefined.

Methods that have special treatment for empty slots include the following: concat(), copyWithin(), every(), filter(), flat(), flatMap(), forEach(), indexOf(), lastIndexOf(), map(), reduce(), reduceRight(), reverse(), slice(), some(), sort(), and splice(). Iteration methods such as forEach don't visit empty slots at all. Other methods, such as concat, copyWithin, etc., preserve empty slots when doing the copying, so in the end the array is still sparse.
