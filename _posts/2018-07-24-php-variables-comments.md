---
layout: post
title: PHP Variables and Comments
---

Variables and comments are widely used in PHP as fundamental building blocks.

## Variables

A variable is symbolic representation of a value. As its name suggest, it can "vary" overtime because it can point to different values.

PHP Variables...

+ Begin with a dollar sign
+ Followed by a letter or underscore
+ Can contain letters, numbers, underscores or dashes
+ No spaces in between
+ Case-sensitive, e.g. lowercase a is different from uppercase A

### Naming Conventions

Almost all programming languages follow different naming conventions. With that said, here's a list of the most commonly used ones in PHP:

```
$var
$Var
$myVar
$MyVar
$my_var
$my-var
$var3
$_var
$__var
```

`$myVar` is in a format called [Camel Case](https://en.wikipedia.org/wiki/Camel_case){:target="_blank"}, `$MyVar` is in a format called [Pascal Case](http://wiki.c2.com/?PascalCase){:target="_blank"} and `$my_var` is in a format called [Snake Case](https://en.wikipedia.org/wiki/Snake_case){:target="_blank"}. These three are the most commonly used naming conventions in PHP.

### Value Assignment

Using the equal sign, also known as the "value assignment operator", we can assign a value to a variable, like so:

```php
$var = 'This is a value';
```

## Comments

Adding comments in your code will help you and others to understand what your code is trying to accomplish and understand the approach that you took. Comments might take additional time to write, but it saves you time later. Comments aren't displayed in the browser because it is simply ignored by the web server.

With that said, there are two ways to write comments in PHP:

+ Single line comments - `// This is a single line comment` or `# This is a single line comment`
+ Double line comments - `/* This is a comment */`

Use double line comments when your comments contain line breaks, for example:

```php
/*
This is a comment
This is another comment
*/
```

## Variables and Comments in Action

```php
$sample_var = 'Hello';
echo $sample_var; // Outputs: Hello

$sample_var = 'World';
echo $sample_var; // Outputs: World
```

In the example code above, `$sample_var` will contain `'Hello'` as its value and then it gets displayed using the `echo` PHP construct, which basically outputs one or more values.

Afterwards, `$sample_var`'s value was changed to `'World'` and then gets displayed again.

PHP has some words that are "reserved". These are words that you're not allowed to use when naming your variables. See [http://www.php.net/manual/en/reserved.php](http://www.php.net/manual/en/reserved.php){:target="_blank"} for complete reference.

**Previous Post:** [PHP Request-Response Cycle]({{ site.url }}/php-request-response-cycle/)

**Next Post:** [PHP Strings]({{ site.url }}/php-strings/)

_This is part 3 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
