================================================================
### koreader-nightly-20140524

**New features**:
* export highlighted text in scanned page to Evernote

**Enhancements**：
* language settings for Kobo finally work
* enlarge touch zone for readerfooter
* incremental export of highlights and notes to Evernote

**Bug fixes**：
* fix a memory leak when automatically detecting bbox

================================================================
### koreader-nightly-20140509

**Bug fixes**：
* return to home screen after exiting koreader for Kobo Mini, Touch and Aura

================================================================
### koreader-nightly-20140502

**New features**：
* add Yinxiang domain for Evernote plugin

**Enhancements**：
* improvement on startup speed especially for reflowing mode
* persistent footer bar status between launchings
* invert effect when tapping on buttons

================================================================
### koreader-nightly-20140424

**New features**：
* add Evernote plugin to export highlights and notes

================================================================
### koreader-nightly-20140408

**New features**：
* add dewatermark option for PDF/DJVU

================================================================
### koreader-nightly-20140405

**New features**：
* highlight current entry in TOC window
* tap on mini progress bar to hide it

================================================================
### koreader-nightly-20140327

**Enhancements**：
* K2pdfopt updated to latest version 2.15
* Luajit updated to latest version 2.1-beta
* License updated to GNU AGPLv3

================================================================
### koreader-nightly-20140311

**Bug fixes**：
* fixed tap gesture unresponsive in page flipping mode
* fixed semi-auto page crop in DJVU documents
* fixed a rare case of infinite loop when processing EPUB docs
* fixed a bug in processing font-family definition in EPUB css

================================================================
### koreader-nightly-20140214

**New features**：
* two finger swipe to right gesture to show Table of Content
* two finger swipe to left gesture to show bookmarks
* long press on progress bar to show Goto dialog

**Enhancements**：
* add full/mini progress bar options
* disable tap zone for bottom config panel

**Bug fixes**：
* fixed frontlight toggler on Kindle Paperwhite2

================================================================
### koreader-nightly-20140210

**New features**：
* exporting highlights to PDF document

**Enhancements**：
* keep up with latest crengine updates
* avoid unnecessary floating of CJK punctuations

**Bug fixes**：
* fixed no screen refresh when exiting from koreader in Kobo
* fixed wrong reading progress when switching between portrait and landscape screen mode
* fixed no default css when opening EPUB/FB2 document

================================================================
### koreader-nightly-20140124

**Bug fixes**：
* fixed font and margin settings missing when toggling floating punctuation on/off 
* several crash fixes

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
### koreader-nightly-20130627

**Enhancements**：
* turn off scroll mode by default for PDF/DJVU document
* turn off scroll mode temporally in page flipping mode
* turn on page mode automatically in zoom-to-page mode
* turn on scroll mode automatically in zoom-to-content mode

================================================================
### koreader-nightly-20130617

**New features**：
* highlight in PDF/djvu document

**Bug fixes**：
* fixed missing glyphs not rendered properly

================================================================
### koreader-nightly-20130614

**Bug fixes**：
* fixed blank screen when opening PDF document
* fixed native status bar shown in koreader in first launching
* fixed multiple screen refreshs when exiting koreader from kpvboolet

================================================================
### koreader-nightly-20130527

**Bug fixes**：
* fixed typeset issues when rendering Chinese charactors in dictionary window

================================================================
### koreader-nightly-20130521

**Bug fixes**：
* fixed lossing reading progress when switching view mode in EPUB document

================================================================
### koreader-nightly-20130503

**Enhancements**：
* word lookup in scanned page via OCR

**Bug fixes**：
* fixd highlight unavilable in some cropped pages
* fixed default page mode and screen mode uneffective
* fixed lookup word with puncuations

================================================================
### koreader-nightly-20130501

**New features**：
* dictionary lookup with Stardict dictionaries

================================================================
### koreader-nightly-20130428

**Enhancements**：
* save reading position in page in scroll mode
* add activity indicator when reflowing in Kindle

================================================================
### koreader-nightly-20130422

**Enhancements**：
* adjustment page margin including page top and bottom

