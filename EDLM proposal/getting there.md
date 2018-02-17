## Getting there

This section conceptually describes how to achieve the goals outlined above.

### Decoupling the content from the format

Writing a document with Microsoft Office Word implies formatting it as well.

Despite the use of a template, guaranteeing a consistent format across a library 
of dozens of documents, written by many authors, sometimes even multiple authors 
for the same document, is almost impossible.

Due to the inherent complexity of Microsoft Word Office, as well as the debatable 
pertinence of some choices it sometimes seems to automatically make for us, some 
subtle format changes are bound to sneak unnoticed within the documents over time.

My first goal is to get rid of this ambiguity, and have one and only one way to 
express a given construct (a paragraph, a heading, a list, a table, ...).

This would also have the beneficial side effect of freeing editors from worrying 
about formatting their content while they are writing it, giving them more brain 
power for the actual content creation.

Decoupling the content and the format also means that any older document, even one that 
hasn't been touched in years, will be automatically updated to the latest 
format/layout whenever the format/layout is updated, since their content has not 
changed (more on this later).

To reach this goal, the **content** needs to be:

- written in pure text, editable with any "dumb" editor
(Notepad, Notepad++, ...);
- totally independent of the formatting of the final document.

#### Specification

Once the content has been created by the editors, my goal is to provide a system 
that will take that "raw" content, and format it, consistently, into different 
formats that will later be published.

A choice format is of course PDF, but we can also convert to Microsoft Word format, 
HTML (create a website automatically for our documentation), EPUB (books that can 
be read easily on readers/mobile), you-name-it.

For the sake of this proposal, I will assume PDF as the default output format.

*Info only*: Here is a non-exhaustive list of the **output** format supported by my proposed 
implementation as of today (even more **input** formats are available):

> Markdown, CommonMark, PHP Markdown Extra, GitHub-Flavored Markdown, MultiMarkdown, 
reStructuredText, XHTML, HTML5, LaTeX (including beamer slide shows), ConTeXt, RTF, 
OPML, DocBook, OpenDocument, ODT, Word docx, GNU Texinfo, MediaWiki markup, DokuWiki 
markup, ZimWiki markup, Haddock markup, EPUB (v2 or v3), FictionBook2, Textile, 
groff man pages, Emacs Org mode, AsciiDoc, InDesign ICML, TEI Simple, and Slidy, 
Slideous, DZSlides, reveal.js or S5 HTML slide shows. It can also produce PDF 
output on systems where LaTeX, ConTeXt, or wkhtmltopdf is installed.

The output should be:

* Consistent: the same content must **always** yield the same result, 
even on different computers, operating systems, or software versions (no more
"locale" issue, translation issue, pages that resize themselves, ...);
* Uniformly formatted: **all** the documents in the library should have the same 
general layout, giving all documentation published by the //wing a visual identity 
of their own;
* Retroactively managed: all documents that have been published in the past should 
be **updated without human intervention**. If a logo changes, if we decide to 
change the title page, or the space after paragraphs, those changes should be 
**automatically propagated across the entire library**;
* Adapted to our needs: the documentation should not look "generic" or bland; 
each document should bear a distinct *132nd touch*, and that *touch* should be 
found on **every** document produced by the //wing;
* Stable: a reference to a document in another document should always
point to that target document, even if it is updated;
* Inter-connected: a document should be able to include another (for example,
a SOP might include a "Quick Reference card" that is also published on the
side). When the included document is updated, the document that includes it
should be automatically updated as well.