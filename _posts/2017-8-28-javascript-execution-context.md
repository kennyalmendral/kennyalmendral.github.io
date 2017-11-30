---
layout: post
title: Execution Context in JavaScript
---

When you run a JavaScript file in the browser or invoke a function, an "Execution Context" is created. The execution context that is created when a JavaScript file is executed on the browser is called as the "Global Execution Context".

## Global Execution Context

A wrapper around the code that you've written together with the code that you haven't. The code that you didn't wrote is created by the JavaScript engine.

To demonstrate, create an empty JavaScript file and run it in the browser, then open up the developer console and enter the keyword **window**, hit enter and you'll see the following results on the developer console:

```
window
Window {stop: f, open: f, alert: f, confirm: f, prompt: f, ...}
```

As you can see, it outputs the `Window` object which is a code that you didn't write and is created by the JavaScript engine.

The execution context that is created when a function is invoked is different from the global execution context. [Check this post](https://kennyalmendral.github.io/javascript-function-invocation-execution-stack/) for more information.

An execution context goes through two phases, namely, the "Creation Phase" and the "Execution Phase".

## Creation Phase

During this phase, the `Window` object (also called as the "Global Object"), the `this` keyword which points to the `Window` object itself and an "Outer Environment" are created by the JavaScript engine.

Afterwards, the JavaScript engine runs through your code and identifies the variables and functions that will be used during the execution phase. This process is called as [Hoisting](https://kennyalmendral.github.io/understanding-javascript-hoisting/).

## Execution Phase

This is the phase where your code is interpreted, compiled and executed line by line. Variable assignment happens during this phase.

----
