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

**When to use the Picture Element**:  

1. Bandwidth
If you have a small screen or device, it is not necessary to load a large image file.  
The browser will use the first `<source>` element with matching attribute values, and ignore any of the following elements.

2. Format Support
Some browsers or devices may not support all image formats.  
By using the `<picture>` element, you can add images of all formats, and the browser will use the first format it recognizes, and ignore any of the following elements.

## Favicon

A favicon is a small image displayed next to the page title in the browser tab.  
A common name for a favicon image is "favicon.ico".  
Next, add a `<link>` element to your "index.html" file, after the `<title>` element, like this:

```html
<html>
<head>
  <title>My Page Title</title>
  <link rel="icon" type="image/x-icon" href="/images/favicon.ico">
</head>
```

## Tables

A table in HTML consists of table cells inside rows and columns.  

Each table cell is defined by a `<td>` and a `</td>` tag.  
Everything between `<td>` and `</td>` are the content of the table cell.  

Each table row starts with a `<tr>` and end with a `</tr>` tag.  
You can have as many rows as you like in a table, just make sure that the number of cells are the same in each row.  

Sometimes you want your cells to be headers, in those cases use the `<th>` tag instead of the `<td>` tag.  
By default, the text in `<th>` elements are bold and centered, but you can change that with CSS.

```html
<table>
  <tr>
    <th>Person 1</th>
    <th>Person 2</th>
    <th>Person 3</th>
  </tr>
  <tr>
    <td>Emil</td>
    <td>Tobias</td>
    <td>Linus</td>
  </tr>
  <tr>
    <td>16</td>
    <td>14</td>
    <td>10</td>
  </tr>
</table>
```

**HTML Table Tags**:  
| Tag | Description |
| --- | ----------- |
| `<table>` | Defines a table |
| `<th>` | Defines a header cell in a table |
| `<tr>` | Defines a row in a table |
| `<td>` | Defines a cell in a table |
| `<caption>` | Defines a table caption |
| `<colgroup>` | Specifies a group of one or more columns in a table for formatting |
| `<col>` | Specifies column properties for each column within a `<colgroup>` element |
| `<thead>` | Groups the header content in a table |
| `<tbody>` | Groups the body content in a table |
| `<tfoot>` | Groups the footer content in a table |

### Table Borders

HTML tables can have borders of different styles and shapes.  
When you add a border to a table, you also add borders around each table cell.  
To add a border, use the CSS `border` property on `table`, `th`, and `td` elements:  

```html
table, th, td {
  border: 1px solid black;
}
```

**Collapsed Table Borders**:  
To avoid having double borders like in the example above, set the CSS `border-collapse` property to `collapse`.

```thml
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
```

**Style Table Borders**:  
If you set a background color of each cell, and give the border a white color (the same as the document background), you get the impression of an invisible border:

```html
table, th, td {
  border: 1px solid white;
  border-collapse: collapse;
}
th, td {
  background-color: #96D4D4;
}
```

**Round Table Borders**:  
With the `border-radius` property, the borders get rounded corners:

```
html
table, th, td {
  border: 1px solid black;
  border-radius: 10px;
}
```

Skip the border around the table by leaving out `table` from the css selector:

```html
th, td {
  border: 1px solid black;
  border-radius: 10px;
}
```

**Dotted Table Borders**:  
With the `border-style` property, you can set the appereance of the border.  
The following values are allowed:

* dotted
* dashed
* solid
* double
* groove
* ridge
* inset
* outset
* none
* hidden

```html
th, td {
  border-style: dotted;
}
```

**Border Color**:  
With the border-color property, you can set the color of the border. 

```html
 th, td {
  border-color: #96D4D4;
}
```

### Table Sizes

Use the `style` attribute with the `width` or `height` properties to specify the size of a table, row or column.  
To set the width of a table, add the `style` attribute to the `<table>` element.  
To set the size of a specific column, add the `style` attribute on a `<th>` or `<td>` element.  
To set the height of a specific row, add the `style` attribute on a table row element.  

```html
<table style="width:100%">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr style="height:200px">
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
</table>
```

### Table Headers

HTML tables can have headers for each column or row, or for many columns/rows.  
Table headers are defined with `th` elements, each `th` element represents a table cell.  

**Vertical Table Headers**:  
To use the first column as table headers, define the first cell in each row as a `th` element:  

```html
<table>
  <tr>
    <th>Firstname</th>
    <td>Jill</td>
    <td>Eve</td>
  </tr>
  <tr>
    <th>Lastname</th>
    <td>Smith</td>
    <td>Jackson</td>
  </tr>
  <tr>
    <th>Age</th>
    <td>94</td>
    <td>50</td>
  </tr>
</table>
```

**Align Table Headers**:  
By default, table headers are bold and centered.  
To left-align the table headers, use the CSS text-align property:

```html
<style>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
th {
  text-align: left;
}
</style>
```

**Header for Multiple Columns**:  
HTML tables can have cells that spans over multiple rows and/or columns.  

To make a cell span over multiple columns, use the `colspan` attribute on the `<th>` element.  
The value of the `colspan` attribute represents the number of columns to span.  

```html
<table>
  <tr>
    <th colspan="2">Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
</table>
```

To make a cell span over multiple rows, use the `rowspan` attribute:

```html
<table>
  <tr>
    <th>Name</th>
    <td>Jill</td>
  </tr>
  <tr>
    <th rowspan="2">Phone</th>
    <td>555-1234</td>
  </tr>
  <tr>
    <td>555-8745</td>
</tr>
</table>
```

**Table Caption**:  
You can add a caption that serves as a heading for the entire table.  
To add a caption to a table, use the `<caption>` tag.  
The `<caption>` tag should be inserted immediately after the `<table>` tag.  

```html
<table style="width:100%">
  <caption>Monthly savings</caption>
  <tr>
    <th>Month</th>
    <th>Savings</th>
```

### Table Padding & Spacing

HTML tables can adjust the padding inside the cells, and also the space between the cells.  

**Table - Cell Padding**:  
Cell padding is the space between the cell edges and the cell content.  
By default the padding is set to 0.  
To add padding on table cells, use the CSS padding property:  

```html
th, td {
  padding: 15px;
}
```

