# CSS Advanced notes

> Here are reprezented my own notes about Advanced CSS

## CSS border-radius Property

The CSS border-radius property defines the radius of an element's corners.  
Here are three examples:

1. Rounded corners for an element with a specified background color;
2. Rounded corners for an element with a border;
3. Rounded corners for an element with a background image;

```css
#rcorners1 {
  border-radius: 25px;
  background: #73AD21;
  padding: 20px;
  width: 200px;
  height: 150px;
}

#rcorners2 {
  border-radius: 25px;
  border: 2px solid #73AD21;
  padding: 20px;
  width: 200px;
  height: 150px;
}

#rcorners3 {
  border-radius: 25px;
  background: url(paper.gif);
  background-position: left top;
  background-repeat: repeat;
  padding: 20px;
  width: 200px;
  height: 150px;
}
```

The border-radius property is actually a shorthand property for the border-top-left-radius, border-top-right-radius, border-bottom-right-radius and border-bottom-left-radius properties.  
The border-radius property can have from one to four values. Here are the rules:  

* Four values - border-radius: 15px 50px 30px 5px; (first value applies to top-left corner, second value applies to top-right corner, third value applies to bottom-right corner, and fourth value applies to bottom-left corner);
* Three values - border-radius: 15px 50px 30px; (first value applies to top-left corner, second value applies to top-right and bottom-left corners, and third value applies to bottom-right corner);
* Two values - border-radius: 15px 50px; (first value applies to top-left and bottom-right corners, and the second value applies to top-right and bottom-left corners);
* One value - border-radius: 15px; (the value applies to all four corners, which are rounded equally;

You could also create elliptical corners:

```css
#rcorners1 {
  border-radius: 50px / 15px;
  background: #73AD21;
  padding: 20px;
  width: 200px;
  height: 150px;
}

#rcorners2 {
  border-radius: 15px / 50px;
  background: #73AD21;
  padding: 20px;
  width: 200px;
  height: 150px;
}

#rcorners3 {
  border-radius: 50%;
  background: #73AD21;
  padding: 20px;
  width: 200px;
  height: 150px;
}
```

## CSS border-image Property

The CSS border-image property allows you to specify an image to be used instead of the normal border around an element.  
The property has three parts:

* The image to use as the border
* Where to slice the image
* Define whether the middle sections should be repeated or stretched

**CSS Border Image Properties**:  

| Property | Description |
| border-image | A shorthand property for setting all the border-image-* properties |
| border-image-source | Specifies the path to the image to be used as a border |
| border-image-slice | Specifies how to slice the border image |
| border-image-width | Specifies the widths of the border image |
| border-image-outset | Specifies the amount by which the border image area extends beyond the border box |
| border-image-repeat | Specifies whether the border image should be repeated, rounded or stretched |

**border-image property**:  
The border-image property takes the image and slices it into nine sections, like a tic-tac-toe board.  
It then places the corners at the corners, and the middle sections are repeated or stretched as you specify.  
Note: For border-image to work, the element also needs the border property set!  

Here, the middle sections of the image are repeated to create the border:

```css
#borderimg {
  border: 10px solid transparent;
  padding: 15px;
  border-image: url(border.png) 30 round;
}
```

Here, the middle sections of the image are stretched to create the border:

```css
#borderimg {
  border: 10px solid transparent;
  padding: 15px;
  border-image: url(border.png) 30 stretch;
}
```

Tip: The border-image property is actually a shorthand property for the border-image-source, border-image-slice, border-image-width, border-image-outset and border-image-repeat properties.

## CSS Multiple Backgrounds

CSS allows you to add multiple background images for an element, through the background-image property.  
The different background images are separated by commas, and the images are stacked on top of each other, where the first image is closest to the viewer.  

```css
#example1 {
  background-image: url(img_flwr.gif), url(paper.gif);
  background-position: right bottom, left top;
  background-repeat: no-repeat, repeat;
}
```

Multiple background images can be specified using either the individual background properties (as above) or the background shorthand property.  
The following example uses the background shorthand property (same result as example above):

```css

#example1 {
  background: url(img_flwr.gif) right bottom no-repeat, url(paper.gif) left top repeat;
}
```

### CSS Background Size

The CSS background-size property allows you to specify the size of background images.  
The size can be specified in:  

* lengths,
* percentages,
* or by using one of the two keywords: contain or cover.

The contain keyword scales the background image to be as large as possible (but both its width and its height must fit inside the content area).  
As such, depending on the proportions of the background image and the background positioning area, there may be some areas of the background which are not covered by the background image.

The cover keyword scales the background image so that the content area is completely covered by the background image (both its width and height are equal to or exceed the content area).  
As such, some parts of the background image may not be visible in the background positioning area.

```css
#div1 {
  background: url(img_flower.jpg);
  background-size: 100px 80px;
  background-repeat: no-repeat;
}
```

```css
#div1 {
  background: url(img_flower.jpg);
  background-size: contain;
  background-repeat: no-repeat;
}

#div2 {
  background: url(img_flower.jpg);
  background-size: cover;
  background-repeat: no-repeat;
}
```

### Define Sizes of Multiple Background Images

The background-size property also accepts multiple values for background size (using a comma-separated list), when working with multiple backgrounds.

```css
#example1 {
  background: url(img_tree.gif) left top no-repeat, url(img_flwr.gif) right bottom no-repeat, url(paper.gif) left top repeat;
  background-size: 50px, 130px, auto;
}
```

### Full Size Background Image

Now we want to have a background image on a website that covers the entire browser window at all times.  
The requirements are as follows:

* Fill the entire page with the image (no white space)
* Scale image as needed
* Center image on page
* Do not cause scrollbars

The following example shows how to do it;  
Use the `<html>` element (the `<html>` element is always at least the height of the browser window).  
Then set a fixed and centered background on it.  
Then adjust its size with the background-size property:

```css
html {
  background: url(img_man.jpg) no-repeat center fixed;
  background-size: cover;
}
```

### Hero Image

You could also use different background properties on a `<div>` to create a hero image (a large image with text), and place it where you want.

```css
.hero-image {
  background: url(img_man.jpg) no-repeat center;
  background-size: cover;
  height: 500px;
  position: relative;
}
```

### CSS background-origin Property

The CSS background-origin property specifies where the background image is positioned.  
The property takes three different values:

* border-box - the background image starts from the upper left corner of the border
* padding-box - (default) the background image starts from the upper left corner of the padding edge
* content-box - the background image starts from the upper left corner of the content

```css
#example1 {
  border: 10px solid black;
  padding: 35px;
  background: url(img_flwr.gif);
  background-repeat: no-repeat;
  background-origin: content-box;
}
```

### CSS background-clip Property

The CSS background-clip property specifies the painting area of the background.  
The property takes three different values:

* border-box - (default) the background is painted to the outside edge of the border
* padding-box - the background is painted to the outside edge of the padding
* content-box - the background is painted within the content box

```css
#example1 {
  border: 10px dotted black;
  padding: 35px;
  background: yellow;
  background-clip: content-box;
}
```

## CSS Colors

**RGBA Colors**:  
RGBA color values are an extension of RGB color values with an alpha channel - which specifies the opacity for a color.

An RGBA color value is specified with: rgba(red, green, blue, alpha).  
The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (fully opaque).

**HSL Colors**:  
HSL stands for Hue, Saturation and Lightness.  

Hue is a degree on the color wheel (from 0 to 360):
0 (or 360) is red
120 is green
240 is blue
Saturation is a percentage value: 100% is the full color.
Lightness is also a percentage; 0% is dark (black) and 100% is white.

**HSLA Colors**:  
HSLA color values are an extension of HSL color values with an alpha channel - which specifies the opacity for a color.  
An HSLA color value is specified with: hsla(hue, saturation, lightness, alpha), where the alpha parameter defines the opacity. The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (fully opaque).

**Opacity**:  
The CSS opacity property sets the opacity for the whole element (both background color and text will be opaque/transparent).  
The opacity property value must be a number between 0.0 (fully transparent) and 1.0 (fully opaque).

## CSS Color Keywords

**The transparent Keyword**:  
The transparent keyword is used to make a color transparent.  
This is often used to make a transparent background color for an element.
Note: The transparent keyword is equivalent to rgba(0,0,0,0).  
RGBA color values are an extension of RGB color values with an alpha channel - which specifies the opacity for a color.  

```css
body {
  background-image: url("paper.gif");
}

div {
  background-color: transparent;
}
```

**The currentcolor Keyword**:  
The currentcolor keyword is like a variable that holds the current value of the color property of an element.  
This keyword can be useful if you want a specific color to be consistent in an element or a page.

```css
div {
  color: blue;
  border: 10px solid currentcolor;
}
```

**The inherit Keyword**:  
The inherit keyword specifies that a property should inherit its value from its parent element.  
The inherit keyword can be used for any CSS property, and on any HTML element.

```css
div {
  border: 2px solid red;
}

span {
  border: inherit;
}
```

## CSS Gradients

CSS gradients let you display smooth transitions between two or more specified colors.  
CSS defines three types of gradients:

* Linear Gradients (goes down/up/left/right/diagonally)
* Radial Gradients (defined by their center)
* Conic Gradients (rotated around a center point)

### CSS Linear Gradients

To create a linear gradient you must define at least two color stops.  
Color stops are the colors you want to render smooth transitions among.  
You can also set a starting point and a direction (or an angle) along with the gradient effect.

Syntax:  
`background-image: linear-gradient(direction, color-stop1, color-stop2, ...);`

**Direction - Top to Bottom (this is default)**:  
The following example shows a linear gradient that starts at the top.  
It starts red, transitioning to yellow:

```css
#grad {
  background-image: linear-gradient(red, yellow);
}
```

**Direction - Left to Right**:  
The following example shows a linear gradient that starts from the left.  
It starts red, transitioning to yellow:

```css
#grad {
  background-image: linear-gradient(to right, red , yellow);
}
```

**Direction - Diagonal**:  
You can make a gradient diagonally by specifying both the horizontal and vertical starting positions.  
The following example shows a linear gradient that starts at top left (and goes to bottom right).  
It starts red, transitioning to yellow:

```css
#grad {
  background-image: linear-gradient(to bottom right, red, yellow);
}
```

**Using Angles**:  
If you want more control over the direction of the gradient, you can define an angle, instead of the predefined directions (to bottom, to top, to right, to left, to bottom right, etc.).  
A value of 0deg is equivalent to "to top".  
A value of 90deg is equivalent to "to right".  
A value of 180deg is equivalent to "to bottom".

Syntax:  
`background-image: linear-gradient(angle, color-stop1, color-stop2);`

```css
#grad {
  background-image: linear-gradient(180deg, red, yellow);
}
```

**Using Multiple Color Stops**:  
The following example shows a linear gradient (from top to bottom) with multiple color stops:

```css
#grad {
  background-image: linear-gradient(red, yellow, green);
}
```

**Using Transparency**:  
CSS gradients also support transparency, which can be used to create fading effects.  
To add transparency, we use the rgba() function to define the color stops.  
The last parameter in the rgba() function can be a value from 0 to 1, and it defines the transparency of the color: 0 indicates full transparency, 1 indicates full color (no transparency).

The following example shows a linear gradient that starts from the left. It starts fully transparent, transitioning to full color red:

```css
#grad {
  background-image: linear-gradient(to right, rgba(255,0,0,0), rgba(255,0,0,1));
}
```

**Repeating a linear-gradient**:  
The repeating-linear-gradient() function is used to repeat linear gradients:

```css
#grad {
  background-image: repeating-linear-gradient(red, yellow 10%, green 20%);
}
```

### CSS Radial Gradients

A radial gradient is defined by its center.  
To create a radial gradient you must also define at least two color stops.

Syntax:  
`background-image: radial-gradient(shape size at position, start-color, ..., last-color);`
By default, shape is ellipse, size is farthest-corner, and position is center.

**Radial Gradient - Evenly Spaced Color Stops (this is default)**:  

```css
#grad {
  background-image: radial-gradient(red, yellow, green);
}
```

**Radial Gradient - Differently Spaced Color Stops**:

```css
#grad {
  background-image: radial-gradient(red 5%, yellow 15%, green 60%);
}
```

**Set Shape**:  
The shape parameter defines the shape. It can take the value circle or ellipse.  
The default value is ellipse.  
The following example shows a radial gradient with the shape of a circle:

```css
#grad {
  background-image: radial-gradient(circle, red, yellow, green);
}
```

**Use of Different Size Keywords**:  
The size parameter defines the size of the gradient.  
It can take four values:

* closest-side
* farthest-side
* closest-corner
* farthest-corner

```css
#grad1 {
  background-image: radial-gradient(closest-side at 60% 55%, red, yellow, black);
}

#grad2 {
  background-image: radial-gradient(farthest-side at 60% 55%, red, yellow, black);
}
```

**Repeating a radial-gradient**:  
The repeating-radial-gradient() function is used to repeat radial gradients:

```css
#grad {
  background-image: repeating-radial-gradient(red, yellow 10%, green 15%);
}
```

### CSS Conic Gradients

A conic gradient is a gradient with color transitions rotated around a center point.  
To create a conic gradient you must define at least two colors.

Syntax:  
`background-image: conic-gradient([from angle] [at position,] color [degree], color [degree], ...);`

By default, angle is 0deg and position is center.  
If no degree is specified, the colors will be spread equally around the center point.

**Conic Gradient: Three Colors and Degrees**:  

```css
#grad {
  background-image: conic-gradient(red 45deg, yellow 90deg, green 210deg);
}
```

**Create Pie Charts**:  
Just add border-radius: 50% to make the conic gradient look like a pie:

```css
#grad {
  background-image: conic-gradient(red, yellow, green, blue, black);
  border-radius: 50%;
}
```

Here is another pie chart with defined degrees for all the colors:

```css
#grad {
  background-image: conic-gradient(red 0deg, red 90deg, yellow 90deg, yellow 180deg, green 180deg, green 270deg, blue 270deg);
  border-radius: 50%;
}
```

**Conic Gradient With Specified From Angle**:  
The [from angle] specifies an angle that the entire conic gradient is rotated by.  
The following example shows a conic gradient with a from angle of 90deg:

```css
#grad {
  background-image: conic-gradient(from 90deg, red, yellow, green);
}
```

**Conic Gradient With Specified Center Position**:  
The [at position] specifies the center of the conic gradient.  
The following example shows a conic gradient with a center position of 60% 45%:

```css
#grad {
  background-image: conic-gradient(at 60% 45%, red, yellow, green);
}
```

**Repeating a Conic Gradient**:  
The repeating-conic-gradient() function is used to repeat conic gradients:

```css
#grad {
  background-image: repeating-conic-gradient(red 10%, yellow 20%);
  border-radius: 50%;
}
```

## CSS Shadow Effects

### CSS Text Shadow

The CSS text-shadow property applies shadow to text.  
In its simplest use, you only specify the horizontal shadow (2px) and the vertical shadow (2px) and to add bluer effect and color:

```css
h1 {
  text-shadow: 2px 2px 5px red;
}
```

**Multiple Shadows**:  
To add more than one shadow to the text, you can add a comma-separated list of shadows.
The following example shows a red and blue neon glow shadow:

```css
h1 {
  color: white;
  text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
}
```

You can also use the text-shadow property to create a plain border around some text (without shadows):

```css
h1 {
  color: coral;
  text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
}
```

### CSS box-shadow Property

The CSS box-shadow property is used to apply one or more shadows to an element.  
In its simplest use, you only specify a horizontal and a vertical shadow.  
The default color of the shadow is the current text-color.

```css
div {
  box-shadow: 10px 10px;
}
```

The color parameter defines the color of the shadow.  
The blur parameter defines the blur radius.  
The higher the number, the more blurred the shadow will be.

```css
div {
  box-shadow: 10px 10px 5px lightblue;
}
```

**Set the Spread Radius of the Shadow**:  
The spread parameter defines the spread radius.  
A positive value increases the size of the shadow, a negative value decreases the size of the shadow.

```css
div {
  box-shadow: 10px 10px 5px 12px lightblue;
}
```

**Set the inset Parameter**:  
The inset parameter changes the shadow from an outer shadow (outset) to an inner shadow.

```css
div {
  box-shadow: 10px 10px 5px lightblue inset;
}
```

**Add Multiple Shadows**:  
An element can also have multiple shadows:

```css
div {
  box-shadow: 5px 5px blue, 10px 10px red, 15px 15px green;
}
```

**Cards**:  
You can also use the box-shadow property to create paper-like cards:

```css
div.card {
  width: 250px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  text-align: center;
}
```

## CSS Text Effects

| Property | Description |
| text-justify | Specifies how justified text should be aligned and spaced |
| text-overflow | Specifies how overflowed content that is not displayed should be signaled to the user |
| word-break | Specifies line breaking rules for non-CJK scripts |
| word-wrap | Allows long words to be able to be broken and wrap onto the next line |
| writing-mode | Specifies whether lines of text are laid out horizontally or vertically |

**CSS Text Overflow**:  
The CSS text-overflow property specifies how overflowed content that is not displayed should be signaled to the user.

```css
p.test1 {
  white-space: nowrap;
  width: 200px;
  border: 1px solid #000000;
  overflow: hidden;
  text-overflow: clip;
}

p.test2 {
  white-space: nowrap;
  width: 200px;
  border: 1px solid #000000;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

The following example shows how you can display the overflowed content when hovering over the element:

```css
div.test:hover {
  overflow: visible;
}
```

**CSS Word Wrapping**:  
The CSS word-wrap property allows long words to be able to be broken and wrap onto the next line.  
If a word is too long to fit within an area, it expands outside.  
The word-wrap property allows you to force the text to wrap - even if it means splitting it in the middle of a word:

```css
p {
  word-wrap: break-word;
}
```

**CSS Word Breaking**:  
The CSS word-break property specifies line breaking rules.

```css
p.test1 {
  word-break: keep-all;
}

p.test2 {
  word-break: break-all;
}
```

**CSS Writing Mode**:  
The CSS writing-mode property specifies whether lines of text are laid out horizontally or vertically.

```css
p.test1 {
  writing-mode: horizontal-tb;
}

span.test2 {
  writing-mode: vertical-rl;
}

p.test2 {
  writing-mode: vertical-rl;
}
```

## CSS Web Fonts

Web fonts allow Web designers to use fonts that are not installed on the user's computer.  
When you have found/bought the font you wish to use, just include the font file on your web server, and it will be automatically downloaded to the user when needed.  
Your "own" fonts are defined within the CSS @font-face rule.

**CSS Font Descriptors**:  
The following table lists all the font descriptors that can be defined inside the @font-face rule:

| Descriptor | Values | Description |
| font-family | name | Required. Defines a name for the font |
| src | URL | Required. Defines the URL of the font file |
| font-stretch | normal
condensed
ultra-condensed
extra-condensed
semi-condensed
expanded
semi-expanded
extra-expanded
ultra-expanded | Optional. Defines how the font should be stretched. Default is "normal" |
| font-style | normal
italic
oblique | Optional. Defines how the font should be styled. Default is "normal" |
| font-weight | normal
bold
100
200
300
400
500
600
700
800
900 | Optional. Defines the boldness of the font. Default is "normal" |
| unicode-range | unicode-range | Optional. Defines the range of UNICODE characters the font supports. Default is "U+0-10FFFF" |

**Different Font Formats**:  

* TrueType Fonts (TTF)
TrueType is a font standard developed in the late 1980s, by Apple and Microsoft.  
TrueType is the most common font format for both the Mac OS and Microsoft Windows operating systems.

* OpenType Fonts (OTF)
OpenType is a format for scalable computer fonts.  
It was built on TrueType, and is a registered trademark of Microsoft.  
OpenType fonts are used commonly today on the major computer platforms.

* The Web Open Font Format (WOFF)
WOFF is a font format for use in web pages.  
It was developed in 2009, and is now a W3C Recommendation.  
WOFF is essentially OpenType or TrueType with compression and additional metadata.  
The goal is to support font distribution from a server to a client over a network with bandwidth constraints.

* The Web Open Font Format (WOFF 2.0)
TrueType/OpenType font that provides better compression than WOFF 1.0.

* SVG Fonts/Shapes
SVG fonts allow SVG to be used as glyphs when displaying text.  
The SVG 1.1 specification define a font module that allows the creation of fonts within an SVG document.  
You can also apply CSS to SVG documents, and the @font-face rule can be applied to text in SVG documents.

* Embedded OpenType Fonts (EOT)
EOT fonts are a compact form of OpenType fonts designed by Microsoft for use as embedded fonts on web pages.

**Using The Font You Want**:  
In the @font-face rule; first define a name for the font (e.g. myFirstFont) and then point to the font file.  
Tip: Always use lowercase letters for the font URL. Uppercase letters can give unexpected results in IE.  
To use the font for an HTML element, refer to the name of the font (myFirstFont) through the font-family property:

```css
@font-face {
  font-family: myFirstFont;
  src: url(sansation_light.woff);
}

div {
  font-family: myFirstFont;
}
```

**Using Bold Text**:  
You must add another @font-face rule containing descriptors for bold text:

```css
@font-face {
  font-family: myFirstFont;
  src: url(sansation_bold.woff);
  font-weight: bold;
}
```

## CSS 2D Transforms

CSS transforms allow you to move, rotate, scale, and skew elements.
With the CSS transform property you can use the following 2D transformation methods:
translate()
rotate()
scaleX()
scaleY()
scale()
skewX()
skewY()
skew()
matrix()

**CSS Transform Properties**:  
The following table lists all the 2D transform properties:

| Property | Description |
| transform | Applies a 2D or 3D transformation to an element |
| transform-origin | Allows you to change the position on transformed elements |

**CSS 2D Transform Methods**:  

| Function | Description |
| matrix(n,n,n,n,n,n) | Defines a 2D transformation, using a matrix of six values |
| translate(x,y) | Defines a 2D translation, moving the element along the X- and the Y-axis |
| translateX(n) | Defines a 2D translation, moving the element along the X-axis |
| translateY(n) | Defines a 2D translation, moving the element along the Y-axis |
| scale(x,y) | Defines a 2D scale transformation, changing the elements width and height |
| scaleX(n) | Defines a 2D scale transformation, changing the element's width |
| scaleY(n) | Defines a 2D scale transformation, changing the element's height |
| rotate(angle) | Defines a 2D rotation, the angle is specified in the parameter |
| skew(x-angle,y-angle) | Defines a 2D skew transformation along the X- and the Y-axis |
| skewX(angle) | Defines a 2D skew transformation along the X-axis |
| skewY(angle) | Defines a 2D skew transformation along the Y-axis |

**The translate() Method**:  
The translate() method moves an element from its current position (according to the parameters given for the X-axis and the Y-axis).
The following example moves the `<div>` element 50 pixels to the right, and 100 pixels down from its current position:

```css
div {
  transform: translate(50px, 100px);
}
```

**The rotate() Method**:  
The rotate() method rotates an element clockwise or counter-clockwise according to a given degree.
The following example rotates the `<div>` element clockwise with 20 degrees:

```css
div {
  transform: rotate(20deg);
}
```

Using negative values will rotate the element counter-clockwise.  
The following example rotates the `<div>` element counter-clockwise with 20 degrees:

```css
div {
  transform: rotate(-20deg);
}
```

**The scale() Method**:  
The scale() method increases or decreases the size of an element (according to the parameters given for the width and height).  
The following example increases the `<div>` element to be two times of its original width, and three times of its original height:  

```css
div {
  transform: scale(2, 3);
}
```

The following example decreases the `<div>` element to be half of its original width and height:  

```css
div {
  transform: scale(0.5, 0.5);
}
```

**The scaleX() Method**:  
The scaleX() method increases or decreases the width of an element.
The following example increases the `<div>` element to be two times of its original width:  

```css
div {
  transform: scaleX(2);
}
```

**The scaleY() Method**:  
The scaleY() method increases or decreases the height of an element.
The following example increases the `<div>` element to be three times of its original height:  

```css
div {
  transform: scaleY(3);
}
```

**The skewX() Method**:  
The skewX() method skews an element along the X-axis by the given angle.  
The following example skews the `<div>` element 20 degrees along the X-axis:

```css
div {
  transform: skewX(20deg);
}
```

**The skewY() Method**:  
The skewY() method skews an element along the Y-axis by the given angle.  
The following example skews the `<div>` element 20 degrees along the Y-axis:

```css
div {
  transform: skewY(20deg);
}
```

**The skew() Method**:  
The skew() method skews an element along the X and Y-axis by the given angles.  
The following example skews the `<div>` element 20 degrees along the X-axis, and 10 degrees along the Y-axis:

```css
div {
  transform: skew(20deg, 10deg);
}
```

**The matrix() Method**:  
The matrix() method combines all the 2D transform methods into one.  
The matrix() method take six parameters, containing mathematic functions, which allows you to rotate, scale, move (translate), and skew elements.  
The parameters are as follow: matrix(scaleX(),skewY(),skewX(),scaleY(),translateX(),translateY())

```css
div {
  transform: matrix(1, -0.3, 0, 1, 0, 0);
}
```

## CSS 3D Transforms

With the CSS transform property you can use the following 3D transformation methods:
rotateX()
rotateY()
rotateZ()

**CSS Transform Properties**:  
The following table lists all the 3D transform properties:

| Property | Description |
| transform | Applies a 2D or 3D transformation to an element |
| transform-origin | Allows you to change the position on transformed elements |
| transform-style | Specifies how nested elements are rendered in 3D space |
| perspective | Specifies the perspective on how 3D elements are viewed |
| perspective-origin | Specifies the bottom position of 3D elements |
| backface-visibility | Defines whether or not an element should be visible when not facing the screen |

**CSS 3D Transform Methods**:  

| Function | Description |
| matrix3d |
(n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n) | Defines a 3D transformation, using a 4x4 matrix of 16 values |
| translate3d(x,y,z) | Defines a 3D translation |
| translateX(x) | Defines a 3D translation, using only the value for the X-axis |
| translateY(y) | Defines a 3D translation, using only the value for the Y-axis |
| translateZ(z) | Defines a 3D translation, using only the value for the Z-axis |
| scale3d(x,y,z) | Defines a 3D scale transformation |
| scaleX(x) | Defines a 3D scale transformation by giving a value for the X-axis |
| scaleY(y) | Defines a 3D scale transformation by giving a value for the Y-axis |
| scaleZ(z) | Defines a 3D scale transformation by giving a value for the Z-axis |
| rotate3d(x,y,z,angle) | Defines a 3D rotation |
| rotateX(angle) | Defines a 3D rotation along the X-axis |
| rotateY(angle) | Defines a 3D rotation along the Y-axis |
| rotateZ(angle) | Defines a 3D rotation along the Z-axis |
| perspective(n) | Defines a perspective view for a 3D transformed element |

**The rotateX() Method**:  
The rotateX() method rotates an element around its X-axis at a given degree:

```css
#myDiv {
  transform: rotateX(150deg);
}
```

**The rotateY() Method**:  
The rotateY() method rotates an element around its Y-axis at a given degree:

**The rotateZ() Method**:  
The rotateZ() method rotates an element around its Z-axis at a given degree:

## CSS Transitions

CSS transitions allows you to change property values smoothly, over a given duration.  
To create a transition effect, you must specify two things:

* the CSS property you want to add an effect to
* the duration of the effect
Note: If the duration part is not specified, the transition will have no effect, because the default value is 0.  

The following example shows a 100px * 100px red `<div>` element.  
The `<div>` element has also specified a transition effect for the width property, with a duration of 2 seconds:

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
}
```

