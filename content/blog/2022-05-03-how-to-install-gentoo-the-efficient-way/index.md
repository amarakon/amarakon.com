---
title: How to Install Gentoo – The Efficient Way
author: ~
date: '2022-05-03'
slug: how-to-install-gentoo-the-efficient-way
categories: ["Operating systems", "Tutorial"]
tags: ["foss", "tutorial"]
draft: true
bibliography: ../../../static/bibliography.bib
csl: ../../../static/citations/apa-no-initials.csl
---

# Introduction

So you finally moved from the beginner distributions and you know want to install truly the best operating system of all time; Gentoo Linux.
Contrary to popular belief, installing this operating system is not difficult in the slightest but it is certainly time consuming.
Usually it will take around five hours to install.
This might deter you, but remember that this operating system will actually save you time in the long run.
Not only is it faster than other operating systems, it also makes the user more intelligent, leading to efficient computer usage.
No current Gentoo user regrets spending five hours installing the operating system to save many more hours in total.

For this installation tutorial, you will need to have an existing Unix-like operating system—like any Linux distribution.
Before I get to the beginning of the installation process, there are a few things you must know.
First, you have to care about computing for the installation of Gentoo to be worth it.
Second, please view the Gentoo wiki while you are watching this video.
It is unlikely but possible that some of the information in this video will be outdated.
The Gentoo wiki also has many details that I will not go into because they are not important enough.
Third, you need to know the architecture of your computer’s CPU, usually it is AMD64.
Finally, you must know whether your computer firmware uses BIOS or UEFI.
Generally, only extremely old computers support only BIOS, only terrible new computers support only UEFI, and most computers support both.
You should be completely sure though to avoid messing your entire installation.

# Preparing the Disks

Obviously, since Gentoo requires installation from the command-line, you will need to open a terminal.
Use the `lsblk` command do check the available block devices.
To be cautious, you can unplug any storage devices you do not want to accidentally wipe.
Also make sure to know which block device your current running operating system so you do not accidentally wipe that either.
Use the `wipefs` command to wipe a block device if it already has a partition scheme.
Then use the `cfdisk` command to begin partitioning.

``` sh
$ lsblk
# wipefs -a /dev/*NAME*
# cfdisk /dev/*NAME*
```

If you’re using BIOS, select DOS.
And if you’re using UEFI, select GPT.
If you’re using BIOS, all you need is one partition.
If you’re using UEFI, you need to make a partition that is at least 128 MB, this will be the boot partition.
You should label this partition “EFI system.”
Then create the second partition using the rest of the space.

Once you exited cfdisk, you need to format your partitions.
If you’re using BIOS, all you have to do is format your one partition as ext4 or any other usable file system you prefer:

``` sh
# mkfs.ext4 /dev/*NAME*1
```

If you’re using UEFI, you must format your first partition as VFAT and your second partition the preferred file system:

``` sh
# mkfs.fat -F 32 /dev/*NAME*1
# mkfs.ext4 /dev/*NAME*2
```

# Installing the Gentoo Installation Files

# Installing the Gentoo Base System

# Configuring the Linux Kernel

# Configuring the System

# Configuring the Bootloader

# Finalizing the Installation