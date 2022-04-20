# Sass Tutorial notes

> Here are reprezented my own notes about Sass Tutorial

**What is Sass?**  
Sass stands for Syntactically Awesome Stylesheet.  
Sass is an extension to CSS.  
Sass is a CSS pre-processor.  
Sass is completely compatible with all versions of CSS.  
Sass reduces repetition of CSS and therefore saves time.  
Sass was designed by Hampton Catlin and developed by Natalie Weizenbaum in 2006.  
Sass is free to download and use.  

Sass lets you use features that do not exist in CSS, like variables, nested rules, mixins, imports, inheritance, built-in functions, and other stuff.

Sass Example

```scss
/* define variables for the primary colors */
$primary_1: #a2b9bc;
$primary_2: #b2ad7f;
$primary_3: #878f99;

/* use the variables */
.main-header {
  background-color: $primary_1;
}

.menu-left {
  background-color: $primary_2;
}

.menu-right {
  background-color: $primary_3;
}
```

**How Does Sass Work?**  
A browser does not understand Sass code.  
Therefore, you will need a Sass pre-processor to convert Sass code into standard CSS.

This process is called transpiling.  
So, you need to give a transpiler (some kind of program) some Sass code and then get some CSS code back.

Tip: Transpiling is a term for taking a source code written in one language and transform/translate it into another language.

**Sass File Type**  
Sass files has the ".scss" file extension.

**Sass Comments**  
Sass supports standard CSS comments `/* comment */`, and in addition it supports inline comments `// comment`:

```scss
/* define primary colors */
$primary_1: #a2b9bc;
$primary_2: #b2ad7f;

/* use the variables */
.main-header {
  background-color: $primary_1; // here you can put an inline comment
}
```

## Sass Variables

Variables are a way to store information that you can re-use later.  
With Sass, you can store information in variables, like:

* strings
* numbers
* colors
* booleans
* lists
* nulls

Sass uses the $ symbol, followed by a name, to declare variables: `$variablename: value;`

The following example declares 4 variables named myFont, myColor, myFontSize, and myWidth.  
After the variables are declared, you can use the variables wherever you want:

```scss
$myFont: Helvetica, sans-serif;
$myColor: red;
$myFontSize: 18px;
$myWidth: 680px;

body {
  font-family: $myFont;
  font-size: $myFontSize;
  color: $myColor;
}

#container {
  width: $myWidth;
}
```

**Sass Variable Scope**:  
Sass variables are only available at the level of nesting where they are defined.  
Look at the following example:

```scss
$myColor: red;

h1 {
  $myColor: green;
  color: $myColor;
}

p {
  color: $myColor;
}
```

The CSS output will be:

```css
h1 {
  color: green;
}

p {
  color: red;
}
```

**Tip: Global variables should be defined outside any rules. It could be wise to define all global variables in its own file, named "_globals.scss", and include the file with the @include keyword.**

**Using Sass !global**:  
The default behavior for variable scope can be overridden by using the !global switch.  
!global indicates that a variable is global, which means that it is accessible on all levels.

Look at the following example (same as above; but with !global added):

```scss
$myColor: red;

h1 {
  $myColor: green !global;
  color: $myColor;
}

p {
  color: $myColor;
```

CSS Output:

```css
h1 {
  color: green;
}

p {
  color: green;
}
```

## Sass Nested Rules and Properties

**Sass Nested Rules**:  
Sass lets you nest CSS selectors in the same way as HTML.  
Look at an example of some Sass code for a site's navigation:

```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }
  li {
    display: inline-block;
  }
  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```

Notice that in Sass, the ul, li, and a selectors are nested inside the nav selector.  
While in CSS, the rules are defined one by one (not nested):

```css
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
nav li {
  display: inline-block;
}
nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```

Because you can nest properties in Sass, it is cleaner and easier to read than standard CSS.

**Sass Nested Properties**:  
Many CSS properties have the same prefix, like font-family, font-size and font-weight or text-align, text-transform and text-overflow.  
With Sass you can write them as nested properties:

```scss
font: {
  family: Helvetica, sans-serif;
  size: 18px;
  weight: bold;
}

text: {
  align: center;
  transform: lowercase;
  overflow: hidden;
}
```

The Sass transpiler will convert the above to normal CSS:

```css
font-family: Helvetica, sans-serif;
font-size: 18px;
font-weight: bold;

text-align: center;
text-transform: lowercase;
text-overflow: hidden;
```

## Sass @import and Partials