The transition effect will start when the specified CSS property (width) changes value.  
Now, let us specify a new value for the width property when a user mouses over the `<div>` element:

```css
div:hover {
  width: 300px;
}
```

**CSS Transition Properties**:  
The following table lists all the CSS transition properties:

| Property | Description |
| transition | A shorthand property for setting the four transition properties into a single property |
| transition-delay | Specifies a delay (in seconds) for the transition effect |
| transition-duration | Specifies how many seconds or milliseconds a transition effect takes to complete |
| transition-property | Specifies the name of the CSS property the transition effect is for |
| transition-timing-function | Specifies the speed curve of the transition effect |

**Change Several Property Values**:  
The following example adds a transition effect for both the width and height property, with a duration of 2 seconds for the width and 4 seconds for the height:

```css
div {
  transition: width 2s, height 4s;
}
```

**Specify the Speed Curve of the Transition**:  
The transition-timing-function property specifies the speed curve of the transition effect.  
The transition-timing-function property can have the following values:

* ease - specifies a transition effect with a slow start, then fast, then end slowly (this is default)
* linear - specifies a transition effect with the same speed from start to end
* ease-in - specifies a transition effect with a slow start
* ease-out - specifies a transition effect with a slow end
* ease-in-out - specifies a transition effect with a slow start and end
* cubic-bezier(n,n,n,n) - lets you define your own values in a cubic-bezier function

