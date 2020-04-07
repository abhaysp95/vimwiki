# Cascading Style Sheets
-------------------------

I'm jotting down some points, according to the need

## Element selector

### tag selector
Selects according to the given tag, like _<p> or <b>_

### id selector
Selects with id of tag. Id shouldn't start with a `number.`

### class selector
Selects according to the given class, either give tag then class or only classname to select without miniding tags. Like, p.cl1 {} or .cl1{}

### universal selector
This above rule will affect every HTML element on the page: `*{}`

### grouping selector
The grouping selector selects all the HTML elements with the same style definitions.

## The Position Property

The `positon` property specifies the type of positioning method used for an element.

There are five different position values:
* static
* relative
* fixed
* absolute
* sticky

Elements are then positioned using the top, bottom, left and right properties. However, these properties will not work unless the `position` property is set first. They also word differently depending on the position value.

### position: static;
An element with `position: static;` is not positioned in any special way; it is always positioned according to the normal flow of the page:

### position: relative;

An element with `postion: relative;` is positioned relative to its normal position.

Setting the top, right, left, and bottom properties of a relatively-positioned element will cause it to be adjusted away from its normal position. Other content will not be adjusted to fit into any gap left by the element.

### position: fixed;

An element with `postion: fixed;` is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to postion the element.

### position: absolute;

An element with `postion: absolute;` is positioned relative to the nearest positioned ancestor(instead of positioned relative to the viewport, like fixed).

However, if an absolute positioned element has no positioned ancestor, it uses the document body, and moves along the page scrolling.

> **NOTE:** A"postioned" element is one whose position is anything except `static`.

### position: sticky;

An element with `position: sticky;` is positioned based on the user's scroll position.

A sticky element toggles between `relative` and `fixed`, depending on the scroll position. It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place(like position:fixed).
