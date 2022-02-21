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

### Google Fonts

If you do not want to use any of the standard fonts in HTML, you can use Google Fonts.  
Google Fonts are free to use, and have more than 1000 fonts to choose from.  

```html
<head>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Sofia">
<style>
body {
  font-family: "Sofia", sans-serif;
}
</style>
</head>
```

`<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Audiowide">`

**Use Multiple Google Fonts**:  
Note: Requesting multiple fonts may slow down your web pages! So be careful about that.  
To use multiple Google fonts, just separate the font names with a pipe character (|), like this:

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Audiowide|Sofia|Trirong">
<style>
h1.a {
  font-family: "Audiowide", sans-serif;
}
h1.b {
  font-family: "Sofia", sans-serif;
}
h1.c {
  font-family: "Trirong", serif;
}
</style>
</head>
<body>
<h1 class="a">Audiowide Font</h1>
<h1 class="b">Sofia Font</h1>
<h1 class="c">Trirong Font</h1>
</body>
</html>
```

**Styling Google Fonts**:  

```html
<head>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Sofia">
<style>
body {
  font-family: "Sofia", sans-serif;
  font-size: 30px;
  text-shadow: 3px 3px 3px #ababab;
}
</style>
</head>
```

**Enabling Font Effects**:  
Google have also enabled different font effects that you can use.  
First add effect=effectname to the Google API, then add a special class name to the element that is going to use the special effect.  
The class name always starts with font-effect- and ends with the effectname.

```html
<head>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Sofia&effect=fire">
<style>
body {
  font-family: "Sofia", sans-serif;
  font-size: 30px;
}
</style>
</head>
<body>

<h1 class="font-effect-fire">Sofia on Fire</h1>

</body>
```

To request multiple font effects, just separate the effect names with a pipe character (|), like this:

```html
<head>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Sofia&effect=neon|outline|emboss|shadow-multiple">
<style>
body {
  font-family: "Sofia", sans-serif;
  font-size: 30px;
}
</style>
</head>
<body>

<h1 class="font-effect-neon">Neon Effect</h1>
<h1 class="font-effect-outline">Outline Effect</h1>
<h1 class="font-effect-emboss">Emboss Effect</h1>
<h1 class="font-effect-shadow-multiple">Multiple Shadow Effect</h1>

</body>
```

### CSS Great Font Pairings

**Font Pairing Rules**:  
Here are some basic rules to create great font pairings:

1. Complement.  
It is always safe to find font pairings that complement one another.  
A great font combination should harmonize, without being too similar or too different.

2. Use Font Superfamilies.  
A font superfamily is a set of fonts designed to work well together. So, using different fonts within the same superfamily is safe.  
For example, the Lucida superfamily contains the following fonts: Lucida Sans, Lucida Serif, Lucida Typewriter Sans, Lucida Typewriter Serif and Lucida Math.

3. Contrast is King.  
Two fonts that are too similar will often conflict. However, contrasts, done the right way, brings out the best in each font.  
Example: Combining serif with sans serif is a well known combination.  
A strong superfamily includes both serif and sans serif variations of the same font (e.g. Lucida and Lucida Sans).

4. Choose Only One Boss.  
One font should be the boss. This establishes a hierarchy for the fonts on your page. This can be achieved by varying the size, weight and color.  

**Examples**:  

* Georgia and Verdana;

```html
body {
  background-color: black;
  font-family: Verdana, sans-serif;
  font-size: 16px;
  color: gray;
}

h1 {
  font-family: Georgia, serif;
  font-size: 60px;
  color: white;
}
```

* Helvetica and Garamond;

**Popular Google Font Pairings**:  

* Merriweather and Open Sans
* Ubuntu and Lora
* Abril Fatface and Poppins
* Cinzel and Fauna One
* Fjalla One and Libre Baskerville
* Space Mono and Muli
* Spectral and Rubik
* Oswald and Noto Sans

### CSS Font Property

To shorten the code, it is also possible to specify all the individual font properties in one property.  
The font property is a shorthand property for:

* font-style
* font-variant
* font-weight
* font-size/line-height
* font-family
Note: The font-size and font-family values are required. If one of the other values is missing, their default value are used.

```html
p.a {
  font: 20px Arial, sans-serif;
}

p.b {
  font: italic small-caps bold 12px/30px Georgia, serif;
}
```

**All CSS Font Properties**:  

| Property | Description |
| font | Sets all the font properties in one declaration |
| font-family | Specifies the font family for text |
| font-size | Specifies the font size of text |
| font-style | Specifies the font style for text |
| font-variant | Specifies whether or not a text should be displayed in a small-caps font |
| font-weight | Specifies the weight of a font |

## CSS Icons

The simplest way to add an icon to your HTML page, is with an icon library, such as Font Awesome.  
Add the name of the specified icon class to any inline HTML element (like `<i>` or `<span>`).  
All the icons in the icon libraries below, are scalable vectors that can be customized with CSS (size, color, shadow, etc.).  
Note: No downloading or installation is required!

```html
<!DOCTYPE html>
<html>
<head>
<script src="https://kit.fontawesome.com/yourcode.js" crossorigin="anonymous"></script>
<!--Get your code at fontawesome.com-->
</head>
<body>

<i class="fas fa-band-aid"></i>
<i class="fas fa-cat"></i>
<i class="fas fa-dragon"></i>
<i class="far fa-clock"></i>
<i class="fas fa-clock"></i>

</body>
</html>
```

**Font Awesome 4 Icons**:  
To use the Font Awesome 4 icons, add the following line inside the `<head>` section of your HTML page:  
Note: No downloading or installation is required!

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
</head>
<body>

<i class="fa fa-cloud"></i>
<i class="fa fa-heart"></i>
<i class="fa fa-car"></i>
<i class="fa fa-file"></i>
<i class="fa fa-bars"></i>

</body>
</html>
```

**List Icons**:  
The fa-ul and fa-li classes are used to replace default bullets in unordered lists.  

```html
<!DOCTYPE html>
<html>
<head>
<title>Font Awesome Icons</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
<!--Get your own code at fontawesome.com-->
</head>
<body style="font-size:24px;">

<ul class="fa-ul">
  <li><span class="fa-li"><i class="fas fa-check-square"></i></span>List Item</li>
  <li><span class="fa-li"><i class="fas fa-spinner fa-pulse"></i></span>List Item</li>
  <li><span class="fa-li"><i class="fas fa-square"></i></span>List Item</li>
</ul>

</body>
</html>

```

**Bootstrap Icons**:  
To use the Bootstrap glyphicons, add the following line inside the `<head>` section of your HTML page:  
`<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">`

Note: No downloading or installation is required!

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
</head>
<body>

<i class="glyphicon glyphicon-cloud"></i>
<i class="glyphicon glyphicon-remove"></i>
<i class="glyphicon glyphicon-user"></i>
<i class="glyphicon glyphicon-envelope"></i>
<i class="glyphicon glyphicon-thumbs-up"></i>

</body>
</html>
```

## CSS Links

**Styling Links**:  
Links can be styled with any CSS property (e.g. color, font-family, background, etc.).

```css
a {
  color: hotpink;
}
```

In addition, links can be styled differently depending on what state they are in.

The four links states are:

* a:link - a normal, unvisited link
* a:visited - a link the user has visited
* a:hover - a link when the user mouses over it
* a:active - a link the moment it is clicked

When setting the style for several link states, there are some order rules:

* a:hover MUST come after a:link and a:visited
* a:active MUST come after a:hover

**Text Decoration**:  
The text-decoration property is mostly used to remove underlines from links:

```css
a:link {
  text-decoration: none;
}
```

**Background Color**:  
The background-color property can be used to specify a background color for links:

```css
a:link {
  background-color: yellow;
}
```

**Link Buttons**:  
This example demonstrates a more advanced example where we combine several CSS properties to display links as boxes/buttons:

```css
a:link, a:visited {
  background-color: #f44336;
  color: white;
  padding: 14px 25px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
}