The following example shows some of the different speed curves that can be used:

```css
#div1 {transition-timing-function: linear;}
#div2 {transition-timing-function: ease;}
#div3 {transition-timing-function: ease-in;}
#div4 {transition-timing-function: ease-out;}
#div5 {transition-timing-function: ease-in-out;}
```

**Delay the Transition Effect**:  
The transition-delay property specifies a delay (in seconds) for the transition effect.  
The following example has a 1 second delay before starting:

```css
div {
  transition-delay: 1s;
}
```

**Transition + Transformation**:  
The following example adds a transition effect to the transformation:

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s, height 2s, transform 2s;
}

div:hover {
  width: 300px;
  height: 300px;
  transform: rotate(180deg);
}
```

**More Transition Examples**:  
The CSS transition properties can be specified one by one, like this:

```css
div {
  transition-property: width;
  transition-duration: 2s;
  transition-timing-function: linear;
  transition-delay: 1s;
}
```

or by using the shorthand property transition:

```css
div {
  transition: width 2s linear 1s;
}
```

## CSS Animations

CSS allows animation of HTML elements without using JavaScript or Flash!

**CSS Animation Properties**:  
The following table lists the @keyframes rule and all the CSS animation properties:

| Property | Description |
| @keyframes | Specifies the animation code |
| animation | A shorthand property for setting all the animation properties |
| animation-delay | Specifies a delay for the start of an animation |
| animation-direction | Specifies whether an animation should be played forwards, backwards or in alternate cycles |
| animation-duration | Specifies how long time an animation should take to complete one cycle |
| animation-fill-mode | Specifies a style for the element when the animation is not playing (before it starts, after it ends, or both) |
| animation-iteration-count | Specifies the number of times an animation should be played |
| animation-name | Specifies the name of the @keyframes animation |
| animation-play-state | Specifies whether the animation is running or paused |
| animation-timing-function | Specifies the speed curve of the animation |

An animation lets an element gradually change from one style to another.  
You can change as many CSS properties you want, as many times as you want.  
To use CSS animation, you must first specify some keyframes for the animation.  
Keyframes hold what styles the element will have at certain times.  

**The @keyframes Rule**:  
When you specify CSS styles inside the @keyframes rule, the animation will gradually change from the current style to the new style at certain times.  
To get an animation to work, you must bind the animation to an element.  

The following example binds the "example" animation to the `<div>` element.  
The animation will last for 4 seconds, and it will gradually change the background-color of the `<div>` element from "red" to "yellow":

```css
/* The animation code */
@keyframes example {
  from {background-color: red;}
  to {background-color: yellow;}
}

