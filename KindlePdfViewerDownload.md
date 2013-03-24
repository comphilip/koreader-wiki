# Download Page
This page lists latest builds of kindlepdfviewer. You can also consider it as an unofficial changelog. ;-P
These builds are for Kindle with keyboard (Kindle 2, DX, DXG, K3) **not for Kindle 4 (NT or Touch) or Paperwhite**. This is the easiest way to get the latest and greatest version of the reader on which developers are working right now. Versions are anotated by git sha string.

## [Nightly builds of master branch](https://code.google.com/p/kindlepdfviewer-package/downloads/list)

* Added `S` command to crereader: css selection menu
* Added `Alt-S` command to crereader: toggle embedded stylesheet
* Updated reflow library (k2pdfopt) to version 1.64a
* Bug fix for page cache

## [Release 2013.1 (kindlepdfviewer-v2013.1)](https://kindlepdfviewer-package.googlecode.com/files/kindlepdfviewer-v2013.1.zip)

* Optimize loading crengine ebooks (fb2, epub, etc)
* Upgrade reflow library (k2pdfopt) to 1.6.3
* Enable hyphenation engine for crengine files (fb2, mobi, epub, etc)
* Add `V` command for crereader to switch between scroll and page viewing modes on the fly
* Fix screen rotation for crengine-related ebooks
* Make "page" viewing mode default (same look and feel as standalone CoolReader3)
* Bugfixes for "page" viewing mode
* Upgraded crengine to the latest version cr3-3.1.2-27
* Enable chapter marks in crereader header
* Cosmetic bugfix for displaying boxes around links
* Don't show overlap when panning in fit content width mode
* Other minor bugfixes

## [Release 2012.11 (kindlepdfviewer-v2012.11)](https://github.com/downloads/hwhw/kindlepdfviewer/kindlepdfviewer-v2012.11.zip)

* Explain `C` command as "align viewport to top/bottom" and make bottom alignment default in single-column mode as well as two-column
* Upgraded muPDF to the latest version with much better rendering of scanned files (make sure they are 300dpi or higher --- _never_ downsample your images!)
* Upgraded LuaJIT to the latest version (various bugfixes)
* Memory leak in KOPTReader fixed
* Lots of enhancements and bugfixes to KOPTReader (the PDF/DjVu reader with reflow)
* Support for deleting bookmarks in crengine (fb2, mobi, epub, etc)
* Force file manager in portrait mode on startup and on closing the document
* Make `O` command (overlap enable/disable) more robust
* Allow entering screensaver from a Help page
* Share .zip format between PDFReader and CREReader (handled by reader-chooser infrastructure)
* Optimized redrawing the current page
* Add any jump from a link (regardless of the distance from source page) to the Jump History list
* Multi-threaded precache in KOPTReader (can be disabled via `Aa` config)
* Uniform timeout (1.5s) for all popup-messages
* Compile djvulibre and LuaJIT as shared libraries
* Move KOPTReader into a separate module and compile as shared library
* Full File Manager functionality (inc files with no extensions)
* Added `Alt-.` command to toggle battery logging to `batlog.txt` file
* Fixed deleting highlights via `Shift-N` command
* Re-sort Last Documents list on open/close of a file

## [Release 2012.10 (kindlepdfviewer-v2012.10)](https://github.com/downloads/hwhw/kindlepdfviewer/kindlepdfviewer-v2012.10.zip)

* Added `Alt-S` command to PDF reader to extract all attachments on the current page. The attachments are saved in the same directory as the PDF file with their original filenames (i.e. those used when they were created). You can use either our own free `pdfattach` script (in the utils directory of source distribution) or Adobe Acrobat Pro commercial software to generate PDF files with other files embedded in them.
* "PDF and DjVu reflow" feature. In quotes because really it is much more subtle and powerful than the conventional PDF reflow that is based on the extraction of characters from the PDF and rendering their glyphs at any desired magnification. More accurately this new feature should be called "adaptive real-time image analysis" as it analyzes the page image and splits it into sub-image groups, preserving those entities (like mathematical formulas) which must be kept as a whole.
* Reader chooser infrastructure. Opening the file for the first time allows to choose between multiple readers (if there are any, e.g. for PDF and DjVu between standard and reflow flavours) and remember this association either on per-file or on per-file-type basis.
* Link shortcuts for crengine formats (epub, mobi, fb2, chm, html...)
* Picture viewer (currently supports colour and grayscale JPEG files)
* Fixed performance issue with viewing scanned books in two column mode
* Added TTS (text to speech) support (in EXPERIMENTAL mode only)
* Removed page rendering indicator as it affects performance
* Full screen refresh after each page by default
* Disabled crengine warnings and debug messages (which can happen at the rate of thousand per second!)
* Don't crash on opening files via stale history entry
* Show detailed DjVu page info in `Menu`
* Show program version in file manager Help header (`H` key)
* Don't kern text in menu items (set with monospaced font)
* Added `O` command which toggles showing overlapping page areas via dimmed box
* Adjust the font size used by each PDF local link shortcut to match the link size
* Added `Shift-L` command to toggle showing underlines for local links
* Added `Alt-H/J` commands for cycling through TOC entries in PDF/DjVu files
* Added `Alt-K/L` commands for cycling through bookmark entries
* Added `C` command for "comics mode" (useful for some other books too, not just comics)
* Added ability to jump to any location in TOC (and other menus) quickly by pressing numbers 1,2,...,0. This is useful for books with huge Table of Contents lists like encyclopedias and dictionaries.

