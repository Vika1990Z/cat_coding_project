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

## CSS User Interface

**CSS Resizing**:  
The resize property specifies if (and how) an element should be resizable by the user.
The following example lets the user resize only the width of a `<div>` element:

```css
div {
  resize: horizontal;
  overflow: auto;
}
```

The following example lets the user resize only the height of a `<div>` element:

```css
div {
  resize: vertical;
  overflow: auto;
}
```

The following example lets the user resize both the height and width of a `<div>` element:

```css
div {
  resize: both;
  overflow: auto;
}
```

In many browsers, `<textarea>` is resizable by default. Here, we have used the resize property to disable the resizability:

```css
textarea {
  resize: none;
}
```

**CSS Outline Offset**:  
The outline-offset property adds space between an outline and the edge or border of an element.  

Note: Outline differs from borders! Unlike border, the outline is drawn outside the element's border, and may overlap other content.  
Also, the outline is NOT a part of the element's dimensions; the element's total width and height is not affected by the width of the outline.

The following example uses the outline-offset property to add space between the border and the outline:

```css
div.ex1 {
  margin: 20px;
  border: 1px solid black;
  outline: 4px solid red;
  outline-offset: 15px;
}

div.ex2 {
  margin: 10px;
  border: 1px solid black;
  outline: 5px dashed blue;
  outline-offset: 5px;
}
```

## CSS Variables - The var() Function

The var() function is used to insert the value of a CSS variable.  
CSS variables have access to the DOM, which means that you can create variables with local or global scope, change the variables with JavaScript, and change the variables based on media queries.  
A good way to use CSS variables is when it comes to the colors of your design.  
Instead of copy and paste the same colors over and over again, you can place them in variables.

**Syntax of the var() Function**:  
The var() function is used to insert the value of a CSS variable.  
The syntax of the var() function is as follows:

`var(--name, value)`

* name - Required. The variable name (must start with two dashes)
* value - Optional. The fallback value (used if the variable is not found)

**How var() Works**:  
First of all: CSS variables can have a global or local scope.  
Global variables can be accessed/used through the entire document, while local variables can be used only inside the selector where it is declared.  

To create a variable with global scope, declare it inside the :root selector.  
The :root selector matches the document's root element.

To create a variable with local scope, declare it inside the selector that is going to use it.
The following example is equal to the example above, but here we use the var() function.

First, we declare two global variables (--blue and --white).  
Then, we use the var() function to insert the value of the variables later in the style sheet:

```css
:root {
  --blue: #1e90ff;
  --white: #ffffff;
}

body { background-color: var(--blue); }

h2 { border-bottom: 2px solid var(--blue); }

.container {
  color: var(--blue);
  background-color: var(--white);
  padding: 15px;
}

button {
  background-color: var(--white);
  color: var(--blue);
  border: 1px solid var(--blue);
  padding: 5px;
}
```

**Advantages of using var() are:**:  

* makes the code easier to read (more understandable)
* makes it much easier to change the color values

### CSS Overriding Variables

**Override Global Variable With Local Variable**:  
From the previous page we have learned that global variables can be accessed/used through the entire document, while local variables can be used only inside the selector where it is declared.

Sometimes we want the variables to change only in a specific section of the page.  
Assume we want a different color of blue for button elements.  
Then, we can re-declare the --blue variable inside the button selector.  
When we use var(--blue) inside this selector, it will use the local --blue variable value declared here.  
We see that the local --blue variable will override the global --blue variable for the button elements:

```css
:root {
  --blue: #1e90ff;
  --white: #ffffff;
}

body {
  background-color: var(--blue);
}

h2 {
  border-bottom: 2px solid var(--blue);
}

.container {
  color: var(--blue);
  background-color: var(--white);
  padding: 15px;
}

button {
  --blue: #0000ff; /* local variable will override global */
  background-color: var(--white);
  color: var(--blue);
  border: 1px solid var(--blue);
  padding: 5px;
}
```

**Add a New Local Variable**:  
If a variable is to be used only one single place, we could also have declared a new local variable, like this:

```css
:root {
  --blue: #1e90ff;
  --white: #ffffff;
}

body {
  background-color: var(--blue);
}

h2 {
  border-bottom: 2px solid var(--blue);
}

.container {
  color: var(--blue);
  background-color: var(--white);
  padding: 15px;
}

button {
  --button-blue: #0000ff; /* new local variable */
  background-color: var(--white);
  color: var(--button-blue);
  border: 1px solid var(--button-blue);
  padding: 5px;
}
```

### CSS Using Variables in Media Queries

```css
/* Variable declarations */
:root {
  --blue: #1e90ff;
  --white: #ffffff;
}

.container {
  --fontsize: 25px;
}

/* Styles */
body {
  background-color: var(--blue);
}

h2 {
  border-bottom: 2px solid var(--blue);
}

.container {
  color: var(--blue);
  background-color: var(--white);
  padding: 15px;
  font-size: var(--fontsize);
}

@media screen and (min-width: 450px) {
  .container {
    --fontsize: 50px;
  }
}
```

## CSS Box Sizing

The CSS box-sizing property allows us to include the padding and border in an element's total width and height.

By default, the width and height of an element is calculated like this:

width + padding + border = actual width of an element
height + padding + border = actual height of an element