**Bug fixes**：
* fixed crash when adjusting frontlight intensity with two finder panning
* fixed crash when switching from landscape to portrait in reflowing mode
* fixed blank screen when entering flipping mode in reflowing mode
* fixed partial blank screen when decreasing font size in reflowing mode

================================================================
### koreader-nightly-20130415

**New features**：
* add auto page cropping in PDF/DJVU document
* add page scrolling in PDF/DJVU document
* add swipe gesture to turning page in EPUB document
* add frontlight controller with two finger panning gesture

================================================================
### koreader-nightly-20130414

**Bug fixes**：
* fixed reflowing page in vertical writing direction

================================================================
### koreader-nightly-20130412

**Enhancements**：
* k2pdfopt updated to version 1.65
* k2pdfopt performance improvment
* add more languages support

================================================================
### koreader-nightly-20130410

**New features**：
* add multilanguage support and set according to locale

================================================================
### koreader-nightly-20130331

**New features**：
* add time display in reader menu

================================================================
### koreader-nightly-20130329

**New features**：
* add gestures for setting page zoom mode
* add gestures for rotating screen

================================================================
### koreader-nightly-20130327

**Enhancements**：
* return to previous page by swiping in page flipping mode

================================================================
### kindlepdfviewer-touch-nightly-20130325

**Bug fixes**：
* fixed page turning failure when page break line stays in the middle part of
the screen in scroll mode
* fixed crash when selecting TOC entries

================================================================
### kindlepdfviewer-touch-nightly-20130320

**New features**：
* add font size tuning in reflowing mode

**Enhancements**：
* rotate screen for 180 degress when reflowing vertically written document

================================================================
### kindlepdfviewer-touch-nightly-20130319

**Bug fixes**：
* fixed returning previous page with swipe even exited from flipping mode
* fixed saved page position not right in scroll mode

================================================================
### kindlepdfviewer-touch-nightly-20130318

**Enhancements**：
* add home icon in top menu to return filemanager

**Bug fixes**：
* fixed screen not refreshing when exiting from screensaver

================================================================
### kindlepdfviewer-touch-nightly-20130317

**Enhancements**：
* improve UI in config panel
* adjusting manual cropping box with swiping gestures

**Bug fixes**：
* fixed no recalculation of menu width when switching to landscape


================================================================
### kindlepdfviewer-touch-nightly-20130316

**Enhancements**：
* touch friendly reader menu

**Bug fixes**：
* fixed Home key unresponsive in Kindle Touch
* fixed repeating of page in scroll mode
* fixed some page not rendered completely in scroll mode
* fixed loop page turning at the first and the last pages

================================================================
### kindlepdfviewer-touch-nightly-20130313

**Enhancements**：
* multithreading when reflowing
* disabling hinting in config panel, flipping mode and manual cropping

**Bug fixes**：
* fixed page tuning direction not the same with swipe direction in flipping mode
* fixed cannot remember new position in flipping mode
* fixed showing native status bar when reading

================================================================
### kindlepdfviewer-touch-nightly-20130312

**Bug fixes**：
* fixed full screen setting uneffective in scroll mode

================================================================
### kindlepdfviewer-touch-nightly-20130311

**New features**：
* add scroll mode for PDF/DJVU document

**Bug fixes**：
* fixed hinting invalid with wrong parameters

================================================================
### kindlepdfviewer-touch-nightly-20130308

**New features**：
* add screenshot function with two finger tap on diagonal corners of the screen

================================================================
### kindlepdfviewer-touch-nightly-20130306

**Bug fixes**：
* fixed scroll mode setting not saved for EPUB document
* fixed initial crop box exceeding page dimension

================================================================
### kindlepdfviewer-touch-nightly-20130304

**New features**：
* add swipe gesture to turn page
* add flipping mode with tap on top-left corner of the screen

================================================================
### kindlepdfviewer-touch-nightly-20130228

**Bug fixes**：
* fixed crash on multitouch gestures

================================================================
### kindlepdfviewer-touch-nightly-20130225

**New features**：
* add reading pregress bar
* add bookmark toggler at top-right corner

**Enhancements**：
* cofirm crop box by double tap gesture
* set default page background color to white
* full screen refresh every 6 page turns

================================================================
### kindlepdfviewer-touch-nightly-20130222

