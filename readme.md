
# Questions Bellow:

# How to add comments on css?
=>  place your plain text inside /* */ marks. 

Examples: 
```js
/* A one-line comment */

/*
A comment
which stretches
over several
lines
*/

/* The comment below is used to
   disable specific styling */
/*
span {
  color: blue;
  font-size: 1.5em;
}
*/
```

# Why do we use pseudo-class?
=> A pseudo-class is used to define a special state of an element. For example, it can be used to: Style an element when a user mouses over it. Style visited and unvisited links differently.

```js
/* Any button over which the user's pointer is hovering */
button:hover {
  color: blue;
}
```

# How is specificity applied?
=> Specificity is the means by which browsers decide which CSS property values are the most relevant to an element and, therefore, will be applied. Specificity is based on the matching rules which are composed of different sorts of CSS selectors.

Specificity is a weight that is applied to a given CSS declaration, determined by the number of each selector type in the matching selector. When multiple declarations have equal specificity, the last declaration found in the CSS is applied to the element. Specificity only applies when the same element is targeted by multiple declarations. As per CSS rules, directly targeted elements will always take precedence over rules which an element inherits from its ancestor.

**OR**

If there are two or more CSS rules that point to the same element, the selector with the highest specificity value will "win", and its style declaration will be applied to that HTML element.

Think of specificity as a score/rank that determines which style declaration are ultimately applied to an element.

Look at the following examples:

**Example 1:**
In this example, we have used the "p" element as selector, and specified a red color for this element. The text will be red:
```js
<html>
<head>
  <style>
    p {color: red;}
  </style>
</head>
<body>

<p>Hello World!</p>

</body>
</html>
```