To add padding only above the content, use the `padding-top` property.  
And the others sides with the `padding-bottom`, `padding-left`, and `padding-right` properties:  

```html
th, td {
  padding-top: 10px;
  padding-bottom: 20px;
  padding-left: 30px;
  padding-right: 40px;
}
```

**Table - Cell Spacing**:  
Cell spacing is the space between each cell.  
By default the space is set to 2 pixels.  
To change the space between table cells, use the CSS `border-spacing` property on the table element:  

```html
table {
  border-spacing: 30px;
}
```

### Table Styling

**Zebra Stripes**:  
If you add a background color on every other table row, you will get a nice zebra stripes effect.  

To style every other table row element, use the `:nth-child(even)` selector like this:

```html
tr:nth-child(even) {
  background-color: #D6EEEE;
}
```

Note: If you use (`odd`) instead of (`even`), the styling will occur on row 1,3,5 etc. instead of 2,4,6 etc.  

**Vertical Zebra Stripes**:  
To make vertical zebra stripes, style every other column, instead of every other row.  
Set the `:nth-child(even)` for table data elements like this:  

```html
td:nth-child(even), th:nth-child(even) {
  background-color: #D6EEEE;
}
```

Note: Put the `:nth-child()` selector on both `th` and `td` elements if you want to have the styling on both headers and regular table cells.  

**Combine Vertical and Horizontal Zebra Stripes**:  
You can combine the styling from the two examples above and you will have stripes on every other row and every other column.  
If you use a transparent color you will get an overlapping effect.  
Use an rgba() color to specify the transparency of the color:  

```html
tr:nth-child(even) {
  background-color: rgba(150, 212, 212, 0.4);
}

th:nth-child(even),td:nth-child(even) {
  background-color: rgba(150, 212, 212, 0.4);
}
```

**Horizontal Dividers**:  
If you specify borders only at the bottom of each table row, you will have a table with horizontal dividers.  
Add the `border-bottom` property to all `tr` elements to get horizontal dividers:

```html
tr {
  border-bottom: 1px solid #ddd;
}
```

**Hoverable Table**:  
Use the `:hover` selector on `tr` to highlight table rows on mouse over:

```html
<!DOCTYPE html>
<html>
<head>
<style>
table {
  border-collapse: collapse;
  width: 100%;
}

th, td {
  padding: 8px;
  text-align: left;
  border-bottom: 1px solid #DDD;
}

tr:hover {background-color: #D6EEEE;}
</style>
```

**Table Colgroup**:  
The `<colgroup>` element is used to style specific columns of a table.  
If you want to style the two first columns of a table, use the `<colgroup>` and `<col>` elements.  

The `<colgroup>` element should be used as a container for the column specifications.  
Each group are specified with a `<col>` element.  
The `span` attribute specifies how many columns that gets the style.  
The `style` attribute specifies the style to give the columns.  

The `<colgroup>` tag must be a child of a `<table>` element and should be placed before any other table elements, like `<thead>`, `<tr>`, `<td>` etc., but after the `<caption>` element, if present.
  
```html
<table>
  <colgroup>
    <col span="2" style="background-color: #D6EEEE">
  </colgroup>
  <tr>
    <th>MON</th>
    <th>TUE</th>
    <th>WED</th>
    <th>THU</th>
...
```

There are only a very limited selection of CSS properties that are allowed to be used in the colgroup:

* width property
* visibility property
* background properties
* border properties

All other CSS properties will have no effect on your tables.

**Multiple Col Elements**:  
If you want to style more columns with different styles, use more `<col>` elements inside the `<colgroup>`:

```html
<table>
  <colgroup>
    <col span="2" style="background-color: #D6EEEE">
    <col span="3" style="background-color: pink">
  </colgroup>
  <tr>
    <th>MON</th>
    <th>TUE</th>
    <th>WED</th>
    <th>THU</th>
...
```

**Empty Colgroups**:  
If you want to style columns in the middle of a table, insert a "empty" `<col>` element (with no styles) for the columns before:  

```html
<table>
  <colgroup>
    <col span="3">
    <col span="2" style="background-color: pink">
  </colgroup>
  <tr>
    <th>MON</th>
    <th>TUE</th>
    <th>WED</th>
    <th>THU</th>
...
```

**Hide Columns**:  
You can hide columns with the `visibility: collapse` property:  

```html
<table>
  <colgroup>
    <col span="2">
    <col span="3" style="visibility: collapse">
  </colgroup>
  <tr>
    <th>MON</th>
    <th>TUE</th>
    <th>WED</th>
    <th>THU</th>
...
```

## HTML Lists

**Unordered HTML List**:  
An unordered list starts with the `<ul>` tag.  
Each list item starts with the `<li>` tag.  
The list items will be marked with bullets (small black circles) by default:

```html
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

The CSS `list-style-type` property is used to define the style of the list item marker.  
It can have one of the following values:

| Value | Description |
| ----- | ----------- |
| disc | Sets the list item marker to a bullet (default) |
| circle | Sets the list item marker to a circle |
| square | Sets the list item marker to a square |
| none | The list items will not be marked |

```html
<ul style="list-style-type:circle;">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

**Ordered HTML List**:  
An ordered list starts with the `<ol>` tag. Each list item starts with the `<li>` tag.  
The list items will be marked with numbers by default:  

```html
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

The `type` attribute of the `<ol>` tag, defines the type of the list item marker:
| Type | Description |
| ---- | ----------- |
| type="1" | The list items will be numbered with numbers (default) |
| type="A" | The list items will be numbered with uppercase letters |
| type="a" | The list items will be numbered with lowercase letters |
| type="I" | The list items will be numbered with uppercase roman numbers |
| type="i" | The list items will be numbered with lowercase roman numbers |

```html
<ol type="A">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

By default, an ordered list will start counting from 1.  
If you want to start counting from a specified number, you can use the `start` attribute:

```html
<ol start="50">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

**Nested HTML Lists**:  
Lists can be nested (list inside list):

```html
<ol>
  <li>Coffee</li>
  <li>Tea
    <ol>
      <li>Black tea</li>
      <li>Green tea</li>
    </ol>
  </li>
  <li>Milk</li>
