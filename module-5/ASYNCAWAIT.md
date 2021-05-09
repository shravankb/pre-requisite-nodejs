# Fundamentals of JavaScript

## Async-Await Pattern


An async function is syntactic sugar over promises, the code looks much cleaner. Its asynchronous code 
looks and behaves a little more like synchronous code. With async/await, you really wait for one promise 
to resolve before moving to the next line.


> ES7 introduced a new way to add async behavior in JavaScript and make working with promises easier.

With the introduction of the async and await keywords, we can create async functions which implicitly return a promise. 
But.. how can we do that? 

Previously, we saw that we can explicitly create promises using the Promise object, whether it was by typing 
`new Promise(() => {})` , `Promise.resolve`, or `Promise.reject`.

Instead of explicitly using the `Promise` object, we can now create asynchronous functions that implicitly return 
an object. This means that we no longer have to write any `Promise` object ourselves.

![async-await](../assets/asyncawait-0.png)

Although the fact that **async** functions implicitly return promises is pretty great, the real power of `async` functions 
can be seen when using the `await` keyword. 

With the `await` keyword, we can suspend the asynchronous function while we wait for the `await`ed value return a 
resolved promise. If we want to get the value of this resolved promise, like we previously did with the `then()` callback, 
we can assign variables to the `await`ed promise value.

Let's see what happens when we run the following block of code:


![async-await](../assets/asyncawait-1.gif)


What's happening here?

![async-await](../assets/asyncawait-2.gif)

First, the engine encounters a `console.log`. It gets popped onto the call stack, after which `Before function!` 
gets logged.

![async-await](../assets/asyncawait-3.gif)

Then, we invoke the async function `myFunc()`, after which the function body of myFunc runs. On the very first 
line within the function body, we call another console.log, this time with the string In function!. The console.log 
gets added to the call stack, logs the value, and gets popped off.

![async-await](../assets/asyncawait-4.gif)

The function body keeps on being executed, which gets us to the second line. Finally, we see an `await` keyword.


The first thing that happens is that the value that gets awaited gets executed: the function `one` in this case. 
It gets popped onto the call stack, and eventually returns a resolved promise. Once the promise has resolved and 
`one` returned a value, the engine encounters the `await` keyword.

When encountering an `await` keyword, the `async` function gets suspended. The execution of the function body 
**gets paused**, and the rest of the async function gets run in a microtask instead of a regular task.

![async-await](../assets/asyncawait-5.gif)

Now that the async function `myFunc` is suspended as it encountered the `await` keyword, the engine jumps out of the 
async function and continues executing the code in the execution context in which the async function got called: 
the global execution context in this case.

![async-await](../assets/asyncawait-6.gif)

Finally, there are no more tasks to run in the global execution context. The event loop checks to see if there are 
any microtasks queued up and there are the `async` myFunc function is queued up after resolving the valued of `one`. 
`myFunc` gets popped back onto the call stack, and continues running where it previously left off.

The variable `res` finally gets its value, namely the value of the resolved promise that `one` returned. We invoke 
`console.log` with the value of res: the string `One!` in this case. `One!` gets logged to the console and gets 
popped off the call stack.


Did you notice how `async` functions are different compared to a promise `then`? The `await` keyword suspends the 
`async` function, whereas the Promise body would've kept on being executed if we would've used `then`.

You can have a look at [Draft ECMAScript 6 Specification Proposal](https://github.com/domenic/promises-unwrapping).

**[ :back: Back to Table of Content](https://github.com/shravankb/pre-requisite-nodejs)** 

**[ :next: ECMASCRIPT](https://github.com/shravankb/ECMAScript-Specifications#what-is-ecmascript)**