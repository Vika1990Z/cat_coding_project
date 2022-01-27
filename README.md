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

### The alt Attribute

The required alt attribute for the `<img>` tag specifies an alternate text for an image, if the image for some reason cannot be displayed.  
This can be due to slow connection, or an error in the src attribute, or if the user uses a screen reader.

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
