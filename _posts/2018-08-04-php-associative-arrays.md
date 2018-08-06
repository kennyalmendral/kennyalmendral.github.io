---
layout: post
title: PHP Associative Arrays
---

PHP has another type of array called "associative array". An associative array behaves like a [regular array]({{ site.url }}/php-arrays/){:target="_blank"}, the only difference is that it is object-indexed rather than integer-indexed. In other words, associative arrays are indexed using labels, commonly known as "keys" rather than integers.

## Key-Value Pairs

Each item in an associative array is a combination of a key and a value, thus a series of key-value pairs makes up an associative array.

The `=>` operator is used to assign a value to a key like so:

```php
$person = array(
    'first_name' => 'John',
    'last_name' => 'Doe'
);
```

The `first_name` and `last_name` are the keys while `John` and `Doe` are their values.  

## Retrieving Values

To retrieve an item in an associative array, we reference that associative array and then append brackets to it.

Inside those brackets, we're going to provide the key that we wanted to retrieve, for example:

```php
$country = array(
    'name' => 'Philippines',
    'abbreviation' => 'PH'
);

echo $country['abbreviation']; // Outputs: PH
```

## Modifying Values

To modify the value of a specific item in an associative array, we reference that associative array with the item's key and assign a new value to it like so:

```php
$person = array(
    'first_name' => 'John',
    'last_name' => 'Doe'
);

echo $person['first_name']; // Outputs: John

$person['first_name'] = 'Jane';
echo $person['first_name']; // Outputs: Jane
```

## Adding Items

In order to add an item to an existing associative array, we reference that existing associative array, append empty brackets and inside those brackets, we assign a key and then assign a value like so:

```php
$person = array(
    'first_name' => 'John',
    'last_name' => 'Doe'
);

print_r($person); // Outputs: Array ( [first_name] => John [last_name] => Doe )

$person['age'] = 25;

print_r($person); // Outputs: Array ( [first_name] => John [last_name] => Doe [age] => 25 )
```

As you may have noticed, a new key-value pair which is `[age] => 25` has been added to the `$person` associative array.

**Previous Post:** [PHP Arrays]({{ site.url }}/php-arrays/)

_This is part 9 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