This means: When you set the width/height of an element, the element often appears bigger than you have set (because the element's border and padding are added to the element's specified width/height).

The box-sizing property solves this problem.
If you set box-sizing: border-box; on an element, padding and border are included in the width and height:

Since the result of using the box-sizing: border-box; is so much better, many developers want all elements on their pages to work this way.  
The code below ensures that all elements are sized in this more intuitive way.  
Many browsers already use box-sizing: border-box; for many form elements (but not all - which is why inputs and text areas look different at width: 100%;).  
Applying this to all elements is safe and wise:

```css
* {
  box-sizing: border-box;
}
```

## CSS Media Queries

**CSS2 Introduced Media Types**:  
The @media rule, introduced in CSS2, made it possible to define different style rules for different media types.  
Examples: You could have one set of style rules for computer screens, one for printers, one for handheld devices, one for television-type devices, and so on.  
Unfortunately these media types never got a lot of support by devices, other than the print media type.

**CSS3 Introduced Media Queries**:  
Media queries in CSS3 extended the CSS2 media types idea:  
Instead of looking for a type of device, they look at the capability of the device.
Media queries can be used to check many things, such as:  

* width and height of the viewport
* width and height of the device
* orientation (is the tablet/phone in landscape or portrait mode?)
* resolution
Using media queries are a popular technique for delivering a tailored style sheet to desktops, laptops, tablets, and mobile phones (such as iPhone and Android phones).

**Media Query Syntax**:  
A media query consists of a media type and can contain one or more expressions, which resolve to either true or false.

```css
@media not|only mediatype and (expressions) {
  CSS-Code;
}
```

The result of the query is true if the specified media type matches the type of device the document is being displayed on and all expressions in the media query are true. When a media query is true, the corresponding style sheet or style rules are applied, following the normal cascading rules.  
Unless you use the not or only operators, the media type is optional and the all type will be implied.  
You can also have different stylesheets for different media:  
`<link rel="stylesheet" media="mediatype and|not|only (expressions)" href="print.css">`

**CSS3 Media Types**:  

| Value | Description |
| all | Used for all media type devices |
| print | Used for printers |
| screen | Used for computer screens, tablets, smart-phones etc. |
| speech | Used for screenreaders that "reads" the page out loud |

```css
@media screen and (min-width: 480px) {
  #leftsidebar {width: 200px; float: left;}
  #main {margin-left: 216px;}
}
```

```css
/* Set the background color of body to tan */
body {
  background-color: tan;
}

/* On screens that are 992px or less, set the background color to blue */
@media screen and (max-width: 992px) {
  body {
    background-color: blue;
  }
}

/* On screens that are 600px or less, set the background color to olive */
@media screen and (max-width: 600px) {
  body {
    background-color: olive;
  }
}
```

**Media Queries For Columns**:

```css
/* Create four equal columns that floats next to each other */
.column {
  float: left;
  width: 25%;
}

/* On screens that are 992px wide or less, go from four columns to two columns */
@media screen and (max-width: 992px) {
  .column {
    width: 50%;
  }
}

/* On screens that are 600px wide or less, make the columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .column {
    width: 100%;
  }
}
```

Tip: A more modern way of creating column layouts, is to use CSS Flexbox (see example below).  
However, it is not supported in Internet Explorer 10 and earlier versions.  
If you require IE6-10 support, use floats (as shown above).

```css
/* Container for flexboxes */
.row {
  display: flex;
  flex-wrap: wrap;
}

/* Create four equal columns */
.column {
  flex: 25%;
  padding: 20px;
}

/* On screens that are 992px wide or less, go from four columns to two columns */
@media screen and (max-width: 992px) {
  .column {
    flex: 50%;
  }
}

/* On screens that are 600px wide or less, make the columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .row {
    flex-direction: column;
  }
}
```

**Hide Elements With Media Queries**:

```css
/* If the screen size is 600px wide or less, hide the element */
@media screen and (max-width: 600px) {
  div.example {
    display: none;
  }
}
```

**Change Font Size With Media Queries**:  

```css
/* If screen size is more than 600px wide, set the font-size of <div> to 80px */
@media screen and (min-width: 600px) {
  div.example {
    font-size: 80px;
  }
}

/* If screen size is 600px wide, or less, set the font-size of <div> to 30px */
@media screen and (max-width: 600px) {
  div.example {
    font-size: 30px;
  }
}
```

**Orientation: Portrait / Landscape**:  
Media queries can also be used to change layout of a page depending on the orientation of the browser.  
You can have a set of CSS properties that will only apply when the browser window is wider than its height, a so called "Landscape" orientation:

```css
@media only screen and (orientation: landscape) {
  body {
    background-color: lightblue;
  }
}
```

**Min Width to Max Width**:  
You can also use the (max-width: ..) and (min-width: ..) values to set a minimum width and a maximum width.

```css
/* when the browser's width is between 600 and 900px, change the appearance of a <div> element: */
@media screen and (max-width: 900px) and (min-width: 600px) {
  div.example {
    font-size: 50px;
    padding: 50px;
    border: 8px solid black;
    background: yellow;
  }
}
```

Using an additional value: In the example below, we add an additional media query to our already existing one using a comma (this will behave like an OR operator):

