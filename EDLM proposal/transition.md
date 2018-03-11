# Transition

Transitioning from the current documentation library to 
EDLM will not be painless, but it should not be too painful 
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

On a big document, like the //sop617, "fixing"  the document
could take a couple of hours (I already did most of the work 
on //sop617, see me [example version of it](http://132virtualwing.org/docs/132%20617th%20SOP%202.1.PDF).

On more simple documents, like the "Welcome letter" or the "Command document",
it might take only a few minutes.

## Process

The actual transition could happen like this:

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
by myself or anyone willing. Probably a week or two, without
working too much?

## Crash course

I plan on offering crash course with Git/Github/Markdown 
to the people who are interested in it, and to write a 
few pages long tutorial to help to get newcomers started 
as well.

The crash course should take about 30 minutes on TS, 
getting people to install the necessary tools, and get 
started with them ("hands on" tutorial).

I will of course be available most days on Discord as well,
to provide assistance as usual.

The written tutorial would be much of the same, covering 
the installation of tools, the publishing process step by step,
and a little syntax related guidelines.