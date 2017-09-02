---
title: OvGME
author:
    - //etcher
author-meta: //etcher
header_text: OvGME
applies:
    - //wing
    - External organizations
title_pictures: //all_logos
subtitle: Operating Instructions for Mods and Skins Management
type: Operating Instructions
version: 0
published_date: unpublished
responsible: //etcher
audience: pilots
summary_of_changes:
    - nil
references:
    - nil
    - nil
---

Introduction to OvGME
=====================

TODO: talk about snapshots during DCS update

Extract from OvGME's homepage: [^1][]

> OvGME is a free and open source standalone Mod Manager based on the idea
> and concept of the old well known JSGME, it takes the GME acronym from
> JSGME which stands for Generic Mod Enabler. The main purpose of OvGME is
> to provide an easy way enable and disable mods with automatic backup
> mechanism.

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

Latest version as of 2017, September 1^st^: **1.7.3**

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

![Create a new configuration](image8.png)

In the pop-up window, fill in the fields "Configuration title",
"Configuration root folder", and "Configuration mods folder", then click
"Create".

!["New configuration" window](media/image9.png)

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

![Save JsGME settings](image10.png)

In the contextual menu that appears, click "Save mod profile...", then
save the resulting `*.mep` file somewhere on your system. That file is
a text file, that you can open with Notepad++ (or similar), containing
the list of the activated mods in your JSGME installation.

#### Uninstall all mods

Click the `<<` button, and confirm:

![Uninstall all JsGME mods](image11.png)

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
> Clients can subscribe to a repository in order to download the mods
> and skins that it offers. Maintainers of a repository can then update
> the mods and skins in a repository, propagating the updates to the
> repository's clients.

Fire up OvGME, and go to "Mods", "Repositories", "Configure..."

![Configure repositories](image12.png)

The following dialog opens:

![Repositories dialog](image13.png)

Copy paste the following line in the "URL" field, then click "Add":

```
http://132virtualwing.org/files/ovgme/132nd
```