```css
/* When the width is between 600px and 900px OR above 1100px - change the appearance of <div> */
@media screen and (max-width: 900px) and (min-width: 600px), (min-width: 1100px) {
  div.example {
    font-size: 50px;
    padding: 50px;
    border: 8px solid black;
    background: yellow;
  }
}
```

## CSS Flexbox

Before the Flexbox Layout module, there were four layout modes:  
Block, for sections in a webpage.  
Inline, for text.  
Table, for two-dimensional table data.  
Positioned, for explicit position of an element.  

The Flexible Box Layout Module, makes it easier to design flexible responsive layout structure without using float or positioning.

### Flexbox Elements

To start using the Flexbox model, you need to first define a flex container.

```css
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

**Parent Element (Container)**:  
Like we specified in the previous chapter, this is a flex container (the blue area) with three flex items:
**The flex container properties are**:  
flex-direction  
flex-wrap  
flex-flow  
justify-content  
align-items  
align-content  

**The flex-direction Property**:  
The flex-direction property defines in which direction the container wants to stack the flex items.

```css
/*The column value stacks the flex items vertically (from top to bottom):*/
.flex-container {
  display: flex;
  flex-direction: column;
}
```

The column value stacks the flex items vertically (from top to bottom).  
The column-reverse value stacks the flex items vertically (but from bottom to top).  
The row value stacks the flex items horizontally (from left to right).  
The row-reverse value stacks the flex items horizontally (but from right to left).  

**The flex-wrap Property**:  
The flex-wrap property specifies whether the flex items should wrap or not.
The examples below have 12 flex items, to better demonstrate the flex-wrap property.

```css
.flex-container {
  display: flex;
  flex-wrap: wrap;
}
```

The wrap value specifies that the flex items will wrap if necessary.  
The nowrap value specifies that the flex items will not wrap (this is default).  
The wrap-reverse value specifies that the flexible items will wrap if necessary, in reverse order.  

**The flex-flow Property**:  
The flex-flow property is a shorthand property for setting both the flex-direction and flex-wrap properties.

```css
.flex-container {
  display: flex;
  flex-flow: row wrap;
}
```

**The justify-content Property**:  
The justify-content property is used to align the flex items.  

```css
.flex-container {
  display: flex;
  justify-content: center;
}
```

The center value aligns the flex items at the center of the container.  
The flex-start value aligns the flex items at the beginning of the container (this is default).  
The flex-end value aligns the flex items at the end of the container.  
The space-around value displays the flex items with space before, between, and after the lines.  
The space-between value displays the flex items with space between the lines.  

**The align-items Property**:  
The align-items property is used to vertical align the flex items.  

```css
.flex-container {
  display: flex;
  height: 200px;
  align-items: center;
}
```

The center value aligns the flex items in the middle of the container.  
The flex-start value aligns the flex items at the top of the container.  
The flex-end value aligns the flex items at the bottom of the container.  
The stretch value stretches the flex items to fill the container (this is default).  
The baseline value aligns the flex items such as their baselines aligns.  

**The align-content Property**:  
The align-content property is used to align the flex lines.

```css
.flex-container {
  display: flex;
  height: 600px;
  flex-wrap: wrap;
  align-content: space-between;
}
```

The space-between value displays the flex lines with equal space between them.  
The space-around value displays the flex lines with space before, between, and after them.  
The stretch value stretches the flex lines to take up the remaining space (this is default).  
The center value displays display the flex lines in the middle of the container.  
The flex-start value displays the flex lines at the start of the container.  
The flex-end value displays the flex lines at the end of the container.  

**Perfect Centering**:  
In the following example we will solve a very common style problem: perfect centering.

SOLUTION: Set both the justify-content and align-items properties to center, and the flex item will be perfectly centered:

```css
.flex-container {
  display: flex;
  height: 300px;
  justify-content: center;
  align-items: center;
}
```

### CSS Flex Items

**Child Elements (Items)**:  
The direct child elements of a flex container automatically becomes flexible (flex) items.

```css
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
```

**The order Property**:  
The order property specifies the order of the flex items.  
The first flex item in the code does not have to appear as the first item in the layout.  
The order value must be a number, default value is 0.

```css
<div class="flex-container">
  <div style="order: 3">1</div>
  <div style="order: 2">2</div>
  <div style="order: 4">3</div>
  <div style="order: 1">4</div>
</div>
```

**The flex-grow Property**:  
The flex-grow property specifies how much a flex item will grow relative to the rest of the flex items.  
The value must be a number, default value is 0.

```css
<div class="flex-container">
  <div style="flex-grow: 1">1</div>
  <div style="flex-grow: 1">2</div>
  <div style="flex-grow: 8">3</div>
</div>
```

**The flex-shrink Property**:  
The flex-shrink property specifies how much a flex item will shrink relative to the rest of the flex items.

```css
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div style="flex-shrink: 0">3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
  <div>7</div>
  <div>8</div>
  <div>9</div>
  <div>10</div>
</div>
```

**The flex-basis Property**:  
The flex-basis property specifies the initial length of a flex item.

```css
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div style="flex-basis: 200px">3</div>
  <div>4</div>
</div>
```

**The flex Property**:  
The flex property is a shorthand property for the flex-grow, flex-shrink, and flex-basis properties.

```css
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div style="flex: 0 0 200px">3</div>
  <div>4</div>
