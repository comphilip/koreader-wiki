
# ShortCuts for Reader
This page aims to list all the available shortcuts that you can use when reading documents (curently supported PDF and DJVU formats).

Tips: `>` stands for page down key and `<` stands for page up key, `+` stands for volumn plus key.


> **NOTICE! NOTICE! NOTICE! NOTICE!!!**

### This page is obsoleted and will not be maintained anymore, if you are using release 2012.04 or newer, please press `h` key while reading and refer to the help page. 


***


## Move
* next page:
`>`

* previous page:
`<`

* 0% of document (i.e. first page):
`1`

* 11% of document:
`2`

* 22% of document:
`3`

* 33% of document:
`4`

* 44% of document:
`5`

* 55% of document:
`6`

* 66% of document:
`7`

* 77% of document:
`8`

* 88% of document:
`9`

* 100% of document (i.e. last page):
`0`

* jump to a specific by number:
`G`

## Zoom
* zoom to fit content height:
`Shift` + `D`

* zoom to fit content width:
`Shift` + `S`

* zoom to fit content:
`Shift` + `A`

	min(fit content height, fit content width)

* zoom to fit page height:
`D`

* zoom to fit page width:
`S`

* zoom to fit page:
`A`

	min(fit page height, fit page width)

* zoom to first column:
`F`

	this will activate manual zoom described below, use fiveway to navigate down,right or up,left

* zoom to first column without margins:
`Shift` + `F`

	useful if you get unneeded white margin on top and left when using just `F`

## Zoom manually

* zoom in by incrementing 20%:
`Shift` + `>`

* zoom in by incrementing 10%:
`Alt` + `>`

* zoom out by decrementing 20%:
`Shift` + `<`

* zoom out by decrementing 10%:
`Alt` + `<`

When in this mode, you can pan around page using `fiveway` directions.
For smaller steps in panning press `shift` (half of normal move) or `alt` (fifth of normal move).

If you press `fiveway`, you will enter special mode in which you can move in any direction by whole screen size which is useful for high zoom levels in multi-column pdf layouts. In this mode, you can still move in small steps using `shift` or `alt` to fine-tune your position. Press `shift` and `fiveway` to reset your panning position to top-left.
Position will be reset to top of page if you press `left` or `right` (you just press `down` to get to bottom of column and then `right` to get to top of next column to the right). Position will be reset to top-left on each page change.

## Manual cropping using custom bounding boxes

Manual cropping allows you to override document's idea of page bounding box which is used to zoom to content and two-column modes (which is handy if two columns are not on page center)

DJVU documents don't have bounding boxes, so zoom to content modes are same as page modes without specifying custom bbox.

Cropping is defined on odd/even page level and for page on which bounding box is defined. This allows easy default for all pages using odd and even definitions, while allowing custom bounding box for few pages which might differ from rest of document.

* define bounding box using displayed page as template:
`Z`

* remove custom bbox for current page:
`Shift` + `Z`

* toggle custom bbox on/off:
`Alt` + `Z`

## Gamma
* increase Gamma (darker):
`+`

* decrease Gamma (dimmer):
`-`


## Rotate

* rotate 10 degrees couterclockwise:
`K`

* rotate 10 degrees clockwise:
`J`

* rotate screen 90 degrees counterclockwise:
`Shift`+`K`

* rotate screen 90 degrees clockwise:
`Shift`+`J`


## Jump history

* show
`B`

* add current page to jump keeper
`Shift`+`B`

* back to last jump
`Back`


## Misc
* reading progress bar
`Menu`

* save settings, exits and back to filechooser:
`Alt`+`Back`

* exit kpfview and back to native system
`Home`

* show table of contents:
`T`
