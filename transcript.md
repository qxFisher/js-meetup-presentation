1 slide. 
JavaScript is single threaded, meaning that two bits of script cannot run at the same time; they have to run one after another. As a human being, you're multithreaded. You can type with multiple fingers, you can drive and hold a conversation at the same time. But we have one blocking function - sneezing, where all current activity must be suspended for the duration of the sneeze. That's pretty annoying, especially when you're driving and trying to hold a conversation. And in this way promises will help us.

2 slide. What is a Promise?
1.A promise is an object that represents the return value or the thrown exception that the function may eventually provide.
In other words, a promise represents a value that is not yet known.
2.You should know that A promise is an asynchronous value.
3.Promises are one way to deal with asynchronous code, without writing too many callbacks in your code.
Javascript Promises are not difficult. However, lots of people find it a little bit hard to understand at the beginning. And I would like to tell you about promises in easy way.

3 slide. How promises work
We start by instantiating a new Promise object and passing it a callback function. The callback takes two arguments, resolve and reject, which are both functions. 

4 slide. Resolve and reject are two callbacks that you use to specify when a promise has either fulfilled when something worked or rejected when something went wrong. A Promise object starts out with a state of pending, to indicate the asynchronous code it's controlling has neither fulfilled or rejected. The function passed to new Promise is called the executor. When the promise is created, this executor function runs automatically. It contains the producing code, that should eventually produce a result. 

5 slide. Here’s an example of a Promise constructor and a simple executor function with its “producing code” 
We can see two things by running the code above:
1.The executor is called automatically and immediately (by the new Promise).
2.The executor receives two arguments: resolve and reject — these functions are pre-defined by the JavaScript engine. So we don’t need to create them. Instead, we should write the executor to call them when ready.
After one second of “processing”, the executor calls resolve to produce the result. Result here is “Done”.
That was an example of a “fulfilled promise”.

6 slide. There can be only a single result or an error
The executor should call only one resolve or reject. The promise’s state change is final.
All further calls of resolve and reject are ignored – reject new Error and set timeout doesn’t work.
And another feature that resolve and reject expect only one argument and will ignore additional arguments.

7 slide. Promise methods
Promise.all() is used If you need to synchronize different promises, Promise.all() helps you define a list of promises, and execute something when they are all resolved.
Promise.race() - runs when the first of the promises you pass to it resolves, and it runs the attached callback just once, with the result of the first promise resolved.
Promise.reject() Returns a Promise object that is rejected with the given reason.
Promise.resolve() Returns a Promise object that is resolved with the given value. 

8 slide. Image onload promise 
let me show you what this actually looks like. 
In this example I'm wrapping an image tag loader in a promise because I want to do some work after the image loads on the page. I'm using the image tags onload handler to specify success. Onload calls resolved which queues up the function passed to then to execute after this function finishes executing
Note. The JavaScript engine does not immediately stop executing this function upon calling resolved

9 slide.  And this is another example.
Any value passed to resolve or reject will be received as an argument by this subsequent dot then or dot catch. In the event that nothing is passed to resolve or reject - it's totally fine! The next link in the chain simply receives undefined
There's a another case and that is if the value that's passed is a promise. if so the then promise will execute first and then whatever value it resolves to will be passed to the next link in the chain

10 slide. Promises chaining
Then() isn't the end of the story, you can chain .thens together to transform values or run additional async actions one after another.
Look at this example. Promise.then returns a promise, so that we can call the next .then on it. When a handler returns a value, it becomes the result of that promise, so the next .then is called with it.

11 slide. Error handling
Developers know that functions can fail. In the network world, functions can fail for many reasons. 

12 slide. Error :C
Asynchronous actions may sometimes fail: in case of an error the promise becomes rejected. For instance, fetch fails if the remote server is not available. We can use .catch to handle errors.
1.Note that resolve and reject have the same syntax. Resolve leads to the next then in the chain while reject leads to the next catch. 
2.When anything in the chain of promises fails and raises an error or rejects the promise, the control goes to the nearest catch() statement down the chain.

13 slide. CASCADING ERRORS
If inside the catch() you raise an error, you can append a second catch() to handle it, and so on.

14 slide. Arrow Functions
If you’re very tired of typing and reading code you can use arrow functions.
Or even like this:
Arrow functions are ES6’s best feature and they can help reduce your train of Promise chains to much more clear blocks of code.

15 slide. JavaScript Promises support and Polyfill
JavaScript Promises are part of the ECMAscript 6 standards and should be supported by all browsers eventually. At the moment that promise is already realized in recent versions of Chrome, FF, Safari, and on mobile browsers with the exception of IE.

Slide 16. 
Promises are going to become the standard approach for dealing with large amounts of asynchronous operations. However, I’ve found them to generally offer a lot of benefits when working on complex sequences of operations where some are sync, and others async. If you have not tried them yet I’d really recommend it on your next project.

Slide 17. Thank You