</div>
```

**The align-self Property**:  
The align-self property specifies the alignment for the selected item inside the flexible container.
The align-self property overrides the default alignment set by the container's align-items property.

```css
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div style="align-self: center">3</div>
  <div>4</div>
</div>
```

### CSS Flex Responsive

For example, if you want to create a two-column layout for most screen sizes, and a one-column layout for small screen sizes (such as phones and tablets), you can change the flex-direction from row to column at a specific breakpoint (800px in the example below):

```css
.flex-container {
  display: flex;
  flex-direction: row;
}

/* Responsive layout - makes a one column layout instead of a two-column layout */
@media (max-width: 800px) {
  .flex-container {
    flex-direction: column;
  }
}
```

Another way is to change the percentage of the flex property of the flex items to create different layouts for different screen sizes. Note that we also have to include flex-wrap: wrap; on the flex container for this example to work:

```css
.flex-container {
  display: flex;
  flex-wrap: wrap;
}

.flex-item-left {
  flex: 50%;
}

.flex-item-right {
  flex: 50%;
}

/* Responsive layout - makes a one column layout instead of a two-column layout */
@media (max-width: 800px) {
  .flex-item-right, .flex-item-left {
    flex: 100%;
  }
}
```

## CSS Responsive

The viewport is the user's visible area of a web page.

You should include the following `<meta>` viewport element in all your web pages:  
`<meta name="viewport" content="width=device-width, initial-scale=1.0">`

The `width=device-width` part sets the width of the page to follow the screen-width of the device (which will vary depending on the device).  
The `initial-scale=1.0` part sets the initial zoom level when the page is first loaded by the browser.  

Some additional rules to follow:  

1. Do NOT use large fixed width elements;  
For example, if an image is displayed at a width wider than the viewport it can cause the viewport to scroll horizontally.  
Remember to adjust this content to fit within the width of the viewport.

2. Do NOT let the content rely on a particular viewport width to render well;  
Since screen dimensions and width in CSS pixels vary widely between devices, content should not rely on a particular viewport width to render well.

3. Use CSS media queries to apply different styling for small and large screens;  
Setting large absolute CSS widths for page elements will cause the element to be too wide for the viewport on a smaller device.  
Instead, consider using relative width values, such as width: 100%. Also, be careful of using large absolute positioning values.  
It may cause the element to fall outside the viewport on small devices.  

### Grid-View

A responsive grid-view often has 12 columns, and has a total width of 100%, and will shrink and expand as you resize the browser window.  

#### Building a Responsive Grid-View

First ensure that all HTML elements have the box-sizing property set to border-box.  
This makes sure that the padding and border are included in the total width and height of the elements.  
Add the following code in your CSS:

```css
* {
  box-sizing: border-box;
}
```

However, we want to use a responsive grid-view with 12 columns, to have more control over the web page.  
First we must calculate the percentage for one column: 100% / 12 columns = 8.33%.  
Then we make one class for each of the 12 columns, class="col-" and a number defining how many columns the section should span:  

```css
.col-1 {width: 8.33%;}
.col-2 {width: 16.66%;}
.col-3 {width: 25%;}
.col-4 {width: 33.33%;}
.col-5 {width: 41.66%;}
.col-6 {width: 50%;}
.col-7 {width: 58.33%;}
.col-8 {width: 66.66%;}
.col-9 {width: 75%;}
.col-10 {width: 83.33%;}
.col-11 {width: 91.66%;}
.col-12 {width: 100%;}
```

All these columns should be floating to the left, and have a padding of 15px:

```css
[class*="col-"] {
  float: left;
  padding: 15px;
  border: 1px solid red;
}
```

Each row should be wrapped in a `<div>`.  
The number of columns inside a row should always add up to 12:

```html
<div class="row">
  <div class="col-3">...</div> <!-- 25% -->
  <div class="col-9">...</div> <!-- 75% -->
</div>
```

The columns inside a row are all floating to the left, and are therefore taken out of the flow of the page, and other elements will be placed as if the columns do not exist.  
To prevent this, we will add a style that clears the flow:

```css
.row::after {
  content: "";
  clear: both;
  display: table;
}
```

We also want to add some styles and colors to make it look better:

```css
html {
  font-family: "Lucida Sans", sans-serif;
}

.header {
  background-color: #9933cc;
  color: #ffffff;
  padding: 15px;
}

.menu ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.menu li {
  padding: 8px;
  margin-bottom: 7px;
  background-color :#33b5e5;
  color: #ffffff;
  box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
}

