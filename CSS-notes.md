# CSS notes

> Here are reprezented my own notes about CSS

CSS stands for Cascading Style Sheets
CSS describes how HTML elements are to be displayed on screen, paper, or in other media
CSS saves a lot of work. It can control the layout of multiple web pages all at once
External stylesheets are stored in CSS files

*A CSS rule consists of a selector and a declaration block.*

The **selector** points to the HTML element you want to style.  
The **declaration block** contains one or more declarations separated by semicolons.  
Each declaration includes a CSS **property name** and a **value**, separated by a colon.  
Multiple CSS declarations are separated with semicolons, and declaration blocks are surrounded by curly braces.

## Selectors

We can divide CSS selectors into five categories:

* Simple selectors (select elements based on name, id, class)
* Combinator selectors (select elements based on a specific relationship between them)
* Pseudo-class selectors (select elements based on a certain state)
* Pseudo-elements selectors (select and style a part of an element)
* Attribute selectors (select elements based on an attribute or attribute value)

### All CSS Simple Selectors

| Selector | Example | Example description |
| `#id` | `#firstname` | Selects the element with id="firstname" |
| `.class` | `.intro` | Selects all elements with class="intro" |
| `element.class` | `p.intro` |Selects only `<p>` elements with class="intro" |
| `*` | `*` | Selects all elements |
| `element` | `p` | Selects all `<p>` elements |
| `element,element,..` | `div, p` | Selects all `<div>` elements and all `<p>` elements |

**The CSS element Selector**:  
The element selector selects HTML elements based on the element name.

```css
p {
  text-align: center;
  color: red;
}
```