/* The element to apply the animation to */
div {
  width: 100px;
  height: 100px;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
}
```

Note: The animation-duration property defines how long an animation should take to complete.  
If the animation-duration property is not specified, no animation will occur, because the default value is 0s (0 seconds).  

In the example above we have specified when the style will change by using the keywords "from" and "to" (which represents 0% (start) and 100% (complete)).  
It is also possible to use percent. By using percent, you can add as many style changes as you like.

The following example will change the background-color of the `<div>` element when the animation is 25% complete, 50% complete, and again when the animation is 100% complete:

```css
/* The animation code */
@keyframes example {
  0%   {background-color: red;}
  25%  {background-color: yellow;}
  50%  {background-color: blue;}
  100% {background-color: green;}
}

/* The element to apply the animation to */
div {
  width: 100px;
  height: 100px;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
}
```

**Delay an Animation**:  
The animation-delay property specifies a delay for the start of an animation.  
The following example has a 2 seconds delay before starting the animation:  

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
  animation-delay: 2s;
}
```

Negative values are also allowed. If using negative values, the animation will start as if it had already been playing for N seconds.

**Set How Many Times an Animation Should Run**:  
The animation-iteration-count property specifies the number of times an animation should run.  
The following example will run the animation 3 times before it stops:  

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
  animation-iteration-count: 3;
}
```

The following example uses the value "infinite" to make the animation continue for ever:

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
  animation-iteration-count: infinite;
}
```

