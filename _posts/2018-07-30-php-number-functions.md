---
layout: post
title: PHP Number Functions
---

Similar to [strings]({{ site.url }}/php-string-functions/){:target="blank"}, PHP also has a wide array of built-in functions that can be used when working with numbers.

Here's a list of the commonly used number functions:

## abs

Takes a number as an argument and then calculates its absolute value, for example:

```php
echo abs(0 - 10); // Outputs: 10
```

## pow

Raises a number to the power of its exponent.

This function accepts two parameters, the first parameter is the base number and the second parameter is the number that determines how many times that base number will be multiplied by itself, for example:

```php
echo pow(2, 4); // Outputs: 16
```

## sqrt

Takes a number as an argument and then calculates its square root, for example:

```php
echo sqrt(9); // Outputs: 3
```

## fmod

Calculates the remainder (modulo) of the division between two numbers.

This function accepts two parameters, the first parameter is a number which is the dividend and the second parameter is also a number which is the divisor, for example:


```php
echo fmod(10, 6); // Outputs: 4
```

## rand

Generates a random integer.

This function accepts two parameters that are optional, the first parameter is a number which is the lowest possible value and the second parameter is also number which is the highest possible value, for example:


```php
echo rand(); // Outputs: Random integer value
echo rand(10, 30); // Outputs: Random integer value between (and including) 10 and 30
```

## round

Rounds the value of a floating point number.

This function accepts two parameters, the first parameter is a number which is the value to round and the second parameter (which is optional) is the number of digits after the decimal point, for example:

```php
echo round(2.2); // Outputs: 2
echo round(4.6); // Outputs: 5
echo round(5.255499159, 4); // Outputs: 5.2555
```

## ceil

Takes a floating point number as an argument and then rounds it up.

```php
echo ceil(2.4); // Outputs: 3
```

## floor

Takes a floating point number as an argument and then rounds it down.

```php
echo floor(4.8); // Outputs: 4
```

## is_int

Takes a number as an argument and then checks if it's an integer.

```php
echo is_int(5); // Outputs: 1
echo is_int(5.8); // Outputs:
```

## is_float

Takes a number as an argument and then checks if it's a floating point number.

```php
echo is_float(5.10); // Outputs: 1
echo is_float(4); // Outputs: 
```
## is_numeric

Takes a value as an argument and then checks if it's a number.

```php
echo is_numeric(1); // Outputs: 1
echo is_numeric(1.5); // Outputs: 1
echo is_numeric('1'); // Outputs: 1
echo is_numeric('one'); // Outputs: 
```

With regards to value returned by the `is_int`, `is_float` and `is_number` functions, take note that 1 means `true` and that blank means `false`.

See [http://php.net/manual/en/ref.math.php](http://php.net/manual/en/ref.math.php){:target="_blank"} for a complete list of built-in functions that can be used on numbers in PHP.

**Previous Post:** [PHP Numbers]({{ site.url }}/php-numbers/)

**Next Post:** [PHP Arrays]({{ site.url }}/php-arrays/)

_This is part 7 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
