### The pros

This section explains why I'm making this proposal in the first place.

#### Centralized repository

All documents live in one repository, that is itself 
hosted on Github.

The advantages are plenty:

* Automated recording of all changes
* Automated and constant backup
* The library is accessible to all; everyone can suggest 
a change or add content
* review process greatly facilitated: changes are incremental, 
and their authors are clearly displayed; discussions about 
those changes are centralized around the pull request; merging 
the changes once they are ready is a one-click operation;
* concurrent edition: many people can work on the same 
document at the same time, sharing their progress along 
the way (conflicts are handled on a per-line basis)
* ease of access: editing a document or suggesting a 
change is available in all web browsers
* **internal links and bibliography**: a document may 
include another, which may in turn include another, 
which may in turn ...; this makes it very easy to 
propagate changes in all "sub-documents" to their "parent" 
document (for example, a procedure that is common to 
the whole //wing might be outlined in a dedicated document, 
which will be "included" in most TRPs; updating the 
sub-document would then upgrade all associated TRPs.
A silly example for that would be the brevity: we
could have a main "brevity" document, and include it
at the end of all the SOPs. Updating the main
brevity would then automatically update all the SOPs); 
* media files like pictures, logos, maps, etc. are shared 
across all documents; updating them propagates to 
all documents using them

#### Automation

This is one of the biggest pro in my book. The starting point is a 
raw text file, editable from anyone that has access to the Internet, 
and, from there, PDF documents are automatically created and published. 
Even a full-fledged website if we want to !

The build process is triggered every time a file changes on Github. 
That means we get to see what the PDF would be like every time 
someone creates a commit. This is of course very desirable when we 
are actually publishing the document, but what of the "draft" versions?

**Every** commit creates PDF. Those PDF are hosted on Appveyor,
and a link to them is supplied on the Pull Request page automatically.
We can then review the output, and discuss about it.

The common way to
do this is to create a branch and make a "Pull Request" from it 
on Github, then push changes to it,
discuss the changes, change so more, discuss some more, etc. until
everyone is happy with the changes.

**Commits that happen on the "master" branch**: Once everyone is happy 
with the changes, the branch we used for the Pull Request
is "merged" into a special branch, called "master", then deleted.
The "master" branch contains
the official documentation. Every commit made on master is 
automatically built and automatically published for the world to 
see as PDF files. The link to those PDFs files do no change.
We can have a link on our "document" page on the website, and that
link will **always** point to the latest, official version of the document.

Cfr. Figure \ref{publish} for a diagram of the publishing workflow.

