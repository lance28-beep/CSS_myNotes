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

<code?>Last Rule and Specificity \* Universal Selector </code><br>
sample:

```
p{
  color:red;
}


p{
  color :blue
}

```

-ma oooverwrite yung first declaration.dito na papasuk yung last rule.ang susundin na style or declaration ng selector is yung nasa bottom part or last entry.

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

The <code>:lang</code> pseudo-class allows you to define special rules for different languages.

Notes:

## Div and Span - used for grouping

- div - used to group multiple elements
- span - used to group inline content

## Inheritance

- children inherit styles from parent, unless have their own styles.

## COLORS

- color, background-color,background
- color names
- rgb,rgba
- hex
- visual studio code color options
- external resources

<b>color properties</b><br>
-control the color of the element
<b>color background</b><br>
-control the background color of the element

```
#first{
  color:white;
  background-color:black;
}
```

<b>color names > 140</b><br>

```
color:red;
color:green;
etc..
/*ctrl + tab(triger vs code suggestion*/
```

<b>RGB (red,green,blue) 0-255 </b><br>

```
color:rgb(255,0,0) /*red*/
```

<b>RGBA A-opacity/transparency 0-1 </b><br>

```
color:rgba(0,255,0,0.5)
```

<b>HSL</b><br>
<b>Hex Value #RRGGBB</b><br>
<b>123456789 A(10) B(11) C(12) D(13) E(14) F(15) </b><br>
<b>10 11 12 13 14 15 </b><br>
<b>#FF0000 - red</b><br>
<b>#00ff00 - green</b><br>

```
color:#ff0000
```

## Units

- absolute,relative
- pixels
- em,rem
- vw ,vh
- font-size, height, width
<hr>

<b>Pixels</b><br>
-Absolute values, one dot on the screen<br>
<b>FONT-SIZE</b><br>
-control size of the font<br>
<b>WIDTH</b><br>
-control width of the element<br>
<b>HEIGHT</b><br>
-control height of an element<br>

<img src='./img/CSSunits.PNG'>

```
h1{
  background:rgb(170, 78, 78);
  color:rgba(255,255,255,0.1);
  font-size:100px;
  width: 500px;
  height:500px;
}
```

<b>% - parent</b><br>
-relative unit/value. Depends on the parent<br>
<img src='./img/relative.PNG' width="500"> <br>

```
/* parent element */
.container{
  background:#c54343;
  width:200px;
  height: 200px;
}

/* child element */
.containerTwo{
background:rgb(92, 92, 194);
width: 50%;
height: 50%;
}
```

<code>
/* <br>
em - relative depends on parent<br>
1em = 16px default browser style;<br>
1em = base value <br>
*/
</code>
<img src="./img/em.PNG" width='500'>

```
/* parent element */
div {
  font-size: 10px;
}
/* relative element */
.relative {
  font-size: 2em;
}

/* absolute element */
.absolute {
  font-size: 32px;
}
```

<code>
/* <br>
rem - relative depends on root<br>
1em = 16px default browser style;<br>
*/
</code> <br>
<img src="./img/rem.PNG" width="500">

```
/* root element */
html{
  font-size: 32px;
}
/* parent element */
div {
  font-size: 10px;
}
/* relative element */
.relative {
  font-size: 2rem;
}
/* absolute element */
.absolute {
  font-size: 32px;
}

```

<code>
/* <br>
vh - height - percent of the screen<br>
vw - width - percent of the screen<br>
*/
</code> <br>
<img src="./img/screenview.PNG">

```
.header{
  width: 50vw;
  height:50vh;
  background: red;
}
.banner{
  width: 100vw;
  height:100vh;
  background: blue;
}
```

<code>
/* <br>
calc()<br>
perform math operations + - *<br>
mix and match values<br>
*/
</code> <br>
<img src="./img/calc.PNG" width='500'>

```
/* reset default margin */
* {
  margin: 0;
}

.navbar {
  background: blue;
  height: 100px;
  color: white;
  font-size: 3rem;
}

.banner {
  background: red;
  min-height: calc(100vh - 100px);
}
```

## TYPOGRAPHY

- properties
- font-stack, generic family
- google fonts

<code>
/* <br>
font-size font-family<br>
*/
</code> <br>

<img src="./img/font-family.PNG" width='500'>

```
body {
font-family: helvetica;
}
h1 {
font-family: verdana;
}

```

