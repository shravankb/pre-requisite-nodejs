# Synchronous v/s Asynchronous Programming


When you execute something synchronously, you wait for it to finish before moving on to another task. When you 
execute something asynchronously, you can move on to another task before it finishes.

In programming, **synchronous operations** block instructions until the task is completed, while **asynchronous operations** can execute without blocking other operations.

>Simplest Analogical Example for a Synchonrous Operation: Supermarket line.
>Super market line will be one person at the time, the person at back will wait until rest of the persons are dispatched.

Asynchronous operations are generally completed by firing an event or by calling a provided callback function.

>Simplest Analogical Example for an Asynchonrous Operation: Restaurant
> in restaurants there are 30, 40, 100 eating at the same time, if two persons order something at menu at the 
>same time, for example one orders one glass of water, one order the most complex thing at menu, the person who 
>asks the glass of water is attented first than the person who asks the most complex thing in menu.


#### Synchronous Operations

Synchronous Operations that run block the next operation until it completes. Blocking operations may not always seem 
like an issue because computers are fast. For example: creating an array and logging the values in an array.

```javascript
Array
    .from({ length: 5 }, (v, i) => i + 1)
    .forEach(value => console.log(value))
```

However if the length was 5000, it would take longer before the array was logged. The difference in timing is a 
result of the thread being locked for a longer time.
Making synchronous calls to resources can lead to long response times locking up the UI until the resource responds. 
As an example:

```javascript
const request = new XMLHttpRequest()
request.open('GET', 'https://httpstat.us', false)
request.send(null)

if (request.status === 200) {
  console.log(request.responseText)
}
```


Making requests to your own services like a database can have the same effect. A common webpage will have many 
requests to make under unique circumstances, and as a developer, you'll want those requests to start as soon as 
possible but still allow the rest of the page to load what it can to enable the requests.

`This is when asynchronous operations become powerful.`

#### Asynchronous Operations

Asynchronous Operations happen independently from the main program flow. A common use for asynchronous code 
is querying a database and using the result. Passing in a callback is a way to interact with the response or 
error.

```javascript
const database = require('thecoolestnewestdbframework')
database('table')
    .select('*')
    .asCallback((err, res) => {
        if (err) {
            throw err
        }
        // do something with the result
    })
```
While the database loads and responds to the request, the rest of the page or other resources cannot load.

**[ :back: Back to Table of Content](https://github.com/shravankb/pre-requisite-nodejs)** 

**[ :next: Data Types](https://github.com/shravankb/pre-requisite-nodejs/blob/main/module-3/DATA_TYPES.md)**
