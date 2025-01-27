# 👋 Javascript Basics / Refresher Course 👋

Topics:

- Console, Code Flow, Loading Order & Defer
- Data types
- Variables & Constants, Assignment & Concatenation
- Floating point problem, parsing
- Pre & Post Increment and Decrement Operators
- if & else, Conditions, Negation, Logic Operators, == vs ===
- switch, case, break
- two common mistakes: - using = (assignment operator) rather than == or === or wrong semicolon at the if line
- loops: while, do... while, for, nested loops
- variables revisited, for loop: local vs global scope
- arrays & objects: value assignment vs reference assignment, get and set values
- conditions revisited: null values
- special for loops: of vs in
- break revisited vs continue
- multi-dimensional arrays
- string manipulation: toUpperCase, toLowerCase, substr, substring
- functions: parameters & arguments, arrow functions, bookmarklet
- exercises: Palindrome, character replacement, return array of values from list of objects
- if we have time: event handlers, async / await, modules

## Console, Code Flow, Loading Order & Defer

# Sinlge-value output

```js
console.log("output one line of text to console");
```

### Multi-value output

```js
console.log(1, 2, 3);
```

```js
let a = 1;
let b = 2;
let c = 3;
console.log(c, b, a);
```

## Data types

### Intergers

```js
console.log(1);
```

### Floating Point

```js
console.log(1);
```

### Text / String

```js
console.log("text");
console.log("1");
console.log(" ");
console.log("First line\nSecond line");
```

### Boolean (true / false)

```js
console.log(true);
console.log(false);
```

## Variables & Constants, Assignment & Concatenation

Variables and constants are ways to store data.
**Variables** are ... variable, it can change over time.
**Constants**, once declared, **cannot be changed**.

There are many ways to declare a variable or constant:

### var (old way to declare variables)

`var` is the old way to declare variables, this is **_discouraged_**.

```js
var v = 1;
var v = 2;
console.log(v);
```

### let (the new way, the safe way)

`let` is the new way, and this has a lot more protection, such as not letting us accidentally make another variable with the same name.

Example:

```js
let d = 1;
let d = 2;
console.log(d);
```

This will lead to us getting this error: `Uncaught SyntaxError: Identifier 'd' has already been declared`.

The right way to do things is:

```js
let x = 1;
console.log(x);
```

Update value later on with another assignment.

```js
x = 2;
console.log(x);
```

This will ensure that the variable is not accidentally remade with another value somewhere else and only change when we want them to.

### const (for constants)

To declare a constant, use the `const` declaration

```js
const greeting = "Hi";
greeting = "Hi there";
const pi = 3.14;
pi = 1;
console.log(greeting, pi);
```

This will give us this error: `Uncaught TypeError: Assignment to constant variable.` as greeting is already set and should not change.

### Assigning values using variables

```js
let y = 3;
let z = x + y;
console.log(y, z);
```

```js
let fname = "First";
let lname = "Last";
console.log(fname + lname);
let name = fname + lname;
console.log(name);
```

## Floating point problem, parsing

### Floating point problem

A well known problem in javascript is the precision of floating point (decimal) values.

The JavaScript Number type is a `double-precision 64-bit binary format IEEE 754 value`, This means it can represent fractional values, but there are some limits to the stored Number's magnitude and precision.

[Read more here: Number Encoding in MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#Number_encoding)

Example:

```js
let d1 = 0.1;
let d2 = 0.2;
console.log(d1 + d2);
```

we are expecting the answer to be 0.3, but... we get something else.

### Parsing (converting values from one type to another)

#### Normal behaviour

```js
console.log("1" + 1);
console.log(1 + "1");
```

This gives as `11` as expected

#### Number cohersion

```js
console.log(1 + +"1");
```

This gives us... 2?

```js
console.log(1 + +"0.1");
```

Also works for floating points!

#### Adding Numbers and strings (text) that are not pure numbers

let's try adding the Number `1` and a string `654.321testing`

```js
let parseString = `987.654testing321`;
console.log(1 + parseString);
```

Let's try to coherse the string to Number like before...

```js
console.log(1 + +parseString);
```

doesn't really work, it gives us `NaN`.

#### NaN

NaN stands for Not a Number

#### Parsing (string to integer or floating point)

```js
console.log(1 + +parseInt(parseString));
```

This will give us `988`, 1 + 987 as a whole number.

```js
console.log(1 + parseFloat(parseString));
```

This will give us `988.654`, 1 + 987.654 as a floating point number.

Note: All parsing will result in removal of any characters after encountering the first alphabet character.

#### Brain teaser: BaNaNa

Using just a combination of operations we've looked at and **ONLY** the lower case letters `a` and `b`, how can we get the console to output `BaNaNa`?

```js
console.log("put your solution here");
```

## Pre & Post Increment and Decrement Operators

let's say we start with the value 1:

```js
let change = 1;
```

we can manually increment the value by 1 using:

```js
change = change + 1;
```

or shorthand is:

```js
change += 1;
```

Which will the `+ 1` operation and then do the assignment operation, as expected from the order of operations when reading this left to right.

### Post increment operator

```js
console.log(change++);
console.log(change);
```

### Pre increment operator

```js
console.log(++change);
console.log(change);
```

### Post decrement operator

```js
console.log(change--);
console.log(change);
```

### Pre decrement operator

```js
console.log(--change);
console.log(change);
```

## if & else, Negation, Conditions, Logic Operators, == vs ===

```js
let condition = true;
if (condition) console.log("true!");
```

```js
condition = false;
if (condition) console.log("true!");
```

```js
condition = true;
if (condition) {
  console.log("true!");
} else {
  console.log("false.");
}
```

```js
condition = false;
if (condition) {
  console.log("true!");
} else {
  console.log("false.");
}
```

## switch, case, break

```js
console.log("replace");
```

## two common mistakes: - using = (assignment operator) rather than == or === or wrong semicolon at the if line

```js
console.log("replace");
```

## loops: while, do... while, for, nested loops

```js
console.log("replace");
```

## variables revisited, for loop: local vs global scope

```js
console.log("replace");
```

## arrays & objects: value assignment vs reference assignment, get and set values

```js
console.log("replace");
```

## conditions revisited: null values

```js
console.log("replace");
```

## special for loops: of vs in

```js
console.log("replace");
```

## break revisited vs continue

```js
console.log("replace");
```

## multi-dimensional arrays

```js
console.log("replace");
```

## string manipulation: toUpperCase, toLowerCase, substr, substring

```js
console.log("replace");
```

## functions: parameters & arguments, arrow functions, bookmarklet

```js
console.log("replace");
```

## exercises: Palindrome, character replacement, return array of values from list of objects

```js
console.log("replace");
```

## if we have time: event handlers, async / await, modules

```js
console.log("replace");
```