<code>
/* <br>
font-stack generic-family<br>
serif, sans-serif, cursive, fantasy, monospace<br>
*/
</code> <br>
A font stack is a list of fonts in the CSS font-family declaration. ... A font stack allows you to control the look of the fonts on the web page even if the site visitor's computer doesn't have the initial font that you called for
 <img src='./img/font-stack.PNG' width='500'>

```
body {
  font-family: helvetica;
}
h1 {
  font-family: 'Courier New', Courier, monospace
}
```

<code>
/* <br>
Google Fonts<br>
*/
</code> <br>

[fonts.google.com](https://fonts.google.com/)

<img src='./img/google-fonts.PNG' width='500'>

```
@import url('https://fonts.googleapis.com/css2?family=Fuggles&display=swap');

body {
  font-family: helvetica;
}
h1 {
  font-family: 'Fuggles', cursive;
  font-size:4rem;
  word-spacing: .5rem;
}

```

<code>
/* <br>
font-weight<br>
font-style<br>
*/
</code> <br>
<img src='./img/font-weight.PNG' width='500'>

```
/* font-weight */
span:nth-child(1) {
  font-weight: 100;
}
span:nth-child(2) {
  font-weight: 200;
}
span:nth-child(3) {
  font-weight: 300;
}
span:nth-child(4) {
  font-weight: 400;
}
span:nth-child(5) {
  font-weight: 500;
}
span:nth-child(6) {
  font-weight: 600;
}
span:nth-child(7) {
  font-weight: 700;
}
span:nth-child(8) {
  font-weight: 800;
}
span:nth-child(9) {
  font-weight: 900;
}
p:nth-child(1) {
  font-weight: lighter;
}
p:nth-child(2) {
  font-weight: normal;
}
p:nth-child(3) {
  font-weight: bold;
}
p:nth-child(4) {
  font-weight: bolder;
}
/* font-style */
.italic {
  font-style: italic;
}
.oblique {
  font-style: oblique;
}
```

<code>
/* <br>
text-align<br>
*/
</code> <br>

<img src='./img/text-align.PNG' width='500'>

```
* {
  margin: 1rem;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Courier New', Courier, monospace;
  text-align: right;
}

.main {
  text-align: center;
}

.two {
  text-align: left;
}
```

<code>
/* <br>
text-indent<br>
*/
</code> <br>

<img src='./img/indent.PNG' width='500'>

```
* {
  margin: 1rem;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Courier New', Courier, monospace;
}

.one {
  text-indent: 10rem;
}
```

<code>
/* <br>
<b>line-height</b> (relative)<br>
letter-spacing<br>
word-spacing<br>
text-transform<br>
text-decoration<br>
*/
</code> <br>

<img src='./img/text-decoration.PNG' width='500'>

```
* {
  margin: 1rem;
  padding: 0;
  box-sizing: border-box;
}
a {
  font-size: 5rem;
  text-decoration: none;
  color: royalblue;
}
h2 {
  text-transform: uppercase;
  text-decoration: line-through;
}
.one {
  line-height: 35px;
  text-decoration: underline;
}
.two {
  letter-spacing: 3px;
  text-decoration: overline;
}
.three {
  word-spacing: 2rem;
  text-decoration: line-through;
}

```

## CSS Tutorial

- CSS Box Model
- padding
- border
- margin
- border-radius, negative margin

## CSS Box Model

<img src="https://www.washington.edu/accesscomputing/webd2/student/unit3/images/boxmodel.gif" width='500'>

<code>padding</code>

<img src='./img/padding.PNG' width='500'>

```
h1 {
  background: red;
  padding-top: 30px;
  padding-bottom: 60px;
  padding-left: 25px;
  padding-right: 50px;
}

/* short-hand */
p {
  background: blue;
  /*padding: 50px; all side*/
  /* padding:30px 60px;top-bottom/left-right */
padding: 20px 40px 60px 10px;
  /*
  top padding is 20px
  right padding is 40px
  bottom padding is 60px
  left padding is 10px
  */
}
```

<code>margin</code> <br>
same principles of padding aside from it a margin.
<img src='./img/margin.PNG' width='500'>

```
h1 {
  background: red;
  padding: 20px;
  margin: 0;
}

p {
  background: blue;
  padding: 20px;
  margin: 0;
}
```

<code>border</code> <br>

<img src='./img/border.PNG' width='500'>

```
h1 {
  background: red;
  padding: 20px;
  margin: 20px;
  border-style: solid;
  border-width: 10px;
  border-color: green;
}
/* shorthand */
p {
  background: blue;
  padding: 20px;
  margin: calc(40px - 20px);
  border: solid 10px red;
}
div {
  width: 350px;
  height: 20vh;
  margin: 0 auto;
  background: aqua;
  border-radius: 50%;
  border-bottom: groove 10px blue;
  border-left: dashed 10px blue;
  border-right: dashed 10px blue;
}
```

<code>Border Style</code>

<img src="./img/border-style.PNG">

<border>
<code>outline & offset</code> <br>

<img src='./img/outline.PNG' width='500'>

```
button {
  padding: 20px;
  background: greenyellow;
  text-transform: capitalize;
  cursor: pointer;
  margin: 20px;
}
button:nth-child(1) {
  border: 5px solid royalblue;
}

button:nth-child(2) {
  border: none;
  outline: 5px solid royalblue;
}

button:nth-child(3) {
  border: none;
  outline: 5px solid royalblue;
  outline-offset: -10px;
}
```

additional guide:
<br><b>Box Model</b>
-everything which is displayed by css is a box.<br>
-The CSS box model is actually a box that wraped around each HTML component.<br>
-it includes:<br>

- margins
- borders
- padding
- actual content

<img src='./img/boxModelTip.PNG' width='500'>
<img src='./img/boxModelTip2.PNG' width='500'>

## CSS tutorial

- display
- block
- inline
- inline-block
- box-sizing:border-box

<img src='./img/display.PNG' width='500'>
<code>
/*<br>
Default displays property<br>
Block : Always starts a new line and takes full width <br>
Inline : Does not start and only take up as much as content space<br>
*/
</code><br>

<img src='./img/inline-block.PNG' width='500'><br>

<img src="./img/inline2.PNG" width='500'>

```
.block {
  background: blue;
  color: white;
  display: inline;
}
.inline {
  background: red;
  color: white;
  display: block;
}
```

-setting to default and make inline to block and block to inline.

<code>
CSS Layout - Horizontal & Vertical Align
</code><br>

<img src='./img/horizontal-centering.PNG' width='500'><br>
<img src="./img/block3.PNG" width='500'>

```
body {
  text-align: center;
}

.block {
  background: blue;
  color: white;
  margin: 0 auto;
}
.inline {
  background: red;
  color: white;
  display: block;
  margin: 0 auto;
}

```

<code>
Block: Top Bottom Margin Respected <br>
Inline: Top Bottom Margin Not Respected <br>
Mobile Navbar<br>
list-style-type:property<br>
descendant selectors
</code><br>

<img src='./img/inline.PNG' width='500'>
<br>
-inline margin and padding are not respected by the browser (top and bottom)

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

ul li {
  list-style: none;
}
ul li a {
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 2px;
  background: #222;
  color: red;
  padding: 10px;
  margin: 10px;
}
```

<img src='./img/block.PNG' width='500'><br>
-block margin and padding are respected by the browser
(top and bottom)

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

ul li {
  list-style: none;
}
ul li a {
  font-size: 0.75em;
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 2px;
  background: #222;
  color: red;
  display: block;
  padding: 10px;
  margin: 10px;
}
```

<img src='./img/inline-block2.PNG' width='500'><br>
<img src='./img/inline-block3.PNG' width='500'><br>
-using <code> display:inline-block</code> inline margin and padding will be respected by the browser in no longer need to set it to block<br>

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

ul li {
  list-style: none;
}
ul li a {
  font-size: 0.75em;
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 2px;
  background: #222;
  color: red;
  display: inline-block;
  padding: 10px;
  margin: 10px;
}


```

<code>
  box-sizing: border-box;
</code>
 border-box tells the browser to account for any border and padding in the values you specify for an element's width and height. If you set an element's width to 100 pixels, that 100 pixels will include any border or padding you added, and the content box will shrink to absorb that extra width.

<img src='./img/border-box.PNG' width='500>'

```
.box-1,
.box-2,
.box-3 {
  width: 200px;
  height: 100px;
  color: #fff;
  box-sizing: border-box;
}
.box-1 {
  background: red;
  padding: 20px;
}
.box-2 {
  background: blue;
}
.box-3 {
  background: green;
  padding: 40px;
}
```

<code>
/* <br>
display:none<br>
opacity:0<br>
visibility:hidden <br>
*/</code><br>

notes: <br>
display:none - remove from the flow, hide element collapse the space <br>
opacity:0;visibility:hidden; - hides element preserves the space.<br>
<img src='./img/opacity.PNG' width='500'><br>

```
div {
  background: blue;
  margin: 10px;
  color: white;
}

.none {
  display: none;
}

.opacity-1 {
  opacity: 1;
}

.opacity-5 {
  opacity: 0.5;
}
.opacity-0 {
  opacity: 0;
}
.visibility {
  visibility: hidden;
}

Note:
display: none;
-- completely taken out the element.
opacity:0;
visibility:0;
-- element still exist but and content are only hidden
```

<code><h2>Opacity Use Cases</h2></code><br>
<code>3 ways to apply opacity in CSS</code><br>
all will achieve a similar result<br>
<img src='./img/opacity1.PNG' width='500'><br>

<code>useful cases</code><br>
<img src='./img/inactive-list.PNG' width='500'><br>
<img src='./img/disabled-forms.PNG' width='500'><br>
<img src='./img/labels-dark.PNG' width='500'><br>
<img src='./img/Area-charts.PNG' width='500'><br>
<img src='./img/modal-background.PNG' width='500'><br>
<img src='./img/Carousel-button.PNG' width='500'><br>

## CSS Tutorial

- background:url('image.jpeg');
- background-repeat
- background-size
- background-position
- background-attachment
- shorthand syntax

The background property in CSS allows you to control the background of any element (what paints underneath the content in that element). It is a shorthand property, which means that it allows you to write what would be multiple CSS properties in one.

<img src='./img/CSSbackground.PNG'><br>

```
body {
  background:
     url(sweettexture.jpg)    /* image */
     top center / 200px 200px /* position / size */
     no-repeat                /* repeat */
     fixed                    /* attachment */
     padding-box              /* origin */
     content-box              /* clip */
     red;                     /* color */
}

```

<b>background-color</b> property specifies the background color of an element.

```
body {
  background-color: lightblue;
}

```

With CSS, a color is most often specified by:

a valid color name - like "red"
a HEX value - like "#ff0000"
an RGB value - like "rgb(255,0,0)"

<b>CSS background-image</b>
-specifies an image to use as the background of an element.

By default, the image is repeated so it covers the entire element.

```
body {
  background-image: url("paper.gif");
}
```

<b>CSS background-repeat</b><br>
By default, the background-image property repeats an image both horizontally and vertically.<br>
note:To repeat an image vertically, set background-repeat: repeat-y;<br>
note:To repeat an image horizontally, set background-repeat: repeat-x;<br>

```
body {
  background-image: url("gradient_bg.png");
  background-repeat: repeat-x;
}
```

<b>background-repeat: no-repeat</b><br>
Showing the background image only once

```
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
}
```

<b>background-position</b><br>
used to specify the position of the background image.

```
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```

<b>Linear-gradient</b><br>
<img src="./img/gradient.PNG" width="500">

```
body {
  display: flex;
}

