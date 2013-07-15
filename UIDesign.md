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
Event system is used for widgets to communicate with each others.

Each event is an object that has two properties: `args` and `handler`. `handler` is the name of function that will be called on receive. `args` is a table that contains all the arguments needed to be passed to the event handler. When a widget receives a event, it will first check to see if `self[event.handler]` exists. If yes, the `self[event.handler]` function will be called and the return value of the handler will be returned.

Notice that If you don't want the event propagate after consumed in your handler, your handler must return True. Otherwise, the event will be passed to other widgets' handlers until one of the handler returns True.

`WidgetContainer` is a special kind of widget. When it receives an event, it will first propagate the event to all its children. If the event is still not consumed (handler returns True), then it will try to handle by itself.

When you call `UIManager:show` on an widget, this widget will be added to the top of `UIManager._window_stack`.
Events are sent to the first widget in `UIManager._window_stack`. If it is not consumed, then UIManager will try to send it to all active widgets (`widget.is_always_active` equals `true`) in the `_window_stack`.


## Draw Page Code Path
* **in readerview.lua:** ReaderView widget flag itself dirty in `ReaderView:recalculate`
* **in ui.lua:** UI main loop calls `ReaderView:paintTo`
* **in readerview.lua:** `ReaderView:paintTo` calls `document:drawPage`
* **in document.lua:** `document:drawPage` check for cache, if found, **return cache**
* **in document.lua:** if cache not found, `document:drawPage` calls `document:renderPage`
* **in document.lua:** `document:renderPage` calls `_document:openPage`, `page:draw` and put the result into cache
