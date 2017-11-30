---
layout: post
title: Action Hooks in WordPress
---

Action hooks are used to execute a function when an event is triggered at a specific point in the WordPress loading process like for example, when a page or post is loaded, an Ajax request is performed or when a user has logged in successfully.

## do_action

This is the function that's used when hooking into WordPress. It is where you can execute functions that are attached to an action hook. The first parameter passed to this function is the name of the action hook.

An example would be the `wp_head` which is a commonly used action hook that is fired between the `<head>...</head>` section of the site in order to add embedded styles, scripts and meta information.

```php
<?php do_action('wp_head'); ?>
```

## What is an action?

An action in WordPress is basically just a PHP function that is registered for an action hook.

_To be continued..._

---