**Run Animation in Reverse Direction or Alternate Cycles**:  
The animation-direction property specifies whether an animation should be played forwards, backwards or in alternate cycles.  
The animation-direction property can have the following values:

* normal - The animation is played as normal (forwards). This is default
* reverse - The animation is played in reverse direction (backwards)
* alternate - The animation is played forwards first, then backwards
* alternate-reverse - The animation is played backwards first, then forwards

The following example will run the animation in reverse direction (backwards):

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
  animation-direction: reverse;
}
```

**Specify the Speed Curve of the Animation**:  
The animation-timing-function property specifies the speed curve of the animation.
The animation-timing-function property can have the following values:

* ease - Specifies an animation with a slow start, then fast, then end slowly (this is default)
* linear - Specifies an animation with the same speed from start to end
* ease-in - Specifies an animation with a slow start
* ease-out - Specifies an animation with a slow end
* ease-in-out - Specifies an animation with a slow start and end
* cubic-bezier(n,n,n,n) - Lets you define your own values in a cubic-bezier function

The following example shows some of the different speed curves that can be used:

```css
#div1 {animation-timing-function: linear;}
#div2 {animation-timing-function: ease;}
#div3 {animation-timing-function: ease-in;}
#div4 {animation-timing-function: ease-out;}
#div5 {animation-timing-function: ease-in-out;}
```

**Specify the fill-mode For an Animation**:  
CSS animations do not affect an element before the first keyframe is played or after the last keyframe is played. The animation-fill-mode property can override this behavior.  
The animation-fill-mode property specifies a style for the target element when the animation is not playing (before it starts, after it ends, or both).  

The animation-fill-mode property can have the following values:

* none - Default value. Animation will not apply any styles to the element before or after it is executing
* forwards - The element will retain the style values that is set by the last keyframe (depends on animation-direction and animation-iteration-count)
* backwards - The element will get the style values that is set by the first keyframe (depends on animation-direction), and retain this during the animation-delay period
* both - The animation will follow the rules for both forwards and backwards, extending the animation properties in both directions

The following example lets the `<div>` element retain the style values from the last keyframe when the animation ends:

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  position: relative;
  animation-name: example;
  animation-duration: 3s;
  animation-fill-mode: forwards;
}
```

