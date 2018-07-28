---
layout: post
title: Variable Environment in JavaScript
---

Variable environment is basically the location where a variable lives in memory. Variables with the same name that are declared in the [global execution context](https://kennyalmendral.github.io/javascript-execution-context/) are different from the ones that resides in a [function’s execution context](https://kennyalmendral.github.io/javascript-function-invocation-execution-stack/). Each [execution context](https://kennyalmendral.github.io/javascript-execution-context/) has its own variable environment.

To demonstrate, consider the following JavaScript code:

```javascript
function fn1() {
  var sampleVar = "World";
  console.log(sampleVar);
  fn2();
}

function fn2() {
  var sampleVar;
  console.log(sampleVar);
}

var sampleVar = "Hello";
console.log(sampleVar);
fn1();
```

which will output the following on the developer console:

```
Hello
World
undefined
```

First, the global execution context is created and the `sampleVar` variable declared on _line 12_ is put into memory during the [creation phase](https://kennyalmendral.github.io/javascript-execution-context/) and then gets assigned the string `"Hello"` as its value during the [execution phase](https://kennyalmendral.github.io/javascript-execution-context/). With that said, the variable environment of the global execution context (in a browser) is the [window object](https://www.w3schools.com/jsref/obj_window.asp){:target="_blank"}.

Afterwards, `fn1` is invoked and it creates its own execution context that is added on top of the global execution context. The execution context of `fn1` will be the variable environment of the `sampleVar` variable declared on _line 2_ and will be assigned the string `"World"` as its value.

Lastly, `fn2` is invoked inside `fn1` which creates another execution context that is added on top of the [execution stack](https://kennyalmendral.github.io/javascript-function-invocation-execution-stack/) and the `sampleVar` variable declared on _line 8_ will reside in this execution context and will be assigned the value of `undefined`.

**Previous Post:** [Function Invocation and the Execution Stack in JavaScript]({{ site.url }}/javascript-function-invocation-execution-stack/)

**Next Post:** [The JavaScript Scope Chain]({{ site.url }}/javascript-scope-chain/)

_This is part 4 of the [JavaScript Concepts]({{ site.url }}/javascript-concepts/){:target="_blank"} series._

----
