---
layout: post
title: PHP String Functions
---

PHP has a wide array of built-in functions that can be used when working with strings. Think of these functions as a tool that takes one or more parameters and then returns a result.

## Functions 101

A function can also be referred to as a "method" and vice versa. They are often used interchangeably. A "parameter" is a variable that is part of the function's declaration while an "argument" is a value or a variable passed to that parameter when the function is called.

Consider the following code:

```php
function displayName($first_name, $last_name) {
  return $first_name . ' ' . $last_name;
}

echo displayName('John', 'Doe');
```

The `$first_name` and the `$last_name` variables inside the function's parentheses are the parameters while the `'John'` and `'Doe'` are the arguments.

With that said, here's a list of the commonly used string functions:

## strtolower

Takes a string as an argument and then converts it to lowercase, for example:

```php
echo strtolower('Hello World'); // Outputs: Hello World
```

## strtoupper

Takes a string as an argument and then converts it to uppercase, for example:

```php
echo strtoupper('Hello World'); // Outputs: HELLO WORLD
```

## ucfirst

Takes a string as an argument and then converts the first letter of that string to uppercase, for example: 

```php
echo ucfirst('this is a string'); // Outputs: This is a string
```

## ucwords

Takes a string as an argument and then converts the first letter of every word in that string to uppercase, for example:

```php
echo ucwords('this is a string'); // Outputs: This Is A String
```

## strlen

Takes a string as an argument and then calculates its length, for example:

```php
echo strlen('string'); // Outputs: 6
```

## trim

Takes a string as an argument and then removes the leading and trailing whitespace(s) from that string, for example:

```php
echo trim('  Hello World '); // Outputs: Hello World
echo 'A' . trim(' B C ') . 'D'; // Outputs: AB CD
```

## strstr

Searches a string within a string and if found, it returns that particular string together with every word that follows it.

This function accepts two parameters, the first parameter is the source string and the second parameter is the search string, for example:

```php
$var = 'This is a string';
echo strstr($var, 'a'); // Outputs: a string
```

## str_replace

Replaces a string with a string inside a string. 

This function accepts three parameters, the first parameter is the "needle" (the string that will be replaced), the second parameter is the replacement string and the third parameter is the source string or "haystack" where the replacement happens, for example:

```php
$target = 'World';
$replace = 'Bird';
$source = 'Hello World';

echo str_replace($target, $replace, $source); // Outputs: Hello Bird
```

## str_repeat

Repeats a string.

This function accepts two parameters, the first parameter is the string to repeat and the second parameter will be a number that will be used to determine how many times that string will be repeated, for example:

```php
echo str_repeat('Knock! ', 2); // Outputs: Knock! Knock!
```

## substr

Takes a portion of a string.

This function accepts three parameters, the first parameter is the source string, the second parameter is a number which is considered as the starting index (the indexing starts at zero by the way) and the third parameter is also a number that will be used to determine how many steps to take starting from that starting index, for example:

```php
echo substr('This is a string', 10, 6); // Outputs: string
```

## strpos

Shows the index or position of a string inside a string (the indexing starts at zero).

This function accepts two parameters, the first parameter is the source string and the second parameter is the search string, for example:

```php
echo strpos('This is a string', 'string'); // Outputs: 10
```

## strchr

Similar to `strstr` but it searches a character instead of a string within a string and if found, it returns that particular character together with everything that follows it.

This function accepts two parameters, the first parameter is the source string and the second parameter is the search character, for example:

```php
echo strchr('This is a string', 'a'); // Outputs: a string
```

See [http://php.net/manual/en/ref.strings.php](http://php.net/manual/en/ref.strings.php){:target="_blank"} for a complete list of built-in functions that can be used on strings in PHP.

**Previous Post:** [PHP Strings]({{ site.url }}/php-strings/)

**Next Post:** [PHP Numbers]({{ site.url }}/php-numbers/)

_This is part 5 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