**The CSS id Selector**:  
The id selector uses the id attribute of an HTML element to select a specific element.  
The id of an element is unique within a page, so the id selector is used to select one unique element!  
To select an element with a specific id, write a hash (#) character, followed by the id of the element.  
Note: An id name cannot start with a number!

```css
#para1 {
  text-align: center;
  color: red;
}
```

**The CSS class Selector**:  
The class selector selects HTML elements with a specific class attribute.  
To select elements with a specific class, write a period (.) character, followed by the class name.
Note: A class name cannot start with a number!  

In this example all HTML elements with class="center" will be red and center-aligned:

```css
.center {
  text-align: center;
  color: red;
}
```

You can also specify that only specific HTML elements should be affected by a class.
In this example only `<p>` elements with class="center" will be red and center-aligned:

```css
p.center {
  text-align: center;
  color: red;
}
```

HTML elements can also refer to more than one class.  
In this example the `<p>` element will be styled according to class="center" and to class="large":

```css
<p class="center large">This paragraph refers to two classes.</p>
```

**The CSS Universal Selector**:  
The universal selector (*) selects all HTML elements on the page.
The CSS rule below will affect every HTML element on the page:

```css
* {
  text-align: center;
  color: blue;
}
```

**The CSS Grouping Selector**:  
The grouping selector selects all the HTML elements with the same style definitions.

```css
h1, h2, p {
  text-align: center;
  color: red;
}
```

### CSS Combinators

A **combinator** is something that explains the relationship between the selectors.  
A CSS selector can contain more than one simple selector. Between the simple selectors, we can include a combinator.  
There are four different combinators in CSS:

* descendant selector (space)
* child selector (>)
* adjacent sibling selector (+)
* general sibling selector (~)

**All CSS Combinator Selectors**:  

| Selector | Example | Example description |
| element element | div p | Selects all `<p>` elements inside `<div>` elements |
| element>element | div > p | Selects all `<p>` elements where the parent is a `<div>` element |
| element+element | div + p | Selects the first `<p>` element that are placed immediately after `<div>` elements |
| element1~element2 | p ~ ul | Selects every `<ul>` element that are preceded by a `<p>` element |

**Descendant Selector**:  
The descendant selector matches all elements that are descendants of a specified element.  
The following example selects all `<p>` elements inside `<div>` elements:

```css
div p {
  background-color: yellow;
}
```

**Child Selector (>)**:  
The child selector selects all elements that are the children of a specified element.  
The following example selects all `<p>` elements that are children of a `<div>` element:

```css
div > p {
  background-color: yellow;
}
```

**Adjacent Sibling Selector (+)**:  
The adjacent sibling selector is used to select an element that is directly after another specific element.  
Sibling elements must have the same parent element, and "adjacent" means "immediately following".  
The following example selects the first `<p>` element that are placed immediately after `<div>` elements:

```css
div + p {
  background-color: yellow;
}
```

**General Sibling Selector (~)**:  
The general sibling selector selects all elements that are next siblings of a specified element.  
The following example selects all `<p>` elements that are next siblings of `<div>` elements:

```css
div ~ p {
  background-color: yellow;
}
```

### CSS Pseudo-classes

A pseudo-class is used to define a special state of an element.  
For example, it can be used to:

* Style an element when a user mouses over it
* Style visited and unvisited links differently
* Style an element when it gets focus

**Syntax**:  
The syntax of pseudo-classes:

```css
selector:pseudo-class {
  property: value;
}
```

**All CSS Pseudo Classes**:  

| Selector | Example | Example description |
| :active | a:active | Selects the active link |
| :checked | input:checked | Selects every checked `<input>` element |
| :disabled | input:disabled | Selects every disabled `<input>` element |
| :empty | p:empty | Selects every `<p>` element that has no children |
| :enabled | input:enabled | Selects every enabled `<input>` element |
| :first-child | p:first-child | Selects every `<p>` elements that is the first child of its parent |
| :first-of-type | p:first-of-type | Selects every `<p>` element that is the first `<p>` element of its parent |
| :focus | input:focus | Selects the `<input>` element that has focus |
| :hover | a:hover | Selects links on mouse over |
| :in-range | input:in-range | Selects `<input>` elements with a value within a specified range |
| :invalid | input:invalid | Selects all `<input>` elements with an invalid value |
| :lang(language) | p:lang(it) | Selects every `<p>` element with a lang attribute value starting with "it" |
| :last-child | p:last-child | Selects every `<p>` elements that is the last child of its parent |
| :last-of-type | p:last-of-type | Selects every `<p>` element that is the last `<p>` element of its parent |
| :link | a:link | Selects all unvisited links |
| :not(selector) | :not(p) | Selects every element that is not a `<p>` element |
| :nth-child(n) | p:nth-child(2) | Selects every `<p>` element that is the second child of its parent |
| :nth-last-child(n) | p:nth-last-child(2) | Selects every `<p>` element that is the second child of its parent, counting from the last child |
| :nth-last-of-type(n) | p:nth-last-of-type(2) | Selects every `<p>` element that is the second `<p>` element of its parent, counting from the last child |
| :nth-of-type(n) | p:nth-of-type(2) | Selects every `<p>` element that is the second `<p>` element of its parent |
| :only-of-type | p:only-of-type | Selects every `<p>` element that is the only `<p>` element of its parent |
| :only-child | p:only-child | elects every `<p>` element that is the only child of its parent |
| :optional | input:optional | Selects `<input>` elements with no "required" attribute |
| :out-of-range | input:out-of-range | Selects `<input>` elements with a value outside a specified range |
| :read-only | input:read-only | Selects `<input>` elements with a "readonly" attribute specified |
| :read-write | input:read-write | Selects `<input>` elements with no "readonly" attribute |
| :required | input:required | Selects `<input>` elements with a "required" attribute specified |
| :root | root | Selects the document's root element |
| :target | #news:target | Selects the current active #news element (clicked on a URL containing that anchor name) |
| :valid | input:valid | Selects all `<input>` elements with a valid value |
| :visited | a:visited | Selects all visited links |

**Anchor Pseudo-classes**:  
Links can be displayed in different ways:

```css
/* unvisited link */
a:link {
  color: #FF0000;
}

/* visited link */
a:visited {
  color: #00FF00;
}

/* mouse over link */
a:hover {
  color: #FF00FF;
}

/* selected link */
a:active {
  color: #0000FF;
}
```

Note:  
`a:hover` MUST come after `a:link` and `a:visited` in the CSS definition in order to be effective!  
`a:active` MUST come after `a:hover` in the CSS definition in order to be effective!  
Pseudo-class names are not case-sensitive.  

**Pseudo-classes and HTML Classes**:  
Pseudo-classes can be combined with HTML classes:  
When you hover over the link in the example, it will change color:

```css
a.highlight:hover {
  color: #ff0000;
}
```

**Hover on `<div>`**:  
An example of using the :hover pseudo-class on a `<div>` element:

```css
div:hover {
  background-color: blue;
}
```

**Simple Tooltip Hover**:  
Hover over a `<div>` element to show a `<p>` element (like a tooltip):

```css
p {
  display: none;
  background-color: yellow;
  padding: 20px;
}

div:hover p {
  display: block;
}
```

**CSS - The :first-child Pseudo-class**:  
The :first-child pseudo-class matches a specified element that is the first child of another element.  

* Match the first `<p>` element:  
In the following example, the selector matches any `<p>` element that is the first child of any element:

```css
p:first-child {
  color: blue;
}
```

* Match the first `<i>` element in all `<p>` elements:  
In the following example, the selector matches the first `<i>` element in all `<p>` elements:

```css
p i:first-child {
  color: blue;
}
```

* Match all `<i>` elements in all first child `<p>` elements
In the following example, the selector matches all `<i>` elements in `<p>` elements that are the first child of another element:

```css
p:first-child i {
  color: blue;
}
```

**CSS - The :lang Pseudo-class**:  
The :lang pseudo-class allows you to define special rules for different languages.  
In the example below, :lang defines the quotation marks for `<q>` elements with lang="no":

```css
<html>
<head>
<style>
q:lang(no) {
  quotes: "~" "~";
}
</style>
</head>
<body>

<p>Some text <q lang="no">A quote in a paragraph</q> Some text.</p>

</body>
</html>
```

### CSS Pseudo-elements

A CSS pseudo-element is used to style specified parts of an element.  
For example, it can be used to:

* Style the first letter, or line, of an element
* Insert content before, or after, the content of an element

**Syntax**:  
The syntax of pseudo-elements:

```css
selector::pseudo-element {
  property: value;
}
```

**All CSS Pseudo Elements**:  

| Selector | Example | Example description |
| ::after | p::after | Insert content after every `<p>` element |
| ::before | p::before | Insert content before every `<p>` element |
| ::first-letter | p::first-letter | Selects the first letter of every `<p>` element |
| ::first-line | p::first-line | Selects the first line of every `<p>` element |
| ::selection | p::selection | Selects the portion of an element that is selected by a user |

**Pseudo-elements and HTML Classes**:  
Pseudo-elements can be combined with HTML classes:  
The example will display the first letter of paragraphs with class="intro", in red and in a larger size.

```css
p.intro::first-letter {
  color: #ff0000;
  font-size: 200%;
}
```

**Multiple Pseudo-elements**:  
Several pseudo-elements can also be combined.  
In the following example, the first letter of a paragraph will be red, in an xx-large font size. The rest of the first line will be blue, and in small-caps. The rest of the paragraph will be the default font size and color:

```css
p::first-letter {
  color: #ff0000;
  font-size: xx-large;
}

p::first-line {
  color: #0000ff;
  font-variant: small-caps;
}
```

**The ::first-line Pseudo-element**:  
The ::first-line pseudo-element is used to add a special style to the first line of a text.  
The following example formats the first line of the text in all `<p>` elements:

```css
p::first-line {
  color: #ff0000;
  font-variant: small-caps;
}
```

Note: The ::first-line pseudo-element can only be applied to block-level elements.  
The following properties apply to the ::first-line pseudo-element:

* font properties
* color properties
* background properties
* word-spacing
* letter-spacing
* text-decoration
* vertical-align
* text-transform
* line-height
* clear

**The ::first-letter Pseudo-element**:  
The ::first-letter pseudo-element is used to add a special style to the first letter of a text.  
The following example formats the first letter of the text in all `<p>` elements:

```css
p::first-letter {
  color: #ff0000;
  font-size: xx-large;
}
```

Note: The ::first-letter pseudo-element can only be applied to block-level elements.  
The following properties apply to the ::first-letter pseudo- element:

* font properties
* color properties
* background properties
* margin properties
* padding properties
* border properties
* text-decoration
* vertical-align (only if "float" is "none")
* text-transform
* line-height
* float
* clear

**CSS - The ::before Pseudo-element**:  
The ::before pseudo-element can be used to insert some content before the content of an element.  
The following example inserts an image before the content of each `<h1>` element:  

```css
h1::before {
  content: url(smiley.gif);
}
```

**CSS - The ::after Pseudo-element**:  
The ::after pseudo-element can be used to insert some content after the content of an element.  
The following example inserts an image after the content of each `<h1>` element:

```css
h1::after {
  content: url(smiley.gif);
}
```

**CSS - The ::marker Pseudo-element**:  
The ::marker pseudo-element selects the markers of list items.  
The following example styles the markers of list items:

```css
::marker {
  color: red;
  font-size: 23px;
}
```

**CSS - The ::selection Pseudo-element**:  
The ::selection pseudo-element matches the portion of an element that is selected by a user.  
The following CSS properties can be applied to ::selection: color, background, cursor, and outline.

The following example makes the selected text red on a yellow background:

```css
::selection {
  color: red;
  background: yellow;
}
```

### CSS Attribute Selectors

It is possible to style HTML elements that have specific attributes or attribute values.

**All CSS Attribute Selectors**:  

| Selector | Example | Example description |
| [attribute] | [target] | Selects all elements with a target attribute |
| [attribute=value] | [target=_blank] | Selects all elements with target="_blank" |
| [attribute~=value] | [title~=flower] | Selects all elements with a title attribute containing the word "flower" |
| [attribute|=value] | [lang|=en] | Selects all elements with a lang attribute value starting with "en" |
| [attribute^=value] | a[href^="https"] | Selects every `<a>` element whose href attribute value begins with "https" |
| [attribute$=value] | a[href$=".pdf"] | Selects every `<a>` element whose href attribute value ends with ".pdf" |
| [attribute*=value] | a[href*="w3schools"] | Selects every `<a>` element whose href attribute value contains the substring "w3schools" |

**CSS `[attribute]` Selector**:  
The `[attribute]` selector is used to select elements with a specified attribute.  
The following example selects all `<a>` elements with a target attribute:

```css
a[target] {
  background-color: yellow;
}
```

**CSS `[attribute="value"]` Selector**:  
The `[attribute="value"]` selector is used to select elements with a specified attribute and value.  
The following example selects all `<a>` elements with a target="_blank" attribute:

```css
a[target="_blank"] {
  background-color: yellow;
}
```

**CSS `[attribute~="value"]` Selector**:  
The `[attribute~="value"]` selector is used to select elements with an attribute value containing a specified word.  
The following example selects all elements with a `title` attribute that contains a space-separated list of words, one of which is "flower":  
The example above will match elements with title="flower", title="summer flower", and title="flower new", but not title="my-flower" or title="flowers".

```css
[title~="flower"] {
  border: 5px solid yellow;
}
```

**CSS `[attribute|="value"]` Selector**:  
The `[attribute|="value"]` selector is used to select elements with the specified attribute, whose value can be exactly the specified value, or the specified value followed by a hyphen (-).  
Note: The value has to be a whole word, either alone, like class="top", or followed by a hyphen( - ), like class="top-text".  

```css
[class|="top"] {
  background: yellow;
}
```

**CSS `[attribute^="value"]` Selector**:  
The `[attribute^="value"]` selector is used to select elements with the specified attribute, whose value starts with the specified value.  
The following example selects all elements with a class attribute value that starts with "top":  
Note: The value does not have to be a whole word!  

```css
[class^="top"] {
  background: yellow;
}
```

**CSS `[attribute$="value"]` Selector**:  
The `[attribute$="value"]` selector is used to select elements whose attribute value ends with a specified value.  
The following example selects all elements with a class attribute value that ends with "test":  
Note: The value does not have to be a whole word!  

```css
[class$="test"] {
  background: yellow;
}
```

**CSS `[attribute*="value"]` Selector**:  
The `[attribute*="value"]` selector is used to select elements whose attribute value contains a specified value.  
The following example selects all elements with a class attribute value that contains "te":  
Note: The value does not have to be a whole word!  

```css
[class*="te"] {
  background: yellow;
}
```

## Ways to Insert CSS

There are three ways of inserting a style sheet:

* External CSS
* Internal CSS
* Inline CSS

**External CSS**:  
With an external style sheet, you can change the look of an entire website by changing just one file!  
Each HTML page must include a reference to the external style sheet file inside the `<link>` element, inside the head section.

```css
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
```

Note: Do not add a space between the property value and the unit:
Incorrect (space): margin-left: 20 px;
Correct (nospace): margin-left: 20px;

**Internal CSS**:  
An internal style sheet may be used if one single HTML page has a unique style.  
The internal style is defined inside the `<style>` element, inside the `head` section.

```css
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
```

**Inline CSS**:  
An inline style may be used to apply a unique style for a single element.  
To use inline styles, add the style attribute to the relevant element.  
The style attribute can contain any CSS property.

```css
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```

**Multiple Style Sheets**:  
If some properties have been defined for the same selector (element) in different style sheets, the value from the last read style sheet will be used. 

**Cascading Order**:  
What style will be used when there is more than one style specified for an HTML element?

All the styles in a page will "cascade" into a new "virtual" style sheet by the following rules, where number one has the highest priority:

Inline style (inside an HTML element)
External and internal style sheets (in the head section)
Browser default
So, an inline style has the highest priority, and will override external and internal styles and browser defaults.

## CSS Comments

Comments are used to explain the code, and may help when you edit the source code at a later date.  
Comments are ignored by browsers.

A CSS comment is placed inside the `<style>` element, and starts with `/*` and ends with `*/`:

```css
/* This is a single-line comment */
p {
  color: red;
}
/* This is
a multi-line
comment */
```

**HTML and CSS Comments**:  
From the HTML tutorial, you learned that you can add comments to your HTML source by using the `<!--...-->` syntax.  
In the following example, we use a combination of HTML and CSS comments:

```html
<!DOCTYPE html>
<html>
<head>
<style>
p {
  color: red; /* Set text color to red */
}
</style>
</head>
<body>

<h2>My Heading</h2>

<!-- These paragraphs will be red -->
<p>Hello World!</p>
<p>This paragraph is styled with CSS.</p>
<p>CSS comments are not shown in the output.</p>

</body>
</html>
```

## CSS Colors

Colors are specified using predefined color names, or RGB, HEX, HSL, RGBA, HSLA values.

**CSS Background Color**:  

```html
<h1 style="background-color:DodgerBlue;">Hello World</h1>
<p style="background-color:Tomato;">Lorem ipsum...</p>
```

**CSS Text Color**:  

```html
<h1 style="color:Tomato;">Hello World</h1>
<p style="color:DodgerBlue;">Lorem ipsum...</p>
<p style="color:MediumSeaGreen;">Ut wisi enim...</p>
```

**CSS Border Color**:  

```html
<h1 style="border:2px solid Tomato;">Hello World</h1>
<h1 style="border:2px solid DodgerBlue;">Hello World</h1>
<h1 style="border:2px solid Violet;">Hello World</h1>
```

**CSS Color Values**:  
In CSS, colors can also be specified using:

* RGB values - (red, green, and blue) defines the intensity of the color with a value between 0 and 255.
* RGBA values - (red, green, blue and alpha) extension of RGB color values with an Alpha channel - which specifies the opacity for a color.
* HEX values - rr (red), gg (green) and bb (blue) are hexadecimal values between 00 and ff (same as decimal 0-255).
* HSL values - hue (degree on the color wheel from 0 to 360), saturation (the intensity of a color - 100% is pure color), and lightness (how much light you want to give the color, where 0% means no light (black))
* HSLA values - (hue, saturation, lightness, alpha) an extension of HSL color values with an Alpha channel - which specifies the opacity for a color.

Same as color name "Tomato":  

* rgb(255, 99, 71)
* #ff6347
* hsl(9, 100%, 64%)

Same as color name "Tomato", but 50% transparent:

* rgba(255, 99, 71, 0.5)
* hsla(9, 100%, 64%, 0.5)

```html
<h1 style="background-color:rgb(255, 99, 71);">...</h1>
<h1 style="background-color:#ff6347;">...</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">...</h1>

<h1 style="background-color:rgba(255, 99, 71, 0.5);">...</h1>
<h1 style="background-color:hsla(9, 100%, 64%, 0.5);">...</h1>
```

## CSS Backgrounds

The CSS background properties are used to add background effects for elements.  

**All CSS Background Properties**:  

| Property | Description |
| background | Sets all the background properties in one declaration |
| background-attachment | Sets whether a background image is fixed or scrolls with the rest of the page |
| background-clip | Specifies the painting area of the background |
| background-color | Sets the background color of an element |
| background-image | Sets the background image for an element |
| background-origin | Specifies where the background image(s) is/are positioned |
| background-position | Sets the starting position of a background image |
| background-repeat | Sets how a background image will be repeated |
| background-size | Specifies the size of the background image(s) |

### CSS background-color

You can set the background color for any HTML elements:

```css
h1 {
  background-color: green;
}

div {
  background-color: lightblue;
}

p {
  background-color: yellow;
}
```

**Opacity / Transparency**:  
The opacity property specifies the opacity/transparency of an element.  
It can take a value from 0.0 - 1.0. The lower value, the more transparent.  

```css
div {
  background-color: green;
  opacity: 0.3;
}
```

Note: When using the opacity property to add transparency to the background of an element, all of its child elements inherit the same transparency.  
This can make the text inside a fully transparent element hard to read.

If you do not want to apply opacity to child elements, like in our example above, use RGBA color values.  
The following example sets the opacity for the background color and not the text:

```css
div {
  background: rgba(0, 128, 0, 0.3) /* Green background with 30% opacity */
}
```

### CSS background-image

The background-image property specifies an image to use as the background of an element.  
By default, the image is repeated so it covers the entire element.

```css
body {
  background-image: url("paper.gif");
}
```

The background image can also be set for specific elements, like the `<p>` element:

```css
p {
    background-image: url("paper.gif");
}
```

### CSS Background Image Repeat

By default, the background-image property repeats an image both horizontally and vertically.  
Some images should be repeated only horizontally or vertically, or they will look strange.

If the image above is repeated only horizontally (background-repeat: repeat-x;):

```css
body {
  background-image: url("gradient_bg.png");
  background-repeat: repeat-x;
}
```

Tip: To repeat an image vertically, set `background-repeat: repeat-y;`

Showing the background image only once is also specified by the background-repeat property:

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
}
```

### CSS background-position

The background-position property is used to specify the position of the background image.

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```