**Animation Shorthand Property**:  
The example below uses six of the animation properties:

```css
div {
  animation-name: example;
  animation-duration: 5s;
  animation-timing-function: linear;
  animation-delay: 2s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

The same animation effect as above can be achieved by using the shorthand animation property:

```css
div {
  animation: example 5s linear 2s infinite alternate;
}
```

## CSS Tooltip

A tooltip is often used to specify extra information about something when the user moves the mouse pointer over an element.  

**Basic Tooltip**:  
Create a tooltip that appears when the user moves the mouse over an element:

```html
<style>
/* Tooltip container */
.tooltip {
  position: relative;
  display: inline-block;
  border-bottom: 1px dotted black; /* If you want dots under the hoverable text */
}

/* Tooltip text */
.tooltip .tooltiptext {
  visibility: hidden;
  width: 120px;
  background-color: black;
  color: #fff;
  text-align: center;
  padding: 5px 0;
  border-radius: 6px;
 
  /* Position the tooltip text - see examples below! */
  position: absolute;
  z-index: 1;
}

/* Show the tooltip text when you mouse over the tooltip container */
.tooltip:hover .tooltiptext {
  visibility: visible;
}
</style>

<div class="tooltip">Hover over me
  <span class="tooltiptext">Tooltip text</span>
</div>
```

**Positioning Tooltips**:  
In this example, the tooltip is placed to the right (left:105%) of the "hoverable" text (`<div>`).  
Also note that top:-5px is used to place it in the middle of its container element.  
We use the number 5 because the tooltip text has a top and bottom padding of 5px.  
If you increase its padding, also increase the value of the top property to ensure that it stays in the middle (if this is something you want).  
The same applies if you want the tooltip placed to the left.

```css
.tooltip .tooltiptext {
  top: -5px;
  right: 105%;
}

```

If you want the tooltip to appear on top or on the bottom, see examples below.  
Note that we use the margin-left property with a value of minus 60 pixels.  
This is to center the tooltip above/below the hoverable text.  
It is set to the half of the tooltip's width (120/2 = 60).  

```css
.tooltip .tooltiptext {
  width: 120px;
  bottom: 100%;
  left: 50%;
  margin-left: -60px; /* Use half of the width (120/2 = 60), to center the tooltip */
}
```

**Tooltip Arrows**:  
To create an arrow that should appear from a specific side of the tooltip, add "empty" content after tooltip, with the pseudo-element class ::after together with the content property.  
The arrow itself is created using borders. This will make the tooltip look like a speech bubble.

This example demonstrates how to add an arrow to the bottom of the tooltip:

```css
.tooltip .tooltiptext::after {
  content: " ";
  position: absolute;
  top: 100%; /* At the bottom of the tooltip */
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: black transparent transparent transparent;
}
```

Example Explained
Position the arrow inside the tooltip: top: 100% will place the arrow at the bottom of the tooltip. left: 50% will center the arrow.
Note: The border-width property specifies the size of the arrow. If you change this, also change the margin-left value to the same. This will keep the arrow centered.
The border-color is used to transform the content into an arrow. We set the top border to black, and the rest to transparent. If all sides were black, you would end up with a black square box.

This example demonstrates how to add an arrow to the right of the tooltip:

```css
.tooltip .tooltiptext::after {
  content: " ";
  position: absolute;
  top: 50%;
  left: 100%; /* To the right of the tooltip */
  margin-top: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: transparent transparent transparent black;
}
```

**Fade In Tooltips (Animation)**:  
If you want to fade in the tooltip text when it is about to be visible, you can use the CSS transition property together with the opacity property, and go from being completely invisible to 100% visible, in a number of specified seconds (1 second in our example):

```css
.tooltip .tooltiptext {
  opacity: 0;
  transition: opacity 1s;
}

