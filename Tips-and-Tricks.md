### 1. Page flipping mode (only for PDF)
Single tap at the top left corner of the screen will bring you into page flipping mode which has an icon of an open book. In page flipping mode panning (moving your finger tip on the screen slowly) horizontally will flip page with steps 1, 2, 5, 10, 20, 50 and 100 according to the panning distance, and panning vertically will flip page with proportionally ( proportion to the whole page number according to the panning distance proportion to the whole screen height). Swipe right will bring you back to the original page where you entered the page flipping mode. (In order to flip pages in flipping mode, we must first set the zoom mode to "Zoom to fit page". Note that the zoom mode set in flipping mode does not affect zoom mode in regular reading.)

### 2. Bookmark browsing mode
Long press at the top right corner of the screen will bring you into bookmark browsing mode in which swipe left and right will show last and next bookmarked pages respectively. Another long press at the top right corner will exit back to normal reading mode.

### 3. Disabling AutoSuspend feature (Kobo only).
To disable AutoSuspend (by default it will kick in after 60 minutes of inactivity) add this line to the file `settings.reader.lua` at the end of `return {...}`:

```
["auto_suspend_timeout_seconds"] = -1
```

adding a comma to the previous line, so the structure is maintained. If you want to have AutoSuspend feature, but prefer a different timeout, just set the value (in seconds) instead of `-1` above.

### 4. Setting default dictionary
Single tap on the dictionary title will make current dictionary the default dictionary for this document.

### 5. Switching progress bar states
Single tap on the mini progress bar will switch between various modes thereof. You can also use "Status bar" menu to show all this info at once. Long touch on the progress bar will invoke the "Goto page" dialog.

### 6. Flipped landscape screen orientation
Tap on the "landscape" option in screen mode panel of reader config window when the screen is already in landscape mode will flip the landscape screen with 180 degrees.

### 7. Quick go back from link
After following links in both EPUB and PDF documents, you can easily go back to the original page by executing a swipe from left to right.

### 8. Lookup new words in dictionary window
Long press on the word title (the red box in the following screenshot) in dictionary window will popup a inputbox in which you can input new words to lookup in dictionaries or the Wikipedia.

[![Input new word in dict](https://github.com/koreader/koreader/wiki/screenshots/dictionary_input_new_word.png)](https://github.com/koreader/koreader/wiki/screenshots/dictionary_input_new_word.png)

### 9. Fine tuning of crop box
There is an anchor at the middle point of each edge of the cropping box. Swipping around the anchors will adjust the position of the edge.