.menu li:hover {
  background-color: #0099cc;
}
```

### Media Queries

The @media rule is used in media queries to apply different styles for different media types/devices.

**Media queries can be used to check many things, such as:**

* width and height of the viewport
* width and height of the device
* orientation (is the tablet/phone in landscape or portrait mode?)
* resolution

**CSS Syntax**:  

```css
@media not|only mediatype and (mediafeature and|or|not mediafeature) {
  CSS-Code;
}
```

**meaning of the not, only and and keywords:**:  

* not: The not keyword inverts the meaning of an entire media query.
* only: The only keyword prevents older browsers that do not support media queries with media features from applying the specified styles. It has no effect on modern browsers.
* and: The and keyword combines a media feature with a media type or other media features.

They are all optional. However, if you use not or only, you must also specify a media type.

You can also have different stylesheets for different media, like this:

```html
<link rel="stylesheet" media="screen and (min-width: 900px)" href="widescreen.css">
<link rel="stylesheet" media="screen and (max-width: 600px)" href="smallscreen.css">
....
```

**Media Types**:  

| Value | Description |
| all | Default. Used for all media type devices |
| print | Used for printers |
| screen | Used for computer screens, tablets, smart-phones etc. |
| speech | Used for screenreaders that "reads" the page out loud |

**Media Features**:  

| Value | Description |
| any-hover | Does any available input mechanism allow the user to hover over elements? (added in Media Queries Level 4) |
| any-pointer | Is any available input mechanism a pointing device, and if so, how accurate is it? (added in Media Queries Level 4) |
| aspect-ratio | The ratio between the width and the height of the viewport |
| color | The number of bits per color component for the output device |
| color-gamut | The approximate range of colors that are supported by the user agent and output device (added in Media Queries Level 4) |
| color-index | The number of colors the device can display |
| grid | Whether the device is a grid or bitmap |
| height | The viewport height |
| hover | Does the primary input mechanism allow the user to hover over elements? (added in Media Queries Level 4) |
| inverted-colors | Is the browser or underlying OS inverting colors? (added in Media Queries Level 4) |
| light-level | Current ambient light level (added in Media Queries Level 4) |
| max-aspect-ratio | The maximum ratio between the width and the height of the display area |
| max-color | The maximum number of bits per color component for the output device |
| max-color-index | The maximum number of colors the device can display |
| max-height | The maximum height of the display area, such as a browser window |
| max-monochrome | The maximum number of bits per "color" on a monochrome (greyscale) device |
| max-resolution | The maximum resolution of the device, using dpi or dpcm |
| max-width | The maximum width of the display area, such as a browser window |
| min-aspect-ratio | The minimum ratio between the width and the height of the display area |
| min-color | The minimum number of bits per color component for the output device |
| min-color-index | The minimum number of colors the device can display |
| min-height | The minimum height of the display area, such as a browser window |
| min-monochrome | The minimum number of bits per "color" on a monochrome (greyscale) device |
| min-resolution | The minimum resolution of the device, using dpi or dpcm |
| min-width | The minimum width of the display area, such as a browser window |
| monochrome | The number of bits per "color" on a monochrome (greyscale) device |
| orientation | The orientation of the viewport (landscape or portrait mode) |
| overflow-block | How does the output device handle content that overflows the viewport along the block axis (added in Media Queries Level 4) |
| overflow-inline | Can content that overflows the viewport along the inline axis be scrolled (added in Media Queries Level 4) |
| pointer | Is the primary input mechanism a pointing device, and if so, how accurate is it? (added in Media Queries Level 4) |
| resolution | The resolution of the output device, using dpi or dpcm |
| scan | The scanning process of the output device |
| scripting | Is scripting (e.g. JavaScript) available? (added in Media Queries Level 4) |
| update | How quickly can the output device modify the appearance of the content (added in Media Queries Level 4) |
| width | The viewport width |

Media query is a CSS technique introduced in CSS3.  
It uses the @media rule to include a block of CSS properties only if a certain condition is true.

```css
@media only screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

### Add a Breakpoint

Earlier in this tutorial we made a web page with rows and columns, and it was responsive, but it did not look good on a small screen.  
Media queries can help with that. We can add a breakpoint where certain parts of the design will behave differently on each side of the breakpoint.

```css
/* For desktop: */
.col-1 {width: 8.33%;}
.col-2 {width: 16.66%;}
.col-3 {width: 25%;}
.col-4 {width: 33.33%;}
.col-5 {width: 41.66%;}
.col-6 {width: 50%;}
.col-7 {width: 58.33%;}
.col-8 {width: 66.66%;}
.col-9 {width: 75%;}
.col-10 {width: 83.33%;}
.col-11 {width: 91.66%;}
.col-12 {width: 100%;}

@media only screen and (max-width: 768px) {
  /* For mobile phones: */
  [class*="col-"] {
    width: 100%;
  }
}
```

**Always Design for Mobile First**:  
Mobile First means designing for mobile before designing for desktop or any other device (This will make the page display faster on smaller devices).  
This means that we must make some changes in our CSS.  
Instead of changing styles when the width gets smaller than 768px, we should change the design when the width gets larger than 768px.  
This will make our design Mobile First:  

```css
/* For mobile phones: */
[class*="col-"] {
  width: 100%;
}

@media only screen and (min-width: 768px) {
  /* For desktop: */
  .col-1 {width: 8.33%;}
  .col-2 {width: 16.66%;}
  .col-3 {width: 25%;}
  .col-4 {width: 33.33%;}
  .col-5 {width: 41.66%;}
  .col-6 {width: 50%;}
  .col-7 {width: 58.33%;}
  .col-8 {width: 66.66%;}
  .col-9 {width: 75%;}
  .col-10 {width: 83.33%;}
  .col-11 {width: 91.66%;}
  .col-12 {width: 100%;}
}
```

You can add as many breakpoints as you like.  
We will also insert a breakpoint between tablets and mobile phones.  
We do this by adding one more media query (at 600px), and a set of new classes for devices larger than 600px (but smaller than 768px):  

