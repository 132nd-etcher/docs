---
title: OvGME
author:
    - //etcher
author-meta: //etcher
applies:
    - //wing
    - External organizations
title_pictures: //all_logos
subtitle: Operating Instructions for Mods and Skins Management
type: Operating Instructions
version: 0
published_date: unpublished
responsible: etcher
summary_of_changes:
    - nil
---

Introduction to OvGME
=====================

Extract from OvGME's homepage[^1]:

> OvGME is a free and open source standalone Mod Manager based on the idea
and concept of the old well known JSGME, it takes the GME acronym from
JSGME which stands for Generic Mod Enabler. The main purpose of OvGME is
to provide an easy way enable and disable mods with automatic backup
mechanism.

OvGME will eventually replace the Skinstaller for the installation and
updates of skins and mods within the 132^nd^ Virtual Wing.

This document is split in two parts:

-   The first part is intended for everyone, and will describe the
    procedures to use OvGME on a day-to-day basis.

-   The second part is intended for maintainers, i.e. the people
    responsible for updating mods and skins, and for keeping them up to
    date.

# OvGME for pilots

This part of the document describes the installation and basic setup of
OvGME, as well as the steps required to install and update the skins and
mods needed to take part in event organised by the 132^nd^ Virtual Wing.

Everyone, include mods/skins makers, should follow the steps described
below.

## OvGME installation

"Download" page of OvGME's website:

> [http://www.ovoid.org/ovgme/downl.htm](http://www.ovoid.org/ovgme/downl.htm)

Latest version as of 2017, May 13^th^: **1.7.1**

Simply run the setup to install OvGME on your system.

OvGME will install a shortcut in your start menu, and optionally on your
desktop if the option was selected.

## OvGME initial setup

OvGME concept: "Configuration"

> A configuration in OvGME is strongly linked to the folder in which the
> mods will be installed (for example, a DCS installation). There can be
> only one configuration pointing to any given destination folder.

OvGME concept: "Mods folder"

> The mods folder is the folder containing the mods that can be
> installed in the destination folder; it is the "source" for the mods.
> It is also the folder in which the mods will be downloaded when using
> the repository feature of OvGME. The mod folder can be shared by
> multiple configurations.

### OvGME configuration for DCS

On OvGME's main window, click the "New" button on the top-right:

![Create a new configuration](image8.png){width="8cm"}

In the pop-up window, fill in the fields "Configuration title",
"Configuration root folder", and "Configuration mods folder", then click
"Create".

!["New configuration" window](media/image9.png){width="8cm"}

### (optional) OpenBeta/OpenAlpha

If you have the OpenBeta and/or the OpenAlpha version(s) of DCS
installed, repeat step 3.2.1 OvGME configuration for DCS for each of
them.

Note that the "Configuration mods folder" **may** be identical for all
three versions, to ease the management of the (many) compatible mods.

### (JSGME users only) Transfer of mods from JSGME

If you are using JSGME, you will need to transfer the management of your
mods to OvGME.

#### Save the current JSGME profile

Just in case something goes wrong, make a backup of your currently
activated mods in JSGME. Open JSGME, and click the blue "Tasks..." menu
in the centre of the window:

![Save JsGME settings](image10.png){width="8cm"}

In the contextual menu that appears, click "Save mod profile...", then
save the resulting `*.mep` file somewhere on your system. That file is
a text file, that you can open with Notepad++ (or similar), containing
the list of the activated mods in your JSGME installation.

#### Uninstall all mods

Click the `<<` button, and confirm:

![Uninstall all JsGME mods](F:\DEV\EDLM\DOCS\OvGME\media\image11.png){width="8cm"}

#### Migrate your mods from JSGME to OvGME

Transfer all your mods from JSGME's mod folder to OvGME mod(s) folder
(defined in step 3.2.1 OvGME configuration for DCS as "Configuration
mods folder").

#### Re-install your mods

All your mods should now appear in OvGME's main window. With a clean DCS
installation, you may now install them again, using OvGME. In case you
forgot which one were activated, you can use the backup `*.mep` file
created during 3.2.3.1 Save the current JSGME profile, it is a simple text file listing installed mods by name).

### Add the 132^nd^ Virtual Wing repositories

This section describes how to add the repositories needed to download
and updates the mod.

OvGME concept: "Repository"

> A repository is a list of mods and skins, located on a web server.
Clients can subscribe to a repository in order to download the mods
and skins that it offers. Maintainers of a repository can then update
the mods and skins in a repository, propagating the updates to the
repository's clients.

Fire up OvGME, and go to "Mods", "Repositories", "Configure..."

![Configure repositories](image12.png){width="8cm"}

The following dialog opens:

![Repositories dialog](image13.png){width="8cm"}

Copy paste the following line in the "URL" field, then click "Add":

```
http://132virtualwing.org/files/ovgme/132nd
```

![Add the //wing repository](image14.png){width="8cm"}

The window will now look like this:

![Properly configured repositories dialog](image15.png){width="8cm"}

The repository is now added and ready to go!

## Download the mods and skins from the repositories

Open "Mods", "Repositories", "Query"

![Query the repositories for new/updated mods](image17.png){width="8cm"}

Click "Download all", and wait for the download to complete

![Download all updates from repository](image19.png){width="8cm"}

Click "Close".

**Due to a bug in OvGME, you will need to close OvGME and restart it
(all the downloaded mods will appear in the list twice).**

**Restart OvGME now.**

The mods and skins now appear in OvGME's main window

![Populated mods window](image20.png){width="8cm"}

## Install the mods and skins

### Mandatory and optional mods and skins

Mods and skins with a name starting with "MANDATORY" **MUST** be
installed before joining an event hosted by the 132^nd^ Virtual Wing.

Note: some "MANDATORY" mods are specific to an aircraft or a situation,
and must be installed only for the people concerned. For example:

*   "**MANDATORY FOR A-10C - 617th - 132nd VW NEW Navigation maps v.2**" must be installed for anyone who wants to fly the A-10C

*   "**MANDATORY FOR MISSION MAKERS - 132nd - DB, TACAN, SADL mod**" must be installed for anyone who wants to create/edit a mission.

Mods and skins that are offered as convenience or eye-candy only are
marked by the prefix "OPTIONAL". Installing those or not is left to the
pilot's discretion.

### Installing a mod

To install a mod, select it in the list, then click "Enable selected"

![Installing a mod](image21.png){width="8cm"}

You can also right click it, and select "Toggle"

![Installing a mod via right-click](image22.png){width="8cm"}

A mod that has been installed will be marked by a green arrow before its
name

![Installed mod with green arrow](image23.png){width="8cm"}

### Uninstalling a mod

To uninstall a mod, follow the steps in the previous section, but select
"Disable selected" instead.

### (Un)Installing multiple mods at once

To select multiple mods for (un)installation, you can use the usual
SHIFT/CTRL selection schemes:

-   Hold CTRL and click on a mod to add/remove it to/from the selection

-   Select a mod, then hold SHIFT a select another to add all the mods
    between them in the list to the selection

## Updating the mods and skins

Upon notification from CMD staff, mods and skins will have to be
updated.

For the sake of demonstration, let us assume there is a mod,
"dummymod", which is at version 0.0.1 on my system:

![Dummy mod](image24.png){width="8cm"}

CMD staff releases a NOTAM stating that pilots should update this very
mod via OvGME. Following the procedure in 3.3 Download the mods and
skins from the repositories, I update my local mods.

During the query, OvGME informs me that "dummymod" had been updated:

![Dummy mod has an update!](image25.png){width="8cm"}

I download the update, then re-start OvGME to get rid of the duplicates.
After the restart, "dummymod" has been updated to 0.0.2, which is good,
but it also has been disabled to allow for the update to take place.

![Dummy mod has been updated](image26.png){width="8cm"}

**Make sure to check all updated mods and re-enable them accordingly
after each query !**

## Updating DCS

**Note:** this is a *mandatory* procedure for when DCS needs updating. If you do not de-activate your mods before updating DCS, headaches will ensue.

When CMD issues a NOTAM to update DCS, the procedure es as follows:
1. Launch //ovgme
2. Take a snapshot of the currently activated mods TODO: add picture
3. De-activate *all* the mods
4. Update DCS
5. (optional) If specified in the NOTAM, query the //ovgme repository to get the latest versions of all mods
6. Re-activate the mods you had before using the snapshot

*Note*: using the "snapshot" feature of //ovgme is not mandatory; the only thing that matters is that all mods are removed before updating DCS.

# OvGME for maintainers

Maintainers are the ones responsible for creating and updating mods and skins.

In addition to //ovgme, you'll need access to the //wing's FTP as well as a working FTP client ([Filezilla](https://filezilla-project.org/)  will do nicely).

The FTP client is used to transfer files back and forth between your computer and the //wing's FTP.

## Getting started

The first thing to do will aways be to to pull the latest changes from the FTP to your local computer. Create a directory somewhere, and name it howerver you'd like. This directory does not need to be located on a SSD, and can grow to a few Gygabytes in size. In this tutorial, I will call that directory the `local root folder`.

In this directory, we will download the //wing's repositories, and work from there.

Fire up Filezilla and connect to the //wing's FTP.

On the left pane, navigate to the folder you have just created (it should be empty).

On the right pane, open the `ovmge` remote folder. In that remote folder, you should see two folders, `132nd` and `externals`, as well as two files, `132nd.xml` and `externals.xml` (some other things may be present, disregard them). Download those four items into your local folder.

Your setup is now ready for adding or updating mods.

## Updating the local root folder

It is paramount that your local root folder is up to date before you start working on it.

A good practice is to update it every time you start working on a mod, before you make any changes.

To update the local root folder, simply fire up Filezilla, and download everything again. Files that are identical may be safely skipped.

**Note:** for advanced users, there are many solutions that will keep your files in sync with the FTP at all times, acting somewhat like Google Drive or Dropbox will. For example, check out the Open Source [SyncAny](https://www.syncany.org/) or the ver handy [WinSCP](https://winscp.net/). If you would prefer to stick with Filezilla, here is [an interesting read](https://superuser.com/questions/935353/filezilla-how-to-synchronize-two-way-newest-file-wins).

## Create a new mod

### Create the source folder

To create a new mod, start by navigating to your local root folder.

Open up the repository in which you want the mod to live in (either `132nd` or `externals` at the time I'm writing this).

Create a folder and give it the name of your mod. This mod folder behaves exactly like in JsGME: any file added to it will end up being installed in the DCS installation of the end-users, mirrorring the fodlers structure.

Make sure to test your mod before you package them by installing them in your own DCS installation and making sure they work as intended !

### Package the mod

Using //ovmg (TODO: add pic and correct terms), create a package from your source folder. A package is simply a zip file that contains:

* Your mod's files;
* Metadata about your mod; when you create the package, //ovgme will ask you to fill in a few boxes, asking you information about your mod (author, version, etc...).

#### Metadata

The metadata about your mod includes the following:

* Version: version of the mod; this will be used by //ovgme to check if a new verison of the mod is available;
* Description: a free text describing the mod.

The version will end up in a `VERSION` file inside the ZIP, and the description in a `README` file.

The description of the mods is very important, because it will appear to the end-user when they select your mod in //ovgme. It may include: author/maintainer of the mod, remarks about installation, URL to the source of the mod (forum page, website, ...), changelog, etc...

The template I've been using so far is the following:

```
maintainer: [name of the person responsible for this mod (in case of issue)]
 
 OpenBeta: yes/no
 OpenAlpha: yes/no
 
 One-line description of the mod
```

When I create a new version, I simply add this line to the description:

```
20170714: etcher: updated skins for DeeJay, added skins for bilgatus and Chilts
```

Or, another example of description, for a mod that is a patch of two others:

```
This package contains a patch for the mod "132nd - DB, TACAN, SADL mod" when using "MANDATORY - 132nd - Helipads".
 
 IMPORTANT: you MUST install this patch AFTER the two mods mentionned above.
```
 
### Update the XML file

In //ovgme, you should now see your shiny new mod appear twice: once for the folder version, and once for the packaged (ZIP) version.

When you create/update the XML file, //ovgme will discard everything except ZIP files, so it's safe to have left-over mods in folder formats.

TODO: write the procedure with pictures to create the XML file

### Upload the results

You now have a modified local repository: your new mod(s), and a modified XML file.

All there is to do is upload them both on the FTP !

Overwrite the XML file and the ZIP files, and your mod should be available for download.

## Updating an existing mod

To update an existing mod, start as before by pulling the latest changes from the FTP to your local root folder.

Edit the mod you want to update, using the folder of the mod to change files and run your tests.

Once you are happy with the results, simply re-package your mod, giving it a new version (don't forget to update the changelog), and **overwrite the existing ZIP file**.

Update the XML file, and upload everything (packages (ZIP) and XML to the FTP.

That's it !

[^1]: http://www.ovoid.org/ovgme/index.htm
