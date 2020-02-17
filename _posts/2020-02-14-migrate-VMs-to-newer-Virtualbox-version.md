---
published: true
layout: post
title: "migrate VMs to a newer Virtualbox version"
date: 2020-02-14
author: gitificial
description: "migrate VMs to newer Virtualbox version"
categories: [system, virtualbox]
tags: [virtualbox]
---

<br/>
A few days ago I tried to install a newer Virtualbox version on my machine. The Virtualbox installation worked flawlessly, but my VMs returned an error message on start. Maybe you have the same problem. To solve it is rather simple.

Tested with:

|------------------+-----------------|
| OS/Software      |Version          |
|------------------|:----------------|
| Ubuntu           |18.04 LTS        |
| Virtualbox (old) |5.1              |
| Virtualbox (new) |6.1.2            |
|------------------+-----------------|

<br/>

Leave the installed Virtualbox (old version) untouched!

Download Virtualbox 6.1.2 from:
```bash
https://download.virtualbox.org/virtualbox/6.1.2/virtualbox-6.1_6.1.2-135662~Ubuntu~bionic_amd64.deb
```

To install Virtualbox just doubleclick the .deb package. 

Run the new Virtualbox version. Your old VMs should be listed. 

Remove the VM entries (ONLY delete!!!) from the list.

Run following command in a terminal to reinstall the kernel module:
```bash
sudo /sbin/vboxconfig
```
Create new VM entries with the old VM images (select the appropriate VM folders).