div {
  width: 150px;
  height: 150px;
  margin: 5px;
}

.one {
  background: linear-gradient(red, green);
}
.two {
  background: linear-gradient(to top, red, green, blue, yellow);
}

.three {
  background: linear-gradient(36deg, red, green);
}
.four {
  background: linear-gradient(to top left, red, green);
}

.five {
  background: linear-gradient(
    to top left,
    rgba(0, 0, 0, 0.3),
    rgba(0, 0, 0, 0.9)
  );
}
```

sample overlays using linear-gradient<br>
<img src="./img/adding-gradient.PNG"><br>

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

div {
  height: 50vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-size: 30px;
  color: orange;
}

.banner {
  background: url(./img/big-image.jpeg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
}

.header {
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.9)),
    url(./img/big-image.jpeg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
}
```

```
/* short-hand property */
.header {
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.9)),
    url(./img/big-image.jpeg) center/cover fixed no-repeat;
}
```

[www.colorzilla.com]('https://www.colorzilla.com/gradient-editor/)

## CSS Tutorial

- float, clear
- position:static,relative,absolute,fixed
- media-queries
- z-index
- ::before and ::after pseudo elements

<b>Overflow</b>
The CSS overflow property controls what happens to content that is too big to fit into an area.
<br>
The overflow property specifies whether to clip the content or to add scrollbars when the content of an element is too big to fit in the specified area.
<br>
The overflow property has the following values:
<br>

- visible - Default. The overflow is not clipped. The content renders outside the element's box
- hidden - The overflow is clipped, and the rest of the content will be invisible
- scroll - The overflow is clipped, and a scrollbar is added to see the rest of the content
- auto - Similar to scroll, but it adds scrollbars only when necessary

<code>
Note: The overflow property only works for block elements with a specified height.
</code><br>

<b>overflow:visible;</b><br>
By default, the overflow is visible, meaning that it is not clipped and it renders outside the element's box:<br>

<img src='./img/overflow-visible.PNG' width='500'>

```
.banner {
  border: 5px solid red;
  padding: 10px;
  width:200px;
  height:100px;
  overflow:visible; /*default*/
}
```

<b>flow: hidden</b><br>
With the hidden value, the overflow is clipped, and the rest of the content is hidden:<br>

<img src='./img/overflow-hidden.PNG' width='500'>

```
.banner {
  border: 5px solid red;
  padding: 10px;
  width: 200px;
  height: 100px;
  overflow: hidden;
}
```

<b>overflow: scroll</b><br>
Setting the value to scroll, the overflow is clipped and a scrollbar is added to scroll inside the box. Note that this will add a scrollbar both horizontally and vertically (even if you do not need it):<br>

<img src='./img/overflow-scroll.PNG' width='500'>

```
.banner {
  border: 5px solid red;
  padding: 10px;
  width: 200px;
  height: 100px;
  overflow: scroll;
}
```

<b>overflow: auto</b><br>
The auto value is similar to scroll, but it adds scrollbars only when necessary:<br>

<img src='./img/overflow-auto.PNG' width='500'>

```
.banner {
  border: 5px solid red;
  padding: 10px;
  width: 200px;
  height: 100px;
  overflow: auto;
}
```

<b>overflow-x and overflow-y/b></b><br>
The overflow-x and overflow-y properties specifies whether to change the overflow of content just horizontally or vertically (or both):<br>

- <b>overflow-x </b>specifies what to do with the left/right edges of the content.
- <b>overflow-y </b>specifies what to do with the top/bottom edges of the content.

<img src='./img/overflow-xy.PNG' width='500'>

```
.banner {
  border: 5px solid red;
  padding: 10px;
  width: 200px;
  height: 100px;
  overflow-y: hidden;
  overflow-x: scroll;
}
```

<code><h2>Useful Overflow Use Cases</h2></code>
<img src="./img/float-right.PNG" width='500'><br>
<b>float and clear</b><br/>

<b>float</b> property specifies how an element should float.<br>
<b>clear</b> property specifies what elements can float beside the cleared element and on which side.

<b>The float Property</b><br>
The float property is used for positioning and formatting content e.g. let an image float left to the text in a container.<br>

<b>Float values</b><br>

- <code>left</code> - The element floats to the left of its container
- <code>right</code> - The element floats to the right of its container
- <code>none</code> - The element does not float (will be displayed just where - it occurs in the text). This is default
- <code>inherit</code> - The element inherits the float value of its parent

<br>
<code>Float:right</code><br>
specifies that an image should float to the right in a text<br>
<img src="./img/sunsetGradient.PNG" width='500'>
<br>
<img src="./img/ribbons.PNG" width='500'>
<br>
<img src="./img/vertical-scroll.PNG" width='500'>
<br>
<img src="./img/horizontal-scroll.PNG" width='500'>
<br>
<img src="./img/carousels.PNG" width='500'>
<br>
<img src="./img/triangles.PNG" width='500'>
<br>
<img src="./img/crop-image.PNG" width='500'>
<br>
<img src="./img/data-tables.PNG" width='500'>
<br>

```
* {
  margin: 0.5rem;
  padding: 0;
  box-sizing: border-box;
}

.banner {
  border: 5px solid red;
  padding: 10px;
  width: calc(100vw - 1rem);
  height: 200px;
  overflow: hidden;
  margin: auto;
}

img {
  width: 100px;
  height: 100px;
  float: right;
}
```

<br>
<code>Float:left</code><br>
specifies that an image should float to the left in a text<br>
<img src="./img/float-left.PNG" width='500'>
<br>

```
* {
  margin: 0.5rem;
  padding: 0;
  box-sizing: border-box;
}

.banner {
  border: 5px solid red;
  padding: 10px;
  width: calc(100vw - 1rem);
  height: 200px;
  overflow: hidden;
  margin: auto;
}

img {
  width: 100px;
  height: 100px;
  float: left;
}
```

<br>
<b>clear Property</b><br>
When we use the <code>float</code> property, and we want the next element below (not on right or left), we will have to use the <code>clear</code> property.<br>
The <code>clear</code> property specifies what should happen with the element that is next to a floating element.
<br>

<b>clear Property Values</b>

- <code>none</code> - The element is not pushed below left or right floated elements. This is default
- <code>left</code> - The element is pushed below left floated elements
- <code>right</code> - The element is pushed below right floated elements
- <code>both </code>- The element is pushed below both left and right floated elements
- <code>inherit</code> - The element inherits the clear value from its parent

Notes<br>
<code>
When clearing floats, you should match the clear to the float: If an element is floated to the left, then you should clear to the left. Your floated element will continue to float, but the cleared element will appear below it on the web page.
</code><br>

sample:<br>
<img src="./img/clear.PNG" width='500'>

```
* {
  margin: 0.5rem;
  padding: 0;
  box-sizing: border-box;
}

div {
  border: 5px solid red;
  padding: 10px;
  width: calc(100vw - 1rem);
  height: 200px;
  overflow: hidden;
  margin: auto;
}
img {
  width: 100px;
  height: 100px;
    float: left;
}

p {
  float: left;
}
```

<code><strong>"clearfix Hack"!</strong></code><br>
if a floated element is taller than the containing element, it will "overflow" outside of its container.We can then add a <code>clearfix hack</code> to solve this problem:
<br>

<img src='./img/overflow-auto2.PNG' width='500'>

```
* {
  margin: 0.5rem;
  padding: 0;
  box-sizing: border-box;
}

div {
  border: 5px solid red;
  padding: 10px;
  overflow: auto;
  margin: auto;
}
img {
  width: 200px;
  height: 200px;
  float: left;
}
```

-Note<br>
the <code>overflow:auto</code> clearfix works well as long as you are able to keep control of your margins and padding (else you might see scrollbars).the <b>new, modern clearfix hack</b> however, is safer to use:<br>

<code>new modern clearfix hack</code><br>
<img src='./img/clearFixModern.PNG' width='500'>

<b>Position Property</b><br>
specifies the type of positioning method used for an element (static, relative, absolute and sticky<br>

<code>Position Values</code>

- static
  > <code>default</code>, always positioned according to the normal flow
- relative
  > position relative to its normal positioned.
  > top,bottom, left, right
- fixed
- absolute
- sticky

Notes:<br>
elements are then positioned using the top, bottom, left, and right properties. However, these properties will not work unless the <code>position</code> property is set first.they will also work differently depending on the position value.<br>

<b>static</b><br>
<img src='./img/static.PNG' width='500'>
-static default position<br>
-Static positioned elements are not affected by the top,bottom,left,and right.<br>
-an element with <code>position:static;</code> is not positioned in any special way;it is always positioned according to the normal flow of the page:<br>

```
* {
  margin: 0.5rem;
  padding: 0;
  box-sizing: border-box;
}

div {
  border: 3px solid red;
  background: yellow;
  margin: 4px;
}

.one {
  background: blue;
  color: white;
}

.two {
  background: greenyellow;
}

.special {
  background: hotpink;
  font-size: 20px;
}
```

<b>relative</b><br>
<img src='./img/relative2.PNG' width='500'><br>
-same with static<br>
-an element with <code>position:relative;</code> is positioned relative to its normal position.<br>
-setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted to fit into any gap left by the element<br>

```
* {
  margin: 0.5rem;
  padding: 0;
  box-sizing: border-box;
}

div {
  border: 3px solid red;
  background: yellow;
  margin: 4px;
}

.one {
  background: blue;
  color: white;
  position: relative;
  top: 200px;
}

.two {
  background: greenyellow;
}

.special {
  background: hotpink;
  font-size: 20px;
}

```

<b>absolute</b><br>
<img src='./img/position-absolute.PNG' width='500'><br>

an element with <code>position:absolute;</code> is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport.)<br>
however,if an absolute positioned element has no positioned ancestors, it used the document body, and moves along with page scrolling.<br>
<code>Notes:</code>
<br> a "positioned" element is one whose position is anything except <code>static</code>

```
* {
  margin: 0.5rem;
  padding: 0;
  box-sizing: border-box;
}
div {
  border: 3px solid red;
  background: yellow;
  margin: 4px;
}
.one {
  background: blue;
  color: white;
}
.two {
  background: greenyellow;
  position: relative;
  left: -0.5rem;
}
.special {
  background: hotpink;
  font-size: 20px;
  position: absolute;
  top: 100px;
  left: 0;
}
```

<b>fixed</b><br>
<img src='./img/fixed.PNG' width='500'><br>
-an element with <code>position:fixed;</code> is positioned relative to the viewport, which means it always stays in the same place even if the page scrolled. The top, right, bottom, and left properties are used to position the element.<br>

```
* {
  margin: 0.5rem;
  padding: 0;
  box-sizing: border-box;
}
div {
  border: 3px solid red;
  background: yellow;
  margin: 4px;
}
.one {
  background: blue;
  color: white;
}
.two {
  background: greenyellow;
  left: -0.5rem;
}
.special {
  background: hotpink;
  font-size: 20px;
  position: fixed;
  top: 0;
  left: 0;
}

```

<b>sticky</b><br>

- an element with <code> position:sticky</code> is positioned based on the user's scroll position.
  <br>
  a sticky element toggles between relative and fixed.depending on the scroll position. It is positioned relative until the given offset position is met in the viewport then sticks in place(like position:fixed)<br>

<code><h1>Media Queries</h1></code>
Responsive Design<br>
Style elements on different screen sizes<br>
min-width: --- starting from:<br>
max-width: --- up to<br>
Mobile first<br>

<code> What is media query?</code><br>
a media query is a css technique introduced in css3.<br>
it is uses the <code>@media</code> rule to include a block of CSS properties if a certain condition is true:<br>

Media queries can be used to check many things,such as:<br>

- width and height of the viewport<br>
- width and height of the device<br>
- orientation(is the tablet/phone in landscapre or portrait mode?)<br>

<code> Media Query syntax</code><br>
-a media query consist of a media type and can contain one or more expressions, which resolve to either true or false<br>

<code>@media not|only mediatype and (expressions){
CSS-Code;</code>
}

```
@media screen and (min-width:576px) {
  body {
    background: red;
  }
  .banner {
    background: yellow;
  }
  h1 {
    color: black;
    font-size: 60px;
  }
}
```

<code>z-index ---- z-axis<br>
position:static --- does not work<br>
</code><br>

property specifies the stack of an element.<br>
an element with greater stack order is always in front of an element with a lower stack order<br>

<code>Note</code><br>
<code>z-index</code> only works on positioned elements(position:absolute,relative,fixed,sticky) and flex(elements that are direct children of display flex elements)<br>

<img src='./img/z-index.PNG' width='500'><br>

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.banner {
  margin: 20px;
  width: 80vw;
  height: 70vh;
  border: 5px solid red;
  position: relative;
}
img {
  width: 100px;
  height: 100px;
  position: absolute;
  border: 1px solid white;
}
.one {
  top: 0;
  left: 0;
}
.two {
  top: 10%;
  left: 10%;
  z-index: 1;
}
.three {
  top: 20%;
  left: 20%;
  z-index: -1;
}


```

<code>pseudo elements <b>::before</b> <b>::after</b> content not element:<br>
content:'' - required<br>
img -- does not work</code> <br>
<img src='./img/beforeAfter.PNG' width='500'>

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

div {
  width: 60vw;
  margin: 100px auto;
  position: relative;
}

img {
  width: 100%;
  display: block;
}

div::before {
  content: '';
  border: 2px solid grey;
  width: 100%;
  height: 100%;
  position: absolute;
  box-sizing: border-box;
  top: -20px;
  left: -20px;
  z-index: -1;
  transition: all 0.5s linear;
}

div::after {
  content: '';
  border: 2px solid red;
  background-color: red;
  width: 100%;
  height: 100%;
  position: absolute;
  box-sizing: border-box;
  top: -10px;
  left: -10px;
  z-index: -1;
  transition: all 0.5s linear;
}

div:hover::after,
div:hover::before {
  top: 0;
  left: 0;
}

```

<br>
<strong> CSS Tutorial </strong><br>

- Basic Selectors
- Pseudo Class Selectors
- Pseudo Element Selectors
<hr>
<code>/* basic selectors*/</code><br>
<img src='./img/basic-selector.PNG' width='500'><br>
<code>/* Descendant and child combinators*/</code><br>
-a <code>combinators</code> is something that explains the relationship between the selectors.<br>

<b>four different combinators in CSS</b><br>

- decendant selectors (space)

  > <i>elment element</i><br> > <code>div p</code><br>
  > selects all <code>\<p></code> elements inside <code>\<div></code> elements<br>

- child selectors (>)

  > <i>elment>element</i><br> > <code>div > p</code><br>
  > selects all <code>\<p></code> elements where the parent is a <code>\<div></code> elements<br>

- adjacent siblings selector(+)

  > <i>elment+element</i><br> > <code>div + p</code><br>
  > selects the first <code>\<p></code> elements that are placed immediately after <code>\<div></code> elements<br>

- general siblings selector(~)
  > <i>elment~element</i><br> > <code>p ~ ul</code><br>
  > selects every<code>\<ul></code> elements that are preceded by a<code>\<p></code> elements<br>
  > preceded:come before (something) in time<br>

<code>/_::first-letter & ::first-line_/</code><br>
<img src='./img/first.PNG' width='500'> <br>

```
p::first-letter {
  font-size: 3rem;
}

p::first-line{
  font-weight: bold;
}
```

<br>
<strong> CSS Tutorial </strong><br>

- transform: translate(), rotate(), scale(),skew()
- transition (change over time)
- animation: (change over time with points)
<hr>

<br>
<strong> CSS Tutorial </strong><br>
- transform: translate(), rotate(), scale(),skew()
- transition (change over time)
- animation: (change over time with points)
<hr>

<code>transform:translate</code><br>
-the translate method moves an element from its current position(according to the parameters given for the x-axis and the y-axis)<br>
<img src='./img/transfor-translate.PNG' width='500'>

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

div {
  width: 150px;
  height: 150px;
  display: inline-block;
}
.one {
  background: red;
  transform: translateX(50%);
}

.two {
  background: green;
  transform: translateY(50%);
  position:relative;
  z-index: 1;
}

.three {
  background: blue;
  transform: translate(-25%, 100%);
}
```

<code>transform:scale</code><br>
-the scale method increases or decreases the size of an element (according to the parameters given for the width and height)<br>
<img src='./img/scale.PNG' width='500'>

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

div {
  width: 150px;
  height: 150px;
  display: inline-block;
}
.one {
  background: red;
  transform: scaleX(0.5);
}

.two {
  background: green;
  transform: scaleY(5);
}

.three {
  background: blue;
  transform: scale(2,4);
}
```

<code>transform:rotate</code><br>
-the rotate method rotates an element clockwise or counter-clockwise according to a given degree/<br>
<img src='./img/rotate.PNG' width='500'>

```
* {
  margin: 2rem;
  padding: 0;
  box-sizing: border-box;
}

div {
  width: 150px;
  height: 150px;
  display:inline-block;
}
.one {
  background: red;
  transform: rotate(10deg);
}

.two {
  background: green;
   transform: rotate(-45deg);
}

.three {
  background: blue;
   transform: rotate(80deg);
}
```

<code>
transition : change over time:<br>
transition-property :<br>
transition-duration :<br>
</code>

sample:

```
:root {
  margin: 5rem;
  padding: 0;
  box-sizing: border-box;
}
div {
  width: 150px;
  height: 150px;
  display: inline-block;
}
div:hover {
  background: crimson;
  transform: scale(50) rotate(90deg);
  border-radius: 50%;
}
.one {
  background: red;
  transition-property: background, transform, border-radius;
  transition-duration: 2s, 2s, 1s;
  transition-delay:5s;
}
```

<code>
transition : change over time:<br>
transition-delay :<br>
transition shorthand :<br>
</code>

shorthand syntax:

> transition : transition-property transition-duration transition-delay(optional),transition-property transition-duration transition-delay(optional)<br>

0r

> transition :all transition-duration transition-delay(optional)

```
:root {
  margin: 5rem;
  padding: 0;
  box-sizing: border-box;
  overflow: hidden;
}
div {
  width: 150px;
  height: 150px;
  display: inline-block;
}
div:hover {
  background: crimson;
  transform: scale(2) rotate(90deg);
  border-radius: 50%;
}
.one {
  background: red;
  transition: background 2s, transform 2s, border-radius 2s 0.2s;

```

<code>
how the transition takes place <br>
transition-timing-function: <br>
transition:all 3s here 5s; <br>
ease = default <br>
ease = slow start, fast, slow end <br>
linear = same speed start to end <br>
ease-in = slow start <br>
ease-out = slow end <br>
ease-in-out = slow start, fast, slow end <br>
</code>
<br>

```
div {
  width: 100px;
  height: 100px;
  background: blue;
  color: white;
  margin: 15px;
  transition: all 1s;
}

div:hover {
width:400px;
}

.ease {
transition-timing-function: ease;
}

.linear {
transition-timing-function: linear;
}

.ease-in {
transition-timing-function: ease-in;
}

.ease-out {
transition-timing-function: ease-out;
}

.ease-in-out {
transition-timing-function: ease-in-out;
}

```

<img src='./img/transition.PNG' width='500'>
