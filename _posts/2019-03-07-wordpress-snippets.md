---
layout: post
title: WordPress Snippets
---

An ongoing collection of short but useful WordPress snippets.

### Disable the Admin Bar
```php
add_filter('show_admin_bar', '__return_false');
```

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

### Display Numbered Pagination Links
```php
global $wp_query;
$total = $wp_query->max_num_pages;

if ($total > 1)  {
  if ( ! $current_page = get_query_var('paged'))
    $current_page = 1;

  $format = empty(get_option('permalink_structure')) ? '&page=%#%' : 'page/%#%/';
  
  echo paginate_links(array(
    'base' => get_pagenum_link(1) . '%_%',
    'format' => $format,
    'current' => $current_page,
    'total' => $total,
    'mid_size' => 4,
    'type' => 'list'
  ));
}
```

### Customize Excerpt Length
```php
function custom_excerpt_length($length) {
  return 40;
}

add_filter('excerpt_length', 'custom_excerpt_length', 999);
```

### Allow Additional Formats in the Media Library
```php
function add_custom_mime_types($mimes) {
  $new_mime_types = array(
    'zip' => 'application/zip',
    'pdf' => 'application/pdf'
  );
  
  return array_merge($mimes, $new_mime_types);
}

add_filter('upload_mimes', 'add_custom_mime_types');
```


### Shortcode
Create shortcode which can use variables from the function to the template to be used
```php
function my_sample_shortcode( $atts ){
    ob_start();

    $a = shortcode_atts( array(
        'type' => 'post',
    ), $atts );

    include( locate_template( 'content-my-sample.php', false, false ) ); 

    return ob_get_clean();
}
add_shortcode( 'my_sample', 'my_sample_shortcode' );
```

### Customize WP Login Logo
```php
function custom_login_logo() {
  echo '<style>';
  echo '#login h1 a, .login h1 a {';
  echo 'background-image: url(' . get_stylesheet_directory_uri() . '/images/logo.png');';
  echo '}';
  echo '</style>';
}

add_action('login_enqueue_scripts', 'custom_login_logo');
```


#### Contributor
+ [Danna Garcia](https://github.com/dannamariegarcia){:target="_blank"}

---
