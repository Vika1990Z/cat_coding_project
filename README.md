# HTML notes

> Here are reprezented my own notes about HTML

**HTML** (Hypertext Markup Language) is the code that is used to structure a web page and its content.
HTML tags are not case sensitive: `<P>` means the same as `<p>`.

## HTML Documents

All HTML documents must start with a document type declaration: `<!DOCTYPE html>`.  
The HTML document itself begins with `<html>` and ends with `</html>`.  
The visible part of the HTML document is between `<body>` and `</body>`.  
Example:  

```html
<!DOCTYPE html>
<html>
<body>
<h1>My First Heading</h1>
<p>My first paragraph.</p>
</body>
</html>
```

**DOCTYPE**.
The `<!DOCTYPE>` declaration represents the document type, and helps browsers to display web pages correctly.  
It must only appear once, at the top of the page (before any HTML tags).  
The `<!DOCTYPE>` declaration is not case sensitive.  

**HTML Headings**.
HTML headings are defined with the `<h1>` to `<h6>` tags.  
`<h1>` defines the most important heading. `<h6>` defines the least important heading:

## HTML Elements

The HTML element is everything from the start tag to the end tag:
Examples of some HTML elements:

```html
<h1>My First Heading</h1>
<p>My first paragraph.</p>
```

| Start tag  | Element content | End tag |
| ---------- | --------------- | ------- |
| `<h1>` | My First Heading | `</h1>` |
| `<p>` | My first paragraph. | `</p>` |
| `<br>` | none | none |

HTML elements can be nested (this means that elements can contain other elements).
All HTML documents consist of nested HTML elements.
The following example contains four HTML elements (`<html>, <body>, <h1> and <p>`):

## HTML Attributes

All HTML elements can have attributes:  

* Attributes provide additional information about elements;  
* Attributes are always specified in the start tag;  
* Attributes usually come in name/value pairs like: name="value";  

The HTML standard does not require lowercase attribute names, but We Suggest: Always Use Lowercase Attributes.  

The HTML standard does not require quotes around attribute values, but We Suggest: Always Quote Attribute Values.  

Double quotes around attribute values are the most common in HTML, but single quotes can also be used.  
In some situations, when the attribute value itself contains double quotes, it is necessary to use single quotes

### The href Attribute

The `<a>` tag defines a hyperlink.
The `href` attribute specifies the URL of the page the link goes to:

```html
<a href="https://www.w3schools.com">Visit W3Schools</a>
```

### The src Attribute

The `<img>` tag is used to embed an image in an HTML page.  
The `src` attribute specifies the path to the image to be displayed:

```html
<img src="img_girl.jpg">
```

There are two ways to specify the URL in the `src` attribute:

* *Absolute URL* - Links to an external image that is hosted on another website.  
Example: `src="https://www.w3schools.com/images/img_girl.jpg".`

> Notes:  
> External images might be under copyright.  
> If you do not get permission to use it, you may be in violation of copyright laws.  
> In addition, you cannot control external images; it can suddenly be removed or changed.

* *Relative URL* - Links to an image that is hosted within the website.  
Here, the URL does not include the domain name.  
If the URL begins without a slash, it will be relative to the current page.  
Example: `src="img_girl.jpg".`  

If the URL begins with a slash, it will be relative to the domain.  
Example: `src="/images/img_girl.jpg".`  

> Tip: It is almost always best to use relative URLs.  
> They will not break if you change domain.

### The width and height Attributes

The `<img>` tag should also contain the width and height attributes, which specifies the width and height of the image (in pixels):

```html
<img src="img_girl.jpg" width="500" height="600">
```

Alternatively, you can use the `style` attribute to specify the width and height of an image:
Use the CSS `float` property to let the image float to the left or to the right:

```html
<img src="img_girl.jpg" alt="Girl in a jacket" style="float:right;width:500px;height:600px;">
```

### The alt Attribute

