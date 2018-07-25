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
```

The `echo $greeting . ' ' . $name . '!';` uses "concatenation" which combines/concatenates values using the dot operator.

The `echo "$greeting $name!";` uses "interpolation" which expands variable value when wrapped inside double quotes.

The `echo "{$greeting} $name!";` uses "in-place substitution" which expands variable value inside curly braces that are inside double quotes. This can be useful when prefixing or suffixing a string, for example:

```php
$table_prefix = 'site_';
echo "{$table_prefix}users"; // Outputs: site_users
```

When a string needs to contain characters like quotation marks, enclose it in single quotes, e.g. `'"Hello John!"'` or if you want to use double quotes, prepend the quotation marks with a backslash, e.g. `"\"Hello John!\""`.

You can append values to an existing variable using the dot equals operator, for example:

```php
$var = 'Hello';
$var .= ' World';
```

Or its long format...

```php
$var = 'Hello';
$var = $var . ' World';
```

**Previous Post:** [PHP Variables](https://kennyalmendral.github.io/php-variables/)

**Next Post:** [PHP String Functions](https://kennyalmendral.github.io/php-string-functions/)

_This is part 4 of the [PHP Basics](https://kennyalmendral.github.io/php-basics/){:target="_blank"} series._

---
