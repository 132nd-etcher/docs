

# Technical

This section describes the tools chain that would 
be used to build and publish the documentation.

## Overview

Despite the vast possibilities that those tools 
permit, with a staggering amount of options, 
configurations and features, the whole process will 
be mostly automated, and the editors/reviewers will 
have to deal with very few technicalities.

## Specific tools

The front-end is what editors will have to work with.

### Markdown

Markdown is a [markup language](https://en.wikipedia.org/wiki/Markup_language) 
widely used across the Internet. Its syntax is simple (similar to 
the syntax we use on our forums) and is meant to be readable. This 
very document is written in Markdown; [click here to see the "raw" 
Markdown text](https://raw.githubusercontent.com/132nd-etcher/docs/develop/EDLM.md).

Excerpt from Wikipedia:

> Markdown is a lightweight markup language with plain text 
formatting syntax. It is designed so that it can be converted 
to HTML and many other formats using a tool by the same name. 
Markdown is often used to format readme files, for writing 
messages in online discussion forums, and to create rich text 
using a plain text editor. As the initial description of Markdown 
contained ambiguities and unanswered questions, many implementations 
and extensions of Markdown appeared over the years to answer these issues.

[Here is a cheat-sheet with the available formatting](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

For example, here's the link to this very document in Markdown: 
[https://raw.githubusercontent.com/132nd-etcher/docs/master/EDLM%20proposal/index.md](https://github.com/132nd-etcher/docs/raw/master/OvGME%20proposal/index.md)

Since it's hosted on Github, here's the link to it when it's 
automatically represented by it (much nicer already): 
[https://github.com/132nd-etcher/docs/blob/master/EDLM%20proposal/index.md](https://github.com/132nd-etcher/docs/blob/master/OvGME%20proposal/index.md)

#### Why Markdown ?

I selected Markdown mainly because **it decouples the content 
and the format**, but also for the following reasons:

* It's readable and easy to "learn";
* It's used all over the web; tutorials are plenty, and all;
questions have been answered;
* It's supported by all the major players;
* It's very easy to transform into PDF, HTML, EPUB, RST, Microsoft Word, etc.

#### Try it out

You can try Markdown right now, without installing anything. 
Just head to one of those online editor, and write away:

* [dillinger](http://dillinger.io/) (my favorite)
* [classeur](http://classeur.io/)
* [stackedit](https://stackedit.io/editor#)
* [jbt.github.io/markdown-editor](https://jbt.github.io/markdown-editor/)
* [markdownlivepreview](http://markdownlivepreview.com/)
* [hackmd](https://hackmd.io/)
* [etc.](https://www.google.be/search?q=markdown+online+editor&amp;rlz=1C1GGRV_enBE752BE752&amp;oq=markdown+online+editor&amp;aqs=chrome.0.0j69i61j69i60j69i61j0l2.2135j0j7&amp;sourceid=chrome&amp;ie=UTF-8)

#### Offline editors

If you prefer to work offline, there are tons of editors for Markdown:

* [Notepad++](https://notepad-plus-plus.org/) with [plugins](https://www.google.be/search?q=notepad%2B%2B+markdown)
* [Atom](https://atom.io/) with [plugins](https://www.google.be/search?rlz=1C1GGRV_enBE752BE752&amp;q=atom+markdown)

[And millions others...](https://www.google.be/search?q=markdown+editor+windows)

### [Git](https://git-scm.com/) &amp; [Github](https://github.com/)

This is where things get a little bit hairy. It will seem very 
complicated at first, but I can assure you that after doing it a 
few times it makes a lot of sense and becomes actually quite easy 
(we're in the business of simulating a very complex environment, 
I reckon a few commands won't scare you that much =)).

Here is an [introductory tutorial about Git &amp; Github](https://guides.github.com/activities/hello-world/).

Here is another [tutorial about the Git philosophy, and one way to use it](http://thepilcrow.net/explaining-basic-concepts-git-and-github/).

Please don't be scared by all the commands, there is a GUI application 
that lets you do all those things with a click of the mouse.

I selected Git &amp; Github because it allows for a *outstanding way 
of working together on the same project*. With Git &amp; Github, you can:

* Track *all* the changes, and roll back whichever one you'd like (constant backup of everything)
* Associate changes with their author at a glance
* Collaborative editing (many people can work on the same document at the same time)
* Incremental review process supporting discussion
* Issue tracker
* Allows for a lot of automation under the hood
* Git is the *de facto* Source Control Manager nowadays (alternatives: 
[Subversion](https://subversion.apache.org/), 
[Mercurial](http://hginit.com/); 
[compare them](https://www.google.be/search?q=git+vs+subversion+vs+mercurial))
* Github is the *de facto* hosting website for open source 
Git projects (alternatives: [Bitbucket](https://bitbucket.org/product), 
[Gitlab](https://about.gitlab.com/); 
[compare them](https://www.google.be/search?q=gitlab+vs+github+vs+bitbucket))

**Note:** I'm leaving out alternatives that are not 
open-source, self-hosted and free to use.

### What you'll need

This is the list of what you would have to install 
on your computer in order to be able to work on the documentation.

#### Option 1: work online only

This is absolutely possible. For example, with [http://dillinger.io/](http://dillinger.io/), 
I'm writing this document in Markdown, I get to have a live preview 
of what I'm writing, and I can push it to Github with one click of 
the mouse. No fuss, no problemo.

#### Option 2: work offline

While option 1 is perfectly fine, you can also decide that you 
need more control of what is going on. In that case, you'll 
need a minimal suite of tools.

##### Edit Markdown

This one is easy: you don't need anything. Markdown is pure 
text, so any text editor will do.

##### Work with git & Github

First, make sure you followed 
[this tutorial](https://guides.github.com/activities/hello-world/) 
and are a little bit familiar with Git.

Then install the following:

* [Git for windows](https://git-scm.com/download/win)
* [Github windows client application](https://desktop.github.com/) 
(alternatives: [smartGit](http://www.syntevo.com/smartgit/) 
(my favorite, more complex), [Gitkraken](https://www.gitkraken.com/))

That's it ! Create an account on [https://github.com/](https://github.com/), 
start your local Git client, and you're ready to rock !

//include "build process.md"