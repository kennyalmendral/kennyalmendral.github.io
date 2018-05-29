---
layout: post
title: Action Hooks in WordPress
---

Action hooks are used to execute a function when an event is triggered at a specific point during the WordPress loading process like for example, when a page or post is loaded, an Ajax request is performed or when a user has logged in successfully.

## do_action

This is the function that's used when hooking into WordPress. It is where you can execute functions that are attached to an action hook. The first parameter passed to this function is the name of the action hook.

An example would be the `wp_head` which is a commonly used action hook that is fired between the `<head>...</head>` section of the site in order to add embedded styles, scripts and meta information.

```php
<?php do_action('wp_head'); ?>
```

An "action" in WordPress is basically just a PHP function that is registered to an action hook.

## add_action

This is the function that is used to add an action to an action hook that accepts 4 parameters:

+ `$tag` - The action hook that the `$function_to_add` will be attached to.
+ `$function_to_add` - The action that will be attached to the `$tag`.
+ `$priority` - This determines when will the `$function_to_add` be executed. The lower the number, the earlier it will run. _This is optional and defaults to 10 if not specified._
+ `$accepted_args` - The number of parameters the `$tag` passes to the `$function_to_add`. _This is optional and defaults to 1 if not specified._

```php
add_action($tag, $function_to_add, $priority = 10, $accepted_args = 1);
```

An action hook can take many actions and aren't limited to a single action.

One commonly used action hook is the `wp_footer` which is fired just before the closing `</body>` tag.

Let's add an action to the `wp_footer` hook that displays the copyright notice:

```php
add_action('wp_footer', 'display_copyright_notice');

function display_copyright_notice() {
  echo "Copyright &copy; " . date('Y') . ' ' . get_bloginfo('name') . ". All rights reserved.";
}
```

If we specify the `$priority` and set it to 20 like so:

```php
add_action('wp_footer', 'display_copyright_notice', 20);
```

The `display_copyright_notice` action will execute later than the other actions that are hooked to `wp_footer`. If it's changed to 3, it will be executed earlier.

Here's a complete list of default WordPress action hooks: [https://codex.wordpress.org/Plugin_API/Action_Reference](https://codex.wordpress.org/Plugin_API/Action_Reference){:target="_blank"}

---
