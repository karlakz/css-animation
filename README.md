# css-animation

## Table of Contents
1. [What is CSS Transition](#what-is-css-transition)

### What is CSS Transition
**CSS transition** is a timing function that allows an element to gradually change from one style to another over a period of time. The transition effect can be applied to a variety of CSS property values, creating the appearance of smooth, gradual change from one property to another. Syntax example:\ 
```
transition: property duration timing-function delay;
```
Where: 
- *property* is the CSS property you wish to animate; 
- *duration* is the duration over which the transition will run; 
- *timing-function* is the speed curve or pace of the transition; 
- *delay* is the amount of time before the transition begins 

When the specified properties of an element change, the transition will kick in, animating (or transitioning) the properties from the old value to the new value over the set duration, at the defined pace. Once completed, the transition will end, and the element will remain in its new state. Example:\
Let's say we want to change the background color of a button element when the user hovers over it. We would set the following CSS on the button:
```
button {
  background-color: blue;
  transition: background-color 0.2s ease-in-out;
}

button:hover {
  background-color: red;
}
```
Once the user hovers over the button, the background color will gradually change from blue to red over 0.2 seconds, using a easing-in-out animation.