### CSS background-attachment

The background-attachment property specifies whether the background image should scroll or be fixed (will not scroll with the rest of the page):

Specify that the background image should be fixed:

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: fixed;
}
```

Specify that the background image should scroll with the rest of the page:

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: scroll;
}
```

### CSS background - Shorthand property

To shorten the code, it is also possible to specify all the background properties in one single property.  
This is called a shorthand property.  

```css
body {
  background: #ffffff url("img_tree.png") no-repeat right top;
}
```

When using the shorthand property the order of the property values is:

* background-color
* background-image
* background-repeat
* background-attachment
* background-position

It does not matter if one of the property values is missing, as long as the other ones are in this order.  
Note that we do not use the background-attachment property in the examples above, as it does not have a value.

## CSS Borders

The CSS border properties allow you to specify the style, width, and color of an element's border.

**All CSS Border Properties**:  
| Property | Description
| border | Sets all the border properties in one declaration |
| border-bottom | Sets all the bottom border properties in one declaration |
| border-bottom-color | Sets the color of the bottom border |
| border-bottom-style | Sets the style of the bottom border |
| border-bottom-width | Sets the width of the bottom border |
| border-color | Sets the color of the four borders |
| border-left | Sets all the left border properties in one declaration |
| border-left-color | Sets the color of the left border |
| border-left-style | Sets the style of the left border |
| border-left-width | Sets the width of the left border |
| border-radius | Sets all the four border-*-radius properties for rounded corners |
| border-right | Sets all the right border properties in one declaration |
| border-right-color | Sets the color of the right border |
| border-right-style | Sets the style of the right border |
| border-right-width | Sets the width of the right border |
| border-style | Sets the style of the four borders |
| border-top | Sets all the top border properties in one declaration |
| border-top-color | Sets the color of the top border |
| border-top-style | Sets the style of the top border |
| border-top-width | Sets the width of the top border |
| border-width | Sets the width of the four borders |