</ol>
```

**Description Lists**:  
A description list is a list of terms, with a description of each term.  
The `<dl>` tag defines the description list, the `<dt>` tag defines the term (name), and the `<dd>` tag describes each term:

```html
<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>
```

**HTML List Tags**:  
| Tag | Description |
| --- | ----------- |
| `<ul>` | Defines an unordered list |
| `<ol>` | Defines an ordered list |
| `<li>` | Defines a list item |
| `<dl>` | Defines a description list |
| `<dt>` | Defines a term in a description list |
| `<dd>` | Describes the term in a description list |

## HTML Block and Inline Elements

Every HTML element has a default display value, depending on what type of element it is.  
There are two display values: block and inline.  

### Block-level Elements

A block-level element always starts on a new line.  
A block-level element always takes up the full width available (stretches out to the left and right as far as it can).  
A block level element has a top and a bottom margin, whereas an inline element does not.  

Here are the block-level elements in HTML:

`<address>` `<article>` `<aside>` `<blockquote>` `<canvas>` `<dd>` `<div>` `<dl>` `<dt>`  
`<fieldset>` `<figcaption>` `<figure>` `<footer>` `<form>` `<h1>`-`<h6>` `<header>` `<hr>`  
`<li>` `<main>` `<nav>` `<noscript>` `<ol>` `<p>` `<pre>` `<section>` `<table>` `<tfoot>` `<ul>`  

### Inline Elements

An inline element does not start on a new line.  
An inline element only takes up as much width as necessary.  
An inline element cannot contain a block-level element!  

Here are the inline elements in HTML:

`<a>` `<abbr>` `<acronym>` `<b>` `<bdo>` `<big>` `<br>` `<button>` `<cite>` `<code>` `<dfn>`  
`<em>` `<i>` `<img>` `<input>` `<kbd>` `<label>` `<map>` `<object>` `<output>` `<q>` `<samp>`  
`<script>` `<select>` `<small>` `<span>` `<strong>` `<sub>` `<sup>` `<textarea>` `<time>` `<tt>` `<var>`  

**The `<div>` Element**:  
The `<div>` element is often used as a container for other HTML elements.  
The `<div>` element has no required attributes, but style, class and id are common.  
When used together with CSS, the `<div>` element can be used to style blocks of content:  

```html
<div style="background-color:black;color:white;padding:20px;">
  <h2>London</h2>
  <p>London is the capital city of England. It is the most populous city in the United Kingdom, with a metropolitan area of over 13 million inhabitants.</p>
</div>
```

**The `<span>` Element**:  
The `<span>` element is an inline container used to mark up a part of a text, or a part of a document.  
The `<span>` element has no required attributes, but style, class and id are common.  
When used together with CSS, the `<span>` element can be used to style parts of the text:

```html
<p>My mother has <span style="color:blue;font-weight:bold">blue</span> eyes and my father has <span style="color:darkolivegreen;font-weight:bold">dark green</span> eyes.</p>
```

## HTML class Attribute

The HTML `class` attribute is used to specify a class for an HTML element.  
Multiple HTML elements can share the same class.  
Tip: The class attribute can be used on any HTML element.  
Note: The class name is case sensitive!  

In the following example we have three `<div>` elements with a class attribute with the value of "city".  
All of the three `<div>` elements will be styled equally according to the `.city` style definition in the `head` section:

```html
<!DOCTYPE html>
<html>
<head>
<style>
.city {
  background-color: tomato;
  color: white;
  border: 2px solid black;
  margin: 20px;
  padding: 20px;
}
</style>
</head>
<body>

<div class="city">
  <h2>London</h2>
  <p>London is the capital of England.</p>
</div>

<div class="city">
  <h2>Paris</h2>
  <p>Paris is the capital of France.</p>
</div>

<div class="city">
  <h2>Tokyo</h2>
  <p>Tokyo is the capital of Japan.</p>
</div>

</body>
</html>
```

In the following example we have two `<span>` elements with a class attribute with the value of "note".  
Both `<span>` elements will be styled equally according to the `.note` style definition in the head section:

```html
<!DOCTYPE html>
<html>
<head>
<style>
.note {
  font-size: 120%;
  color: red;
}
</style>
</head>
<body>

<h1>My <span class="note">Important</span> Heading</h1>
<p>This is some <span class="note">important</span> text.</p>

</body>
</html>
```

**The Syntax For Class**:  
To create a class; write a period (.) character, followed by a class name.  
Then, define the CSS properties within curly braces {}.  

**Multiple Classes**:  
HTML elements can belong to more than one class.  
To define multiple classes, separate the class names with a space, e.g. `<div class="city main">`.  
The element will be styled according to all the classes specified.  
In the following example, the first `<h2>` element belongs to both the city class and also to the main class, and will get the CSS styles from both of the classes.  

**Different Elements Can Share Same Class**:  
Different HTML elements can point to the same class name.  
In the following example, both `<h2>` and `<p>` points to the "city" class and will share the same style.  

## HTML id Attribute

The id attribute specifies a unique id for an HTML element.  
The value of the id attribute must be unique within the HTML document.  
The id attribute is used to point to a specific style declaration in a style sheet.  
It is also used by JavaScript to access and manipulate the element with the specific id.  

The syntax for id is: write a hash character (#), followed by an id name.  
Then, define the CSS properties within curly braces {}.

The id name is case sensitive!  
The id name must contain at least one character, cannot start with a number, and must not contain whitespaces (spaces, tabs, etc.).  

In the following example we have an `<h1>` element that points to the id name "myHeader".  
This `<h1>` element will be styled according to the #myHeader style definition in the head section:  

```html
<!DOCTYPE html>
<html>
<head>
<style>
#myHeader {
  background-color: lightblue;
  color: black;
  padding: 40px;
  text-align: center;
}
</style>
</head>
<body>

<h1 id="myHeader">My Header</h1>

</body>
</html>
```

**Difference Between Class and ID**:  
A class name can be used by multiple HTML elements, while an id name must only be used by one HTML element within the page:

```html
<style>
/* Style the element with the id "myHeader" */
#myHeader {
  background-color: lightblue;
  color: black;
  padding: 40px;
  text-align: center;
}

/* Style all elements with the class name "city" */
.city {
  background-color: tomato;
  color: white;
  padding: 10px;
}
</style>

