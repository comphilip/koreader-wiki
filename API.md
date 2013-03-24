# API
sorted by modules and files.

**This is still imcomplete. If in doubt, ask - or look into the source files.**


Note: point (xpos, ypos) stands for left-down corner, while point (x, y) stands for left-up corner.


## einkfb (einkfb.c)
This module is used to control the eink display.
### refresh
```lua
einkfb:refresh(fxtype=0, x=0, y=0, width=screen_width, height=screen_height)
```
Refresh (update) a given area of the screen, specify by (xpos, ypos, width and height). The screen will remain the unchanged unless you call this function.

**fxtype** can be `0` or `1`. `1` stands for partial refresh while `0` stands for full refresh. Since this function supports default argument, you can do a full screen partial refresh with:
```lua
fb:refresh(1)
```


## blitbuffer (blitbuffer.c)
This module is used to draw stuff, you need the refresh function in `einkfb` module to reflect the changes.
### paintRect
```lua
blitbuffer:paintRect(x, y, w, h, c)
```
Paint a rectangle that starts from point (`x`,`y`), with `w` as width, `h` as height and fill it with color `c`.

### invertRect
```lua
blitbuffer:invertRect(x, y, w, h)
```
Invert a rectangle that starts from point (`x`,`y`), with `w` as width, `h` as height and fill it with XOR 0xFF

### blitFrom
```lua
blitbuffer:blitFrom(bb, dst_x, dst_y, x_offs, y_offs, w, h)
```
Fill biltbuffer, starts from (`dst_x`, `dst_y`), with content from `bb`. The content is copied from `bb`, starts from (`x_offs`, `y_offs`), with `w` as width and `h` as height.

## pdfpage (pdf.c)
### getSize (getPageSize)
return page width and height after zoomed.

## rendertext (rendertext.lua)
### renderUtf8Text
```lua
renderUtf8Text(buffer, xpos, ypos, face, facehash, text, kerning)
```
Draw text, start from point (xpos, ypos). Note that (xpos, ypos) points to the left-down corner of the font.


## UniReader (unireader.lua)
### setzoom
```lua
UniReader:setzoom(page)
```
Render a given page and return a `DrawContext`, can be used by `pdfpage:draw`.

### draworcache
```lua
UniReader:draworcache(no, zoom, offset_x, offset_y, width, height, gamma, rotate)
```
Return the hash of drawn page. The drawn result is saved in `self.cache[hash]`. So you can blit the result to screen with `fb.bb:blitFullFrom(self.cache[hash].bb)`.


## graphics (graphics.lua)
### blitbuffer.paintBorder
```lua
blitbuffer.paintBorder(bb, x, y, w, h, bw, c)
```
Paint a border in a given area, starts from point `(x, y)` as left-upper corner, with `w` width and `h` height. The border width is `bw` and border color is `c`.

`c` can range from 0 to 15 (white to black). 
