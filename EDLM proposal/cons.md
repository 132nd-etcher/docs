### The cons

Allow me to start with the cons, and provide, for each of them, the way(s) I found 
to mitigate them.

#### No WYSIWYG ("What you see is what you get")

In my current proposition, I plan to use the Markdown syntax to write the 
actual content. Markdown is (very) simple; it's pretty much pure text, and 
very similar to the syntax we're using for the forum.

The downside is that, since Markdown is pure text, an editor who is busy 
writing documentation does not see the result appear as he types. He will
only see his text.

Font does not resize for headings, pictures do not appear, 
tables look "raw", etc.

##### Mitigation

* Converting from Markdown to Word/PDF/HTML is trivial, and the tool that 
I will be providing can be installed on any modern computer. Output can 
therefore be refreshed as often as needed to get a "sneak peek" into the 
actual result;
* Numerous WYSIWYG tools exists *online* to edit Markdown. Some of those tools are 
bare editor, providing a side by side "Edit" window and a "Result" window. 
Their offline equivalent are available as well. Moreover, and this gets 
really interesting, Markdown is mature enough that many *free* online editors 
offer amazing synchronization capabilities with Google Drive, Dropbox, 
Github, ..., **effectively allowing anyone to work on any document from any 
computer connected to the web, and directly share their work for review**.
* Writing in pure text means that everyone can use their editor of choice;
some of use will be comfortable with Notepad++, others might prefer Atom,
SublimeText, Vim (sic), ... .

#### Less liberty when it comes to customizing the format/layout

Having a common template for the layout/format of our document effectively 
"castrates" editors, denying them the liberty to get creative with the way 
their content is rendered.

This could get on the nerves on some, especially the most perfectionists among us.

##### Mitigation

* In my current proposition, the rendering, formatting and layout is done by 
a professional (although free) typesetting application that has been in 
existence since 1985: [Latex](https://en.wikipedia.org/wiki/LaTeX). 32 years 
of development, testing and improvements have made it quite robust. It has 
been in use for decades by the scientific and teaching community all around 
the world for papers, essays, reports, etc. Even if we might disagree with 
some of the minor formatting choices it makes when it comes to typesetting 
the document (I sometimes do myself, with the placement of pictures for example), 
we can at least be sure that the standard it follows is accepted world-wide, 
and is the result of decades of professional work;
* The layout/format will be 100% identical for all documentation published by 
the //wing, branding our documents with a unique "personality", and giving an 
overall "neat" picture of the Wing to the external world;
* In case it becomes necessary, when part of the output does not fit a specific 
need of ours, we can take advantage of the maturity of the tools and customize 
every little detail to our needs, even though that will require some tinkering,
and defeats the purpose of reaching for consistency.
* Some documents might need a different kind of template: for example,
the FLIP for Georgia can very well be generated from Markdown, creating
beautiful FLIPs automatically from the just the text (i.e. the values).

#### Resources like pictures are to be included on the side

All the files that are to appear in the final document will be referenced in 
Markdown as links only, pointing to a file that exists near the Markdown 
source document (I'll come back on the structure later), or to a website,
for example `http://www.website.com/my_cool_picture.png` is perfectly
valid).

To give an example, if I wanted to include a file named `picture.png` in a 
document named `index.md`, I would have to write the following in `index.md`: 

```
[Picture caption](picture.png)
```

"Picture caption" simply describes the picture, and can be any sort of text. 

"picture.png" is the file itself. I will explain later how the picture is "found".

##### Mitigation

* Updating pictures can be done without even opening the document. 
A file named `picture.png` will be included in the final document, 
whatever that file contains. Updating batch of pictures is thus 
very easy, and does not require updating them one by one in every 
Word document (imagine having to edit dozens of Word documents
to update a logo in each of them ...);
* Pictures are automatically indexed and referenced in the final document, 
and an automatic "Table of figures" is automatically generated, with 
links to the pictures within the text (see the one at the end of this very file);
* Pictures (and other media) are shared across documents (if we want to). 
There are two locations for pictures (more on that later): one that is
specifically for the document, and another that will be shared between 
*all* documents (for example, the squadrons logos). If a logo picture 
is updated (for any reason, this is just an example), updating the 
picture file in the shared folder would propagate to *all* the documents 
in the library, updating that picture in each one of them **in a 
completely automated way**.
* Picture are automatically resized depending on
a document size; we might want the same document to be created in A3,
A4 and A6, but what of the picture? The same picture would appear tiny
in A3, and overflow the page in A6. With this implementation, pictures
are automatically resized to take approximately 80% of the width of the
page. There is no need to edit anything.


#### New technologies

While all the cons so far are of relatively small import, I fear this 
one might raise the most shields in our community. Please bear with 
me for a little while?

For this project, I plan on using two pieces of software for the 
front-end (the parts people are expected to interact with): **Markdown** 
and **Git**. For more information about them, see the "Technical" 
section of this document.

##### Mitigation

While switching to new software always implies somewhat of a 
**learning curve**, I used the following criteria to select them:

  * Free (as in *no dinero*);
  * Open source;
  * Mature;
  * Widely used across the world;
  * Well documented;
  * Will be supported for years to come;
  * Easy enough for the intended usage;
  * Has a luxuriant and flourishing ecosystem of tools around them;
  * Resilient.

The initial learning curve should be very much dampened by the *huge* 
amount of documentation around both *Markdown*, and *Git/Github*.

Tutorials and documentation is all over the web, and, more importantly, 
**mistakes are free**. Even if someone completely nukes all our 
documentation (and the chances for that to happen are almost none) 
while toying around trying to learn, it can be restored in seconds.

In its simplest form, creating a document would simply be:

1. (only once) Download the Github Desktop application
2. Clone or pull our documentation repository
3. Make some changes using Notepad++ (or any other editor)
4. Commit those changes to a branch
5. Push that branch
6. Signal a repository admin that changes are available
(or create a Pull Request if the editor feels really brave...)

As some of us can already attest, while frightening in the beginning,
this is far from rocket science.