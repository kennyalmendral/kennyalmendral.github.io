---
layout: post
title: WordPress Plugins in a Nutshell
---

Understanding how WordPress plugins work will be beneficial if you are interested in developing your own or extending existing ones to suit your needs.

## What is a WordPress plugin?

A WordPress plugin alters or extends core functionalities that are built-in to WordPress. In other words, plugins are files that are installed, activated or sometimes created in a WordPress site to add a feature, or set of features and it can range from a simple calendar widget to a full-featured e-commerce system.

## When are WordPress plugins loaded?

WordPress plugins are loaded early when you visit a page in a WordPress site, WordPress will go through the following standard loading process:

+ First it will load the `wp-config.php` file located in the root directory.
+ Second, it will load the `functions.php` file under the `wp_includes` directory.
+ Third, it will load all the plugins that are installed and activated.
+ Fourth, it will load the [pluggable](https://codex.wordpress.org/Pluggable_Functions){:target="_blank"} functions. These functions override specific core functions in a plugin. An example would be the `wp_mail` function. You can use this function in your plugin to send email using SMTP rather than the default `mail` PHP function. All pluggable functions are defined in the `pluggable.php` core WordPress file under the `wp_includes` directory.
+ Fifth, it will load the translations that are done through [internationalization and localization](https://codex.wordpress.org/I18n_for_WordPress_Developers){:target="_blank"}.
+ Sixth, it will load the theme that is currently active.
+ Lastly, it will load the page content.

## WordPress Plugin Directories

WordPress features two plugin directories. The primary directory for plugins is located under `wp-content/plugins`. The second, lesser known plugin directory is located under `wp-content/mu-plugins`. MU which stands for "Must-Use" is not created by WordPress, it must be manually created to be used.

The plugins under the `mu-plugins` directory doesn't have an activate/deactivate feature and will always be executed globally. The only way to deactivate one is by deleting the file completely with conviction...

## WordPress Plugin Types and Statuses

WordPress features a few types and statuses for plugins:

+ **Active** – A status that indicates that a plugin is active and running in WordPress.
+ **Inactive** – A status that indicates that a plugin is installed but not active and no code from the plugin are being executed.
+ **Must Use** – These are plugins that are created manually in the `wp-content/mu-plugins` directory and are loaded site-wide automatically.
+ **Drop-ins** – These plugins replaces core WordPress functionalities, they are a specifically named PHP files located in the wp-content directory. Here's some drop-ins that are available: `db.php`, `db-error.php`, `install.php`, `maintenance.php`, `advanced-cache.php` and `object-cache.php`.

## Where to download WordPress plugins?

WordPress plugins can be downloaded (either paid or free) from a variety of sources like [CodeCanyon](https://codecanyon.net/category/wordpress){:target="_blank"} and the [Official WordPress Plugin Directory](http://wordpress.org/extend/plugins){:target="_blank"}. All the plugins available in the plugin directory are 100% GPL and free to use for personal or commercial purposes.

----
