---
layout: post
title: Import CSV Data Into WordPress Programmatically
---

There's a lot of ways to import CSV data into WordPress, it's either by using the WordPress Importer or by installing a [plugin](https://kennyalmendral.github.io/wordpress-plugins-nutshell/).

But what if you want to do some custom actions programmatically through code? That's where the following code snippet comes into play:

```php
function import_csv_form() {
  if (isset($_POST['submit'])) {
    $csv_file = $_FILES['csv_file'];
    $csv_to_array = array_map('str_getcsv', file($csv_file['tmp_name']));
		
    foreach ($csv_to_array as $key => $value) {
      if ($key == 0)
        continue;
        
      // custom action goes here...
    }
  } else {
    echo '<form action="" method="post" enctype="multipart/form-data">';
    echo '<input type="file" name="csv_file">';
    echo '<input type="submit" name="submit" value="submit">';
    echo '</form>';
  }
}

add_shortcode('import_csv_form', 'import_csv_form');
```

It's basically a function that checks if a form is submitted via the submit button and if not, it will just show the form.

This function can be added to the `functions.php` file of the theme that's currently active and can be attached to any page or post using `[import_csv_form]` shortcode or to a template file using `<?php echo do_shortcode('[import_csv_form]'); ?>` since it's treated as a [shortcode](https://codex.wordpress.org/Shortcode){:target="_blank"}.

Take note that it lacks validation like making sure that the form contains some data upon submission, etc. and that's up to you to implement if needed. Also, the first row in the CSV file will be skipped because it's used for column labels and with that said, if you don't have column labels, remove the following lines of code:

```php
if ($key == 0)
  continue;
```

## Sample Usage

Supposedly, I'll upload a CSV file that contains 5 users with their ID on the first column and current activation status on the second column.

| user_id | activation_status |
| :-----: | :---------------: |
| 22      | 0                 |
| 17      | 0                 |
| 72      | 0                 |
| 42      | 1                 |
| 56      | 0                 |

During the upload process, I'll execute some code to check if a user's account is already activated and if not, activate it by setting the activation status to 1. In this case, the user with the ID of 42 will be skipped since it's already activated.

But before doing so, I want to know the indeces to access by dumping the data submitted through `print_r` enclosed in `<pre>` tag to make it more readable like so:

```php
foreach ($csv_to_array as $key => $value) {
  if ($key == 0)
    continue;
    
  echo '<pre>';
  print_r($value);
  echo '</pre>';
}
```

which will output the following:

```
Array
(
  [0] => 22
  [1] => 0
)

Array
(
  [0] => 17
  [1] => 0
)

Array
(
  [0] => 72
  [1] => 0
)

Array
(
  [0] => 42
  [1] => 1
)

Array
(
  [0] => 56
  [1] => 0
)
```

From there, I can see that `$value[0]` contains the user ID and `$value[1]` contains the activation status. The code would now look something like this:

```php
foreach ($csv_to_array as $key => $value) {
  if ($key == 0)
    continue;
    
  // check if user exists
  if (get_userdata($value[0])) {
    // check if user is not yet activated
    if ( ! $value[1]) {
      update_user_meta($value[0], 'activation_status', 1);
    }
  }
}
```
That's it!

----
