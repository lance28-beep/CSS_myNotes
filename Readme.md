# CSS Notes

documenting / taking notes every topic of the tutorial <br>
[CSS_ZeroToHero](https://youtu.be/1Rs2ND1ryYc) <br>

# CSS: An Introduction

## What is CSS?

- CSS stands for Cascading Style Sheet.
- It is a language used to give styling and design to websites
- It is the standard for styling websites, used by most/all website across the globe
- It usually goes hand-in-hand with HTML, while CSS3 (lates version) brings lots of new feature to table

## Why use CSS?

There are many reasons to use CSS,such as:

- Styling
- Layout & Design
- Animations
- Font Changes
- Organization
- Grid Systems

<img src="https://qph.fs.quoracdn.net/main-qimg-14f73f0964d83a1757aa564ba129c0b7" width='500'>

## How is CSS Used?

- typically, a file is saved in the <code>.css</code> format, and linked to using an HTML tag.
- CSS selectors can be used to address parts of the page style and use.
- HTML Elements are given Class and ID attributes, which are then used to manipulate in CSS.
- It typically follows this method:Select, then Edit.

## Creating & Linking a CSS stylesheet

<img src='./img/linkingcss.PNG' width='500'>

# CSS syntax

<img src="./img/cssSyntax.PNG" width="500">

- <b>Selector</b> - points to the HTML element you want to style
- <b>Declaration block</b> - contains one or more declarations separated by semicolons <code>";"</code>.
- each declaration includes a CSS <b>property</b> name and a <b>value</b>, separated by a colon<code>":"</code>.
- Multiple CSS declarations are separated wih semicolons, and declaration blocks are sorrounded by curly braces.

## CSS Selectors

- Selectors are used to find or select the HTML elements you want to style
- Selectors are ways of grabbing and manipulating HTML
- There are many different ways to select, however they all turn out the same way.
- Different selectors have different applications.

## Five Categories of Selectors

- <b>Simple selectors</b> - Select elements based on name, id,class
- <b>Combinator Selectors</b> - Select elements based on a specific relationship between them
- <b>Psedo-class selectors</b> - select elements based on a certain state.
- <b>Pseudo-elements selectors </b> - select and style a part of an element
- <b>Attribute selectors</b> - select elements based on an attribute or attribute value

<hr>

## Selectors: The Element Selector

<img src='./img/selectors1.PNG' width='300' height='180'>HTML
<img src='./img/selectors2.PNG' height='180' width='300'>CSS
<img src='./img/selector3.PNG' height='180' width='300'>WEB Output<br>

- you can select entire elements without any special characters.
- This applies to all of the elements with that tag on the page.
- it ranks on the bottom of the specificity scale.

<hr>

## Selectors: The Class Selector

<img src='./img/classOne.PNG' width='300' height='180'>HTML
<img src='./img/classTwo.PNG' height='180' width='300'>CSS
<img src='./img/classThree.PNG' height='180' width='300'>WEB Output<br>

- this is used to select elements with a certain class name.
- can be used on any and all elements with that class.
- can be used multiple times, and is select with the <code>.</code>symbol

You can also specify that only specific HTML elements should be affected by a class.

```
p.center {
  text-align: center;
  color: red;
}
```

HTML elements can also refer to more than one class

```
<p class="center large">This paragraph refers to two classes.</p>
```

<hr>

## Selectors: The ID Selectors

<img src='./img/IDone.PNG' width='300' height='180'>HTML
<img src='./img/IDtwo.PNG' height='180' width='300'>CSS
<img src='./img/IDthree.PNG' height='180' width='300'>WEB Output<br>

- this is used to select elements with a certain ID name.
- Can be used on any and all elements with that ID
- unlike classes,it can only be used on one element at a time,and is selected with <code>#</code> symbol.However, It is possible to use more than once,
- an ID name <code>cannot start with a number!</code>

<hr>

## Selectors: Universal Selector

- The universal selector <code>\*</code> selects all HTML elements on the page

```
* {
  text-align: center;
  color: blue;
}
```

<hr>

## Selectors: Grouping Selector

- The grouping selector selects all the HTML elements with the same style definitions.
- It will be better to group the selectors, to minimize the code.

```
h1, h2, p {
  text-align: center;
  color: red;
}
```

<hr>

## Selectors: Three ways to insert CSS

- External CSS
- Internal CSS
- Inline CSS

<b>External CSS</b>

```
<link rel="stylesheet" href="mystyle.css">
```

<b>Internal CSS</b>

```
<link rel="stylesheet" href="mystyle.css">
```

<b>Internal CSS</b>

```
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

<b>Inline CSS</b>

```
<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>
```

Note:<br>
What style will be used when there is more than one style specified for an HTML element?<br>
All the styles in a page will "cascade" into a new "virtual" style sheet by the following rules, where number one has the highest priority:

- Inline style (inside an HTML element)
- External and Internal style sheets ( in the head section)
- Browser default
  so, an inline style has the highest priority, and will override external and internal styles and browser defaults

## Specificity & When to use Selectors

<hr>

## What is Specificity?

It there are two or more conflicting CSS rules that point to the same element, the browser follows some rules to determine which one is most specific and therefore wins out.<br>
Think of specificity as a score/rank that determines which style declarations are ultimately applied to an element.<br>
The universal selector<code>(\*)</code> has low specificity, while ID selectors are highly specific!<br>
<code>Specificity is a common reason why you CSS- rules dont apply to some elements, although you think they should</code>

## Specificity hierarchy

Every selector has its place in the specificity hierarchy. There are four categories which define the specificity level of a selector:<br>

- <b>Inline styles </b> - An inline style is attached directly to the element to be styled

```
<h1 style="color: #ffffff;">
```

- <b>IDs </b> - an ID is a unique identifier to the page elements, such as #navbar

- <b>Classes, attributes and pseudo-classes </b> - This category includes .classes, [attributes] and pseudo-classes such as :hover ,:focus etc.

- <b>Elements and pseudo-elements </b> - this category includes element names and pseudo-elements, such as h1, div, :before and :after

## How to Calculate Specificity?

<code>Memorize how to calculate specificity!</code><br>
Start at 0, and 1000 for style attribute, add 100 for each ID, add 10 for each attribute, class or pseudo-class, and 1 for each element name or pseudo-element.<br>
sample:

```
A: h1
B: #content h1
C: <div id="content"><h1 style="color: #ffffff">Heading</h1></div>
```

- the specificity of A is 1 (one element)
- the specificity of B is 101 (one ID reference and one element)
- the specificity of C is 1000(inline styling)<br>

## Specificity Rules

<b>Equal specificity:the latest rule counts</b>- if the same rule is written twice into the external style sheet, then the lower rule in the style sheet is closer to the element to be styled, and therefore wil be applied:

```
h1 {background-color: yellow;}
h1 {background-color: red;}
```

the latter rule is always applied
<b>ID selectors have a higher specificity than attribute selectors</b>

```
div#a {background-color: green;}
#a {background-color: yellow;}
div[id=a] {background-color: blue;}
```

the first rule is more specific than the other two, and will be applied.

<b>Contextual selectors are more specific than a single element selector</b>
the embedded style sheet is closer to the element to be styled.

```
From external CSS file:
#content h1 {background-color: red;}

In HTML file:
<style>
#content h1 {
  background-color: yellow;
}
</style>

