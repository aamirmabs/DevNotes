# CSS(Cascading Style Sheets) DevRef <!-- omit in toc -->

CSS is a stylesheet language that is used to describe the presentation of a HTML document. It describes how the elements should be rendered on screen, paper or any other medium.

---

## Contents

- [Contents](#contents)
- [Linking CSS to HTML](#linking-css-to-html)
  - [Inline CSS](#inline-css)
  - [Style Tag](#style-tag)
  - [External CSS](#external-css)
- [CSS Selectors](#css-selectors)
  - [CSS Selectors For Tags](#css-selectors-for-tags)
  - [CSS Selectors For Classes](#css-selectors-for-classes)
  - [CSS Selectors For ID's](#css-selectors-for-ids)
  - [CSS Selectors For Pseudo-Classes](#css-selectors-for-pseudo-classes)
  - [CSS Selectors For Attributes](#css-selectors-for-attributes)
  - [Multiple Selectors](#multiple-selectors)
- [Display and Positioning with CSS](#display-and-positioning-with-css)
  - [CSS Display Property](#css-display-property)
  - [Z-index Property](#z-index-property)
  - [Units: Absolute or Relative](#units-absolute-or-relative)
    - [Absolute Units](#absolute-units)
    - [Relative Units](#relative-units)
- [Typography](#typography)
  - [Text Alignment](#text-alignment)
  - [Text Decoration](#text-decoration)
  - [Text Spacing](#text-spacing)
- [Fonts](#fonts)
  - [Font Family](#font-family)
  - [Font Weight and Style](#font-weight-and-style)
  - [External Fonts](#external-fonts)
- [Media Queries](#media-queries)
  - [Multiple Breakpoints](#multiple-breakpoints)
- [Flexbox](#flexbox)
  - [How to Flex](#how-to-flex)
  - [Steps to Set Flexbox](#steps-to-set-flexbox)
  - [Align and Justify Content](#align-and-justify-content)
- [CSS Grid](#css-grid)
  - [Grid Rows and Columns](#grid-rows-and-columns)
  - [Grid Areas](#grid-areas)

---

## Linking CSS to HTML

There are three ways in which we can link CSS to HTML.

- Inline CSS
- External CSS
- Style Tag

### Inline CSS

```html
<p style="color: red;">I'm learning to code!</p>
```

You can add multiple style rules to inline styles.

```html
<p style="color: red; font-size: 20px;">I'm learning to code!</p>
```

Inline styles have the highest precedence. They will overwrite any CSS declared in the `<style>` element or in an external file.

### Style Tag

"MUST EDIT"

HTML allows you to write CSS code in its own dedicated section with the `<style>` element. CSS can be written between opening and closing `<style>` tags. To use the `<style>` element, it **must be placed _inside_** of the `<head>` element.

```html
<head>
  <style>
    p {
      color: red;
      font-size: 20px;
    }
  </style>
</head>
```

### External CSS

"MUST EDIT"

When HTML and CSS code are in separate files, the files must be linked. Otherwise, the HTML file won’t be able to locate the CSS code, and the styling will not be applied.

You can use the `<link>` element to link HTML and CSS files together. The `<link>` element must be placed within the head of the HTML file. It is a self-closing tag and requires the following three attributes:

- `href` — like the anchor element, the value of this attribute must be the address, or path, to the CSS file.
- `type` — this attribute describes the type of document that you are linking to (in this case, a CSS file). The value of this attribute should be set to text/css.
- `rel` — this attribute describes the relationship between the HTML file and the CSS file.
  Because you are linking to a stylesheet, the value of rel should be set to stylesheet.

When linking an HTML file and a CSS file together, the `<link>` element will look like the following:

```html
<link href="www.abc.com/style.css" type="text/css" rel="stylesheet" />
```

If the CSS file is stored in the same directory as your HTML file, then you can specify a relative path instead of a URL, like so:

```html
<link href="./style.css" type="text/css" rel="stylesheet" />
```

## CSS Selectors

CSS can utilize different types of selectors to target different types of elements on an HTML page.

SYNTAX :

```css
selector {
  property: value;
}

// example
h1 {
  color: purple;
}

.highlight {
  background-color: red;
  font-size: 1.2rem;
}
```

You can use the HTML code snippet below to experiment with the different CSS selectors that we talk about in this section.

```html
<!-- Selectors for tags -->
<h1>Have you heard of Bees?</h1>

<h2>They are the saviors of the planet!</h2>

<p>Bees are flying insects closely related to wasps and ants, known for their role in pollination and, in the case of the best-known bee species, the western honey bee, for producing honey and beeswax. They are found on every continent except Antarctica, in every habitat on the planet that contains insect-pollinated flowering plants.</p>

<h3>Bee facts<span class="small">(for kids)<span></h3>

<ul>
  <li>Beekeepers use smoke to calm bees when they are collecting honey or relocating a hive</li>
  <li>Bees make honey to feed their young and so they have something to eat during the winter.</li>
  <li>Certain species of bees die after stinging.</li>
  <li></li>
  <li></li>
</ul>
```

### CSS Selectors For Tags

Tag selectors are used to target HTML tags.

SYNTAX:

```css
tag {
  property: value;
}

// example
h1 {
  color: red;
}

p {
  font-size: 1.2rem;
}
```

### CSS Selectors For Classes

Class selectors are used to target all elements that belong to class. To target the class we use a dot `.` before the class name to specify the selector.

For example, if the class name is `title`, in CSS we would target the elements with `.title`.

SYNTAX:

```css
.class {
  property: value;
}

// example
.title {
  font-size: 1.5rem;
}
```

### CSS Selectors For ID's

ID selectors are used to target the specific element that is assigned the ID. To target the ID we use a hash `#` before the ID name to specify the selector.

For example, if the class name is `special`, in CSS we would target the elements with `#special`.

SYNATAX:

```css
#id {
  property: value;
}

// example
#special {
  font-size: 1.5rem;
}
```

### CSS Selectors For Pseudo-Classes

dasdf

### CSS Selectors For Attributes

asdf

### Multiple Selectors

Imagine if we needed to set the same CSS Style for a bunch of elements. Say, for example, we wanted to set the same style for all levels of headings, we could write something like this:

```css
h1 {
  font-family: "Arial", sans-serif;
}

h2 {
  font-family: "Arial", sans-serif;
}

h3 {
  font-family: "Arial", sans-serif;
}

h4 {
  font-family: "Arial", sans-serif;
}

h5 {
  font-family: "Arial", sans-serif;
}

h6 {
  font-family: "Arial", sans-serif;
}
```

This would become very cumbersome, hard to scale and over time as the project grows, it will become harder to maintain.

Instead, we can combine all the style declarations and define them together like this:

```css
h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Arial", sans-serif;
}
```

The advantage of doing this is that all the declartions are in a single place and when we do want to make changes to the headings, we will need to do it at a single place.

## Display and Positioning with CSS

### CSS Display Property

CSS display property determines the outside display options of an element. The biggest distinction between the outside display options is whether if the element will occupy the entire line or if the elements be displayed next to each other.

CSS display has 4 main properties:

- `display: block` - Each element will be displayed independently on its own line one after another.
- `display: inline` - Each element is displayed next to each other side by side on the same line.
  - `display: inline` elements do not have any height or width properties.
  - They are usually used to set properties to elements that are displayed in the middle of elements, like highlighting some text in the middle of a sentence.
- `display: inline-block` - Each element will be displayed as a block with height and width properties and will be displayed inline.
- `display: none`

### Z-index Property

If two elements overlap in the display window, we can use the `z-index` and give it a value to control which element is displayed above which one. The element with the _higher value_ is displayed above the element with the lower value.

If element `one` has `z-index: 1` and element `two` has `z-index: -1`, then element `one` will be displayed over element `two` even if it comes after element `two` in the HTML file. This is determined by the `z-index` property.

### Units: Absolute or Relative

Units of measurement in CSS can be categorized into absolute and relative units. Absolute units are ones that are fixed irrespective of the conditions in which the content is being displayed.

If you set the size of some element to `50 px`, it would occupy only `50 px` irrespective of whether if the user had a standard display resolution display or a very high resolution display like a retina display.

But if you would use a relative unit, like `50%` width, then the elements absolute size(measure in how many pixels it would occupy on the screen) would vary from device to device and size of the display port.

#### Absolute Units

Absolute units in CSS are:

- `px`
- `mm`
- `cm`
- `inch`

The usage of absolute units is straight forward. The element will occupy the size spaecified.

#### Relative Units

Relative units in CSS are measured relative to some base unit. The relative units used in CSS are:

- `%` - percentage of something like screen width
- `em` - value equivalent of the current font size. If current font size is 10 px, then 5 em would be 50 px.
- `vw` - units of viewport width. The complete viewport is divided into 100 equal units.
- `vh` - similar to `vw` but the division is along the height.

## Typography

Typography is all about the spacing and the distance between words and paragraphs in CSS. E can control how the words will display with CSS properties that will control aspects such as `font-weight`, `line-height`, `alignment`, etc.

### Text Alignment

Text can me aligned with the `text-align` property in the following directions:

- left
- center
- right

```css
p {
  text-align: left;
}
```

### Text Decoration

The `text-decoration` property can be used to underline and strike through text. The `text-decoration-line` acceptable values are:

- overline
- underline
- line-through
- underline overline

SYNTAX:

`text-decoration: text-decoration-line text-decoration-color text-decoration-style|initial|inherit;`

EXAMPLE:

```css
h1 {
  text-decoration: underline dotted red;
}
```

### Text Spacing

Line height properties are used to determine the spacing between paragraphs and lines. We can alter and modify these by altering these properties:

- `margin-top`/`padding-top`
- `margin-bottom`/`padding-bottom`
- `line-height` - sets the spacing between lines in the same paragraph

## Fonts

### Font Family

`font-family` defines the typeface for the element selected. It accepts multiple values because not all users will have the same fonts installed.

When the browser comes across the declared fonts, it starts looking for the availability of the fonts from left to right and checks to see if it can render the text using the font(s) you've provided. If it can't use the first font, then the browser moves to the next font, and so-on.

### Font Weight and Style

Font weights are expressed as numeric values between 100 and 900. Fortunately, there are relatively standardized, human-friendly terms for each of these numeric values. “Black” usually means 900, “bold” is 700, “regular” is 400, etc.

Font weights are declared with the `font-weight` property.

### External Fonts

External fonts can be linked in many different ways. One of the popular ways to use Google Fonts CDN and import a font to be used.

We can import the font by declaring it in the `<head>` section of the HTML document.

```html
<head>
  <link
    href="https://fonts.googleapis.com/css?family=Montserrat&display=swap"
    rel="stylesheet"
  />
</head>
```

Then, we can use the font in our styles by declaring the font name.

```css
.p {
  font-family: "Montserrat", sans-serif;
}
```

## Media Queries

Expressions that we can add to our code to that can modify our website based on the characteristics of the device that the website is being viewed.

There are a couple of important things that we need to pay attention to when we set media queries:

- `breakpoints` - used to set the `viewport` width at which the layout should change.
- The styles that are written in the media query will come into effect when the page is viewed on a viewport width higher than what we have specified.

SYNTAX:

```css
@media (feature: value) {
  /* settings here */
}
```

EXAMPLE:

```css
@media (min-width: 900px) {
  body {
    background: red;
  }
}
```

### Multiple Breakpoints

We can specify more than one breakpoints to set up different layouts. For example, if we wanted to design three layouts for mobile, tablet and desktop, we could do something like this:

```css
.container {
  /* settings for small/mobile screens */
}

@media (min-width: 600px) and (max-width: 899px) {
  .container {
    /* rules for medium-sized screen */
  }
}

/* Large Screens */
@media (min-width: 900px) {
  .container {
    /* rules for large screen */
  }
}
```

## Flexbox

- Flexbox helps us distribute and align elements within a container
- A flex container can expand to contain and fit the elements inside it
- The `container` contains the elements and the elements contained inside it are called `items`
- To use flexbox, we need to set the `display` property of an element to `flex` and we can start displaying items within it

### How to Flex

- Flexbox has relies on two main axes - the main axis and the cross axis. :

  - Direction: It is the main axes with 4 possible settings:
    - `Row`
    - `Row-Reverse`
      - The two row settings will set the main axis horizontally or inline
    - `Column`
    - `Column-Reverse`
      - The two column settings will set the main axis vertically or block aligned
  - Axes
    - Whichever axis is not the main direction will be the alternate axis.
    - Eg: If the main direction is set to `row` then the alternate axis is set to `column`

### Steps to Set Flexbox

1. Set the display property of the parent container to flex:

```css
.container {
  display: flex;
}
```

2. State whether the content should be laid out in rows or columns using the `flex-direction` property and if they should be in the forward or reverse direction.

```css
.container {
  display: flex;
  flex-direction: row;
}
```

3. Order of the items can be specified to determine the order in which the items will appear.

There are three ways to explicitly set the order in which items will appear in a grid.

1. Moving the HTML code for the elements themselves to reorder
2. Appending `-reverse` to `row` or `column` will reverse the order in the specified row or column
3. Using the `order` property of the individual items inside the grid. The lower the order value, the earlier the item will be rendered.

Consider this snippet of `html` that contains a flex `container` and three `box` items within it.

```html
<div class="container">
  <div class="box" id="one">Box 1</div>
  <div class="box" id="two">Box 2</div>
  <div class="box" id="three">Box 3</div>
</div>
```

With the corresponding CSS:

```css
.container {
  display: flex;
  flex-direction: column;
}

.box {
  width: 100px;
  height: 100px;
  background-color: gray;
}
```

We can set the order in which the items will be displayed by altering the `order` value in the css. If all the elements that have the same `order` value, then the elements will appear in the order in which they are placed in the HTML file.

In this case the order of the elements will be one, two and three.

```css
#one {
  order: 1;
}
#two {
  order: 1;
}
#three {
  order: 1;
}
```

Consider this case with the changed values of `order`:

```css
#one {
  order: 30;
}
#two {
  order: 20;
}
#three {
  order: 10;
}
```

In this case, the element `#three` has the lowest `order` value, therefore will be rendered first. This will be followed by element `#two` which has the next lowest value and lastly element `#one` which has the highest value.

### Align and Justify Content

Two CSS properties are used to align the elements with flexbox:

- `justify-content` - is used to align content along the `main axis`. The properties it accepts are:
  - `flex-start`
  - `flex-end`
  - `center`
  - `space-around`
  - `space-between`
  - `space-evenly`
- `align-items` - is used to align content along the `cross axis`. The properties it accepts are:
  - `stretch`
  - `flex-start`
  - `flex-end`
  - `center`

## CSS Grid

Flexbox is for how content flows, Grid is for how content is placed - i.e. grid works nicely for page layouts, flex works nicely for regions within the grid.

Grid and Flexbox must be used together to compensate for the shortcomings of each other. At the highest level CSS Grid excels at creating layouts for a webpage, while Flexbox is a master of content flow for each element that makes up the page layout.

Comparing Grid and Flexbox, we can see that:

- Grid is two dimensional, while Flex is one
- Grid is layout first, while Flexbox is content first
- Flex is for components of an app, Grid is for the app layout itself

To test run how Grid works, check out this [awesome CSS Grid Generator](https://cssgrid-generator.netlify.com/) developed by [Sarah Drasner](https://github.com/sdras/).

### Grid Rows and Columns

We can set the rows and columns of a grid by using a few CSS Grid settings:

```css
.container {
  display: grid;
  grid-template-columns: 35vw 35vw;
  grid-template-rows: 45vh 45vh;
  grid-gap: 15px;
}
```

Note: `grid-gap` has been depreciated. Please use `grid-gap-row` and `grid-gap-column` instead.

Let us look at the `column` and `row` settings in a little more detail:

- `grid-template-columns: 35vw 35vw;` - sets the number of columns and the width of the columns. The numbers implicitly indicate the number of columns the grid will have. This grid will have two columns.
  - Alternatively you can use `repeat()` syntax if you are creating columns with equal widths. The syntax would be `grid-template-columns: repeat(3, 100px;`.
- `grid-template-rows: 45vh 45vh;` - sets the number of rows and their widths. This grid will have two rows.
  - Alternatively you can use `repeat()` syntax if you are creating rows with equal widths. The syntax would be `grid-template-rows: repeat(3, 100px;`.
  - Defining the rows in the above ways limits the number of rows that a grid can have. We can automate the row generation with `grid-auto-rows: minmax(100px, auto)`.
- `grid-gap: 15px;` - sets the gap between the columns and rows.

### Grid Areas

`grid-area` is used to set the columns and rows that a particular grid item will occupy.

```css
.item {
  grid-area: 1/2/3/3;
}
```

`grid-area` is short hand for the following four properties: `grid-row-start`, `grid-column-start`, `grid-row-end` and `grid-column-end`.

In the example above, `grid-area: 1/2/3/3` will place the item from rows 1-3, and columns 2-3.

Areas can also be defined with names. For example:

```css
container {
}
```
