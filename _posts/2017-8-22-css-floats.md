---
layout: post
title: CSS Floats
---

Floating an element in CSS either to the left or to the right removes it from the normal document flow of its parent element, allowing text and inline elements to wrap around it.

## Floating Elements

The contents of an element defines its height by default.

When floating an element inside its parent element using the `float` CSS property, that element would be removed from the normal document flow causing its parent element to collapse.

Here's a sample HTML markup:

```html
<div id="parent">
  <div id="one">One</div>
  <div id="two">Two</div>
</div>
```

When `float: left` is applied to the `div` element with an id of `one`, that element would be removed from the normal document flow and will be floated to the left corner of its parent element and the `div` with the id of `two` would then take the place of the `div` with the id of `one` to re-establish normal document flow.

If `float: left` is applied to both `div` element, both of them will be removed from the normal document flow and their parent `div` element with an id of `parent` collapses. Try inspecting that parent `div` element and you'll see that its `height` property is `0`.

## Clearing Floats

To turn floats off and restore normal document flow, use the `clear` CSS property. For example:

```html
<img id="img" src="http://via.placeholder.com/600x500">
<p id="p1">Paragraph 1</p>
<p id="p2">Paragraph 2</p>
```

If I apply `clear: left`, `clear: right` or `clear: both` to the `p` element with an id of `p1`, it will break into its own line.

**Note:** `clear` on an element only clears the floats before it in the normal document flow order, it doesn't clear floats after it. The left and right values mean clearance of left floats and right floats preceding an element respectively. They don't mean clearing floats before and after the element.

## Containing Floats

To stop the parent element from collapsing when all of its child elements are floated, either:

+ Apply `overflow: hidden` to the parent element.
+ Apply `float: left` or `float: right` to the parent element itself.
+ Add any HTML element as the last child of a parent element and apply `clear: both` to it like so:

```html
<body>
  <div id="parent">
    <div id="one">One</div>
    <div id="two">Two</div>
    <div style="clear: both;"></div>
  </div>
</body>
```

The first one will work most of the time, but take note that some CSS3 properties like `box-shadow` will be clipped. The second one works also, but you need to consider that there will be a chain reaction, e.g. the `body` element collapses and needs to be contained as well while the last will always work, though you need to add an additional HTML markup every time.

## Clearfix Technique

The clearfix hack is a popular way to contain floats without resorting to using additional HTML markup:

```css
.clearfix:before, 
.clearfix:after {
  content: '';
  display: table;
}

.clearfix:after {
  clear: both;
}
```

This hack generates pseudo-elements and sets their `display` property to `table` which creates an anonymous `table-cell`. The `:before` pseudo-element prevents top-margin collapse while the `:after` pseudo-element is used to clear the floats.

Add the `clearfix` class to a parent element if any of its child elements needs to be floated.

----