.tooltip:hover .tooltiptext {
  opacity: 1;
}
```

## CSS Styling Images

**Rounded Images**:  
Use the border-radius property to create rounded images:  
Circled Image:

```css
img {
  border-radius: 50%;
}
```

**Thumbnail Images**:  
Use the border property to create thumbnail images.

```css
img {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 150px;
}

img:hover {
  box-shadow: 0 0 2px 1px rgba(0, 140, 186, 0.5);
}

<a href="paris.jpg">
  <img src="paris.jpg" alt="Paris">
</a>
```

**Responsive Images**:  
Responsive images will automatically adjust to fit the size of the screen.  
If you want an image to scale down if it has to, but never scale up to be larger than its original size, add the following:

```css
img {
  max-width: 100%;
  height: auto;
}
```

**Polaroid Images / Cards**:  

```css
div.polaroid {
  width: 80%;
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

img {width: 100%}

div.container {
  text-align: center;
  padding: 10px 20px;
}
```

**Image Filters**:  
The CSS filter property adds visual effects (like blur and saturation) to an element.  
Note: The filter property is not supported in Internet Explorer or Edge 12.

```css
img {
  filter: grayscale(100%);
}
```

**Image Hover Overlay**:  
Create an overlay effect on hover:

```html
  <!DOCTYPE html>
  <html>
  <head>
  <style>
  .container {
    position: relative;
    width: 50%;
  }

  .image {
    display: block;
    width: 100%;
    height: auto;
  }

  .overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #008CBA;
    overflow: hidden;
    width: 0;
    height: 100%;
    transition: .5s ease;
  }

  .container:hover .overlay {
    width: 100%;
  }

  .text {
    white-space: nowrap; 
    color: white;
    font-size: 20px;
    position: absolute;
    overflow: hidden;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    -ms-transform: translate(-50%, -50%);
  }
  </style>
  </head>
  <body>

  <h2>Slide in Overlay from the Left</h2>

  <div class="container">
    <img src="img_avatar.png" alt="Avatar" class="image">
    <div class="overlay">
      <div class="text">Hello World</div>
    </div>
  </div>

  </body>
  </html>
```

**Flip an Image**:  

```css
img:hover {
  transform: scaleX(-1);
}
```

**Responsive Image Gallery**:  
CSS can be used to create image galleries. This example use media queries to re-arrange the images on different screen sizes. Resize the browser window to see the effect:

```css
.responsive {
  padding: 0 6px;
  float: left;
  width: 24.99999%;
}

@media only screen and (max-width: 700px){
  .responsive {
    width: 49.99999%;
    margin: 6px 0;
  }
}

@media only screen and (max-width: 500px){
  .responsive {
    width: 100%;
  }
}
```

**Image Modal (Advanced)**:  
This is an example to demonstrate how CSS and JavaScript can work together.  
First, use CSS to create a modal window (dialog box), and hide it by default.  
Then, use a JavaScript to show the modal window and to display the image inside the modal, when a user clicks on the image:

**CSS Image Reflection**:  

The box-reflect property is used to create an image reflection.
The value of the box-reflect property can be: below, above, left , or right.  

```css
img {
  -webkit-box-reflect: right;
}
```

**CSS Reflection Offset**:  
To specify the gap between the image and the reflection, add the size of the gap to the box-reflect property.

```css
img {
  -webkit-box-reflect: below 20px;
}
```

**CSS Reflection With Gradient**:  
We can also create a fade-out effect on the reflection.

```css
img {
  -webkit-box-reflect: below 0px linear-gradient(to bottom, rgba(0,0,0,0.0), rgba(0,0,0,0.4));
}
```

## CSS The object-fit Property

The CSS object-fit property is used to specify how an `<img>` or `<video>` should be resized to fit its container.
This property tells the content to fill the container in a variety of ways; such as "preserve that aspect ratio" or "stretch up and take up as much space as possible".

The object-fit property can take one of the following values:

* fill - This is default. The image is resized to fill the given dimension. If necessary, the image will be stretched or squished to fit
* contain - The image keeps its aspect ratio, but is resized to fit within the given dimension
* cover - The image keeps its aspect ratio and fills the given dimension. The image will be clipped to fit
* none - The image is not resized
* scale-down - the image is scaled down to the smallest version of none or contain

```css
img {
  width: 200px;
  height: 300px;
  object-fit: cover;
}
```

```css
.fill {object-fit: fill;}
.contain {object-fit: contain;}
.cover {object-fit: cover;}
.scale-down {object-fit: scale-down;}
.none {object-fit: none;}
```

## CSS The object-position Property

The CSS object-position property is used to specify how an `<img>` or `<video>` should be positioned within its container.
Let's say that the part of the image that is shown, is not positioned as we want.  
To position the image, we will use the object-position property.

```css
img {
  width: 200px;
  height: 300px;
  object-fit: cover;
  object-position: 80% 100%;
}
```

## CSS Masking

With CSS masking you create a mask layer to place over an element to partially or fully hide portions of the element.

The CSS mask-image property specifies a mask layer image.
The mask layer image can be a PNG image, an SVG image, a CSS gradient, or an SVG `<mask>` element.

Note: Most browsers only have partial support for CSS masking. You will need to use the -webkit- prefix in addition to the standard property in most browsers.

**CSS Masking Properties**:  

| Property | Description |
| mask-image | Specifies an image to be used as a mask layer for an element |
| mask-mode | Specifies whether the mask layer image is treated as a luminance mask or as an alpha mask |
| mask-origin | Specifies the origin position (the mask position area) of a mask layer image |
| mask-position | Sets the starting position of a mask layer image (relative to the mask position area) |
| mask-repeat | Specifies how the mask layer image is repeated |
| mask-size | Specifies the size of a mask layer image |

**Use an Image as the Mask Layer**:  
To use a PNG or an SVG image as the mask layer, use a url() value to pass in the mask layer image.  
The mask image needs to have a transparent or semi-transparent area. Black indicates fully transparent.  

Here is the mask image (a PNG image) we will use:

```css
.mask1 {
  -webkit-mask-image: url(w3logo.png);
  mask-image: url(w3logo.png);
  -webkit-mask-repeat: no-repeat;
  mask-repeat: no-repeat;
}
```

The mask-image property specifies the image to be used as a mask layer for an element.  
The mask-repeat property specifies if or how a mask image will be repeated. The no-repeat value indicates that the mask image will not be repeated (the mask image will only be shown once).  

**Use Gradients as the Mask Layer**:  
CSS linear and radial gradients can also be used as mask images.

```css
.mask1 {
  -webkit-mask-image: linear-gradient(black, transparent);
  mask-image: linear-gradient(black, transparent);
}
```

Use a linear gradient along with text masking as a mask layer:

```css
.mask1 {
  max-width: 600px;
  height: 350px;
  overflow-y: scroll;
  background: url(img_5terre.jpg) no-repeat;
  -webkit-mask-image: linear-gradient(black, transparent);
  mask-image: linear-gradient (black, transparent);
}
```

**Radial Gradient Examples**:  
Here, we use a radial-gradient (shaped as a circle) as the mask layer for our image:

```css
.mask2 {
  -webkit-mask-image: radial-gradient(circle, black 50%, rgba(0, 0, 0, 0.5) 50%);
  mask-image: radial-gradient(circle, black 50%, rgba(0, 0, 0, 0.5) 50%);
}
```

**Use SVG as the Mask Layer**:  
The SVG `<mask>` element can be used inside an SVG graphic to create masking effects.  
Here, we use the SVG `<mask>` element to create different mask layers for our image:  

```html
<svg width="600" height="400">
  <mask id="svgmask1">
    <polygon fill="#ffffff" points="200 0, 400 400, 0 400"></polygon>
  </mask>
  <image xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="img_5terre.jpg" mask="url(#svgmask1)"></image>
