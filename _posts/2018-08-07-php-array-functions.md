---
layout: post
title: PHP Array Functions
---

Just like [strings]({{ site.url }}/php-string-functions/){:target="_blank"} and [numbers]({{ site.url }}/php-number-functions/){:target="_blank"}, PHP also has a wide variety of built-in functions that can be used when working with arrays.

Here's a list of the commonly used array functions:

## count

Takes an array as an argument and then counts all items in it, like so:

```php
$people = array('John', 'Jane');
echo count($people); // Outputs: 2
```

## max

Takes an array as an argument and finds the highest value in it, like so:

```php
$numbers = array(2, 100, 80, 50, 75);
echo max($numbers); // Outputs: 100
```

## min

Takes an array as an argument and finds the lowest value in it, like so:

```php
$numbers = array(2, 100, 80, 50, 75);
echo min($numbers); // Outputs: 2
```

## sort

Takes an array as an argument and sorts each item in that array. If the item is a string, it will be sorted alphabetically and if the item is a number, it will be sorted numerically, for example:

```php
// Sorting an array of numbers
$numbers = array(2, 10, 5, 1, 88, 48);
print_r($numbers); // Outputs: Array ( [0] => 2 [1] => 10 [2] => 5 [3] => 1 [4] => 88 [5] => 48 )

sort($numbers);
print_r($numbers); // Outputs: Array ( [0] => 1 [1] => 2 [2] => 5 [3] => 10 [4] => 48 [5] => 88 )

// Sorting an array of strings
$letters = array('c', 'a', 'b', 'z', 's');
print_r($letters); // Outputs: Array ( [0] => c [1] => a [2] => b [3] => z [4] => s )

sort($letters);
print_r($letters); // Outputs: Array ( [0] => a [1] => b [2] => c [3] => s [4] => z )
```

## rsort

Takes an array as an argument and sorts each item in that array in reverse order. If the item is a string, it will be sorted alphabetically and if the item is a number, it will be sorted numerically, for example:

```php
// Reverse sorting an array of numbers
$numbers = array(2, 10, 5, 1, 88, 48);
print_r($numbers); // Outputs: Array ( [0] => 2 [1] => 10 [2] => 5 [3] => 1 [4] => 88 [5] => 48 )

rsort($numbers);
print_r($numbers); // Outputs: Array ( [0] => 88 [1] => 48 [2] => 10 [3] => 5 [4] => 2 [5] => 1 )

// Reverse sorting an array of strings
$letters = array('c', 'a', 'b', 'z', 's');
print_r($letters); // Outputs: Array ( [0] => c [1] => a [2] => b [3] => z [4] => s )

rsort($letters);
print_r($letters); // Outputs: Array ( [0] => z [1] => s [2] => c [3] => b [4] => a )
```

## implode

## explode

## array_sum

## array_product

## array_rand

## array_unique

## array_push

## array_pop

## array_shift

## array_unshift

## array_merge

## array_keys

## array_values

## in_array

## is_array

See [http://php.net/manual/en/ref.array.php](http://php.net/manual/en/ref.array.php){:target="_blank"} for a complete list of built-in functions that can be used on arrays in PHP.

**Previous Post:** [PHP Associative Arrays]({{ site.url }}/php-associative-arrays/)

_This is part 10 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
