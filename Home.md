<img align="right" src="https://github.com/koreader/koreader/raw/master/resources/koreader.png" height="180" width="180" />

# KOReader WIKI

[简体中文](wiki/KOReader维基)

_KOReader is a document viewer for E-ink devices. Supported document formats include PDF, DjVu, XPS, CBZ, FB2, PDB, TXT, HTML, RTF, CHM, EPUB, DOC, MOBI, and ZIP files. Latest Kindle and Kobo devices are supported._

* [[Features list]]
* [[KOReader Screenshots]]
* [Configuration](#configuration)
* [Community](#community)

## Setup

First-time setup depends on the device you are using. This device separation stems from the highly device-specific tool-chains used.

* [[Installation on Kindle devices]]
* [[Installation on Kobo devices]]
* [[Installation on PocketBook devices]]

## Installation 
<a name="installation"/>

Read [[Changelog]] or [Known problems][issue-tracker] first. Choose the KOReader build archive appropriate for your device from the following channels:

- [daily builds](http://build.koreader.rocks/download/nightly/): generated automatically, might contain severe bugs.
- [unstable builds](https://github.com/koreader/koreader/releases): released every two months on average, having less bugs.
- [custom builds](https://github.com/koreader/koreader#building-prerequisites): build it by yourself.

Steps to install:

1. Save the settings of an existing installation if necessary. (Long pressing certain menu actions will save the program's defaults automatically to a separate file `defaults.persistent.lua`.) 
2. Unpack the downloaded archive in the right folder on your device to install/upgrade. 

## Configuration
<a name="configuration"/>

After starting up KOReader, all you need to do is navigate the file manager to a library folder and set it as default by long-pressing the file name. Touch gestures are explained in [[KOReader Gestures]]. The program is loaded with useful features and settings that can be adjusted to your needs:

### Features
* [[Dictionary support]]
* [[Wikipedia support]]
* [[OPDS support]]
* [[Troubleshooting]]

### Plugins
* [[Calibre wireless connection]]
* [[Evernote export]]
* [[Progress sync]]
* [[Zsync transport]]
* [[Statistics plugin]]

### Advanced
* [[Tips and Tricks]]
* [[Change defaults]]
* [[Reflowing tweaks]]

## Development community
<a name="community"/>

KOReader is rewrite of "kindlepdfviewer", which is originally built by [hawhill](http://www.mobileread.com/forums/member.php?u=86292) based on the [mupdf](http://www.mupdf.com/) source. Since then it has come a long way, based on requests and updates by hackers around the world. The name "KOReader stands for Kindle/Kobo Open Reader, the devices for which KOReader orginally was written. 

> Some of the content on the WIKI might be out of date. You are welcome to make it better by opening an issue if you find any of the instructions unclear or confusing.

### Users

You can open new issues on [Known problems][issue-tracker]. There are related discussion threads on the MobileRead Forums, one of the largest English language web forums for e-book reading/publishing:

* [KOReader Forum](http://www.mobileread.com/forums/forumdisplay.php?f=276)
* [KOReader for Kindle devices](http://www.mobileread.com/forums/showthread.php?t=209276)
* [KOReader for Kobo devices](http://www.mobileread.com/forums/showthread.php?t=216960)
* [KOReader for PocketBook devices](http://www.mobileread.com/forums/showthread.php?t=254659) 
* [KOReader for Android devices](http://www.mobileread.com/forums/showthread.php?t=240617)  
* [mailing list](https://www.freelists.org/list/koreader)

### Hackers

Contribute by writing code.

* [[How to Start|Development-Guide]]
* [Coding Style][coding_style]
* [[UI Design|UIDesign]]
* [How to collaborate with Git](https://github.com/koreader/koreader-base/wiki/CollaboratingWithGit)
* [Bug Hunting in Koreader-base][bug-hunt-base]
* [Remote debugging with gdbserver](https://github.com/koreader/koreader-base/wiki/Remote-debugging-with-gdbserver)
* [How to port KOReader to other platform][porting]



[coding_style]:https://github.com/koreader/koreader-base/wiki/Coding-style
[nightly build script]:https://gist.github.com/4002028
[issue-tracker]:https://github.com/koreader/koreader/issues?state=open
[bug-hunt-base]:https://github.com/koreader/koreader-base/wiki/Bug-hunting-in-koreader-base
[porting]:https://github.com/koreader/koreader/wiki/porting