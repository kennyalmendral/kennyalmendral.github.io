---
layout: post
title: CSS Positioning
---

Positioning an element in CSS manipulates its location in the document.

## Static Positioning

This is the default position value of elements, "static" represents a box in a normal document flow.

## Relative Positioning

When you apply `position: relative` to an element, you'll be able to offset it from its normal position. Offset CSS properties consist of the following: `top`, `right`, `bottom` and `left`. Take note that the element is still part of the normal document flow.

## Absolute Positioning

When you apply `position: absolute` to an element, you'll be able to offset it from its normal position. Offset CSS properties consist of the following: `top`, `right`, `bottom` and `left`. Take note that the element is removed from the normal document flow.

**Note:** Relative positioning provides a positioning value for _container elements_, these are parent elements that contain child elements that are positioned absolute to its parent.

## Fixed Positioning

When you apply `position: fixed` to an element, you'll be able to offset it from its normal position. Offset CSS properties consist of the following: `top`, `right`, `bottom` and `left`. Take note that elements with fixed positioning don't care what type of positioning their parents have, they're always relative to the browser viewport (the viewport is the available viewing space in your browser).

## Stacking Order

Stacking order can be controlled using the `z-index` CSS property and has three possible values: `auto`, any positive or negative integer and `inherit`. By default, positioned elements are stacked on top of each other based on where they are encountered in the source order, with the last object on top.

Each element when give a `z-index` value, it creates a "stacking context", so the initial stacking context in a document is the initial root tag which is the `<html>` element. Once you apply a `z-index` value to an element, that element begins a new stacking context and if that element contains child elements, all of them are now considered a part of that stacking context which is different from the initial stacking context of the root `<html>` element.

Items are ordered based on "stacking context." The root element forms the initial stacking context, with other stacking contexts being created by applying a `z-index` value other than `auto`.

Within each stacking context, elements are stacked in the following order:

+ The background and borders of the parent element forming the stacking context are painted first
+ Any child stacked elements with a negative `z-index`
+ Elements in normal flow
+ Non-positioned floats
+ Any child stacked elements with a `z-index` of `0` or `auto`
+ Any child stacked elements with a positive `z-index` value, lowest to highest

----