## [Release 2012.09 (kindlepdfviewer-v2012.09-2-g53a6049)](https://github.com/downloads/hwhw/kindlepdfviewer/kindlepdfviewer-v2012.09-2-g53a6049.zip)

* panning in fit to content mode will return to fit to content on page change
* information about folders
* improved support for GUI-configurable font faces
* calculator (`Shift-K` in file manager)
* deleting bookmarks
* deleting highlights via `Shift-N` list
* better support for reading in twocolumn mode
* more consistent handling of `<>` (Prev/Next) page keys in `Shift-S` (fit content) mode
* page rendering indicator - flashing boxes on top of screen, one for each page
* cache crengine DOM in `cr3cache` directory to speed up repeated file open
* Multi-level TOC support (`Right`/`Left` - expand/collapse, `Shift-Right` - expand all)
* `filemanager_expert_mode` setting to rename any files (not just ones associated with reader)
* `Alt+<>` - zoom in 1% steps
* `Shift+Up/Down` - increase / decrease Y-panning step
* `Shift+Left/Right` - decrease / increase X-panning step
* `M` - zoom mode menu
* `R` - DjVu rendering mode menu
* In `Menu` mode `C` clears internal cache and `D` clears document cache
* `Shift+R` - Set the number of page turns before a full screen refresh (0 to always do full refresh)
* crereader: fast navigation using `Shift+fiveway`: jump to previous / next TOC-entry; scroll 10 pages backwards / forward
* upgraded crengine to 3.0.57-15