```css
/* For mobile phones: */
[class*="col-"] {
  width: 100%;
}

@media only screen and (min-width: 600px) {
  /* For tablets: */
  .col-s-1 {width: 8.33%;}
  .col-s-2 {width: 16.66%;}
  .col-s-3 {width: 25%;}
  .col-s-4 {width: 33.33%;}
  .col-s-5 {width: 41.66%;}
  .col-s-6 {width: 50%;}
  .col-s-7 {width: 58.33%;}
  .col-s-8 {width: 66.66%;}
  .col-s-9 {width: 75%;}
  .col-s-10 {width: 83.33%;}
  .col-s-11 {width: 91.66%;}
  .col-s-12 {width: 100%;}
}

@media only screen and (min-width: 768px) {
  /* For desktop: */
  .col-1 {width: 8.33%;}
  .col-2 {width: 16.66%;}
  .col-3 {width: 25%;}
  .col-4 {width: 33.33%;}
  .col-5 {width: 41.66%;}
  .col-6 {width: 50%;}
  .col-7 {width: 58.33%;}
  .col-8 {width: 66.66%;}
  .col-9 {width: 75%;}
  .col-10 {width: 83.33%;}
  .col-11 {width: 91.66%;}
  .col-12 {width: 100%;}
}
```

```html
<div class="row">
  <div class="col-3 col-s-3">...</div>
  <div class="col-6 col-s-9">...</div>
  <div class="col-3 col-s-12">...</div>
</div>
```

**Typical Device Breakpoints**:  
There are tons of screens and devices with different heights and widths, so it is hard to create an exact breakpoint for each device. To keep things simple you could target five groups:

```css
/* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {...}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {...}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {...}

/* Large devices (laptops/desktops, 992px and up) */
@media only screen and (min-width: 992px) {...}

/* Extra large devices (large laptops and desktops, 1200px and up) */
@media only screen and (min-width: 1200px) {...}
```

#### Orientation: Portrait / Landscape

Media queries can also be used to change layout of a page depending on the orientation of the browser.  
You can have a set of CSS properties that will only apply when the browser window is wider than its height, a so called "Landscape" orientation:  

```css
@media only screen and (orientation: landscape) {
  body {
    background-color: lightblue;
  }
}
```

#### Hide Elements With Media Queries

Another common use of media queries, is to hide elements on different screen sizes:

```css
/* If the screen size is 600px wide or less, hide the element */
@media only screen and (max-width: 600px) {
  div.example {
    display: none;
  }
}
```

#### Change Font Size With Media Queries

You can also use media queries to change the font size of an element on different screen sizes:

```css
/* If the screen size is 601px or more, set the font-size of <div> to 80px */
@media only screen and (min-width: 601px) {
  div.example {
    font-size: 80px;
  }
}

/* If the screen size is 600px or less, set the font-size of <div> to 30px */
@media only screen and (max-width: 600px) {
  div.example {
    font-size: 30px;
  }
}
```

## Responsive Web Design - Images

**Using The width Property**:  
If the width property is set to a percentage and the height property is set to "auto", the image will be responsive and scale up and down:

```css
img {
  width: 100%;
  height: auto;
}
```

Notice that in the example above, the image can be scaled up to be larger than its original size.  
A better solution, in many cases, will be to use the max-width property instead.

**Using The max-width Property**:  
If the max-width property is set to 100%, the image will scale down if it has to, but never scale up to be larger than its original size:  

```css
img {
  max-width: 100%;
  height: auto;
}
```

**Different Images for Different Devices**:  

```css
/* For width smaller than 400px: */
body {
  background-image: url('img_smallflower.jpg');
}

/* For width 400px and larger: */
@media only screen and (min-width: 400px) {
  body {
    background-image: url('img_flowers.jpg');
  }
}
```

You can use the media query min-device-width, instead of min-width, which checks the device width, instead of the browser width. Then the image will not change when you resize the browser window:

```css
/* For devices smaller than 400px: */
body {
  background-image: url('img_smallflower.jpg');
}

/* For devices 400px and larger: */
@media only screen and (min-device-width: 400px) {
  body {
    background-image: url('img_flowers.jpg');
  }
}
```

### The HTML `<picture>` Element

The HTML `<picture>` element gives web developers more flexibility in specifying image resources.  
The most common use of the `<picture>` element will be for images used in responsive designs.  
Instead of having one image that is scaled up or down based on the viewport width, multiple images can be designed to more nicely fill the browser viewport.

The `<picture>` element works similar to the `<video>` and `<audio>` elements.  
You set up different sources, and the first source that fits the preferences is the one being used:

```html
<picture>
  <source srcset="img_smallflower.jpg" media="(max-width: 400px)">
  <source srcset="img_flowers.jpg">
  <img src="img_flowers.jpg" alt="Flowers">
</picture>
```

The `srcset` attribute is required, and defines the source of the image.  
The media attribute is optional, and accepts the media queries you find in CSS @media rule.  
You should also define an `<img>` element for browsers that do not support the `<picture>` element.

## Responsive Web Design - Videos

**Using The width Property**:  
If the width property is set to 100%, the video player will be responsive and scale up and down:

```css
video {
  width: 100%;
  height: auto;
}
```

Notice that in the example above, the video player can be scaled up to be larger than its original size. A better solution, in many cases, will be to use the max-width property instead.

