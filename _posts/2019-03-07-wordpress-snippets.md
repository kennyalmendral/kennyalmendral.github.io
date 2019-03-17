---
layout: post
title: WordPress Snippets
---

An ongoing collection of useful WordPress snippets.

### Get the Current Page Slug
```php
global $wp;
$current_page_slug = add_query_arg(array(), $wp->request);
```

### Retrieve the Currently Queried Object
```php
$current_obj = get_queried_object();
```

### Get an HTML Image Element Representing an Image Attachment
[https://developer.wordpress.org/reference/functions/wp_get_attachment_image](https://developer.wordpress.org/reference/functions/wp_get_attachment_image/){:target="_blank"}
```php
wp_get_attachment_image(get_the_ID(), 'thumbnail', false, array('class' => 'img-responsive'));
```

#### Contributor
+ [Danna Garcia](https://github.com/dannamariegarcia){:target="_blank"}

---
