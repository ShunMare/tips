---
title: CSS and SASS Managing Style Priority 
published: true
description: description
tags: SASS, CSS
---
In CSS, style priority is determined by the rules of **specificity** and **source order**. Specificity determines which CSS rule is applied by the browsers based on matching conditions. Source order is the order in which the browsers read the CSS; later rules will override earlier ones if the specificity is the same.

## CSS Specificity

Specificity is determined by:

1. Inline styles (an element's `style` attribute) have the highest specificity.
2. ID selectors have higher specificity than class selectors, attribute selectors, and pseudo-classes.
3. Class selectors, attribute selectors, and pseudo-classes have higher specificity than type selectors and pseudo-elements.

## CSS Source Order

If two selectors have the same specificity, the one that comes last in the CSS will be applied. 

## Adjusting Specificity with Sass

You can adjust the specificity of your styles in Sass by making your selectors more specific. For instance, `body .pink` is more specific than `.pink` or `.default-gray`.

```scss
body .pink {
  background-color: pink;
}

.default {
  &-gray {
    background-color: gray;
  }
}
```
The & is a special feature of Sass that refers to the parent selector. Here, &-gray is compiled into .default-gray in CSS.

This compiles into the following CSS:
```css
body .pink {
  background-color: pink;
}

.default-gray {
  background-color: gray;
}
```
In this example, even if `.pink` and `.default-gray` are applied to the same element, the style of `.pink` has higher specificity due to its more specific selector, so its style will take precedence, making the background color `pink`.
Note: However, using more specific selectors limits the flexibility of your CSS rules, because they apply to fewer elements. Always choose the most appropriate method according to your needs.
