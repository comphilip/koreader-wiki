[SkimToWidget](https://github.com/koreader/koreader/blob/master/frontend/ui/widget/skimtowidget.lua) is a multifunctional book navigation tool. It can be invoked with:
- reader menu `Navigation` – `Skim document`;
- `Skim` button in the `Go to page` dialog;
- a long press on the bottom status bar, if enabled;
- an assigned gesture.  
![SkimToWidget](https://user-images.githubusercontent.com/62179190/111024709-e4404280-83e8-11eb-94d1-9d09659f4f74.png)
---
  
**Top row buttons** actions:  
<kbd>▕◁</kbd> **press**: go to the previous chapter; **hold**: go to the first page of the book  
<kbd>◁☆</kbd> **press**: go to the previous bookmark; **hold**: go to the first bookmark  
<kbd>☆</kbd> **press**: toggle bookmark; **hold**: show the list of bookmarks  
<kbd>☆▷</kbd> **press**: go to the next bookmark; **hold**: go to the last bookmark  
<kbd>▷▏</kbd> **press**: go to the next chapter; **hold**: go to the last page of the book  

Tap the **progress bar** to go to the desired location in the book.  
Reader menu `Navigation` - `Settings` – `Progress bars` sets the ToC level for ticks shown in the progress bar.
 
**Bottom row buttons** actions on press:  
<kbd>-10</kbd> go to 10 pages backward  
<kbd>-1</kbd> go to one page backward  
<kbd>##</kbd> invoke `Go to page` dialog  
<kbd>+1</kbd> go to one page forward  
<kbd>+10</kbd> go to 10 pages forward  
 
SkimToWidget is a [movable element](https://github.com/koreader/koreader/pull/3636).  
Hold the widget outside of the top row buttons to toggle its transparency.

Tap the screen outside of the SkimToWidget to close it.
