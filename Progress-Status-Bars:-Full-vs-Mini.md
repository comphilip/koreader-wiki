In KOReader, there are two types of progress/status bars available during reading a book: one at the top of the screen, and another at the bottom. The bottom menu gives two options, "mini" and "full".

**1** The option "mini" gives the bottom-side bar (or, status bar) located at the bottom of the page, which can be hidden by tapping on it. Its settings can be accessed from the KOReader menu: Gear - Status bar. There you can toggles icons you would like to see, as well as some advanced settings like progress bar existence/appearance and other fine tuning. \
It has two modes which affect page rendering: in Settings -> "Reclaim bar height from bottom margin". If **Reclaim is on**, then all the pages will be rendered until the page margin defined via bottom menu, so the mini bar might overlap with text if the bottom margin is too small. This mode suggests that the mini bar should be hidden most of time and called by a tap at the bottom only when needed. If **Reclaim is off**, then bottom margin starts at least above the mini bar height, so you can leave it on while reading since it won't overlap.

**2** The option "full" gives both bottom-side and top-side status bar. The latter is rendered by the CR engine, it is located at the top of a page, and it cannot be hidden. Once you activate it, all pages in the book are re-rendered taking into account the top progress bar's height (and bottom progress bar's too with the Reclaim option on). 
Its settings can be accessed from the file: `koreader/data/cr3.ini`.
Make sure not to alter any settings which you don't know in this file except those related to the full progress bar you would like to tweak. \
The appearance is controlled by: \
crengine.page.header.chapter.marks=1 \
crengine.page.header.font.color=0xFF000000 \
crengine.page.header.font.face=Noto Sans \
crengine.page.header.font.size=10

The icons that appear on the progress bar are selected here: \
window.status.battery=1 \
window.status.battery.percent=0 \
window.status.clock=1 \
window.status.line=0 \
window.status.pos.page.count=0 \
window.status.pos.page.number=0 \
window.status.pos.percent=0 \
window.status.title=1

***

Here is an example of both progress bars visible. The full one has Author name, Book title, chapter marks on, time and battery icons. The mini one has page count, the title of the current chapter, how many pages left until the next chapter and the total progress percentage.
***
![](https://i.imgur.com/dMcmNcD.png) 