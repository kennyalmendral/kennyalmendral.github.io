---
layout: post
title: CSS Box Model
---

The CSS box model is a box that contains the margin, padding, border and the content of each HTML element.

## Element Dimensions

To clarify the relationships of margins and their elements in terms of size. There are two blocks of calculations for an element, namely:

+ _Content block:_ The element’s width, border and padding.
+ _Containing block:_ The elements margin edges.

Certain things happen when an element is considered "over-constrain". Over-constrain simply means that an element no longer fits inside its parent element's dimensions. 

When something is over-constrain, the browser had to make decisions about what to do. Often, it will ignore margins and paddings in order to make things fit.

If the containing block an of an element is wider than its parent, the excess right margin of that element will be ignored by the browser. On the other hand, if the content block of an element is wider than its parent, the overflowing would occur.

There is a CSS property to control this sort of overflowing:

+ `overflow: hidden` - This will clip the excess overflow.
+ `overflow: scroll` - This will add scrollbars even if there is no overflowing happening.
+ `overflow: auto` - This will add scrollbars only if there is overflowing happening.

**Note:** This CSS property should be applied to the element's parent.

One more thing... If the parent element has a left and right padding (which adds to its total content block width) and its child element overflows, the right padding of that parent element will be ignored. That right padding of the parent element is still there though, and other child elements (if there is) would respond to it excluding that child element that’s overflowing.

## Vertical Margin Collapse

Vertical margins collapse with the larger of the top or bottom margin values used to calculate the amount of space between elements while horizontal margins combine to create the total amount of space between elements. This prevents paragraphs, headings and other typographic elements from having “double spacing” between elements.

Without something to keep the margins from touching (such as padding or border), the collapsing will occur.

## EM Values

+ For the `font-size` CSS property, the calculation will be based from the font size of the element's parent element.
+ For other CSS box model properties like `margin` or `padding`, the calculation will be based on the element's own font size.

## Percentage Values

+ For the `font-size` CSS property like `em`, the calculation will be based from the font size of the element's parent.
+ For other CSS box model properties like `width`, `margin` or `padding`, the calculation will be based from the element's parent width.

**Note:** Percentages doesn’t apply to the `border` CSS property.

## Normal Document Flow

Normal document flow is exactly what happens to your page when you don’t apply any user defined CSS at all. It’s the rules that all browsers used to control the appearance of HTML elements on a web page by default.

----
