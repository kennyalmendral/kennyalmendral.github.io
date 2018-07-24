---
layout: post
title: PHP Strings
---

A text or a set of characters (letters, numbers, symbols) that's defined inside quotation marks either single quotes, e.g. 'This is a string' or double quotes, e.g. "This is a string".

**Example Code:**

```php
$greeting = 'Hello';
$name = 'John';

echo $greeting . ' ' . $name . '!'; // Outputs: Hello John!
echo "$greeting $name!"; // Outputs: Hello John!
echo "{$greeting} $name!"; // Outputs: Hello John!
```

In the example code above, there are different ways to display two or more variables, `echo $greeting . ' ' . $name . '!';` uses "concatenation" which combines/concatenates values using the _dot_ operator while `echo "$greeting $name!";` uses "interpolation" which expands variable value when wrapped inside double quotes and the `echo "{$greeting} $name!";` uses "in-place substitution" which expands variable value inside curly braces that are inside double quotes.

---
