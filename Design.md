# Design

## UI Framework
### Events
Events are passed to child Widgets (or child containers) before their own handler sees them. See the implementation of WidgetContainer:handleEvent(). So a child widget, for instance a text input widget, gets the input events before the layout manager. The child widgets can "consume" an event by returning "true" from the event handler. Thus a text input widget just implements an input handler and consumes left/right presses, returning true in those cases. It can even make its return code dependent on whether the cursor is on the last position (do not consume press to right) or first position (do not consume press to left) to have proper focus movement in those cases.