**Using The max-width Property**:  
If the max-width property is set to 100%, the video player will scale down if it has to, but never scale up to be larger than its original size:

```css
video {
  max-width: 100%;
  height: auto;
}
```

**Add a Video to the Example Web Page**:  
We want to add a video in our example web page. The video will be resized to always take up all the available space:

```css
video {
  width: 100%;
  height: auto;
```

## CSS Grid Layout Module

The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

Grid Elements
A grid layout consists of a parent element, with one or more child elements.

```html
<div class="grid-container">
  <div class="grid-item">1</div>
  <div class="grid-item">2</div>
  <div class="grid-item">3</div>
  <div class="grid-item">4</div>
  <div class="grid-item">5</div>
  <div class="grid-item">6</div>
  <div class="grid-item">7</div>
  <div class="grid-item">8</div>
  <div class="grid-item">9</div>
</div>
```

A Grid Layout must have a parent element with the display property set to grid or inline-grid.  
Direct child element(s) of the grid container automatically becomes grid items.  

```css
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto;
  background-color: #2196F3;
  padding: 10px;
}
.grid-item {
  background-color: rgba(255, 255, 255, 0.8);
  border: 1px solid rgba(0, 0, 0, 0.8);
  padding: 20px;
  font-size: 30px;
  text-align: center;
}
```

**Display Property**:  
An HTML element becomes a grid container when its display property is set to grid or inline-grid.
All direct children of the grid container automatically become grid items.

```css
.grid-container {
  display: grid;
}
```

**Grid Columns**:  
The vertical lines of grid items are called columns.

**Grid Rows**:  
The horizontal lines of grid items are called rows.

**Grid Gaps**:  
The spaces between each column/row are called gaps.  
You can adjust the gap size by using one of the following properties:  
column-gap  
row-gap  
gap  

```css
.grid-container {
  display: grid;
  column-gap: 50px;
}
```

**Grid Lines**:  
The lines between columns are called column lines.  
The lines between rows are called row lines.  
Refer to line numbers when placing a grid item in a grid container:

Place a grid item at column line 1, and let it end on column line 3:

```css
.item1 {
  grid-column-start: 1;
  grid-column-end: 3;
}
```

Place a grid item at row line 1, and let it end on row line 3:

```css
.item1 {
  grid-row-start: 1;
  grid-row-end: 3;
}
```

**All CSS Grid Properties**:  

| Property | Description |
| column-gap | Specifies the gap between the columns |
| gap | A shorthand property for the row-gap and the column-gap properties |
| grid | A shorthand property for the grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and the grid-auto-flow properties |
| grid-area | Either specifies a name for the grid item, or this property is a shorthand property for the grid-row-start, grid-column-start, grid-row-end, and grid-column-end properties |
| grid-auto-columns | Specifies a default column size |
| grid-auto-flow | Specifies how auto-placed items are inserted in the grid |
| grid-auto-rows | Specifies a default row size |
| grid-column | A shorthand property for the grid-column-start and the grid-column-end properties |
| grid-column-end | Specifies where to end the grid item |
| grid-column-gap | Specifies the size of the gap between columns |
| grid-column-start | Specifies where to start the grid item |
| grid-gap | A shorthand property for the grid-row-gap and grid-column-gap properties |
| grid-row | A shorthand property for the grid-row-start and the grid-row-end properties |
| grid-row-end | Specifies where to end the grid item |
| grid-row-gap | Specifies the size of the gap between rows |
| grid-row-start | Specifies where to start the grid item |
| grid-template | A shorthand property for the grid-template-rows, grid-template-columns and grid-areas properties |
| grid-template-areas | Specifies how to display columns and rows, using named grid items |
| grid-template-columns | Specifies the size of the columns, and how many columns in a grid layout |
| grid-template-rows | Specifies the size of the rows in a grid layout |
| row-gap | Specifies the gap between the grid rows |

### Grid Container

To make an HTML element behave as a grid container, you have to set the display property to grid or inline-grid.  
Grid containers consist of grid items, placed inside columns and rows.  

**The grid-template-columns Property**:  
The grid-template-columns property defines the number of columns in your grid layout, and it can define the width of each column.
The value is a space-separated-list, where each value defines the width of the respective column.
If you want your grid layout to contain 4 columns, specify the width of the 4 columns, or "auto" if all columns should have the same width.

```css
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto;
}
```

Note: If you have more than 4 items in a 4 columns grid, the grid will automatically add a new row to put the items in.

The grid-template-columns property can also be used to specify the size (width) of the columns.

```css
.grid-container {
  display: grid;
  grid-template-columns: 80px 200px auto 40px;
}
```

**The grid-template-rows Property**:  
The grid-template-rows property defines the height of each row.

```css
.grid-container {
  display: grid;
  grid-template-rows: 80px 200px;
}
```

**The justify-content Property**:  
The justify-content property is used to align the whole grid inside the container.

Note: The grid's total width has to be less than the container's width for the justify-content property to have any effect.

```css
.grid-container {
  display: grid;
  justify-content: space-evenly;
}
```

**The align-content Property**:  
The align-content property is used to vertically align the whole grid inside the container.
Note: The grid's total height has to be less than the container's height for the align-content property to have any effect.

```css
.grid-container {
  display: grid;
  height: 400px;
  align-content: center;
}
```

