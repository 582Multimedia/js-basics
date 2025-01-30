# 👋 Javascript Basics / Refresher Course 👋

[download Node.js](https://nodejs.org/en)
- in terminal, see node version type: $ node -v (without the dollar sign which just tells us to input this in terminal)
- enter node: $ node

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

### Sinlge-value output

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

### Intergers (whole numbers)

```js
console.log(1);
```

### Floating Point (decimal)

```js
console.log(0.1);
```

### String (Text)

Strings can only be written on a single line, by wrapping the text with either single quotes `'` or double quotes `"`.

```js
console.log("text");
console.log("1");
console.log(" ");
console.log("", "empty string");
```

If you want to write on more than one line, you can use the new line symbol `\n`.

#### Template literals

You can use template literals to write more than one line, instead of using regular single or double quotes, you can use **backticks** `` ` `` (the backticks key is usually under the `esc` key and next to the `1` key).

```js
console.log(`
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam luctus, urna non malesuada interdum, justo nibh ornare diam, sed maximus urna magna id augue. Sed condimentum in tellus ac tincidunt. Vestibulum molestie neque odio, eget iaculis ex iaculis quis. Nunc congue eleifend aliquam. In hac habitasse platea dictumst. Sed pulvinar aliquam eros sit amet varius. Maecenas pharetra nisi id luctus tincidunt. Fusce et efficitur lectus. Quisque cursus maximus tristique. Pellentesque eget nibh consequat, vulputate augue a, dictum massa. Donec suscipit mi quis purus sollicitudin, nec mattis enim egestas. Curabitur sed libero non risus sollicitudin laoreet nec malesuada nisl. Phasellus laoreet luctus est euismod tincidunt.

Aenean dignissim dolor eget tortor bibendum, in lacinia arcu elementum. Vivamus mollis ex id odio suscipit, vitae dignissim ante maximus. Phasellus vel congue diam. Donec eget imperdiet sem. Nulla egestas, erat non viverra ultrices, tortor sem tristique mauris, et viverra enim augue at enim. Duis vitae leo ac ex imperdiet tempus. Sed sed sapien vel felis maximus vulputate. Maecenas sed commodo dui. Mauris gravida a ex dignissim lobortis. Pellentesque commodo tincidunt leo, ut tristique turpis egestas at. Quisque eget magna eget metus finibus finibus vel sed eros. Mauris ullamcorper quam nibh, volutpat scelerisque arcu mattis non.

Fusce metus dui, dapibus ac elit ut, laoreet posuere est. Pellentesque consectetur metus sed risus facilisis dapibus. Maecenas quis porta nulla. Nulla consequat purus eget nunc finibus fringilla. Aenean non ultricies nunc, quis iaculis magna. Ut posuere interdum massa et interdum. Quisque luctus risus quam, quis aliquet libero accumsan at. Morbi vehicula dapibus metus porttitor tincidunt. Nunc et augue lacinia, dignissim neque sed, scelerisque est. Donec in vehicula leo, eu vulputate purus. Curabitur tristique, felis at semper egestas, libero eros malesuada felis, at euismod lectus odio vitae mi. In hac habitasse platea dictumst. Vestibulum feugiat molestie cursus.

Nam pellentesque varius accumsan. Vivamus lacinia ipsum vel velit congue commodo. Donec id gravida lacus, ac egestas ex. Donec odio lacus, mollis quis sollicitudin vitae, auctor vitae ante. Nunc ac odio ultrices, ornare felis ac, tempor nulla. Quisque vitae mauris in nisl malesuada vulputate. Aliquam quis cursus dolor, at dignissim dolor. Curabitur rhoncus at nulla quis hendrerit. In posuere elementum erat, ut fringilla velit ultricies vitae. Fusce sollicitudin enim quis placerat dignissim. Nam mattis tellus non nisi interdum, vitae auctor neque vestibulum. Aenean eget volutpat nulla. Duis ultrices, massa sed varius fermentum, nunc libero sodales eros, sed feugiat nunc purus nec massa. Curabitur auctor arcu nisl, ac fermentum neque faucibus quis.

Integer lobortis eleifend ipsum, ac vehicula nisl posuere quis. Vivamus laoreet lacus in faucibus venenatis. Vivamus non sagittis orci. Donec a leo risus. Sed nunc dui, gravida sit amet odio ac, lacinia condimentum arcu. Phasellus sit amet mauris turpis. Nam et augue diam. Aenean venenatis lectus quis lacus interdum sodales.
`);
```

### Boolean (true / false)

Truthy values are called booleans and are written in code **without quotes** (otherwise, it is considered a text and not actually truthy values).

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

### Logging mixed data in console

We saw that we can log two variables in the console, but we can also log mixed data, like Numbers and Strings and even variables together.

```js
console.log("Hi my name is:" + fname + " " + lname);
```

### Template literals with variables

But there is a better way to log variables within a line, using `${expression}` inside a template literal. The expression will be evaluated and replaced in this process.

**_Make sure to use proper template literal quotations!_**

```js
console.log("Hi my name is:" + fname + " " + lname);
console.log(`Hi my name is: ${fname} ${lname}!`);
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
let mixedString = `987.654testing321`;
console.log(1 + mixedString);
```

Let's try to coherse the string to Number like before...

```js
console.log(1 + +mixedString);
```

doesn't really work, it gives us `NaN`.

#### NaN

NaN stands for Not a Number

#### Parsing (string to integer or floating point)

```js
console.log(1 + +parseInt(mixedString));
```

This will give us `988`, 1 + 987 as a whole number.

```js
console.log(1 + parseFloat(mixedString));
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

## Boolean revisited & negation, if... else, Conditions, Logic Operators, == vs ===

### Boolean revisited & negation

Booleans like we said were truthy values, they can either be `true` or `false`.

#### Negation

True is the opposite of false, we can use the `!` negation operator to get the opposite of something.

```js
console.log(!true);
console.log(!false);
```

#### Double Negation

If something is the opposite of the opposite...

```js
console.log(!!true);
console.log(!!false);
```

### Truth cohersion

However, there are also alternative values that also mean true or false...

#### Numbers

Like in the case of a number, 0 would be empty and any other number it is not (even for negative numbers).

```js
console.log(!!0);
console.log(!!1);
console.log(!!1000);
console.log(!!-1);
```

#### Strings

```js
console.log(!!"");
console.log(!!"Hi!");
console.log(!!"0");
console.log(!!"1");
```

## if... else

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

## Equality == and ===

We can check equality using the `==` operator

```js
console.log(1 == 1);
console.log("hello" == "hello");
console.log("1" == 1);
console.log(0 == false);
```

Sometimes, it's also important to check if they have the **same type of data**, particularly for `Numbers`, we can use the strict equality `===` operator.

```js
console.log(1 === 1);
console.log("hello" === "hello");
console.log("1" === 1);
console.log(0 === false);
```

We can check equality using variables

```js
let bool1 = true;
let bool2 = false;
console.log(bool1 == bool2);
```

if we use it inside an if... else statement:

```js
if (bool1 == bool2) {
  console.log("true!");
} else {
  console.log("false.");
}
```

## two common mistakes: - using = (assignment operator) rather than == or === or wrong semicolon at the if line

This will fail:

```js
if (bool1 == bool2) console.log("true!");
else console.log("false.");
```

This also...

```js
if ((bool1 = bool2)) {
  console.log("true!");
} else {
  console.log("false.");
}
console.log(`Values:
bool1: ${bool1}
bool2: ${bool2}`);
```

If we invert the value of bool2 before we run it again...

```js
if ((bool1 = !bool2)) {
  console.log("true!");
} else {
  console.log("false.");
}
console.log(`Values:
bool1: ${bool1}
bool2: ${bool2}`);
```

## Logical operators

### Operators

| Operator  | Usage            | Description                                                       |
| --------- | ---------------- | ----------------------------------------------------------------- |
| AND (&&)  | expr1 && expr2   | If both are true, return true; otherwise, return false.           |
| OR (\|\|) | expr1 \|\| expr2 | If either is true, return true; if both are false, returns false. |
| XOR (^)   | expr1 ^ expr2    | Return true if ONLY one of the two if true.                       |
| NOT (!)   | !expr            | If expression is true, return false and vice versa.               |

### Logic table

| expr1                   | expr2                   | AND                | OR                 | XOR                |
| ----------------------- | ----------------------- | ------------------ | ------------------ | ------------------ |
| :white_check_mark: true | :white_check_mark: true | :white_check_mark: | :white_check_mark: | :x:                |
| :white_check_mark: true | :x: false               | :x:                | :white_check_mark: | :white_check_mark: |
| :x: false               | :white_check_mark: true | :x:                | :white_check_mark: | :white_check_mark: |
| :x: false               | :x: false               | :x:                | :x:                | :x:                |

### Examples

#### AND

```js
let tryAnd;
tryAnd = 12;
if (tryAnd > 10 && tryAnd < 20) {
  console.log(`${tryAnd} is between 11 and 19.`);
} else {
  console.log(`${tryAnd} is NOT between 11 and 19.`);
}
```

#### OR

```js
let tryOr;
tryOr = 9;
if (tryOr < 10 || tryOr > 20) {
  console.log(`${tryOr} is smaller than 10 or bigger than 20.`);
} else {
  console.log(`${tryOr} is between 10 and 20.`);
}
```

#### XOR

```js
let tryXor;
tryXor = 9;
if ((tryXor < 10) ^ (tryXor % 3 == 0)) {
  console.log(
    `${tryXor} is either smaller than 10 or divisible by 3, but not both.`
  );
} else {
  console.log(
    `${tryXor} is either:
    - smaller than 10 and divisible by 3
    or
    - not smaller than 10 and not divisible by 3.`
  );
}
```

#### XOR and NOT

```js
let tryXorNot;
tryXorNot = 9;
if ((tryXorNot < 10) ^ !(tryXorNot % 3)) {
  console.log(
    `${tryXorNot} is either smaller than 10 or divisible by 3, but not both.`
  );
} else {
  console.log(
    `${tryXorNot} is either:
    - smaller than 10 and divisible by 3
    or
    - not smaller than 10 and not divisible by 3.`
  );
}
```

## switch, case, break

```js
const expr = "Papayas";
switch (expr) {
  case "Oranges":
    console.log("Oranges are $0.59 a pound.");
    break;
  case "Mangoes":
  case "Papayas":
    console.log("Mangoes and papayas are $2.79 a pound.");
    // Expected output: "Mangoes and papayas are $2.79 a pound."
    break;
  default:
    console.log(`Sorry, we are out of ${expr}.`);
}
```

## loops: while, do... while, for, nested loops

### while loop

When using a `while` loop, the condition is verified **before** each iteration of the code block enclosed within curly brackets `{}`.

```js
let n = 0;

while (n < 3) {
  n++;
}
console.log(n);
```

### do.. while loop

When using a `do... while` loop, the condition is verified **after** each iteration of the code block enclosed within curly brackets `{}`.

> [!NOTE]
> A `do... while` loop will run **at least once** compared to a `while` loop since it will run **after** each iteration.

```js
let result = "";
let i = 0;

do {
  i = i + 1;
  result = result + i;
} while (i < 5);

console.log(result);
```

## variables revisited, for loop: global vs local / block scope

Think levels of government: federal, provincal, municipal. When you go from the global scope into a local scope, the value can be redefined for that scope and when we exit and go back to the global scope, the value returns back to the global value.

```js
let scope = 5;
{
  let scope = 3;
}
console.log(scope);
```

```js
for (let step = 0; step < 5; step++) {
  console.log("Walking east one step");
}
```

```js
for (let countdown = 10; countdown > 0; countdown--) {
  console.log(countdown);
}
```

## arrays & objects

### arrays

```js
const colors = ["red", "yellow", "blue"];
const sequence = [1, 1, 2, 3, 5, 8, 13];
const random = ["tree", 795, [0, 1, 2]];
console.log(colors);
console.log(sequence);
console.log(random);
```

### Accessing data within an array using item index

An item in a JavaScript array is accessed by referring to the index number of the item in square brackets. We know 0 will always output the first item in an array.

```js
const firstColor = colors[0];
console.log(firstColor);
```

This will give us `red` as we expected.

### array length

We can get the length of an array using the `.length` property of the array.

```js
const sequenceLength = sequence.length;
console.log(sequenceLength);
```

### for loop using arrays or words

```js
let word = "tacocat";
for (let i = 0; i < word.length; i++) {
  console.log(word[i]);
}
```

## Assignment - Basic Palindrome

### :trollface:

For this exercise, use all the concepts above and divise a way to check if a word is a Palindrome or not.

A palindrome is a word, number, phrase, or other sequence of symbols that reads the same backwards as forwards, such as madam or racecar, the date "22/02/2022" and the sentence: "A man, a plan, a canal - Panama".

Sample code:

```js
let wordToCheck = "tacocat";
let isPalindrome;
// ... write some code
console.log(isPalindrome);
```

`isPalindrome` should be assigned a `true` or `false` value depending on if `wordToCheck` is a Palindrome or not.
