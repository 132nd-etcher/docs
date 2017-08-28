---
author:
 - etcher
applies:
 - //wing
title_pictures:
 - logo617th.png
 - logo23rd.png
 - logo259th.png
 - logo696th.png
 - logo176th.png
 - logo765th.png
subtitle: Documentation overhaul
type: Enhancement Proposal
version: 0
published_date: unpublished
responsible: etcher
summary_of_changes:
 - nil
---


![Documentation](https://www.virtual-aaf.com/uploads/monthly_2017_06/OvGME-logo.png.a0cf027982a22a14140b3523e254bf08.png)

# Enhancement Proposal

## Abstract

This document contains an enhancement proposal submitted to CMD for review.

The proposal is about managing mods and skins in the //wing. I would like to make it easier for maintainers to offer and maintain mods, while keeping it simple for the end-user to install them.

## Rationale



## Objective

What I'm trying to achieve:



What I'm trying to get rid of:



## Getting there

This section conceptually describes how to achieve the goals outlined above.

### Decoupling the content from the format

Writing a document with Microsoft Office Word implies formatting it as well. Despite the use of a template, guaranteeing a consistent format across a library of dozens of documents, written by many authors, sometimes even multiple authors for the same document, is almost impossible.

Due to the inherent complexity of Microsoft Word Office, as well as the debatable pertinence of some choices it sometimes seems to automatically make for us, some subtle format changes are bound to sneak unnoticed within the document over time.

My first goal is to get rid of this ambiguity, and have one and only one way to express a given construct (a paragraph, a heading, a list, a table, ...).

This would also have the beneficial side effect of freeing editors from worrying about formatting their content while they are writing it, giving them more brain power for the actual content creation

Decoupling content and format also means that any older document, even one that hasn't been touched in years, will be automatically updated to the latest format/layout whenever the format/layout is updated, since their content has not changed.

#### Specification

## Pros and cons

This section objectively (as much as I could) describes the pros and cons of the method I propose to implement.

### The cons

### The pros

## Technical

This section describes the tools chain that would be used to build and publish the documentation.

### Overview

## Transition


### Crash course

I plan on offering crash course with Git/Github/Markdown to the people who are interested in it, and to write a few pages long tutorial to help to get newcomers started as well.

The crash course should take about 30 minutes on TS, getting people to install the necessary tools, and get started with them ("hands on" tutorial).

The written tutorial would be much of the same, covering the installation of tools, the publishing process and a little syntax related guidelines.
 
