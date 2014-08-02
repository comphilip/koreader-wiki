## [Nightly builds](https://github.com/koreader/koreader/releases)
* add menu entry for E-ink screen refresh rate
* add menu entry for UI font size
* add menu entry for OTA update
* add floating punctuation toggler for EPUBs
* prompt users to turn on Wifi if network is unreachable
* handle the new 4GB PW2 models
* shortcut chevrons for the first/last page navigation in menus
* swipe east/west to switch dictionary in dict quick lookup window
* update mupdf and k2pdfopt to latest version
* hold on config panel, zoom mode menu and font menu to set global default option
* show pages left and battery status on minibar
* restrict highlight in current page area
* optimize compiling parameters for all three platforms(kindle, kobo and Android)
* fix back to nickel on 3.4.1 for kobos
* fix cannot get word box in last page of a chapter
* fix screen auto rotation on Android causes koreader freeze
* add ZSync plugin (a peer-to-peer document sharing plugin in LAN)
* persistent option for defaults.lua
* new swipe diagonal gesture for screenshot
* fix hyphenation dictionaries
* fix Kobo suspend support
* fix screen offset in Kobo Aura
* fix detection of two-fingers-pan gestures
* fix FC on Android with "Start with last opened file" checked
* fix crash on Kobo Mini and some marks of Kobo Touch
* fix font weight option not persistent
* add Android port of koreader
* language settings for Kobo finally work
* enlarge touch zone for readerfooter
* fix a memory leak when automatically detecting bbox
* export highlighted text in scanned page to Evernote
* return to home screen after exiting koreader for Kobo Mini, Touch and Aura
* add Yinxiang domain for Evernote plugin
* improvement on startup speed especially for reflowing mode
* persistent footer bar status between launchings
* invert effect when tapping on buttons
* add Evernote plugin to export highlights and notes

## [Stable release](https://github.com/koreader/koreader/releases/tag/v2014.04-stable)
* dewatermark option for pdf/djvu
* file copy/paste in filemanager
* language settings in reader menu
* highlight in EPUB document
* support link in EPUB/PDF document
* add battery icons in page header
* fix memory leak when reading EPUB document
* add dictionary support (PDF/Djvu/Epub)
* synchronize highlights in non-/reflowing modes (PDF/Djvu only)
* add goto page support (PDF/Djvu only)
* add highlight support (PDF/Djvu only)
* Translation for Turkish, German, Czech, Russian, French, Portuguese, Italian and Chinese
* Add two finger swipe/pan gesture
* bug fix in bbox calculation
* gettext support
* 2x reflow speed
* Touch support
* Scroll mode in PDF/DJVU
* Many features ported from the old code base.