## Conditional Statements

JavaScript conditional statements are used to make decisions in code based on certain conditions. These statements allow your program to execute different blocks of code depending on whether a specified condition evaluates to true or false.

In JavaScript we have the following conditional statements:

-   The **if** is used to specify a block of code to be executed, if a specified condition is true
-   The **else** is used to specify a block of code to be executed, if the same condition is false
-   The **else if** is used to specify a new condition to test, if the first condition is false
-   The **switch** is used to specify many alternative blocks of code to be executed

### 1. The **if** statement:

The if statement is the fundamental conditional statement. It allows you to execute a block of code if a specified condition is true. The basic syntax is as follows:

```js
if (condition) {
    //  block of code to be executed if the condition is true
}
```

### 2. The **else** statement:

The else statement is used in conjunction with an if statement to specify a block of code to be executed if the condition in the if statement is false. The syntax is:

```js
if (condition) {
    //  block of code to be executed if the condition is true
} else {
    //  block of code to be executed if the condition is false
}
```

### 3. The **else if** statement:

The else if statement allows you to specify additional conditions to be tested if the previous conditions in the if and else if statements are false. It is used when you have multiple conditions to check. The syntax is:

```js
if (condition1) {
    //  block of code to be executed if condition1 is true
} else if (condition2) {
    //  block of code to be executed if the condition1 is false and condition2 is true
} else {
    //  block of code to be executed if the condition1 is false and condition2 is false
}
```

### 4. The **switch** statement

Use the switch statement to select one of many code blocks to be executed. It allows you to compare the value of an expression against multiple possible case values and execute code blocks based on the matching case. The execution inside the switch expression works as follows:

-   The switch expression is evaluated once.
-   The value of the expression is compared with the values of each **case**.
-   If there is a match, the associated block of code is executed.
-   If there is no match, the **default** code block is executed.

The syntax is:

```js
switch (expression) {
    case value1:
        // code to be executed if expression === value1
        break;
    case value2:
        // code to be executed if expression === value2
        break;
    // additional cases as needed
    default:
    // code to be executed if none of the cases match
}
```

##### The **break** Keyword

When JavaScript reaches a **break** keyword, it breaks out of the switch block. This will stop the execution inside the switch block. It is not necessary to break the last case in a switch block. The block breaks (ends) there anyway.

##### The **default** Keyword

The **default** keyword specifies the code to run if there is no case match.