![Add the //wing repository](image14.png)

The window will now look like this:

![Properly configured repositories dialog](image15.png)

The repository is now added and ready to go!

## Download the mods and skins from the repositories

Open "Mods", "Repositories", "Query"

![Query the repositories for new/updated mods](image17.png)

Click "Download all", and wait for the download to complete

![Download all updates from repository](image19.png)

Click "Close".

**Due to a bug in OvGME, you will need to close OvGME and restart it
(all the downloaded mods will appear in the list twice).**

**Restart OvGME now.**

The mods and skins now appear in OvGME's main window

![Populated mods window](image20.png)

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

![Installing a mod](image21.png)

You can also right click it, and select "Toggle"

![Installing a mod via right-click](image22.png)

A mod that has been installed will be marked by a green arrow before its
name

![Installed mod with green arrow](image23.png)

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

![Dummy mod](image24.png)

CMD staff releases a NOTAM stating that pilots should update this very
mod via OvGME. Following the procedure in 3.3 Download the mods and
skins from the repositories, I update my local mods.

During the query, OvGME informs me that "dummymod" had been updated:

![Dummy mod has an update!](image25.png)

I download the update, then re-start OvGME to get rid of the duplicates.
After the restart, "dummymod" has been updated to 0.0.2, which is good,
but it also has been disabled to allow for the update to take place.

![Dummy mod has been updated](image26.png)

**Make sure to check all updated mods and re-enable them accordingly
after each query !**

## Updating DCS

**Note:** this is a *mandatory* procedure for when DCS needs updating. If you do not de-activate your mods before updating DCS, headaches will ensue.

When CMD issues a NOTAM to update DCS, the procedure is as follows:

1. Launch //ovgme
2. Create a profile of the currently activated mods if you don't have one yet
3. De-activate *all* the mods
4. Update DCS
5. (optional) If specified in the NOTAM, query the //ovgme repository to get the latest versions of all mods
6. Re-activate the mods you had before using the profile created in step 2

![Create a profile](profile_create.png)

![Name profile](profile_name.png)

![Activate profile](profile_activate.png)

*Note*: using the "profile" feature of //ovgme is not mandatory; the only thing that matters is that all mods are removed before updating DCS.

# OvGME for maintainers

Maintainers are the ones responsible for creating and updating mods and skins.

In addition to //ovgme, you'll need access to the //wing's FTP as well as a working FTP client.

The FTP client is used to transfer files back and forth between your computer and the //wing's FTP.

I will use WinSCP (because it has a nice synchronization feature), but you can use pretty much any FTP client software.

[Click here to obtain a copy of WinSCP](https://winscp.net/eng/download.php).

## Initial setup

### Create local root folder

Create a directory somewhere, and name it however you'd like. This directory does not need to be located on a SSD, and can grow to a few Gigabytes in size.

In this tutorial, I will call that directory the `local root folder`.

![Empty local root folder](local_root_folder.png)

### Setup WinSCP

Fire up WinSCP.

![WinSCP initial screen](winscp.png)

Click the `New` button, and create the initial configuration.

![WinSCP initial configuration](winscp_create_config.png)

Click the `Save` button (check `Save password` if you want to, it's fine).

Select the //wing's FTP in the list, and click `Login``.

A scary SSH window will open, because WinSCP does not yet know the SSH key of the //wing's server. Just click `Yes`.

![WinSCP SSH confirmation](winscp_ssh.png)

On the left pane, navigate to your `local root folder`.

On the right pane, click the combo menu and select `root`.

![WinSCP navigate, 1](winscp_navigate.png)

Navigate to the `/var/www/132web/files/ovgme` folder.

![WinSCP navigate, 2](winscp_navigate2.png)

Save your session; that way, the next time you connect, WinSCP will start in those folders.

![WinSCP save session](winscp_save_session.png)

### Pull changes from the FTP

The first thing to do will aways be to to pull the latest changes from the FTP to your local computer.

Connect to the //wing's FTP using WinSCP, and activate `Synchronized browsing` (`CTRL+ALT+B`); this is something you'll amost always want to do when starting WinSCP.

Next, we'll need to mirror the content of the FTP in your `local root folder`.

Open the `Synchronize` dialog of WinSCP (`CTRL+S`).

![WinSCP synchronize](winscp_sync.png)

Settings:

* Target: Local (we want to transfer from the server **to** your `local root folder`)
* Mode: Synchronize file
* Synchronization options:
  * Delete: checked (remove files that are no longer present on the FTP)
  * Existing files only: unchecked (we want to pull newer files)
  * Preview changes: checked (we are not crazy yet)
* Comparison criteria: both checked

![WinSCP synchronization parameters](winscp_sync_params.png)

Click `Ok`, and make sure everything makes sense in the next dialog.

![WinSCP synchronization checklist](winscp_sync_checklist.png)

Click `Ok` to confirm, and go grab a coffee (this will be faster next time).

### Setup //ovgme

We will need to create a `config` in //ovgme for each repository we're going to manage (`132nd` and `externals` at the time I'm writing this).

Fire up //ovgme, and click the `New` button.

![//ovgme new configuration](image8.png)

* Configuration title: `132nd`, `externals`, ...;
* Configuration root folder: doesn't matter, a random test folder will do (I create a `test` folder in my `local root folder` for testing purposes);
* Configuration mods folder: this is the most important one; point to the *sub-directory* of your `local root folder` that contains the mods for this repository (in my example, `132nd`).

![//ovgme repository initial config](root_folder_config.png)

 Click `Ok`. You should now see all mods that are contained in the repository (`132nd` in the example) **twice**.

 * "folder": the mod in its raw form, following the JsGME format. That is where you can make changes to the mod;
 * "zip": this is a compressed version of the "folder" form, created by //ovgme *from* the "folder" (more on that later).

![Repository view](ovgme_repo_view.png)

## Create a new mod

### Create the source folder

To create a new mod, start by navigating to your `local root folder`.

Open up the repository in which you want the mod to live in (either `132nd` or `externals` at the time I'm writing this).

Create a folder and give it the name of your mod. This mod folder behaves exactly like in JsGME: any file added to it will end up being installed in the DCS installation of the end-users, mirroring the folders structure.

Make sure to test your mod before you package them by installing them in your own DCS installation and making sure they work as intended !

Your mod should appear in //ovgme (make sure you selected the correct `config`).

![New mod](ovgme_new_mod.png)

#### Naming your mod

Currently, the convention is to use one of the following prefix:

* MANDATORY: denotes a mod that *everyone must install* to join the server;
* OPTIONAL: denotes a mod that people may *choose* to install (if applicable, please add the name of the squadron the mod is targeting, for sorting purposes).

Make sure to include the prefix in the `source folder` name, since it will be the name of your mod in the end !

### Package the mod

Once you're happy with your mod, it's time to distribute it.

In //ovgme, right click your new mod, and select `Make mod archive`.

![Make mod archive](ovgme_create_mod_archive.png)

Create the `metadata` for your mod, then click the `Make` button.

#### Mods' metadata

The metadata about your mod includes the following:

* Version: version of the mod; this will be used by //ovgme to check if a new version of the mod is available;
* Description: a free text describing the mod.

The version will end up in a `VERSION` file inside the ZIP, and the description in a `README` file.

The version is very, very important: //ovgme will use it to detect new version of your mods, allowing end-users to update their mods.

The description of the mods is very important too, because it will appear to the end-user when they select your mod in //ovgme. It may include: author/maintainer of the mod, remarks about installation, URL to the source of the mod (forum page, website, ...), changelog, etc...

The template I've been using so far is the following:

```
maintainer: [name of the person responsible for this mod (in case of issues/questions)]

 OpenBeta: yes/no
 OpenAlpha: yes/no

 One-line description of the mod
```

When I create a new version, I simply add this line to the description:

```
20170714: etcher: updated skins for DeeJay, added skins for Bilgatus and Chilts
```

Or, another example of description, for a mod that is a patch of two others:

```
This package contains a patch for the mod "132nd - DB, TACAN, SADL mod" when using "MANDATORY - 132nd - Helipads".

 IMPORTANT: you MUST install this patch AFTER the two mods mentioned above.
```

### Update the XML file

In //ovgme, you should now see your shiny new mod appear twice: once for the folder version, and once for the packaged (ZIP) version.

![Packaged mod](packaged_mod.png)

The "XML" file is a list of all the mods that are available to download from a repository (the `132nd` repository for example). It is created automatically by //ovgme, using your current `config`.

**Note**: when you create/update the XML file, //ovgme will discard everything except "zip" mods, so it's safe to have left-over mods in "folder" formats.

To update the "XML", click `Mods`, `Repositories`, `Make XML source...`

![Make XML source](make_xml_source.png)

In the `Download link base URL`, copy paste the following:

![Finished XML source](xml_made.png)

```http://132virtualwing.org/files/ovgme/REPOSITORY_NAME```

Replace `REPOSITORY_NAME` by the name of the repository, for example `132nd` (the current repositories are: `132nd`, `externals`).

Click `Generate XML`, then `Save as XML...`. Navigate to your `local root folder`, and **overwrite** the old "XML" file.

### Upload the results

You now have a modified local repository: your new mod(s), and a modified XML file.

All there is to do is upload them both on the FTP !

Fire up WinSCP, and open the `Synchronize` dialog (`CTRL+S`).

This time, the target should be `remote` (all other options similar as what we did for pulling the files, cfr. "Pull changes from the FTP").

Let WinSCP analyze the changes, and make sure the preview makes sense before going ahead.

![Upload preview](upload_preview.png)

Once the upload is done, your new mod should be available for download!

## Updating an existing mod

To update an existing mod, start as before by pulling the latest changes from the FTP to your local root folder.

Edit the mod you want to update, using the folder of the mod to change files and run your tests.

Once you are happy with the results, simply re-package your mod, giving it a new version (don't forget to update the changelog), and **overwrite the existing ZIP file**.

Update the XML file, and upload everything.

That's it !

**Remember to always get the latest changes from the FTP before you start working on a mod!**

[^1]: http://www.ovoid.org/ovgme/index.htm
