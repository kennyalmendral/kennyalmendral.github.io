---
layout: post
title: PHP Strings
---

A string is a set of characters (letters, numbers, symbols) inside single quotes, e.g. `'This is a string'` or double quotes, e.g. `"This is a string"`.

**Example code:**

```php
$greeting = 'Hello';
$name = 'John';

echo $greeting . ' ' . $name . '!'; // Outputs: Hello John!
echo "$greeting $name!"; // Outputs: Hello John!
echo "{$greeting} $name!"; // Outputs: Hello John!
echo '"Hello John!"'; // Outputs: "Hello John!"
echo "\"Hello John!\""; // Outputs: "Hello John!"

// Appending values to an existing variable
$var = 'Hello';
$var .= ' World';
echo $var; // Outputs: Hello World

$var = 'Hello';
$var = $var . ' World';
echo $var; // Outputs: Hello World

```

The `echo $greeting . ' ' . $name . '!';` uses "concatenation" which combines/concatenates values using the dot operator.

The `echo "$greeting $name!";` uses "interpolation" which expands variable value when wrapped inside double quotes.

The `echo "{$greeting} $name!";` uses "in-place substitution" which expands variable value inside curly braces that are inside double quotes.

When a string needs to contain symbols aside from letters like quotation marks, enclose it in single quotes, e.g. `'"Hello John!"'` or if you want to use double quotes, use the backslash escape character, e.g. `"\"Hello John!\""`.

You can append values to an existing variable using the dot equals operator, e.g. `$var .= ' World';` or its long format, e.g. `$var = $var . ' World';`.

_Previous Post:_ [PHP Variables](https://kennyalmendral.github.io/php-variables/)

_Next Post:_ [PHP String Functions](https://kennyalmendral.github.io/php-string-functions/)

---
