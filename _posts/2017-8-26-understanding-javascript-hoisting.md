---
layout: post
title: Understanding Hoisting in JavaScript
---

Variables and functions in JavaScript behave a little bit different from other languages like PHP.

Take the code below as an example:

```javascript
console.log(sampleVar);
sampleFn();

var sampleVar = 'Sample Variable';

function sampleFn() {
  console.log('Called sampleFun()');
}
```

Notice that I accessed the variable `sampleVar` via `console.log` and invoked the function `sampleFn` before declaring them.

In other languages, accessing a variable before declaring it will generate an error, but when I run the code on the browser, it doesn't show any error and outputs the following instead:

```
undefined
Called sampleFun()
```

And why is that? Enter Hoisting \m/

## Hoisting

In JavaScript, variables and functions go through a process called as "Hoisting" which sets up memory space for variables and functions and it happens during the [creation phase](https://kennyalmendral.github.io/javascript-execution-context/).

During this process, variables are initially set to `undefined` while functions will sit in memory in its entirety.

## undefined

A declared variable that is uninitialized is by default "undefined". It's basically a primitive value or special keyword that JavaScript has within it internally that means that a variable hasn't been set.

Modify the code and declare the `sampleVar` variable before accessing it via `console.log`.

```javascript
var sampleVar = 'Sample Variable';

console.log(sampleVar);
sampleFn();

function sampleFn() {
  console.log('Called sampleFun()');
}
```

Save the file and run it in the browser, then open up the developer console:

```
Sample Variable
Called sampleFun()
```

Even though the value of the `sampleVar` variable is now assigned with the `"Sample Variable"` string as its value, keep in mind that during the creation phase, the `sampleVar` variable is _hoisted_ (its value is initially set to `undefined`). It's during the [execution phase](https://kennyalmendral.github.io/javascript-execution-context/) that the `"Sample Variable"` string is assigned to the `sampleVar` variable.

----