### CSS Border Style

The border-style property specifies what kind of border to display.
Note: None of the OTHER CSS border properties will have ANY effect unless the border-style property is set!  

The following values are allowed:

* dotted - Defines a dotted border
* dashed - Defines a dashed border
* solid - Defines a solid border
* double - Defines a double border
* groove - Defines a 3D grooved border. The effect depends on the border-color value
* ridge - Defines a 3D ridged border. The effect depends on the border-color value
* inset - Defines a 3D inset border. The effect depends on the border-color value
* outset - Defines a 3D outset border. The effect depends on the border-color value
* none - Defines no border
* hidden - Defines a hidden border

**Specific Side Styles**:  
The border-style property can have from one to four values (for the top border, right border, bottom border, and the left border).

```html
<!DOCTYPE html>
<html>
<head>
<style>
p.dotted {border-style: dotted;}
p.dashed {border-style: dashed;}
p.solid {border-style: solid;}
p.double {border-style: double;}
p.groove {border-style: groove;}
p.ridge {border-style: ridge;}
p.inset {border-style: inset;}
p.outset {border-style: outset;}
p.none {border-style: none;}
p.hidden {border-style: hidden;}
p.mix {border-style: dotted dashed solid double;}
</style>
</head>
<body>

<h2>The border-style Property</h2>
<p>This property specifies what kind of border to display:</p>

<p class="dotted">A dotted border.</p>
<p class="dashed">A dashed border.</p>
<p class="solid">A solid border.</p>
<p class="double">A double border.</p>
<p class="groove">A groove border.</p>
<p class="ridge">A ridge border.</p>
<p class="inset">An inset border.</p>
<p class="outset">An outset border.</p>
<p class="none">No border.</p>
<p class="hidden">A hidden border.</p>
<p class="mix">A mixed border.</p>

</body>
</html>
```

