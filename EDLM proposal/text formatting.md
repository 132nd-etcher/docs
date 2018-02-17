A few examples:

### Emphasis

*slight emphasis*

```
*slight emphasis*
```

**stronger emphasis**

```
**stronger emphasis**
```

### Lists

A bullet list:

* some
  * nested
    * list
	
	We can also write paragraphs inside lists, of course.
	
  * that
* can
  * keep
    * going
  * on
  * and
	* on
	
```
* some
  * nested
    * list
	
	We can also write paragraphs inside lists, of course.
	
  * that
* can
  * keep
    * going
  * on
  * and
	* on
```

A numbered list:

1. Item1
	1. Item 1.1
	1. Item 1.2
		1. Item 1.2.1
		1. Item 1.2.2
	1. Item 1.3
1. Item 2
	1. Item 2.1
	1. Item 2.2
1. Item 3

```
1. Item1
	1. Item 1.1
	1. Item 1.2
		1. Item 1.2.1
		1. Item 1.2.2
	1. Item 1.3
1. Item 2
	1. Item 2.1
	1. Item 2.2
1. Item 3
```

### Highlighting text:
  
A `block text` inside a sentence.

```
A `block text` inside a sentence.
```

> framed text

```
> framed text
```

```
long
block
  of
text

    spanning

multiple

lines
```

~~~
```
long
block
  of
text

    spanning

multiple

lines
```
~~~

We can
also see
that
paragraphs
are
broken and assembled intelligently.

The
newline is only after
a blank spaces
in the document.

```
We can
also see
that
paragraphs
are
broken and assembled intelligently.

The
newline is only after
a blank spaces
in the document.
```

### Links

[This is a link to Google.com](http://www.google.com)

`[This is a link to Google.com](http://www.google.com)`

### Pictures

We can use the internal "media folders" system[^1]:

![Example picture 1](image2.jpg)

```
! [Example picture 1](image2.jpg)
```

Or link to a URL:

![Example picture 2](http://www.publicdomainpictures.net/pictures/200000/velka/unicorn-icon.jpg)

```
! [Example picture 2](http://www.publicdomainpictures.net/pictures/200000/velka/unicorn-icon.jpg)
```

Either way, the picture will be automatically given a number and will appear in the "List of figures" at the end of the document.

As you can see, those pictures are quite big (1920x1920). Normally, they would overflow the page and make a mess.

However, the system is smart enough to:

1. Know that we are making an A4 page (that is totally up to the author);
2. Resize the pictures accordingly.

Since these example pictures are very big, they will appear on their own page later in the document (probably a page or two away).

I have also included an example of a smaller picture at Figure \ref{smaller}.

![Example picture 3 (smaller)\label{smaller}](image3.jpg)

[^1]: I had to include a space between the "!" and the "[" in the picture examples, otherwise the picture would appear instead of the example text.


### Internal links

Or, how to reference other parts of the same document.

Imagine I have the following section:

```
#### Fluffy section
```

If I want a link to that section somewhere else in the document, I can do the following:

```
For more information, see the [Fluffy section](#fluffy-section)
```

And here's the result: For more information, see the [Fluffy section](#fluffy-section)

#### Fluffy section

**Note**: this one has a bit of a trick to it: the heading must be converted to lower-case, and
all spaces must be replaced by dashes (`-`). So for example, `My Heading` becomes `#my-heading`.


What if you want to create your own labels? That's of course possible!

You can make a reference like this:

```
\label{my-awesome-label}
```

This is my label \label{my-awesome-label} (you can't actually see it, but it's there!)

You can then create a link to it later using:

```
See my "Awesome label", \ref{my-awesome-label}
```

This is my reference: See my "Awesome label", \ref{my-awesome-label}.

It even adds the numbering for us !

### Footnotes

Footnotes are also very simple:

```
This is very true[^2]

...

[^2]: except when it is not
```

And the result:

This is very true[^2]

[^2]: except when it is not

I'm using two because I already had a footnote before, but anything goes:

```
This is very true[^my-footnote]

...

[^my-footnote]: except when it is not
```

### Tables

To create a table:

```
Table: example table 1

-----------------------
left   centered   right
----- ---------- ------
row1  row1       row1

row2  row2       row2

row3  row3       row3
----------------------
```

Gives the following:


Table: example table 1

-----------------------
left   centered   right
----- ---------- ------
row1  row1       row1

row2  row2       row2

row3  row3       row3
----------------------

Alignment is based on the header only. If I wanted all centered-align in the above table, I would do:


```
Table: example table 2

------------------------
 left   centered   right
------ ---------- -------
row1   row1       row1

row2   row2       row2

row3   row3       row3
-----------------------
```

Which would give the following:


Table: example table 2

------------------------
 left   centered   right
------ ---------- -------
row1   row1       row1

row2   row2       row2

row3   row3       row3
-----------------------

Note that if you do not want to type the tables yourself,
you can use the
[online markdown tables generator](https://www.tablesgenerator.com/markdown_tables)

A few more examples:

//include "table examples.md"

### Flow commands

This is all fine and dandy, now we can create all sorts of stuff in our documents.

But what if I don't want a page break here? Or if I want one here? And what if I
want a line break but not a paragraph break?

Well, in Word (& Co.), your best bet is to hope to find the correct command, and
hope that it will actually do what you say.

In our case, since we're using Markdown and Latex, we can use those lovely
commands:

* \textbackslash \textbackslash start a new paragraph.
* \textbackslash \textbackslash* start a new line but not a new paragraph.
* \textbackslash - OK to hyphenate a word here.
* \textbackslash cleardoublepage flush all material and start a new page, start new odd numbered page.
* \textbackslash clearpage plush all material and start a new page.
* \textbackslash hyphenation enter a sequence pf exceptional hyphenations.
* \textbackslash linebreak allow to break the line here.
* \textbackslash newline request a new line.
* \textbackslash newpage request a new page.
* \textbackslash nolinebreak no line break should happen here.
* \textbackslash nopagebreak no page break should happen here.
* \textbackslash pagebreak encourage page break.

They are explained in more details [here](http://www.personal.ceu.hu/tex/breaking.htm).

The one that I find myself using the most when writing in Latex is \textbackslash clearpage, because
when I'm done with a section I like to have the pictures that are relevant to that section to appear
before the next section starts.







