---
title: "Proposal: OvGME"
author:
  - //etcher
author-meta: //etcher
applies:
    - //wing
title_pictures: //all_logos
audience: CMD
subtitle: Mods and skins management
keywords: "mods,skins,jsgme,ovgme,proposal"
type: Enhancement Proposal
version: 1
published_date: 2017-08-29
responsible: //etcher
summary_of_changes:
 - nil
---

# Abstract

This document contains an enhancement proposal submitted to CMD for review about managing mods and skins in the //wing.

# Rationale

The current system for skins distribution is working fine, from the end-user point of view at least. Using the //ski to install files is a one-click process and that is really, really good.

That being said, there are two issues with it at the moment:

1. While it is easy for *users* to use the //ski, updating the skins with it is a pain for the *maintainer*;
2. The //ski only installs files under the "Saved Games" directory. This is a problem for some of the mods we need nowadays, they need to go in the DCS installation directly. The //ski was never meant to manage mods, and our needs we have have evolved.

This proposal has been cooking since May 2017, and now I'm rushing it because of the issues we've had lately with some of the mandatory mods (Helipad, WASP, Range targets, ...). It has become difficult and troublesome for people to make sure that their DCS installation is compatible with the //wing's server.

My apologies for the rough state of this proposal, as well as for the half-finished documentation.

# Objectives

**Note**: in tis document, I'm using the terms "end-user and "maintainer" to describe:

> End-user: a pilot that will use our skins and mods; they might be part or the //wing or member of an external organization.

> Maintainer: a maintainer is a member of the //wing who is responsible for maintaining a mod/skin up to date. They also are the ones who initially creates mods/skins packages, and upload them.

What I'm trying to achieve:

1. Simplify the building/updating process for maintainers
2. Keep the installation process as simple as possible for the end-user
3. Allow for he installation of mods in the DCS installation as well as in the Saved Games folder


# Proposed solution