a:hover, a:active {
  background-color: red;
}
```

This example demonstrates the different types of cursors (can be useful for links):

```html
<span style="cursor: auto">auto</span><br>
<span style="cursor: crosshair">crosshair</span><br>
<span style="cursor: default">default</span><br>
<span style="cursor: e-resize">e-resize</span><br>
<span style="cursor: help">help</span><br>
<span style="cursor: move">move</span><br>
<span style="cursor: n-resize">n-resize</span><br>
<span style="cursor: ne-resize">ne-resize</span><br>
<span style="cursor: nw-resize">nw-resize</span><br>
<span style="cursor: pointer">pointer</span><br>
<span style="cursor: progress">progress</span><br>
<span style="cursor: s-resize">s-resize</span><br>
<span style="cursor: se-resize">se-resize</span><br>
<span style="cursor: sw-resize">sw-resize</span><br>
<span style="cursor: text">text</span><br>
<span style="cursor: w-resize">w-resize</span><br>
<span style="cursor: wait">wait</span>
```

## CSS Lists

In HTML, there are two main types of lists:

* unordered lists (`<ul>`) - the list items are marked with bullets
* ordered lists (`<ol>`) - the list items are marked with numbers or letters

The CSS list properties allow you to:

* Set different list item markers for ordered lists
* Set different list item markers for unordered lists
* Set an image as the list item marker
* Add background colors to lists and list items

**All CSS List Properties**:  

| Property | Description |
| list-style | Sets all the properties for a list in one declaration |
| list-style-image | Specifies an image as the list-item marker |
| list-style-position | Specifies the position of the list-item markers (bullet points) |
| list-style-type | Specifies the type of list-item marker |

**Different List Item Markers**:  
The list-style-type property specifies the type of list item marker.  
The following example shows some of the available list item markers:

```css
ul.a {
  list-style-type: circle;
}

ul.b {
  list-style-type: square;
}

ol.c {
  list-style-type: upper-roman;
}

ol.d {
  list-style-type: lower-alpha;
}
```

**An Image as The List Item Marker**:  
The list-style-image property specifies an image as the list item marker:

```css
ul {
  list-style-image: url('sqpurple.gif');
}
```

**Position The List Item Markers**:  
The list-style-position property specifies the position of the list-item markers (bullet points).  
`"list-style-position: outside;"` means that the bullet points will be outside the list item.  
The start of each line of a list item will be aligned vertically.  
`"list-style-position: inside;"` means that the bullet points will be inside the list item.  
As it is part of the list item, it will be part of the text and push the text at the start:

```css
ul.a {
  list-style-position: outside;
}

ul.b {
  list-style-position: inside;
}
```

**Remove Default Settings**:  
The list-style-type:none property can also be used to remove the markers/bullets.  
Note that the list also has default margin and padding.  
To remove this, add margin:0 and padding:0 to `<ul>` or `<ol>`:

```css
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
```

**List - Shorthand property**:  
The list-style property is a shorthand property.  
It is used to set all the list properties in one declaration:

```css
ul {
  list-style: square inside url("sqpurple.gif");
}
```

When using the shorthand property, the order of the property values are:

* list-style-type (if a list-style-image is specified, the value of this property will be displayed if the image for some reason cannot be displayed)
* list-style-position (specifies whether the list-item markers should appear inside or outside the content flow)
* list-style-image (specifies an image as the list item marker)

If one of the property values above are missing, the default value for the missing property will be inserted, if any.

**Styling List With Colors**:  
We can also style lists with colors, to make them look a little more interesting.  
Anything added to the `<ol>` or `<ul>` tag, affects the entire list, while properties added to the `<li>` tag will affect the individual list items:

```css
ol {
  background: #ff9999;
  padding: 20px;
}

ul {
  background: #3399ff;
  padding: 20px;
}

ol li {
  background: #ffe5e5;
  padding: 5px;
  margin-left: 35px;
}

ul li {
  background: #cce5ff;
  margin: 5px;
}

```

Customized list with a red left border:

```html
<!DOCTYPE html>
<html>
<head>
<style>
ul {
  border-left: 5px solid red;
  background-color: #f1f1f1;
  list-style-type: none;
  padding: 10px 20px;
}
</style>
</head>
<body>

<h2>List with a red left border</h2>

<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Coca Cola</li>
</ul>

</body>
</html>

```

## CSS Tables

**CSS Table Properties**:  

| Property | Description |
| border | Sets all the border properties in one declaration |
| border-collapse | Specifies whether or not table borders should be collapsed |
| border-spacing | Specifies the distance between the borders of adjacent cells |
| caption-side | Specifies the placement of a table caption |
| empty-cells | Specifies whether or not to display borders and background on empty cells in a table |
| table-layout | Sets the layout algorithm to be used for a table |

**Table Borders**:  
To specify table borders in CSS, use the border property.  
The example below specifies a black border for `<table>`, `<th>`, and `<td>` elements:

```css
table, th, td {
  border: 1px solid black;
}
```

**Double Borders**:  
Notice that the table in the examples above have double borders.  
This is because both the table and the `<th>` and `<td>` elements have separate borders.

To remove double borders, take a look at the example below.

**Collapse Table Borders**:  
The border-collapse property sets whether the table borders should be collapsed into a single border:

```css
table {
  border-collapse: collapse;
}
```

If you only want a border around the table, only specify the border property for `<table>`:

```css
table {
  border: 1px solid black;
}
```

**Table Width and Height**:  
The width and height of a table are defined by the width and height properties.  
The example below sets the width of the table to 100%, and the height of the `<th>` elements to 70px:

```css
table {
  width: 100%;
}

