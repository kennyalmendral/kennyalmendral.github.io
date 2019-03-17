---
layout: post
title: The JavaScript Scope Chain
---

When an [execution context](https://kennyalmendral.github.io/javascript-execution-context/) is created through [function invocation](https://kennyalmendral.github.io/javascript-function-invocation-execution-stack/), aside from having its own variable environment also creates a reference to its outer environment and thus the "Scope Chain" occurs.

JavaScript does more than just look at the variable environment of the execution context that's currently running when accessing a variable inside it.

To see it in action, consider the following JavaScript code:

```javascript
function fn1() {
  console.log(sampleVar);
}

function fn2() {
  var sampleVar = 'World';
  fn1();
}

var sampleVar = 'Hello';
fn2();
```

which would output the following result in the developer console:

```
Hello
```

In the case of `fn1`, its outer environment is the [global execution context](https://kennyalmendral.github.io/javascript-execution-context/) and that's also the case for `fn2` because these two functions was declared in the global scope in the code. Even though `fn1` is invoked inside `fn2`'s execution context, `fn2`'s outer environment reference will still be the global execution context because it is where it was declared lexically.

Every execution context has a reference to its outer environment and when accessing a variable that doesn't exist (like in `fn1`) inside an execution context, JavaScript will search in that execution context's outer environment and so on until it gets to the global execution context. If it still didn't find the variable in the global scope, it will throw an error.

```
Uncaught ReferenceError: sampleVar is not defined
  at fn1 (app.js:2)
  at fn2 (app.js:7)
  at app.js:11
```

What if `fn1` is moved inside `fn2` like so:

```javascript
function fn2() {
  var sampleVar = 'World';
  fn1();
  
  function fn1() {
    console.log(sampleVar);
  }
}

var sampleVar = 'Hello';
fn2();
```

which will now output the following in the developer console:

```
World
```

The function `fn1` now sits lexically inside `fn2` and so its outer environment reference will be `fn2`'s execution context.

Another thing is that since `fn1` is declared inside `fn2`, it cannot be invoked anymore in the global execution context, only in the `fn2`'s execution context itself.

**Previous Post:** [Variable Environment in JavaScript]({{ site.url }}/javascript-variable-environment/)

**Next Post:** [The Synchronous Nature of JavaScript]({{ site.url }}/synchronous-javascript/)

_This is part 5 of the [JavaScript Concepts]({{ site.url }}/javascript-concepts/){:target="_blank"} series._

----
