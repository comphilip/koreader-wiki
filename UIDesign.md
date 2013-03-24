## NOTICE!
**Please always refer to the code first!** Content in this page is not actively maintained and might be outdated.

## How to Debug
We have a helper function called `DEBUG` to help with debugging. You can use that function to print string and tables:
```lua
a = {"1", "2", "3"}
DEBUG("table a: ", a)
```
Anything printed by `DEBUG` will starts with a `#` sign.

## Event system
Events are sent to the first widget in `UIManager._window_stack`. If it is not consumed, then it will be sent to all widget that is always active (`widget.is_always_active` equals `true`).

`WidgetContainer` is also a widget. When it receives an event, it will first propagate the event to all its children. If the event is still not consumed, then it will try to handle by itself.

## Draw Page Code Path
* **in readerview.lua:** ReaderView widget flag itself dirty in `ReaderView:recalculate`
* **in ui.lua:** UI main loop calls `ReaderView:paintTo`
* **in readerview.lua:** `ReaderView:paintTo` calls `document:drawPage`
* **in document.lua:** `document:drawPage` check for cache, if found, **return cache**
* **in document.lua:** if cache not found, `document:drawPage` calls `document:renderPage`
* **in document.lua:** `document:renderPage` calls `_document:openPage`, `page:draw` and put the result into cache