th {
  height: 70px;
}
```

**Horizontal Alignment**:  
The text-align property sets the horizontal alignment (like left, right, or center) of the content in `<th>` or `<td>`.  
By default, the content of `<th>` elements are center-aligned and the content of `<td>` elements are left-aligned.  
To center-align the content of  `<td>` elements as well, use text-align: center:

```css
td {
  text-align: center;
}
```

**Vertical Alignment**:  
The vertical-align property sets the vertical alignment (like top, bottom, or middle) of the content in `<th>` or `<td>`.  
By default, the vertical alignment of the content in a table is middle (for both `<th>` and `<td>` elements).  
The following example sets the vertical text alignment to bottom for `<td>` elements:

```css
td {
  height: 50px;
  vertical-align: bottom;
}
```

**Table Padding**:  
To control the space between the border and the content in a table, use the padding property on `<td>` and `<th>` elements:

```css
th, td {
  padding: 15px;
  text-align: left;
}
```

**Horizontal Dividers**:  
Add the border-bottom property to `<th>` and `<td>` for horizontal dividers:

```css
th, td {
  border-bottom: 1px solid #ddd;
}
```

**Hoverable Table**:  
Use the :hover selector on `<tr>` to highlight table rows on mouse over:
`tr:hover {background-color: yellow;}`

**Striped Tables**:  
For zebra-striped tables, use the nth-child() selector and add a background-color to all even (or odd) table rows:  
`tr:nth-child(even) {background-color: #f2f2f2;}`

**Table Color**:  
The example below specifies the background color and text color of `<th>` elements:  

```css
th {
  background-color: #04AA6D;
  color: white;
}
```

**Responsive Table**:  
A responsive table will display a horizontal scroll bar if the screen is too small to display the full content.  
Add a container element (like `<div>`) with overflow-x:auto around the `<table>` element to make it responsive:

```html
<div style="overflow-x:auto;">

<table>
... table content ...
</table>

</div>
```

**Set the position of the table caption**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
table, td, th {
  border: 1px solid black;
}

caption {
  caption-side: bottom;
}
</style>
</head>
```

## CSS Layout - The display Property

The display property specifies if/how an element is displayed.  
Every HTML element has a default display value depending on what type of element it is.  
The default display value for most elements is block or inline.

**CSS Display/Visibility Properties**:  

| Property | Description |
| display | Specifies how an element should be displayed |
| visibility | Specifies whether or not an element should be visible |

**Block-level Elements**:  
A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).  
Examples of block-level elements:

* `<div>`
* `<h1> - <h6>`
* `<p>`
* `<form>`
* `<header>`
* `<footer>`
* `<section>`

**Inline Elements**:  
An inline element does not start on a new line and only takes up as much width as necessary.  
Examples of inline elements:

* `<span>`
* `<a>`
* `<img>`

**Display: none;**:  
display: none; is commonly used with JavaScript to hide and show elements without deleting and recreating them.  

The `<script>` element uses display: none; as default.  

**Override The Default Display Value**:  
As mentioned, every element has a default display value.  
However, you can override this.  
Changing an inline element to a block element, or vice versa, can be useful for making the page look a specific way, and still follow the web standards.  
A common example is making inline `<li>` elements for horizontal menus:

```css
li {
  display: inline;
}
```

Note: Setting the display property of an element only changes how the element is displayed, NOT what kind of element it is.  
So, an inline element with display: block; is not allowed to have other block elements inside it.

**Hide an Element - display:none or visibility:hidden?**  

Hiding an element can be done by setting the display property to none.  
The element will be hidden, and the page will be displayed as if the element is not there:

```css
h1.hidden {
  display: none;
}
```

visibility:hidden; also hides an element.  
However, the element will still take up the same space as before.  
The element will be hidden, but still affect the layout:

```css
h1.hidden {
  visibility: hidden;
}
```

## CSS Layout - width and max-width

**Using width, max-width and margin: auto;**

As mentioned in the previous chapter; a block-level element always takes up the full width available (stretches out to the left and right as far as it can).  
Setting the width of a block-level element will prevent it from stretching out to the edges of its container.  
Then, you can set the margins to auto, to horizontally center the element within its container.  
The element will take up the specified width, and the remaining space will be split equally between the two margins:

Note: The problem with the `<div>` above occurs when the browser window is smaller than the width of the element.  
The browser then adds a horizontal scrollbar to the page.

Using max-width instead, in this situation, will improve the browser's handling of small windows.  
This is important when making a site usable on small devices:

```css
div.ex2 {
  max-width: 500px;
  margin: auto;
  border: 3px solid #73AD21;
}
```

## CSS Layout - The position Property

The position property specifies the type of positioning method used for an element.  
There are five different position values:

* static
* relative
* fixed
* absolute
* sticky

Elements are then positioned using the top, bottom, left, and right properties.  
However, these properties will not work unless the position property is set first.  
They also work differently depending on the position value.

**All CSS Positioning Properties**:  

| Property | Description |
| bottom | Sets the bottom margin edge for a positioned box |
| clip | Clips an absolutely positioned element |
| left | Sets the left margin edge for a positioned box |
| position | Specifies the type of positioning for an element |
| right | Sets the right margin edge for a positioned box |
| top | Sets the top margin edge for a positioned box |

**position: static;**  
HTML elements are positioned static by default.  
Static positioned elements are not affected by the top, bottom, left, and right properties.  
An element with position: static; is not positioned in any special way; it is always positioned according to the normal flow of the page.

**position: relative;**  
An element with position: relative; is positioned relative to its normal position.  
Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position.  
Other content will not be adjusted to fit into any gap left by the element.

```css
div.relative {
  position: relative;
  left: 30px;
  border: 3px solid #73AD21;
}
```

**position: fixed;**  
An element with position: fixed; is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled.  
The top, right, bottom, and left properties are used to position the element.  
A fixed element does not leave a gap in the page where it would normally have been located.  
Notice the fixed element in the lower-right corner of the page. Here is the CSS that is used:

```css
div.fixed {
  position: fixed;
  bottom: 0;
  right: 0;
  width: 300px;
  border: 3px solid #73AD21;
}
```

**position: absolute;**  
An element with position: absolute; is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed).  
However; if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling.  
Note: Absolute positioned elements are removed from the normal flow, and can overlap elements.

```css
div.relative {
  position: relative;
  width: 400px;
  height: 200px;
  border: 3px solid #73AD21;
}

div.absolute {
  position: absolute;
  top: 80px;
  right: 0;
  width: 200px;
  height: 100px;
  border: 3px solid #73AD21;
}
```

**position: sticky;**  
An element with position: sticky; is positioned based on the user's scroll position.  
A sticky element toggles between relative and fixed, depending on the scroll position.  
It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place (like position:fixed).

Note: Internet Explorer does not support sticky positioning.  
Safari requires a -webkit- prefix (see example below).  
You must also specify at least one of top, right, bottom or left for sticky positioning to work.

```css
div.sticky {
  position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
  background-color: green;
  border: 2px solid #4CAF50;
}
```

**Positioning Text In an Image**:  
How to position text over an image:

```html
<!DOCTYPE html>
<html>
<head>
<style>
.container {
  position: relative;
}

.topleft {
  position: absolute;
  top: 8px;
  left: 16px;
  font-size: 18px;
}

img { 
  width: 100%;
  height: auto;
  opacity: 0.3;
}
</style>
</head>
<body>

<h2>Image Text</h2>
<p>Add some text to an image in the top left corner:</p>

<div class="container">
  <img src="img_5terre_wide.jpg" alt="Cinque Terre" width="1000" height="300">
  <div class="topleft">Top Left</div>
</div>
```

**Set the shape of an element**:  
This example demonstrates how to set the shape of an element. The element is clipped into this shape, and displayed.

```css
img {
  position: absolute;
  clip: rect(0px,60px,200px,0px);
}
```

## CSS Layout - The z-index Property

When elements are positioned, they can overlap other elements.  
The z-index property specifies the stack order of an element (which element should be placed in front of, or behind, the others).  
An element can have a positive or negative stack order:

```css
img {
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: -1;
}
```

Note: z-index only works on positioned elements (position: absolute, position: relative, position: fixed, or position: sticky) and flex items (elements that are direct children of display: flex elements).

**Without z-index**:  
If two positioned elements overlap each other without a z-index specified, the element defined last in the HTML code will be shown on top.

## CSS Layout - Overflow

The overflow property specifies whether to clip the content or to add scrollbars when the content of an element is too big to fit in the specified area.  
The overflow property has the following values:

* visible - Default. The overflow is not clipped. The content renders outside the element's box
* hidden - The overflow is clipped, and the rest of the content will be invisible
* scroll - The overflow is clipped, and a scrollbar is added to see the rest of the content. Note that this will add a scrollbar both horizontally and vertically (even if you do not need it)
* auto - Similar to scroll, but it adds scrollbars only when necessary

Note: The overflow property only works for block elements with a specified height.

**All CSS Overflow Properties**:  

| Property | Description |
| overflow | Specifies what happens if content overflows an element's box |
| overflow-wrap | Specifies whether or not the browser can break lines with long words, if they overflow its container |
| overflow-x | Specifies what to do with the left/right edges of the content if it overflows the element's content area |
| overflow-y | Specifies what to do with the top/bottom edges of the content if it overflows the element's content area |

**overflow-x and overflow-y**:  
The overflow-x and overflow-y properties specifies whether to change the overflow of content just horizontally or vertically (or both):

* overflow-x specifies what to do with the left/right edges of the content.
* overflow-y specifies what to do with the top/bottom edges of the content.

```css
div {
  overflow-x: hidden; /* Hide horizontal scrollbar */
  overflow-y: scroll; /* Add vertical scrollbar */
}
```

## CSS Layout - float and clear

The CSS float property specifies how an element should float.  
The CSS clear property specifies what elements can float beside the cleared element and on which side.

**All CSS Float Properties**:  

| Property | Description  |
| box-sizing | Defines how the width and height of an element are calculated: should they include padding and borders, or not |
| clear | Specifies what should happen with the element that is next to a floating element |
| float | Specifies whether an element should float to the left, right, or not at all |
| overflow | Specifies what happens if content overflows an element's box |
| overflow-x | Specifies what to do with the left/right edges of the content if it overflows the element's content area |
| overflow-y | Specifies what to do with the top/bottom edges of the content if it overflows the element's content area |

### The float Property

The float property is used for positioning and formatting content e.g. let an image float left to the text in a container.  
The float property can have one of the following values:

* left - The element floats to the left of its container
* right - The element floats to the right of its container
* none - The element does not float (will be displayed just where it occurs in the text). This is default
* inherit - The element inherits the float value of its parent

In its simplest use, the float property can be used to wrap text around images.

```css
img {
  float: right;
}
```

**Float Next To Each Other**:  
Normally div elements will be displayed on top of each other.  
However, if we use float: left we can let elements float next to each other:

```html
<!DOCTYPE html>
<html>
<head>
<style>
div {
  float: left;
  padding: 15px; 
}

.div1 {
  background: red;
}

.div2 {
  background: yellow;
}

.div3 {
  background: green;
}
</style>
</head>
<body>

<h2>Float Next To Each Other</h2>

<p>In this example, the three divs will float next to each other.</p>

<div class="div1">Div 1</div>
<div class="div2">Div 2</div>
<div class="div3">Div 3</div>

</body>
</html>
```

### The clear Property

When we use the float property, and we want the next element below (not on right or left), we will have to use the clear property.  
The clear property specifies what should happen with the element that is next to a floating element.  
The clear property can have one of the following values:

* none - The element is not pushed below left or right floated elements. This is default
* left - The element is pushed below left floated elements
* right - The element is pushed below right floated elements
* both - The element is pushed below both left and right floated elements
* inherit - The element inherits the clear value from its parent

When clearing floats, you should match the clear to the float:  
If an element is floated to the left, then you should clear to the left.  
Your floated element will continue to float, but the cleared element will appear below it on the web page.

```css
div1 {
  float: left;
}

div2 {
  clear: left;
}
```

**The clearfix Hack**:  
If a floated element is taller than the containing element, it will "overflow" outside of its container.  
We can then add a clearfix hack to solve this problem:

```css
.clearfix {
  overflow: auto;
}
```

The overflow: auto clearfix works well as long as you are able to keep control of your margins and padding (else you might see scrollbars).  
The new, modern clearfix hack however, is safer to use, and the following code is used for most webpages:

```css
.clearfix::after {
  content: "";
  clear: both;
  display: table;
}
```

### Examples

**Grid of Boxes / Equal Width Boxes**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
* {
  box-sizing: border-box;
}

.box {
  float: left;
  width: 33.33%;
  padding: 50px;
}

.clearfix::after {
  content: "";
  clear: both;
  display: table;
}
</style>
</head>
<body>

<h2>Grid of Boxes</h2>
<p>Float boxes side by side:</p>

<div class="clearfix">
  <div class="box" style="background-color:#bbb">
  <p>Some text inside the box.</p>
  </div>
  <div class="box" style="background-color:#ccc">
  <p>Some text inside the box.</p>
  </div>
  <div class="box" style="background-color:#ddd">
  <p>Some text inside the box.</p>
  </div>
</div>
```

What is box-sizing?

You can easily create three floating boxes side by side.  
However, when you add something that enlarges the width of each box (e.g. padding or borders), the box will break.  
The box-sizing property allows us to include the padding and border in the box's total width (and height), making sure that the padding stays inside of the box and that it does not break.

**Images Side By Side**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
* {
  box-sizing: border-box;
}

.img-container {
  float: left;
  width: 33.33%;
  padding: 5px;
}

.clearfix::after {
  content: "";
  clear: both;
  display: table;
}
</style>
</head>
<body>

<h2>Images Side by Side</h2>
<p>Float images side by side:</p>

<div class="clearfix">
  <div class="img-container">
  <img src="img_5terre.jpg" alt="Italy" style="width:100%">
  </div>
  <div class="img-container">
  <img src="img_forest.jpg" alt="Forest" style="width:100%">
  </div>
  <div class="img-container">
  <img src="img_mountains.jpg" alt="Mountains" style="width:100%">
  </div>
</div>
```

**Equal Height Boxes**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
* {
  box-sizing: border-box;
}

.box {
  float: left;
  width: 50%;
  padding: 50px;
  height: 300px;
}

.clearfix::after {
  content: "";
  clear: both;
  display: table;
}
</style>
</head>
<body>

<h2>Equal Height Boxes</h2>
<p>Floating boxes with equal heights:</p>

<div class="clearfix">
  <div class="box" style="background-color:#bbb">
  <h2>Box 1</h2>
  <p>Some content, some content, some content</p>
  </div>
  <div class="box" style="background-color:#ccc">
  <h2>Box 2</h2>
  <p>Some content, some content, some content</p>
  <p>Some content, some content, some content</p>
  <p>Some content, some content, some content</p>
  </div>
</div>
```

**Navigation Menu**:  
You can also use float with a list of hyperlinks to create a horizontal menu:

```html
<!DOCTYPE html>
<html>
<head>
<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: inline-block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #111;
}

.active {
  background-color: red;
}
</style>
</head>
<body>

<ul>
  <li><a href="#home" class="active">Home</a></li>
  <li><a href="#news">News</a></li>
  <li><a href="#contact">Contact</a></li>
  <li><a href="#about">About</a></li>
</ul>

</body>
</html>
```

**Web Layout Example**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
* {
  box-sizing: border-box;
}

.header, .footer {
  background-color: grey;
  color: white;
  padding: 15px;
}

.column {
  float: left;
  padding: 15px;
}

.clearfix::after {
  content: "";
  clear: both;
  display: table;
}

.menu {
  width: 25%;
}

.content {
  width: 75%;
}

.menu ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.menu li {
  padding: 8px;
  margin-bottom: 8px;
  background-color: #33b5e5;
  color: #ffffff;
}

.menu li:hover {
  background-color: #0099cc;
}
</style>
</head>
<body>

<div class="header">
  <h1>Chania</h1>
</div>

<div class="clearfix">
  <div class="column menu">
    <ul>
      <li>The Flight</li>
      <li>The City</li>
      <li>The Island</li>
      <li>The Food</li>
    </ul>
  </div>

  <div class="column content">
    <h1>The City</h1>
    <p>Chania is the capital of the Chania region on the island of Crete. The city can be divided in two parts, the old town and the modern city.</p>
    <p>You will learn more about web layout and responsive web pages in a later chapter.</p>
  </div>
</div>

<div class="footer">
  <p>Footer Text</p>
</div>

</body>
</html>
```

**Let the first letter of a paragraph float to the left**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
span {
  float: left;
  width: 0.7em;
  font-size: 400%;
  font-family: algerian, courier;
  line-height: 80%;
}
</style>
</head>
<body>

<h2>Style the first letter of a paragraph and let it float left</h2>

<p>
<span>H</span>ere, the first letter of this text is embedded in a span element.
```

## CSS Layout - display: inline-block

**The display: inline-block Value**:  
Compared to display: inline, the major difference is that display: inline-block allows to set a width and height on the element.  
Also, with display: inline-block, the top and bottom margins/paddings are respected, but with display: inline they are not.  

Compared to display: block, the major difference is that display: inline-block does not add a line-break after the element, so the element can sit next to other elements.  

**Using inline-block to Create Navigation Links**:  
One common use for display: inline-block is to display list items horizontally instead of vertically.  
The following example creates horizontal navigation links:

```css
.nav {
  background-color: yellow;
  list-style-type: none;
  text-align: center; 
  padding: 0;
  margin: 0;
}

.nav li {
  display: inline-block;
  font-size: 20px;
  padding: 20px;
}
```

## CSS Layout - Horizontal & Vertical Align

**Center Align Elements**:  
To horizontally center a block element (like `<div>`), use margin: auto;  
Setting the width of the element will prevent it from stretching out to the edges of its container.  
The element will then take up the specified width, and the remaining space will be split equally between the two margins:

```css
.center {
  margin: auto;
  width: 50%;
  border: 3px solid green;
  padding: 10px;
}
```

Note: Center aligning has no effect if the width property is not set (or set to 100%).

**Center Align Text**:  
To just center the text inside an element, use text-align: center;

```css
.center {
  text-align: center;
  border: 3px solid green;
}
```

**Center an Image**:  
To center an image, set left and right margin to auto and make it into a block element:

```css
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 40%;
}
```

**Left and Right Align - Using position**
One method for aligning elements is to use position: absolute;

```css
.right {
  position: absolute;
  right: 0px;
  width: 300px;
  border: 3px solid #73AD21;
  padding: 10px;
}
```

Note: Absolute positioned elements are removed from the normal flow, and can overlap elements.

**Left and Right Align - Using float**:  
Another method for aligning elements is to use the float property:  

```css
.right {
  float: right;
  width: 300px;
  border: 3px solid #73AD21;
  padding: 10px;
}
```

**The clearfix Hack**:  
Note: If an element is taller than the element containing it, and it is floated, it will overflow outside of its container.  
You can use the "clearfix hack" to fix this (see example below).  
Then we can add the clearfix hack to the containing element to fix this problem:

```css
.clearfix::after {
  content: "";
  clear: both;
  display: table;
}
```

**Center Vertically - Using padding**:  
There are many ways to center an element vertically in CSS. A simple solution is to use top and bottom padding:

```css
.center {
  padding: 70px 0;
  border: 3px solid green;
}
```

To center both vertically and horizontally, use padding and text-align: center:

```css
.center {
  padding: 70px 0;
  border: 3px solid green;
  text-align: center;
}
```

**Center Vertically - Using line-height**:  
Another trick is to use the line-height property with a value that is equal to the height property:

```css
.center {
  line-height: 200px;
  height: 200px;
  border: 3px solid green;
  text-align: center;
}

/* If the text has multiple lines, add the following: */
.center p {
  line-height: 1.5;
  display: inline-block;
  vertical-align: middle;
}
```

**Center Vertically - Using position & transform**:  
If padding and line-height are not options, another solution is to use positioning and the transform property:

```css
.center {
  height: 200px;
  position: relative;
  border: 3px solid green;
}

.center p {
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

**Center Vertically - Using Flexbox**:  
You can also use flexbox to center things. Just note that flexbox is not supported in IE10 and earlier versions:

```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 200px;
  border: 3px solid green;
}
```

## CSS Opacity / Transparency

The opacity property can take a value from 0.0 - 1.0. The lower value, the more transparent.  
The opacity property is often used together with the :hover selector to change the opacity on mouse-over:

```css
img {
  opacity: 0.5;
}

