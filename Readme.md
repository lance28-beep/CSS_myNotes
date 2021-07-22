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

<b>External CSS</b>

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

<b>External CSS</b>

```
<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>
```