**New features**：
* add contrast setting for PDF document
* auto set zoom-to-content-width mode in landscape mode

**Enhancements**：
* more anchors for cropping box
* add confirm/cancel buttons for cropping dialog

================================================================
### kindlepdfviewer-touch-nightly-20130220

**New features**：
* add KUAL extension
* filter out sdr directories

**Bug fixes**：
* fixed zoom mode not restored when switching from non-reflowing mode to
reflowing mode

================================================================
### kindlepdfviewer-touch-nightly-20130219

**Bug fixes**：
* fixed 10 pixels mismatch between screen width and actual resolution
* fixed no recalculation of page size when cropping

================================================================
### kindlepdfviewer-touch-nightly-20130217

**Bug fixes**：
* fixed crash when opening TOC menu in PDF document without TOC

================================================================
### kindlepdfviewer-touch-nightly-20130213

**Bug fixes**：
* fixed unable to rotate screen in config panel
* fixed unable to save screen mode

================================================================
### kindlepdfviewer-touch-nightly-20130209

**Bug fixes**：
* fixed cannot apply cropping settings instantly

================================================================
### kindlepdfviewer-touch-nightly-20130206

**New features**：
* add landscape screen mode

================================================================
### kindlepdfviewer-touch-nightly-20130204

**New features**：
* add manual page cropping for PDF document

================================================================
### kindlepdfviewer-touch-nightly-20130123

**Enhancements**：
* K2pdfopt updated to version 1.64a

================================================================
### kindlepdfviewer-touch-nightly-20130122

**Enhancements**：
* use embeded CSS in EPUB document by default
* use optional stylesheet shipped with crengineEPUB

================================================================
### kindlepdfviewer-touch-nightly-20130118

**Bug fixes**：
* fixed crash when hinting last page

================================================================
### kindlepdfviewer-touch-nightly-20130116

**Enhancements**：
* add more reflowing options

================================================================
### kindlepdfviewer-touch-nightly-20130110

**Bug fixes**：
* fixed crash when entering screensaver
* fixed full screen refresh failure in Kindle Paperwhite

================================================================
### kindlepdfviewer-touch-nightly-20130107

**New features**(preview release):
* integrate koreader into native system with kpvbooklet
* reflowing almost done
* switching between non-reflowing mode and reflowing mode on the fly

================================================================
### kindlepdfviewer-nightly-20121222

**Enhancements**：
* K2pdfopt updated to version 1.63

================================================================
### kindlepdfviewer-new-ui-demo

**New features**：
* experimentally support Kindle Paperwhite and Kindle Touch

================================================================
### kindlepdfviewer-nightly-20121122

**Enhancements**：
* turning on multithreading by default
* customizable reflowing parameters

**Bug fixes**：
* fixed a memory leak in reflowing
* fixed reader unresponsiveness caused by cache manager
* fixed crash when mamually crop page in multithreading mode

================================================================
### kindlepdfviewer-nightly-20121117

**Enhancements**：
* K2pdfopt updated to version 1.62

**Bug fixes**：
* fixed last line not shown in reflowing mode

================================================================
### kindlepdfviewer-nightly-20121115

**Enhancements**：
* decrease default word gap parameter for better reflowing on Chinese document

================================================================
### kindlepdfviewer-nightly-20121114

**Bug fixes**：
* fixed togglering multithreading also triggers reflowing
* fixed notification of Rendering in background not disappear
 
================================================================
### kindlepdfviewer-nightly-20121113

**New features**：
* add multithreading mode for better reflowing performence

**Enhancements**：
* set default column size to 2

================================================================
### kindlepdfviewer-nightly-20121111

**New features**：
* add crop page before reflowing option

**Enhancements**：
* avoid contrast processing when contrast is set to 1.0
* use compilation parameter -O3 for better performance

**Bug fixes**：
* fixed choose reader dialog not closed when opening file
* fixed text lost in pre-cropped document
* fixed paged displayed center

================================================================
### kindlepdfviewer-nightly-20121109

**Bug fixes**：
* fixed reader association problem

================================================================
### kindlepdfviewer-nightly-20121106

**New features**：
* add reflowing quality option
* add defect size option

**Enhancements**：
* K2pdfopt updated to version 1.60