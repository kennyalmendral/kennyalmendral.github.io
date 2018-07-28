---
layout: post
title: The Synchronous Nature of JavaScript
---

Synchronous just means one at a time. In the context of JavaScript, one line of code is being executed one at a time and in the order they're written.

Even though JavaScript is synchronous in its execution, there's this thing called asynchronous callbacks or simply "Ajax" for short.

## Asynchronous Callbacks

Asynchronous means more than one at a time, thus, any lines of code can be executed at the same time and it doesn't matter the order they're written. JavaScript handles these asynchronous callbacks through an "Event Queue".

## Event Queue

When the [execution stack](https://kennyalmendral.github.io/javascript-function-invocation-execution-stack/) is empty, JavaScript will periodically watch the event queue and waits for something to be there (for example, a click event) and if something is there, it then checks if a particular function should be executed when that event is triggered and if so, that function creates its execution context that will be added on top of the execution stack.

When the function finishes its synchronous execution, it will be removed from the execution stack and since the execution stack is empty once again, JavaScript will check the event queue again for further items (if any) and repeats the same procedure.

Consider the following JavaScript code:

```javascript
function longRunningFunction() {
  var i = 0;
  
  while (i < 9999999999) {
    i++;
  }
  
  console.log('Finished longRunningFunction execution');
}

longRunningFunction();

function clickEventHandler() {
  console.log('Triggered click event');
}

document.addEventListener('click', clickEventHandler);
```

Run it in the browser and while the `longRunningFunction` is running, try clicking around and you'll notice that the `clickEventHandler` is not logging anything to the developer console.

When the `longRunningFunction` is done with its execution, which then outputs `Finished longRunningFunction execution` in the developer console, that's the time where the `clickEventHandler` will fire and log `Triggered click event` in the developer console.

**Previous Post:** [The JavaScript Scope Chain]({{ site.url }}/javascript-scope-chain/)

_This is part 6 of the [JavaScript Concepts]({{ site.url }}/javascript-concepts/){:target="_blank"} series._

----
