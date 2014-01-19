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
