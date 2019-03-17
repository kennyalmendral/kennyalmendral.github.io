---
layout: post
title: Function Invocation and the Execution Stack in JavaScript
---

Function invocation is just another term for calling a function using the open and close parentheses notation.

To see it in action, create a JavaScript file and inside it, add a function that adds two numbers.

```javascript
function add() {
  return 1 + 2;
}
```

Run it in the browser and open up the developer console. On the developer console, enter the function name **add**, hit enter and you'll get the following result (which is the function definition itself):

```
f add() {
  return 1 + 2;
}
```

Enter the function name again in the developer console, but this time append the open and close parentheses at the end like this: **add()**, hit enter and you'll get the expected result of the function which is 3.

When a function is invoked, an [execution context](https://kennyalmendral.github.io/javascript-execution-context/) is created and is added on top of the so-called "Execution Stack" and the one that's currently on top of the stack is the one that's _currently running_.

## Execution Stack

When a JavaScript file is executed on the browser, the [global execution context](https://kennyalmendral.github.io/javascript-execution-context/) will be the first item that will be placed on the stack and if that JavaScript file contains some functions, those will be added on top of the stack _in the order they are invoked_.

When the function that's currently running finishes its execution, it will be _removed from the stack_. This process will go on until it gets back to the global execution context.

Consider the following JavaScript code:

```javascript
function fn1() {
  console.log("invoked fn1()");
}

function fn2() {
  console.log("invoked fn2()");
}

function fn3() {
  console.log("invoked fn3()");
}

fn2();
fn1();
fn3();
```

which would output the following result in the developer console:

```
invoked fn2()
invoked fn1()
invoked fn3()
```

...and here's what happened behind the scenes:

Initially, the global execution context is added to the stack and goes through the [creation phase](https://kennyalmendral.github.io/javascript-execution-context/).

During this phase, the `fn1()`, `fn2()` and `fn3()` functions are [hoisted](https://kennyalmendral.github.io/understanding-javascript-hoisting/).

Afterwards, it goes through the [execution phase](https://kennyalmendral.github.io/javascript-execution-context/) and in this phase, `fn2()` is invoked and it creates an execution context that is added on top of the global execution context and after it's done with its execution, it will be removed from the stack. The same is true with `fn1()` and `fn3()`.

**Previous Post:** [Execution Context in JavaScript]({{ site.url }}/javascript-execution-context/)

**Next Post:** [Variable Environment in JavaScript]({{ site.url }}/javascript-variable-environment/)

_This is part 3 of the [JavaScript Concepts]({{ site.url }}/javascript-concepts/){:target="_blank"} series._

----
