---
author:
 - etcher
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
type: Enhancement Proposal
version: 0
published_date: unpublished
responsible: etcher
summary_of_changes:
 - nil
---


![Documentation](https://www.virtual-aaf.com/uploads/monthly_2017_06/OvGME-logo.png.a0cf027982a22a14140b3523e254bf08.png)

# Enhancement Proposal

## Abstract

This document contains an enhancement proposal submitted to CMD for review.

The proposal is about managing mods and skins in the //wing. I would like to make it easier for maintainers to offer and maintain mods, while keeping it simple for the end-user to install them.

## Rationale

The current system for skins distribution is working fine, from the end-user point of view at least. Using the //ski to install files is a one-click process and that is really, really good. There two issues with it though:

1. While it is easy for *users* to use the //ski, updating the skins with it is a pain for the *maintainer*
2. The //ski only installs files under the "Saved Games" directory. This is a problem for some of the mods we need nowadays, they need to go in the DCS installation directly. Now the //ski ws never meant to manage mods, so this isn't something I'm holding against it, but the needs we have have changed.

This proposal has been cooking since July 2017, but I've decided to rush it because of the issues we've had lately with some of the mandatory mods (Helipad, WASP, Range targets, ...). It has become difficult and troublesome for people to make sure that their DCS installation is compatible with the //wing's server. My apologies for the rough state of this proposal, as well as for the half-finish documentation.

## Objective

> **Note:** in tis document, I'm using the terms "end-user and "maintainer" to describe:
    End-user: a pilot that will use our skins and mods; they might be part or the //wing or memeber of an external organization.
    Maintainer: a maintainer is a member of the //wing who is responsible for maintaining a mod/skin up to date. They also are the ones who initially creates mods/skins packages, and upload them.

What I'm trying to achieve:

1. Simplify the building/updating process for maintainers
2. Keep the installation process as simple as possible for the end-user
3. Allow for he installation of mods in the DCS installation as well as in the Saved Games folder


## Getting there

This section conceptually describes how to achieve the goals outlined above.

### Using //ov

This proposal is very simple. The plan is to use //ov instead of the //ski to distribute mods and skins within the //wing.

#### Specification

OvGME is a mod management application, much like JsGME, that allows to install/uninstall mods (obviously), but also to subrscribe to remote repositories of versionned mods. This  makes propagating and updating the mods much simpler.

## Pros and cons

This section objectively (as much as I could) describes the pros and cons of the method I propose to implement.

### The cons

* Depending on yet another dependency: we will have to transition from using the //ski to using /ov, which might pose a problem to the less tech-asvvy of our userbase. See "Transition" section below.
* Modular dependencies: no more *one click install* of mods and skins. Since some mods are optional (for mission makers for example) and others contextual (a pit for the Ka50 for example), users will need to install some mods and skip others. **To mitigate that, my solution is currently to tag every mod/skin as "MANDATORY" or "OPTIONAL"**, making it obvious which one MUST be installed to join the server.
* External organizations do not need access to all of our mods, and some mods might resitrict re-distribution, forcing us to redirect external users to their official website and to assume they'll be able to install them themselves. Internally, distributing "protected" mods is not an issue.

### The pros

* Single source of thruth: this a big one. No more fiddling around with the //ski on one side, then going to google Drive/Dropbox to grab mods and install them manually, or with JsGME///ov. This should help a lot with the current situation, where it is not an uncommon occurence to have to debug with users before the flight on TS because  a missing mod won't let them join the server.
* Most of us are already using JsGME or //ov, to integrating the new workflow won't be a problem for those.
* Mods and skins are modular: this is also a pro, because it allows squadrons to ditribute mods that are not mandatory, but nice to have (ex: new cockpit, maps for the TAD, ...). This allows getting newcomers onbaord much faster.
* Versionning of mods and skins: each mod and each skin uploaded to our repository receives a version. This makes it *very* easy to make sure that everyone has the correct, latest version of the mods. When a maintainer releases a new version of a mod or a skin, a NOTAM would be issued, and the people who currently have this mod installed (or everyone in acse of a "MANDATORY" mod) just need to fire up //ov and update the mod (a few click and a few seconds).
* Much simpler job for maintainers: creating, uploading and updating mods and skins in the repository is much simpler than with the //ski. It takes but a few clicks and a few minutes to have a new version of a mods on in the repository, available for users to download.
* Sharing the load: splitting the mods and skins into smaller, more manageable units allows for a better repartition of tasks. Each mod/skin should have an official "maintainer", and that person is responsible for keeping it up-to-date. For example, someone might be responsible for the skins of the //259, while someone else would be responsible for the "MISSION MAKERS" mods. No more huge, monolithic list of mingled skins.
* Using external repositories: in the future, maybe an external organization will be using //ov to manage their list of skins and mods. Adding their reporitory to //ov is a trivial process, and it would allow us to user their skins directly, instead of having to re-package them ourselves.
* //ov is capable of managing multiple target destinations; this would be very useful in case we need one of the following:
    * Manage different version of the mods/skins for different DCS versions
    * Install some mods in the Save Games folder, and other directly in the main DCS installation

## Technical

This section describes the tools chain that would be used to build and publish the documentation.

### Overview

this section describes the tools and workflow needed to implement the new system.

#### End-user

The only tool needed for the end-user is //ov itself.

#### Maintainer

Maintainers will need //ov, as wel as a FTP client to be able to upload files on the //wing's FTP ([Filezilla](https://filezilla-project.org/) is a good starting point).

## Transition

This section describes how to transition to the new system if we decide to switch.

### Overview

Description of the transition process step by step:

1. Freeze the current mods and skins list
2. Transfer them into the //ov repository of the //wing
3. Create another repository for external organizations
4. Publish //ov documentation along with a NOTAM
5. Help users who have trouble getting up to speed

Step 1 and 2 are almost taken care of, I have a working, test repository that's been going on for a while now. you can find it at: [http://132virtualwing.org/files/ovgme/](http://132virtualwing.org/files/ovgme/) (**note**: the only two relevant folders are "132nd" and "externals", the others are artifacts from previous testing.).

Step 4 is ongoing, as I've already written the documentation for the end-users. I still have to write documentation for maintainers.

Step 5 would take very little time, as I expect little to no issue by using this process. The only trouble I can foresee is for people who are not using a mod manager at this time, relying instead on just dropping mod content in their install; they'll have a bad time removing old mods betfore switching.

### Documentation

I'm writing a document describing, step by step, how to use //ov as:

* an end-user, to downloads, install and update mods and skins (done)
* a maintainer, to create, upload and update mods and skins (ongoing)

### Crash course

I plan on offering crash course with OvGME to the people who are interested in it.

The crash course should take about 10 minutes on TS for end-users, and maybe 30 minutes for the maintainers.
 
