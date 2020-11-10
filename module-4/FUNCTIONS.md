# Fundamentals of JavaScript

## Functions

Functions are the main "building blocks" of the program. They allow the code to be called many times without repetition.

You must've already seen examples of built-in functions, like alert("message"), console.log("message"). But we can create functions of our own as well.

### Function Declaration

To create a function we can use a function declaration, as shown below:

```javascript
  function showMessage() {
    console.log( 'Hello everyone!' );
  }
```

The `function` keyword goes first, then goes the *name of the function*, then a list of *parameters* in the brackets (empty in the example above) and finally the code of the function, also named "the function body".


![functionDeclaration](../assets/function_basics.png)


Our new function can be called by its name: `showMessage()`. We can invoke the function or call the function using the function name followed by `()`, for instance:

```javascript

// function declaration
function showMessage() {
  console.log( 'Hello everyone!' ); // function definition
}


/**
* function call; showMessage() has been called/invoked two times
*/
showMessage(); // Hello everyone!
showMessage(); // Hello everyone!

```

Note: A function can return a value back into the calling code as the result.


The simplest example would be a function that sums two values:

```javascript
function sum(a, b) {
  return a + b;
}

let result = sum(1, 2);

console.log( result ); // 3

```

#### Variable scope in functions


A variable has global scope if it exists during the life of the program and is accessible from anywhere in the program. A variable 
has function scope if it is declared within a function and is not accessible outside of that function and will cease to exist when
the function finishes execution.


<p float="left">
  <img src="../assets/javascript-scope.png" width="40%" />
  <img src="../assets/javascript-nested-scopes.png" width="40%" height="10%" /> 
</p>


With function scope, the parameters and variables that you define as part of a function are not available outside the function 
body; they are only visible within the function throughout the lifetime of the function.

```javascript

var num = 1;          // variable is global
function showGlobal() {
  console.log(num);         // uses the global num
}
showGlobal();         // 1

function showLocal(){
  var num = 2;        // num is local, hides the global num 
  console.log(num);
}
showLocal();           // 2

function showArgument(num) {
    console.log(num);       // arguments are locally scoped
}
showArgument(3);      // 3

```

What about the variable’s accessibility? Here’s one simple rule to remember:
> "The inner scope can access the variables of its outer scope."



## JavaScript Function Objects

> Note : Functions are first-class objects

In JavaScript, functions are objects. You can work with functions as if they were objects. 

For example, you can assign functions to variables, to array elements, and to other objects. They can also be passed around as arguments to other functions or be returned from those functions.

Let's first run a small test and confirm that a function is indeed an object instance:

```javascript

function message() {
    console.log("Greetings Linda!");
}

console.log(typeof message);                   // function
console.log(message instanceof Object);        // true

```

JavaScript functions are a special type of objects, called *function objects*. A function object includes a string which holds the actual code -- **the function body** -- of the function. The code is literally just a string. 

Although not recommended, you can create a new function object by passing the built-in Function constructor a string of code, like so:

```javascript

var body = "return Math.PI * radius * radius";

var circle = new Function("radius", body);    // new Function([...arguments], functionDefinition);

console.log(circle(5));                       // 78.53981633974483

```

### Different forms of Functions:

There are two forms of writing/defining function:

1. Named Functions
2. Anonymous Functions

There is a special syntax for declaring functions:

```javascript
function name([param[, param[, ... param]]]) {
   statements
}

/**
* name : the function name
* param : the name of an argument to be passed to the function
* statements : the statements comprising the body of the function
*/

```


Here is an example of an **anonymous function expression** (the name is not used):

```javascript
var myFunction = function() {
    statements
}
```

It is also possible to provide a name inside the definition in order to create a **named function expression**:

```javascript
function myFunction() {  
    statements
}
```

One of the benefits of creating a named function expression is that in case we encountered an error, the stack trace will contain the name of the function, making it easier to find the origin of the error.

As we can see, both examples do not start with the function keyword. Statements involving functions which do not start with function are function expressions.

Following these aspects, there are some patterns of function, viz., IIFE and generator function.

An **IIFE (Immediately Invoked Function Expression)** is a JavaScript function that runs as soon as it is defined.An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined.

```javascript

(function () {
    statements
})();
```
It is a design pattern which is also known as a Self-Executing Anonymous Function and contains two major parts:

1. The first is the anonymous function with lexical scope enclosed within the Grouping Operator (). This prevents accessing variables within the IIFE idiom as well as polluting the global scope.
2. The second part creates the immediately invoked function expression () through which the JavaScript engine will directly interpret the function.


Likewise, generator functions was the new way of working with functions, introduced recently with ES7 (ES - standards of JS). 

A function that can stop midway and then continue from where it stopped. Appears to be a function; behaves like an
**iterator**. `yield` keyword pauses generator function execution.


```javascript
function * generatorFunction() { // Line 1
  console.log('This will be executed first.');
  yield 'Hello, ';   // Line 2
  console.log('I will be printed after the pause');  
  yield 'World!';
}

const generatorObject = generatorFunction(); // Line 3
console.log(generatorObject.next().value); // Line 4
console.log(generatorObject.next().value); // Line 5
console.log(generatorObject.next().value); // Line 6

// OUTPUT: 
//  This will be executed first.
//  Hello, 
//  I will be printed after the pause
//  World!
//  undefined
```