img:hover {
  opacity: 1.0;
}
```

When using the opacity property to add transparency to the background of an element, all of its child elements inherit the same transparency.  
This can make the text inside a fully transparent element hard to read.  
If you do not want to apply opacity to child elements, like in our example above, use RGBA color values.

```css
div {
  background: rgba(76, 175, 80, 0.3) /* Green background with 30% opacity */
}
```

**Text in Transparent Box**:  

```html
<html>
<head>
<style>
div.background {
  background: url(klematis.jpg) repeat;
  border: 2px solid black;
}

div.transbox {
  margin: 30px;
  background-color: #ffffff;
  border: 1px solid black;
  opacity: 0.6;
}

div.transbox p {
  margin: 5%;
  font-weight: bold;
  color: #000000;
}
</style>
</head>
<body>

<div class="background">
  <div class="transbox">
    <p>This is some text that is placed in the transparent box.</p>
  </div>
</div>

```

## CSS Navigation Bar

**Navigation Bar = List of Links**:  
A navigation bar needs standard HTML as a base.  
In our examples we will build the navigation bar from a standard HTML list.  
A navigation bar is basically a list of links, so using the `<ul>` and `<li>` elements makes perfect sense:

### Vertical Navigation Bar

```css
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

li a {
  display: block;
  width: 60px;
  background-color: #dddddd;
}
```

Example explained:

* list-style-type: none; - removes the bullets. A navigation bar does not need list markers
* margin: 0; and padding: 0; - removes browser default settings
* display: block; - Displaying the links as block elements makes the whole link area clickable (not just the text), and it allows us to specify the width (and padding, margin, height, etc. if you want)
* width: 60px; - Block elements take up the full width available by default. We want to specify a 60 pixels width

You can also set the width of `<ul>`, and remove the width of `<a>`, as they will take up the full width available when displayed as block elements. This will produce the same result as our previous example:

**Active/Current Navigation Link**:  
Add an "active" class to the current link to let the user know which page he/she is on:

```css
Active/Current Navigation Link
Add an "active" class to the current link to let the user know which page he/she is on:
```

**Full-height Fixed Vertical Navbar**:  
Create a full-height, "sticky" side navigation:

```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  margin: 0;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  width: 25%;
  background-color: #f1f1f1;
  position: fixed;
  height: 100%;
  overflow: auto;
}

