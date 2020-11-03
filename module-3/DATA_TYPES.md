# Fundamentals of JavaScript

## Primitive Data types ( Basic Data Types )

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
- ["null" value]()
- ["undefined"]()

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

**Note:** Double and single quotes are "simple" quotes. There's no difference between them in JavaScript.

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
