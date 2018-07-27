---
layout: post
title: PHP Numbers
---

There are two types of number in PHP, namely, integers and floating point numbers, also known as “floats”.

## Integer

An integer is a whole number like 1, 2 and 3 as well as -1, -2 and -3.

## Floating point number

A floating point number is a number that has a decimal in it followed by a number of significant digits like 2.5 or -4.202.

**Example code:**

```php
$var1 = 1; // Integer
$var2 = 2.5; // Floating point number

echo ((1 + 5 + $var1) * $var2) / 2 - 3; // Outputs: 5.75
```

Take note that in PHP, basic math rules like the parentheses and the order of operations between multiplication, division, addition and subtraction still applies.

Therefore, `1 + 5 + $var1` will be evaluated first which results to `7` and then gets multiplied by the value of `$var2` which is `2.5` and then gets divided by `2` and lastly, gets subtracted by `3` which results to `5.75`.

**Previous Post:** [PHP String Functions](https://kennyalmendral.github.io/php-string-functions/)

**Next Post:** [PHP Number Functions and Operations](https://kennyalmendral.github.io/php-number-functions-operations/)

_This is part 6 of the [PHP Basics](https://kennyalmendral.github.io/php-basics/){:target="_blank"} series._

---