The required `alt` attribute for the `<img>` tag specifies an alternate text for an image, if the image for some reason cannot be displayed.  
This can be due to slow connection, or an error in the src attribute, or if the user uses a screen reader.  
The value of the `alt` attribute should describe the image:  

```html
<img src="img_girl.jpg" alt="Girl with a jacket">
```

### The style Attribute

The style attribute is used to add styles to an element, such as color, font, size, and more.

```html
<p style="color:red;">This is a red paragraph.</p>
```

### The lang Attribute

You should always include the lang attribute inside the `<html>` tag, to declare the language of the Web page.  
This is meant to assist search engines and browsers.

The following example specifies English as the language:

```html
<!DOCTYPE html>
<html lang="en">
<body>
...
</body>
</html>
```

Country codes can also be added to the language code in the lang attribute.  
So, the first two characters define the language of the HTML page, and the last two characters define the country.

```html
<html lang="en-US">
```

### The title Attribute

The title attribute defines some extra information about an element.  
The value of the title attribute will be displayed as a tooltip when you mouse over the element:

```html
<p title="I'm a tooltip">This is a paragraph.</p>
```

## HTML Headings

HTML headings are titles or subtitles that you want to display on a webpage.  
HTML headings are defined with the `<h1>` to `<h6>` tags.

### Bigger Headings

Each HTML heading has a default size. However, you can specify the size for any heading with the style attribute, using the CSS font-size property:

```html
<h1 style="font-size:60px;">Heading 1</h1>
```

## HTML Paragraphs

A paragraph always starts on a new line, and is usually a block of text.  
The HTML `<p>` element defines a paragraph.  
A paragraph always starts on a new line, and browsers automatically add some white space (a margin) before and after a paragraph.

You cannot be sure how HTML will be displayed.  
Large or small screens, and resized windows will create different results.

### HTML Horizontal Rules

The `<hr>` tag defines a thematic break in an HTML page, and is most often displayed as a horizontal rule.  
The `<hr>` tag is an empty tag, which means that it has no end tag.  
The `<hr>` element is used to separate content (or define a change) in an HTML page:  

```html
<h1>This is heading 1</h1>
<p>This is some text.</p>
<hr>
<h2>This is heading 2</h2>
<p>This is some other text.</p>
<hr>
```

### HTML Line Breaks

The HTML `<br>` element defines a line break.  
The `<br>` tag is an empty tag, which means that it has no end tag.  
Use `<br>` if you want a line break (a new line) without starting a new paragraph:

```html
<p>This is<br>a paragraph<br>with line breaks.</p>
```

## HTML Styles

The HTML style attribute is used to add styles to an element, such as color, font, size, and more.

### The HTML Style Attribute

Setting the style of an HTML element, can be done with the style attribute.  
The HTML style attribute has the following syntax:

```html
<tagname style="property:value;">
```

The property is a CSS property. The value is a CSS value.

### Background Color

The CSS background-color property defines the background color for an HTML element.

Example:  
Set the background color for a page to powderblue:

```html
<body style="background-color:powderblue;">

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
```

Example
Set background color for two different elements:

```html
<body>

<h1 style="background-color:powderblue;">This is a heading</h1>
<p style="background-color:tomato;">This is a paragraph.</p>

</body>
```

### Text Color

The CSS color property defines the text color for an HTML element:

```html
<h1 style="color:blue;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>
```

### Fonts

The CSS font-family property defines the font to be used for an HTML element:

```html
<h1 style="font-family:verdana;">This is a heading</h1>
<p style="font-family:courier;">This is a paragraph.</p>
```

### Text Size

The CSS font-size property defines the text size for an HTML element:

```html
<h1 style="font-size:300%;">This is a heading</h1>
<p style="font-size:160%;">This is a paragraph.</p>
```

### Text Alignment

The CSS text-align property defines the horizontal text alignment for an HTML element:

```html
<h1 style="text-align:center;">Centered Heading</h1>
<p style="text-align:center;">Centered paragraph.</p>
```