```

the latter rule will be applied <br>

<b>a class selector beats any number of element selectors</b>

- a class selector such as .intro beats h1,p,div etc:

```
.intro {background-color: yellow;}
h1 {background-color: red;}
```

<b>The universal selector and inherited values have a specificity of 0</b> - body and similar have a zero specificity. Inherited values also have a specificity of 0.

## Pseudoselectors

<hr>

## Pseudo-Classes

a pseudo-class is used to define a special state of an element.

- style an element when a user mouss over it
- style visisted and unvisited links differently
- style an element when it gets focus

## syntax

```
selector:pseudo-class {
  property: value;
}
```
# Anchor Pseudo-classes
```
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
<b>Note</b>:<br>
<code>a:hover</code> Must come after <code>a:link</code> and <code>a:visited</code> in the CSS defination in order to be effective!<code>a:active</code> Must come after a <code>a:hover</code> in the CSS definition in order to be effective! Pseudo-class names are not case-sensitive.

## Pseudo-classes and CSS Classes
Pseudo-classes can be combined with CSS classes:
When you hover over the link in the example,it will change color:
```
a.highlight:hover {
  color: #ff0000;
}
```
## Simple Tooltip Hover
hover over a div element to show a <code>\<p></code> element (like a tooltip)

p {
  display: none;
  background-color: yellow;
  padding: 20px;
}

div:hover p {
  display: block;
}

## The :first-child Pseudo-class
the <code>:first-child</code> pseudo-class matches a specified element that is the first child of another element.
```
ul li:first-child {
  color: red;
}
```

## The :lang Pseudo-class
The <code>:lang<code> pseudo-class allows you to define special rules for different languages.


Notes:
##  Div and Span - used for grouping
- div - used to group multiple elements
- span - used to group inline content