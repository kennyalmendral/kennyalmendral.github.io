---
layout: post
title: PHP Constants and NULL
---

The last two data types in PHP are called "constants" and "null".

## Constants

Think of a constant as the opposite of a [variable]({{ site.url }}/php-variables-comments/#variables){:target="_blank"} because the initial value assigned to it upon declaration cannot be redefined or changed down the line.

Constants should be written in capital letters with no dollar sign and the only way to assign a value to a constant is by using a built-in PHP function called `define`. This function accepts two parameters, the first parameter is the name of the constant enclosed in quotation marks and the second parameter is the value of that constant, for example:

```php
define('PROJECT_NAME', 'Sample Project');
echo PROJECT_NAME; // Outputs: Sample Project
```

When we try to change the initial value of that constant, we'll get an error message like so:

```php
PROJECT_NAME = 'Demo Project'; // Outputs: PHP Parse error:  syntax error, unexpected '='...
```

Also, when we try to redefine the value of that constant, we'll get a notice like so:

```php
define('PROJECT_NAME', 'DEMO PROJECT'); // Outputs: PHP Notice:  Constant PROJECT_NAME already defined in...
```

With that said, constants are commonly used for data that is fixed like the root directory of a project or the project name itself.

## NULL

It's possible that a variable might not have a value at all and that's where null can be used. A null is just another term for nothing, it's not zero, an empty string or even a boolean.

**Previous Post:** [PHP Booleans]({{ site.url }}/php-booleans/)

**Next Post:** [PHP Type Juggling and Type Casting]({{ site.url }}/php-type-juggling-type-casting/)

_This is part 12 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
