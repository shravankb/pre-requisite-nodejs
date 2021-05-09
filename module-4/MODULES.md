# Fundamentals of JavaScript

## Modules

As our application grows bigger, we want to split it into multiple files, so called “modules”. A module may contain a class or a library of functions for a specific purpose.

But eventually scripts became more and more complex, so the community invented a variety of ways to organize code into modules, special libraries to load modules on demand.

### What is a module?

A module is just a file. One script is one module. As simple as that.

Modules can load each other and use special directives export and import to interchange functionality, call functions of one module from another one:

- `export` keyword labels variables and functions that should be accessible from outside the current module.
- `import` allows the import of functionality from other modules.

For instance, if we have a file sayHi.js exporting a function:

```javascript
// 📁 sayHi.js
export function sayHi(user) {
  console.log(`Hello, ${user}!`);
}
```

Then another file may import and use it:

```javascript
// 📁 main.js
import { sayHi } from './sayHi.js';

console.log(sayHi); // function...
sayHi('John'); // Hello, John!
```
![module](../assets/module.png)

**[ :back: Back to Table of Content](https://github.com/shravankb/pre-requisite-nodejs)** 

**[ :next: Modules](https://github.com/shravankb/pre-requisite-nodejs/blob/main/module-4/DOM.md)**