[Build 2012-08-29 (kindlepdfviewer-25edd31.zip)](https://github.com/downloads/dpavlin/kindlepdfviewer/kindlepdfviewer-25edd31.zip)

* opening TOC positions you to correct place in the tree
* Long file names are cut off in the info window Issue #214
* improvements to inputbox @NuPogodi
* shift+K to get calculator in filechooser @NuPogodi
* search highlight in CoolReader engine @dpavlin

[Build 2012-08-26 (kindlepdfviewer-0f22302.zip)](https://github.com/downloads/dpavlin/kindlepdfviewer/kindlepdfviewer-0f22302.zip)
* djvu gamma support and render mode by @tigran123
* highlight search terms using new dot shortcut (in pdf and djvu only) @dpavlin
* fixed inputbox default value
* Bug fix for font handling (cache deadlock)
* Current font can be made the default font in CREngine mode by Shift-F
* Jump-to-percentage dialog in CREngine mode (ebook formats) with "G" key press
* Kindle 2 compatibility by setting a key code
* Fix wrong page count in help page, reported by Verci
* Handle USB cable plug in/out events
* Screenshot in BMP & PGM format, by @NuPogodi

## [Release 2012.05 (kindlepdfviewer-202b6fc.zip)](https://github.com/downloads/hwhw/kindlepdfviewer/kindlepdfviewer-202b6fc.zip)
* `Shift`+`X` shortcut to select page crop using top-left and bottom-right point #35
* `Shift`+`P` shortcut to do screenshot. Raw image will be stored in `kindlepdfviewer/screenshots/`. (Patch by NuPogodi)
* Document type detection for zip files. (Patch by NuPogodi)
* Bug fix in inputbox, previously, it has issue with deleting.
* long lines (filenames in 'Document Info') are now splitted in more human-readable way @NuPogodi
* fonts selection in filemanager (key 'F' or 'Aa') shows how font looks like @NuPogodi
* preserve position inside cr-documents (epub, mobi, ...) when chaning fontface or line spacing @NuPogodi
* TOC-menu and Fonts Menu  highlight the current item @NuPogodi
* Nice icons (by NuPogodi)
* File management functions (by NuPogodi)
* Faster cursor in highlighting mode
* kite support files (as suggested by NuPogodi)

## [Release 2012.04.2 (kindlepdfviewer-bb5c54d.zip)](https://github.com/downloads/hwhw/kindlepdfviewer/kindlepdfviewer-bb5c54d.zip)
* Add mobi, zip, doc format support
* Fix bugs in left page backward key handling
* Fix bugs in highlight feature
* Show current page in goto page inputbox
* Fix bug in creader's font setting menu
* Fix bug in creader's help page
* Fix bug in select menu (sometimes cannot select with five way key in DXG)
* Fix font setting bug for some documents supported by CREngine.
* Fix wrong page number in DjVu's TOC.
* New shortcut `x` to show bounding box of document or manually cropped area in current page.
* Key repetition in file chooser and in document view

## [Release 2012.04.1 (kindlepdfviewer-30766f8.zip)](https://github.com/downloads/hwhw/kindlepdfviewer/kindlepdfviewer-30766f8.zip)

* We skipped announcing Release 2012.04, since some last-minute bug fixes came up
* InfoMessage dialog on slow operations (search, open file, etc)
* New launchpad shortcut `Shift`+`P`+`K` which kills Amazon framework before start to free up more memory (somewhat important on DXG with scanned pdfs). `Shift`+`P`+`L` will open last document without framework. `Shift`+`P`+`R` will restart the framework (try this if you have your kindle frozen).
* Menu in reading mode
* Fix for buggy rotation of pages that specify their own rotation (PDF)
* XPS and basic CBZ support (no CBR yet, sorry)
* EPUB, TXT, RTF, HTML, FB2, CHM support ¿?Thanks to CREngine¿?
* Input passwords for PDFs
* Help page
* Cursor support in inputbox
* Bug fix in menus
* Shortcut for manual full screen refresh, `Shift`+`R`.
* Configurable entry in `.reader.kpdfview.lua` for partial refresh counts.
* Improved memory usage control
* Text highlight in DjVu
* Text highlight in Pdf
* Bug fix in screen saver
* Bug fix in filechooser
* Show overlap when moving with pan_by_page


## [kindlepdfviewer-7b120b0 (Release 2012.03)][v2012.03]

* DJVU support
* Human readable and editable settings files
* New key binds `Home`, used to exit program directly while reading
* One bug fix in fit-to-content mode
* Two bug fixes in two column mode
* Compile with optimization options enabled, much faster
* Jump history can be restored when you open the book next time
* Notes support for jump history. notes are auto generated according to the TOC section where the page is in. you can change it by editing the book setting file (the one that generated in the same directory with your book).
* New two column mode without margins, invoked by `Shift`+`F`
* Improved file browser: 
  * Navigate throughout entire filesystem
  * Manage unreadable dirs
  * Show current path on last line;
* Add "single file mode": if kpdfview called without any file/folder param, open last viewed file;
* Bug fixes in reading Table of Content
* Duokan style menu item shortcuts
* Fast jump by percent, refer to the **move section** in [Short Cut Guide][shortcut_guide].
* The behavior for page turn is now consistent with kindle native reader in fit_to_content_width mode. (i.e. do a real page turn until hit page bottom)
* You can now change default settings for your reader in `.reader.kpdfview.lua`. Refer to **settings section** of [user guide][user_guide].
* Manual page crop, refer to [Short Cut Guide][shortcut_guide].
* 90 degree rotation support. `Shift`+`K` and `Shift`+`J`.
* Reading progress bar with Key `Menu`.
* Goto input box in reading mode.
* Rewrite caching strategy.


## [kindlepdfviewer-09c6c10][09c6c10]

* Bug fix in toc entry, delete empty boxes at the end of the entry (please fire a bug report if you still find empty boxes in TOC entry)
* Bug fix in shiftmode and altmode recording
* Bug fix in refreshing screen after kpdfviewer exits
* Bug fix in filesearcher. (search recursively now)
* Landscape five up support in two-column mode


## [kindlepdfviewer-de1725d][de1725d_two_columns]

* Add two-column zoom mode, please refer to [this post][de1725d_release_note]. dpavlin also made a [video demo][two_column_demo] ;-)
* Switch BACK and ALT+BACK key binding
* Bug fix in font reseting 
* Add font menu in search result window


[09c6c10]:https://github.com/downloads/houqp/kindlepdfviewer/kindlepdfviewer-09c6c10.zip
[v2012.03]:https://github.com/downloads/hwhw/kindlepdfviewer/kindlepdfviewer-7b120b0.zip
[de1725d_two_columns]:https://github.com/downloads/dpavlin/kindlepdfviewer/kindlepdfviewer-de1725d.zip
[de1725d_release_note]:http://www.mobileread.com/forums/showpost.php?p=1986344&postcount=93
[two_column_demo]:http://www.youtube.com/watch?v=moiRFi6Ttp4
[78efdc7_test]:https://github.com/downloads/dpavlin/kindlepdfviewer/kindlepdfviewer-78efdc7.zip

[shortcut_guide]:https://github.com/hwhw/kindlepdfviewer/wiki/ShortCutsForPdfReader
[user_guide]:https://github.com/hwhw/kindlepdfviewer/wiki/Userguide
