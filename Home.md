<img align="right" src="https://github.com/koreader/koreader/raw/master/resources/koreader.png" height="180" width="180" />

# KOReader WIKI

[简体中文](wiki/KOReader维基)

_KOReader is a document viewer for E-ink devices. Supported document formats include PDF, DjVu, XPS, CBZ, FB2, PDB, TXT, HTML, RTF, CHM, EPUB, DOC, MOBI, and ZIP files. Latest Kindle and Kobo devices are supported. The original  software stays available to use after installation._

* reflow of complex PDF's using `k2pdfopt`
* saving and exporting notes to files or Evernote 
* custom `.ttf` fonts and stardict dictionaries
* cloud storage and synchronization
* content providers: [Wikipedia](https://github.com/koreader/koreader/wiki/Wikipedia-support), [OPDS](https://github.com/koreader/koreader/wiki/OPDS-support) and Goodreads

An extended survey can be found on [[Features list]] or jump directly to [Configuration](#configuration), [Community](#community).

## Getting started

First-time users need to setup a way to launch KOReader. Choose your device brand and follow the model specific steps on one of the following pages: [Kindle](https://github.com/koreader/koreader/wiki/Installation-on-Kindle-devices),  [Kobo](https://github.com/koreader/koreader/wiki/Installation-on-Kobo-devices) or [Pocketbook](https://github.com/koreader/koreader/wiki/Installation-on-PocketBook-devices). This brand-model separation stems from the highly device-specific tool-chains used. 

## Installation/Upgrading
<a name="installation"/>

Make sure that you have completed the preceding setup completely. Save the settings of any existing KOReader installation if necessary before upgrading. (Long pressing certain menu actions will save the program's defaults automatically to a separate file `defaults.persistent.lua`. See [[Change defaults]] for making manual changes.) 

### Using Wi-Fi

Asuming you already installed KOReader succesfully. Enable Wi-Fi and connect to the internet. Use KOReader's top menu to check for a new version. You can to check for upgrades on predefined stable or nightly OTA channels.

### Connected as a USB mass storage device

Choose the KOReader build archive appropriate for your device from the following channels:

- [nightly builds](http://koreader.ak-team.com/): generated automatically overnight. This builds sometimes contain severe bugs (tracked in [issue tracker][issue-tracker]), but contain the latest daily patches.
- [stable builds](https://github.com/koreader/koreader/releases): released every two months on average. Release notes are attached.
- [custom builds](https://github.com/koreader/koreader#building-prerequisites): build it by yourself.

Unpack the downloaded archive in the right folder on your device (see device specific setup instructions for finding the correct path) to install/upgrade. 

## Configuration
<a name="configuration"/>

After starting up KOReader, all you need to do is navigate the file manager to a (hidden) library folder and set it as default by long-pressing the file name. Files with supported file extensions will show op in this file manager. Touch gestures for navigating the user interface are explained in [gestures](https://github.com/koreader/koreader/wiki/KOReader-Gestures). Read more about less known [useful functions](https://github.com/koreader/koreader/wiki/Tips-and-Tricks).

* [[Dictionary support]]
* [[Calibre wireless connection]]
* [[Evernote export]]
* [[Progress sync]]
* [[Zsync transport]]
* [[Statistics plugin]]

## Development community
<a name="community"/>

KOReader is rewrite of "kindlepdfviewer", which is originally built by [hawhill](http://www.mobileread.com/forums/member.php?u=86292) based on the [mupdf](http://www.mupdf.com/) source. Since then it has come a long way, based on requests and updates by hackers around the world. The name "KOReader stands for Kindle/Kobo Open Reader, the devices for which KOReader orginally was written. 

### Users

> Some of the content on the WIKI might be out of date. You are welcome to make it better by opening an issue if you find any of the instructions unclear or confusing.

You can open new issues on the [issue tracker][issue-tracker]. There are related discussion threads on the MobileRead Forums, one of the largest English language web forums for e-book reading/publishing:

* [KOReader Forum](http://www.mobileread.com/forums/forumdisplay.php?f=276)
* [KOReader for Kindle devices](http://www.mobileread.com/forums/showthread.php?t=209276)
* [KOReader for Kobo devices](http://www.mobileread.com/forums/showthread.php?t=216960)
* [KOReader for PocketBook devices](http://www.mobileread.com/forums/showthread.php?t=254659) 
* [KOReader for Android devices](http://www.mobileread.com/forums/showthread.php?t=240617)  
* [mailing list](https://www.freelists.org/list/koreader)

### Hackers

Contribute by writing code.

* [[Start by building the emulator|https://github.com/koreader/koreader#building-prerequisites]]
* [Coding Style][coding_style]
* [[UI Events|http://koreader.rocks/doc/topics/Events.md.html]]
* [How to collaborate with Git](http://koreader.rocks/doc/topics/Collaborating.html)
* [Remote debugging with gdbserver](https://github.com/koreader/koreader-base/wiki/Remote-debugging-with-gdbserver)
* [How to port KOReader to other platform](http://koreader.rocks/doc/topics/Porting.md.html)



[coding_style]:https://github.com/koreader/koreader-base/wiki/Coding-style
[nightly build script]:https://gist.github.com/4002028
[issue-tracker]:https://github.com/koreader/koreader/issues?state=open