<!-- An element with a unique id -->
<h1 id="myHeader">My Cities</h1>

<!-- Multiple elements with same class -->
<h2 class="city">London</h2>
<p>London is the capital of England.</p>

<h2 class="city">Paris</h2>
<p>Paris is the capital of France.</p>

<h2 class="city">Tokyo</h2>
<p>Tokyo is the capital of Japan.</p>
```

### HTML Bookmarks with ID and Links

HTML bookmarks are used to allow readers to jump to specific parts of a webpage.  
Bookmarks can be useful if your page is very long.  
To use a bookmark, you must first create it, and then add a link to it.  
Then, when the link is clicked, the page will scroll to the location with the bookmark.

Example:  
First, create a bookmark with the id attribute:

```html
<h2 id="C4">Chapter 4</h2>
```

Then, add a link to the bookmark ("Jump to Chapter 4"), from within the same page:

```html
<a href="#C4">Jump to Chapter 4</a>
```

Or, add a link to the bookmark ("Jump to Chapter 4"), from another page:

```html
<a href="html_demo.html#C4">Jump to Chapter 4</a>
```

**Using The id Attribute in JavaScript**:  
The id attribute can also be used by JavaScript to perform some tasks for that specific element.  
JavaScript can access an element with a specific id with the getElementById() method:  

```html
<script>
function displayResult() {
  document.getElementById("myHeader").innerHTML = "Have a nice day!";
}
</script>
```

<!-- ## HTML Iframes -->

An HTML iframe is used to display a web page within a web page.  
The HTML `<iframe>` tag specifies an inline frame.  
An inline frame is used to embed another document within the current HTML document.  

```html
<iframe src="url" title="description"></iframe>
```

It is a good practice to always include a title attribute for the `<iframe>`.  
This is used by screen readers to read out what the content of the iframe is.  

**Iframe - Set Height and Width**:  
Use the `height` and `width` attributes to specify the size of the iframe.  
The height and width are specified in pixels by default:

```html
<iframe src="demo_iframe.htm" height="200" width="300" title="Iframe Example"></iframe>
```

Or you can add the style attribute and use the CSS height and width properties:

```html
<iframe src="demo_iframe.htm"    title="Iframe Example"></iframe>
```

**Iframe - Remove the Border**:  
By default, an iframe has a border around it.  
To remove the border, add the `style` attribute and use the CSS `border` property:

```html
<iframe src="demo_iframe.htm" style="border:none;" title="Iframe Example"></iframe>
```

With CSS, you can also change the size, style and color of the iframe's border:

```html
<iframe src="demo_iframe.htm" style="border:2px solid red;" title="Iframe Example"></iframe>
```

**Iframe - Target for a Link**:  
An iframe can be used as the target frame for a link.  
The `target` attribute of the link must refer to the `name` attribute of the iframe:

```html
<iframe src="demo_iframe.htm" name="iframe_a" title="Iframe Example"></iframe>

<p><a href="https://www.w3schools.com" target="iframe_a">W3Schools.com</a></p>
```

## HTML JavaScript

**The HTML `<script>` Tag**:  
The HTML `<script>` tag is used to define a client-side script (JavaScript).  
The `<script>` element either contains script statements, or it points to an external script file through the src attribute.  
Common uses for JavaScript are image manipulation, form validation, and dynamic changes of content.  
To select an HTML element, JavaScript most often uses the `document.getElementById()` method.  

**The HTML `<noscript>` Tag**:  
The HTML `<noscript>` tag defines an alternate content to be displayed to users that have disabled scripts in their browser or have a browser that doesn't support scripts:

```html
<script>
document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
<noscript>Sorry, your browser does not support JavaScript!</noscript>
```

## HTML File Paths

A file path describes the location of a file in a web site's folder structure.

**Absolute File Paths** - An absolute file path is the full URL to a file:

```html
<img src="https://www.w3schools.com/images/picture.jpg" alt="Mountain">
```

**Relative File Paths** - A relative file path points to a file relative to the current page.  
In the following example, the file path points to a file in the images folder located at the root of the current web:

```html
<img src="/images/picture.jpg" alt="Mountain">
```

It is best practice to use relative file paths (if possible).  
When using relative file paths, your web pages will not be bound to your current base URL.  
All links will work on your own computer (localhost) as well as on your current public domain and your future public domains.  

## HTML - The Head Element

The HTML `<head>` element is a container for the following elements: `<title>`, `<style>`, `<meta>`, `<link>`, `<script>`, and `<base>`.  

The `<head>` element is a container for metadata (data about data) and is placed between the `<html>` tag and the `<body>` tag.  
HTML metadata is data about the HTML document. Metadata is not displayed.  

Metadata typically define the document title, character set, styles, scripts, and other meta information.  

**HTML head Elements**:  
| Tag | Description |
| --- | ----------- |
| `<head>` | Defines information about the document |
| `<title>` | Defines the title of a document |
| `<base>` | Defines a default address or a default target for all links on a page |
| `<link>` | Defines the relationship between a document and an external resource |
| `<meta>` | Defines metadata about an HTML document |
| `<script>` | Defines a client-side script |
| `<style>` | Defines style information for a document |

### The HTML `<title>` Element

The `<title>` element defines the title of the document.  
The title must be text-only, and it is shown in the browser's title bar or in the page's tab.  

The `<title>` element is required in HTML documents!
The contents of a page title is very important for search engine optimization (SEO)!  
The page title is used by search engine algorithms to decide the order when listing pages in search results.  

The `<title>` element:

* defines a title in the browser toolbar
* provides a title for the page when it is added to favorites
* displays a title for the page in search engine-results
So, try to make the title as accurate and meaningful as possible!

### The HTML `<style>` Element

The `<style>` element is used to define style information for a single HTML page.

### The HTML `<link>` Element

The `<link>` element defines the relationship between the current document and an external resource.  
The `<link>` tag is most often used to link to external style sheets:

```html
<link rel="stylesheet" href="mystyle.css">
```

### The HTML `<meta>` Element

The `<meta>` element is typically used to specify the character set, page description, keywords, author of the document, and viewport settings.  
The metadata will not be displayed on the page, but are used by browsers (how to display content or reload page), by search engines (keywords), and other web services.

Examples:  
Define the character set used:  
`<meta charset="UTF-8">`

Define keywords for search engines:  
`<meta name="keywords" content="HTML, CSS, JavaScript">`

Define a description of your web page:  
`<meta name="description" content="Free Web tutorials">`

Define the author of a page:  
`<meta name="author" content="John Doe">`

Refresh document every 30 seconds:  
`<meta http-equiv="refresh" content="30">`

Setting the viewport to make your website look good on all devices:  
`<meta name="viewport" content="width=device-width, initial-scale=1.0">`

### Setting The Viewport

The viewport is the user's visible area of a web page.  
It varies with the device - it will be smaller on a mobile phone than on a computer screen.  
You should include the following `<meta>` element in all your web pages:

`<meta name="viewport" content="width=device-width, initial-scale=1.0">`

This gives the browser instructions on how to control the page's dimensions and scaling.  
The `width=device-width` part sets the width of the page to follow the screen-width of the device (which will vary depending on the device).  
The `initial-scale=1.0` part sets the initial zoom level when the page is first loaded by the browser.

### The HTML `<script>` Element

The `<script>` element is used to define client-side JavaScripts.

### The HTML `<base>` Element

The `<base>` element specifies the base URL and/or target for all relative URLs in a page.  
The `<base>` tag must have either an `href` or a `target` attribute present, or both.  

There can only be one single `<base>` element in a document!

```html
<head>
<base href="https://www.w3schools.com/" target="_blank">
</head>

