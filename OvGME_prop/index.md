---
title: "Proposal: OvGME"
title-meta: "Proposal: OvGME"
author:
  - 132nd-etcher
author-meta: 132nd-etcher
applies:
    - //wing
title_pictures:
    - logo617th.png
    - logo23rd.png
    - logo259th.png
    - logo696th.png
    - logo176th.png
    - logo765th.png
audience: CMD
subtitle: Mods and skins management
keywords: mods,skins,jsgme,ovgme,proposal
type: Enhancement Proposal
version: 0
published_date: unpublished
responsible: etcher
summary_of_changes:
 - nil
---


![//ovgme logo](https://www.virtual-aaf.com/uploads/monthly_2017_06/OvGME-logo.png.a0cf027982a22a14140b3523e254bf08.png)

# Abstract

This document contains an enhancement proposal submitted to CMD for review is about managing mods and skins in the //wing.

# Rationale

The current system for skins distribution is working fine, from the end-user point of view at least. Using the //ski to install files is a one-click process and that is really, really good. There two issues with it though:

1. While it is easy for *users* to use the //ski, updating the skins with it is a pain for the *maintainer*;
2. The //ski only installs files under the "Saved Games" directory. This is a problem for some of the mods we need nowadays, they need to go in the DCS installation directly. The //ski was never meant to manage mods, it is just that the needs we have have changed.

This proposal has been cooking since July 2017, but I've decided to rush it because of the issues we've had lately with some of the mandatory mods (Helipad, WASP, Range targets, ...). It has become difficult and troublesome for people to make sure that their DCS installation is compatible with the //wing's server. My apologies for the rough state of this proposal, as well as for the half-finish documentation.

# Objective

> **Note:** in tis document, I'm using the terms "end-user and "maintainer" to describe:
> * End-user: a pilot that will use our skins and mods; they might be part or the //wing or memeber of an external organization.
> * Maintainer: a maintainer is a member of the //wing who is responsible for maintaining a mod/skin up to date. They also are the ones who initially creates mods/skins packages, and upload them.

What I'm trying to achieve:

1. Simplify the building/updating process for maintainers
2. Keep the installation process as simple as possible for the end-user
3. Allow for he installation of mods in the DCS installation as well as in the Saved Games folder


# Proposed solution

This proposal is very simple. The plan is to use [//ovgme](http://www.ovoid.org/ovgme/) instead of the //ski to distribute mods and skins within the //wing.

OvGME is a mod management application, much like JsGME, that allows to install/uninstall mods (obviously), but also to subscribe to remote repositories of versionned mods, making propagating and updating mods and skins much simpler.

[Documentation website for //ovgme](http://www.ovoid.org/ovgme/help/en/index.php?c=introduction.html).

# Pros and cons

This section objectively (as much as I could) describes the pros and cons of the method I propose to implement.

## The cons

* Depending on yet another dependency: we will have to transition from using the //ski to using //ovgme, which might pose a problem to the less tech-asvvy of our userbase. See "Transition" section below.
* Modular dependencies: no more *one click install* of mods and skins. Since some mods are optional (for mission makers for example) and others contextual (a pit for the Ka50 for example), users will need to install some mods and skip others. **To mitigate that, my solution is currently to tag every mod/skin as "MANDATORY" or "OPTIONAL"**, making it obvious which one MUST be installed to join the server and letting the user decide which optional mod to install.
* External organizations do not need access to all of our mods, and some mods might resitrict re-distribution, forcing us to redirect external users to their official website and to assume they'll be able to install them themselves. Internally, distributing "protected" mods is not an issue.
* Atomal packaging of mods: the idea would be to have one mod labelled as "MANDATORY", so users who want the minimal amount of bother can install that one and be done with it. The issue with it is that updating and downloading a mod is an atomic operation: if we want to update one skin, we have to upload the whole ZIP file again, and users who want to update will have to download the whole file as well. If we put all our mods together in one single, nice package, then every time we update a skins for the //617 for example, we'll have to **upload** all skins (including externals, some of them weight hundreds of megabytes), and users would have to download it as well. I find it impractical, which is why I decided to split mods and skins into more manageable chuncks.

## The pros

* Single source of thruth: this a big one. No more fiddling around with the //ski on one side, then going to google Drive/Dropbox to grab mods and install them manually, or with JsGME///ovgme. This should help a lot with the current situation, where it is not an uncommon occurence to have to debug with users before the flight on TS because  a missing mod won't let them join the server.
* Most of us are already using JsGME or //ovgme, to integrating the new workflow won't be a problem for those.
* Mods and skins are modular: this is also a pro, because it allows squadrons to ditribute mods that are not mandatory, but nice to have (ex: new cockpit, maps for the TAD, ...). This allows getting newcomers onbaord much faster.
* Versionning of mods and skins: each mod and each skin uploaded to our repository receives a version. This makes it *very* easy to make sure that everyone has the correct, latest version of the mods. When a maintainer releases a new version of a mod or a skin, a NOTAM would be issued, and the people who currently have this mod installed (or everyone in acse of a "MANDATORY" mod) just need to fire up //ovgme and update the mod (a few click and a few seconds).
* Much simpler job for maintainers: creating, uploading and updating mods and skins in the repository is much simpler than with the //ski. It takes but a few clicks and a few minutes to have a new version of a mods on in the repository, available for users to download.
* Sharing the load: splitting the mods and skins into smaller, more manageable units allows for a better repartition of tasks. Each mod/skin should have an official "maintainer", and that person is responsible for keeping it up-to-date. For example, someone might be responsible for the skins of the //259, while someone else would be responsible for the "MISSION MAKERS" mods. No more huge, monolithic list of mingled skins.
* Using external repositories: in the future, maybe an external organization will be using //ovgme to manage their list of skins and mods. Adding their reporitory to //ovgme is a trivial process, and it would allow us to user their skins directly, instead of having to re-package them ourselves.
* //ovgme is capable of managing multiple target destinations; this would be very useful in case we need one of the following:
    * Manage different version of the mods/skins for different DCS versions
    * Install some mods in the Save Games folder, and other directly in the main DCS installation
* Managing conflicts: when two mods modified the same file, there is a conflict. Sometimes, the conflict is void, because the two mods are making the same change. Other times, the two mods are changing different part of the same file. In that latter case, a "patch" needs to be created, that merges the changes from the two conflicting mods. With //ovgme, this is very easy to do.

# Technical

This section describes the tools chain that would be used to build and publish the documentation.

## Overview

This section describes the tools and workflow needed to implement the new system.

### End-user

The only tool needed for the end-user is //ovgme itself. Some might need guidance during the initial transition process, which will be provided by the documentation. Using //ovgme is straight forward enough that everyone should be able to maintain with ease.

### Maintainer

Maintainers will need //ovgme, as wel as a FTP client to be able to upload files on the //wing's FTP ([Filezilla](https://filezilla-project.org/) is a good starting point).

#### Brief description

The documentation will eventually cover this in a more detailed fashion, but here is a brief overview of how it works:

**Note**: to follow along, open [http://132virtualwing.org/files/ovgme/](http://132virtualwing.org/files/ovgme/) in your borwser.

The //wing's repository is described by the 132nd.xml file. That file is automatically generated by //ovgme.

All the mods themselves are contained in the "132nd" folder, right next to the file.

The mods are in two format:
    * bare folder:  the mod itself, deflated, containing all the files, in the same format as JSGME; this is the "source"
    * ZIP: mod packaged and ready to be distributed; this is the "package"
    
To create a mod, the first thing to do is to create the source folder, containing the files of the mods. For example, a simple skin. This folder follows the JsGME standard, replicating the target directory structure, adding and replacing files on the fly.

Onca created, the source folder is available locally for installation, thus permitting to test the mod before packaging it.

Then, using //ovgme, the source folder is packaged into a ZIP file, along with "metadata" about (metadata is things like version, description, author, etc.).

That ZIP file is also availabe locally for installation, and it should be tested as well.

Now, stil using //ovgme, there is a command to create a "repository" file from all the mods currently available locally. That command will look for every ZIP-ped mod, and create a "*.xml" file containing metadata for all of them (see, for example, [132.xml](http://132virtualwing.org/files/ovgme/132nd.xml)).

At that point, all there is to do is upload both the ZIP file and the XML file to the FTP, and you're set.

**Note**: I've upload the mods in folder formats on the FTP as well, so if someone wants to update one of the mods, they have access to the source folder I've used to create the ZIP package.

##### Profiles

I've explained briefly how to go from a mod folder to a ZIP package, and how to make a repository out of a set of packages (for example the "132nd" folder and the "132nd.xml" file on the FTP). This section describes how to manage and switch repositories.

To manage different repositories, you need "profiles". When you build the "*.xml" file, //ovgme will use *all* the mods that are present in the curent profile (the current mods folder of //ovgme), or to be put it another way, all the mods that are visible in //ovgme at that time.

So, if we want to create another repository for "externals", for example, we need another profile. That is what I did with the "external" folder and the "external.xml" on the FTP.

So, in the end, I have 3 profiles in //ovgme:

* My regular profile, pointing to DCS, to install mods and skins
* A profile for the "132nd" repository, in sync with the "132nd" dir of the FTP
* A profile for the "externals" repository, in sync with the "exeternal" dir of the FTP
 
##### Workflow

Now that we know all that, the work flow to add or update a mod is as follows:

1. Connect to the FTP and download the latest changes into the local profile
2. Make the changes needed or add the new mod/skin
3. Test the new/updated mod
4. Create a ZIP package for the mod, adding or updating the metadata (version, author, decsription, ...)
5. Update the XML file with //OV
6. Upload the new/updated ZIP package and the XML to the FTP

# Transition

This section describes how to transition to the new system if we decide to switch.

## Overview

Description of the transition process step by step:

1. Freeze the current mods and skins list
2. Transfer them into the //ovgme repository of the //wing
3. Create another repository for external organizations
4. Publish //ovgme documentation along with a NOTAM
5. Help users who have trouble getting up to speed

Step 1 and 2 are almost taken care of, I have a working, test repository that's been going on for a while now. you can find it at: [http://132virtualwing.org/files/ovgme/](http://132virtualwing.org/files/ovgme/) (**note**: the only two relevant folders are "132nd" and "externals", the others are artifacts from previous testing.).

Step 4 is ongoing, as I've already written the documentation for the end-users. I still have to write documentation for maintainers.

Step 5 would take very little time, as I expect little to no issue by using this process. The only trouble I can foresee is for people who are not using a mod manager at this time, relying instead on just dropping mod content in their install; they'll have a bad time removing old mods betfore switching.

## Documentation

I'm writing a document describing, step by step, how to use //ovgme as:

* an end-user, to downloads, install and update mods and skins (done)
* a maintainer, to create, upload and update mods and skins (ongoing)

## Crash course

I plan on offering crash course with OvGME to the people who are interested in it.

The crash course should take about 10 minutes on TS for end-users, and maybe 30 minutes for the maintainers.