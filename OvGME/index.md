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
save the resulting "\*.mep" file somewhere on your system. That file is
a text file, that you can open with Notepad++ (or similar), containing
the list of the activated mods in your JSGME installation.

#### Uninstall all mods

Click the ```<<<``` button, and confirm:

![Uninstall all JsGME mods](F:\DEV\EDLM\DOCS\OvGME\media\image11.png){width="8cm"}

#### Migrate your mods from JSGME to OvGME

Transfer all your mods from JSGME's mod folder to OvGME mod(s) folder
(defined in step 3.2.1 OvGME configuration for DCS as "Configuration
mods folder").

#### Re-install your mods

All your mods should now appear in OvGME's main window. With a clean DCS
installation, you may now install them again, using OvGME. In case you
forgot which one were activated, you can use the backup "\*.mep" file
created during 3.2.3.1 Save the current JSGME profile).

### Add the 132^nd^ Virtual Wing repositories

This section describes how to add the repositories needed to download
and updates the mod.

OvGME concept: "Repository"

> A repository is a list of mods and skins, located on a web server.
> Clients can subscribe to a repository in order to download the mods
> and skins that it offers. Maintainers of a repository can then update
> the mods and skins in a repository, propagating the updates to the
> repository's clients.

Fire up OvGME, and go to "Mods", "Repositories", "Configure..."

![Configure repositories](image12.png){width="8cm"}

The following dialog opens:

![Repositories dialog](image13.png){width="8cm"}

Copy paste the following line in the "URL" field, then click "Add":

> http://132virtualwing.org/files/ovgme/132nd

![Add the //wing repository](image14.png){width="8cm"}

The window will now look like this:

![Properly configured repositories dialog](image15.png){width="8cm"}

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

TODO

[^1]: http://www.ovoid.org/ovgme/index.htm
