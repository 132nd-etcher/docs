![Documentation](https://i.imgur.com/DNB0lco.png)

# Enhancement Proposal

```
Author: 132nd-etcher
Published: 2017-08-11
Version: DRAFT-1
Audience: 132^nd^ Virtual Wing CMD
```

## Abstract

This document contains an enchancement proposal submitted to CMD for review.

The proposal is about documentation in the 132^nd^ Virtual Wing. I would like to explore possible ways to make it better, easier to produce and easier to maintain.

## Rationale

I was working a while back on the 696^th^ TRP (which produced no useful end-result), and was taken aback by many of Microsoft Word pitfalls. Why does it decide to auto-format so many things on my behalf ? And why can't it keep it consistent ? Reznik and I were editing with different locale settings (fr_BE and da_DK), which added even more fun to the mix: different paper size, different quote characters, and so on ...

I've also been offered the chance to review the new 176^th^ before it officially came out, and the whole review process, using a proxy Google Docs temporary document seemed archaic and painful to me. This extra step adds a lot of undesirable overhead to the process.

Last example: as a side-project, I'm maintaining a kneeboard document written with Microsoft Excel, and that takes the pain to a whole new level.

I would like to propose a solution to get rid of those issues, and implement a better workflow for everyone. This document is published for review in order to assess how interested/willing people are interested to give it a try.

## Objective

What I'm trying to achieve:

* Increase quality and consistency of the documentation
* Allow for easier collaboration and review
* Maintain an easy workflow for everyone
 
What I'm trying to get rid of:

* Variations in style or formatting
* Older documents not updated to latest layout/formatting
* Passing documents around during review/editing process

## Achieving these goals

### 1. Decoupling the content from the format

Writing a document with Microsoft Office Word implies formatting it as well. Despite the use of a template, guaranteeing a consistent format across a library of dozens of documents, written by many different authors, sometimes even multiple authors for the same document, is almost impossible.

Due to the inherent complexity of Microsoft Word Office, as well as the debatable pertinence of some choices it sometimes seems to automatically make for us, some subtle format changes are bound to sneak unnoticed within the document over time.

My first goal is to get rid of this ambiguity, and have one and only one way to express a given construct (a paragraph, a heading, a list, a table, ...).

This would also have the benefical side-effect of freeing editors from worrying about formatting their content while they are writing it, giving them more brain power for the actual content creation

Decoupling content and format also means that any older document, even one that hasn't been touched in years, will be automatically updated to the latest format/layout whenever the format/layout is updated, since their content has not changed.

Once the content has been created by the editors, my goal is to provide a system that will take that "raw" content, and format it, consistently, into different formats that will later be published. A choice format is of course PDF, but I'm thinking HTTP (web) or EPUB (books) as well.

The output should be:

* Consistent across builds: the same content must **always** yield the same result, even on different computers, operating systems, or software versions
* Uniformly formatted: **all** the documents in the library should have the same general layout, giving all documentation published by the 132<sup>nd</sup> Virtual Wing a visual identity of their own
* Retroactively managed: all documents that have been published in the past should be **updated without human intervention**. If a logo changes, if we decide to change the title page, or the space after paragraphs, those changes should be **automatically propagated across the entire library**
* Adapted to our needs: the documentation should not look "generic"

## Pros & cons

Allow me to start with the cons, and provide, for each of them, a way to mitigate them.

* No WYSIWYG ("What you see is what you get")
> Markdown is pure text, therefore an editor who is busy writing documentation do not see the result appear as he types. Font does not resize for headings, pictures do not appear, and tables look like a mess.
> 
> **Mitigation**
> 
> * Converting from Markdown to Word/PDF/HTML is trivial, and the tool that I will be providing can be installed on any modern computer. Output can therefore be refreshed as often as needed to get a "sneak speek" into the actual result.
> * Numerous tools exists *online* to edit Markdown. Some of those tools are bare editor, providing a side by side `Edit` window and a `Result` window. Their `offline` equivalent are available as well. Moreover, and this gets really interesting, Markdown is mature enough that many *free* online editors offer amazing synchronization capabilities with Google Drive, Dropbox, Github, ... , **effectively allowing anyone to work on any document from any computer connected to the web, and directly sends their work for review into the Github repository of the 132<sup>nd</sup> Virtual Wing** for review.

* Less liberty when it comes to customizing the format/layout
> Having a common template for the layout/format of our document effectively "castrates" editors, denying them the liberty to get creative with the way their content is rendered. This could get on the nerves on some, especially the most perfectionists among us.
> 
> **Mitigation**
> 
> * The rendering, formatting and layout is done by a professional (although free) typesetting application that has been in existence since 1985. 32 years of development, testing and improvements have made it quite robust. It has been in use for decades by the scientific and teaching community all around the world for papers, essays, reports, etc. While some might be reluctant to accept some of the formatting choices, it is my opinion that the resulting output is far above and beyond the minimum expected quality.
> * The layout/format will be 100% identical for all documentation published by the 132<sup>nd</sup> Virtual Wing, branding our documents with a unique "personality", and giving an overall "neat" picture of the Wing to the external world.
> * In case of necessity, when part of the output does not fit a specific need of ours, we can take advantage of the maturity of the tools and customize every little detail to our needs (this would of course be my job in the first time).
> 
* Resources like pictures, videos, sound, are to be included on the side
> All the files that are to appear in the final document will be referenced in Markdown as links only, pointing to a file that exists near the Markdown source document (I'll come back on the structure later). 
> 
> To give an example, if I wanted to include a file named `picture.png` in a document named `index.md`, I would have to write the following in `index.md`: `[Picture caption](path/to/picture.png){width: 8cm}`. "Picture caption" simply describes the picture, and can be any text. The `path` part is irrelevant, since that will be handled by the tools I am writing, but the problem persists: media only appear as text and are to exist alongside the source. The `{width: 8cm}` part is optional, but is amazing to "force" the same width (or height) on all pictures throughout a document (which looks real nice).
> 
> **Mitigation**
> * Declaring pictures by name offers a finer grained controls on their size, and allow for dynamic resizing of pictures from all origins
> * Updating pictures can be done without even opening the source. A file named `picture.png` will be included in the final document, whatever that file contains. Updating batch of pictures is thus very easy, and does not require updating them one by one in every Word document.
> Pictures are automatically indexed and referenced in the final document, and an automatic "Table of figures" is automatically generated, with hyperlinks to the pictures within the text.

* New technologies, part 1: Markdown
> While all the cons so far are of relatively small import, I fear this one might raise the most shields in our small community.
> 
> In order to be able to write documents, we would have to transition from using Microsoft Office to using Markdown. Now, Markdown is the definition of simple. It's an markup language that uses only text (this very document is written in Markdown!).
>
> It is used all round the world for things like writing small blogs posts to writing entire, full-featured books or website. It's also used for Github comments readme files, etc. Its strength is that it is, in its text only form, highly readable. But its real power is that, from that text only form, content can be generated in almost any form (PDF, Website, books, EPUBS, ...).
> TODO: give an example with Stackedit

* New technologies, part 2: Git (and Github)
> Now this is where I'm really afraid people will refuse to play along. Git is an amazing tool, for a lot of reasons, and is perfectly suited for the task at hand (managing a lot of text document). Its reliability, versatility and resiliency make it the uncontested choice for us. That being said, Git has a bad rap because its primary audience is programmer (it was written by Linus Torvald to manage the source code of the Linux kernel back in the day).
> People using Git for the first time (especially those who aren't f


## Technical

This section describes the tools chain that would be used to build and publish the documentation.

### Overview

Despite the vast possibilities that those tools permit, with a staggering amount of options, configurations and features, the whole process will be mostly automated, and the editors/reviewers will have to deal with very few technicalities.

The editor is responsible for creating or editing (new) content. From his point of view, the system works as follows:

1. The editor starts by cloning or pulling content from Github; this will give him th latest version of our documentation repository
2. The editor then starts a new document, or make changes to an existing one
3. Once the editor is happy with his changes, he commits them, and sends them back to Github
4. The editor then creates a pull request, effectively stating "hey, I made some changes here, what do you guys think about them?"
5. The editor then waits for review
	* The review process is sometimes very straight-forward, for example if the changes involve only fixing a typo, in which case the changes may be merged very quickly
	* The review process may also raise issues with the changes; maybe someone disagrees with part of the changes, or maybe someone has a better way. In essence, the pull request is effectively a **discussion over the proposed changes**, in which everyone can chime in
6. If the changes are accepted, the editor then merges his changes into the repository, and the documentation is automatically updated and published.

### Specific tools

This section gives a little description of each tool.

#### ![Mardown logo](https://i.imgur.com/ZGkIYsr.png) Markdown

Markdown is a [markup language](https://en.wikipedia.org/wiki/Markup_language) widely used across the Internet. Its syntax is simple (similar to the syntax we use on our forums) and is meant to be readable. This very document is written in Markdown (TODO: add link to source).

Excerpt from Wikipedia:

> Markdown is a lightweight markup language with plain text formatting syntax. It is designed so that it can be converted to HTML and many other formats using a tool by the same name. Markdown is often used to format readme files, for writing messages in online discussion forums, and to create rich text using a plain text editor. As the initial description of Markdown contained ambiguities and unanswered questions, many implementations and extensions of Markdown appeared over the years to answer these issues.

http://thepilcrow.net/explaining-basic-concepts-git-and-github/

```flow
st=>start: Start
e=>end
op=>operation: My Operation
cond=>condition: Yes or No?
st->op->cond
cond(yes)->e
cond(no)->op
```

​```mermaid
  sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick
    Bob->>Alice: Not so good :(
    else is well
    Bob->>Alice: Feeling fresh like a daisy
    end
    opt Extra response
    Bob->>Alice: Thanks for asking
    end
​```

   ```mermaid
   graph LR
   stepA-->stepB
   stepB-->stepC
   stepA-->stepC
   ```