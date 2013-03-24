This page is to serve as tips for some useful but not easy to find features or tricks.

## font setting trap for fonthack users
[Reference](https://github.com/hwhw/kindlepdfviewer/issues/700#issuecomment-12154312)

Usually you can see all the droid fonts, host fonts, and any ttf fonts you placed under kindlepdfviewer/fonts directory in font selection, but if you are fonthack user and selected kindle system fonts (host fonts under /host directory in font settings) for one font, for example cfont, then you may found that after that font selection, you can only see kindle system fonts for cfont. This is caused some conflict between fonthack and kindlepdfviewr font path. You can restore the font selection to any droid font by editing the settings.reader.lua, then you will be able to select all kinds of font again. So please remember never select the host fonts in font selection. If you do want a kindle system font, you can copy that font to the kindlepdfviewer/fonts directory and select it there.


## Shift-X usage
[Reference](https://github.com/hwhw/kindlepdfviewer/issues/457#issuecomment-9519967)
You can define crop box for odd and even pages of pdf with Shift-X.

1. Press A to see the full page
1. Press Shift-X and set the boundaries (top-left and bottom-right) of the bbox appropriately. Note you can use the keyboard shortcut to select some position directly instead of keep moving cursor.
1. Press Next to go to the next page.
1. Press Shift-X and do the same for this page also.
1. Press Prev to go back to the previous page (assuming that is where you want to start reading).
1. Press Shift-S and enjoy reading. This is "fit content-width" mode, so the screen area will be used fully. When you finished reading on current screen, press page down will bring to the remaining part of current page, and that part can be less than one screen which is normal. There is feature suggestion on "scroll mode" which will connect next page to the remaining part of current page, but that is not easy to implement right now.

## Jump in last documents list
[Reference](https://github.com/hwhw/kindlepdfviewer/issues/508)
In other part of kpv user can often jump to certain position of a list directly by pressing keys listed before items of list. This is not available in "Last Documents" (by pressing L in file browser) list because this is a part of file browser which is quite different with other lists.

Though user still have plenty of options to locate an item in "Last Documents" quickly:

1. Press Numbers (Alt-Q... Alt-P) to jump to 10%, 20%,... 0% of the list instantly. Note user can press the first line of keyboard directly without the Alt modifier to input numbers in other places, but Alt modifier is needed in this case.
1. Press s to search, which can filter result quickly.
1. Just press and hold the five way button, the cursor moving speed is fast enough.

## Change the margin color

Some user would want to change the color of pdf margin to make the margin box disappear.

Use text editor to open defaults.lua under kpv folder, find following line:

```lua
-- background colour: 8 = gray, 0 = white, 15 = black
DBACKGROUND_COLOR = 8
```

edit this line and change the value to 0:

```lua
DBACKGROUND_COLOR = 0
```
