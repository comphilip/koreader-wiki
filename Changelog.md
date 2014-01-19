================================================================
### koreader-nightly-20140119

**New features**：
* highlighting in EPUB document
* following links in PDF/EPUB document (use swipe right gesture to return to previous position)
* language setting in reader menu
* file copy/paste/cut/delete operations in filemanager

**Bug fixes**：
* fixed inconsistent left/right margins in EPUB document
* fixed bookmark dogear not shown properly in EPUB document
* fixed partial screen not refreshed after resuming from screensaver if launched by KUAL

**Enhancements**：
* larger font sizes range in EPUB document, with font size fine tuning

================================================================
### koreader-nightly-20140108

**New features**：
* Chinese punctuation taboo implementation

**Bug fixes**：
* fixed invalid document cache after chaning page margin in EPUB document

================================================================
### koreader-nightly-20140105

**New features**：
* battery icon in page header when reading EPUB document
* bookmark flipping mode by holding at top-right corner of screen

**Enhancements**：
* page overlap toggler in reader menu

================================================================
### koreader-nightly-20140104

**New features**：
* (experimental) regional zoom in PDF page by tap on top-left corner on screen

**Enhancements**：
* K2pdfopt updated to latest version 2.14
* invert color in menu item when tapping

**Bug fixes**：
* fixed a memory leak when reading EPUB document
* fixed page margin setting not persistent

================================================================
### koreader-nightly-20131230

**Enhancements**：
* reader menu and reader config panel shown simultaneously
* auto saving reading progress by editting defaults.lua
* notifying window when opening document

**Bug fixes**：
* fixed frontlight intensity cannot be saved in Kobo
* fixed auto CSS detection
* fixed page margin settings cannot be saved
* fixed missing XPS document handler

================================================================
### koreader-nightly-20131227

**Enhancements**：
* accommodation of dictionary window position
* invert color when selecting in filemanager
* increased font size in filemanager

**Bug fixes**：
* fixed losing reading progress when changing font size, font face and page margins
* fixed font size setting cannot be saved in EPUB document
* fixed rendering problem on Kobo devices

================================================================
### koreader-nightly-20131225

**New features**：
* dictionary lookup in EPUB document

================================================================
### koreader-nightly-20131217

**New features**：
* customizable tap zones for page turning
* current time can be shown in progress bar in PDF/DJVU document

**Enhancements**：
* show page overlap in non-scroll mode bt default
* return to Nickel when exiting Koreader in Kobo

**Bug fixes**：
* fixed dictionary lookup not working properly in reflowing mode
* fixed menu items rendered out of menu window
* fixed less responsive UI after running for a while in Kobo

================================================================
### koreader-nightly-20131202

**Enhancements**：
* K2pdfopt updated to latest version 2.12

**Bug fixes**：
* fixed word picking failure in multicolumn PDF pages in reflowing mode
* fixed history file list not sorted by last accessed time
* fixed koreader cannot be launched in some 3G Paperwhite2 models

================================================================
### koreader-nightly-20131128

**New features**：
* add Kindle Paperwhite2 and Kobo Aura support

**Enhancements**：
* new blitbuffer for 4-bit(Kindle), 8-bit, 16-bit(Kobo), 24-bit and 32-bit framebuffer devices

**Bug fixes**：
* fixed full refresh bug in new blitbuffer

================================================================
### koreader-nightly-20131029

**Enhancements**：
* code refactoring (avoid usage of global variables)
* code refactoring (new blitbuffer implemented with lua ffi)
* more smooth scroll in scroll mode
* calculate word gap in reflowing mode
* calculate indendtation in reflowing mode

**Bug fixes**：
* fixed word picking problems in reflowing mode
* fixed screen refresh failure caused by Enter key in Goto dialog
* fixed highlighting failure when highlighted line only has one word

================================================================
### koreader-nightly-20131018

**Enhancements**：
* reader Goto now supports EPUB document in page mode
* reader Goto now responses Enter key

**Bug fixes**：
* fixed non-ASCII characters not shown in dictionary window in Kobo
* fixed non-ASCII words cot picked up for dictionary in Kobo
* fixed fallback font too large in Kobo Aura HD
* fixed fallback font missing for CSS definded font family

================================================================
### koreader-nightly-20131016

**Enhancements**：
* MuPDF updated to latest version 1.3
* K2pdfopt updated to latest version 2.03
* hiting for 2 pages by default ( or any arbitary value of DHINTCOUNT specified in default.lua)
* better cache memory management to decrease crash frequency of native framework
* interoperable highlight between reflowing and non-reflowing mode for PDF/DJVU document

**Bug fixes**：
* fixed menu page count not shown when pages exceeding 10
* fixed reader crash when rendering some PDF pages in landscape
* fixed menu widget rendered out of screen

================================================================
### koreader-nightly-20130801

**New features**：
* add reader Goto support

**Enhancements**：
* disabling double tap gesture by default for more responsive UI

**Bug fixes**：
* fixed A2 refreshing ineffective when scrolling in PDF/DJVU document
* fixed virtual keyboard not shown completely in landscape
* fixed delete characters in blank inputbox would make subsequent input invalid

================================================================
### koreader-nightly-20130731

**Bug fixes**：
* fixed line cannot wrap in dictionary window
* fixed two-column mode for EPUB document in landscape

================================================================
### koreader-nightly-20130725

**New features**：
* support for font-face definition in EPUB CSS

================================================================
### koreader-nightly-20130724

**Bug fixes**：
* fixed blank lines at the bottom of dictionary window

**Enhancements**：
* full refresh when changing dictionary
* A2 refresh when scrolling in PDF/DJVU document

================================================================
### koreader-nightly-20130722

**New features**：
* support word lookup in multiple dictionaries
* tap on dictionary title will make current dictionary default on current document
* support Chinese word lookup

================================================================
### koreader-nightly-20130721

**New features**：
* add document language option for PDF/DJVU document for OCR

**Bug fixes**：
* fixed auto-crop failure in some PDF pages
* fixed cannot picking up single character in Chinese document

**Enhancements**：
* auto set small word gap when selecting CJK document language
* save last used config panel

================================================================
### koreader-nightly-20130714

**Bug fixes**：
* fixed inconsistent saved settings when opening documents from different relative paths

**Enhancements**：
* add semi-auto page crop
* two orientations for landscape

================================================================
### koreader-nightly-20130713

**Bug fixes**：
* fixed swapped x,y coordinates for touch events in Kobo touch
* fixed forked process not exits after reader crash
* fixed reader crash when holding in blank page

**Enhancements**：
* detect device DPI in Kobo
* use fixed-point algorithm in page reflowing for better performence

================================================================
### koreader-nightly-20130703

**Enhancements**：
* add config file koreader/defaults.lua

================================================================
### koreader-nightly-20130630

**New features**：
* add page margin setting for EPUB document

================================================================