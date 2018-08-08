---
layout: post
title: PHP Array Functions
---

Just like [strings]({{ site.url }}/php-string-functions/){:target="_blank"} and [numbers]({{ site.url }}/php-number-functions/){:target="_blank"}, PHP also has a wide variety of built-in functions that can be used when working with arrays.

Here's a list of the commonly used array functions:

## count

Takes an array as an argument and then counts all items in it, for example:

```php
$people = array('John', 'Jane');
echo count($people); // Outputs: 2
```

## max

Takes an array as an argument and finds the highest value in it, for example:

```php
$numbers = array(2, 100, 80, 50, 75);
echo max($numbers); // Outputs: 100
```

## min

Takes an array as an argument and finds the lowest value in it, for example:

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

Converts an array into a string.

This function accepts two parameters, the first parameter is the divider or "delimiter" that will be used to separate each item in the array when converted to a string and the second parameter is the array itself, for example:

```php
$people = array('John', 'Jane');
print_r($people); // Outputs: Array ( [0] => 'John' [1] => 'Jane' )

echo implode(',', $people); // Outputs: John,Jane
echo implode(' ', $people); // Outputs: John Jane
```

As you may have noticed, the comma and the blank space are used as delimiters which are common. You can also combine both like so:

```php
echo implode(', ', $people); // Outputs: John, Jane
```

## explode

Converts a string into an array.

This function accepts two parameters, the first parameter is the delimiter and the second parameter is the array itself, for example:

```php
$people = 'John,Jane';
echo $people; // Outputs: John,Jane

print_r(explode(',', $people)); // Outputs: Array ( [0] => 'John' [1] => 'Jane' )
```

## array_merge

Takes any number of arrays as an argument and merge them together, for example:

```php
$numbers = array(1, 2, 3, 4, 5);
$letters = array('a', 'b', 'c', 'd', 'e');
$numbers_letters = array_merge($numbers, $letters);

print_r($numbers); // Outputs: Array ( [0] => 1 [1] => 2 [2] => 3 [3] => 4 [4] => 5 )
print_r($letters); // Outputs: Array ( [0] => a [1] => b [2] => c [3] => d [4] => e )
print_r($numbers_letters); // Outputs: Array ( [0] => 1 [1] => 2 [2] => 3 [3] => 4 [4] => 5 [5] => a [6] => b [7] => c [8] => d [9] => e )
```

## in_array

Checks if a value exists in an array.

This function accepts two parameters, the first parameter is the search value or keyword and the second parameter is the array itself, for example:

```php
$countries = array('Norway', 'Finland', 'Sweden');

echo in_array('Finland', $countries); // Outputs: 1
echo in_array('Philippines', $countries); // Outputs:
```

## is_array

Checks if a variable is an array, for example:

```php
$people = array('John', 'Jane');
$name = 'John Doe';

echo is_array($people); // Outputs: 1
echo is_array($name); // Outputs:
```

Once again, with regards to the value returned by the `in_array` and `is_array` functions, take note that 1 means true and that blank means false.

See [http://php.net/manual/en/ref.array.php](http://php.net/manual/en/ref.array.php){:target="_blank"} for a complete list of built-in functions that can be used on arrays in PHP.

**Previous Post:** [PHP Associative Arrays]({{ site.url }}/php-associative-arrays/)

_This is part 10 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
