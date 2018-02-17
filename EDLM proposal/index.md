---
title: "EDLM: proposal"
author:
 - //etcher
author-meta: //etcher
applies:
 - //wing
audience: CMD
status: in writing
title_pictures: //all_logos
subtitle: Documentation overhaul
type: Enhancement Proposal
version: 0
published_date: unpublished
responsible: etcher
summary_of_changes:2
 - nil
---


![A pile of books](https://i.imgur.com/DNB0lco.png)

# Enhancement Proposal

//include "intro.md"

//include "rationale.md"

//include "objective.md"

//include "examples.md"

//include "getting there.md"

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

//include "settings.md"

\clearpage

//include "build process.md"


Basically, what happens during the conversion is:

1. Grab the settings from the global `settings.yml` file
2. Update those settings with the document `settings.yml` file
    * All settings that were in the global settings are 
	preserved, unless a setting with the same name is 
	declared for the document, in which case the global 
    settings are overwritten
    * All settings present in the document file that are 
	not in the global settings will simply be added
3. Using those settings, pre-process the markdown text 
files; settings may include:
    * aliases to replace some text in the document 
	with predefined string
    * a new title for the document, different from the 
	folder name; maybe some characters you want in the 
	title aren't allowed as a folder name on Windows? 
	**Note**: at the time this proposal were written, 
	those were the only two possible settings; many 
	others will probably come in the future
4. Still using the settings, pre-process the Latex 
template; this will, for example:
    * compute the path to the media file
5. Using the resulting template and markdown text, 
build the final PDF.

Why such a complicated system ?

First, we want to be able to declare and access 
settings that are common to all documents, and are 
susceptible to change in the future (new settings may 
be added later without requiring changing the document 
text, no worries). That is the role of the global 
`settings.yml`.

Then, we also want to be able to create settings that 
are specific to the document itself. Maybe some abbreviations 
are valid only in the scope of a specific squadron ? 
That is the role of the `settings.yml` that is in the 
document folder itself.

With those settings, we are able to pre-process the 
Markdown document. Aliases are replaced withon the 
text, etc.

Finally, we need a global `template.tex` to create PDF. 
That template ensures that all documents received the 
same formatting. But, each document also has specific 
needs: their `media` folder will be at a different 
location, and some other settings may be different too. 
So we also pre-process the template using the current 
settings (and information gathered automatically, like 
the `media` folder path).

We now have a pre-processed Markdown, and a pre-processed 
template. We can use Pandoc to get a PDF out of those 
two, and voila !

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

[Here is a cheat-sheet with the available formatting](https://gist.github.com/jonschlinkert/5854601).

For example, here's the link to this very document in Markdown: 
[https://raw.githubusercontent.com/132nd-etcher/docs/master/EDLM%20proposal/index.md](https://github.com/132nd-etcher/docs/raw/master/OvGME%20proposal/index.md)

Since it's hosted on Github, here's the link to it when it's 
automatically represented by it (much nicer already): 
[https://github.com/132nd-etcher/docs/blob/master/EDLM%20proposal/index.md](https://github.com/132nd-etcher/docs/blob/master/OvGME%20proposal/index.md)

#### Why Markdown ?

I selected Markdown mainly because **it decouples the content 
and the format**, but also for the following reasons:

* It's readable and easy to "learn"
* It's used all over the web; tutorials are plenty, and all 
questions have been answered
* It's supported by all the major players
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
* [etc...](https://www.google.be/search?q=markdown+online+editor&amp;rlz=1C1GGRV_enBE752BE752&amp;oq=markdown+online+editor&amp;aqs=chrome.0.0j69i61j69i60j69i61j0l2.2135j0j7&amp;sourceid=chrome&amp;ie=UTF-8)

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

This is absolutely possible. For example, with http://dillinger.io/, 
I'm writing this document in Markdown, I get to have a live preview 
of what I'm writing, and I can push it to Github with one click of 
the mouse. No fuss, no problemo.

#### Option 2: work offline

While option 1 is perfectly fine, you can also decide that you 
need more control of what is going on. In that case, you'll 
need a minimal suite of tools.

##### Edit Markdown

This one is easy: you don't need anything. Markdown is pure 
text, so any text editor will do

##### Work with git &amp; Github

First, make sure you followed 
[this tutorial](https://guides.github.com/activities/hello-world/) 
and are a little bit familiar with Git.

Then install the following:
* [Git for windows](https://git-scm.com/download/win)
* [Github windows client application](https://desktop.github.com/) 
(alternatives: [smartGit](http://www.syntevo.com/smartgit/) 
(my favorite, more complex), [Gitkraken](https://www.gitkraken.com/))

That's it ! Create an account on https://github.com/, 
start your local Git client, and you're ready to rock !

# Transition

Transitioning from the current documentation library to 
EDLM will not be painless, but it should not be painful 
either, nor take an unreasonable amount of time.

I'm providing tools to convert from Word/PDF to Markdown, 
but that process is error-prone. So, far, the issues I've 
been able to identify are:

* The format
    * Tables
    * Lists
* The pictures (the pictures are correctly extracted from 
the Word/PDF document, and put in the media folder, but 
their format and/or positioning might need to be adjusted).
 On a big document, like the //617 SOP, this could take a 
 couple of hours. On more simple documents, it might take 
 only a few minutes.

## Process

The actual transition would happen like this:

1. Freeze the current state of the library (no more 
edition of current Word documents)
2. Convert documents in Markdown
3. Build a sane structure for the new library
 * Place pictures in the correct folder (maybe some of 
 them should be shared between document? Or even maybe 
 with the whole Wing?)
 * Define settings and metadata for the documents 
 (title, authors, ...)
4. Build the new library incrementally, green-lighting 
documents one by one until they all pass QA

In all honesty, I'm unable to give an objective estimate 
of the time this will take, mainly because I don't know 
who will be able to spend time on this. Older documents, 
whose maintainers are gone or inactive, can be updated 
by myself or anyone willing.


## Crash course

I plan on offering crash course with Git/Github/Markdown 
to the people who are interested in it, and to write a 
few pages long tutorial to help to get newcomers started 
as well.

The crash course should take about 30 minutes on TS, 
getting people to install the necessary tools, and get 
started with them ("hands on" tutorial).

The written tutorial would be much of the same, covering 
the installation of tools, the publishing process and a 
little syntax related guidelines.
 
# Closing words
 
 Thank you for reading that huge blob of text, I hope I 
 managed to make sense most of the time.
 
 Now that this proposal is out for review within CMD, 
 the next step, in my opinion, could be one of those two:
 
1. The proposal is rejected by CMD, in which case 
the project dies right here.
2. The proposal is accepted by CMD, and is pushed 
to all IPs for review; I'm suggesting this 
supplementary review step because a lot of our 
documentation is actually written by IPs, it would 
make sense for them to have a say in the matter.
3. Depending on IPs feedback, the project either dies,
is adapted, or adopted.

# Pictures used throughout the document
 
The pictures have been generated using PlantUML 
syntax, thanks to the [Planttext website](http://www.planttext.com).
 
Figure \ref{doc_folder}:
[Document folder](https://www.planttext.com/?text=ROzB2W8n343tEKNe0GfwWbcuzGnIsZW4-XdI51IPkrix3kF2RF9vZuHCLPreIn50MIFXfVYMA2lUImma05j6imE3hc8jJJpX2x37Rbmfi1iuVQel7GRtpMPXhqteP9Syc__iVB0L3bf9bVDidobkvyNV-kp7u1peOLCOU3Im0aoKG__j3G00)

Figure \ref{root_folder}:
[Root folder](https://www.planttext.com/?text=RLBB2i8m4BpdAq8_e505lVRWLV3WlOHaRGDvbCqMAj9_jwQfVMWkOMScExj3oa02gRE6CT9aWDyRuEWzyOSt2f2nwURPJI0uuaeZIFBupBW8l9t05-FZcPLNK5giwCf-W2IAGZqQPSRNlZWUdCfRLsT_o5DnfcOX1xRG0OYqg_EdDRDHDMARCUvWMoC8GbHGggf4xwUP-PoWtpnOUwVE5oyx-zbx0g8y-0ubhDl-fB6FOJ5ljQGEeTWcySCVjlomMs4VIa3v3MLHQQUWpwsAabYa3GTMWbFZLtW3)

Figure \ref{nested}:
[Nested root folders](https://www.planttext.com/?text=VPBDYiCW58NtFeNa0KArqDbsCTk1MNHVHE-aWZ_1t41ByTrhJKAQA9DDSk_vv1mFEGye0exM488Q3T3B3MZm7kcVDme28TERDhyYW4EgT029FZmQAWRQvoMZJqBJiw0_eBJ8kdr_BN96TF9eZEyyEtAdsjvrJKKyiI-yhM8agpm0edPT-x0cMwIPRTp_2Se_azJ3yfLOFNijSGnmsCOjzEDMZxkBLPBp8iu5R6y4mf0HdAVhBDV2BKoBSDySgWMPNRwz7EsxfMannV5ZaB2tgBUqeuecMDbKmV2IYPNh5Qq5UKsx2gcTWdjhLSRoi6iWaaZEu5JwtLy0)

Figure \ref{processing}: 
[Processing](https://www.planttext.com/?text=TLVRRkCs47tdLmpyq4sAh03VZJvirsswHO4D47I3zgM0GKiZcx142XJbooxoxnrUH4cEumV7EdD83WyFPvJFjU7QD6N1c16cGFZ6ouh-P2fjIfG6TYXHSoEK_4_YsGKPaof367rxMV_zyWki9Iyktn5grUYKHWgDgL7wCW9UGssmsemPorMHeORHCzTsrY6fyk0F1lHfcK-O2TuBRqeB198Z2ifpLAYT6aydCaigkHlT22x6IxFlWg-i2zTeZ92xv58MxK8RmWPfl21jcHki7SE4fqq8NsVJnXE3vy60_jfXviSWiTV9YzURxuqCr_llLgr4QXgDuw44R-AJOVprAlThDMgTHZKwbf0PdfCoSnJt4BRsoXWZAucSfuRE-V6B6-1rpNB6KgwpJivVepeRF5Tale13alHGgGZHOhSteF8Ejmk-x36A2uAcekVHjcYmqe8q3Kfhu4KHpLmd3dPVVnaxwhJdnbBKQK04enofKEf00N701pW9imSEHzGNiczDKgL67Ft1Zfm3uHz1LuaNy2_9EFA3Vu8SiHYi-u6MrS8ObAGVVANyppJxNgHxcn5th5JPYtQ6bqk5uLoWu7BNy1sbictygTH8sT1w5IfxPsasgu9TdPBMoBEBenqaRU-EKuA5Ek8z2DFFvqFPag7IwYWoDvn-qx9-VAqAaNLY6wjPlLTDaS41qHz7KyDEsP5ESrg8VXfH8aDQrXvZQu3VLLcwL8JqvaZBZCg3ynPcHHdjPnysOUzri4A1kNF2CERjGDgvMQo6i2lKbeG9MifSx1fVn3p79ld7uzUdDtvef3tiuW9SNfH4EBbTXXtIt5Iv6cstAPKkQG5LXUBuu3XqC7OMhoDcTXlShdz4ASXMZdFY5x8N5KQbgMQ6FS0MpGbHXcEjQvlgdP1KFdbcTxpdHxki8Jyu3Xrq2SeVUEebzOubMG4vUScgVv_qz6TKwjC3bUrspLohigszljpuUn_Yuzi3GgMwCM1oUy3WL5lkz3OtlNP7ovynSZxbEVeYgDr4s75o2xbInKBDWeyVV-xj8zJr0JfX0nCDObD6fXmWCvgwdOu2gh_dzjS0dqPyEi1d4Pyvl9-x5yGL_21l7Nee1NpxOspG35sAlUXjzAgCzaFMCcigVA53MEjIlI6TXRSYNOFGTq8_ulPcjmxqKr5bf1cs22NFl3dvaOk2R-cYaT4jp-tIXTeAEp2cVvqO9_0d9xOUh5Z7ruXnu4s8HuSPwr7VYKIR1DhKqzf-rNKZIve6qioJ1dQoyLc8pnDurYgb2ndNYvnvu2mIeA9MDSOgS0PHabEX5jyxvY8mbzriJrmVCdMIaRCCd5K2lpM2YWvrq1XSKVLKqcXLmCZMBHSuANr0FNytidWtidmtih9bmbzmxoBtzjPpJ8J7h6t74Pem9tPydhBexeZDM4Wx8lE0B2Ao2CWo8ik0h2AoUkjgEp2s0lleNWiKy9IgYihQbx1Cv3cwcbTngjxkf6guMyzy2L_F7s2zUA3taEI-rnwUsmj2rmzuOrH9PJ-bTuRG8lUwaGUm9shRiDBsheINY9ow1eUQsaL1O4NkkAhALcFQsATFGLZttG4J1qmwOEg0QGVC733hWBa3vXsmSC2Y0vOEM7R0oW4h3xWNDlfyfZpfVuF_0G00)

Figure \ref{basic_workflow}: 
[Basic work flow](https://www.planttext.com/?text=ZP9DQWGX48NtdgBe_GHQ-m2p2Ta4iiW97AsP4HnD_864aBkdhD4GGjEq6_sgwzLxK7tCHQTIRru8RKfCC3rQH_S4EWFQMPoZjqZbrrYJGRWZVyt9pF0bW0wDS6VIm-I2nO-7cvsWjRJwBBx5UyMAC3r7epqaV8kvUNpoc8RpkhlSTfSxtEKETxdkhhRTrGvtjSDThRilOclm8eoFrOu85mpKzX9SG9B-Jed1KwKjeBVtVgkBFkbCgPvSkTRJ_rYNQvFGzk5mw3kaPGoG16g08bW6B893i-o-LkuVA1dLGCN8uX5KiAfLA09B_hnLV_VcJdIE62pzmJy0)

Figure \ref{commit}:
[Commit workflow](https://www.planttext.com/?text=bPAxJiKm38PtFuNL7IGEbmM4G48mWH0milYaBer8av1BqH7YtN6I0aBgGeVM_Mr_Jlxa8YOAAKy6W5xO9kmkSt8J9Uun9lOTvCYA8cDtIpQJMLGmBEKz6XuIF8sIdaWoeSDj8Aj6r15zS8cLa4xXpYKaktEMKP55d-E8oQ5E-o2KnW9GnkKUyGDGdfuIRUlW6vt6lCN0taMTNDWzsqStyJAfGuhuCXx0vty0jtMrVn6RWlXsmVkPToxK5CsWhPGFf8HsduqHrblcc6hQ1u31cLvuFtqehcgfJt4XbFzbOOCs1NDrtRhxuM1TtgpBX-loqRfyl2wVbBtAsQjNxCHCSLF9MxSDjH3Q1_Vspgk_FnVXWMVDxxKoy0mySwWdUrOgY-A3DDNej-bIAVODJpK4CSSLn_f9swQN241crPdYEiq5rCo3nKCHnF1Qsyg-QUMpB7O3CdmrMm_hGcwRNFal)

Figure \ref{publish}:
[Publish workflow](https://www.planttext.com/?text=RLAxRiCm3Dpv5OJt34dQZa6A1kqKe5ExTA4bsHOYIuOU2OAY_rwQTjt5MdIyeqJof6FA57Ff7G2rncUidaiEFMMZCMKpL52IKPGCLcVoXTpCWdAXQCHlG5wQCjMIz6PpLsgCPWZ9vX3lN_vCV2HY7Schha9As7Rmyrzl6Axc7g8eT0LeWjESlmZ83Tg6L4vJ2aTpsSOwBlb-UXLXqCrsdTwjq_jr-c6TVboddyPH9ZEgxNxdDNvODfID-hI-nPkfsGSZsJDU9Z-PmOMxI5eW0B-6kc3r4lhUPWmUUp5FSfIGC6susHn67w7j1B9nT6Kazapmy7Vhj2tY4XwMZiHJrfSEer6PV3lEUWggzDplwBn17svSYwoZsarJHO3vc5p9uT5upJ_g5m00)



