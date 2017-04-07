## Supported Devices
Koreader can be installed on all Kindle devices; however, certain features are currently unavailable on non-touch devices such as the Kindle4 (NT) and earlier. See [Issue 1898](https://github.com/koreader/koreader/issues/1898).

## Installation
Besides the reader itself, you will also need to install a launcher. For that purpose, you can use KPVBooklet or KUAL, or even both.

  1. Jailbreak your Kindle, refer to [this post](http://www.mobileread.com/forums/showthread.php?t=186645).
  1. Install a launcher
    * Install KPV Booklet, refer to [this wiki](https://github.com/koreader/kpvbooklet/wiki).
    * Install KUAL, refer to [the official thread](http://www.mobileread.com/forums/showthread.php?t=203326)
  1. Install KOReader
    1. Download the latest Kindle package from [this page](https://github.com/koreader/koreader/wiki/Download).
    1. Unzip the whole archive into the Kindle's USB root directory
  1. Install Stardict dictionaries (optional)
    * Copy Stardict format dictionary files (*.idx, *.ifo, *.dict) into the koreader/data/dict directory.
  1. Install Tesseract language data (optional)
    * Copy Tesseract-OCR language data files (eng.*) for Tesseract 3.02 into the koreader/data/tessdata directory.

## Launching
### via KPV Booklet
Just open any book from the native system, all files except for mobi and txt will be opened with KOReader.
### via KUAL
After installing KOReader, you will see related entries in the KUAL menu. Just tap on it :). The **(no framework)** variants will kill the native GUI first, and restart it once you've quit KOReader (the goal being to gain some more free RAM).

NOTE: After a firmware update, you will most likely have to reinstall some stuff. Of particular importance to KOReader: KPVBooklet if you're using it, and [MKK](http://www.mobileread.com/forums/showthread.php?t=233932) if you're using [KUAL](http://www.mobileread.com/forums/showthread.php?t=203326).