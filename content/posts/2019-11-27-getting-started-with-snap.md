---
template: post
title: 'Getting Started with Snap'
featuredImage: '../featuredImages/terminal.png'
date: '2019-11-27'
author: 'Pabon'
profileUrl: 'https://github.com/shahnawaz-pabon'
category:
  - Ubuntu
tags:
  - snap
  - ubuntu
---

## Table of Contents
&nbsp;&nbsp;&nbsp;&nbsp; #:hand: &nbsp; **[Getting Started](#getting-started)** <br/>
&nbsp;&nbsp;&nbsp;&nbsp; #:wrench: &nbsp; **[Setting Up](#setting-up)** <br/>
&nbsp;&nbsp;&nbsp;&nbsp; #:running: &nbsp; **[Install and Run your first Snap](#install-and-run-your-first-snap)** <br/>
&nbsp;&nbsp;&nbsp;&nbsp; #:speech_balloon: &nbsp; **[More Features](#more-features)**

<h3 id="getting-started">#:hand: Getting Started</h3>

1. Snap (or `Snappy` package manager) is one of the best software deployment and package management system which is built by `Canonical`.
2. A `snap` is a bundle of an app and works across many different Linux distributions as well.
3. App packages that are installed through `snap`, called `Snaps`. So `Snaps` are containerized software packages.
4. These are disclosable and installable from the `Snap Store`.
5. `snapd` is the tool for using `snaps`.


The system is actually designed for **IoT, Cloud and Desktop Computing** that are
* Easy to install
* Secured
* Cross-Platform
* Dependency-free

<br/>
<h3 id="setting-up">#:wrench: Setting Up</h3>

#### #:pencil: Installing `snapd` on Ubuntu

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ sudo apt install snapd
```

It manages the snap environment on local the system and will include the snap tool for interacting with snaps as well. You can check whether snap is installed or not by running `snap version` on the command line:

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ snap version
snap    2.42.1
snapd   2.42.1
series  16
ubuntu  18.04
kernel  5.0.0-36-generic
```

<br/>
<h3 id="install-and-run-your-first-snap">#:running: Install and Run your first Snap</h3>

#### #:pencil: Finding a `snap`

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ snap find something
Name                 Version       Publisher       Notes    Summary
paintsupreme-3d      1.0.41        braindistrict   -        PaintSupreme 3D
syncthing            1.3.1         syncthing✓      -        Open Source Continuous File Synchronization
openscad-nightly     0+git.eedfcc4 torsten-paul    -        The Programmers Solid 3D CAD Modeller
step                 19.08.0       kde✓            -        Simulate physics experiments
draftman             1.0.12        jsseidel        classic  A plain-text draft management tool for novelists.
spt                  v0.4.0        popey           -        Spotify TUI
```

`snap find <search keywords>` queries the store and list the results with their details. `✓` indecates that publisher has been verified.


#### #:pencil: Learning about a `snap`

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ snap info hello
name:      hello
summary:   GNU Hello, the "hello world" snap
publisher: Canonical✓
contact:   snaps@canonical.com
license:   GPL-3.0
description: |
  GNU hello prints a friendly greeting. This is part of the snapcraft tour at https://snapcraft.io/
snap-id: mVyGrEwiqSi5PugCwyH7WgpoQLemtTd6
channels:
  stable:    2.10    2019-04-17 (38) 98kB -
  candidate: 2.10    2017-05-17 (20) 65kB -
  beta:      2.10.1  2017-05-17 (29) 65kB -
  edge:      2.10.42 2017-05-17 (34) 65kB -

```

You will know details about a package by running this command.


#### #:pencil: Install and execution

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ sudo snap install hello
hello 2.10 from Canonical✓ installed
```

For running the command simply write `hello` in the command line.

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ hello
Hello, world!
```


#### #:pencil: Keep tracking installed `snaps`

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ snap list
Name                  Version                     Rev   Tracking  Publisher   Notes
core                  16-2.42.1                   8039  stable    canonical✓  core
core18                20191030                    1265  stable    canonical✓  base
gnome-3-28-1804       3.28.0-16-g27c9498.27c9498  110   stable/…  canonical✓  -
```

Installed snaps on your system will be listed by this command.


#### #:pencil: Refreshing an installed `snap`

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ sudo snap refresh hello
snap "hello" has no updates available
```

Above command will check whether a newer version is available or not and it will be downloaded and installed automatically.

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ sudo snap refresh --channel=beta hello
hello (beta) 2.10.1 from Canonical✓ refreshed
```

You can change the channel from which your snap will be tracked and refreshed with this single command.

<br/>
<h3 id="more-features">#:speech_balloon: More Features </h3>

#### #:pencil: Reverting an installed `snap`

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ sudo snap revert hello
hello reverted to 2.10
```

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ snap list --all hello
Name   Version  Rev  Tracking  Publisher   Notes
hello  2.10     38   beta      canonical✓  -
hello  2.10.1   29   beta      canonical✓  disabled
```

Above command will list all `revisions` of hello.

*`Revision` is the sequence number which is assigned by the store when it was uploaded*

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ snap list --all
```

This will list all `revisions` available for every installed snaps.


#### #:pencil: Enabling and Disabling a `snap`

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ sudo snap disable hello
hello disabled

$ sudo snap enable hello
hello enabled
```


#### #:pencil: Removing a `snap`

<div class=fakeMenu>
  <div class="fakeButtons fakeClose"></div>
  <div class="fakeButtons fakeMinimize"></div>
  <div class="fakeButtons fakeZoom"></div>
</div>

```bash
$ sudo snap remove hello
hello removed
```

After running this command, all snap's revisions will be removed. To remove specific revision add `--revision=<revision-number>` to the remove command.