### CSS Border Width

The border-width property specifies the width of the four borders.  
The width can be set as a specific size (in px, pt, cm, em, etc) or by using one of the three pre-defined values: thin, medium, or thick:

```html
p.one {
  border-style: solid;
  border-width: 5px;
}

p.two {
  border-style: solid;
  border-width: medium;
}

p.three {
  border-style: dotted;
  border-width: 2px;
}

p.four {
  border-style: dotted;
  border-width: thick;
}
```

**Specific Side Widths**:  
The border-width property can have from one to four values (for the top border, right border, bottom border, and the left border):

```html
p.one {
  border-style: solid;
  border-width: 5px 20px; /* 5px top and bottom, 20px on the sides */
}

p.two {
  border-style: solid;
  border-width: 20px 5px; /* 20px top and bottom, 5px on the sides */
}

p.three {
  border-style: solid;
  border-width: 25px 10px 4px 35px; /* 25px top, 10px right, 4px bottom and 35px left */
}
```

### CSS Border Color

The border-color property is used to set the color of the four borders.

The color can be set by:

* name - specify a color name, like "red"
* HEX - specify a HEX value, like "#ff0000"
* RGB - specify a RGB value, like "rgb(255,0,0)"
* HSL - specify a HSL value, like "hsl(0, 100%, 50%)"
* transparent

Note: If border-color is not set, it inherits the color of the element.

```css
p.one {
  border-style: solid;
  border-color: red;
}

p.two {
  border-style: solid;
  border-color: green;
}

p.three {
  border-style: dotted;
  border-color: blue;
}
```

**Specific Side Colors**:  
The border-color property can have from one to four values (for the top border, right border, bottom border, and the left border).

```css
p.one {
  border-style: solid;
  border-color: red green blue yellow; /* red top, green right, blue bottom and yellow left */
}
```

### CSS Border - Individual Sides

It is possible to specify a different border for each side.  
In CSS, there are also properties for specifying each of the borders (top, right, bottom, and left):

```css
p {
  border-top-style: dotted;
  border-right-style: solid;
  border-bottom-style: dotted;
  border-left-style: solid;
}
```

The example above gives the same result as this:

```css
p {
  border-style: dotted solid;
}
```

So, here is how it works:

If the border-style property has four values - `border-style: dotted solid double dashed;`

* top border is dotted
* right border is solid
* bottom border is double
* left border is dashed

If the border-style property has three values - `border-style: dotted solid double;`

* top border is dotted
* right and left borders are solid
* bottom border is double

If the border-style property has two values - `border-style: dotted solid;`

* top and bottom borders are dotted
* right and left borders are solid

If the border-style property has one value - `border-style: dotted;`

* all four borders are dotted

The border-style property is used in the example above.  
However, it also works with border-width and border-color.

### CSS Border - Shorthand Property

Like you saw in the previous page, there are many properties to consider when dealing with borders.  
To shorten the code, it is also possible to specify all the individual border properties in one property.  
The border property is a shorthand property for the following individual border properties:

* border-width
* border-style (required)
* border-color

```css
p {
  border: 5px solid red;
}
```

```css
p {
  border-left: 6px solid red;
  background-color: lightgrey;
}
```

### CSS Rounded Borders

The border-radius property is used to add rounded borders to an element:

```css
p {
  border: 2px solid red;
  border-radius: 5px;
}
```

## CSS Margins

Margins are used to create space around elements, outside of any defined borders.

**All CSS Margin Properties**:  

| Property | Description |
| margin | A shorthand property for setting the margin properties in one declaration |
| margin-bottom | Sets the bottom margin of an element |
| margin-left | Sets the left margin of an element |
| margin-right | Sets the right margin of an element |
| margin-top | Sets the top margin of an element |

**Margin - Individual Sides**:  
CSS has properties for specifying the margin for each side of an element:

* margin-top
* margin-right
* margin-bottom
* margin-left

All the margin properties can have the following values:

* auto - the browser calculates the margin
* length - specifies a margin in px, pt, cm, etc.
* % - specifies a margin in % of the width of the containing element
* inherit - specifies that the margin should be inherited from the parent element

Tip: Negative values are allowed.

```css
p {
  margin-top: 100px;
  margin-bottom: 100px;
  margin-right: 150px;
  margin-left: 80px;
}
```

**Margin - Shorthand Property**:  
To shorten the code, it is possible to specify all the margin properties in one property.  
So, here is how it works:

```css
p {
  margin: 25px 50px 75px 100px;
}
```

If the margin property has four values: - `margin: 25px 50px 75px 100px;`

* top margin is 25px
* right margin is 50px
* bottom margin is 75px
* left margin is 100px

If the margin property has three values - `margin: 25px 50px 75px;`

* top margin is 25px
* right and left margins are 50px
* bottom margin is 75px

If the margin property has two values - `margin: 25px 50px;`

* top and bottom margins are 25px
* right and left margins are 50px

If the margin property has one value - `margin: 25px;`

* all four margins are 25px

**The auto Value**:  
You can set the margin property to auto to horizontally center the element within its container.  
The element will then take up the specified width, and the remaining space will be split equally between the left and right margins.

```css
div {
  width: 300px;
  margin: auto;
  border: 1px solid red;
}
```

**The inherit Value**:  
This example lets the left margin of the `<p class="ex1">` element be inherited from the parent element (`<div>`):

```css
div {
  border: 1px solid red;
  margin-left: 100px;
}

p.ex1 {
  margin-left: inherit;
}
```

**CSS Margin Collapse**:  
Top and bottom margins of elements are sometimes collapsed into a single margin that is equal to the largest of the two margins.  
This does not happen on left and right margins! Only top and bottom margins!  

Look at the following example:

```css
h1 {
  margin: 0 0 50px 0;
}

h2 {
  margin: 20px 0 0 0;
}
```

In the example above, the `<h1>` element has a bottom margin of 50px and the `<h2>` element has a top margin set to 20px.  
Common sense would seem to suggest that the vertical margin between the `<h1>` and the `<h2>` would be a total of 70px (50px + 20px).  
But due to margin collapse, the actual margin ends up being 50px.

## CSS Padding

Padding is used to create space around an element's content, inside of any defined borders.

**All CSS Padding Properties**:  

| Property | Description |
| padding | A shorthand property for setting all the padding properties in one declaration |
| padding-bottom | Sets the bottom padding of an element |
| padding-left | Sets the left padding of an element |
| padding-right | Sets the right padding of an element |
| padding-top | Sets the top padding of an element |

