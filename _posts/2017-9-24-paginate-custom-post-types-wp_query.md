---
layout: post
title: Paginate Custom Post Types using WP_Query
---

One of the most common tasks when working with WordPress is to be able to paginate custom post types.

Supposedly, I have a custom post type called _Product_. Using the [WP_Query](https://codex.wordpress.org/Class_Reference/WP_Query){:target="_blank"} class, here's the standard loop implementation without pagination:

```php
$the_query = new WP_Query(array(
  'post_type' => 'product',
  'post_status' => 'publish',
  'orderby' => 'date',
  'order' => 'DESC'
));

if ($the_query->have_posts()) {
  echo '<ul>';
  
  while ($the_query->have_posts()) {
    $the_query->the_post();
    
    echo '<li>' . get_the_title() . '</li>';
  }
  
  echo '</ul>';
  
  wp_reset_postdata();
}
```

...and here's the standard loop with pagination:

```php
global $wp_query;

$wp_query = new WP_Query(array(
  'post_type' => 'product',
  'post_status' => 'publish',
  'posts_per_page' => 5,
  'paged' => (get_query_var('paged')) ? get_query_var('paged') : 1,
  'orderby' => 'date',
  'order' => 'DESC'
));

if ($wp_query->have_posts()) {
  echo '<ul>';
  
  while ($wp_query->have_posts()) {
    $wp_query->the_post();
    
    echo '<li>' . get_the_title() . '</li>';
  }
  
  echo '</ul>';
  
  wp_reset_postdata();
}
```

## The Process

1. Declare the `$wp_query` global variable before the `WP_Query` instance.
2. Add the following parameters to the `WP_Query` instance:
  - `'posts_per_page' => 5, // number of posts per page to display`
  - `'paged' => (get_query_var('paged')) ? get_query_var('paged') : 1,`
3. Change all occurrences of `$the_query` to `$wp_query`.

----
