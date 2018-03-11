### (only once) Install the required tools

The only thing you would absolutely need is some way to pull/push to Github.

That means a Git client, which can be one of:

1. The Git command line (only for the nerds)
2. SmartGit (mostly for the nerds too, we don't need a tenth of its features)
3. The [Github official client  application](https://desktop.github.com/)
This is is the one I will recommend to newcomers. It is very simple to use,
and does absolutely all that we need.

**Optional**: install EDLM

(EDLM is the name of the tool I made)

For those who want to preview their PDF locally instead of online, there is
the possibility to install and use the tool I made on their machine.

There isn't much to it either:

1. Download and install [Python](https://www.python.org/downloads/) (only once);
2. Open a cmd prompt and type the following:

> pip install --upgrade edlm
>
> edlm convert pdf .

That will install the tool, update it, and convert all the documents in the current folder.

Of course, if this project is accepted, I will (at some point int the future, since it's 
perfectly working and workable at this stage):

* Create an installer (`EDLM.msi`) so there is no intermediate step;
* Build a GUI around the application (same as EMFT) so there is no need for the command line.

### Create a document

To create a document, on would:

1. Clone or pull the Github repository;
1. Create a folder for their document in the repository (this is the `source folder`);
1. Create a file named `index.md` in the `source folder`;
1. Add whatever content they want in `index.md`
1. Commit their changes;
1. Push their changes.

That's it ! We have a new document =)

As an example, here is this very section of this very document written in Markdown:

```Markdown
### Create a document

To create a document, on would:

1. Clone or pull the Github repository;
1. Create a folder for their document in the repository (this is the `source folder`;
1. Create a file named `index.md` in the `source folder`;
1. Add whatever content they want in `index.md`
1. Commit their changes;
1. Push their changes.


That's it ! We have a new document =)

As an example, here is this very section of this very document written in Markdown:
```

Cfr. \ref{commit} for a diagram of the committing workflow.

Cfr. \ref{basic_workflow} for a diagram of the editing workflow.

![Basic work flow \label{basic_workflow}](https://www.planttext.com/plantuml/img/ZP9DQWGX48NtdgBe_GHQ-m2p2Ta4iiW97AsP4HnD_864aBkdhD4GGjEq6_sgwzLxK7tCHQTIRru8RKfCC3rQH_S4EWFQMPoZjqZbrrYJGRWZVyt9pF0bW0wDS6VIm-I2nO-7cvsWjRJwBBx5UyMAC3r7epqaV8kvUNpoc8RpkhlSTfSxtEKETxdkhhRTrGvtjSDThRilOclm8eoFrOu85mpKzX9SG9B-Jed1KwKjeBVtVgkBFkbCgPvSkTRJ_rYNQvFGzk5mw3kaPGoG16g08bW6B893i-o-LkuVA1dLGCN8uX5KiAfLA09B_hnLV_VcJdIE62pzmJy0)

![Commit workflow \label{commit}](https://www.planttext.com/plantuml/img/bPAxJiKm38PtFuNL7IGEbmM4G48mWH0milYaBer8av1BqH7YtN6I0aBgGeVM_Mr_Jlxa8YOAAKy6W5xO9kmkSt8J9Uun9lOTvCYA8cDtIpQJMLGmBEKz6XuIF8sIdaWoeSDj8Aj6r15zS8cLa4xXpYKaktEMKP55d-E8oQ5E-o2KnW9GnkKUyGDGdfuIRUlW6vt6lCN0taMTNDWzsqStyJAfGuhuCXx0vty0jtMrVn6RWlXsmVkPToxK5CsWhPGFf8HsduqHrblcc6hQ1u31cLvuFtqehcgfJt4XbFzbOOCs1NDrtRhxuM1TtgpBX-loqRfyl2wVbBtAsQjNxCHCSLF9MxSDjH3Q1_Vspgk_FnVXWMVDxxKoy0mySwWdUrOgY-A3DDNej-bIAVODJpK4CSSLn_f9swQN241crPdYEiq5rCo3nKCHnF1Qsyg-QUMpB7O3CdmrMm_hGcwRNFal)

\clearpage

### The header

Now there is more to this, of course. We want to give "properties" to our documents!

An author, a published date, a list of changes,etc.

There is a standard header for all documents. Here's, for example, the header of
the [OvGME for pilots PDF](http://132virtualwing.org/docs/OvGME%20for%20pilots.PDF):

```yaml
---
title: OvGME for pilots
author:
    - // etcher
author-meta: // etcher
header_text: OvGME for pilots
status: effective
applies:
    - // wing
    - External organizations
title_pictures: // all_logos
subtitle: Operating Instructions for Mods and Skins Installation
type: Operating Instructions
version: 1.3
published_date: 22/09/2017
responsible: // etcher
audience: pilots
summary_of_changes:
 - '171116: updated link to 132nd repository (removed extra spaces for copy-paste)'
 - '180216: update for 2.5'
 - '180217: update recommended OvGME version'
---
```

And here is what it looks like on [Github](https://github.com/132nd-etcher/docs/blob/master/OvGME%20for%20pilots/index.md).

**Note**: do not pay attention to `// etcher`, `// wing` and `// all_logos` for the time being, they're just "shortcuts"
that I'm using. `// all_logos`, for example, will be replaced by the list of all the logos of all the squadrons of the wing.
(actually they are "aliases", but we'll talk about them later)

The header comes before the text in `index.md`, and contains the "metadata" about the document. You can see them rendered
on the 3rd page of all the PDF I gave as examples.

As you can see, their format isn't black-magic. Some values are just text, like the `title` or the `status`, and other
values are "lists", like `applies` or `summary of changes`.






