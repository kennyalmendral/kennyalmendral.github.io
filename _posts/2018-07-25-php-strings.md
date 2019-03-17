---
layout: post
title: PHP Strings
---

A string is a set of characters (letters, numbers and symbols) inside single quotes, e.g. `'This is a string'` or double quotes, e.g. `"This is a string"`.

**Example code:**

```php
$greeting = 'Hello';
$name = 'John';

echo $greeting . ' ' . $name . '!'; // Outputs: Hello John!
echo "$greeting $name!"; // Outputs: Hello John!
echo "{$greeting} $name!"; // Outputs: Hello John!
```

## String Concatenation

The `echo $greeting . ' ' . $name . '!';` uses "concatenation" which combines/concatenate string values using the dot operator.

## String Interpolation

The `echo "$greeting $name!";` uses "interpolation" which expands a variable's value when wrapped inside double quotes.

The `echo "{$greeting} $name!";` uses another form of interpolation that expands a variable's value inside curly braces that are inside double quotes. This can be useful when prefixing or suffixing a string, for example:

```php
$table_prefix = 'site_';
echo "{$table_prefix}users"; // Outputs: site_users
```

## Escaping Characters

If a string contains quotation marks, enclose it in single quotes or if you want to use double quotes instead, prepend the quotation marks with a backslash, also known as the "escape character", for example:

```php
echo '"Hello World!"'; // Outputs: "Hello World!"
echo "\"Hello World!\""; // Outputs: "Hello World!"
```

If a string contains apostrophes, enclose it in double quotes or if you want to use single quotes, prepend the apostrophes with a backslash,  for example:

```php
echo "Child's Play"; // Outputs: Child's Play
echo 'Child\'s Play'; // Outputs: Child's Play
```

## Appending Values

You can append values to an existing variable using the dot equals operator like so:

```php
$var = 'Hello';
$var .= ' World';
```

Or its longer format...

```php
$var = 'Hello';
$var = $var . ' World';
```

**Previous Post:** [PHP Variables and Comments]({{ site.url }}/php-variables-comments/)

**Next Post:** [PHP String Functions]({{ site.url }}/php-string-functions/)

_This is part 4 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
