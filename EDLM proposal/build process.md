## The build process

Before I can present you with examples, I need to explain a few basics 
about the build process I'm proposing.

### The document folder

Every document lives in its own folder, and is composed of three parts:

![Document folder \label{doc_folder}](https://www.planttext.com/plantuml/img/ROzB2W8n343tEKNe0GfwWbcuzGnIsZW4-XdI51IPkrix3kF2RF9vZuHCLPreIn50MIFXfVYMA2lUImma05j6imE3hc8jJJpX2x37Rbmfi1iuVQel7GRtpMPXhqteP9Syc__iVB0L3bf9bVDidobkvyNV-kp7u1peOLCOU3Im0aoKG__j3G00)

#### **index.md**: the document ("md": "Markdown")

This file contains the actual text of the document.

It can also contains references to other Markdown files, in order
to "include" them, for example the //sop617 "include"
the //qr617.


#### **settings.yml**: the document's settings ("yml": "YAML")

This file contains the settings for the document, for example:

* aliases
* paper size
* references
* title
* etc.

**aliases** are a neat way to create a placeholder for a "complicated", or 
rather long text. For example:

```
aliases:
  - //jf: "J-TAC/FAC(A)"
```

would let us write `// jf` in our `index.md` file, and they would
be automatically replaced by "J-TAC/FAC(A)" in the final document.
It just saves a lot of typing and help reduce typos.

It also help us to have a more "uniform" rendering of the names & conventions
within the //wing: for example, I'm using this setting in my "settings.yml":

```
aliases:
  // wing: 132^nd^ Virtual Wing
```

Whenever I want to reference the Wing, I type `// wing`. If everyone does that,
then we have one and only one way to "express" a given thing.

**Papersize** is a list of formats we'd like to create this document in, 
for example:

```
papersize:
  - a4
  - a5
```

would automatically create two specific PDFs, one in A4, and one in A5.

**references** is a neat way to create a "bibliography" of documents.

For example, here's a piece of mine so far:

```
references:
  // ttp1: "132-TTP-1 CAS Manual, https://www.dropbox.com/..."
  // ttp1a: "132-TTP-1-A CAS Formats, https://www.dropbox.com/..."
  // ttp4: "132-TTP-4 Brevity, https://www.dropbox.com/..."
  // ttp5: "132-TTP-5-ATC and Airbase operations, https://www.dropbox.com/..."
  // ttp6: "132-TTP-6 SCAR, https://www.dropbox.com/..."
  // ttp7: "132-TTP-7 Flight Lead, https://www.dropbox.com/..."
  // ttp8: "132-TTP-8 Briefing Guide, https://www.dropbox.com/..."
  // ttp9: "132-TTP-9-Range Control Officer, https://www.dropbox.com/..."
  // ttp10: "132-TTP-10-AWACS Procedures, https://www.dropbox.com/..."
```

(I removed the full links because they're not needed for this example)

This works the same way as "aliases": if I type `// ttp1` in my document, it will insert a
clickable hyperlink to the document I'm referencing.

If, later, that document's link changes for some reason, there is no need to manually
update all other documents that reference it; all we need to do is update "settings.yml",
re-build the library, and the link is magically updated everywhere.

#### **media** is a folder that contains the images for this document.

If I want to include a picture that is in "media/picture1.png", all I need 
to do is type the following in my `index.md`:

```[My picture cool name](picture1.png)```

All the rest (layout & formatting) is automatically taken care of
for me.

Also, if I want to change that picture later, I do not need to edit
my document; overwriting the old picture with the new one will do!


### The root folder

A "document folder" will "live" inside a "root folder" (it's just the 
directory that "contains" the "document folder").

![Root folder \label{root_folder}](https://www.planttext.com/plantuml/img/RP7B2i8m44Nt-OhG3oYqWcwxS2kuS5z2CjP07cKoWOhqtwrfQn-QJSYz1oOdgG89f6WDOwJ90ByzWAFtnE_UA436nfrdLu7WY2kD8CdZC-CYy7OCNumFQoOleBHOrRNz11EKG3qCoenlV74edSfRrsH_ocDneiTIzcof0n1fr-HFQ-P1zP2j20BR6a6G4tG9cOFDLSzUHlin68C41XzHmlgwFrvxeMLigoL5X6BhzDENsxxVsU_r0iglta9ffw3BhKf8EaplrBCAd1e-zGq0)

We can see similarities between the "root folder" and the "document folder":

* Both of them contains a "settings.yml" file
* Both of them contains a "media" folder

Put simply, a "root folder" will "share" its settings and its pictures withall its "children"
documents. That allows us to re-use pictures, and declare settings "globally".

For example, we do want to share aliases between documents. Or we might want
to share the GRG map that Looney made between documents.

A very neat feature of that architecture is that updating a setting
or a picture in the "root folder" will update it for *all its
children documents*, in one fell swoop. No need to manually edit
dozens of documents if we decide to change a logo or a name.

**Note**: if the same setting, or the same picture, is declared
in both the "document folder" and the "root folder", then the one
closest to the document will take precedence. That allows us to
"replace" pictures or settings on a per-document basis.

In addition to those three parts, there are also the global settings 
and the global media folder. Those are simply settings and pictures 
that are shared with *all* the documents.

**template.tex**

This file is the "blueprint" that is used to create PDFs.

It is thanks to it that files "look alike".

It is also the most complex part of the chain; it is
written in Latex, which is definitely not user-friendly.

However, the end-result is *amazing*, and, for that reason,
it is used world-wide to this day for an impressive amount
of application.

Several members of the //wing are already using it
to create and publish documents, so I'm not afraid
that no-one would be able to tweak the current template
should something happen to me.

\clearpage

### The build process, step by step

**Note**: this section is for information and reference only

Starting from a valid `source folder` with an `index.md` files:

1. Gather all media folders
2. Find the closest "template" folder
3. Find the `index.md` file
4. Gather all the settings, giving priority to the closest
4. Get all the files that are included in `index.md`, including
all the recursive includes in them
5. Search for `template.tex`
6. Get a title for the document
	* If it's not in the settings, use the folder name
7. Create the output folder if need be
8. Repeat for all paper sizes:
	1. Set the pictures (maximum) size
	2. If we're using multiple paper formats,
	and this one is not "A4", append the format
	to the output file (ex: "MyPDF_a5.pdf")
	2. Try to download the latest official version of this file
	2. If there is an official version of this file,
	and it hasn't changed since the last time we built it,
	stop the build here
	3. Process the text of the document:
		* Replaces aliases
		* Process the pictures
			* Include the pictures with the correct width
			* Check that all pictures that are in the media
			folders are used, warn the user if there are unused ones
		* Process the references
			* Gather all references in the documents
			* Replace them in the text by a nice link
			* Add a "References" section at the end of the document,
			linking to all references used throughout it
		* Process the includes
			* for every other file that is included in this one, restart at step 9.5
			and process them too
		* Final processing: final touch to the text
	4. Create the (modified) Markdown text and write it to a temporary directory
	5. Actually create the PDF
	6. Mark the PDF with:
		* EDLM version
		* Aggregated hexdigest of all the files (Markdown, template, pictures, settings, ..., 
		recursively for all includes) that have been used during the creation process,
		so if we build this file again in the future we can check if something has changed
		(see 9.4)
	
![Processing \label{processing}](https://www.planttext.com/plantuml/img/TLVRRXit47tdLn1wQEp24Q2xNHHftBef2iI0qHZjIm63tXr9XBZaWilL9ON_lOUNlScs7nplcI5dUEPmXlbSEM5TNIZ6d7IA-3THbFWdDrbTa7PyGvgiSDBeVpKTWv4nRNBYes-Fjtyz_iHljL2dxyGhKziCAwMbp1bx6d5HySfH-JHXR6rKJfQF7eJrkmwToWZ-npX-6izxogNecPyA3oIdu2YHvqYPZPdCfZeVbtepUiEudApSjZE-iCvSaNDIRyQdGZM1de0DqdWa75augeA7IrzFoNoUJMCVEpeE5lHZfvtl4iMHfqXURxzND9oVlujQoipLbYP32bxPfqFxordkvsnKDclPwBoapkauBlBW4ZxIqLuOOv2IN8lCeSvtNyA2o6k-PYmJDk_e_ALbvucE9SINS3uUzr1jW5YvsJfkrXtk0pvkgIMNIso5xz6pggcq4fmcfYqNIhLYhiO13h_-T7xLOIkSTp67WIDt9ZWfOtOmo1rTyODqMoxudkm9ygr0LURaFXPs51J8_vQuIaBnVq3ZA2x-WQ-9r23k1uIrqZdIu8z_HVv7xBwLsTPd989NPln5E_B7KqcfBbm9lQd51gayrx4g5I4Rn2l9-3kBtJmBFZgIjYJoKt3RQHplGY11PVPqoQNhv_EXQ9nvQSrUvc4v_aROkBuoIkOTsSvpLcrDhNA-8uhbg2k-CNvbu1o1yAUJ1J52M5_6HW2_cQ88gKWTnP4LETf3q1RbgcZbvp-Uqjch90L5ww24eItA0To5NJo7VAFCCuX9NEgrtDInYKKVd-JlTr_lN-cXrhxOwiI5FXbD_11EcKw8lT6vQkkFgOqj4C2KgJbU1HyKnkyIUQJS7qFu-7lI4h8AFWTnWhpG68r5pqnduC_a3aGwbRMgVAeNKgDzYjoVU2lsFgo37e8F2brm4mkUHKgZOa4h9m4jUVOlnpt-6LfzjaFRRcAkhIcQtXlRJRptoJvvUq7gL6yicBwzO53LndVsjczshex6VywWVEGv-Y8nRbeu-Amz55eLIpsBV_puO-ySgQyFq2aRY6XWcp68Se3CiNMp7GocV-Rchm4-Q_7P09-t-3pW_TmZ8Q7X9tghD4DXYEEFiS4m32dsh6-ZPssqR_AIkKNZInF2InVz1ZpBA4LSWpHtqZmI_cOt2enReJDYXsVYXSYZECLUI2MUST4WTEyNJXbCJOVj2pE-9luGyBI3Q5NxX9WqJgXYquXQuxHdRCPJDtoynwpdCP2EDyu7opDLvzGP5yduO4s6Q_aw-38veA-LjVCa7Bai85PUoU-Ts-fidtjXTxavwDRXEZdyMajq78pFrdA3rccqiqRnaMzQmN0mTaTsyQvb-QvbzQxb-btBZUyUyTv7SOL7NKz8BJnXpPHkeIaBHMc_PwmLVOlDMJfGYomIicoHPK9MBR9Ao7MBN2VafaLkNilVRzNE3FyPtW-6Ympjn-JDQosNwpM5vbWAjFbGpufVtCvZhxzTNF7RvHKUBEFBtXnvQ6uIxYaNjJC5vaE6nqMQfLjRwnttfVVpsbX_gT9hOutn8dY5kQ80bj1G_vRWLKCMZwkaLBoVCOcgFGqrwp-yRwR0mATFgIQ1cWX41nPBUExJ0wO1c7R0B02p3fW7ODu1Ym0i-Cz0OfputJei0x3iW5K0LXrmtKyrbY_yZa1uH-BdCrZ1Vrd-1m00)

\clearpage
