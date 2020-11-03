# Fundamentals of JavaScript

## Data Types

Two types of data: 
1. [Primitive Data Types](#primitive-data-types--basic-data-types-)
2. [Non - Primitive Data Types](#non-primitive-data-types--basic-data-types-)


### Primitive Data types ( Basic Data Types )

Primitive Values are numbers and strings, among other things. Open your browser's console and print these primitive 
values using console.log():

```javascript
// console.log() is the 'cout'/'System.out.print' of JavaScript
console.log(2);  
console.log("hello");
console.log(undefined);
```

![data-types](../assets/data-types.png)

JavaScript basically supports 7 basic data types; these otherwise called as primitive data types viz.,

- [Number](#Number)
- [String](#String)
- [Boolean](#Boolean)
- ["null" value](#null-value)
- ["undefined"](#undefined)

#### Number

```javascript
var n = 123;

const pi = 3.14;
```
The number type serves both for integer and floating point numbers. There are many operations for numbers, 
e.g. multiplication ( * ), division ( **/** ), addition ( **+** ), substraction ( **-** ) and so on.

Besides regular numbers, there are so-called "special numeric values" which also belong to that type: **Infinity**, 
**-Infinity** and **NaN**.

- Infinity represents the mathematical Infinity ∞. It is a special value that's greater than any number.
  We can get it as a result of division by zero:

```javascript
    console.log( 1 / 0 ); // Infinity

    console.log( Infinity ); // Infinity
```

- NaN represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance:

```javascript
    console.log( "not a number" / 2 ); // NaN, such division is erroneous
```

Special numeric values formally belong to the "number" type. Of course they are not numbers in a common sense of this word.

#### String

A string in JavaScript must be quoted.

```javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed ${str}`;
```

In JavaScript, there are 3 types of quotes.

1. Double quotes: ```"Hello"```.
2. Single quotes: ```'Hello'```.
3. Backticks: <code>&#96;Hello&#96;</code>.

*Note:* Double and single quotes are "simple" quotes. There's no difference between them in JavaScript.

Backticks are "extended functionality" quotes. They allow to embed variables and expressions into a string by wrapping them in ${…}, 
for example:

let name = "John";

```javascript
// console the variable 'name'
console.log( `Hello, ${name}!` ); // Hello, John!
```

#### Boolean

The boolean type has only two values: true and false.

This type is commonly used to store yes/no values: **true** means "yes, correct", and **false** means the "no, incorrect".

For instance:

```javascript
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
```

Boolean values also come as a result of comparisons:
```javascript
let isGreater = 4 > 1;
alert( isGreater ); // true (the comparison result is "yes")
```

#### "null" value

The special *null* value does not belong to any type of those described above. 
It forms a separate type of its own, which contains only the *null* value:

```javascript
let age = null;
```
The code above states that the age is unknown or empty for some reason.


In JavaScript null is not a "reference to a non-existing object" or a "null pointer" like in some other languages. It's 
just a special value which has the sense of "nothing", "empty" or "value unknown".


#### "undefined"

The special value *undefined* stands apart. It makes a type of its own, just like null. The meaning of undefined is 
**"value is not assigned"**.

If a variable is declared, but not assigned, then its value is exactly undefined:

```javascript
let x;
console.log(x); // shows "undefined"
```

Technically, it is possible to assign any variable to undefined:

```javascript
let x = 123;
x = undefined;
alert(x); // "undefined"
```

*Note:* But it's not recommended to do that. Normally, we use null to write an "empty" or an "unknown" value into 
the variable, and undefined is only used for checks, to see if the variable is assigned or similar.



