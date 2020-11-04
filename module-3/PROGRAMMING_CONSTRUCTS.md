# Fundamentals of JavaScript

## Conditional Statements

Conditional statement is a set of rules performed if a certain condition is met. The two types of conditional statements are:
- if
- else if

To declare an if statement in JavaScript you need to use the ‘if’ keyword. The syntax is as follows:

```javascript
if(condition) {
statement;
}
```

Else statement is used to execute a block of code if the same condition is false. The syntax is as follows:

```javascript
if(condition) {
statement a;
}
else (condition) {
statement b;
}
```

## Loops Constructs

Loops are used to repeat a specific block until some end condition is met. There are three categories of loops in JavaScript :

1. while loop
2. do while loop
3. for loop

#### while loop

While the condition is true, the code within the loop is executed.

The syntax is:

```javascript
 while(condition) {
loop code;
}
```

#### do-while loop

This loop will first execute the code, then check the condition and while the condition holds true, execute repeatedly.

The syntax is as follows:

```javascript
do {
loop code;
} while(condition);
```

#### for loop

The for loop repeatedly executes the loop code while a given condition is TRUE. It tests the condition before executing the 
loop body.

The syntax is:

```javascript
for(initialisationExpression; testExpression; incrementalExpression) {
loop code;
}
```