**Padding - Individual Sides**:  
CSS has properties for specifying the padding for each side of an element:

* padding-top
* padding-right
* padding-bottom
* padding-left

All the padding properties can have the following values:

* length - specifies a padding in px, pt, cm, etc.
* % - specifies a padding in % of the width of the containing element
* inherit - specifies that the padding should be inherited from the parent element

Note: Negative values are not allowed.

**Padding - Shorthand Property**:  
To shorten the code, it is possible to specify all the padding properties in one property.  
So, here is how it works:

```css
div {
  padding: 25px 50px 75px 100px;
}
```

If the padding property has four values - `padding: 25px 50px 75px 100px;`

* top padding is 25px
* right padding is 50px
* bottom padding is 75px
* left padding is 100px

If the padding property has three values - `padding: 25px 50px 75px;`

* top padding is 25px
* right and left paddings are 50px
* bottom padding is 75px

If the padding property has two values - `padding: 25px 50px;`

* top and bottom paddings are 25px
* right and left paddings are 50px

If the padding property has one value `padding: 25px;`

* all four paddings are 25px

**Padding and Element Width**:  
The CSS width property specifies the width of the element's content area.  
The content area is the portion inside the padding, border, and margin of an element (the box model).

So, if an element has a specified width, the padding added to that element will be added to the total width of the element.  
This is often an undesirable result.

Example
Here, the `<div>` element is given a width of 300px.  
However, the actual width of the `<div>` element will be 350px (300px + 25px of left padding + 25px of right padding):

```css
div {
  width: 300px;
  padding: 25px;
}
```

To keep the width at 300px, no matter the amount of padding, you can use the `box-sizing` property.  
This causes the element to maintain its actual width; if you increase the padding, the available content space will decrease.

```css
div {
  width: 300px;
  padding: 25px;
  box-sizing: border-box;
}
```

## CSS Height and Width

The CSS height and width properties are used to set the height and width of an element.  
The CSS max-width property is used to set the maximum width of an element.

The height and width properties do not include padding, borders, or margins.  
It sets the height/width of the area inside the padding, border, and margin of the element.

**All CSS Dimension Properties**:  

| Property | Description |
| height | Sets the height of an element |
| max-height | Sets the maximum height of an element |
| max-width | Sets the maximum width of an element |
| min-height | Sets the minimum height of an element |
| min-width | Sets the minimum width of an element |
| width | Sets the width of an element |

**CSS height and width Values**:  
The height and width properties may have the following values:

* auto - This is default. The browser calculates the height and width
* length - Defines the height/width in px, cm etc.
* % - Defines the height/width in percent of the containing block
* initial - Sets the height/width to its default value
* inherit - The height/width will be inherited from its parent value

**Setting max-width**:  
The max-width property is used to set the maximum width of an element.  
The max-width can be specified in length values, like px, cm, etc., or in percent (%) of the containing block, or set to none (this is default. Means that there is no maximum width).  

The problem with the `<div>` above occurs when the browser window is smaller than the width of the element (500px).  
The browser then adds a horizontal scrollbar to the page.  
Using max-width instead, in this situation, will improve the browser's handling of small windows.

Note: If you for some reason use both the width property and the max-width property on the same element, and the value of the width property is larger than the max-width property; the max-width property will be used (and the width property will be ignored).  

```html
<style>
img.one {
  height: auto;
}

img.two {
  height: 200px;
  width: 200px;
}

div.three {
  height: 300px;
  width: 300px;
  background-color: powderblue;
}
</style>
```

## The CSS Box Model

In CSS, the term "box model" is used when talking about design and layout.  
The CSS box model is essentially a box that wraps around every HTML element.  
It consists of: margins, borders, padding, and the actual content.  

Explanation of the different parts:

* **Content** - The content of the box, where text and images appear
* **Padding** - Clears an area around the content. The padding is transparent
* **Border** - A border that goes around the padding and content
* **Margin** - Clears an area outside the border. The margin is transparent

The box model allows us to add a border around elements, and to define space between elements. 

**Width and Height of an Element**:  
In order to set the width and height of an element correctly in all browsers, you need to know how the box model works.  
Important: When you set the width and height properties of an element with CSS, you just set the width and height of the content area. To calculate the full size of an element, you must also add padding, borders and margins.

Example:  
This `<div>` element will have a total width of 350px: 

```css
div {
  width: 320px;
  padding: 10px;
  border: 5px solid gray;
  margin: 0;
}
```

*The total width of an element should be calculated like this*:  
Total element width = width + left padding + right padding + left border + right border + left margin + right margin

*The total height of an element should be calculated like this*:  
Total element height = height + top padding + bottom padding + top border + bottom border + top margin + bottom margin

## CSS Outline

An outline is a line that is drawn around elements, OUTSIDE the borders, to make the element "stand out".

**All CSS Outline Properties**:  

| Property | Description |
| outline | A shorthand property for setting outline-width, outline-style, and outline-color in one declaration |
| outline-color | Sets the color of an outline |
| outline-offset | Specifies the space between an outline and the edge or border of an element |
| outline-style | Sets the style of an outline |
| outline-width | Sets the width of an outline |

**CSS has the following outline properties:**

* outline-style
* outline-color
* outline-width
* outline-offset
* outline

Note: Outline differs from borders!  
Unlike border, the outline is drawn outside the element's border, and may overlap other content.  
Also, the outline is NOT a part of the element's dimensions; the element's total width and height is not affected by the width of the outline.

**CSS Outline Style**:  
The outline-style property specifies the style of the outline, and can have one of the following values:
Note: None of the other outline properties (which you will learn more about in the next chapters) will have ANY effect unless the outline-style property is set!

* dotted - Defines a dotted outline
* dashed - Defines a dashed outline
* solid - Defines a solid outline
* double - Defines a double outline
* groove - Defines a 3D grooved outline
* ridge - Defines a 3D ridged outline
* inset - Defines a 3D inset outline
* outset - Defines a 3D outset outline
* none - Defines no outline
* hidden - Defines a hidden outline

The following example shows the different outline-style values:

```css
p.dotted {outline-style: dotted;}
p.dashed {outline-style: dashed;}
p.solid {outline-style: solid;}
p.double {outline-style: double;}
p.groove {outline-style: groove;}
p.ridge {outline-style: ridge;}
p.inset {outline-style: inset;}
p.outset {outline-style: outset;}
```

**CSS Outline Width**:  
The outline-width property specifies the width of the outline, and can have one of the following values:

