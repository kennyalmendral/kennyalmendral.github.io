---
layout: post
title: WordPress Snippets
---

An ongoing collection of useful WordPress snippets.

### Get Current Page Slug
```php
global $wp;
$current_page_slug = add_query_arg(array(), $wp->request);
```

# Test
Description Here
```php
$ob = get_queried_object();
```

## Contributor
+ [Danna Garcia](https://github.com/dannamariegarcia){:target="_blank"}

---
