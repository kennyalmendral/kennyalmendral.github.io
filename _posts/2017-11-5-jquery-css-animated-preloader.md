---
layout: post
title: Implement an Animated Preloader using CSS and jQuery
---

The blank white screen works fine when waiting for a page to load in the browser, but would it be better to at least add some kind of indicator like an animated preloader to tell the visitor that something is happening?

Research has also shown that the feeling of waiting can be reduced by keeping a user's attention occupied. With that said, let's get started on implementing it using CSS and jQuery.

But before that, you should first choose an animated graphic to display. You can find a variety of animated graphics at [loading.io](https://loading.io/spinner/){:target="_blank"}. In this example, I'll be using [this one](https://loading.io/spinner/hourglass/-sandglass-time-loading-gif){:target="_blank"} in [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG){:target="_blank"} format.

## HTML Markup

Add the following HTML markup just after the opening `<body>` tag:

```html
<div id="preloader"></div>
```

Next is...

## CSS Styling

Add the following CSS code:

```css
#preloader {
  position: fixed; 
  left: 0; 
  top: 0; 
  z-index: 999; 
  width: 100%; 
  height: 100%; 
  overflow: visible; 
  background: #fff url("images/preloader.svg") no-repeat center center; 
}
```

which basically positions the animated graphic to the center of the screen.

Lastly...

## jQuery Implementation

Add the following jQuery code:

```javascript
$(window).on('load', function() {
  $('#preloader').delay(100).fadeOut('slow', function() {
    $(this).remove();
  });
});
```

which waits for the [window object](https://developer.mozilla.org/en-US/docs/Web/API/Window){:target="_blank"} to be loaded before removing the preloader from the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model){:target="_blank"} in a smooth manner.

----
