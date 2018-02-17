### Intro: the build process

Before I can present you with examples, I need to explain a few basics 
about the build process I'm proposing.

#### The document folder

Every document lives in its own folder, and is composed of three parts:

![Document folder \label{doc_folder}](https://www.planttext.com/plantuml/img/ROzB2W8n343tEKNe0GfwWbcuzGnIsZW4-XdI51IPkrix3kF2RF9vZuHCLPreIn50MIFXfVYMA2lUImma05j6imE3hc8jJJpX2x37Rbmfi1iuVQel7GRtpMPXhqteP9Syc__iVB0L3bf9bVDidobkvyNV-kp7u1peOLCOU3Im0aoKG__j3G00)

##### **index.md**: the document ("md": "Markdown")

This file contains the actual text of the document.

It can also contains references to other Markdown files, in order
to "include" them, for example the //sop617 "include"
the //qr617.


##### **settings.yml**: the document's settings ("yml": "YAML")

This file contains the settings for the document, for example:
* aliases  
* paper size
* references
* title
* etc...

**aliases** are a neat way to create a placeholder for a "complicated", or 
rather long text.For example:

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
  //wing: 132^nd^ Virtual Wing
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

##### **media** is a folder that contains the images for this document.

If I want to include a picture that is in "media/picture1.png", all I need 
to do is type the following in my `index.md`:

```[My picture cool name](picture1.png)```

All the rest (layout & formatting) is automatically taken care of
for me.

Also, if I want to change that picture later, I do not need to edit
my document; overwriting the old picture with the new one will do!


#### The "root" folder

A "document folder" will "live" inside a "root folder" (it's just the 
directory that "contains" the "document folder").

![Root folder \label{root_folder}](https://www.planttext.com/plantuml/img/RLBB2i8m4BpdAq8_e505lVRWLV3WlOHaRGDvbCqMAj9_jwQfVMWkOMScExj3oa02gRE6CT9aWDyRuEWzyOSt2f2nwURPJI0uuaeZIFBupBW8l9t05-FZcPLNK5giwCf-W2IAGZqQPSRNlZWUdCfRLsT_o5DnfcOX1xRG0OYqg_EdDRDHDMARCUvWMoC8GbHGggf4xwUP-PoWtpnOUwVE5oyx-zbx0g8y-0ubhDl-fB6FOJ5ljQGEeTWcySCVjlomMs4VIa3v3MLHQQUWpwsAabYa3GTMWbFZLtW3)

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

Finally, this structure can be repeated *ad nauseam* if we need to:

![Nested root folders \label{nested}](https://www.planttext.com/plantuml/img/VPBDYiCW58NtFeNa0KArqDbsCTk1MNHVHE-aWZ_1t41ByTrhJKAQA9DDSk_vv1mFEGye0exM488Q3T3B3MZm7kcVDme28TERDhyYW4EgT029FZmQAWRQvoMZJqBJiw0_eBJ8kdr_BN96TF9eZEyyEtAdsjvrJKKyiI-yhM8agpm0edPT-x0cMwIPRTp_2Se_azJ3yfLOFNijSGnmsCOjzEDMZxkBLPBp8iu5R6y4mf0HdAVhBDV2BKoBSDySgWMPNRwz7EsxfMannV5ZaB2tgBUqeuecMDbKmV2IYPNh5Qq5UKsx2gcTWdjhLSRoi6iWaaZEu5JwtLy0)

\clearpage

#### The build process, step by step

**Note**: this section is for information and reference only

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
	
![Processing \label{processing}](https://www.planttext.com/plantuml/img/TLVRRkCs47tdLmpyq4sAh03VZJvirsswHO4D47I3zgM0GKiZcx142XJbooxoxnrUH4cEumV7EdD83WyFPvJFjU7QD6N1c16cGFZ6ouh-P2fjIfG6TYXHSoEK_4_YsGKPaof367rxMV_zyWki9Iyktn5grUYKHWgDgL7wCW9UGssmsemPorMHeORHCzTsrY6fyk0F1lHfcK-O2TuBRqeB198Z2ifpLAYT6aydCaigkHlT22x6IxFlWg-i2zTeZ92xv58MxK8RmWPfl21jcHki7SE4fqq8NsVJnXE3vy60_jfXviSWiTV9YzURxuqCr_llLgr4QXgDuw44R-AJOVprAlThDMgTHZKwbf0PdfCoSnJt4BRsoXWZAucSfuRE-V6B6-1rpNB6KgwpJivVepeRF5Tale13alHGgGZHOhSteF8Ejmk-x36A2uAcekVHjcYmqe8q3Kfhu4KHpLmd3dPVVnaxwhJdnbBKQK04enofKEf00N701pW9imSEHzGNiczDKgL67Ft1Zfm3uHz1LuaNy2_9EFA3Vu8SiHYi-u6MrS8ObAGVVANyppJxNgHxcn5th5JPYtQ6bqk5uLoWu7BNy1sbictygTH8sT1w5IfxPsasgu9TdPBMoBEBenqaRU-EKuA5Ek8z2DFFvqFPag7IwYWoDvn-qx9-VAqAaNLY6wjPlLTDaS41qHz7KyDEsP5ESrg8VXfH8aDQrXvZQu3VLLcwL8JqvaZBZCg3ynPcHHdjPnysOUzri4A1kNF2CERjGDgvMQo6i2lKbeG9MifSx1fVn3p79ld7uzUdDtvef3tiuW9SNfH4EBbTXXtIt5Iv6cstAPKkQG5LXUBuu3XqC7OMhoDcTXlShdz4ASXMZdFY5x8N5KQbgMQ6FS0MpGbHXcEjQvlgdP1KFdbcTxpdHxki8Jyu3Xrq2SeVUEebzOubMG4vUScgVv_qz6TKwjC3bUrspLohigszljpuUn_Yuzi3GgMwCM1oUy3WL5lkz3OtlNP7ovynSZxbEVeYgDr4s75o2xbInKBDWeyVV-xj8zJr0JfX0nCDObD6fXmWCvgwdOu2gh_dzjS0dqPyEi1d4Pyvl9-x5yGL_21l7Nee1NpxOspG35sAlUXjzAgCzaFMCcigVA53MEjIlI6TXRSYNOFGTq8_ulPcjmxqKr5bf1cs22NFl3dvaOk2R-cYaT4jp-tIXTeAEp2cVvqO9_0d9xOUh5Z7ruXnu4s8HuSPwr7VYKIR1DhKqzf-rNKZIve6qioJ1dQoyLc8pnDurYgb2ndNYvnvu2mIeA9MDSOgS0PHabEX5jyxvY8mbzriJrmVCdMIaRCCd5K2lpM2YWvrq1XSKVLKqcXLmCZMBHSuANr0FNytidWtidmtih9bmbzmxoBtzjPpJ8J7h6t74Pem9tPydhBexeZDM4Wx8lE0B2Ao2CWo8ik0h2AoUkjgEp2s0lleNWiKy9IgYihQbx1Cv3cwcbTngjxkf6guMyzy2L_F7s2zUA3taEI-rnwUsmj2rmzuOrH9PJ-bTuRG8lUwaGUm9shRiDBsheINY9ow1eUQsaL1O4NkkAhALcFQsATFGLZttG4J1qmwOEg0QGVC733hWBa3vXsmSC2Y0vOEM7R0oW4h3xWNDlfyfZpfVuF_0G00)

\clearpage