* thin (typically 1px)
* medium (typically 3px)
* thick (typically 5px)
* A specific size (in px, pt, cm, em, etc)

```css
p.ex1 {
  border: 1px solid black;
  outline-style: solid;
  outline-color: red;
  outline-width: thin;
}
```

**CSS Outline Color**:  
The outline-color property is used to set the color of the outline.  
The color can be set by:

* name - specify a color name, like "red"
* HEX - specify a hex value, like "#ff0000"
* RGB - specify a RGB value, like "rgb(255,0,0)"
* HSL - specify a HSL value, like "hsl(0, 100%, 50%)"
* invert - performs a color inversion (which ensures that the outline is visible, regardless of color background)

```css
p.ex1 {
  border: 2px solid black;
  outline-style: solid;
  outline-color: red;
}
```

**CSS Outline - Shorthand property**:  
The outline property is a shorthand property for setting the following individual outline properties:

* outline-width
* outline-style (required)
* outline-color

The outline property is specified as one, two, or three values from the list above.  
The order of the values does not matter.

```css
p.ex1 {outline: dashed;}
p.ex2 {outline: dotted red;}
p.ex3 {outline: 5px solid yellow;}
p.ex4 {outline: thick ridge pink;}
```

**CSS Outline Offset**:  
The outline-offset property adds space between an outline and the edge/border of an element.  
The space between an element and its outline is transparent.  

```css
p {
  margin: 30px;
  background: yellow;
  border: 1px solid black;
  outline: 1px solid red;
  outline-offset: 15px;
}
```

## CSS Text

**All CSS Text Properties**:  
| Property | Description |
| color | Sets the color of text |
| direction | Specifies the text direction/writing direction |
| letter-spacing | Increases or decreases the space between characters in a text |
| line-height | Sets the line height |
| text-align | Specifies the horizontal alignment of text |
| text-align-last | Specifies how to align the last line of a text |
| text-decoration | Specifies the decoration added to text |
| text-indent | Specifies the indentation of the first line in a text-block |
| text-justify | Specifies how justified text should be aligned and spaced |
| text-overflow | Specifies how overflowed content that is not displayed should be signaled to the user |
| text-shadow | Specifies the shadow effect added to text |
| text-transform | Controls the capitalization of text |
| unicode-bidi | Used together with the direction property to set or return whether the text should be overridden to support multiple languages in the same document |
| vertical-align | Sets the vertical alignment of an element |
| white-space | Specifies how white-space inside an element is handled |
| word-spacing | Increases or decreases the space between words in a text |

### Text Color

The color property is used to set the color of the text.  
The color is specified by:

* a color name - like "red"
* a HEX value - like "#ff0000"
* an RGB value - like "rgb(255,0,0)"

The default text color for a page is defined in the body selector.

```css
body {
  color: blue;
}

h1 {
  color: green;
}
```

**Text Color and Background Color**:  
In this example, we define both the background-color property and the color property:

```css
body {
  background-color: lightgrey;
  color: blue;
}

h1 {
  background-color: black;
  color: white;
}

div {
  background-color: blue;
  color: white;
}
```

### Text Alignment

The text-align property is used to set the horizontal alignment of a text.  
A text can be left or right aligned, centered, or justified.  

The following example shows center aligned, and left and right aligned text (left alignment is default if text direction is left-to-right, and right alignment is default if text direction is right-to-left):

```css
h1 {
  text-align: center;
}

h2 {
  text-align: left;
}

h3 {
  text-align: right;
}
```

When the text-align property is set to "justify", each line is stretched so that every line has equal width, and the left and right margins are straight (like in magazines and newspapers):

```css
div {
  text-align: justify;
}
```

**Text Align Last**
The text-align-last property specifies how to align the last line of a text.

```css
p.a {
  text-align-last: right;
}

p.b {
  text-align-last: center;
}

p.c {
  text-align-last: justify;
}
```

### CSS Text Decoration

The text-decoration property is used to set or remove decorations from text.  
The value text-decoration: none; is often used to remove underlines from links:

```css
a {
  text-decoration: none;
}
```

The other text-decoration values are used to decorate text:

```css
h2 {
  text-decoration: overline;
}

h3 {
  text-decoration: line-through;
}

h4 {
  text-decoration: underline;
}
```

Note: It is not recommended to underline text that is not a link, as this often confuses the reader.

### CSS Text Transformation

The text-transform property is used to specify uppercase and lowercase letters in a text.  
It can be used to turn everything into uppercase or lowercase letters, or capitalize the first letter of each word:

```css
p.uppercase {
  text-transform: uppercase;
}

p.lowercase {
  text-transform: lowercase;
}

p.capitalize {
  text-transform: capitalize;
}
```

### CSS Text Spacing

**Text Indentation**:  
The text-indent property is used to specify the indentation of the first line of a text:

```css
p {
  text-indent: 50px;
}
```

**Letter Spacing**:  
The letter-spacing property is used to specify the space between the characters in a text.  
The following example demonstrates how to increase or decrease the space between characters:  

```css
h1 {
  letter-spacing: 5px;
}

h2 {
  letter-spacing: -2px;
}
```

**Line Height**:  
The line-height property is used to specify the space between lines:

```css
p.small {
  line-height: 0.8;
}

p.big {
  line-height: 1.8;
}
```

**Word Spacing**:  
The word-spacing property is used to specify the space between the words in a text.  
The following example demonstrates how to increase or decrease the space between words:

```css
p.one {
  word-spacing: 10px;
}

p.two {
  word-spacing: -2px;
}
```

**White Space**:  
The white-space property specifies how white-space inside an element is handled.  
This example demonstrates how to disable text wrapping inside an element:

```css
p {
  white-space: nowrap;
}
```

### CSS Text Shadow

The text-shadow property adds shadow to text.  
In its simplest use, you only specify the horizontal shadow (2px) and the vertical shadow (2px):

```css
h1 {
  text-shadow: 2px 2px;
}
```

Next, add a color (red) to the shadow:

```css
h1 {
  text-shadow: 2px 2px red;
}
```

Then, add a blur effect (5px) to the shadow:

```css
h1 {
  text-shadow: 2px 2px 5px red;
}
```

```css
h1 {
  color: white;
  text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
}
```

## CSS Fonts

**Generic Font Families**:  
In CSS there are five generic font families:

* Serif fonts have a small stroke at the edges of each letter. They create a sense of formality and elegance.
* Sans-serif fonts have clean lines (no small strokes attached). They create a modern and minimalistic look.
* Monospace fonts - here all the letters have the same fixed width. They create a mechanical look. 
* Cursive fonts imitate human handwriting.
* Fantasy fonts are decorative/playful fonts.