<body>
<img src="images/stickman.gif" width="24" height="39" alt="Stickman">
<a href="tags/tag_base.asp">HTML base Tag</a>
</body>
```

## HTML Layout Elements and Techniques

Websites often display content in multiple columns (like a magazine or a newspaper).  

**HTML Layout Elements**:  
HTML has several  c elements that define the different parts of a web page:

* `<header>` - Defines a header for a document or a section
* `<nav>` - Defines a set of navigation links
* `<section>` - Defines a section in a document
* `<article>` - Defines an independent, self-contained content
* `<aside>` - Defines content aside from the content (like a sidebar)
* `<footer>` - Defines a footer for a document or a section
* `<details>` - Defines additional details that the user can open and close on demand
* `<summary>` - Defines a heading for the `<details>` element

**HTML Layout Techniques**:  
There are four different techniques to create multicolumn layouts. Each technique has its pros and cons:

* CSS framework
* CSS float property
* CSS flexbox
* CSS grid

## HTML Computer Code Elements

HTML contains several elements for defining user input and computer code.

* The `<kbd>` element defines keyboard input
* The `<samp>` element defines sample output from a computer program
* The `<code>` element defines a piece of computer code
* The `<var>` element defines a variable in programming or in a mathematical expression
* The `<pre>` element defines preformatted text

### HTML `<code>` For Computer Code

The HTML `<code>` element  is used to define a piece of computer code.  
The content inside is displayed in the browser's default monospace font.  

```html
<code>
x = 5;
y = 6;
z = x + y;
</code>
```

Notice that the `<code>` element does not preserve extra whitespace and line-breaks.  
To fix this, you can put the `<code>` element inside a `<pre>` element:

### HTML `<kbd>` For Keyboard Input

The HTML `<kbd>` element is used to define keyboard input.  
The content inside is displayed in the browser's default monospace font.

```html
<p>Save the document by pressing <kbd>Ctrl + S</kbd></p>
```

### HTML `<samp>` For Program Output

The HTML `<samp>` element is used to define sample output from a computer program.  
The content inside is displayed in the browser's default monospace font.

```html
<p>Message from my computer:</p>
<p><samp>File not found.<br>Press F1 to continue</samp></p>
```

### HTML `<var>` For Variables

The HTML `<var>` element  is used to define a variable in programming or in a mathematical expression.  
The content inside is typically displayed in italic.

```html
<p>The area of a triangle is: 1/2 x <var>b</var> x <var>h</var>, where <var>b</var> is the base, and <var>h</var> is the vertical height.</p>
```

## HTML Semantic Elements

A semantic element clearly describes its meaning to both the browser and the developer.  
Examples of non-semantic elements: `<div>` and `<span>` - Tells nothing about its content.  
Examples of semantic elements: `<form>`, `<table>`, and `<article>` - Clearly defines its content.

Below is a list of some of the semantic elements in HTML.

| Tag | Description |
| `<article>` | Defines independent, self-contained content |
| `<aside>` | Defines content aside from the page content |
| `<details>` | Defines additional details that the user can view or hide |
| `<figcaption>` | Defines a caption for a `<figure>` element |
| `<figure>` | Specifies self-contained content, like illustrations, diagrams, photos, code listings, etc. |
| `<footer>` | Defines a footer for a document or section |
| `<header>` | Specifies a header for a document or section |
| `<main>` | Specifies the main content of a document tн может повторяться|
| `<mark>` | Defines marked/highlighted text |
| `<nav>` | Defines navigation links |
| `<section>` | Defines a section in a document |
| `<summary>` | Defines a visible heading for a `<details>` element |
| `<time>` | Defines a date/time |

### HTML `<section>` Element

The `<section>` element defines a section in a document.  
Examples of where a `<section>` element can be used:

* Chapters
* Introduction
* News items
* Contact information

A web page could normally be split into sections for introduction, content, and contact information.

### HTML `<article>` Element

The `<article>` element specifies independent, self-contained content.  
An article should make sense on its own, and it should be possible to distribute it independently from the rest of the web site.  
Examples of where the `<article>` element can be used:

* Forum posts
* Blog posts
* User comments
* Product cards
* Newspaper articles

```html
<html>
<head>
<style>
.all-browsers {
  margin: 0;
  padding: 5px;
  background-color: lightgray;
}

.all-browsers > h1, .browser {
  margin: 10px;
  padding: 5px;
}

.browser {
  background: white;
}

.browser > h2, p {
  margin: 4px;
  font-size: 90%;
}
</style>
</head>
<body>

<article class="all-browsers">
  <h1>Most Popular Browsers</h1>
  <article class="browser">
    <h2>Google Chrome</h2>
    <p>Google Chrome is a web browser developed by Google, released in 2008. Chrome is the world's most popular web browser today!</p>
  </article>
