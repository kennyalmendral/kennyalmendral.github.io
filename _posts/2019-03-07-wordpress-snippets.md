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

### Retrieve the currently-queried object
```php
$ob = get_queried_object();
```

### Get an HTML img element representing an image attachment
```php
wp_get_attachment_image( $id, 'size', 'bolean', array() );
```

#### Contributor
+ [Danna Garcia](https://github.com/dannamariegarcia){:target="_blank"}

---
