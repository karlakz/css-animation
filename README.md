# css-animation

## Table of Contents
1. [What is CSS Transition](#what-is-css-transition)
2. [Best properties to animate](#best-properties-to-animate)
3. [Background Property](#background-property)
4. [CSS Positioning and pseudo-elements](#css-positioning-and-pseudo-elements)
5. [CSS Animation Keyframes](#css-animation-keyframes)

### What is CSS Transition
**CSS transition** is a timing function that allows an element to gradually change from one style to another over a period of time. The transition effect can be applied to a variety of CSS property values, creating the appearance of smooth, gradual change from one property to another. Syntax example:
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

### Best properties to animate
2 properties that animate very well in the browser:
1. Opacity;
2. Transform for positioning, scaling and rotating elements, because browsers animate them smoothly;

### Background Property
The CSS **background** property allows you to control the background of any element on a web page. It can be used to set the background color, image, or both, and it allows you to control how the background image is displayed, such as its position, repeat, size, and more. The background property can also be used to set a background animation such as a gradient or a color animation.\
The CSS **background-animation** property is used to create an animation effect for an element's background. It works similarly to an animation keyframe, where you can define multiple states for the background and set transition times between them. This allows you to create complex animations and effects using a combination of colors, gradients, and other creative techniques. Example:
```
background: linear-gradient(to bottom, rgba(0,0,0,0), rgba(0,0,0,0.8)), url(../images/puppy.jpg) no-repeat bottom;
```
Here, a **linear gradient** background color transitions from completely transparent to 80% opaque black over a vertical distance of 50%! The first color parameter, **rgba(0,0,0,0)**, denotes a black color with 0%!opacity - i.e. it is completely transparent. The second color parameter, **rgba(0,0,0,0.8)**, denotes a black color with 80% opacity - i.e. it is mostly opaque. The linear gradient is set to transition from one color to the other from top to bottom by using the "to bottom" direction parameter. Additionally, this background includes a puppy image with no repeat at the bottom.
```
  background-size: cover;
```
Here, it tells the browser to crop the image either horizontally or vertically to fill the entire shape.

### CSS Positioning and pseudo-elements
```
header::before {
    position: absolute; // This places the element at a specific position in the page
    top: 0, // This positions the element at the top of the page
    right:0, // This places the element 0px from the right
    left:0, 
    bottom:0, 
    z-index: -1
}
```
This creates a **before** pseudo-element positioned absolutely relative to its parent element (header), with all four of its sides aligned with the edges of the parent element, and given a negative z-index. This ensures that the before pseudo-element will be placed behind the content of the header. 

```
header:after {
  background: #F9FCFF;
  content: "";
  height: 40rem;
  left: -5%;
  position: absolute;
  right: -5%;
  top: 90%;
}
```
This code defines a CSS pseudo-element called "header::after," which is an element that is added to the HTML after an existing element (in this case, the "header" element). This element is a rectangular box that is 40rem high and extends 5% of its total width to the left and right of the header element, and is positioned 90% from the top of the header element. The background of this box is set to "#F9FCFF," which is a light blue color. The content property is blank.

### CSS Animation Keyframes

```
@keyframes fade-slide-down {
  0% {
    opacity: 0;
    transform: translateY(-4rem);
  }
  100% {
    opacity: 1;
    transform: none;
  }
}
```
This code creates a keyframes animation called "fade-slide-down". At 0% the animation sets the initial state of opacity to 0, and translates the element up by 4rem. At 100% the animation sets the end state of opacity to 1, and sets the transform property to 'none', effectively undoing any transforms. This creates an animation of an element fading in while sliding down.
```
@keyframes rotate-up {
  100% {
    transform: rotateZ(-4deg);
  }
}
```
It defines the keyframes of an animation called "rotate-upn" where an element (header::after) will rotate clockwise around its z-axis by a negative 4 degree angle when the animation is at its 100% completion.
```
.header-down-arrow img {
  opacity: 0;
  animation: fade-slide-up 1s ease-out 1s forwards,
              pulse 2s 3s ease-out infinite
}
```
Multiple animations are added by using commas, each will stack and should work in parallel. Be careful when more than one keyframes operate on the same property such as transform, it can cause conflicts. Here, second animation is started after 3s delay.