```

### HTML `<header>` Element

The `<header>` element represents a container for introductory content or a set of navigational links.  
A `<header>` element typically contains:

* one or more heading elements (`<h1> - <h6>`)
* logo or icon
* authorship information

Note: You can have several `<header>` elements in one HTML document.  
However, `<header>` cannot be placed within a `<footer>`, `<address>` or another `<header>` element.

```html
<article>
  <header>
    <h1>What Does WWF Do?</h1>
    <p>WWF's mission:</p>
  </header>
  <p>WWF's mission is to stop the degradation of our planet's natural environment,
  and build a future in which humans live in harmony with nature.</p>
</article>
```

### HTML `<footer>` Element

The `<footer>` element defines a footer for a document or section.  
A `<footer>` element typically contains:

* authorship information
* copyright information
* contact information
* sitemap
* back to top links
* related documents

You can have several `<footer>` elements in one document.

```html
<footer>
  <p>Author: Hege Refsnes</p>
  <p><a href="mailto:hege@example.com">hege@example.com</a></p>
</footer>
```

### HTML `<nav>` Element

The `<nav>` element defines a set of navigation links.  
Notice that NOT all links of a document should be inside a `<nav>` element.  
The `<nav>` element is intended only for major block of navigation links.  

```html
<nav>
  <a href="/html/">HTML</a> |
  <a href="/css/">CSS</a> |
  <a href="/js/">JavaScript</a> |
  <a href="/jquery/">jQuery</a>
</nav>
```

### HTML `<aside>` Element

The `<aside>` element defines some content aside from the content it is placed in (like a sidebar).  
The `<aside>` content should be indirectly related to the surrounding content.  

```html
<html>
  <head>
<style>
aside {
  width: 30%;
  padding-left: 15px;
  margin-left: 15px;
  float: right;
  font-style: italic;
  background-color: lightgray;
}
</style>
</head>
<body>

<p>My family and I visited The Epcot center this summer. The weather was nice, and Epcot was amazing! I had a great summer together with my family!</p>

<aside>
<p>The Epcot center is a theme park at Walt Disney World Resort featuring exciting attractions, international pavilions, award-winning fireworks and seasonal special events.</p>
</aside>

<p>My family and I visited The Epcot center this summer. The weather was nice, and Epcot was amazing! I had a great summer together with my family!</p>
```

### HTML `<figure>` and `<figcaption>` Elements

The `<figure>` tag specifies self-contained content, like illustrations, diagrams, photos, code listings, etc.  
The `<figcaption>` tag defines a caption for a `<figure>` element.  
The `<figcaption>` element can be placed as the first or as the last child of a `<figure>` element.  
The `<img>`   element defines the actual image/illustration.  

```html
<figure>
  <img src="pic_trulli.jpg" alt="Trulli">
  <figcaption>Fig1. - Trulli, Puglia, Italy.</figcaption>
</figure>
```

## HTML Style Guide

A consistent, clean, and tidy HTML code makes it easier for others to read and understand your code.  
Here are some guidelines and tips for creating good HTML code.  

**Always Declare Document Type**:  
Always declare the document type as the first line in your document.  
The correct document type for HTML is:  
`<!DOCTYPE html>`

**Use Lowercase Element Names and Lowercase Attribute Names**;
HTML allows mixing uppercase and lowercase letters in element names.  
However, we recommend using lowercase element names.  

**Close All HTML Elements**:  
In HTML, you do not have to close all elements (for example the `<p>` element).  
However, we strongly recommend closing all HTML elements.

**Always Quote Attribute Values**:  
HTML allows attribute values without quotes.  
However, we recommend quoting attribute values.  

**Always Specify alt, width, and height for Images**:  
Always specify the alt attribute for images.  
This attribute is important if the image for some reason cannot be displayed.  
Also, always define the width and height of images.  
This reduces flickering, because the browser can reserve space for the image before loading.

**Spaces and Equal Signs**:  
HTML allows spaces around equal signs.  
But space-less is easier to read and groups entities better together.  
Good:  
`<link rel="stylesheet" href="styles.css">`

**Avoid Long Code Lines**:  
When using an HTML editor, it is NOT convenient to scroll right and left to read the HTML code.  
Try to avoid too long code lines.

**Blank Lines and Indentation**:  
Do not add blank lines, spaces, or indentations without a reason.  
For readability, add blank lines to separate large or logical code blocks.  
For readability, add two spaces of indentation. Do not use the tab key.  

Good:  

```html
<body>

<h1>Famous Cities</h1>

<h2>Tokyo</h2>
<p>Tokyo is the capital of Japan, the center of the Greater Tokyo Area,
and the most populous metropolitan area in the world.
It is the seat of the Japanese government and the Imperial Palace,
and the home of the Japanese Imperial Family.</p>

</body>
```

**Never Skip the `<title>` Element**:  
The `<title>` element is required in HTML.  
The contents of a page title is very important for search engine optimization (SEO)! The page title is used by search engine algorithms to decide the order when listing pages in search results.
The `<title>` element:

* defines a title in the browser toolbar
* provides a title for the page when it is added to favorites
* displays a title for the page in search-engine results

**Omitting `<html>` and `<body>`**?  
An HTML page will validate without the `<html>` and `<body>` tags.  
However, we strongly recommend to always add the `<html>` and `<body>` tags!  
Omitting `<body>` can produce errors in older browsers.  
Omitting `<html>` and `<body>` can also crash DOM and XML software.

**Omitting `<head>`**?  
The HTML `<head>` tag can also be omitted.  
Browsers will add all elements before `<body>`, to a default `<head>` element.  
However, we recommend using the `<head>` tag.

**Close Empty HTML Elements**?  
In HTML, it is optional to close empty elements.  
In HTML, it is optional to close empty elements.

Allowed:  
`<meta charset="utf-8">`
Also Allowed:  
`<meta charset="utf-8" />`

If you expect XML/XHTML software to access your page, keep the closing slash (/), because it is required in XML and XHTML.

**Add the `lang` Attribute**:  
You should always include the lang attribute inside the `<html>` tag, to declare the language of the Web page. This is meant to assist search engines and browsers.

**Meta Data**:  
To ensure proper interpretation and correct search engine indexing, both the language and the character encoding `<meta charset="charset">` should be defined as early as possible in an HTML document.  

**Setting The Viewport**:  
The viewport is the user's visible area of a web page.  
It varies with the device - it will be smaller on a mobile phone than on a computer screen.

You should include the following `<meta>` element in all your web pages:

`<meta name="viewport" content="width=device-width, initial-scale=1.0">`

This gives the browser instructions on how to control the page's dimensions and scaling.  
The `width=device-width` part sets the width of the page to follow the screen-width of the device (which will vary depending on the device).  
The `initial-scale=1.0` part sets the initial zoom level when the page is first loaded by the browser.

**HTML Comments**:  
Short comments should be written on one line, like this:  
`<!-- This is a comment -->`

Comments that spans more than one line, should be written like this:  

```html
<!--
  This is a long comment example. This is a long comment example.
  This is a long comment example. This is a long comment example.
