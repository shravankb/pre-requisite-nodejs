# Fundamentals of JavaScript

## Data types

JavaScript basically supports 7 basic data types; these otherwise called as primitive data types viz.,

- Number
- String
- Boolean
- "null" value
- "undefined"

**Number**
```javascript
var n =123;

const pi=3.14
```
The number type serves both for integer and floating point numbers. There are many operations for numbers, 
e.g. multiplication *'*'*, division *'/'*, addition *'+'*, substraction *'-'* and so on.

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

