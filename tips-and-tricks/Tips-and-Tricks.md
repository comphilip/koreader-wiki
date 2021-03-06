### 1. Page flipping mode (only for PDF and DjVu)
A single tap in the top left corner of the screen will enable page flipping mode. This is indicated by an icon of an open book. In page flipping mode panning (moving your fingertip on the screen slowly) horizontally will flip pages with steps 1, 2, 5, 10, 20, 50 and 100 according to the panning distance, and panning vertically will flip pages proportionally (proportion to the whole page number according to the panning distance proportion to the whole screen height).

Swipe right will bring you back to the original page where you entered the page flipping mode. (In order to flip pages in flipping mode, we must first set the zoom mode to "Zoom to fit page". Note that the zoom mode set in flipping mode does not affect zoom mode in regular reading.)

### 2. Bookmark browsing mode (only for PDF and DjVu)
Long press at the top right corner of the screen will bring you into bookmark browsing mode in which swipe left and right will show last and next bookmarked pages respectively. Another long press at the top right corner will exit back to normal reading mode.

### 3. Disabling AutoSuspend feature (Kobo only).
To disable AutoSuspend (by default it will kick in after 60 minutes of inactivity) add this line to the file `settings.reader.lua` at the end of `return {...}`:

```
["auto_suspend_timeout_seconds"] = -1
```

adding a comma to the previous line, so the structure is maintained. If you want to have AutoSuspend feature, but prefer a different timeout, just set the value (in seconds) instead of `-1` above.

### 4. Setting the default dictionary
A single tap on the dictionary title will make the current dictionary the default dictionary for this document.

### 5. Switching progress bar states
A single tap on the mini progress bar will switch between various modes. You can try tapping slightly *above* the progress bar if this doesn't work. You can also use the "Status bar" menu to show all this info at once. Long touch on the progress bar will invoke the "Goto page" dialog.

### 6. Flipped/Inverted Screen orientation
A tap on the current orientation (whether it be "portrait" or "landscape") button in the orientation tab of the bottom reader menu will flip the screen by 180 degrees, allowing you to switch to Inverted Portrait (Upside Down), and Inverted Landscape (Counter ClockWise).

### 7. Quick go back from link
After following links in both EPUB and PDF documents, you can easily go back to the original page by executing a swipe from left to right.

### 8. Look up new words in dictionary window
A long press on the word title (the red box in the following screenshot) in the dictionary window will pop up an input dialog in which you can enter new words to look up in dictionaries or on Wikipedia.

[![Input new word in dict](https://github.com/koreader/koreader/wiki/screenshots/dictionary_input_new_word.png)](https://github.com/koreader/koreader/wiki/screenshots/dictionary_input_new_word.png)

### 9. Fine-tuning of the crop box
When you set-up a crop box, it saves it for the page you are on, and also in a generic crop for odd and even.
Then, on a later page with no crop box for it yet defined, it automatically uses the one from odd/even:

There is an anchor at the middle point of each edge of the cropping box. Swiping around the anchors will adjust the position of the edge.

### 10. Toggle visibility of status bar easily
(Discovered this on PDF mode, not sure if it works in Epub mode.)
Tap the bottom right corner, the status/progress bar will disappear.

### 11. Alternative Table of Contents
[Long-pressing on the "Table of Contents" menu item will offer to generate a _ToC_ based on the document's headings](https://github.com/koreader/koreader/pull/4011). This is useful when the native ToC is bogus or incomplete.
![appbar screenshot](https://user-images.githubusercontent.com/24273478/41361691-f54900ce-6f2f-11e8-99cf-99eb6a5dd9a2.png)