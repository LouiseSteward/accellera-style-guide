---
title: "2. Document authoring and formatting"
style: chapter
---

# 2. Document authoring and formatting

This chapter explains the document authoring and formatting.  

## 2.1 Use of Markdown and Kramdown

The Accellera documentation flow uses [Markdown](https://en.wikipedia.org/wiki/Markdown) as primary text input format. More specifically, the [Kramdown](https://kramdown.gettalong.org/syntax.html) flavor of Markdown is used, since it offers additional capabilities to ease automation.

This section gives an overview of the commonly used structural elements.

### 2.1.1 Paragraphs

Consecutive lines of text are considered to be one paragraph. Paragraphs are separated by a blank line.

In Markdown, line brakes are replaced by spaces. A paragraph in Markdown ends when using an empty line.

*Example*

```
This is a the first paragraph.

This is the second
paragraph.
```

Renders into:

This is a the first paragraph.

This is the second
paragraph.

Explicit line breaks in a paragraph can be made by using two spaces or two backslashes at the end of a line. 

Note---It is recommended to use the two backslashes for a line break as some editors are not showing spaces. For the technical editor the use of two backslashes are clearly recognizable.

*Example*

```
This is a paragraph\\
which contains a hard line break.
```

Renders into:

This is a paragraph\\
which contains a hard line break.

### 2.1.2 Headers

Headings are created by starting a line with one or more hash (#) characters and then the header text. The number of hash characters specifies the heading level: one hash character means the first level heading, two means second level heading and so on, until a maximum of six hash characters for a sixth level heading.

No spaces are allowed before the hash characters. Optionally, hashes may be used at the end of the line to close the header. Any leading or trailing spaces are stripped from the header text.

Like with paragraphs, separate the heading from everything else with an empty line space.

*Example:*

```
## This is a second-level heading

This is a paragraph.
```

Kramdown supports setting the header ID as shown below:

```
# This is a first-level heading  {#my-first-id}

## This is a second-level heading with trailing hashes ##  {#my-second-id}
```

When setting the option `auto_ids` to `false`, then the automatic header ID generation is turned off, see example below:

*Example*

```
{::options auto_ids="false" /}

#### Level-4 header without an ID
```

{::options auto_ids="false" /}

#### Level-4 header without an ID

### 2.1.3 Italics 

Use a star character (\*\) before and after the italicised words.

*Example:*

```
This function is *implementation-defined*.
```

Renders into:

This function is *implementation-defined*.

### 2.1.4 Bold

Use two star characters before and after the bold text.

*Example:*

```
The member function **stop** shall halt the simulator.
```

Renders into:

The member function **stop** shall halt the simulator.

### 2.1.5 Lists

#### 2.1.5.1 Unordered lists

Unordered lists are started by using a star character (\*\) followed by a space and then the list item text.

*Example:*

```
* Unordered list item 1.
This sentence is part of the same line.

* Unordered list item 2.

```

Renders into:

* Unordered list item 1.
This sentence is part of the same line.

* Unordered list item 2.

#### 2.1.5.2 Ordered lists

Ordered lists are started by using a number followed by a period, a space and then the list item text.

*Example:*

```
1. Ordered list item 1.
This sentence is part of the same line.

   1. nested ordered list item.

   2. nested ordered list item.

2. Unordered list item 2.

2. Unordered list item 3.
```

Renders into:

1. Ordered list item 1.
This sentence is part of the same line.

   1. nested ordered list item.

   2. nested ordered list item.

2. Unordered list item 2.

2. Unordered list item 3.

### 2.1.6 Tables

Tables can be created by using pipe characters (\|), dash characters (-) and the equal sign character (=).

A table row starts with a pipe character (\|) followed by a space and the text of the column. Multiple columns are added by repeating this pattern. There is no need to vertically align the text and columns, however, for readability this is recommended.

If a pipe characters is immediately followed by a dash (-), a horizontal separator line is created to mark the end of the table header. If the pipe character is followed by an equal sign (=), the tables rows below it are part of the table footer.

*Example:*

```
| colum 1       | column 2 |
|---------------|----------|
| A simple      | table    |
| with multiple | lines    |
```

Renders into:

| colum 1       | column 2 |
|---------------|----------|
| A simple      | table    |
| with multiple | lines    |

### 2.1.7 Code blocks

Three consecutive tilde characters are used to mark the start and end of a code block, as shown below:

<pre><code>
~~~
struct S {
    int a;
}
~~~
</code></pre>

Renders into:

~~~
struct S {
    int a;
}
~~~

Alternatively, lines indented with either four spaces or one tab are also interpreted as an inline code block.

*Example:*

```
This is the paragraph explaining the sample code block.

    void function(int a);
```

Renders into:

This is the paragraph explaining the sample code block.

    void function(int a);

### 2.1.8 Footnotes

A footnote marker consists of square brackets with a caret and the footnote name inside. The footnote definition can be placed elsewhere in the document.

*Example:*

```
This is a text with a footnote[^fn].

[^fn]: And here is the footnote definition.
```

Renders into:

This is a text with a footnote[^fn].

[^fn]: And here is the footnote definition.

The footnote name is only used for the anchors and the numbering is done automatically in document order. Repeated footnote markers will link to the same footnote definition.

### 2.1.9 Links

A simple link can be created by surrounding the text with square brackets and the link URL with parentheses:

```
A [link](https://accellera.org) to the Accellera homepage.
```

Renders into:

A [link](https://accellera.org) to the Accellera homepage.

Alternatively, the link and URL can be decoupled by using a reference name, such that the links can be listed in a separate section. For this, the reference name is used in square brackets instead of the link URL.

```
A [link][accellera] to the Accellera homepage.

[accellera]: https://accellera.org
```

### 2.1.10 Images

A link to an image uses an exclamation mark before the square brackets. The link text will become the alternative text of the image and the link URL specifies the image source:

```
An image: ![gras](img/image.jpg)
```

### 2.1.11 HTML attributes

HTML attributes can be used to specify specific styles.

*Example:*

```
This is <span style="color: red">written in red</span>.
```
Renders into:

This is <span style="color: red">written in red</span>.