-->
```

Long comments are easier to observe if they are indented with two spaces.

**Using Style Sheets**:  
Use simple syntax for linking to style sheets (the type attribute is not necessary):  
`<link rel="stylesheet" href="styles.css">`

Short CSS rules can be written compressed, like this:  
`p.intro {font-family:Verdana;font-size:16em;}`

Long CSS rules should be written over multiple lines:

```html
body {
  background-color: lightgrey;
  font-family: "Arial Black", Helvetica, sans-serif;
  font-size: 16em;
  color: black;
}
```

* Place the opening bracket on the same line as the selector
* Use one space before the opening bracket
* Use two spaces of indentation
* Use semicolon after each property-value pair, including the last
* Only use quotes around values if the value contains spaces
* Place the closing bracket on a new line, without leading spaces

**Loading JavaScript in HTML**:  
Use simple syntax for loading external scripts (the type attribute is not necessary):  
`<script src="myscript.js">`

**Use Lower Case File Names**:  
Some web servers (Apache, Unix) are case sensitive about file names: "london.jpg" cannot be accessed as "London.jpg".  
Other web servers (Microsoft, IIS) are not case sensitive: "london.jpg" can be accessed as "London.jpg".  
If you use a mix of uppercase and lowercase, you have to be aware of this.

If you move from a case-insensitive to a case-sensitive server, even small errors will break your web!  
To avoid these problems, always use lowercase file names!  

**File Extensions**:  
HTML files should have a .html extension (.htm is allowed).  
CSS files should have a .css extension.  
JavaScript files should have a .js extension.  

**Differences Between .htm and .html**?  
There is no difference between the .htm and .html file extensions!  
Both will be treated as HTML by any web browser and web server.  

**Default Filenames**:  
When a URL does not specify a filename at the end (like "https://www.w3schools.com/"), the server just adds a default filename, such as "index.html", "index.htm", "default.html", or "default.htm".  
If your server is configured only with "index.html" as the default filename, your file must be named "index.html", and not "default.html".  
However, servers can be configured with more than one default filename; usually you can set up as many default filenames as you want.

## HTML Forms

An HTML form is used to collect user input. The user input is most often sent to a server for processing.

**The `<form>` Element**:  
The HTML `<form>` element is used to create an HTML form for user input.  
The `<form>` element is a container for different types of input elements, such as: text fields, checkboxes, radio buttons, submit buttons, etc.  

**The `<input>` Element**:  
The HTML `<input>` element is the most used form element.  
An `<input>` element can be displayed in many ways, depending on the type attribute.

Here are the different input types you can use in HTML:

* `<input type="button">` - Displays a clickable button
* `<input type="checkbox">` - Displays a checkbox (for selecting zero or more of many choices)
* `<input type="color">`
* `<input type="date">`
* `<input type="datetime-local">`
* `<input type="email">`
* `<input type="file">`
* `<input type="hidden">`
* `<input type="image">`
* `<input type="month">`
* `<input type="number">`
* `<input type="password">`
* `<input type="radio">` - Displays a radio button (for selecting one of many choices)
* `<input type="range">`
* `<input type="reset">`
* `<input type="search">`
* `<input type="submit">` - Displays a submit button (for submitting the form)
* `<input type="tel">`
* `<input type="text">` - Displays a single-line text input field
* `<input type="time">`
* `<input type="url">`
* `<input type="week">`

Tip: The default value of the type attribute is "text".

**The `<label>` Element**:  
The `<label>` tag defines a label for many form elements.  
The `<label>` element is useful for screen-reader users, because the screen-reader will read out loud the label when the user focus on the input element.  
The `<label>` element also help users who have difficulty clicking on very small regions (such as radio buttons or checkboxes) - because when the user clicks the text within the <label> element, it toggles the radio button/checkbox.  
The for attribute of the `<label>` tag should be equal to the id attribute of the `<input>` element to bind them together.

**Radio Buttons**:  
The `<input type="radio">` defines a radio button.
Radio buttons let a user select ONE of a limited number of choices.

```html
<p>Choose your favorite Web language:</p>

<form>
  <input type="radio" id="html" name="fav_language" value="HTML">
  <label for="html">HTML</label><br>
  <input type="radio" id="css" name="fav_language" value="CSS">
  <label for="css">CSS</label><br>
  <input type="radio" id="javascript" name="fav_language" value="JavaScript">
  <label for="javascript">JavaScript</label>
</form>
```

**Input Type Button**:  
`<input type="button">` defines a button:

```html
<input type="button" onclick="alert('Hello World!')" value="Click Me!">
```

**Input Type Color**:  
The `<input type="color">` is used for input fields that should contain a color.  
Depending on browser support, a color picker can show up in the input field.

```html
<form>
  <label for="favcolor">Select your favorite color:</label>
  <input type="color" id="favcolor" name="favcolor">
</form>
```

**Input Type Date**:  
The `<input type="date">` is used for input fields that should contain a date.  
Depending on browser support, a date picker can show up in the input field.

```html
<form>
  <label for="birthday">Birthday:</label>
  <input type="date" id="birthday" name="birthday">
</form>
```

You can also use the min and max attributes to add restrictions to dates:

```html
<form>
  <label for="datemax">Enter a date before 1980-01-01:</label>
  <input type="date" id="datemax" name="datemax" max="1979-12-31"><br><br>
  <label for="datemin">Enter a date after 2000-01-01:</label>
  <input type="date" id="datemin" name="datemin" min="2000-01-02">
