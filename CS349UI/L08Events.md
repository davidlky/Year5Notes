## L08, Events
Event Driven programming that bases flow based on events (actions, system etc.)
- very little happens unless something occurs

Event: an observable occurrence -> often extraordinary

KeyEvent, MouseEvent, MouseWheelEvent, FocusEvent, ComponentEvent, WindowEvent

WS needs to package events and sends them to the right app
- collect event, put metadata, order events, deliver events

Event Arch
- Capture -> Queue -> dispatch -> Binding (bind to right widget in app)

Every GUI has an event loop (get event -> redraw)

Apps might have own event queues too!
- XWindows will pull from BWS event queue and manage them immediately
- JRE will queue for them

XWindows requires apps to handle own event loops
- need to register to receieve events
- interpret events
- update program based on it
- redraw to show what has changed

basically
```c++
XEvent event;
while (true){
  XNextEvent(display, &event);
  switch (event.type){
    // handle
    repaint()
  }
}
```

Select input to listen to
```c++
XSelectInput(display, window, TASK_TYPE|TASK_TYPE)
```
XSelectInput -> XNextEvent (within the looop) -> Redraw

### Java Event Loop
2 main threades: main thread and UI thread for UI (Event handling thread)
- console app have just this one thread

Java Swing
- single threaded toolkit: all UI code need to be on UI thread
- event handled here too (since one handled at a time, hence we need event loop)
  - avoid blocking

`invokeLater` -> places a task on the event queue

### Event Dispatch
- Dispatch to correct window and widget
- find who triggered event or is in the foreground/accepting events

View Herarchy - Interactor Tree
- 2D layout of widget forms a hierarchy
- Heavyweight
  - WS/OS provides windowing system for all widgets
  - BWS can dispatch event to specific widget
  - Have hiararchy to traverse
- Lightweight
  - draws its own widgets and maps events to its own widget
  - BWS/OS will send to window
  - toolkit will handle dispatching

Positional Dispatch: send input to widget under mouse
- problem: overlap
- solution:
  - Bottom Up
    - lowest level node has first chance to handle event (send to the leaf node to handle cursor)
      - choose to handle or pass to parent
  - Top Down
    - send downwards, the biggest one gets to process it first
- Dragging becomes an issue, sometimes it isnt enough

Need to see whats in focus too!

Focus Dispatch
- dispatched to widget regardless of position
- needed for keyboard + mouse event
  - maximum 1 though for in focus!
- helpful to have a specific focus manager to manage which widget has focus!

Accelerator Key Dispatch
- dispatchs based on what keys are pressed

### Event Binding
- after dispatch is received, how do we bind event to code?

1. One giant event loop and just switch
2. Inheritance Binding
  - object oriented manner, each method has to handle ALL event, and override when needed
  - problem: code is everywhere and each container has to check what widget is event for
3. Interface Binding
   - describe signature for handling events, implement when needed
   - listen to specific event
   - many listener with multiple method has adapter class with no-op default methods, so override as needed (extend adapter)
   - anonymous inner classes works too!


Delegate Binding (NET)
- when heavy weight, direct callback functions can be used
- define a function thats to be called, and use `delegate` to assign the handler (pointer to function)
  - can have multiple functions called
  - outside class can only `+=` or `-=` cannot do assign!!!

Sometimes, you can monitor events across all apps

Sometimes events are too high freq, hence you can include array of skipped events at other events


