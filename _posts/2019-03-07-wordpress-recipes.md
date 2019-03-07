---
layout: post
title: Language Code Cheatsheet
---

## Get Current Page Slug
```php
global $wpdb;
$current_page_slug = add_query_arg(array(), $wp->request);
```