### CSS Grid Item

**Child Elements (Items)**:  
A grid container contains grid items.
By default, a container has one grid item for each column, in each row, but you can style the grid items so that they will span multiple columns and/or rows.

**The grid-column Property**:  
The grid-column property defines on which column(s) to place an item.  
You define where the item will start, and where the item will end.  
Note: The grid-column property is a shorthand property for the grid-column-start and the grid-column-end properties.

To place an item, you can refer to line numbers, or use the keyword "span" to define how many columns the item will span.

```css
/* Make "item1" start on column 1 and end before column 5: */
.item1 {
  grid-column: 1 / 5;
}
```

```css
/* Make "item1" start on column 1 and span 3 columns: */
.item1 {
  grid-column: 1 / span 3;
}
```

**The grid-row Property**:  
The grid-row property defines on which row to place an item.  
You define where the item will start, and where the item will end.  
Note: The grid-row property is a shorthand property for the grid-row-start and the grid-row-end properties.

To place an item, you can refer to line numbers, or use the keyword "span" to define how many rows the item will span:

```css
/* Make "item1" start on row-line 1 and end on row-line 4: */
.item1 {
  grid-row: 1 / 4;
}
```

```css
/* Make "item1" start on row 1 and span 2 rows: */
.item1 {
  grid-row: 1 / span 2;
}
```

**The grid-row Property**:  
The grid-row property defines on which row to place an item.  
You define where the item will start, and where the item will end.  
Note: The grid-row property is a shorthand property for the grid-row-start and the grid-row-end properties.

To place an item, you can refer to line numbers, or use the keyword "span" to define how many rows the item will span:

```css
.item1 {
  grid-row: 1 / 4;
}
```

**The grid-area Property**:  
The grid-area property can be used as a shorthand property for the grid-row-start, grid-column-start, grid-row-end and the grid-column-end properties.
You can use the grid-area property to specify where to place an item.

The syntax is:  
`grid-row-start / grid-column-start / grid-row-end / grid-column-end.`

```css
/* Make "item8" start on row-line 1 and column-line 2, and end on row-line 5 and column line 6: */
.item8 {
  grid-area: 1 / 2 / 5 / 6;
}
```

```css
.item8 {
  grid-area: 2 / 1 / span 2 / span 3;
}
```

**Naming Grid Items**:  
The grid-area property can also be used to assign names to grid items.  
Named grid items can be referred to by the grid-template-areas property of the grid container.

```css
.item1 {
  grid-area: myArea;
}
.grid-container {
  grid-template-areas: 'myArea myArea myArea myArea myArea';
}
```

Each row is defined by apostrophes (' ')

The columns in each row is defined inside the apostrophes, separated by a space.

```css
/* Let "myArea" span two columns in a five columns grid layout (period signs represent items with no name): */
.item1 {
  grid-area: myArea;
}
.grid-container {
  grid-template-areas: 'myArea myArea . . .';
}
```

To define two rows, define the column of the second row inside another set of apostrophes:

```css
/* Make "item1" span two columns and two rows: */
.grid-container {
  grid-template-areas: 'myArea myArea . . .' 'myArea myArea . . .';
}
```

Name all items, and make a ready-to-use webpage template:

```css
.item1 { grid-area: header; }
.item2 { grid-area: menu; }
.item3 { grid-area: main; }
.item4 { grid-area: right; }
.item5 { grid-area: footer; }

.grid-container {
  display: grid;
  grid-template-areas:
    'header header header header header header'
    'menu main main main right right'
    'menu footer footer footer footer footer';
  gap: 10px;
  background-color: #2196F3;
  padding: 10px;
}

.grid-container > div {
  background-color: rgba(255, 255, 255, 0.8);
  text-align: center;
  padding: 20px 0;
  font-size: 30px;
  ```

**The Order of the Items**:  
The Grid Layout allows us to position the items anywhere we like.  
The first item in the HTML code does not have to appear as the first item in the grid.  

```css
.item1 { grid-area: 1 / 3 / 2 / 4; }
.item2 { grid-area: 2 / 3 / 3 / 4; }
.item3 { grid-area: 1 / 1 / 2 / 2; }
.item4 { grid-area: 1 / 2 / 2 / 3; }
.item5 { grid-area: 2 / 1 / 3 / 2; }
.item6 { grid-area: 2 / 2 / 3 / 3; }
```

You can re-arrange the order for certain screen sizes, by using media queries:

```css
@media only screen and (max-width: 500px) {
  .item1 { grid-area: 1 / span 3 / 2 / 4; }
  .item2 { grid-area: 3 / 3 / 4 / 4; }
  .item3 { grid-area: 2 / 1 / 3 / 2; }
  .item4 { grid-area: 2 / 2 / span 2 / 3; }
  .item5 { grid-area: 3 / 1 / 4 / 2; }
  .item6 { grid-area: 2 / 3 / 3 / 4; }
}
```

## Sass Tutorial

Sass is a CSS pre-processor.  
Sass reduces repetition of CSS and therefore saves time.

```css
/* Define standard variables and values for website */
$bgcolor: lightblue;
$textcolor: darkblue;
$fontsize: 18px;

/* Use the variables */
body {
  background-color: $bgcolor;
  color: $textcolor;
  font-size: $fontsize;
}
```
