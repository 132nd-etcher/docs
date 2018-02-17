The settings file is a simple text file, named `settings.yml`, that lives either next to `index.md`,
or in the parent directory.

Note that the `settings.yml` in the parent directory will be "shared" by all the documents next to it,
which is very useful for what we're about to talk about.

If there are both a "parent" `settings.yml` and another one next to `index.md`, and they define
different values for the same setting, the closest one (to `index.md`) will take precedence.

Here is an example of a `settings.yml` file[^alias_space]:

```  
papersize:
  - a4
  
aliases:
  // wing: 132^nd^ Virtual Wing
  // etcher: "132nd-etcher"
  // all_logos: "[logo617th.png,logo696th.png,logo176th.png,logo23rd.png,logo259th.png,logo765th.png]"
  // 617: 617^th^ DAMBUSTERS
  
references:
  // ttp1: "132-TTP-1 CAS Manual, https://www.dropbox.com/..."
  // ttp1a: "132-TTP-1-A CAS Formats, https://www.dropbox.com/..."
  // geospins: "Special Instructions(SPINS) Georgian Airspace, https://www.dropbox.com/..."
  // multi_instr: "Multiplayer Instructions - External, https://www.dropbox.com/..."
  // freqs: "132nd Operational Frequencies, http://132virtualwing.org/index.php/page/freqlist"
  // ato_manual: "ATO Manual, http://132virtualwing.org/index.php/page/ato_manual"
  // charts: "Ground and Airport Charts, http://www.ariescon.com/DCS_GND_VAD_Charts_v36_030513x.zip"
  
papersize:
  - a4
```

### Papersize

Allow me to start with the simplest.

The `papersize` settings is simply a list of formats ("A3", "A4", "A5", ...).

Here's a list of supported formats:

```
letter, ledger, tabloid, legal, folio, and executive sizes from the North American paper standard;
sizes A0 – A10, B0 – B10, and C0 – C10 from the A, B, and C series of the ISO-216 standard;
sizes RA0 – RA4 and SRA0 – SRA4 from the RA and SRA series of ISO-217 paper standard;
sizes C6/C5, DL, and E4 from ISO-269 standard envelope sizes;
envelope 9 – envelope 14 sizes from the American postal standard;
sizes G5 and E5 from the Swedish SIS-014711 standard. These are used for Swedish theses;
size CD for CD covers;
size S3 – S6, S8, SM, and SW for screen sizes. These sizes are useful for presentations.
S3 – S6 and S8 have an aspect ratio of 4:3. S3 is 300pt wide, S4 is 400pt wide, and so on.
S6 is almost as wide as a A4 paper. SM and SW are for medium and wide screens;
they have the same height as S6;
```

If a document has only one format, then the output will always be `title.pdf`.

If the document has many formats, the output will be:

Table: Paper formats output

---------------------------
  Format     Output
----------  ---------------
 A4			 title.pdf
 
 A3			 title_a3.pdf
 
 A5          title_a5.pdf
---------------------------

This setting is just a convenient way to output the same document multiple time,
for example to make a version that can more easily be converted to a kneeboard
(hint, hint).


### Aliases

Aliases are a simple way to *replace* text in the document.

For example: [^alias_space]

```
aliases:
	- // etcher: "132nd-etcher"
	- //jf: "J-TAC/FAC(A)"
```

This would allow me to type `// jf`[^alias_space] or `// etcher`[^alias_space] in my document,
and have that replaced by the corresponding text.

It also help us to have a more "uniform" rendering of the names & conventions
within the //wing.

### References

References work exactly like aliases, with one added benefits: all references used in a document
are neatly assembled in a "References list" at the beginning of the document.

Here's one for the sake of the example: //ttp1 (I just typed `// ttp1`[^alias_space] in my document).

[^alias_space]: I had to include a space after each `//` in the example in order
to prevent automatic processing of the aliases/references.