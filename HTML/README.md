# HTML DevRef

HTML, in simple terms, forms the _building blocks to everything you see_ on the Web.

This repo is _**not** going to teach you HTML_ from the ground up. It's just a collections of notes/snippets which I would have saved in different places for further reference.

For example, there could be a snippet about, let's say, `viewport` settings for tablet sized devices, with some notes about why I've done `abc` in `line x`; but I will not elaborate or explain the snippet in detail.

With that out of the way, here goes nothing...

---

## Table of Contents

- [HTML DevRef](#html-devref)
  - [Table of Contents](#table-of-contents)
  - [Intro To HTML](#intro-to-html)
    - [Analogies To Understand HTML, CSS And Javascript](#analogies-to-understand-html-css-and-javascript)
      - [Analogy Of The Human Body](#analogy-of-the-human-body)
      - [Analogy Of Building A House](#analogy-of-building-a-house)
  - [Higher Level HTML Tags](#higher-level-html-tags)
    - [DOCTYPE](#doctype)
    - [HTML Tag](#html-tag)
    - [Head Tag](#head-tag)
    - [Body Tag](#body-tag)
    - [Comment Tag](#comment-tag)
    - [Putting Them Together](#putting-them-together)
  - [Block Level Elements](#block-level-elements)
    - [Lists](#lists)
      - [Unordered Lists](#unordered-lists)
      - [Ordered Lists](#ordered-lists)
      - [Description Lists](#description-lists)

---

## Intro To HTML

HTML stands for `Hyper Text Markup Language`; the same `Hypertext` in `http:\\` that we use for all webpage addresses.

HTML works hand in hand with CSS and Javascript to make webpages look good and respond to our actions respectively. We can use a couple of analogies to understand how they interact with each other.

A complete list of HTML tags is can be referenced here on the MDN [HTML Elements Reference Page](https://developer.mozilla.org/en-US/docs/Web/HTML/Element).

### Analogies To Understand HTML, CSS And Javascript

#### Analogy Of The Human Body

- We can think of HTML as the skeleton :
  - It defines how our head/hands/legs are attached to the torso
  - It defines how tall/short we will be
  - In webpages, HTML will define the order in which content is rendered and what type of content will be rendered(like paragraphs, titles, tables, etc.)
- We can think of CSS as the skin and outlook :
  - Our skin and its distribution defines what shade we look and how we look. It defines if we will look skinny or fat.
  - Our clothes and other accessories we choose to wear define how we look over our layers of skin.
  - In webpages, CSS will define overall settings like the background color of the page, how wide the content will be, etc. And CSS settings can be defined to set text font, colors and styles.
- We can think of Javascript as the brain :
  - Out brain controls everything we do. How we walk, move, breathe, etc.
  - In webpages, Javascript is used to define how the webpage will respond to interactions. Javascript can be written to define what happens on mouse-clicks, what errors to show if we enter invalid information in our forms, etc.

#### Analogy Of Building A House

- HTML is the foundation and structure of the house :
  - When you build a house, you first lay down a foundation, build walls, lay a roof, put doors in place, etc.
  - In webpages, HTML defines the main layout of the page. It decides what piece of content go where(a header menu, then a title, then a paragraph... ) and what types of content a page will contain(paragraphs, images, videos...).
- CSS is the visual style of the house :
  - After the foundation is laid, you take some time to set the theme of the house. You choose the paint for the outside, texture of walls on the inside, what color the floor tiles will be, etc.
  - In webpages, CSS is used to set the colors, styling, padding and all other properties pertaining to the visual style of the web page.
- Javascript is the internal wiring and the mechanics of the house :
  - You expect the doorbell to ring when you press the switch. You expect the lights to turn on when you turn them on. You expect water to flow when you open the tap. All these are things are possible because of the way the wires are connected and plumbing is done(which are not visible on the outside).
  - On a webpage, Javascript is used to add interactivity and logic to the website. When you click on some button and a message is shown or if your form is not accepted if you entered an invalid email - it is done with Javascript.

---

## Higher Level HTML Tags

### DOCTYPE

Almost every web document will have the `<DOCTYPE>` tag which tells the browser what type of document it is.

Web pages are mostly of the type `<!DOCTYPE html>`.

### HTML Tag

The `<html>` opening tag will mostly come right after the `<!DOCTYPE html>` tag and denotes the beginning of the html content on the document. The end of the content is denoted by `</html>` closing tag where the `/` before the `html` denotes that it is a closing tag.

Almost all tags in HTML will have opening and closing tags. There are a few exceptions though. The `<!DOCTYPE>` tag does not have a closing tag. Similarly, there are a few tags that are considered self-closing like a `<br />` tag that is used to denote line breaks.

### Head Tag

Content about the Head Tag

### Body Tag

Most of the content that we see on the webpage will go within the opening `<body>` and closing `</body>` tag.

### Comment Tag

You can add notes/write messages on a HTML document for further referrence or clarification for your future self or any future developer/s that might be blessed with the opportunity to lay their eyes on your beautiful code.

The syntax of a comment code is `<!-- Your Comment Here -->`.

### Putting Them Together

Here is how the general structure of a HTML Document will look.

```html
<html>
  <head>
    <!-- Head content would go here -->
  </head>
  <body>
    <!-- Page content would go here -->
  </body>
</html>
```

---

## Block Level Elements

### Lists

HTML Lists are of three types:

1. Unordered Lists
2. Ordered Lists
3. Description Lists

#### Unordered Lists

The syntax for unordered lists is :

```html
<ul>
  <li>This is</li>
  <li>an unordered</li>
  <li>list.</li>
</ul>
```

`ul` - Unordered list tag
`li` - List item tag

**OUTPUT**:

<ul>
  <li>This is</li>
  <li>an unordered</li>
  <li>list.</li>
</ul>

#### Ordered Lists

The syntax for ordered lists is very similar to that or unordered list :

```html
<ol>
  <li>This is</li>
  <li>an ordered</li>
  <li>list.</li>
</ol>
```

`ol` - Ordered list tag
`li` - List item tag

**OUTPUT**:

<ol>
  <li>This is</li>
  <li>an ordered</li>
  <li>list.</li>
</ol>

#### Description Lists

Description lists are lists with key value pairs. The syntax for description lists is :

```html
<p>Making Power-Puff Girls</p>

<dl>
  <dt>Sugar</dt>
  <dd>A large jar of white and brown sugar.</dd>

  <dt>Spice</dt>
  <dd>ALL of them.</dd>

  <dt>Everything Nice</dt>
  <dd>Chocolates, candies and more.</dd>
</dl>
```

`dl` - Description list
`dt` - Description title
`dd` - Description details

**OUTPUT**:

<p>Making Power-Puff Girls</p>

<dl>
  <dt>Sugar</dt>
  <dd>A large jar of white and brown sugar.</dd>

  <dt>Spice</dt>
  <dd>ALL of them.</dd>

  <dt>Everything Nice</dt>
  <dd>Chocolates, candies and more. </dd>
</dl>
