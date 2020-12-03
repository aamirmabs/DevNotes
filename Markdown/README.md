# Markdown DevRef

This is a guide that list the most commonly used (almost all) features of markdown used to build the DevNotes Repo.

I am primarily using GFM (GitHub Flavored Markdown), which is Github's custom version of Markdown that is built on top of the Sundown parser.

I love working on [VSCode](https://code.visualstudio.com/) and it is my editor of choice. I highly recommend using the '[Markdown All In One Plugin (Markdown AIO)](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)' which has made writing markdown much more simpler for me. It has many powerful features such as keyboard shortcuts, supports GFM, HTML previews and much more.

Note: **All keyboard shortcuts** mentioned on this repo page are for the Markdown AIO plugin. Also, I will not be elaborating a lot about features particular to the plugin until they are relevant to writing/editing markdown.

## Table of Contents

- [Markdown DevRef](#markdown-devref)
  - [Table of Contents](#table-of-contents)
  - [The Purpose of Markdown](#the-purpose-of-markdown)
  - [Headings](#headings)
  - [Horizontal Rules](#horizontal-rules)
  - [Styling text](#styling-text)
      - [Bold](#bold)
      - [Italics](#italics)
      - [Strikethrough](#strikethrough)
      - [Italics nested within bold text](#italics-nested-within-bold-text)
      - [Bold + Italic text](#bold--italic-text)
  - [Quoting](#quoting)
  - [Links](#links)
  - [Images](#images)
  - [Lists](#lists)
      - [Unordered Lists](#unordered-lists)
      - [Ordered Lists](#ordered-lists)
      - [Nested Lists](#nested-lists)
  - [Escaping\Ignoring Markdown](#escapingignoring-markdown)
  - [Code Highlighting And Blocks](#code-highlighting-and-blocks)
    - [Inline](#inline)
    - [Fenced Blocks](#fenced-blocks)
    - [Code Highlighting](#code-highlighting)
  - [Task Lists](#task-lists)
  - [Tables](#tables)

---

## The Purpose of Markdown

It is an idea that lets you use simple plain text editors and create well-formatted and intelligently organized documents. Markdown is a format or style of being able to add text formatters like stylizing with bold or italics, adding list, adding links, managing tasks, etc.

Oh, and you can view these documents in HTML with all the rendered bells and whistles.

If you've used Facebook messenger or posted on Reddit, then you've used some flavour of Markdown.

Here are a few advantages of learning markdown:

1. It's clean and easy to write.
2. It will always be cross-platform as the files are plain text.
3. It will fit any setup or workflow.

---

## Headings

Heading lines start with #, ##, ... ###### to represent H1 - H6 respectively.

Note: I have not rendered H1 - H3 at this location as rendering them at this position in the document as they would break a few markdownlint rules and also break the table of contents. I use [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) plugin by [David Anson](https://github.com/DavidAnson) for linting markdown. The code snippet below shows the markdown to render H1-H3.

#### This is a h4 <!-- omit in toc -->

##### This is a h5 <!-- omit in toc -->

###### This is a h6 <!-- omit in toc -->

```markdown
# This is a h1

## This is a h2

### This is a h3

#### This is a h4

##### This is a h5

###### This is a h6
```

---

## Horizontal Rules

Use three or more `***`, `---` or `___` to render a horizontal rule. The rendered output looks the same for all three inputs.

---

```markdown
---
```

Note: I personally use five `-----`'s to place horizontal rules as it is easy to visually understand them.

---

## Styling text

#### Bold

We can make text **bold** by enclosing them in `**`'s.

```markdown
We can make text **bold** by enclosing them in \*\*'s.
```

We can also use **`Ctrl + B`** to make a selection bold if you are using '[Markdown All In One Plugin](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)' on VSCode (which I highly recommend).

#### Italics

We can make text _italics_ by enclosing them in `*`'s.

```markdown
We can make text _italics_ by enclosing them in \*'s.
```

We can also use **`Ctrl + I`** to make a selection bold if you are using '[Markdown All In One Plugin](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)' on VSCode (which I highly recommend).

#### Strikethrough

~~Strikethrough~~ text is created by enclosing text in \~\~'s.

```markdown
~~Strikethrough~~ text is created by enclosing text in ~~'s.
```

#### Italics nested within bold text

We can emphasize text with italics **in a _bold_ statement**

```markdown
We can emphasize text with italics **in a _bold_ statement**
```

#### Bold + Italic text

Statements enclosed in \*\*\* will be both bold and italicizes.

We can make text **_both bold and italic_** with three `***`'s.

```markdown
We can make text **_both bold and italic_** with three `***`'s.
```

---

## Quoting

A statement or a part of a statement that you do not want to apply markdown to can be `quoted` by enclosing them within \`'s.

If you want to apply the quotation functionality to a block, you should enclose the block in \`\`\`'s.

```markdown
These block of lines
is quoted...
```

The code for the above snippet is:
\`\`\`
These block of lines
is quoted...
\`\`\`

---

## Links

To create a [link](#), we use the following syntax.

```markdown
[Link text](https://url.address/)
```

Note: Github automatically creates links for **valid** url's. You can create links to Github users/issues/pull-requests etc. by using this feature. Learn more about this feature [here](https://help.github.com/en/github/writing-on-github/autolinked-references-and-urls).

Markdown allows linking withing the folder structure using relative links.

_Github Flavoured Markdown(GFM) automatically **transforms** the relative address to the absolute address_ when it is rendered and you can be assured that the relative links will always work.

1. Relative Links:

Relative links and image paths can be reached by specifying the destination relative to the current location.

For the uninitiated, here is a quick refresher to relative links:

- File in same folder - `/file.ext`
- File in sub folder - `/sub/location/file.ext`
- Root location - `../`

For example, if I wanted to [link to the main page](../README.md) of this repo, I would use the following code: `[link to the main page](../README.md)`.

If I wanted to link to a sister section on the same level, say for example the [python section](/Python/README.md), I would use the following code: `[python section](/Python/README.md)`.

The same address can be accessed by using an absolute address. We would access the [python section](../Python/README.md) by using this markdown: `../Python/README.md`.

2. Section Links:

You can link to a section on the page by copying the link from the _rendered file_. You will have to hover over the section to view the required link.

3. Internal Links on Page:

---

#### Top Link <!-- omit in toc -->

[Click here](#bottom-link) - to scroll to 'Bottom Link'.\*\*\*

---

Have a look at this snippet which links between 'Top Link' and 'Bottom Link':

```markdown
#### Top Link

[Click here](#bottom-link) - - to scroll to 'Bottom Link'.

.

..

Some content here

..

.

#### Bottom Link

[Click here](#top-link) - to scroll to 'Bottom Link'.
```

Internal links can be created to link to headings which use preceding `#`'s. To link to a heading(`# Heading Name`) on the page use the following syntax: `Click [here](#heading-name)`.

Here are the rules that are applied to internal links in a markdown document:

- punctuation marks will be dropped
- leading white spaces will be dropped
- upper case will be converted to lower
- spaces between letters will be converted to -

---

#### Bottom Link <!-- omit in toc -->

[Click here](#top-link) - to scroll to 'Top Link'.\*\*\*

---

## Images

Markdown on Github can be used to place an image along with the alt-text describing it as shown below.

![Programmers can relate...](https://i.imgur.com/I6RpztMl.jpg)

```markdown
![Programmers can relate...](https://i.imgur.com/I6RpztMl.jpg)
Format: ![Alt Text](url)
```

#### Links placed on images <!-- omit in toc -->

There is no functionality built in to markdown that allows us to link images to urls, but there are a few workarounds listed below.

1. Image with link to a url.

[![Visit YouTube.com](https://i.imgur.com/SrQXBqG.gif)](https://www.youtube.com/ "Image Title on Hover Here")

```markdown
[![IMAGE ALT TEXT HERE](https://image-url.here)](https://www.url.here "Title on Hover Here")
```

The markdown basically comprises of two parts:

- an image (the-link-text) `![IMAGE ALT TEXT HERE](https://image-url.here)`
- wrapped in a link `[the-link-text](https://www.url.here "Title on Hover Here")`

2. Image with link to a video.

Please note that this is **_not_** _a different method_ than the one listed above. what I personally do link my videos on my Github repos.

The syntax is the same as the above but we will perform a the extra step of making a custom thumbnail for the video, uploading it to an online service (like Imgur) and using that image in the markdown.

[![YouTube video on making custom thumbnail](https://i.imgur.com/SrQXBqG.gif)](https://www.youtube.com/watch?v=8YbZuaBP9B8 "WATCH Video - How to Make a YouTube Custom Thumbnail Tutorial")

```markdown
[![YouTube video on making custom thumbnail](https://i.imgur.com/SrQXBqG.gif)](https://www.youtube.com/watch?v=8YbZuaBP9B8 "WATCH Video - How to Make a YouTube Custom Thumbnail Tutorial")
```

---

## Lists

#### Unordered Lists

Preceding a line with `-` or `*` will begin an unordered list.

- This
- is a
- list

```markdown
- This
- is a
- list
```

Using a `*` will have the same effect.

- Here is
- another
- list

```markdown
- Here is
- another
- list
```

#### Ordered Lists

Preceding a line with a number will start a numbered list starting at the number specified.

1. This is
2. an ordered
3. list

```markdown
1. This is
2. an ordered
3. list
```

7. This list
8. starts with
9. number 7

```markdown
7. This list
8. starts with
9. number 7
```

#### Nested Lists

If any line in a list is indented, it is rendered as a sub list.

1. Main list item 1
2. Main list item 2
   1. Sub list item 1
3. Main list item 3
   - Sub list item 2
4. Main list item 4

```markdown
1. Main list item 1
2. Main list item 2
   1. Sub list item 1
3. Main list item 3
   - Sub list item 2
4. Main list item 4
```

---

## Escaping\Ignoring Markdown

Using a `\` before a character which has a special meaning in markdown is used to ignore\escape it from being formatted in markdown.

For example, if I wanted to render a \*, \` or a \\ as normal text, we will need to escape it.

```markdown
For example, if I wanted to render a \*, \` or a \\ as normal text, we will need to escape it.
```

If the word or phrase that you want to display uses one or more backticks, you can escape it by enclosing it in double backticks` (``) `.

`` Add `this code` to your file. ``

```markdown
`` Add `this code` to your file. ``
```

---

## Code Highlighting And Blocks

### Inline

You can highlight some code inline by enclosing it in backticks(`).

Type `this code` in your editor.

```markdown
Type `this code` in your editor.
```

### Fenced Blocks

A multi-line snippet of code can be shown by enclosing it between three backticks.

```
sample
.
code
.
here
```

### Code Highlighting

GFM supports syntax highlighting. You will place the name of the language whose syntax highlighting you want after the opening triple backticks.

The snippet below is in Python:

```python
ten = 10
print(ten)
```

I personally use this feature to highlight code for just the handful of web development languages I use(HTML/CSS, Javascript, Python and maybe Java).

Github itself refers you to checkout the [highlight.js demo page](https://highlightjs.org/static/demo/) to have a look at all the languages that are supported byt his feature.

But, behind the scenes, Github actually uses [linguist](https://github.com/github/linguist) to detect the languages. Here is the list of [all the languages supported](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml).

---

## Task Lists

Task lists are easy to create with markdown.

- Create a list of items using `- Task details`
- Preface the item with a space and `[ ]`
- If an item is complete mark the item with `[x]`

Here is an example list:

- [x] Create Github repo to maintain notes
- [x] Add your notes to repo
- [x] Add lots more useful stuff
- [ ] Get Github stars ;-)

```markdown
- [x] Create Github repo to maintain notes
- [x] Add your notes to repo
- [x] Add lots more useful stuff
- [ ] Get Github stars ;-)
```

---

## Tables

Markdown spec **does not support tables** but it is supported in GFM. Here are the rules we need to follow to set tables:

1. The first row is used to set the headers. Columns are divided with `|`.
2. The second row must have `---`'s which denote that this is a table. Each column should have a minimum of three `-`'s.
3. Colon's are used to specify the alignment on the second row:
   - All columns are left aligned by default.
   - Right alignment is specified by having colons on both sides(`:---:`) of the hyphens.
   - Left alignment is specified by placing a colon on the left side(`---:`) of the hyphens.
4. The outer `|` is not mandatory.
5. The markdown does not need to be aligned perfectly for the table to be rendered.

Here is a sample table illustrated below:

| Col 1 Header | Col 2 Header | Col 3 Header |
| ------------ | :----------: | -----------: |
| Col 1 is     |     left     |      aligned |
| col 2 is     |    center    |      aligned |
| Col 3 is     |    right     |      aligned |

```markdown
| Col 1 Header | Col 2 Header | Col 3 Header |
| ------------ | :----------: | -----------: |
| Col 1 is     |     left     |      aligned |
| col 2 is     |    center    |      aligned |
| Col 3 is     |    right     |      aligned |
```

---