</svg>
```

## CSS Buttons

**Hoverable Buttons**:  

```css
.button {
  transition-duration: 0.4s;
}

.button:hover {
  background-color: #4CAF50; /* Green */
  color: white;
}
```

**Shadow Buttons**:  

```css
.button1 {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
}

.button2:hover {
  box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
}
```

**Disabled Buttons**:  
Use the opacity property to add transparency to a button (creates a "disabled" look).  
Tip: You can also add the cursor property with a value of "not-allowed", which will display a "no parking sign" when you mouse over the button:

```css
.disabled {
  opacity: 0.6;
  cursor: not-allowed;
}
```

**Button Groups**:  
Remove margins and add float:left to each button to create a button group:

```css
.button {
  float: left;
}
```

**Vertical Button Group**:  
Use display:block instead of float:left to group the buttons below each other, instead of side by side:

```css
.button {
  display: block;
}
```

**Button on Image**;  
**Animated Buttons**:  

```css
.button {
  display: inline-block;
  border-radius: 4px;
  background-color: #f4511e;
  border: none;
  color: #FFFFFF;
  text-align: center;
  font-size: 28px;
  padding: 20px;
  width: 200px;
  transition: all 0.5s;
  cursor: pointer;
  margin: 5px;
}

.button span {
  cursor: pointer;
  display: inline-block;
  position: relative;
  transition: 0.5s;
}

.button span:after {
  content: '\00bb';
  position: absolute;
  opacity: 0;
  top: 0;
  right: -20px;
  transition: 0.5s;
}

.button:hover span {
  padding-right: 25px;
}

.button:hover span:after {
  opacity: 1;
  right: 0;
}
```

## CSS Pagination Examples

**Active and Hoverable Pagination**:  

```css
.pagination {
  display: inline-block;
}

.pagination a {
  color: black;
  float: left;
  padding: 8px 16px;
  text-decoration: none;
}

.pagination a.active {
  background-color: #4CAF50;
  color: white;
}

.pagination a:hover:not(.active) {background-color: #ddd;}
```

**Hoverable Transition Effect**:  

```css
.pagination a {
  transition: background-color .3s;
}
```

**Centered Pagination**:  

```css
.center {
  text-align: center;
}
```

**Breadcrumbs**:  

```css
ul.breadcrumb {
  padding: 8px 16px;
  list-style: none;
  background-color: #eee;
}

ul.breadcrumb li {display: inline;}

ul.breadcrumb li+li:before {
  padding: 8px;
  color: black;
  content: "/\00a0";
}
```

## CSS Multiple Columns

**CSS Multi-columns Properties**:  

| Property | Description |
| column-count | Specifies the number of columns an element should be divided into |
| column-fill | Specifies how to fill columns |
| column-gap | Specifies the gap between the columns |
| column-rule | A shorthand property for setting all the column-rule-* properties |
| column-rule-color | Specifies the color of the rule between columns |
| column-rule-style | Specifies the style of the rule between columns |
| column-rule-width | Specifies the width of the rule between columns |
| column-span | Specifies how many columns an element should span across |
| column-width | Specifies a suggested, optimal width for the columns |
| columns | A shorthand property for setting column-width and column-count |

**CSS Create Multiple Columns**:  
The column-count property specifies the number of columns an element should be divided into.  
The following example will divide the text in the `<div>` element into 3 columns:  

```css
div {
  column-count: 3;
}
```

**CSS Specify the Gap Between Columns**:  
The column-gap property specifies the gap between the columns.  
The following example specifies a 40 pixels gap between the columns:

```css
div {
  column-gap: 40px;
}
```

**CSS Column Rules**:  
The **column-rule-style** property specifies the style of the rule between columns:

```css
div {
  column-rule-style: solid;
}
```

The **column-rule-width** property specifies the width of the rule between columns:

```css
div {
  column-rule-width: 1px;
}
```

The **column-rule-color** property specifies the color of the rule between columns:

```css
div {
  column-rule-color: lightblue;
}
```

The **column-rule** property is a shorthand property for setting all the column-rule-* properties above.  
The following example sets the width, style, and color of the rule between columns:

```css
div {
  column-rule: 1px solid lightblue;
}
```

**Specify How Many Columns an Element Should Span**:  
The column-span property specifies how many columns an element should span across.
The following example specifies that the `<h2>` element should span across all columns:

```css
h2 {
  column-span: all;
}
```

**Specify The Column Width**:  
The column-width property specifies a suggested, optimal width for the columns.  
The following example specifies that the suggested, optimal width for the columns should be 100px:

```css
div {
  column-width: 100px;
}
```

