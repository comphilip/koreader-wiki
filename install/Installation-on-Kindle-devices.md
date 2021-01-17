## Supported Devices
KOReader can be installed on all *jailbroken* Kindle devices.

**NOTE:** The ability to jailbreak a Kindle device depends on both the model, the specific variant of its model, and the current firmware version it's running.
Detailing the whole process is out of scope for this document, so, please check the current state of things on [MobileRead](https://www.mobileread.com/forums/forumdisplay.php?f=150). Currently, [this thread](https://www.mobileread.com/forums/showthread.php?t=320564) should be a good starting point.
In general, the newer the device, the trickier it gets.


Certain minor features may currently still be unavailable on non-touch devices such as the Kindle 4 (NT) and earlier. Don't hesitate to check and open an issue if you encounter such a problem.

## Installation
Besides the reader itself, you will also need to install a launcher. For that purpose, you can use KPVBooklet or KUAL, or even both, with the caveat that KPVBooklet only supports devices running FW 5.x, and may not function properly on recent FW 5.x releases ;).

  1. Jailbreak your Kindle, refer to [this post](https://www.mobileread.com/forums/showthread.php?t=320564) or others, depending on your device (see the NOTE at the top of this page).
  1. Install a launcher
      * Install KUAL, refer to [the official thread](http://www.mobileread.com/forums/showthread.php?t=203326)
      * Install KPV Booklet, refer to [this wiki](https://github.com/koreader/kpvbooklet/wiki). ***NOTE***: KPV is deprecated, largely because it is unmaintained, and is known to be broken on a wide range of not-so-recent FW versions.
  1. Install KOReader
      1. Read [this section at the end of the page](#err-there-are-three-kindle-packages-to-choose-from-which-do-i-pick) to figure out which Kindle release you want to download.
      1. Download the latest Kindle package from [this page](https://github.com/koreader/koreader/releases).
      1. Unzip the whole archive into the Kindle's USB root directory
  1. Install Stardict dictionaries (optional)
      * Copy Stardict format dictionary files (*.idx, *.ifo, *.dict) into the koreader/data/dict directory.
  1. Install Tesseract language data (optional)
      * Copy Tesseract-OCR language data files (eng.*) for Tesseract 3.02 into the koreader/data/tessdata directory.

## Launching
### via KUAL
After installing KOReader, you will see related entries in the KUAL menu. Just tap on it :). The **(no framework)** variants will kill the native GUI first, and restart it once you've quit KOReader (the goal being to gain some more free RAM). Note that said variant may not be completely functional on some model/FW combinations. It's mostly aimed at older devices.


NOTE: After a firmware update, you will most likely have to reinstall some stuff. Of particular importance to KOReader: KPVBooklet itself if you're using it, as well as [KUAL](http://www.mobileread.com/forums/showthread.php?t=203326) itself if you're running the Booklet version. More generally, the [JB Hotfix](https://www.mobileread.com/forums/showpost.php?p=3004892&postcount=1597) is the first thing to try, although current JB versions should ensure basic functionality makes it through. 

### via KPV Booklet
Just open any book from the native system, all files except for mobi and txt will be opened with KOReader.

NOTE: On some recent FW versions, KPVBooklet may be non-functional. You may also need a tweaked version of KUAL. Again, check MobileRead's Kindle Dev forum.

NOTE: KPVBooklet may have some issues that don't happen with KUAL:
[Screensaver issues](https://github.com/koreader/koreader/issues/4605), 
[White screen occasionally while reading epub files](https://github.com/koreader/koreader/issues/3287), 
[White screen after waking up](https://github.com/koreader/koreader/issues/4413).


## OTA Update
1. Simply tap the top portion of the device to bring up the menu

2. Tap item in the top right corner

3. Tap update, and follow the on-screen instructions


## Manual Update
Download the latest version as described in the [Install section](#Install). Copy the **koreader-kindle\*.zip** or koreader-kindle\*.tar.gz** in the kindle root folder (a.k.a. /mnt/us, this is the folder that directly contains `documents` folder ). On the kindle, go to KUAL->KOReader->Tools->Update KOReader. 

Done!

(This calls the script on the kindle */mnt/us/extenstions/koreader/bin/koreader-ext.sh*, which extracts the archive to the koreader folder on the kindle.)

[More information can be found here](https://www.mobileread.com/forums/showthread.php?t=326052)

## USB
**IMPORTANT NOTE:** Switching your device to USBMS mode (by plugging it to a computer over USB) while KOReader is running is *entirely unsupported*, and risks crashing in fun and interesting ways, both KOReader, and possibly the Kindle's underlying system. Recent KOReader versions make an attempt at avoiding complete and utter mayhem, but it's still not recommended to try to test that theory ;).
If you need to charge your device while KOReader is running, either do it with a charger, or switch your device to USBNet mode first.

## Err, there are three Kindle packages to choose from, which do I pick?

They're indicative of the earliest device family the binaries support (and are optimized for). Ideally, you choose the one that most closely matches your actual device, in order to enjoy the best possible performance.

* **Legacy**: K2, DX, K3 (and all their variants).
* **Kindle**: K4, K5, PW1
* **PW2**: Everything else, starting from the PW2 (i.e., PW2, KV, KT2, PW3, KOA, KT3, KOA2, PW4, KT4).


If you're unsure of which exact model you have, or if those nicknames confuse you, please refer to [this handy table](https://wiki.mobileread.com/wiki/Kindle_Serial_Numbers) ;).