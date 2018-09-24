---
layout: post
title: PHP Booleans
---

PHP has another data type called "boolean". A boolean is not a string or a number and it can only be either `true` or `false`. When we say `true`, we're not referring to the string `'true'` or even the number `1`.

The `true` and `false` boolean values can also be written as `TRUE` or `FALSE`, either way it's best to choose one and stick to it.

Booleans are commonly used in PHP when performing tests, for example:

```php
echo is_int(4); // Outputs: 1
echo is_float(4); // Outputs: 

echo is_int(4.4); // Outputs: 
echo is_float(4.4); // Outputs: 1

echo is_string(2); // Outputs: 
echo is_string('2'); // Outputs: 1
```

Take note that in PHP, the output of a `true` value is the number `1` whereas the output of a `false` value is nothing (as you can see in the example code above).

There's a built-in PHP function called `is_bool` to check if something is a boolean or not like so:

```php
echo is_bool('Hello World'); // Outputs: 
echo is_bool(1); // Outputs: 
echo is_bool(true); // Outputs: 1
echo is_bool(false); // Outputs: 1
```

**Previous Post:** [PHP Array Functions]({{ site.url }}/php-array-functions/)

**Next Post:** [PHP Constants and NULL]({{ site.url }}/php-constants-null/)

_This is part 11 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
