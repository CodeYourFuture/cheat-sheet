# Javascript Cheat Sheet

A small primer on the syntax and rules seen so far

## Basics

The ground rules for the Javascript language

### Comments

A comment is a piece of text that will be skipped by the interpreter. It's useful to leave remarks in the code or to temporary deactivate a certain piece of code.

``` js
// any text on a line after a double dash won't be considered code
```

``` js
/*
    dash + star are a 
    useful way
    to do multine comments
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


flow
    if
    loops
    functions

advanced
    scope
    function reference
    callback
    promises
    template literals

es6
    const
    let
    arrow functions

style
    naming and case
    spacing
    semicolons
    indent
    shortcuts

misc
    js vs node vs chrome