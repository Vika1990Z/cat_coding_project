# Questions

## HTML - Hyper Text Markup Language

### 1) What is an attribute in HTML?

All HTML elements can have attributes  
Attributes provide additional information about elements  
Attributes are always specified in the start tag  
Attributes usually come in name/value pairs like: name="value"  
The Attributes name and values are case sensitive, and it is recommended by W3C that it should be written in Lowercase only.  
You can add multiple attributes in one HTML element, but need to give space between two attributes.  
`<element attribute_name="value">content</element>`  
`<p style="height: 50px; color: blue">It will add style property in element</p>`  

All HTML elements can have attributes  
The **href** attribute of `<a>` specifies the URL of the page the link goes to  
The **src** attribute of `<img>` specifies the path to the image to be displayed  
The **width** and **height** attributes of `<img>` provide size information for images  
The **alt** attribute of `<img>` provides an alternate text for an image  
The **style** attribute is used to add styles to an element, such as color, font, size, and more  
The **lang** attribute of the `<html>` tag declares the language of the Web page  
The **title** attribute defines some extra information about an element  

### 2) What is Marquee in HTML?

Тег `<marquee>` используется для создания бегущей строки на сайте.  
При помощи этого тега можно перемещать текст или изображения по горизонтали и вертикали.  
Тег `<marquee>` считается устаревшим  

### 3) What is semantic HTML?

A semantic element clearly describes its meaning to both the browser and the developer.  
It makes HTML more comprehensible by better defining the different sections and layout of web pages.  
Examples of non-semantic elements: `<div>` and `<span>` - Tells nothing about its content.  
Examples of semantic elements: `<form>`, `<table>`, and `<article>` - Clearly defines its content.

### 4) How do you  display a table on a HTML webpage?

A table in HTML consists of table cells inside rows and columns

```html
<table>
  <tr> <!-- table row -->
    <th>Company</th> <!-- table header -->
  </tr>
  <tr>
    <td>Alfreds Futterkiste</td> <!-- table data -->
  </tr>
  <tr>
    <td>Centro comercial Moctezuma</td>
  </tr>
</table>
```

`<tr>` - represents rows  
`<td>` - used to create data cells  
`<th>` - used to add table headings  
`<caption>` - used to insert captions  
`<thead>` - adds a separate header to the table  
`<tbody>` - shows the main body of the table  
`<tfoot>` - creates a separate footer for the table  

### 5) What is SVG in HTML?

SVG stands for Scalable Vector Graphics  
SVG is used to define vector-based graphics for the Web  
SVG defines the graphics in XML format  
Every element and every attribute in SVG files can be animated  
SVG is a W3C recommendation  
SVG integrates with other W3C standards such as the DOM and XSL

```html
<html>
<body>

<h1>My first SVG</h1>

<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
</svg>

</body>
</html>
```

### 6) How to sepaete the section of the text in HTML?

To define a section of text as an HTML paragraph, you should use a pair of `<p>` tags.  
Note: HTML paragraphs don't have any formatting – it must be added manually.  

You can use the `<br>` element whenever you need to add an HTML new line but not a new paragraph.  
As it is an empty element, it does not have a closing tag.

If you'd prefer to separate your paragraphs with a horizontal line instead of a simple HTML paragraph break, use the `<hr>` element.  

### 7) Difference between HTML and HTML5, new tags in HTML5?

## CSS

### 1) What is the best way to include CSS styling in HTML?

CSS can be added to HTML documents in 3 ways:  

Inline - by using the style attribute inside HTML elements  
`<p style="color:red;">A red paragraph.</p>`

Internal - by using a `<style>` element in the `<head>` section.  

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
```

External - by using a `<link>` element to link to an external CSS file.  

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
```

The most common way to add CSS, is to keep the styles in external CSS files.  

### 2) Mention the different types of CSS Selectors

CSS selectors are used to "find" (or select) the HTML elements you want to style.

We can divide CSS selectors into five categories:

Simple selectors (select elements based on name, id, class)  
Combinator selectors (select elements based on a specific relationship between them):
    descendant selector (space)  (`div p{background-color: yellow;}` - all p in div, in all levels)
    child selector (>)  (`div > p` - only first child level, but all of them)
    adjacent sibling selector (+)  (`div + p` - first p after div (not a child))
    general sibling selector (`div ~ p`- all p after div)

Pseudo-class selectors (select elements based on a certain state)  
    `:hover`  
    `:first-child`  
    `a:active`  
    `:checked`  
    `input:focus`  
    `p:nth-child(2)`  
    `p:nth-last-child(2)`  
    `input:read-only`  
    `:root`

Pseudo-elements selectors (select and style a part of an element)  
    `p::after`  
    `p::before`  
    `::first-letter`  
    `::first-line`  
    `::selection`  
    `::marker`

Attribute selectors (select elements based on an attribute or attribute value)  
    `a[target] {background-color: yellow;}` - all.  
    `a[target="_blank"] {background-color: yellow;}` - =  
    `[title~="flower"] {border: 5px solid yellow;}` - contein (whole word but not -)
    `[class|="top"] {background-color: yellow;}` - starting with "top" (whole word or -)
    `[class^="top"] {background-color: yellow;}` - begins with "top" (not the whole word and with -)
    `[class$="test"] {background-color: yellow;}`-  ends with "test" (not the whole word and `_,-`)
    `[class*="te"] {background-color: yellow;}` -  contains "te" (not the whole word and `-, _`)

### 3) What are Saas, Less and Stylus?

a CSS pre-processor.
Sass – Syntactically Awesome Style Sheets
LESS – Leaner Style Sheets

### 4) Explain Box Sizing Property

The CSS box-sizing property allows us to include the padding and border in an element's total width and height.

By default, the width and height of an element is calculated like this:  
width + padding + border = actual width of an element  
height + padding + border = actual height of an element

If you set box-sizing: border-box; on an element, padding and border are included in the width and height:

### 5) What are the different ways to hide an element using CSS?

Absolute position
h1 {position: absolute;}
h1.hide {left: -999px;}

**Color**  
h1.hide {color: transparent;}

**Clip-path**  
.rect {
    margin: 20px;
    height: 100px;
    width: 100px;
    background-color: #fff;
}
.rect.hide {clip-path: circle(0);}

**Display** - The element will be hidden, and the page will be displayed as if the element is not there.  
h1.hide {display: none;}

**Filter**  
h1.hide {filter: opacity(0);}

**Measurements**  
h1.hide {
    height: 0px;
    width: 0px;
    overflow: hidden;
}

**Opacity**  
h1.hide {opacity: 0;}

**Transform**  
.crcl.hide {transform: scale(0);}

**Visibility**  - the element will still take up the same space as before.  
.crcl.hide {visibility: hidden;}

### 6) What does `important` in CSS mean?

If you use the !important rule, it will override ALL previous styling rules for that specific property on that element!

p {background-color: red !important;}

### 7) What are CSS Sprites?

CSS Sprites are a collection of images that are combined into a single file that an HTML document can access.  
These images are then called into use within the HTML code to be displayed on the website.

### 8) Explain CSS Positioning

The CSS position property defines the position of an element in a document.  
This property works with the left, right, top, bottom and z-index properties to determine the final position of an element on a page.

There are five values the position property can take. They are:

static (default) - it is always positioned according to the normal flow of the page.  
relative - is positioned relative to its normal position.  
absolute - is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed).  
fixed - is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled.  
sticky - is positioned based on the user's scroll position.

## JavaScript
