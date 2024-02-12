## Looping

In JavaScript, loops are used to repeatedly execute a block of code as long as a certain condition is true. They provide a way to automate repetitive tasks and iterate over data structures. There are several types of loops in JavaScript, each with its own use cases. JavaScript supports different kinds of loops:

-   **for** - loops through a block of code a number of times
-   **for/in** - loops through the properties of an object
-   **for/of** - loops through the values of an iterable object
-   **while** - loops through a block of code while a specified condition is true
-   **do/while** - also loops through a block of code while a specified condition is true

### 1. The **For** Loop

When you know the exact number of iterations and want to control the loop with an initialization, condition, and iteration statement.

```js
for (initialization; condition; iteration) {
    // code block to be executed
}
```

##### **initialization**

is the initial expression and is executed only once at the beginning of the loop. It typically initializes a counter variable.

##### **condition**

is the expression that is **evaluated before** each iteration. If the condition is true, the loop continues; otherwise, it exits.

##### **iteration**

is the expression that is **executed after** each iteration of the loop. It is usually responsible for updating the counter variable.

Example:

```js
for (let i = 0; i < 5; i++) {
    text += "The number is " + i + "<br>";
}
```

### 2. The **for...in** loop:

When iterating over enumerable **properties/keys** of an **Object** is required. This includes the inherited properties form the object's prototype chain. The order of iteration is not guaranteed and can vary based on the JavaScript engine.

```js
for (key in object) {
    // code to be executed
}
```

##### **key**

Represents a different property name / key on each iteration.

Example:

```js
const person = { name: "John", age: 30 };
for (let key in person) {
    console.log(key, person[key]);
}
```

### 3. The **for...of** loop:

Designed for looping through the values of an iterable objects like **arrays, strings, maps, sets, etc**. It provides a simpler syntax compared to for...in when dealing with arrays. Iterates in the order the elements appear in the iterable.

```js
for (variable of iterable) {
    // code to be executed
}
```

##### **variable**

for every iteration the value of the next property is assigned to the variable. Variable can be declared with const, let, or var.

##### **iterable**

an object that has iterable properties.

Example:

```js
const fruits = ["apple", "banana", "orange"];
for (let fruit of fruits) {
    console.log(fruit);
}
```

### 4. The **while** loop:

When you don't know the number of iterations beforehand and the loop should continue based on a certain condition.

```js
while (condition) {
    // code to be executed
}
```

##### **condition**

is the expression that is **evaluated before** each iteration. If the condition is true, the loop continues; otherwise, it exits.

Example:

```js
let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
```

### 5. The **do - while** loop

To be used when you want the loop to execute at least once, before checking if the condition is true, and then continue based on a certain condition as long as it is **true**. The do while loop is a variant of the while loop.

```js
do {
    // code to be executed
} while (condition);
```

##### **condition**

similar to the while loop, but the condition is checked after the first iteration. This ensures that the code block executes at least once.

Example:

```js
do {
    text += "The number is " + i;
    i++;
} while (i < 10);
```
