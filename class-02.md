# Class 2

- arrays & objects: value assignment vs reference assignment, get and set values
- conditions revisited: null values
- special for loops: of vs in
- break revisited vs continue
- multi-dimensional arrays
- string manipulation: toUpperCase, toLowerCase, substr, substring
- functions: parameters & arguments, arrow functions, bookmarklet
- exercises: Palindrome, character replacement, return array of values from list of objects
- if we have time: event handlers, async / await, modules

## Nested loops

Loop inside a loop

```js
for (let i = 0; i < 10; i++) {
  for (let j = 0; j < 10; j++) {
    console.log("" + i + j);
  }
}
```

## multi-dimensional arrays

```js
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];
console.log(matrix);
```

Inside the matrix, we can get value 4 using the index `matrix[1][0]` and the value 9 using index `matrix[2][2]`.

## Objects

To declare objects, use the curly brackets notation `{}`, inside, there should be property and value pairs, properties must have unique names and should never repeat within an object (or else, properties will be overridden).

```js
let dog = {
  name: "Rocky",
};
let student = {
  firstName: "Jack",
  rollNo: 32,
};
let car = { type: "Fiat", model: "500", color: "white" };

console.log(dog);
console.log(student);
console.log(car);
```

## Get and set object values

To read the value of a property within an object, simply use the `.` notation.

```js
console.log(dog.name);
console.log(student.firstName);
```

To change or add a property for an object, simply access and assign a value to an existing property or it will add a new property with the property name given.

```js
dog.name = "Snoopy";
student.lastName = "Bauer";
console.log(dog);
console.log(student);
```

## Value assignment vs reference assignment

As we previously saw, when we assign a value to a variable, the variable retains that value in memory. However, for arrays and objects, things are ... not the same.

Let's add a new dog and assign it the first dog and change something here...

```js
let dog2 = dog;
dog.name = "Laika";
console.log(dog2);
console.log(dog);
```

Uh oh! Changing either's properties will change the other!

Same applies for arrays...

```js
let refArr = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
let refArrCopy = refArr;
console.log(refArr);
console.log(refArrCopy);
```

```js
refArrCopy[0] = 1;
console.log(refArrCopy);
console.log(refArr);
```

> [!WARNING]
> If you make copies of arrays and objects, we need to make **deep** copies, meaning they are generated brand new and not a reference copy like we saw.

## Conditions revisited: null values

Let's try...

```js
console.log(!![]);
console.log(!!{});
```

Unlike Numbers or Strings, empty arrays and objects are **not** `false`.

## Special for loops: for...of vs for...in

For arrays, we use the for... of loop, think: 1 of 3.

```js
let array1 = ["a", "b", "c"];

for (let element of array1) {
  console.log(element);
}
```

For objects, we use the for... in loop, think: seats in a car.

```js
let object = { a: 1, b: 2, c: 3 };

for (let property in object) {
  console.log(`${property}: ${object[property]}`);
}
```

We can actually use the for... in loop for arrays too... but what should it give you?

```js
let special = ["a", "b", "c"];
for (let element in array1) {
  console.log(element);
}
```

However the opposite is not true, we **cannot** use a for... of loop for objects.

```js
let object = { a: 1, b: 2, c: 3 };

for (let property of object) {
  console.log(`${property}`);
}
```

We will get a `Uncaught TypeError: object is not iterable` error if we tried.

> [!IMPORTANT]
> Always remember:
> For arrays, use the for... of loop.
> For objects, use the for... in loop.

## break revisited vs continue

The `break` statement terminates the current loop or switch statement and transfers program control to the statement following the terminated statement.

```js
let i = 0;

while (i < 6) {
  if (i === 3) {
    break;
  }
  i = i + 1;
}

console.log(i);
// Expected output: 3
```

The `continue` statement terminates execution of the statements in the current iteration of the current loop, and continues execution of the loop with the next iteration.

```js
let text = "";

for (let i = 0; i < 10; i++) {
  if (i === 3) {
    continue;
  }
  text = text + i;
}

console.log(text);
// Expected output: "012456789"
```

## string manipulation: toUpperCase, toLowerCase, substring, split

```js
const sentence = "The quick brown fox jumps over the lazy dog.";

console.log(sentence.toUpperCase());
// Expected output: "THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG."

console.log(sentence.toLowerCase());
// Expected output: "the quick brown fox jumps over the lazy dog."
```

The `substring()` method of String values returns the part of this string from the start index up to and excluding the end index, or to the end of the string if no end index is supplied.