## HTML Text Formatting

### HTML Formatting Elements

Formatting elements were designed to display special types of text:

* `<b>` - Bold text without any extra importance  
* `<strong>` - Important text (typically displayed in bold)  
* `<i>` - Italic text (text in an alternate voice or mood), (ften used to indicate a technical term, a phrase from another language, a thought, a ship name, etc.)  
* `<em>` - Emphasized text (tyically displayed in italic)  
* `<mark>` - Marked text  
* `<small>` - Smaller text  
* `<del>` - Deleted text (Browsers will usually strike a line through deleted text)  
* `<ins>` - Inserted text (Browsers will usually underline inserted text)  
* `<sub>` - Subscript text (Subscript text appears half a character below the normal line, and is sometimes rendered in a smaller font. Subscript text can be used for chemical formulas, like H2O)  
* `<sup>` - Superscript text (Superscript text appears half a character above the normal line, and is sometimes rendered in a smaller font. Superscript text can be used for footnotes)

### The HTML `<pre>` Element

The HTML `<pre>` element defines preformatted text.  
The text inside a `<pre>` element is displayed in a fixed-width font (usually Courier), and it preserves both spaces and line breaks:

```html
<pre>
  My Bonnie lies over the ocean.

  My Bonnie lies over the sea.

  My Bonnie lies over the ocean.

  Oh, bring back my Bonnie to me.
</pre>
```

### HTML Quotation and Citation Elements

* `<blockquote>` - element defines a section that is quoted from another source.  
Browsers usually indent `<blockquote>` elements.  

* `<q>` - tag defines a short quotation.  
Browsers normally insert quotation marks around the quotation ("").

* `<abbr>` - tag defines an abbreviation or an acronym, like "HTML", "CSS", "Mr.", "Dr.", "ASAP", "ATM".  
Marking abbreviations can give useful information to browsers, translation systems and search-engines.  
Use the global title attribute to show the description for the abbreviation/acronym when you mouse over the element.

```html
<p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>
```

* `<address>` - tag defines the contact information for the author/owner of a document or an article.  
The contact information can be an email address, URL, physical address, phone number, social media handle, etc.  
The text in the `<address>` element usually renders in italic, and browsers will always add a line break before and after the <address> element.

```html
<address>
Written by John Doe.<br>
Visit us at:<br>
Example.com<br>
Box 564, Disneyland<br>
USA
</address>
```

* `<cite>` - tag defines the title of a creative work (e.g. a book, a poem, a song, a movie, a painting, a sculpture, etc.).  
Note: A person's name is not the title of a work.  
The text in the `<cite>` element usually renders in italic.  

```html
<p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>
```

* `<bdo>` - for Bi-Directional Override.  
The HTML `<bdo>` tag is used to override the current text direction:

```html
<bdo dir="rtl">This text will be written from right to left</bdo>
```

## HTML Comments

HTML comments are not displayed in the browser, but they can help document your HTML source code.

### HTML Comment Tag

You can add comments to your HTML source by using the following syntax:
Comments are also great for debugging HTML, because you can comment out HTML lines of code, one at a time, to search for errors.

```html
<!-- Write your comments here -->
```

Notice that there is an exclamation point (!) in the start tag, but not in the end tag.  
Comments are not displayed by the browser, but they can help document your HTML source code.

### Hide Content

Comments can be used to hide content.  
Which can be helpful if you hide content temporarily:  

```html
<p>This is a paragraph.</p>

<!-- <p>This is another paragraph </p> -->

<p>This is a paragraph too.</p>
```

You can also hide more than one line, everything between the <!-- and the --> will be hidden from the display.

```html
Hide a section of HTML code:

<p>This is a paragraph.</p>
<!--
<p>Look at this cool image:</p>
<img border="0" src="pic_trulli.jpg" alt="Trulli">
-->
<p>This is a paragraph too.</p>
```

Comments can be used to hide parts in the middle of the HTML code.