![Publishing workflow \label{publish}](https://www.planttext.com/plantuml/img/RLAxRiCm3Dpv5OJt34dQZa6A1kqKe5ExTA4bsHOYIuOU2OAY_rwQTjt5MdIyeqJof6FA57Ff7G2rncUidaiEFMMZCMKpL52IKPGCLcVoXTpCWdAXQCHlG5wQCjMIz6PpLsgCPWZ9vX3lN_vCV2HY7Schha9As7Rmyrzl6Axc7g8eT0LeWjESlmZ83Tg6L4vJ2aTpsSOwBlb-UXLXqCrsdTwjq_jr-c6TVboddyPH9ZEgxNxdDNvODfID-hI-nPkfsGSZsJDU9Z-PmOMxI5eW0B-6kc3r4lhUPWmUUp5FSfIGC6susHn67w7j1B9nT6Kazapmy7Vhj2tY4XwMZiHJrfSEer6PV3lEUWggzDplwBn17svSYwoZsarJHO3vc5p9uT5upJ_g5m00)

\clearpage

**Note:** using the FTP to host documents is my current idea of the 
implementation, but can be changed very easily. I like the FTP idea 
because it means that the same document will always have the same 
link pointing to it, even between versions, which is very convenient 
for writing briefings, or the documents page of our website.

**Note**: for those of us who worked with *EMFT*, forget about develop
and the like. The flow I'm pushing for in this case is *much* simpler:
"master" is the official branch, everything else is just a
"proposed change". The Pull Request on Github is a very neat way to "talk"
about the changes before they can make their way into "master".
See: [Github flow vs Gitflow](https://lucamezzalira.com/2014/03/10/git-flow-vs-github-flow/)

Automation also gives us a lot of flexibility. Let us say we decide 
to change the font we use for the documentation, and examine the 
two following scenarios:

* First scenario, we're using Word. We need to open each document, 
change the style to use the new font, and hope that all the other 
styles used in the document depend on the main style. We visually 
check for that, and hope we won't miss a line. This will take a 
little bit of time (pun intended) and is very error-prone.
* Second scenario, we're using Markdown. We pull the repo (one click), 
change one line (10 seconds), then push the repo back (one click). 
This change is absolute over the entire document library, every 
single character is guaranteed to have been updated.

This stands not only for the font, but for pretty much everything 
else too. Another use case: the application I'm writing lets us 
define "aliases" for recurrent terms. For example, the words 
"132^nd^ Virtual Wing" can be abbreviated to `// wing` in the 
Markdown text file (which is what I'm actually using in this very 
document). Those aliases can be defined globally and for each 
document in a settings files. If we ever decide to become the 
131^st^ Virtual Wing, all it takes to update *all* the documents 
in the library is to change the alias *once* in the root 
settings file (this is a silly example of course, but you get 
the gist). Another advantage is that we won't have a mix of 
//wing, 132nd Virtual Wing, 132nd vWing, 132 Wing, 132nd, etc.,
so it increases the overall consistency of our documentation.

The same goes for pictures: imagine we decide to include the 
GRG made by Looney (respect, sir) into the //sop617. We drop 
the file "dush_grg.png" into a "media" folder next to our 
markdown, and simply type `[Dusheti GRG](dush_grg.png)` 
in our Markdown text. Now every time Looney 
updates his GRG, all there is to do is drop the new file in place 
of the old one, and commit the change. No worries about resizing, 
aligning, formatting, publishing. Pull, change, commit, push, and 
grab a coffee; 2 minutes top, coffee included, worry free.

Let's take the example above a tad further. Imagine the //765 
decides to include the GRG too. They move the "dush_grg.png" file 
into the "media" folder of the //wing, making it available for 
every document in the library, and include it in their TRP too. 
Now, whenever anyone updates "dush_grg.png" in the root media 
folder, it automatically gets updated in every document that 
uses it. How cool is that ? =)

This integrated and automated publication process also gives us 
a lot of information about everything that is going on, at any 
given time. For example, I could see who modified a specific 
line in a specific document. I could also comment directly on 
*that specific line* and start a discussion about it. I could 
revert a specific set of changes, if it turns out they're not 
as good as we thought. Since every commit is independently 
built, and Git branches are cheap, multiple people can work 
at the same time on different chapters of the same document, 
without ever colliding with each other, and have a immediate 
snapshot of their work every time they push it. Once finished, 
integrating the changeset back into the "master" 
branch is as simple as a click of the mouse.

A side effect of this system is that absolutely every change 
ever pushed on Github are recorded. Every little one of them 
can be retrieved, analyzed, and reverted if we want to. Which 
is, essentially, **free backup**.

Finally, hosting the documentation on Github gives everyone 
access to it. Anyone can jump in at any given point, and 
suggest a change, fix a typo, etc. Owners and maintainers 
are responsible for accepting or rejecting those changes, 
but virtually anyone willing to create a Github account 
can turn into a contributor.

**Note:** if it turns out that having our work publicly 
available is a show stopper for some of us, please note 
that Bitbucket offers the same kind of functionality for 
an unlimited number of private repositories. I'm a strong 
advocate of going public, though.

See Figure \ref{basic_workflow} for a conceptualized workflow
of how to edit the documents.

#### Unified format

All markdown documents are transformed into a PDF with a 
master template. This means that:

* all documents will have the same layout and general 
format, giving them a distinct //wing look and feel;
* updating the template will reflect the changes on all 
documents (ex: title page format, heading size, paragraph 
spacing, bullet lists format, etc.);
* content and format are decoupled;
* metadata like table of content, table of figures, table 
of tables (yes), heading numbers, etc. are automatically 
generated for all documents, with links and numbering.

Having that master template means that we can control
how our documentation will look, without actually *editing*
the documentation itself.

Let's say our documents are written, nice and cosy. Then one day
I wonder, how would they look with a little more spacing between
the paragraphs? How about adding the current chapter in the header?
And what if I wanted all pictures to be rotated 90° clockwise?

Well, for all those (silly) examples, it would be as simple as:

1. Pull the repo
2. Create a test branch
3. Edit and commit the template
4. Push back

That would give me **all** the documents re-built following my new
template. Neat!

Now I can check them out, see how they look. If I like them more
that way, I can then open a Pull Request and ask everyone else
to take a look (one click).

If everyone likes my changes, we can make them happen officially
by merging back into "master" (still one click).

#### Professional typesetting

In this implementation, I'm using [Latex](https://www.latex-project.org/) to
render the PDFs. Latex is *the* most used *de facto* standard
for uncountable thesis, essays, scientific papers, resumes, etc.
for decades.

Latex basically takes care of everything that is style-related in the
document.

It will try and make the most of all pages, subtly adjusting size, 
positions, spacing, etc .. to try and make the best output as possible.

Have a look at this very document, and try to find defects in the layout.
If you manage to find one that is not purely opinionated, it's probably my fault,
report it and I'll fix it =)

Since it's been in production for so long, the amount of community-driven
(read: free) packages is staggering. The possibilities are truly end-less.
The amount of customization that we can get out of it is staggering.
Just keeping up-to-date and reading about would be more than a full-time job.

**Also, many members of the //wing are already using Latex.** I'm not
proposing some obscure, hacky back-water little program. When I'm 
unavailable and there is an issue with Latex, someone will be able
to take a look at it and hopefully fix it.

For example, this has been done in latex:

[http://wpage.unina.it/agodemar/DSV-DQV/DSV-DQV_Quaderno_1.pdf](http://wpage.unina.it/agodemar/DSV-DQV/DSV-DQV_Quaderno_1.pdf)

And this:

[https://tug.org/texshowcase/cheat.pdf](https://tug.org/texshowcase/cheat.pdf)

Or this:

[https://tug.org/texshowcase/tabela_periodica.pdf](https://tug.org/texshowcase/tabela_periodica.pdf)

Even maps:

[https://tug.org/texshowcase/maps.pdf](https://tug.org/texshowcase/maps.pdf)

3D calculus?:

[https://tug.org/texshowcase/lee-wilczynski.pdf](https://tug.org/texshowcase/lee-wilczynski.pdf)

Some icons?:

[https://tug.org/texshowcase/cubs_v_cards_8sep98.pdf](https://tug.org/texshowcase/cubs_v_cards_8sep98.pdf)

Graphs?:

[https://tug.org/texshowcase/diagram.pdf](https://tug.org/texshowcase/diagram.pdf)

Posters?

[https://tug.org/texshowcase/program_sample.pdf](https://tug.org/texshowcase/program_sample.pdf)

Music sheets?:

[https://tug.org/texshowcase/kv315f.pdf](https://tug.org/texshowcase/kv315f.pdf)

Latex is an incredibly flexible language. We can give it raw data (for example, the areas, ranges
and altitude for a FLIP), and it'll make consistently beautifully rendered PDFs 

#### Extensibility

Once the content has been created (i.e.: the Markdown 
texts are written), we can output in a lot of different 
formats. This means that if, at any given point in the 
future, we find that we would need to publish books with 
our documentation on the Google Play Store and its Apple 
counter-part, it would take us about 5 minutes of manual 
work. The *content* is there already, all we would need 
to do is add the *output* to the pipeline.

This is of course a silly example, but I think 
extensibility is still a very strong pro.

#### Flexibility

**Disclaimer**: This section talks about possibilities
in the future, not things that are actually
implemented and working already

Now imagine that, in a couple months, we have our actually
documentation resting nice and safe in a repository.

Anything we decide to do with it, we can. The content is
there. The content is text only. The content is structured
in a way that a machine can understand.

All sorts of things become possible. We can parse that content,
shape it any way we'd like, and feed it to another program
that will, I don't know, make a website out of our documentation.
Or installs automatically up-to-date kneeboards in everyone cockpit.

Having our documents written in a way that is *machine-readable*
opens up a lot of possibilities.