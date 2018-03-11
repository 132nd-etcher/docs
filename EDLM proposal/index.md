---
title: "EDLM: proposal"
author:
 - //etcher
author-meta: //etcher
applies:
 - //wing
audience: CMD
status: published for review by CMD
title_pictures: //all_logos
subtitle: Documentation overhaul
type: Enhancement Proposal
version: 0.2
published_date: 180218
responsible: etcher
summary_of_changes:
  - 0.2 180223 fixed layouts and references
  - 0.1 180218 initial publication for review by CMD
---

# Enhancement Proposal

//include "intro.md"

\clearpage

## Pros and cons

This section objectively (as much as I could) describes the pros and cons 
of the method I propose to implement.

//include "cons.md"

//include "pros.md"

\clearpage

## The workflow

This section describes how to *actually* create a document with this system.

It is meant as a quick walk-through of the system, to give you an idea of
what would actually be required of people willing to create or edit 
documents if we decide to adopt it.

//include "workflow.md"

\clearpage

## Text formatting

So how is text formatted if we're not using Word? With Markdown!

Before we dive in, I recommend you head to [Dillinger online Markdown editor](https://dillinger.io/).
That way, you'll be able to toy with it yourself =)

Here's a [cheat-sheet of Markdon syntax](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
Feel free to give it a quick glance to see if it looks over-complicated, but I will go over the basics
so you can see the actual results once converted in PDF.

//include "text formatting.md"

\clearpage

## Diving a bit deeper

Before I can talk about the next three features, I need to introduce a new concept: the "settings" file.

**Note**: it's perfectly Ok to *not* have a settings file, you do not need it to create a document. I'm
talking about it here for the sake of being exhaustive in my presentation.

//include "settings.md"

\clearpage

//include "technical.md"

\clearpage

//include "transition.md"

\clearpage
 
//include "closing words.md"

\clearpage

//include "pictures.md"

