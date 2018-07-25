---
layout: post
title: PHP Variables
---

A variable is symbolic representation of a value. As its name suggest, it can "vary" overtime because it can point to different values.

PHP Variables...

+ Begin with a dollar sign
+ Followed by a letter or underscore
+ Can contain letters, numbers, underscores or dashes
+ No spaces in between
+ Case-sensitive, e.g. lowercase a is different from uppercase A

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

`$myVar` is in a format called [Camel Case](https://en.wikipedia.org/wiki/Camel_case){:target="_blank"}, `$MyVar` is in a format called [Pascal Case](http://wiki.c2.com/?PascalCase){:target="_blank"} and `$my_var` is in a format called [Snake Case](https://en.wikipedia.org/wiki/Snake_case){:target="_blank"}. These are the most commonly used naming conventions.

**Example code:**

```php
$sample_var = 'Hello';
echo $sample_var; // Outputs: Hello

$sample_var = 'World';
echo $sample_var; // Outputs: World
```

In the example code above, `$sample_var` will contain the string `'Hello'` and then it gets displayed using the `echo` PHP construct. Afterwards, `$sample_var` was changed to the string `'World'` and then gets displayed again.

PHP has some words that are "reserved". These are words that you're not allowed to use when naming your variables. See [http://www.php.net/manual/en/reserved.php](http://www.php.net/manual/en/reserved.php){:target="_blank"} for reference.

**Previous Post:** [PHP Request-Response Cycle](https://kennyalmendral.github.io/php-request-response-cycle/)

**Next Post:** [PHP Strings](https://kennyalmendral.github.io/php-strings/)

_This is part 3 of the [PHP Basics](https://kennyalmendral.github.io/php-basics/){:target="_blank"} series._
    
---