**Example 2:**
In this example, we have added a class selector (named "test"), and specified a green color for this class. The text will now be green (even though we have specified a red color for the element selector "p". This is because the class selector is given higher priority:
```js
<html>
<head>
  <style>
    .test {color: green;}
    p {color: red;}
  </style>
</head>
<body>

<p class="test">Hello World!</p>

</body>
</html>
```

**Example 3:**
In this example, we have added the id selector (named "demo"). The text will now be blue, because the id selector is given higher priority:
```js
<html>
<head>
  <style>
    #demo {color: blue;}
    .test {color: green;}
    p {color: red;}
  </style>
</head>
<body>

<p id="demo" class="test">Hello World!</p>

</body>
</html>
```

**Example 4:**
In this example, we have added an inline style for the "p" element. The text will now be pink, because the inline style is given the highest priority:
```js
<html>
<head>
  <style>
    #demo {color: blue;}
    .test {color: green;}
    p {color: red;}
  </style>
</head>
<body>

<p id="demo" class="test" style="color: pink;">Hello World!</p>

</body>
</html>
```

**Equal specificity: the latest rule wins** - If the same rule is written twice into the external style sheet, then the latest rule wins:

**Example:**
```js
h1 {background-color: yellow;}
h1 {background-color: red;}
```

# What method allows an element to be moved from its current position?
=>  The translate() method moves an element from its current position (according to the parameters given for the X-axis and the Y-axis).

The following example moves the <div> element 50 pixels to the right, and 100 pixels down from its current position:

**Examples->**
```js
div {
  transform: translate(50px, 100px);
}
```

# what properties does flex model have?
=> The flex property sets the flexible length on flexible items. Note: If the element is not a flexible item, the flex property has no effect.
...
The flex property is a shorthand property for:
- flex-grow.
- flex-shrink.
- flex-basis.

**Example:**
Set the initial length of the second flex-item to 100 pixels:
```js
div:nth-of-type(2) {
  flex-basis: 100px;
}
```

**Example:**
Let the second flex-item grow three times wider than the rest:
```js
div:nth-of-type(1) {flex-grow: 1;}
div:nth-of-type(2) {flex-grow: 3;}
div:nth-of-type(3) {flex-grow: 1;}
```

**Example:**
Let the second flex-item shrink three times more than the rest:
```js
div:nth-of-type(2) {
  flex-shrink: 3;
}
```
```js
<!DOCTYPE html>
<html>
<head>
<style> 
#main {
  width: 350px;
  height: 100px;
  border: 1px solid #c3c3c3;
  display: flex;
}

#main div {
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 100px;
}

#main div:nth-of-type(2) {
  flex-shrink: 3;
}
</style>
</head>
<body>

<h1>The flex-shrink Property</h1>

<div id="main">
  <div style="background-color:coral;"></div>
  <div style="background-color:lightblue;"></div>
  <div style="background-color:khaki;"></div>
  <div style="background-color:pink;"></div>
  <div style="background-color:lightgrey;"></div>
</div>

<p><b>Note:</b> Internet Explorer 10 and earlier versions do not support the flex-shrink property.</p>

</body>
</html>
```

# What is the difference between flex and grids?
=> Grid is made for two-dimensional layout while Flexbox is for one. This means Flexbox can work on either row or columns at a time, but Grids can work on both. Flexbox, gives you more flexibility while working on either element (row or column).

Difference Between Grid and Flexbox:

1. **Dimensionality and Flexibility:**
Flexbox offers greater control over alignment and space distribution between items. Being one-dimensional, Flexbox only deals with either columns or rows.
Grid has two-dimension layout capabilities which allow flexible widths as a unit of length. This compensates for the limitations in Flex.

2. **Alignment:**
Flex Direction allows developers to align elements vertically or horizontally, which is used when developers create and reverse rows or columns.
CSS Grid deploys fractional measure units for grid fluidity and auto-keyword functionality to automatically adjust columns or rows.

3. **Item Management**
Flex Container is the parent element while Flex Item represents the children. The Flex Container can ensure balanced representation by adjusting item dimensions. This allows developers to design for fluctuating screen sizes.
Grid supports both implicit and explicit content placement. Its inbuilt automation allows it to automatically extend line items and copy values into the new creation from the preceding item.


**Property           Grid                  Flexbox**

Dimension       Two – Dimensional         One – Dimensional

Features        Can flex combination      Can push content element
                of items through          to extreme alignment
                space-occupying Features

Support Type    Layout First             Content First


# Give an example where we have to use grids and where you have to use flexbox?
=> CSS Grid and Flexbox are layout models that share similarities and can be used together. The key difference is that CSS Grid can be used to create two-dimensional layouts, while Flexbox can only be used to create one-dimensional layouts.

**Grid:** CSS Grid Layout, is a two-dimensional grid-based layout system with rows and columns, making it easier to design web pages without having to use floats and positioning. Like tables, grid layout allow us to align elements into columns and rows.

To get started you have to define a container element as a grid with display: grid, set the column and row sizes with grid-template-columns and grid-template-rows, and then place its child elements into the grid with grid-column and grid-row.
Example: 
```js
<!DOCTYPE html>
<html lang="en">
<head>
	<style>
		.main{
			
			display: grid;
			display: grid;
			grid: auto auto / auto auto auto auto;
			grid-gap: 10px;
			background-color: green;
			padding: 10px;
		}
		.gfg {
			background-color: rgb(255, 255, 255);
			text-align: center;
			padding: 25px 0;
			font-size: 30px;
		}
	</style>
</head>
<body>
	<h2 style="text-align: center;">Welcome To GeeksForGeeks </h2>
	<div class="main">
		<div class="gfg">Home</div>
		<div class="gfg">Read</div>
		<div class="gfg">Write</div>
		<div class="gfg">About Us</div>
		<div class="gfg">Contact Us</div>
		<div class="gfg">Privacy Policy</div>
	</div>
</body>
</html>
```
**Flexbox:** The CSS Flexbox offers a one-dimensional layout. It is helpful in allocating and aligning the space among items in a container (made of grids). It works with all kinds of display devices and screen sizes.

To get started you have to define a container element as a grid with display: flex;

Example:
```js
<!DOCTYPE html>
<html lang="en">
<head>
	<style>
		.main{
			
			display: flex;
			display: flex;
			grid: auto auto / auto auto auto auto;
			grid-gap: 10px;
			background-color: green;
			padding: 10px;
		}
		.gfg {
			background-color: rgb(255, 255, 255);
			text-align: center;
			padding: 25px 0;
			font-size: 30px;
		}
	</style>
</head>
<body>
	<h2 style="text-align: center;">Welcome To GeeksForGeeks </h2>
	<div class="main">
		<div class="gfg">Home</div>
		<div class="gfg">Read</div>
		<div class="gfg">Write</div>
		<div class="gfg">About Us</div>
		<div class="gfg">Contact Us</div>
		<div class="gfg">Privacy Policy</div>
	</div>
</body>
</html>
```

# Give an example where you cannot use flexbox, and you can only use grids?
=> The basic difference between CSS Grid Layout and CSS Flexbox Layout is that flexbox was designed for layout in one dimension - either a row or a column. Grid was designed for two-dimensional layout - rows, and columns at the same time. The two specifications share some common features, however, and if you have already learned how to use flexbox, the similarities should help you get to grips with Grid.

In this first example, I am using flexbox to lay out a set of boxes. I have five child items in my container, and I have given the flex properties values so that they can grow and shrink from a flex-basis of 150 pixels.

I have also set the flex-wrap property to wrap, so that if the space in the container becomes too narrow to maintain the flex basis, items will wrap onto a new row.
```js
<div class="wrapper">
  <div>One</div>
  <div>Two</div>
  <div>Three</div>
  <div>Four</div>
  <div>Five</div>
</div>

.wrapper {
  width: 500px;
  display: flex;
  flex-wrap: wrap;
}
.wrapper > div {
  flex: 1 1 150px;
}
```

The same layout with CSS grids:

In this next example, I create the same layout using Grid. This time we have three 1fr column tracks. We do not need to set anything on the items themselves; they will lay themselves out one into each cell of the created grid. As you can see they stay in a strict grid, lining up in rows and columns. With five items, we get a gap on the end of row two.
```js
<div class="wrapper">
  <div>One</div>
  <div>Two</div>
  <div>Three</div>
  <div>Four</div>
  <div>Five</div>
</div>

.wrapper {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```
A simple question to ask yourself when deciding between grid or flexbox is:

- do I only need to control the layout by row or column – use a flexbox
- do I need to control the layout by row and column – use a grid

# What are combinators? give examples of how you can use them
=> A combinator is something that explains the relationship between the selectors. A CSS selector can contain more than one simple selector. Between the simple selectors, we can include a combinator.

There are four different combinators in CSS:

- descendant selector (space)
- child selector (>)
- adjacent sibling selector (+)
- general sibling selector (~)

**Descendant Selector:** 
The descendant selector matches all elements that are descendants of a specified element.

The following example selects all <p> elements inside <div> elements: 

Example: 
```js
div p {
  background-color: yellow;
}
```
**Child Selector (>):**
The child selector selects all elements that are the children of a specified element.

The following example selects all <p> elements that are children of a <div> element:

Example:
```js
div > p {
  background-color: yellow;
}
```

**Adjacent Sibling Selector (+):**
The adjacent sibling selector is used to select an element that is directly after another specific element.

Sibling elements must have the same parent element, and "adjacent" means "immediately following".

The following example selects the first <p> element that are placed immediately after <div> elements:

Example:
```js
div + p {
  background-color: yellow;
}
```

**General Sibling Selector (~):**
The general sibling selector selects all elements that are next siblings of a specified element.

The following example selects all <p> elements that are next siblings of <div> elements: 

Example:
```js
div ~ p {
  background-color: yellow;
}
```

# What does object-fit do?
=> The object-fit property is used to specify how an <img> or <video> should be resized to fit its container.

This property tells the content to fill the container in a variety of ways; such as "preserve that aspect ratio" or "stretch up and take up as much space as possible".

Example: 
Cut off the sides of an image, preserving the aspect ratio, and fill in the space:
```js
img.a {
  width: 200px;
  height: 400px;
  object-fit: cover;
}
```

Syntax:
```js
object-fit: contain;
object-fit: cover;
object-fit: fill;
object-fit: none;
object-fit: scale-down;

/* Global values */
object-fit: inherit;
object-fit: initial;
object-fit: revert;
object-fit: unset;
```
The object-fit property is specified as a single keyword chosen from the list of values.

# What does rotate do?
=> The rotate() CSS function defines a transformation that rotates an element around a fixed point on the 2D plane, without deforming it. Its result is a <transform-function> data type.

The fixed point that the element rotates around — mentioned above — is also known as the transform origin. This defaults to the center of the element, but you can set your own custom transform origin using the transform-origin property.

Syntax: 
The amount of rotation created by rotate() is specified by an <angle>. If positive, the movement will be clockwise; if negative, it will be counter-clockwise. A rotation by 180° is called point reflection.
```js
rotate(a)
```

Example:
```js
<div>Normal</div>
<div class="rotated">Rotated</div>

div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.rotated {
  transform: rotate(45deg); /* Equal to rotateZ(45deg) */
  background-color: pink;
}
```

# What rule can be used to define animations?
=> The @keyframes rule specifies the animation code. The animation is created by gradually changing from one set of CSS styles to another. During the animation, you can change the set of CSS styles many times.

Example: 
Make an element move gradually 200px down:
```js
@keyframes mymove {
  from {top: 0px;}
  to {top: 200px;}
}
```

# When working with attribute selectors, how can you select elements which contain a particular attribute value?
=> The [attribute|="value"] selector is used to select elements with the specified attribute, whose value can be exactly the specified value, or the specified value followed by a hyphen (-).

The CSS attribute selector matches elements based on the presence or value of a given attribute.
```js
/* <a> elements with a title attribute */
a[title] {
  color: purple;
}

/* <a> elements with an href matching "https://example.org" */
a[href="https://example.org"] {
  color: green;
}

/* <a> elements with an href containing "example" */
a[href*="example"] {
  font-size: 2em;
}

/* <a> elements with an href ending ".org" */
a[href$=".org"] {
  font-style: italic;
}

/* <a> elements whose class attribute contains the word "logo" */
a[class~="logo"] {
  padding: 2px;
}

a {
  color: blue;
}

/* Internal links, beginning with "#" */
a[href^="#"] {
  background-color: gold;
}

/* Links with "example" anywhere in the URL */
a[href*="example"] {
  background-color: silver;
}

/* Links with "insensitive" anywhere in the URL,
   regardless of capitalization */
a[href*="insensitive" i] {
  color: cyan;
}

/* Links with "cAsE" anywhere in the URL,
with matching capitalization */
a[href*="cAsE" s] {
  color: pink;
}

/* Links that end in ".org" */
a[href$=".org"] {
  color: red;
}

/* Links that start with "https" and end in ".org" */
a[href^="https"][href$=".org"] {
  color: green;
}

<ul>
  <li><a href="#internal">Internal link</a></li>
  <li><a href="http://example.com">Example link</a></li>
  <li><a href="#InSensitive">Insensitive internal link</a></li>
  <li><a href="http://example.org">Example org link</a></li>
  <li><a href="https://example.org">Example https org link</a></li>
</ul>


/* All divs with a `lang` attribute are bold. */
div[lang] {
  font-weight: bold;
}

/* All divs without a `lang` attribute are italicized. */
div:not([lang]) {
  font-style: italic;
}

/* All divs in US English are blue. */
div[lang~="en-us"] {
  color: blue;
}

/* All divs in Portuguese are green. */
div[lang="pt"] {
  color: green;
}

/* All divs in Chinese are red, whether
   simplified (zh-CN) or traditional (zh-TW). */
div[lang|="zh"] {
  color: red;
}

/* All divs with a Traditional Chinese
   `data-lang` are purple. */
/* Note: You could also use hyphenated attributes
   without double quotes */
div[data-lang="zh-TW"] {
  color: purple;
}

<div lang="en-us en-gb en-au en-nz">Hello World!</div>
<div lang="pt">Olá Mundo!</div>
<div lang="zh-CN">世界您好！</div>
<div lang="zh-TW">世界您好！</div>
<div data-lang="zh-TW">世界您好！</div>

/* Case-sensitivity depends on document language */
ol[type="a"] {
  list-style-type: lower-alpha;
  background: red;
}

ol[type="b" s] {
  list-style-type: lower-alpha;
  background: lime;
}

ol[type="B" s] {
  list-style-type: upper-alpha;
  background: grey;
}

ol[type="c" i] {
  list-style-type: upper-alpha;
  background: green;
}

<ol type="A">
  <li>Red background for case-insensitive matching (default for the type selector)</li>
</ol>
<ol type="b">
  <li>Lime background if `s` modifier is supported (case-sensitive match)</li>
</ol>
<ol type="B">
  <li>Grey background if `s` modifier is supported (case-sensitive match)</li>
</ol>
<ol type="C">
  <li>Green background if `i` modifier is supported (case-insensitive match)</li>
</ol>

input[type="text"] {
  width: 150px;
  display: block;
  margin-bottom: 10px;
  background-color: yellow;
}

input[type="button"] {
  width: 120px;
  margin-left: 35px;
  display: block;
}
```

# What does @media do?
=> The @media rule is used in media queries to apply different styles for different media types/devices. Media queries can be used to check many things, such as: 
- width and height of the viewport. 
- width and height of the device.

Example: 
Change the background color of the <body> element to "lightblue" when the browser window is 600px wide or less:
```js
@media only screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

# What can be used to override properties of an element?
=> How to override !important. 
- Add another CSS rule with !important , and either give the selector a higher specificity (adding a tag, id or class to the selector), or add a CSS rule with the same selector at a later point than the existing one. This works because in a specificity tie, the last rule defined wins.


# How can you select every alternate elements in a list of elements using css?
=> 
```js
.text:nth-child(odd)
{
    color: green;
}
.text:nth-child(even)
{ 
      color:Red;
}
```

# What is the ranking of selectors with respect to specificity?
=> Every selector has its place in the specificity hierarchy. If two selectors apply to the same element, the one with higher specificity wins. There are four distinct categories which define the specificity level of a given selector: 
- inline styles,
- IDs, 
- classes, 
- attributes, and 
- elements.

# How can we apply same styles to multiple selectors?
=> The grouping selector selects all the HTML elements with the same style definitions. It will be better to group the selectors, to minimize the code. To group selectors, separate each selector with a comma.

Example: 
In this example we have grouped the selectors from the code above: 
```js
h1, h2, p {
  text-align: center;
  color: red;
}
```

# What are the differences between relative and absolute in CSS?
=> position: relative places an element relative to its current position without changing the layout around it, whereas position: absolute places an element relative to its parent's position and changing the layout around it.
![relative-absolute](https://user-images.githubusercontent.com/80479635/161960913-e1a86a1a-db65-42eb-a144-24aafd14752b.jpg)
![relative-absolute1](https://user-images.githubusercontent.com/80479635/161960927-ed567b95-cf2b-4afc-8b1d-769e0a1310b1.png)