```html
<p>This <!-- great text --> is a paragraph.</p>
```

## Colors

HTML colors are specified with predefined color names, or with RGB, HEX, HSL, RGBA, or HSLA values.  
In HTML, a color can be specified by using a color name: Tomato, Orange, DodgerBlue, MediumSeaGreen, Gray, SlateBlue, Violet, LightGray.  
HTML supports 140 standard color names.

* Background Color

```html
<h1 style="background-color:DodgerBlue;">Hello World</h1>
<p style="background-color:Tomato;">Lorem ipsum...</p>
```

* Text Color

```html
<h1 style="color:Tomato;">Hello World</h1>
<p style="color:DodgerBlue;">Lorem ipsum...</p>
<p style="color:MediumSeaGreen;">Ut wisi enim...</p>
```

* Border Color

```html
<h1 style="border:2px solid Tomato;">Hello World</h1>
<h1 style="border:2px solid DodgerBlue;">Hello World</h1>
<h1 style="border:2px solid Violet;">Hello World</h1>
```

In HTML, colors can also be specified using RGB values, HEX values, HSL values, RGBA values, and HSLA values.
The following two <div> elements have their background color set with RGBA and HSLA values, which adds an Alpha channel to the color (here we have 50% transparency):

```html
<h1 style="background-color:rgb(255, 99, 71);">...</h1>
<h1 style="background-color:#ff6347;">...</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">...</h1>

<h1 style="background-color:rgba(255, 99, 71, 0.5);">...</h1>
<h1 style="background-color:hsla(9, 100%, 64%, 0.5);">...</h1>
```

### RGB Colors

An RGB color value represents RED, GREEN, and BLUE light sources.  

In HTML, a color can be specified as an RGB value, using this formula:  
`rgb(red, green, blue)`

Each parameter (red, green, and blue) defines the intensity of the color with a value between 0 and 255.  
This means that there are 256 x 256 x 256 = 16777216 possible colors!  

For example, rgb(255, 0, 0) is displayed as red, because red is set to its highest value (255), and the other two (green and blue) are set to 0.  
To display black, set all color parameters to 0, like this: rgb(0, 0, 0).  
To display white, set all color parameters to 255, like this: rgb(255, 255, 255).  

**Shades of Gray** - are often defined using equal values for all three parameters: (rgb(60,60,60), rgb(100,100,100), rgb(140,140,140)...)

### RGBA Colors

RGBA color values are an extension of RGB color values with an Alpha channel - which specifies the opacity for a color.  
An RGBA color value is specified with:  
`rgba(red, green, blue, alpha)`

The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (not transparent at all): (rgba(255, 99, 71, 0), rgba(255, 99, 71, 0.2), rgba(255, 99, 71, 1)...)

### HEX Colors

In HTML, a color can be specified using a hexadecimal value in the form:
`#rrggbb`

Where rr (red), gg (green) and bb (blue) are hexadecimal values between 00 and ff (same as decimal 0-255).  

For example, #ff0000 is displayed as red, because red is set to its highest value (ff), and the other two (green and blue) are set to 00.  
Another example, #00ff00 is displayed as green, because green is set to its highest value (ff), and the other two (red and blue) are set to 00.  
To display black, set all color parameters to 00, like this: #000000.  
To display white, set all color parameters to ff, like this: #ffffff.  

