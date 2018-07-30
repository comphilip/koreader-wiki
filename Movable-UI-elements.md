Some UI elements can be moved on screen:

![moving UI elements](https://user-images.githubusercontent.com/24273478/35508739-ca7bbc2c-04f1-11e8-811a-37b283ab2c6b.gif)

You have this commands or gestures:

* Move with Swipe: the widget will be constrained to screen borders (swipe is the quick natural way to move it quickly, with the nice side effect that there is a 0°/45°/90°... direction only, so it stays aligned)
* Move with Hold and pan: the widget can overflow the borders, and be moved any direction.
* Hold with no move: will reset the widget to its original position.
* If the widget has not been moved or is already at its original position, Hold with no move will toggle between full opacity and 0.7 transparency.

It is applied at this elements (widgets) at the moment:

* SkimToWidget (because in the middle of the screen is sometimes not the best place to see what's on the screen, and you can wish to move it to see some chapter title underneath it).
* ReaderSearch (buttondialog) widget with the << < > >> buttons (for the same reason as SkimToWidget)
* ButtonDialog/ButtonDialogTitle: the highlight 2x4 menu, the Hold on file menu, that you may wish to move to see again what's underneath.
* InfoMessage & ConfirmBox: mostly for the lookups/Wiki save as EPUB, so you can move them out while waiting.
* InputDialog: for consistency because why not?
* DictQuickLookup: because sometimes, you may want to see the text around the word you just looked up.
* TextViewer: could be useful with bookmarks to see the list while viewing one.

More info can be found [here.](https://github.com/koreader/koreader/pull/3636)