
# JavaScript

JavaScript was initially created to “make web pages alive”.

oday, JavaScript can execute not only in the browser, but also on the server, or actually on any device that has a special program called the JavaScript engine.

The browser has an embedded engine sometimes called a “JavaScript virtual machine”.

Different engines have different “codenames”. For example:

V8 – in Chrome, Opera and Edge.
SpiderMonkey – in Firefox.
…There are other codenames like “Chakra” for IE, “JavaScriptCore”, “Nitro” and “SquirrelFish” for Safari, etc.

Modern JavaScript is a “safe” programming language. It does not provide low-level access to memory or CPU, because it was initially created for browsers which do not require it.

JavaScript’s capabilities greatly depend on the environment it’s running in. For instance, Node.js supports functions that allow JavaScript to read/write arbitrary files, perform network requests, etc.

In-browser JavaScript can do everything related to webpage manipulation, interaction with the user, and the webserver.

## Variables

A variable is a “named storage” for data.  
To create a variable in JavaScript, use the let keyword.

```js
let message;
message = 'Hello!';
alert(message); // shows the variable content
```

To be concise, we can combine the variable declaration and assignment into a single line:

```js
let message = 'Hello!'; // define the variable and assign the value
alert(message); // Hello!
```

We can also declare multiple variables in one line:

```js
let user = 'John', age = 25, message = 'Hello';
```

**Variable naming**:  
There are two limitations on variable names in JavaScript:

* The name must contain only letters, digits, or the symbols $ and _.
* The first character must not be a digit.
Examples of valid names:

```js
let userName;
let test123;
```

*Case matters: Variables named apple and AppLE are two different variables.*

## Constants

To declare a constant (unchanging) variable, use const instead of let:

```js
const myBirthday = '18.04.1982';
```

They cannot be reassigned.

## Data types

A value in JavaScript is always of a certain type.
There are eight basic data types in JavaScript.  

We can put any type in a variable. For example, a variable can at one moment be a string and then store a number.  
Programming languages that allow such things, such as JavaScript, are called “dynamically typed”, meaning that there exist data types, but variables are not bound to any of them.

**Number**:  
The number type represents both integer and floating point numbers.  
Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: Infinity, -Infinity and NaN.

* Infinity represents the mathematical Infinity ∞. It is a special value that’s greater than any number.
We can get it as a result of division by zero Or just reference it directly:

```js
alert( 1 / 0 ); // Infinity
alert( Infinity ); // Infinity
```

* NaN represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance:
NaN is sticky. Any further mathematical operation on NaN returns NaN:

```js
alert( "not a number" / 2 ); // NaN, such division is erroneous
alert( NaN + 1 ); // NaN
alert( 3 * NaN ); // NaN
alert( "not a number" / 2 - 1 ); // NaN
```

So, if there’s a NaN somewhere in a mathematical expression, it propagates to the whole result (there’s only one exception to that: NaN ** 0 is 1).

Doing maths is “safe” in JavaScript. We can do anything: divide by zero, treat non-numeric strings as numbers, etc.

The script will never stop with a fatal error (“die”). At worst, we’ll get NaN as the result.

**BigInt**:  
In JavaScript, the “number” type cannot represent integer values larger than (253-1) (that’s 9007199254740991), or less than -(253-1) for negatives.  
It’s a technical limitation caused by their internal representation.  
BigInt type was recently added to the language to represent integers of arbitrary length.  
A BigInt value is created by appending n to the end of an integer:

```js
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```

**String**:  
A string in JavaScript must be surrounded by quotes.

```js
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

In JavaScript, there are 3 types of quotes.  
Double quotes: "Hello".  
Single quotes: 'Hello'.  
Backticks: `Hello`.  

Double and single quotes are “simple” quotes.  
There’s practically no difference between them in JavaScript.

Backticks are “extended functionality” quotes.  
They allow us to embed variables and expressions into a string by wrapping them in ${…}, for example:

```js
let name = "John";
// embed a variable
alert( `Hello, ${name}!` ); // Hello, John!
// embed an expression
alert( `the result is ${1 + 2}` ); // the result is 3
alert( "the result is ${1 + 2}" ); // the result is ${1 + 2} (double quotes do nothing)

```

>Please note that this can only be done in backticks. Other quotes don’t have this embedding functionality!

**Boolean (logical type)**:  
The boolean type has only two values: true and false.  

```js
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
let isGreater = 4 > 1;
alert( isGreater ); // true (the comparison result is "yes")
```

**The “null” value**:  
In JavaScript, null is not a “reference to a non-existing object” or a “null pointer” like in some other languages.  
It’s just a special value which represents “nothing”, “empty” or “value unknown”.  
The code above states that age is unknown.  

```js
let age = null;
```

**The “undefined” value**:  
The meaning of undefined is “value is not assigned”.  
If a variable is declared, but not assigned, then its value is undefined:

```js
let age;
alert(age); // shows "undefined"
```

**Objects and Symbols**:  
All other types are called “primitive” because their values can contain only a single thing (be it a string or a number or whatever).  
In contrast, objects are used to store collections of data and more complex entities.  

The symbol type is used to create unique identifiers for objects.  

**The typeof operator**:  
The typeof operator returns the type of the argument.  
It’s useful when we want to process values of different types differently or just want to do a quick check.

A call to typeof x returns a string with the type name:

```js
typeof undefined // "undefined"
typeof 0 // "number"
typeof 10n // "bigint"
typeof true // "boolean"
typeof "foo" // "string"
typeof Symbol("id") // "symbol"
typeof Math // "object"  Math is a built-in object that provides mathematical operations.
typeof null // "object"  Definitely, null is not an object. It is a special value with a separate type of its own. The behavior of typeof is wrong here.
typeof alert // "function"  (3)
```

## Interaction: alert, prompt, confirm

As we’ll be using the browser as our demo environment, let’s see a couple of functions to interact with the user: alert, prompt and confirm.

**alert**:  
It shows a message and waits for the user to press “OK”.

The mini-window with the message is called a modal window.  
The word “modal” means that the visitor can’t interact with the rest of the page, press other buttons, etc, until they have dealt with the window.  
In this case – until they press “OK”.

```js
alert("Hello");
```

**prompt**
It shows a modal window with a text message, an input field for the visitor, and the buttons OK/Cancel.  
The function prompt accepts two arguments:

* title - The text to show the visitor.
* default - An optional second parameter, the initial value for the input field.

```js
let age = promt("howold are you", 100);
alert ("You are ${age} old");
```