**Shades of Gray** - defined using equal values for all three parameters: (#404040, #a0a0a0, #dcdcdc...).

### HSL Colors

HSL stands for hue, saturation, and lightness.  
`hsl(hue, saturation, lightness)`

**Hue** is a degree on the color wheel from 0 to 360. 0 is red, 120 is green, and 240 is blue.  

**Saturation** - the intensity of a color.  
100% is pure color, no shades of gray (hsl(0, 100%, 50%)).  
50% is 50% gray, but you can still see the color.  
0% is completely gray, you can no longer see the color. (hsl(0, 0%, 50%)).  

**Lightness88** - how much light you want to give the color, where 0% means no light (black), 50% means 50% light (neither dark nor light) 100% means full lightness (white).  
hsl(0, 100%, 0%) - black
hsl(0, 100%, 100%) - white
hsl(0, 100%, 50%) - brigth

**Shades of Gray** - defined by setting the hue and saturation to 0, and adjust the lightness from 0% to 100% to get darker/lighter shades: (hsl(0, 0%, 20%), hsl(0, 0%, 40%), hsl(0, 0%, 90%)...)

### HSLA Color

HSLA color values are an extension of HSL color values with an Alpha channel - which specifies the opacity for a color.  
An HSLA color value is specified with:  
`hsla(hue, saturation, lightness, alpha)`

The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (not transparent at all): (v, hsla(9, 100%, 64%, 0.6), hsla(9, 100%, 64%, 1)...)

## HTML Styles - CSS

CSS stands for Cascading Style Sheets, is used to format the layout of a webpage.  

The word cascading means that a style applied to a parent element will also apply to all children elements within the parent.  
So, if you set the color of the body text to "blue", all headings, paragraphs, and other text elements within the body will also get the same color (unless you specify something else)!  

### Using CSS

*CSS can be added to HTML documents in 3 ways:*

* **Inline** - by using the style attribute inside HTML elements.  
An inline CSS is used to apply a unique style to a single HTML element.  
An inline CSS uses the style attribute of an HTML element.  

```html
<h1 style="color:blue;">A Blue Heading</h1>
<p style="color:red;">A red paragraph.</p>
```

* **Internal** - by using a `<style>` element in the `<head>` section.  

An internal CSS is used to define a style for a single HTML page.  
An internal CSS is defined in the `<head>` section of an HTML page, within a `<style>` element.  

```html
<!DOCTYPE html>
<html>
<head>
<style>
body {background-color: powderblue;}
h1   {color: blue;}
p    {color: red;}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

* **External** - by using a `<link>` element to link to an external CSS file.  
An external style sheet is used to define the style for many HTML pages.  
To use an external style sheet, add a link to it in the `<head>` section of each HTML page:  

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

The external style sheet can be written in any text editor. The file must not contain any HTML code, and must be saved with a .css extension.

Here is what the "styles.css" file looks like:

```css
body {
  background-color: powderblue;
}
h1 {
  color: blue;
}
p {
  color: red;
}
```

External style sheets can be referenced with a full URL or with a path relative to the current web page.  

```html
This example uses a full URL to link to a style sheet:
<link rel="stylesheet" href="https://www.w3schools.com/html/styles.css">

This example links to a style sheet located in the html folder on the current web site: 
<link rel="stylesheet" href="/html/styles.css">

This example links to a style sheet located in the same folder as the current page:
<link rel="stylesheet" href="styles.css">
```

The most common way to add CSS, is to keep the styles in external CSS files.  

### CSS Colors, Fonts and Sizes

The CSS **color** property defines the text color to be used.  
The CSS **font-family** property defines the font to be used.  
The CSS **font-size** property defines the text size to be used.  

### CSS Border, Padding and Margin

The CSS **border** property defines a border around an HTML element.  
The CSS **padding** property defines a padding (space) between the text and the border.  
The CSS **margin** property defines a margin (space) outside the border.  

```html
p {
  border: 2px solid powderblue;
  padding: 30px;
  margin: 50px;
}
```

## Links

HTML links are hyperlinks.  
You can click on a link and jump to another document.  

The HTML `<a>` tag defines a hyperlink. It has the following syntax.  
The most important attribute of the `<a>` element is the `href` attribute, which indicates the link's destination.  
The link text is the part that will be visible to the reader.  

```html
<a href="https://www.w3schools.com/">Visit W3Schools.com!</a>
```

By default, the linked page will be displayed in the current browser window.  
To change this, you must specify another `target` for the link.  
The `target` attribute specifies where to open the linked document.

The `target` attribute can have one of the following values:

**_self** - Default. Opens the document in the same window/tab as it was clicked.  
**_blank** - Opens the document in a new window or tab.  
**_parent** - Opens the document in the parent frame.  
**_top** - Opens the document in the full body of the window.  

The `title` attribute specifies extra information about an element.  
The information is most often shown as a tooltip text when the mouse moves over the element.  

```html
<a href="https://www.w3schools.com/html/" title="Go to W3Schools HTML section">Visit our HTML Tutorial</a>
```

### Image as a Link

To use an image as a link, just put the `<img>` tag inside the `<a>` tag:

```html
<a href="default.asp">
<img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;">
</a>
```

### Link to an Email Address

Use `mailto:` inside the `href` attribute to create a link that opens the user's email program (to let them send a new email):

```html
<a href="mailto:someone@example.com">Send email</a>
```

### Button as a Link

To use an HTML button as a link, you have to add some JavaScript code.  
JavaScript allows you to specify what happens at certain events, such as a click of a button:

```html
<button onclick="document.location='default.asp'">HTML Tutorial</button>
```

### HTML Link Colors, Buttons

By default, a link will appear like this (in all browsers):

* An unvisited link is underlined and blue;
* A visited link is underlined and purple;
* An active link is underlined and red.  

You can change the link state colors, by using CSS:

```css
<style>
a:link {
  color: green;
  background-color: transparent;
  text-decoration: none;
}

a:visited {
  color: pink;
  background-color: transparent;
  text-decoration: none;
}

a:hover {
  color: red;
  background-color: transparent;
  text-decoration: underline;
}

a:active {
  color: yellow;
  background-color: transparent;
  text-decoration: underline;
}
</style>
```

* A link can also be styled as a button, by using CSS:

```css
<style>
a:link, a:visited {
  background-color: #f44336;
  color: white;
  padding: 15px 25px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
}

a:hover, a:active {
  background-color: red;
}
</style>
```

### HTML Links - Create Bookmarks

HTML links can be used to create bookmarks, so that readers can jump to specific parts of a web page.  
Bookmarks can be useful if a web page is very long.  
To create a bookmark - first create the bookmark, then add a link to it.  
When the link is clicked, the page will scroll down or up to the location with the bookmark.

Example:  
First, use the id attribute to create a bookmark:

```html
<h2 id="C4">Chapter 4</h2>
```

Then, add a link to the bookmark ("Jump to Chapter 4"), from within the same page:

```html
<a href="#C4">Jump to Chapter 4</a>
```

You can also add a link to a bookmark on another page:

```html
<a href="html_demo.html#C4">Jump to Chapter 4</a>
```

## Images

The HTML `<img>` tag is used to embed an image in a web page.  
Images are not technically inserted into a web page; images are linked to web pages.  
The `<img>` tag creates a holding space for the referenced image.  
The `<img>` tag is empty, it contains attributes only, and does not have a closing tag.  

The `<img>` tag has two required attributes:

* `src` - Specifies the path to the image;  
* `alt` - Specifies an alternate text for the image, if the user for some reason cannot view it.  

```html
<img src="url" alt="alternatetext">
```

The `<img>` tag can have additional attributes:

* `style` - Specifies the width and height of an image.

```html
<img src="img_girl.jpg" alt="Girl in a jacket" style="width:500px;height:600px;">
```

Alternatively, you can use the `width` and `height` attributes:

```html
<img src="img_girl.jpg" alt="Girl in a jacket" width="500" height="600">
```

Note: Always specify the width and height of an image. If width and height are not specified, the web page might flicker while the image loads.  
However, we suggest using the style attribute.  

```html
<!DOCTYPE html>
<html>
<head>
<style>
img {
  width: 100%;
}
</style>
</head>
<body>

<img src="html5.gif" alt="HTML5 Icon" width="128" height="128">

<img src="html5.gif" alt="HTML5 Icon" style="width:128px;height:128px;">

</body>
</html>
```

Use the CSS float property to let the image float to the right or to the left of a text:

```html
<p><img src="smiley.gif" alt="Smiley face" style="float:right;width:42px;height:42px;">
The image will float to the right of the text.</p>
```

### Common Image Formats

| Abbreviation | File Format | File Extension |
| ------------ | ----------- | -------------- |
| APNG | Animated Portable Network Graphics | .apng |
| GIF | Graphics Interchange Format | .gif |
| ICO | Microsoft Icon | .ico, .cur |
| JPEG | Joint Photographic Expert Group image | .jpg, .jpeg, .jfif, .pjpeg, .pjp |
| PNG | Portable Network Graphics | .png |
| SVG | Scalable Vector Graphics | .svg |

### Image Maps

The HTML `<map>` tag defines an image map.  
An image map is an image with clickable areas.  
The areas are defined with one or more `<area>` tags.  

```html
<img src="workplace.jpg" alt="Workplace" usemap="#workmap">

<map name="workmap">
  <area shape="rect" coords="34,44,270,350" alt="Computer" href="computer.htm">
  <area shape="rect" coords="290,172,333,250" alt="Phone" href="phone.htm">
  <area shape="circle" coords="337,300,44" alt="Coffee" href="coffee.htm">
</map>
```

* `usemap` attribute - used to create a relationship between the image and the image map.  
* `<map>` element is used to create an image map, and is linked to the image by using the required name attribute;
* `name` attribute must have the same value as the `<img>`'s usemap attribute;  
* `<area>` element - define the shape of the clickable area:
  * `rect` - defines a rectangular region;  
  * `circle` - defines a circular region;  
  * `poly` - defines a polygonal region;  
  * `default` - defines the entire region.  
* `coords` - define some coordinates to be able to place the clickable area onto the image.   

### Background Images

To add a background image on an HTML element, use the HTML `style` attribute and the CSS `background-image` property:

```html
<div style="background-image: url('img_girl.jpg');">
```

You can also specify the background image in the `<style>` element, in the `<head>` section:

```html
<style>
div {
  background-image: url('img_girl.jpg');
}
</style>
```

If you want the entire page to have a background image, you must specify the background image on the `<body>` element:

```html
<style>
body {
  background-image: url('img_girl.jpg');
}
</style>
```

**Background Repeat**:  
If the background image is smaller than the element, the image will repeat itself, horizontally and vertically, until it reaches the end of the element.  
To avoid the background image from repeating itself, set the `background-repeat` property to `no-repeat`:  

```html
<style>
body {
  background-image: url('example_img_girl.jpg');
  background-repeat: no-repeat;
}
</style>
```

**Background Cover**:  
If you want the background image to cover the entire element, you can set the `background-size` property to `cover`.  
Also, to make sure the entire element is always covered, set the `background-attachment` property to `fixed`.  
This way, the background image will cover the entire element, with no stretching (the image will keep its original proportions):  

```html
<style>
body {
  background-image: url('img_girl.jpg');
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
}
</style>
```

**Background Stretch**:  
If you want the background image to stretch to fit the entire element, you can set the `background-size` property to `100% 100%`:

```html
<style>
body {
  background-image: url('img_girl.jpg');
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: 100% 100%;
}
</style>
```

### HTML `<picture>` Element

The HTML `<picture>` element allows you to display different pictures for different devices or screen sizes.  
The `<picture>` element contains one or more `<source>` elements, each referring to different images through the `srcset` attribute.  
This way the browser can choose the image that best fits the current view and/or device.  

Each `<source>` element has a media attribute that defines when the image is the most suitable.

```html
<picture>
  <source media="(min-width: 650px)" srcset="img_food.jpg">
  <source media="(min-width: 465px)" srcset="img_car.jpg">
  <img src="img_girl.jpg">
</picture>
```

Note: Always specify an `<img>` element as the last child element of the `<picture>` element.  
The `<img>` element is used by browsers that do not support the `<picture>` element, or if none of the `<source>` tags match.



