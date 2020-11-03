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

<br><br><br><hr>

### Non - Primitive Data Types

Non - Primitive Data types supported by JavaScript are viz.,

- [Object](#Object)
- [Function](#Function)


#### Object

A JavaScript object is a collection of properties where each property has a name and a value.  The name of a property can be 
any string, including an empty string. 

The value can be any value, such as a string, Boolean, number, and null, but it cannot be "undefined". The object's 
properties can be defined even after you start using the object.

```javascript
var rect = {};          // creates an empty object
rect.width = 20;
rect.height = 10;

console.log(rect.width);      // 20
console.log(rect.height);     // 10
```

As an alternative you can immediately assign properties and their values in the literal notation.

```javascript

var rect = { width: 20, height: 10 };
console.log(rect.width);      //  20
console.log(rect.height);     //  10
```

Property values are not limited to primitive types, like number or string; you can also add properties that are other objects, 
including functions. When a function is added to an object it is called a method.

```javascript
var rect = { width: 20, height: 10 };

// add new object
rect.color = { red: 0, green: 255, blue: 128 }; 

// add new method
rect.getArea = function() {                    
    return this.width * this.height;
};
console.log(rect.color.red);  //  0
console.log(rect.getArea());  //  200
```

Property values can be retrieved in one of two ways; dot notation and bracket notation. Below are examples of each:

```javascript
var rect = { width: 20, height: 10 };
console.log(rect.width);             // 20 (dot notation)
console.log(rect["width"]);          // 20 (bracket notation)

// Note : Dot notation is used more often because it is easier to read and more compact. 
```

So when would you use bracket notation?
Square brackets allow you to use property names that are not valid identifiers and don't work with dot notation, 
for example when they have spaces in them or start with a number. 

```javascript
var shape = {
   "bounding box width": 20,                
   "bounding box height": 10
}

console.log(shape["bounding box width"]); // 20

```

**Exception**: JavaScript Array is also considered as an Object. Unlike other languages, arrays in JavaScript are not homogenous 
collection of elements.  

An array is a special variable, which can hold more than one value at a time.

```javascript
var cars = [];
cars[0] = "Ford"; 
cars[1] = "BMW";
cars[2] = "Honda";
cars[4] = 4000;
cars["six"] = "TVS";

.                 //    0       1       2       3     4        5
console.log(cars) // ["Ford", "BMW", "Honda", empty, 4000, six: "TVS"]
console.log(cars.length); // 5
console.log(cars[3]) // undefined
console.log(cars[4]) // 4000

```


#### Functions
