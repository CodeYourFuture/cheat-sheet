# Javascript Cheat Sheet

A small primer on the syntax and rules seen so far.

## Table of Contents
* Basics
    * [Comments](###Comments)
    * [Data Types](###Data-Types)
    * [Variables and Assignment](###Variables-and-Assignment)
    * [Logging](###Logging)
    * [Operators](###Operators)
* Execution Flow
    * [If Statements](###If-Statements)
    * [Loops](###Loops)
    * [Functions](###Functions)
* Advanced Concepts
    * [Function reference](###Function-reference)
    * [Callbacks](###Callbacks)
    * [Scope](###Scope)
    * [Map](###Map)
    * [Reduce](###Reduce)
    * [Promises](###Promises)
* ES6 / ES2015
    * [Let](###Let)
    * [Const](###Const)
    * [Template Literals](###Template-Literals)
    * [Arrow Functions](###Arrow-Functions)

## Basics

The ground rules for the Javascript language.

### Comments

A comment is a piece of text that will be skipped by the interpreter. It's useful to leave remarks in the code or to temporary deactivate a certain piece of code.

``` js
// any text on a line after a double dash won't be considered code
```

``` js
/*
    multiline comments a
    useful way
    to have long pieces of text
    without having to comment each line
*/
```

### Data Types

Javascript understand different type of data, each with it's own syntax and rules.

Strings: can be delimited by either single `'` or double `"` quotes
``` js
'Hello'

"Hello"
```

Numbers: there is no distinction between entire, decimal or negative numbers, they are all the same type.
``` js
10 

10.15

-23
```

Booleans: can be either true or false. No quotes required (if you add quotes, they will be strings instead).
``` js
true

false
```

Arrays: a collection of other data types, with a specified order. The included elements can be of any other type.
``` js
[1,2,3]

['leon', 'cat', 'puma']

[1.2, 'car', true]

[[1,4,3], 6, 1]  // nested array
```

Objects: a collection of key-value pairs, with each value accessible by key and no specified order. The included elements can be of any other type.
``` js
{
    key: 'value',
    secondKey: 142,
    thirdKey: ['hello', 'this', 'is', 'an', 'array']
}
```

### Variables and Assignment

A variable stores a value for manipulation and later usage. The name of the variable should come after `var` and a value is assigned with `=`.

``` js
var myNumber = 1;

var mySecondNumber = 2;

var myText = 'Hello friend';

var copyOfMyNumber = myNumber;  // assign the value of 'myNumber' to a new var called 'copyOfMyNumber'
```

### Logging

Logging is a easy way to print information to the screen, to debug or display results.

``` js
console.log('Hello World');

console.log(123.2);

var text = 'Hello there';
console.log(text);
```

### Operators

There are several operators that are used to manipulate variables. Here is a list of the most common. The same symbol might act differently on different Data types.

Numbers:
``` js
1 + 2  // sum, result is 3
1 - 2  // subtraction, result is -1

2 * 2  // multiplication, result is 4
5 / 2  // division, result is 2.5

5 % 2  // modulo, result is 1
```

Booleans:
``` js
true && true  // logic AND, result is true
true || false  // logic OR, result is true

!true  // logic NOT (negation), result is false
```

Strings:
``` js
'Hello ' + 'World'  // concatenation, result is 'Hello World'
```

Comparison:
``` js
1 === 1  // is equal, result is true
1 !== 1  // is not equal, result is false

1 > 1  // greater, result is false
1 >= 1  // greater or equal, result is true

1 < 1  // smaller, false
1 <= 1  // smaller or equal, true
```

## Execution flow

Logic required to direct the flow of a program.

### If Statements

If statements allow conditional execution of code depending on a initial condition.

Simple if/else:
``` js
var condition = true;

if (condition) {
    console.log('"condition" is true');
} else {
    console.log('"condition" is false');
}
```

Additional else if statement:
``` js
var number = 1;

if (number === 0) {
    console.log('"number" is 0');
} else if (number === 1) {
    console.log('"number" is 1');
} else {
    console.log('"number" is neither 0 or 1');
}
```

A if/else statement can also be simplified with a ternary operator:
``` js
var condition = true;

condition ? console.log('"condition" is true') : console.log('"condition" is false')
```

### Loops

Loops allow multiple exections of the same piece of code.

``` js
for (iteration = 0; iteration < 5; iteration++) {
    console.log('hello, iteration = ' + iteration);
}
```

``` js
var iteration = 0;
while (iteration < 10) {
    console.log('hello, iteration = ' + iteration);
    iteration = iteration + 1;
}
```

### Functions

Functions enclose a block of code, executing it only when invoked/called. They are used to package piece of code and allow for it to be called an used several times.

Simple functions:
``` js 
// define the function without executing the code in it
function myFunction() {
    console.log('Hello World');
}

// invoke the function and execute it
myFunction();
```

Function parameters:
``` js
function addNumbers(a, b) {
    var result = a + b;
    console.log('The result is: ', result);
}

// function can be invoked multiple times with different values
addNumbers(1, 4);
addNumbers(5, 5);
```

Function return value:
``` js
function returnAddedNumbers(a, b) {
    var result = a + b;
    return result;
}

// function will return a value that can be assigned to a variable for further use
var returnedValue = returnAddedNumbers(1, 1);
console.log('the returned value is: ', returnedValue);
```

## Advanced concepts

Extra concepts and rules useful for writing non-trivial javascript code.

### Function reference

A _reference_ to a function can be assigned to a variable. This is helpful to pass the reference around without executing the function itself.

``` js
function sayHello(name) {
    console.log('Hello, ' + name);
}

var functionReference = sayHello;  // note how the function is not called here

functionReference('your name');  // sayHello is executed here
```

### Callbacks

Callback is the conventional name for a function reference passed to a function as a parameter. It's not a keyword or reserved word in Javascript.

``` js
function printNumber(number) {
    console.log('the number is ' + number);
}

function mainFunction(callback) { 
    var result = 1 + 2;

    callback(result);  // invoke the function passed as parameter with the result. printNumber(result) is executed here
}

mainFunction(printNumber);  // printNumber passed as a function reference
```

### Scope

Variables are not 'visible' to all the code, but follow certain rules. Variables with the same names can exists in different contexts and have different values.

``` js
var outerVariable = 'outer';

function myFunction() {
    var innerVariable = 'inner';

    console.log(outerVariable, innerVariable);  // both are defined
}

console.log(outerVariable, innerVariable);  // innerVariable is undefined, as its scope is only the function body (between the {})
```

Variable name shadowing

``` js
var myVariable = 'outer';

function myFunction() {
    var myVariable = 'inner';

    console.log(myVariable);  // 'inner'
}

console.log(myVariable);  // 'outer'
```

### Map

Map is a method of Array objects that returns a new array. Each element of the new array is the result of the given callback applied to the corresponding element of the old array.

``` js
function doubleNumber(num) {
    return num * 2;
}

var oldArray = [1, 2, 3];

var newArray = oldArray.map(doubleNumber);  // the callback is a reference to the 'double' function

console.log(newArray);  // [2, 4, 6]
```

### Reduce

Redude is a method of Array objects that returns a single value. Reduce iterates over each element and applies the given callback. The callback accepts 2 param, the current element and the accumulator, which is the result of the last iteration. The final value of the accumulator is the return value.

``` js
function addToAccumulator(accumulator, number) {
    return accumulator + number;
}

var oldArray = [1, 2, 3];

var result = oldArray.reduce(addToAccumulator);

console.log(result);  // 6, which is 1 + 2 + 3

```

### Promises

Promises are a way to deal with asyncronous code, like http calls, without resorting to huge amounts of callbacks and deeply nested code. 

``` js
function successCallback(response) {
    console.log('promise resolved with response:', response);
}

function failureCallback(error) {
    console.log('promise rejected with error:', error);
}

fetch('www.example.com')  // the fetch command returns a promise
    .then(successCallback)  // specify function to call on success
    .catch(failureCallback);  // specify function to call on failure
```

Promise chaining:
``` js
fetch('www.example.com')
    .then(function(response) {
        return response.status;  // return values are passed as argument to the next 'then' element
    })
    .then(function(status) {
        console.log('status code is:', status);
    })
```

## ES6 / ES2015

New syntax and features introduced in the modern version of Javascript, not available in older browsers or version of node.


### Let

Let declares a value, similar to the `var` statement, but with a block rather than global scope.

``` js
if (true) {
    var myVar = 1;
}
console.log(myVar);  // 1

if (true) {
    let myLet = 1;
}
console.log(myLet);  // not defined
```

### Const

Declares a constant value with the same scoping rules as `let`. Can't be redefined or assigned a new value. The check is carried only on the root reference, so child elements of a array/object can still be manipulated.

``` js
const myConstant = 1;

const myConstant = 2;  // will throw an error due to attemped redefinition

myConstant = 3;  // will throw an error due to attemped assignment
```

Reassignment of nested elements is valid:
``` js
const myArray = [1,2,3];
myArray[0] = 5;
console.log(myArray);  // [5,2,3]

const myObject = { a: 1, b: 2 };
myObject.b = 5;
console.log(myObject);  // { a: 1, b: 5 }
```

### Template Literals

String interpolation, allowing for easier dynamic string creation.

``` js
const myName = 'Person';

const interpolatedString = `Hello ${myName}! 1 plus 1 is equal to ${1 + 1}`;

console.log(interpolatedString);  // 'Hello Person! 1 plus 1 is equal to 2
```

### Arrow Functions

Arrow functions are special functions that are commonly used due to the more concise form over classical functions.
They do not have their own `this`, `arguments`, `super` and `target.new` values, leading to some simplications in more advanced JS code.

``` js
const doubleClassic = function(number) {
    return number * 2;
}

const doubleV1 = (number) => {
    return number * 2;
}

const doubleV2 = number => {  // single arguments do not require parentheses around it
    return number * 2;
}

const doubleV3 = number => number * 2;  // single line function body do not require curly braces, and the return value is implicit.

/* all 4 functions are equivalent */
```


## TODO:
* style
    * naming a2nd case
    * spacing
    * semicolons
    * indent
    * shortcuts

* misc
    * js vs node vs chrome