li a {
  display: block;
  color: #000;
  padding: 8px 16px;
  text-decoration: none;
}

li a.active {
  background-color: #04AA6D;
  color: white;
}

li a:hover:not(.active) {
  background-color: #555;
  color: white;
}
</style>
</head>
<body>

<ul>
  <li><a class="active" href="#home">Home</a></li>
  <li><a href="#news">News</a></li>
  <li><a href="#contact">Contact</a></li>
  <li><a href="#about">About</a></li>
</ul>

<div style="margin-left:25%;padding:1px 16px;height:1000px;">
  <h2>Fixed Full-height Side Nav</h2>
  <h3>Try to scroll this area, and see how the sidenav sticks to the page</h3>
```

### CSS Horizontal Navigation Bar

There are two ways to create a horizontal navigation bar. Using inline or floating list items.

**nline List Items**:  
One way to build a horizontal navigation bar is to specify the `<li>` elements as inline, in addition to the "standard" code from the previous page:  

```css
li {
  display: inline;
}
```

**Floating List Items**:  
Another way of creating a horizontal navigation bar is to float the `<li>` elements, and specify a layout for the navigation links:

```css
li {
  float: left;
}

a {
  display: block;
  padding: 8px;
  background-color: #dddddd;
}
```

Example explained:

* float: left; - Use float to get block elements to float next to each other
* display: block; - Allows us to specify padding (and height, width, margins, etc. if you want)
* padding: 8px; - Specify some padding between each `<a>` element, to make them look good
* background-color: #dddddd; - Add a gray background-color to each `<a>` element

Tip: Add the background-color to `<ul>` instead of each `<a>` element if you want a full-width background color:

**Active/Current Navigation Link**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover:not(.active) {
  background-color: #111;
}

.active {
  background-color: #04AA6D;
}
```