```js
const str = "Mozilla";

console.log(str.substring(1, 3));
// Expected output: "oz"

console.log(str.substring(2));
// Expected output: "zilla"
```

The `split`() method of String values takes a pattern and divides this string into an ordered list of substrings by searching for the pattern, puts these substrings into an array, and returns the array.

```js
const str = "The quick brown fox jumps over the lazy dog.";

const words = str.split(" ");
console.log(words[3]);
// Expected output: "fox"

const chars = str.split("");
console.log(chars[8]);
// Expected output: "k"

const strCopy = str.split();
console.log(strCopy);
// Expected output: Array ["The quick brown fox jumps over the lazy dog."]
```

## Functions

Functions are one of the fundamental building blocks in JavaScript. A function in JavaScript is similar to a procedure—a set of statements that performs a task or calculates a value, but for a procedure to qualify as a function, it should take some input and return an output where there is some obvious relationship between the input and the output. To use a function, you must define it somewhere in the scope from which you wish to call it.

See also the [exhaustive reference chapter about JavaScript functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) to get to know the details.

[Functions - mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)

### Function declarations, parameters & arguments

A function definition (also called a function declaration, or function statement) consists of the `function` keyword, followed by:

The name of the function.
A list of parameters to the function, enclosed in parentheses and separated by commas.
The JavaScript statements that define the function, enclosed in curly braces, `{ /\* … \*/ }`.
For example, the following code defines a function named square:

```js
function square(number) {
  return number * number;
}
```

The function `square` takes one parameter, called `number`. The function consists of one statement that says to return the parameter of the function (that is, `number`) multiplied by itself.

### return

The `return` statement specifies the value returned by the function, which is `number * number`.

### value vs reference revisited

Parameters are essentially passed to functions **by value** — so if the code within the body of a function assigns a completely new value to a parameter that was passed to the function, **the change is not reflected globally or in the code which called that function**.

When you pass an object as a parameter, if the function changes the object's properties, that change is visible outside the function.

We can do another example:

```js
function printParms(parameter1, parameter2, parameter3) {
  // code to be executed
  console.log(`
  parameter1: ${parameter1}
  parameter2: ${parameter2}
  parameter3: ${parameter3}
  `);
}
```

### Calling functions

Defining a function does not execute it. Defining it names the function and specifies what to do when the function is called.

Calling the function actually performs the specified actions with the indicated parameters. For example, if you define the function square, you could call it as follows:

```js
square(5);
square(34);
```

```js
printParms(1, 2, 3);
printParms("hi", "my", "name");
```

### Arrow functions

An **arrow function expression** is a compact alternative to a traditional function expression, with some semantic differences and deliberate limitations in usage:

- Arrow functions don't have their own bindings to this, arguments, or super, and should not be used as methods.
- Arrow functions cannot be used as constructors. Calling them with new throws a TypeError. They also don't have access to the new.target keyword.
- Arrow functions cannot use yield within their body and cannot be created as generator functions.

```js
// Traditional anonymous function
(function (a) {
  return a + 100;
});

// 1. Remove the word "function" and place arrow between the argument and opening body brace
(a) => {
  return a + 100;
};

// 2. Remove the body braces and word "return" — the return is implied.
(a) => a + 100;
```

Let's try an example:

```js
const add100 = (a) => a + 100;
add100(3);
```

### bookmarklet

Bookmarklets are browser bookmarks that execute JavaScript instead of opening a webpage. They're also known as bookmark applets, favlets, or JavaScript bookmarks.

- [Making Bookmarklets](https://gist.github.com/caseywatts/c0cec1f89ccdb8b469b1)
- [cornify](https://www.cornify.com/extras)

```js
javascript: (function () {
  document.body.style.background = "pink";
})();
```

Remember we said sometimes we need the `\n` new line character for multiline output for **special cases**? This is it! Because when you copy paste the bookmarklet into the address to save... there are no new lines, so template literally don't really work for outputting multiple lines.

Let's do an example with:

[Mean, moody and magnificent: film noir studio portraits – in pictures](https://www.theguardian.com/film/gallery/2022/nov/10/mean-moody-and-magnificent-film-noir-studio-portraits-in-pictures)

## Assignment: Palindrome revisited

This time, we will amend the palindrome problem with more flexiblity in the input, such as:

"A man, a plan, a canal, Panama"

It should now be able to handle, upper and lower case characters in the sentence, as well as spaces and punctuations (, and .).

```js
function isPalindrome(sentence) {
  // your code here
  // should return true or false
}
```