Sass keeps the CSS code DRY (Don't Repeat Yourself).  
One way to write DRY code is to keep related code in separate files.

You can create small files with CSS snippets to include in other Sass files.  
Examples of such files can be: reset file, variables, colors, fonts, font-sizes, etc.  

**Sass Importing Files**:  
Just like CSS, Sass also supports the @import directive.  
The @import directive allows you to include the content of one file in another.

The CSS @import directive has a major drawback due to performance issues; it creates an extra HTTP request each time you call it.  
However, the Sass @import directive includes the file in the CSS; so no extra HTTP call is required at runtime!

Sass Import Syntax: `@import filename;`

Tip: You do not need to specify a file extension, Sass automatically assumes that you mean a .sass or .scss file.  
You can also import CSS files.  
The @import directive imports the file and any variables or mixins defined in the imported file can then be used in the main file.

You can import as many files as you need in the main file:

```scss
@import "variables";
@import "colors";
@import "reset";
```

Let's look at an example: Let's assume we have a reset file called "reset.scss", that looks like this:
SCSS Syntax (reset.scss):

```scss
html,
body,
ul,
ol {
  margin: 0;
  padding: 0;
}
```

and now we want to import the "reset.scss" file into another file called "standard.scss".  
Here is how we do it: It is normal to add the @import directive at the top of a file; this way its content will have a global scope:

SCSS Syntax (standard.scss):

```scss
@import "reset";

body {
  font-family: Helvetica, sans-serif;
  font-size: 18px;
  color: red;
}
```

So, when the "standard.css" file is transpiled, the CSS will look like this:

```css
html, body, ul, ol {
  margin: 0;
  padding: 0;
}

body {
  font-family: Helvetica, sans-serif;
  font-size: 18px;
  color: red;
}
```

**Sass Partials**:  
By default, Sass transpiles all the .scss files directly. However, when you want to import a file, you do not need the file to be transpiled directly.

Sass has a mechanism for this: If you start the filename with an underscore, Sass will not transpile it.  
Files named this way are called partials in Sass.
So, a partial Sass file is named with a leading underscore:

Sass Partial Syntax: `filename;`

The following example shows a partial Sass file named "_colors.scss". (This file will not be transpiled directly to "colors.css"):

```scss
$myPink: #EE82EE;
$myBlue: #4169E1;
$myGreen: #8FBC8F;
```

Now, if you import the partial file, omit the underscore. Sass understands that it should import the file "_colors.scss":

```scss
@import "colors";

body {
  font-family: Helvetica, sans-serif;
  font-size: 18px;
  color: $myBlue;
}
```

## Sass @mixin and @include

The @mixin directive lets you create CSS code that is to be reused throughout the website.  
The @include directive is created to let you use (include) the mixin.

**Defining a Mixin**:  
A mixin is defined with the @mixin directive.

Sass @mixin Syntax:

```scss
@mixin name {
  property: value;
  property: value;
  ...
}
```

The following example creates a mixin named "important-text":

```scss
@mixin important-text {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
}
```

Tip: A tip on hyphens and underscore in Sass: Hyphens and underscores are considered to be the same. This means that @mixin important-text { } and @mixin important_text { } are considered as the same mixin!

**Using a Mixin**:  
The @include directive is used to include a mixin.

Sass @include mixin Syntax:

```scss
selector {
  @include mixin-name;
}
```

So, to include the important-text mixin created above:

```scss
.danger {
  @include important-text;
  background-color: green;
}
```

The Sass transpiler will convert the above to normal CSS:

```css
.danger {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
  background-color: green;
}
```

A mixin can also include other mixins:

```scss
@mixin special-text {
  @include important-text;
  @include link;
  @include special-border;
}
```

**Passing Variables to a Mixin**:  
Mixins accept arguments. This way you can pass variables to a mixin.  
Here is how to define a mixin with arguments:

```scss
/* Define mixin with two arguments */
@mixin bordered($color, $width) {
  border: $width solid $color;
}

.myArticle {
  @include bordered(blue, 1px);  // Call mixin with two values
}

.myNotes {
  @include bordered(red, 2px); // Call mixin with two values
}

```

Notice that the arguments are set as variables and then used as the values (color and width) of the border property.  
After compilation, the CSS will look like this:

```css
.myArticle {
  border: 1px solid blue;
}

.myNotes {
  border: 2px solid red;
}
```

**Default Values for a Mixin**:  
It is also possible to define default values for mixin variables:

```scss
@mixin bordered($color: blue, $width: 1px) {
  border: $width solid $color;
}
```

Then, you only need to specify the values that change when you include the mixin:

```scss
.myTips {
  @include bordered($color: orange);
}
```

**Using a Mixin For Vendor Prefixes**:  
Another good use of a mixin is for vendor prefixes.  
Here is an example for transform:

```scss
@mixin transform($property) {
  -webkit-transform: $property;
  -ms-transform: $property;
  transform: $property;
}

.myBox {
  @include transform(rotate(20deg));
}
```

## Sass @extend and Inheritance

The @extend directive lets you share a set of CSS properties from one selector to another.  
The @extend directive is useful if you have almost identically styled elements that only differ in some small details.

The following Sass example first creates a basic style for buttons (this style will be used for most buttons).  
Then, we create one style for a "Report" button and one style for a "Submit" button.  
Both "Report" and "Submit" button inherit all the CSS properties from the .button-basic class, through the @extend directive.  
In addition, they have their own colors defined:

```scss
.button-basic  {
  border: none;
  padding: 15px 30px;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
}

.button-report  {
  @extend .button-basic;
  background-color: red;
}

.button-submit  {
  @extend .button-basic;
  background-color: green;
  color: white;
}

```

CSS Output:

```css
.button-basic, .button-report, .button-submit {
  border: none;
  padding: 15px 30px;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
}

.button-report  {
  background-color: red;
}

.button-submit  {
  background-color: green;
  color: white;
}
```

By using the @extend directive, you do not need to specify several classes for an element in your HTML code, like this: `<button class="button-basic button-report">Report this</button>`.  
You just need to specify `.button-report` to get both sets of styles.

The @extend directive helps keep your Sass code very DRY.

## Sass Functions

* Sass String Functions
* Sass Numeric Functions
* Sass List Functions
* Sass Map Functions
* Sass Selector Functions
* Sass Introspection Functions
* Sass Color Functions