**Right-Align Links**:  

```html
<ul>
  <li><a href="#home">Home</a></li>
  <li><a href="#news">News</a></li>
  <li><a href="#contact">Contact</a></li>
  <li style="float:right"><a class="active" href="#about">About</a></li>
</ul>
```

**Border Dividers**:  
Add the border-right property to `<li>` to create link dividers:

```css
/* Add a gray right border to all list items, except the last item (last-child) */
li {
  border-right: 1px solid #bbb;
}

li:last-child {
  border-right: none;
}
```

**Fixed Navigation Bar**:

```css
ul {
  position: fixed;
  top: 0;
  width: 100%;
}
```

Note: Fixed position might not work properly on mobile devices.

**Sticky Navbar**:  

```css
ul {
  position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
}
```

**Responsive Topnav**:  

```css
@media screen and (max-width: 600px) {
  ul.topnav li.right, 
  ul.topnav li {float: none;}
}
```

**Dropdown Navbar**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a, .dropbtn {
  display: inline-block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover, .dropdown:hover .dropbtn {
  background-color: red;
}

li.dropdown {
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}

.dropdown-content a:hover {background-color: #f1f1f1;}

.dropdown:hover .dropdown-content {
  display: block;
}
</style>
</head>
<body>

<ul>
  <li><a href="#home">Home</a></li>
  <li><a href="#news">News</a></li>
  <li class="dropdown">
    <a href="javascript:void(0)" class="dropbtn">Dropdown</a>
    <div class="dropdown-content">
      <a href="#">Link 1</a>
      <a href="#">Link 2</a>
      <a href="#">Link 3</a>
    </div>
  </li>
</ul>

<h3>Dropdown Menu inside a Navigation Bar</h3>
<p>Hover over the "Dropdown" link to see the dropdown menu.</p>

</body>
</html>
```

## CSS Dropdowns

```html
<style>
/* Style The Dropdown Button */
.dropbtn {
  background-color: #4CAF50;
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
  cursor: pointer;
}

/* The container <div> - needed to position the dropdown content */
.dropdown {
  position: relative;
  display: inline-block;
}

/* Dropdown Content (Hidden by Default) */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

/* Links inside the dropdown */
.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

/* Change color of dropdown links on hover */
.dropdown-content a:hover {background-color: #f1f1f1}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {
  display: block;
}

/* Change the background color of the dropdown button when the dropdown content is shown */
.dropdown:hover .dropbtn {
  background-color: #3e8e41;
}
</style>

<div class="dropdown">
  <button class="dropbtn">Dropdown</button>
  <div class="dropdown-content">
    <a href="#">Link 1</a>
    <a href="#">Link 2</a>
    <a href="#">Link 3</a>
  </div>
</div>
```

**Right-aligned Dropdown Content**:  

```css
.dropdown-content {
  right: 0;
}
```

**Dropdown Image**:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

.dropdown:hover .dropdown-content {
  display: block;
}

.desc {
  padding: 15px;
  text-align: center;
}
</style>
</head>
<body>

<h2>Dropdown Image</h2>
<p>Move the mouse over the image below to open the dropdown content.</p>

<div class="dropdown">
  <img src="img_5terre.jpg" alt="Cinque Terre" width="100" height="50">
  <div class="dropdown-content">
  <img src="img_5terre.jpg" alt="Cinque Terre" width="300" height="200">
  <div class="desc">Beautiful Cinque Terre</div>
  </div>
</div>

</body>
</html>
```

## CSS Image Gallery

```html
<html>
<head>
<style>
div.gallery {
  margin: 5px;
  border: 1px solid #ccc;
  float: left;
  width: 180px;
}

div.gallery:hover {
  border: 1px solid #777;
}

div.gallery img {
  width: 100%;
  height: auto;
}

div.desc {
  padding: 15px;
  text-align: center;
}
</style>
</head>
<body>

<div class="gallery">
  <a target="_blank" href="img_5terre.jpg">
    <img src="img_5terre.jpg" alt="Cinque Terre" width="600" height="400">
  </a>
  <div class="desc">Add a description of the image here</div>
</div>

<div class="gallery">
  <a target="_blank" href="img_forest.jpg">
    <img src="img_forest.jpg" alt="Forest" width="600" height="400">
  </a>
  <div class="desc">Add a description of the image here</div>
</div>

<div class="gallery">
  <a target="_blank" href="img_lights.jpg">
    <img src="img_lights.jpg" alt="Northern Lights" width="600" height="400">
  </a>
  <div class="desc">Add a description of the image here</div>
</div>

<div class="gallery">
  <a target="_blank" href="img_mountains.jpg">
    <img src="img_mountains.jpg" alt="Mountains" width="600" height="400">
  </a>
  <div class="desc">Add a description of the image here</div>
</div>

</body>
</html>
```

## CSS Image Sprites

An image sprite is a collection of images put into a single image.  
A web page with many images can take a long time to load and generates multiple server requests.  
Using image sprites will reduce the number of server requests and save bandwidth.

```html
<!DOCTYPE html>
<html>
<head>
<style>
#navlist {
  position: relative;
}

#navlist li {
  margin: 0;
  padding: 0;
  list-style: none;
  position: absolute;
  top: 0;
}

#navlist li, #navlist a {
  height: 44px;
  display: block;
}

#home {
  left: 0px;
  width: 46px;
  background: url('img_navsprites_hover.gif') 0 0;
}

#prev {
  left: 63px;
  width: 43px;
  background: url('img_navsprites_hover.gif') -47px 0;
}

#next {
  left: 129px;
  width: 43px;
  background: url('img_navsprites_hover.gif') -91px 0;
}

#home a:hover {
  background: url('img_navsprites_hover.gif') 0 -45px;
}

#prev a:hover {
  background: url('img_navsprites_hover.gif') -47px -45px;
}

#next a:hover {
  background: url('img_navsprites_hover.gif') -91px -45px;
}
</style>
</head>
<body>

<ul id="navlist">
  <li id="home"><a href="default.asp"></a></li>
  <li id="prev"><a href="css_intro.asp"></a></li>
  <li id="next"><a href="css_syntax.asp"></a></li>
</ul>

</body>
</html>
```

## CSS Forms

**Styling Input Fields**:  
Use the width property to determine the width of the input field:

```css
input {
  width: 100%;
}
```

The example above applies to all `<input>` elements.  
If you only want to style a specific input type, you can use attribute selectors:

* `input[type=text]` - will only select text fields
* `input[type=password]` - will only select password fields
* `input[type=number]` - will only select number fields
etc..

**Padded Inputs**:  
Use the padding property to add space inside the text field.  
Tip: When you have many inputs after each other, you might also want to add some margin, to add more space outside of them:

```css
input[type=text] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
}
```

**Bordered Inputs**:  
Use the border property to change the border size and color, and use the border-radius property to add rounded corners:

```css
input[type=text] {
  border: 2px solid red;
  border-radius: 4px;
}
```

**Colored Inputs**:  
Use the background-color property to add a background color to the input, and the color property to change the text color:

```css
input[type=text] {
  background-color: #3CBC8D;
  color: white;
}
```

**Focused Inputs**:  
By default, some browsers will add a blue outline around the input when it gets focus (clicked on).  
You can remove this behavior by adding outline: none; to the input.  
Use the :focus selector to do something with the input field when it gets focus:

```css
input[type=text]:focus {
  background-color: lightblue;
}
input[type=text]:focus {
  border: 3px solid #555;
}
```

**Input with icon/image**:  
If you want an icon inside the input, use the background-image property and position it with the background-position property.  
Also notice that we add a large left padding to reserve the space of the icon:

```css
input[type=text] {
  background-color: white;
  background-image: url('searchicon.png');
  background-position: 10px 10px;
  background-repeat: no-repeat;
  padding-left: 40px;
}
```

**Animated Search Input**:  
In this example we use the CSS transition property to animate the width of the search input when it gets focus.  
You will learn more about the transition property later, in our CSS Transitions chapter.

```css
input[type=text] {
  transition: width 0.4s ease-in-out;
}

input[type=text]:focus {
  width: 100%;
}
```

**Styling Textareas**:  
Tip: Use the resize property to prevent textareas from being resized (disable the "grabber" in the bottom right corner):

```css
textarea {
  width: 100%;
  height: 150px;
  padding: 12px 20px;
  box-sizing: border-box;
  border: 2px solid #ccc;
  border-radius: 4px;
  background-color: #f8f8f8;
  resize: none;
}
```

**Styling Select Menus**:  

```html
<!DOCTYPE html>
<html>
<head>
<style> 
select {
  width: 100%;
  padding: 16px 20px;
  border: none;
  border-radius: 4px;
  background-color: #f1f1f1;
}
</style>
</head>
<body>

<h2>Styling a select menu</h2>

<form>
  <select id="country" name="country">
  <option value="au">Australia</option>
  <option value="ca">Canada</option>
  <option value="usa">USA</option>
  </select>
</form>

</body>
</html>
```

**Styling Input Buttons**:  

```css
input[type=button], input[type=submit], input[type=reset] {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 16px 32px;
  text-decoration: none;
  margin: 4px 2px;
  cursor: pointer;
}

/* Tip: use width: 100% for full-width buttons */
```

**Responsive Form**:  
Resize the browser window to see the effect.  
When the screen is less than 600px wide, make the two columns stack on top of each other instead of next to each other.

```css
* {
  box-sizing: border-box;
}

input[type=text], select, textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  resize: vertical;
}

label {
  padding: 12px 12px 12px 0;
  display: inline-block;
}

input[type=submit] {
  background-color: #04AA6D;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  float: right;
}

input[type=submit]:hover {
  background-color: #45a049;
}

.container {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}

.col-25 {
  float: left;
  width: 25%;
  margin-top: 6px;
}

.col-75 {
  float: left;
  width: 75%;
  margin-top: 6px;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Responsive layout - when the screen is less than 600px wide, make the two columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .col-25, .col-75, input[type=submit] {
    width: 100%;
    margin-top: 0;
  }
}
```

## CSS Counters

CSS counters are "variables" maintained by CSS whose values can be incremented by CSS rules (to track how many times they are used).  
Counters let you adjust the appearance of content based on its placement in the document.  

**Automatic Numbering With Counters**:  
CSS counters are like "variables".  
The variable values can be incremented by CSS rules (which will track how many times they are used).

To work with CSS counters we will use the following properties:

* counter-reset - Creates or resets a counter
* counter-increment - Increments a counter value
* content - Inserts generated content
* counter() or counters() function - Adds the value of a counter to an element
To use a CSS counter, it must first be created with counter-reset.

The following example creates a counter for the page (in the body selector), then increments the counter value for each `<h2>` element and adds "Section `<value of the counter>:`" to the beginning of each `<h2>` element:

```css
body {
  counter-reset: section;
}

h2::before {
  counter-increment: section;
  content: "Section " counter(section) ": ";
}
```

## CSS Website Layout

**Header**:  
A header is usually located at the top of the website (or right below a top navigation menu). It often contains a logo or the website name:

```css
.header {
  background-color: #F1F1F1;
  text-align: center;
  padding: 20px;
}
```

**Navigation Bar**:  
A navigation bar contains a list of links to help visitors navigating through your website:

```CSS
/* The navbar container */
.topnav {
  overflow: hidden;
  background-color: #333;
}

/* Navbar links */
.topnav a {
  float: left;
  display: block;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

/* Links - change color on hover */
.topnav a:hover {
  background-color: #ddd;
  color: black;
}
```

**Content**:  
The layout in this section, often depends on the target users.  
The most common layout is one (or combining them) of the following:

1-column (often used for mobile browsers)
2-column (often used for tablets and laptops)
3-column layout (only used for desktops)

We will create a 3-column layout, and change it to a 1-column layout on smaller screens:

```css
/* Create three equal columns that float next to each other */
.column {
  float: left;
  width: 33.33%;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Responsive layout - makes the three columns stack on top of each other instead of next to each other on smaller screens (600px wide or less) */
@media screen and (max-width: 600px) {
  .column {
    width: 100%;
  }
}
```

**Unequal Columns**:  
The main content is the biggest and the most important part of your site.

It is common with unequal column widths, so that most of the space is reserved for the main content. The side content (if any) is often used as an alternative navigation or to specify information relevant to the main content.  
Change the widths as you like, only remember that it should add up to 100% in total:

```css
.column {
  float: left;
}

/* Left and right column */
.column.side {
  width: 25%;
}

/* Middle column */
.column.middle {
  width: 50%;
}

/* Responsive layout - makes the three columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .column.side, .column.middle {
    width: 100%;
  }
}
```

**Footer**:  
The footer is placed at the bottom of your page.  
It often contains information like copyright and contact info:

```css
.footer {
  background-color: #F1F1F1;
  text-align: center;
  padding: 10px;
}
```

**Responsive Website Layout**:  
By using some of the CSS code above, we have created a responsive website layout, which varies between two columns and full-width columns depending on screen width:

```html
<!DOCTYPE html>
<html>
<head>
<style>
* {
  box-sizing: border-box;
}

body {
  font-family: Arial;
  padding: 10px;
  background: #f1f1f1;
}

/* Header/Blog Title */
.header {
  padding: 30px;
  text-align: center;
  background: white;
}

.header h1 {
  font-size: 50px;
}

/* Style the top navigation bar */
.topnav {
  overflow: hidden;
  background-color: #333;
}

/* Style the topnav links */
.topnav a {
  float: left;
  display: block;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

/* Change color on hover */
.topnav a:hover {
  background-color: #ddd;
  color: black;
}

/* Create two unequal columns that floats next to each other */
/* Left column */
.leftcolumn {   
  float: left;
  width: 75%;
}

/* Right column */
.rightcolumn {
  float: left;
  width: 25%;
  background-color: #f1f1f1;
  padding-left: 20px;
}

/* Fake image */
.fakeimg {
  background-color: #aaa;
  width: 100%;
  padding: 20px;
}

/* Add a card effect for articles */
.card {
  background-color: white;
  padding: 20px;
  margin-top: 20px;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Footer */
.footer {
  padding: 20px;
  text-align: center;
  background: #ddd;
  margin-top: 20px;
}

/* Responsive layout - when the screen is less than 800px wide, make the two columns stack on top of each other instead of next to each other */
@media screen and (max-width: 800px) {
  .leftcolumn, .rightcolumn {   
    width: 100%;
    padding: 0;
  }
}

/* Responsive layout - when the screen is less than 400px wide, make the navigation links stack on top of each other instead of next to each other */
@media screen and (max-width: 400px) {
  .topnav a {
    float: none;
    width: 100%;
  }
}
</style>
</head>
<body>

<div class="header">
  <h1>My Website</h1>
  <p>Resize the browser window to see the effect.</p>
</div>

<div class="topnav">
  <a href="#">Link</a>
  <a href="#">Link</a>
  <a href="#">Link</a>
  <a href="#" style="float:right">Link</a>
</div>

<div class="row">
  <div class="leftcolumn">
    <div class="card">
      <h2>TITLE HEADING</h2>
      <h5>Title description, Dec 7, 2017</h5>
      <div class="fakeimg" style="height:200px;">Image</div>
      <p>Some text..</p>
      <p>Sunt in culpa qui officia deserunt mollit anim id est laborum consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco.</p>
    </div>
    <div class="card">
      <h2>TITLE HEADING</h2>
      <h5>Title description, Sep 2, 2017</h5>
      <div class="fakeimg" style="height:200px;">Image</div>
      <p>Some text..</p>
      <p>Sunt in culpa qui officia deserunt mollit anim id est laborum consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco.</p>
    </div>
  </div>
  <div class="rightcolumn">
    <div class="card">
      <h2>About Me</h2>
      <div class="fakeimg" style="height:100px;">Image</div>
      <p>Some text about me in culpa qui officia deserunt mollit anim..</p>
    </div>
    <div class="card">
      <h3>Popular Post</h3>
      <div class="fakeimg"><p>Image</p></div>
      <div class="fakeimg"><p>Image</p></div>
      <div class="fakeimg"><p>Image</p></div>
    </div>
    <div class="card">
      <h3>Follow Me</h3>
      <p>Some text..</p>
    </div>
  </div>
</div>

<div class="footer">
  <h2>Footer</h2>
</div>

</body>
</html>
```

## CSS Units

CSS has several different units for expressing a length.  
Many CSS properties take "length" values, such as width, margin, padding, font-size, etc.  
Length is a number followed by a length unit, such as 10px, 2em, etc.

Note: A whitespace cannot appear between the number and the unit.  
However, if the value is 0, the unit can be omitted.

For some CSS properties, negative lengths are allowed.  
There are two types of length units: absolute and relative.

**Absolute Lengths**:  
The absolute length units are fixed and a length expressed in any of these will appear as exactly that size.
Absolute length units are not recommended for use on screen, because screen sizes vary so much.  
However, they can be used if the output medium is known, such as for print layout.

| Unit | Description |
| cm | centimeters |
| mm | millimeters |
| in | inches (1in = 96px = 2.54cm) |
| px * | pixels (1px = 1/96th of 1in) |
| pt | points (1pt = 1/72 of 1in) |
| pc | picas (1pc = 12 pt) |

**Relative Lengths**:  
Relative length units specify a length relative to another length property.  
Relative length units scales better between different rendering mediums.

| Unit | Description |
| em | Relative to the font-size of the element (2em means 2 times the size of the current font) |
| ex | Relative to the x-height of the current font (rarely used) |
| ch | Relative to width of the "0" (zero) |
| rem | Relative to font-size of the root element |
| vw | Relative to 1% of the width of the viewport`*` |
| vh | Relative to 1% of the height of the viewport `*` |
| vmin | Relative to 1% of viewport's `*` smaller dimension |
| vmax | Relative to 1% of viewport's* larger dimension |
| % | Relative to the parent element |

## CSS Specificity

If there are two or more CSS rules that point to the same element, the selector with the highest specificity value will "win", and its style declaration will be applied to that HTML element.

**Specificity Hierarchy**:  
Every CSS selector has its place in the specificity hierarchy.  
There are four categories which define the specificity level of a selector:

* Inline styles - Example: `<h1 style="color: pink;">`
* IDs - Example: #navbar
* Classes, pseudo-classes, attribute selectors - Example: .test, :hover, `[href]`
* Elements and pseudo-elements - Example: h1, :before

**How to Calculate Specificity?**:  
Memorize how to calculate specificity!  
Start at 0, add 100 for each ID value, add 10 for each class value (or pseudo-class or attribute selector), add 1 for each element selector or pseudo-element.  
Note: Inline style gets a specificity value of 1000, and is always given the highest priority!  
Note 2: There is one exception to this rule: if you use the !important rule, it will even override inline styles!

The table below shows some examples on how to calculate specificity values:

| Selector | Specificity Value | Calculation |
| p | 1 | 1 |
| p.test | 11 | 1 + 10 |
| p#demo | 101 | 1 + 100 |
| `<p style="color: pink;">` | 1000 | 1000 |
| #demo | 100 | 100 |
| .test | 10 | 10 |
| p.test1.test2 | 21 | 1 + 10 + 10 |
| #navbar p#demo | 201 | 100 + 1 + 100 |
| * | 0 | 0 (the universal selector is ignored) |

**Equal specificity:** the latest rule wins - If the same rule is written twice into the external style sheet, then the latest rule wins;

**ID selectors have a higher specificity than attribute selectors** - Look at the following three code lines:

```css
div#a {background-color: green;}
#a {background-color: yellow;}
div[id=a] {background-color: blue;}
```

**Contextual selectors are more specific than a single element selector** - The embedded style sheet is closer to the element to be styled. So in the following situation
the latter rule will be applied.

```css
From external CSS file:
#content h1 {background-color: red;}

In HTML file:
<style>
#content h1 {background-color: yellow;}
</style>
```

**A class selector beats any number of element selectors** - a class selector such as .intro beats h1, p, div, etc:

```css
.intro {background-color: yellow;}
h1 {background-color: red;}
```

The universal selector (*) and inherited values have a specificity of 0 - The universal selector (*) and inherited values are ignored!

## CSS The !important Rule

The !important rule in CSS is used to add more importance to a property/value than normal.  
In fact, if you use the !important rule, it will override ALL previous styling rules for that specific property on that element!

```css
#myid {
  background-color: blue;
}

.myclass {
  background-color: gray;
}

p {
  background-color: red !important;
}
```

Example Explained:  
In the example above. all three paragraphs will get a red background color, even though the ID selector and the class selector has a higher specificity. The !important rule overrides the background-color property in both cases.

**mportant About !important**:  
The only way to override an !important rule is to include another !important rule on a declaration with the same (or higher) specificity in the source code - and here the problem starts!  
This makes the CSS code confusing and the debugging will be hard, especially if you have a large style sheet!

**Maybe One or Two Fair Uses of !important**:  
One way to use !important is if you have to override a style that cannot be overridden in any other way.  
This could be if you are working on a Content Management System (CMS) and cannot edit the CSS code.  
Then you can set some custom styles to override some of the CMS styles.

Another way to use !important is: Assume you want a special look for all buttons on a page.  
Here, buttons are styled with a gray background color, white text, and some padding and border.  
The look of a button can sometimes change if we put it inside another element with higher specificity, and the properties get in conflict. Here is an example of this:

To "force" all buttons to have the same look, no matter what, we can add the !important rule to the properties of the button, like this:

```css
.button {
  background-color: #8c8c8c !important;
  color: white !important;
  padding: 5px !important;
  border: 1px solid black !important;
}

#myDiv a {
  color: red;
  background-color: yellow;
}
```

## CSS Math Functions

The CSS math functions allow mathematical expressions to be used as property values.  
Here, we will explain the calc(), max() and min() functions.

**The calc() Function**:  
The calc() function performs a calculation to be used as the property value.

```css
#div1 {
  position: absolute;
  left: 50px;
  width: calc(100% - 100px);
  border: 1px solid black;
  background-color: yellow;
  padding: 5px;
}
```

**The max() Function**:  
The max() function uses the largest value, from a comma-separated list of values, as the property value.

Use max() to set the width of #div1 to whichever value is largest, 50% or 300px:

```css
#div1 {
  background-color: yellow;
  height: 100px;
  width: max(50%, 300px);
}
```

**The min() Function**:  
The min() function uses the smallest value, from a comma-separated list of values, as the property value.

```css
Use min() to set the width of #div1 to whichever value is smallest, 50% or 300px:

#div1 {
  background-color: yellow;
  height: 100px;
  width: min(50%, 300px);
}
```
