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

## KOReader Gestures
KOReader on Kindle Touch/PaperWhite supports various [multi-touch gestures](http://en.wikipedia.org/wiki/Multi-touch#Multi-touch_gestures).

### Features that can be triggered by gestures:
#### Page Up
  * Single tap on the left (first quarter of the screen)

#### Page Down
  * Single tap on the right (remaining three quarters of the screen)

#### Display main menu/config Menu
  * Single tap on the upper center of the screen

#### Dismiss main/config Menu
  * Single tap outside of the menu frame

#### Page turn in menus
  * Next page: swipe to the left
  * Previous page: swipe to the right

#### Add/Remove bookmark on the current page
  * Single tap on the upper right corner

#### Toggle flipping mode
  * Single tap on the upper left corner

#### Set page zoom mode
  * Page: Diagonal pinch
  * PageWidth: Horizontal pinch
  * PageHeight: Vertical pinch
  * Content: Diagonal zoom
  * ContentWidth: Horizontal zoom
  * ContentHeight: Vertical zoom

#### Set screen rotation (portrait/landscape)
  * Rotate on screen with an angle larger than 15 degrees

#### Screenshot
  * Tap on diagonally opposed corners of the screen with two fingers at the same time

## Exiting
A single tap on the "File Manager" title will make the reader menu popup, from which you can exit KOReader with the Home icon.