In KOReader, there are two types of progress/status bars available during reading a book: the main one at the bottom of the screen (with more features), and the legacy one at the top of a page.


**1. The Main Status Bar (at the bottom of a page)** is available in both CR-engine files (epub, fb2, etc) and muPDF-engine files (PDF, etc). It is configured from Top Menu -> Gear -> Status Bar. There you can toggles icons you would like to see, as well as some advanced settings like progress bar existence/appearance and other fine tuning. \
It has two modes which affect page rendering: in Settings -> "Reclaim bar height from bottom margin". If **Reclaim is on**, then all the pages will be rendered until the page margin defined via bottom menu, so the mini bar might overlap with text if the bottom margin is too small. This mode suggests that the mini bar should be hidden most of time and called by a tap at the bottom only when needed. If **Reclaim is off**, then bottom margin starts at least above the mini bar height, so you can leave it on while reading since it won't overlap. \
By default, the Main Status Bar has the **"Lock status bar"** option unchecked, meaning that tapping on it will make it cycle through items which did not fit on current length of the status bar, and ultimately hide the status bar. To reveal it, tap once again. If you want to have the status bar always visible through taps, check this option. \
**Tap and hold** the Main status bar to bring up the "Skim" dialog. \
Swiping along the progress bar right/left will make the reader jump to the next/previous book chapter, respectfully. You can also configure **which level labels from Table of Content (ToC)** have marks shown on the progress bar, as well as which marks are used for swiping and showing current chapter title (if such options is checked).

**2. Alternative Status bar (at the top of a page)** is available only in CR-engine files since it is tied to that engine. It can be enabled from Bottom Menu -> Gear - "Alt Status Bar". The status bar is located at the top of a page, and it cannot be cycled or hidden via taps. Once you activate it, all pages in the book are re-rendered taking into account the top progress bar's height and there is no "Reclaim" option alternative. The Alt status bar settings can be accessed from the file: `koreader/data/cr3.ini`.
Make sure not to alter any settings which you don't know in this file except those related to the Alt status bar you would like to tweak. \
The appearance is controlled by:
```lua
crengine.page.header.chapter.marks=1
crengine.page.header.font.color=0xFF000000
crengine.page.header.font.face=Noto Sans
crengine.page.header.font.size=10
```

The icons that appear on the progress bar are selected here:
```lua
window.status.battery=1
window.status.battery.percent=0
window.status.clock=1
window.status.line=0
window.status.pos.page.count=0
window.status.pos.page.number=0
window.status.pos.percent=0
window.status.title=1
```

***

Here is an example of both progress bars visible. The Main one has Author name, Book title, chapter marks on, time and battery icons. The Alt one has page count, the title of the current chapter, how many pages left until the next chapter and the total progress percentage.
***
![](https://i.imgur.com/dMcmNcD.png) 