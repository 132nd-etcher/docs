---
title: OvGME for maintainers
author:
    - //etcher
author-meta: //etcher
header_text: OvGME for maintainers
applies:
    - //wing
title_pictures: //all_logos
subtitle: Operating Instructions for Mods and Skins Management
type: Operating Instructions
version: 0
published_date: unpublished
responsible: //etcher
audience: mods maintainers
summary_of_changes:
    - nil
references:
    - nil
    - nil
---

# Introduction

Maintainers are the ones responsible for creating and updating mods and skins.

In addition to //ovgme, you'll need access to the //wing's FTP as well as a working FTP client.

The FTP client is used to transfer files back and forth between your computer and the //wing's FTP.

I will use WinSCP (because it has a nice synchronization feature), but you can use pretty much any FTP client software.

[Click here to obtain a copy of WinSCP](https://winscp.net/eng/download.php).

# Initial setup

## Create local root folder

Create a directory somewhere, and name it however you'd like. This directory does not need to be located on a SSD, and can grow to a few Gigabytes in size.

In this tutorial, I will call that directory the `local root folder`.

## Setup WinSCP

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

## Pull changes from the FTP

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

## Setup //ovgme

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

# Create a new mod

## Create the source folder

To create a new mod, start by navigating to your `local root folder`.

Open up the repository in which you want the mod to live in (either `132nd` or `externals` at the time I'm writing this).

Create a folder and give it the name of your mod. This mod folder behaves exactly like in JsGME: any file added to it will end up being installed in the DCS installation of the end-users, mirroring the folders structure.

Make sure to test your mod before you package them by installing them in your own DCS installation and making sure they work as intended !

Your mod should appear in //ovgme (make sure you selected the correct `config`).

![New mod](ovgme_new_mod.png)

### Naming your mod

Currently, the convention is to use one of the following prefix:

* MANDATORY: denotes a mod that *everyone must install* to join the server;
* OPTIONAL: denotes a mod that people may *choose* to install (if applicable, please add the name of the squadron the mod is targeting, for sorting purposes).

Make sure to include the prefix in the `source folder` name, since it will be the name of your mod in the end !

## Package the mod

Once you're happy with your mod, it's time to distribute it.

In //ovgme, right click your new mod, and select `Make mod archive`.

![Make mod archive](ovgme_create_mod_archive.png)

Create the `metadata` for your mod, then click the `Make` button.

### Mods' metadata

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

## Update the XML file

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

## Upload the results

You now have a modified local repository: your new mod(s), and a modified XML file.

All there is to do is upload them both on the FTP !

Fire up WinSCP, and open the `Synchronize` dialog (`CTRL+S`).

This time, the target should be `remote` (all other options similar as what we did for pulling the files, cfr. "Pull changes from the FTP").

Let WinSCP analyze the changes, and make sure the preview makes sense before going ahead.

![Upload preview](upload_preview.png)

Once the upload is done, your new mod should be available for download!

# Updating an existing mod

To update an existing mod, start as before by pulling the latest changes from the FTP to your local root folder.

Edit the mod you want to update, using the folder of the mod to change files and run your tests.

Once you are happy with the results, simply re-package your mod, giving it a new version (don't forget to update the changelog), and **overwrite the existing ZIP file**.

Update the XML file, and upload everything.

That's it !

**Remember to always get the latest changes from the FTP before you start working on a mod!**

[^1]: http://www.ovoid.org/ovgme/index.htm
