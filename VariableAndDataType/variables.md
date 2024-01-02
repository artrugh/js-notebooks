## Variables

In JavaScript, a variable is a **named container** for storing data values. It's like a labeled box where you can store information and refer to it later using the variable's name. Variables allow you to manipulate and work with data within your code.

A variable consists of three main parts:

- Keyword: This can be var, let, or const, used to declare the variable. These keywords have different behaviors regarding the scope and mutability of the variable (var has broader scope rules compared to let and const, and const declares a constant variable).

- Name/Identifier: It's the unique name you assign to the variable. This name is used to refer to the stored value later in the code.

- Value: This is the data or information stored within the variable. It's optional during the declaration but can be assigned later using the = operator.

When you declare a variable, you use the keyword followed by the variable name. Optionally, you can initialize it with an initial value:


```js
// Declaring a variable using 'let'
let myVariable; // Variable declaration without value

// Assigning a value to the variable
myVariable = 10; // Variable assignment

// Declaring and assigning a value in a single line
var anotherVariable = "Hello"; // Variable declaration and assignment

// 'const' is used to declare constants (immutable variables)
const pi = 3.14;
```

They can also be reassigned if they are declared using let or var, but a variable declared with const cannot be reassigned a new value once it has been initialized.

Variables provide a way to store and reference values throughout your JavaScript code, making your programs dynamic and flexible.