---
layout: post
title: PHP Numbers
---

There are two types of number in PHP, namely, integers and floating point numbers, also known as “floats”.

## Integer

An integer is a whole number like 1, 2 and 3 as well as -1, -2 and -3.

## Floating Point Number

A floating point number is a number that has a decimal in it followed by a number of significant digits like 2.5 or -4.202.

**Example code:**

```php
$var1 = 1; // Integer
$var2 = 2.5; // Floating Point Number

echo ((1 + 5 + $var1) * $var2) / 2 - 3; // Outputs: 5.75
```

Take note that in PHP, basic math rules like the parentheses and the order of operations between multiplication, division, addition and subtraction still applies.

Therefore...

+ `1 + 5 + $var1` will be evaluated first which returns 7.
+ 7 gets multiplied by the value of `$var2` which returns 17.5.
+ 17.5 gets divided by `2` which returns 8.75.
+ 8.75 gets subtracted by `3` which would then return 5.75.

## Incrementing/Decrementing a value

If you combine addition, subtraction, multiplication or division with the [value assignment operator]({{ site.url }}/php-variables-comments/#value-assignment){:target="blank"}, you can either increment or decrement a number, for example:

```php
$var1 = 1;
$var2 = 10;
$var3 = 2;
$var4 = 20;

echo $var1 += 2; // Outputs: 3
echo $var2 -= 5; // Outputs: 5
echo $var3 *= 2; // Outputs: 4
echo $var4 /= 2; // Outputs: 10
```

The above code can also be written in a much longer format like so:

```php
$var1 = 1;
$var2 = 10;
$var3 = 2;
$var4 = 20;

echo $var1 = $var1 + 2; // Outputs: 3
echo $var2 = $var2 - 5; // Outputs: 5
echo $var3 = $var3 * 2; // Outputs: 4
echo $var4 = $var4 / 2; // Outputs: 10
```

If you only need to increment or decrement a number by 1, use `++` or `--` instead, for example:

```php
$var = 1;

$var++;
echo $var; // Outputs: 2

$var--;
echo $var; // Outputs: 1
```

**Previous Post:** [PHP String Functions]({{ site.url }}/php-string-functions/)

**Next Post:** [PHP Number Functions]({{ site.url }}/php-number-functions/)

_This is part 6 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
