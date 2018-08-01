---
layout: post
title: PHP Arrays
---

An array is an ordered, integer-indexed collection of objects. These objects can either be a string, a number or another array.

Arrays groups objects together and keeps their respective position in that group in the same order so that we can refer to them by their position, also known as "index".

Arrays are a useful mechanism for keeping information organized since we can reference different information using just a single variable.

Imagine if we have one hundred email addresses, it's not practical to create a variable for each of them, instead we assign each item to an array and then use that array to retrieve each email address by referencing their index.

## Defining an Array

An array is commonly assigned to a variable as its value using the `array()` syntax like so:

```php
$numbers = array();
```

In the example above, we have defined an empty array and assign it to the `$numbers` variable.

We can put objects in an array by separating them with commas like so:

```php
$numbers = array(8, 88, 2, 10, 100);
```

Now we have an array that consists of numbers and those numbers will always stay in the order they are placed.

## Retrieving Values

To retrieve an item in an array, reference the array itself and then add brackets to it. Inside those brackets, we're going to provide the index or position that we wanted to retrieve, for example:

```php
$numbers = array(1, 2 ,3 ,4, 5);
echo $numbers[1]; // Ouputs: 2
echo $numbers[4]; // Ouputs: 5
```

Take note that arrays are indexed starting from 0 and that's the reason why `echo $numbers[1];` returned 2 instead of 1 and `echo $numbers[4];` returned 5 instead of 4.

## Mixing Objects

An array can also contain a mixture of strings, numbers or even another array like so:

```php
$objects = array(23, 'cat', 'dog', 1, 'owl', array('x', 'yz'));
echo $objects[2]; // Outputs: dog
echo $objects[5]; // Outputs: Array
```

Notice that `echo $objects[5];` outputs the word `Array` instead of the contents of that array.

If we wanted to see the contents of that array, instead of `echo`, we can either use `print_r` or `var_dump` which are both built-in PHP functions, for example:

```php
print_r($objects[5]); // Outputs: Array ( [0] => x [1] => yz )
var_dump($objects[5]); // Outputs: array(2) { [0]=> string(1) "x" [1]=> string(2) "yz" }
```

The only difference between the two is that `var_dump` outputs more information about the array like how many items does it contain and the data type and length of each item.

Also, both functions will show the index of each item together with its value in the array all in one line. We can format it so that it would be more readable by enclosing it in `pre` HTML tags, for example:

```php
echo '<pre>';
print_r($objects[5]);
echo '</pre>';

echo '<pre>';
var_dump($objects[5]);
echo '</pre>';
```

Which will output the following:

```
Array
(
    [0] => x
    [1] => y
)

array(2) {
  [0]=>
  string(1) "x"
  [1]=>
  string(2) "yz"
}
```

To retrieve values from an array inside an array, reference the array and append another set of brackets and inside those brackets, specify an index like so:

```php
echo $objects[5][0]; // Outputs: x
```

## Modifying an Array

To modify the value of a specific item in an array, reference the array with the item's index and assign a value to it like so:

```php
$animals = array('cat', 'dog', 'pig');
print_r($animals); // Outputs: Array ( [0] => cat [1] => dog [2] => pig )

$animals[2] = 'rat';
print_r($animals); // Outputs: Array ( [0] => cat [1] => dog [2] => rat )
```

As you may have noticed, the string with the value of `'pig'` in the array which is located at index 2 was changed to `'rat'`.

In order to add an item to an existing array, we reference the existing array, append empty brackets and assign a value to it like so:

```php
$animals = array('cat', 'dog');
$animals[] = 'pig';

print_r($animals); // Outputs: Array ( [0] => cat [1] => dog [2] => pig )
```

Take note that the item added using this method will always be the last item in the array.

As of PHP 5.4, the shorthand syntax for declaring an array which is the `[]` syntax can now be used instead of the `array()` syntax.

**Previous Post:** [PHP Number Functions]({{ site.url }}/php-number-functions/)

_This is part 8 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