All the different font names belong to one of the generic font families. 

**The CSS font-family Property**:  
In CSS, we use the font-family property to specify the font of a text.  
Note: If the font name is more than one word, it must be in quotation marks, like: "Times New Roman".  
Tip: The font-family property should hold several font names as a "fallback" system, to ensure maximum compatibility between browsers/operating systems.  
Start with the font you want, and end with a generic family (to let the browser pick a similar font in the generic family, if no other fonts are available).

```css
.p1 {
  font-family: "Times New Roman", Times, serif;
}

.p2 {
  font-family: Arial, Helvetica, sans-serif;
}

.p3 {
  font-family: "Lucida Console", "Courier New", monospace;
}
```

### CSS Web Safe Fonts

Web safe fonts are fonts that are universally installed across all browsers and devices.

**Fallback Fonts**:  
However, there are no 100% completely web safe fonts.  
There is always a chance that a font is not found or is not installed properly.  
Therefore, it is very important to always use fallback fonts.

This means that you should add a list of similar "backup fonts" in the font-family property.  
If the first font does not work, the browser will try the next one, and the next one, and so on.  
Always end the list with a generic font family name.

Example:  
Here, there are three font types: Tahoma, Verdana, and sans-serif. The second and third fonts are backups, in case the first one is not found.

```css
p {
font-family: Tahoma, Verdana, sans-serif;
}
```

**Best Web Safe Fonts for HTML and CSS**:  
The following list are the best web safe fonts for HTML and CSS:

* Arial (sans-serif) - is the most widely used font for both online and printed media. Arial is also the default font in Google Docs.
* Verdana (sans-serif) - is a very popular font. Verdana is easily readable even for small font sizes.
* Helvetica (sans-serif) - is loved by designers. It is suitable for many types of business.
* Tahoma (sans-serif) - has less space between the characters.
* Trebuchet MS (sans-serif) - was designed by Microsoft in 1996. Use this font carefully. Not supported by all mobile operating systems.
* Times New Roman (serif) - is one of the most recognizable fonts in the world. It looks professional and is used in many newspapers and "news" websites. It is also the primary font for Windows devices and applications.
* Georgia (serif) - is an elegant serif font. It is very readable at different font sizes, so it is a good candidate for mobile-responsive design.
* Garamond (serif) - is a classical font used for many printed books. It has a timeless look and good readability.
* Courier New (monospace) - the most widely used monospace serif font. Courier New is often used with coding displays, and many email providers use it as their default font. Courier New is also the standard font for movie screenplays.
* Brush Script MT (cursive) - was designed to mimic handwriting. It is elegant and sophisticated, but can be hard to read. Use it carefully.

### CSS Font Fallbacks

**Commonly Used Font Fallbacks**:  
Below are some commonly used font fallbacks, organized by the 5 generic font families:

* Serif - ("Times New Roman", Times, serif). (Georgia, serif), (Garamond, serif)
* Sans-serif - (Arial, Helvetica, sans-serif), (Tahoma, Verdana, sans-serif), ("Trebuchet MS", Helvetica, sans-serif), (Georgia, Verdana, sans-serif)
* Monospace - ("Courier New", Courier, monospace)
* Cursive - ("Brush Script MT", cursive)
* Fantasy - (Copperplate, Papyrus, fantasy)

### CSS Font Style

**Font Style**:  
The font-style property is mostly used to specify italic text.  
This property has three values:

* normal - The text is shown normally
* italic - The text is shown in italics
* oblique - The text is "leaning" (oblique is very similar to italic, but less supported)

```css
p.normal {
  font-style: normal;
}

p.italic {
  font-style: italic;
}

p.oblique {
  font-style: oblique;
}
```

**Font Weight**:  
The font-weight property specifies the weight of a font:

```css
p.normal {
  font-weight: normal;
}

p.thick {
  font-weight: bold;
}
```

**Font Variant**:  
The font-variant property specifies whether or not a text should be displayed in a small-caps font.  
In a small-caps font, all lowercase letters are converted to uppercase letters.  
However, the converted uppercase letters appears in a smaller font size than the original uppercase letters in the text.

```css
p.normal {
  font-variant: normal;
}

p.small {
  font-variant: small-caps;
}
```

### CSS Font Size

The font-size property sets the size of the text.  
Being able to manage the text size is important in web design.  
However, you should not use font size adjustments to make paragraphs look like headings, or headings look like paragraphs.  
Always use the proper HTML tags, like `<h1>` - `<h6>` for headings and `<p>` for paragraphs.

The font-size value can be an absolute, or relative size.
*Absolute size:*

* Sets the text to a specified size
* Does not allow a user to change the text size in all browsers (bad for accessibility reasons)
* Absolute size is useful when the physical size of the output is known

*Relative size:*

* Sets the size relative to surrounding elements
* Allows a user to change the text size in browsers

Note: If you do not specify a font size, the default size for normal text, like paragraphs, is 16px (16px=1em).

**Set Font Size With Pixels**:  
Setting the text size with pixels gives you full control over the text size:

```css
h1 {
  font-size: 40px;
}

h2 {
  font-size: 30px;
}

p {
  font-size: 14px;
}
```

Tip: If you use pixels, you can still use the zoom tool to resize the entire page.

**Set Font Size With Em**:  
To allow users to resize the text (in the browser menu), many developers use em instead of pixels.  
1em is equal to the current font size.  
The default text size in browsers is 16px.  
So, the default size of 1em is 16px.

The size can be calculated from pixels to em using this formula: pixels/16=em

```css
h1 {
  font-size: 2.5em; /* 40px/16=2.5em */
}

h2 {
  font-size: 1.875em; /* 30px/16=1.875em */
}

p {
  font-size: 0.875em; /* 14px/16=0.875em */
}
```

In the example above, the text size in em is the same as the previous example in pixels.  
However, with the em size, it is possible to adjust the text size in all browsers.

Unfortunately, there is still a problem with older versions of Internet Explorer.  
The text becomes larger than it should when made larger, and smaller than it should when made smaller.

**Use a Combination of Percent and Em**:  
The solution that works in all browsers, is to set a default font-size in percent for the `<body>` element:

```css
body {
  font-size: 100%;
}

h1 {
  font-size: 2.5em;
}

h2 {
  font-size: 1.875em;
}

p {
  font-size: 0.875em;
}
```

**Responsive Font Size**:  
The text size can be set with a vw unit, which means the "viewport width".  
That way the text size will follow the size of the browser window:

```html
<h1 style="font-size:10vw">Hello World</h1>
```

Viewport is the browser window size. 1vw = 1% of viewport width.  
If the viewport is 50cm wide, 1vw is 0.5cm.