</form>
```

**Input Type File**:  
The `<input type="file">` defines a file-select field and a "Browse" button for file uploads.

```html
<form>
  <label for="myfile">Select a file:</label>
  <input type="file" id="myfile" name="myfile">
</form>
```

**Checkboxes**;  
The `<input type="checkbox">` defines a checkbox.  
Checkboxes let a user select ZERO or MORE options of a limited number of choices.

```html
<form>
  <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike">
  <label for="vehicle1"> I have a bike</label><br>
  <input type="checkbox" id="vehicle2" name="vehicle2" value="Car">
  <label for="vehicle2"> I have a car</label><br>
  <input type="checkbox" id="vehicle3" name="vehicle3" value="Boat">
  <label for="vehicle3"> I have a boat</label>
</form>
```

**The Submit Button**:  
The `<input type="submit">` defines a button for submitting the form data to a form-handler.  
The form-handler is typically a file on the server with a script for processing input data.  
The form-handler is specified in the form's action attribute.  

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname" value="John"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname" value="Doe"><br><br>
  <input type="submit" value="Submit">
</form>
```

**The Name Attribute for `<input>`**:  
Notice that each input field must have a name attribute to be submitted.  
If the name attribute is omitted, the value of the input field will not be sent at all.

### HTML Form Attributes

List of All `<form>` Attributes

| Attribute | Description |
| accept-charset | Specifies the character encodings used for form submission |
| action | Specifies where to send the form-data when a form is submitted |
| autocomplete | Specifies whether a form should have autocomplete on or off |
| enctype | Specifies how the form-data should be encoded when submitting it to the server (only for method="post") |
| method | Specifies the HTTP method to use when sending form-data |
| name | Specifies the name of the form |
| novalidate | Specifies that the form should not be validated when submitted |
| rel | Specifies the relationship between a linked resource and the current document |
| target | Specifies where to display the response that is received after submitting the form |

**The Action Attribute**:  
The action attribute defines the action to be performed when the form is submitted.  
Usually, the form data is sent to a file on the server when the user clicks on the submit button.  
If the action attribute is omitted, the action is set to the current page.  
In the example below, the form data is sent to a file called "action_page.php". This file contains a server-side script that handles the form data:

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname" value="John"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname" value="Doe"><br><br>
  <input type="submit" value="Submit">
</form>
```

**The Target Attribute**:  
The target attribute specifies where to display the response that is received after submitting the form.  
The target attribute can have one of the following values:  

| Value | Description |
| `_blank` | The response is displayed in a new window or tab |
| `_self` | The response is displayed in the current window |
| `_parent` | The response is displayed in the parent frame |
| `_top` | The response is displayed in the full body of the window |
| `framename` | The response is displayed in a named iframe |

The default value is `_self` which means that the response will open in the current window.

**The Method Attribute**:  
The method attribute specifies the HTTP method to be used when submitting the form data.  
The form-data can be sent as URL variables (with method="get") or as HTTP post transaction (with method="post").  
The default HTTP method when submitting form data is GET. 

*Notes on GET:*  

* Appends the form data to the URL, in name/value pairs
* NEVER use GET to send sensitive data! (the submitted form data is visible in the URL!)
* The length of a URL is limited (2048 characters)
* Useful for form submissions where a user wants to bookmark the result
* GET is good for non-secure data, like query strings in Google

*Notes on POST:*

* Appends the form data inside the body of the HTTP request (the submitted form data is not shown in the URL)
* POST has no size limitations, and can be used to send large amounts of data.
* Form submissions with POST cannot be bookmarked

Tip: Always use POST if the form data contains sensitive or personal information!

**The Autocomplete Attribute**:  
The autocomplete attribute specifies whether a form should have autocomplete on or off.  
When autocomplete is on, the browser automatically complete values based on values that the user has entered before.  

**The Novalidate Attribute**:  
The novalidate attribute is a boolean attribute.  
When present, it specifies that the form-data (input) should not be validated when submitted.  

`<form action="/action_page.php" novalidate>`

### HTML Form Elements

The HTML `<form>` element can contain one or more of the following form elements:

* `<input>`
* `<label>`
* `<select>`
* `<textarea>`
* `<button>`
* `<fieldset>`
* `<legend>`
* `<datalist>`
* `<output>`
* `<option>`
* `<optgroup>`

**The `<input>` Element**:  
One of the most used form element is the `<input>` element.  
The `<input>` element can be displayed in several ways, depending on the type attribute.  

```html
<label for="fname">First name:</label>
<input type="text" id="fname" name="fname">
```

**The `<label>` Element**:  
The `<label>` element defines a label for several form elements.  
The `<label>` element is useful for screen-reader users, because the screen-reader will read out loud the label when the user focus on the input element.  
The `<label>` element also help users who have difficulty clicking on very small regions (such as radio buttons or checkboxes) - because when the user clicks the text within the `<label>` element, it toggles the radio button/checkbox.  
The `for` attribute of the `<label>` tag should be equal to the id attribute of the `<input>` element to bind them together.

**The `<select>` Element**:  
The `<select>` element defines a drop-down list:

```html
<label for="cars">Choose a car:</label>
<select id="cars" name="cars">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```

The `<option>` elements defines an option that can be selected.  
By default, the first item in the drop-down list is selected.  
To define a pre-selected option, add the selected attribute to the option:  

`<option value="fiat" selected>Fiat</option>`

**Visible Values**:  
Use the size attribute to specify the number of visible values:

```html
<label for="cars">Choose a car:</label>
<select id="cars" name="cars" size="3">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```

**Allow Multiple Selections**:  
Use the multiple attribute to allow the user to select more than one value:

```html
<label for="cars">Choose a car:</label>
<select id="cars" name="cars" size="4" multiple>
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```

**The `<textarea>` Element**:  
The `<textarea>` element defines a multi-line input field (a text area):

```html
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
```

The `rows` attribute specifies the visible number of lines in a text area.  
The `cols` attribute specifies the visible width of a text area.

You can also define the size of the text area by using CSS:

```html
<textarea name="message" style="width:200px; height:600px;">
The cat was playing in the garden.
</textarea>
```