This proposal is very simple. The plan is to use [//ovgme](http://www.ovoid.org/ovgme/) instead of the //ski to distribute mods and skins within the //wing.

![//ovgme logo](https://www.virtual-aaf.com/uploads/monthly_2017_06/OvGME-logo.png.a0cf027982a22a14140b3523e254bf08.png)

OvGME is a mod management application, much like JsGME, that allows to install/uninstall mods (obviously).

The difference is that /ovgme also allows end-users to subscribe to remote repositories of versioned mods, making propagating and updating mods and skins much simpler. Keeping those repositories up-to-date is also very easy for maintainers.

[Documentation website for //ovgme](http://www.ovoid.org/ovgme/help/en/index.php?c=introduction.html).

# Pros and cons

This section objectively (as much as I could) describes the pros and cons of the method I propose to implement.

## The cons

* Depending on yet another dependency: we will have to transition from using the //ski to using //ovgme, which might pose a problem to the less tech-savvy of our users base. **See "Transition" section below**;
* Modular dependencies: no more *one click install* of mods and skins. Since some mods are optional (for mission makers for example) and others contextual (a pit for the Ka50 for example), users will need to install some mods and skip others. **To mitigate that, my solution is currently to tag every mod/skin as "MANDATORY" or "OPTIONAL"**, making it obvious which one MUST be installed to join the server and letting the user decide which optional mod to install;
* External organizations do not need access to all of our mods, and some mods might restrict re-distribution, forcing us to redirect external users to their official website and to assume they'll be able to install them themselves. **Internally, distributing "protected" mods is not an issue**;
* Atomal packaging of mods: the idea would be to have one mod labelled as "MANDATORY", so users who want the minimal amount of bother can install that one and be done with it. The issue with it is that updating and downloading a mod is an atomic operation: if we want to update one skin, we have to upload the whole ZIP file again, and users who want to update will have to download the whole file as well. If we put all our mods together in one single, nice package, then every time we update a skin for the //617 for example, we'll have to **upload** all skins (including externals, some of them weight hundreds of megabytes), and users would have to download it as well. I find it impractical, which is why I decided to split mods and skins into more manageable chunks.

## The pros

* Single source of truth: this a big one. No more fiddling around with the //ski on one side, then going to google Drive/Dropbox to grab mods and install them manually, or with JsGME///ovgme. This should help a lot with the current situation, where it is not an uncommon occurrence to have to debug with users before the flight on TS because  a missing mod won't let them join the server;
* Most of us are already using JsGME or //ovgme, to integrating the new workflow won't be a problem for those;
* Mods and skins are modular: this is both a pro and a con, because while it denies us the blessed "one-click-install', it also allows squadrons to distribute mods that are not mandatory, but nice to have (ex: new cockpit, maps for the TAD, ...). This will help getting newcomers up to speed with their installation;
* Versionning of mods and skins: each mod and each skin uploaded to our repository receives a version. This makes it *very* easy to make sure that everyone has the correct, latest version of the mods. When a maintainer releases a new version of a mod or a skin, a NOTAM would be issued, and the people who currently have this mod installed (or everyone in case of a "MANDATORY" mod) just need to fire up //ovgme and update the mod (a few click and a few seconds);
* Much simpler job for maintainers: creating, uploading and updating mods and skins in the repository is much simpler than with the //ski. It takes but a few clicks and a few minutes to have a new version of a mods on in the repository, available for users to download;
* Sharing the load: splitting the mods and skins into smaller, more manageable units allows for a better repartition of tasks. Each mod/skin should have an official "maintainer", and that person is responsible for keeping it up-to-date. For example, someone might be responsible for the skins of the //259, while someone else would be responsible for the "MISSION MAKERS" mods. No more huge, monolithic list of mingled skins;
* Using external repositories: in the future, maybe an external organization will be using //ovgme to manage their list of skins and mods. Adding their repository to //ovgme is a trivial process, and it would allow us to user their skins directly, instead of having to re-package them ourselves;
* //ovgme is capable of managing multiple target destinations; this would be very useful in case we need one of the following:
    * Manage different version of the mods/skins for different DCS versions;
    * Install some mods in the Save Games folder, and other directly in the main DCS installation;
* Managing conflicts: when two mods modify the same file, there is a conflict. Sometimes, the conflict is void, because the two mods are making the same change(s). Other times, the two mods are changing different part of the same file. In that latter case, a "patch" needs to be created, that merges the changes from the two conflicting mods. With //ovgme, this is very easy to do.

# Technical

This chapter is about the technical details of the proposed solution.

## Overview

This section describes the tools and workflow needed to implement the new system.

### End-user

The only tool needed for the end-user is //ovgme itself. Some might need guidance during the initial transition process (see "Transition"). Using //ovgme is straight forward enough that everyone should be able to maintain with ease.

### Maintainer

Maintainers will need //ovgme, as well as a FTP client to be able to upload files on the //wing's FTP ([Filezilla](https://filezilla-project.org/) is a good starting point).

## Brief description

The documentation will eventually cover this in a more detailed fashion, but here is a brief overview of how it works:

**Note**: to follow along, open [http://132virtualwing.org/files/ovgme/](http://132virtualwing.org/files/ovgme/) in your browser.

### The repository

The repository is comprised of two things: the metadata and the mods themselves. I will use the "132nd" repository for this example.

* The metadata: the //wing's main repository is described by the "132nd.xml" file. That file has been automatically generated by //ovgme; feel free to click on it and check what's inside.
* The mods: those are contained in the "132nd" folder. The subfolders are irrelevant to the repository, only ZIP files are actual mods (more on that below).

### Mods/skins

All the mods themselves are contained in the "132nd" folder.

The mods come in two formats:

* bare folder:  the mod itself, deflated, containing all the files, in the same format as JSGME; this is the "source" (this is used by the maintainer to create/update their mods);
* ZIP: mod packaged and ready to be distributed; this is the "package" (this is what end-users will download eventually).

In the "132nd" folder, all mods are present in the two formats; I'll explain why later.
    
To create a mod, the first thing to do is to create the source folder, containing the files of the mods. For example, a simple skin. This folder follows the JsGME standard, replicating the target directory structure, adding and replacing files on the fly.

Once created, the source folder is available locally for installation, thus permitting to test the mod before packaging it.

### Packaging

Once the mod is ready, the source folder is packaged into a ZIP file using //ovgme's menu. During the operation, //ovgme will ask for "metadata" (things like version, description, author, etc.).

The resulting  ZIP file is also available locally for installation, and it should be tested as well.

Now, still using //ovgme, there is a command to create a "repository" from all the mods currently available locally. That command will look for every ZIP-ped mod, and create a "*.xml" file containing metadata for all of them (see, for example, [132.xml](http://132virtualwing.org/files/ovgme/132nd.xml)).

At that point, all there is to do is upload both the ZIP files and the XML file to the FTP.

**Note**: I've uploaded the mods in folder formats on the FTP as well, so if someone wants to update one of the mods, they have access to the source folder that  I've used to create the ZIP package.

### Profiles

I've explained briefly how to go from a mod folder to a ZIP package, and how to make a repository out of a set of packages (for example the "132nd" folder and the "132nd.xml" file on the FTP). This section describes how to manage and switch repositories.

To manage different repositories, you need "profiles" (they're called "Config" in //ovgme). When you build the XML file, //ovgme will use *all* the mods that are present in the current profile (the current mods folder of //ovgme), or to be put it another way, all the mods that are visible in //ovgme at that time.

So, if we want to create another repository for "externals", for example, we need another profile. That is what I did with the "external" folder and the "external.xml" on the FTP.

For example, in the end, I have 3 profiles ("Config") in //ovgme:

* My regular profile, pointing to DCS, to actually install mods and skins into DCS
* A profile for the "132nd" repository, in sync with the "132nd" dir of the FTP, to "build" the "132nd" repository
* A profile for the "externals" repository, in sync with the "externals" dir of the FTP, to "build" the "externals" repository

### Workflow

(note: this is missing from the documentation for the time being, I will document all those steps in detail as soon as I have the time to do so.)

Now that we know all that, the work flow to add or update a mod is as follows:

1. Connect to the FTP and download the latest changes into the local profile (download all the source folders for all mods)
2. Make the changes needed or add the new mod/skin
3. Test the new/updated mod
4. Create a ZIP package for the updated/new mod(s), adding or updating the metadata (version, author, description ...)
5. Update the XML file for the whole repository with //ovgme
6. Upload the new/updated ZIP package(s) as well as the updated XML to the FTP

Once that is done, the new/updated mods will be available for download to the end-users.

# Transition

This section describes how to transition to the new system if we decide to switch.

## Overview

Description of the transition process step by step:

1. Freeze the current mods and skins list (no more updates for a day or two)
2. Create the //wing repository
3. Create another repository for external organizations
4. Publish //ovgme documentation along with a NOTAM
5. Help users who have trouble getting up to speed

Step 1, 2 and 3 are almost taken care of, I have a working, test repository that's been going on for a while now. you can find it at: [http://132virtualwing.org/files/ovgme/](http://132virtualwing.org/files/ovgme/).

If you want to test those repositories locally, launch //ovgme, click "Mods", "Repositories", "Configure", and add `http://132virtualwing.org/files/ovgme/132nd/` (replace `132nd` with `externals` to test the other one). Then click "Mods", "Repositories", "Query" to update the repo.

Step 4 is ongoing, as I've already written the documentation for the end-users. I still have to write documentation for maintainers.

Step 5 would take very little time, as I expect little to no issue by using this process. The only trouble I can foresee is for people who are not using a mod manager at this time, relying instead on just dropping mod content in their install; they'll have a bad time removing old mods before switching.

## Documentation

I'm writing a document describing, step by step, how to use //ovgme as:

* an end-user, to downloads, install and update mods and skins (done)
* a maintainer, to create, upload and update mods and skins (ongoing)

A **VERY** early version of that document can be found [here](https://drive.google.com/file/d/0B7vvW7GYaD8oQlBOWkFJdnNhUkk/view?usp=sharing).

## Crash course

I plan on offering crash courses on TS for both end-users and maintainers if need be.