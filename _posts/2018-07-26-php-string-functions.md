---
layout: post
title: PHP String Functions
---

PHP has a wide array of internal (built-in) functions that can be used when working with strings. Think of a function as a tool that can take something as an input and returns an output (for now).

Here's a list of the commonly used ones:

**strtolower**

Takes a string as an input and then converts it to lowercase, for example:

```php
echo strtolower('Hello World'); // Outputs: Hello World
```

**strtoupper**

Takes a string as an input and then converts it to uppercase, for example:

```php
echo strtolower('Hello World'); // Outputs: HELLO WORLD
```

**ucfirst**

Takes a string as an input and then converts the first letter of that string to uppercase, for example: 

```php
echo ucfirst('this is a string'); // Outputs: This is a string
```

**ucwords**

Takes a string as an input and then converts the first letter of every word in that string to uppercase, for example:

```php
echo ucwords('this is a string'); // Outputs: This Is A String
```

**strlen**

Takes a string as an input and then displays the length of that string, for example:

```php
echo strlen('string'); // Outputs: 6
```

**trim**

Takes a string as an input and then removes the leading and trailing whitespace(s) from that string, for example:

```php
echo trim('  Hello World '); // Outputs: Hello World
echo 'A' . trim(' B C ') . 'D'; // Outputs: AB CD
```

**strstr**

This function finds a string within a string and takes two inputs. The first input is the string being searched while the second input is the search string or term, for example:

```php
$var = 'Hello World';
echo strstr($var, 'World'); // Outputs: World
```

**str_replace**

This function replaces a string with a string inside a string and takes three inputs. The first input is the string that will be replaced while the second input is the replacement string and the third input is source string where the replacement happens, for example:

```php
$target = 'World';
$replace = 'Bird';
$source = 'Hello World';

echo str_replace($target, $replace, $source); // Outputs: Hello Bird
```

See [http://php.net/manual/en/ref.strings.php](http://php.net/manual/en/ref.strings.php){:target="_blank"} for a complete list of built-in functions that can be used on strings in PHP. 

**Previous Post:** [PHP Strings](https://kennyalmendral.github.io/php-strings/)

_This is part 5 of the [PHP Basics](https://kennyalmendral.github.io/php-basics/){:target="_blank"} series._

---
