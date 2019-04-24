Undo: allows for exploratory learning, recover from error and evaluate modifications

Most basic: Checkpointing (like a video game)

need to identify

- Undoable Actions (what can be undone)
  - some should not be undoable (resizing, quitting, printing)
  - changes to model should be undoable!
- State restoration (what part of UI is restored)
  - scroll to the undo-ed action?
- Granularity (how much to undo?)
  - undo a line or a pixel?
- Scope (is undo global, local, in between)
  - Where does it happen (undo a field, form, page?)

Implementing Undo

- Forward Undo: save complete baseline state at some past point, save the amount of changes from the point, if undo, don't apply the latest
- Reverse Undo: save current document state and work backwards (save the reverse change records)
- To enable redo, you need a seperate stack!
  - only add when undo is done

Change record Implementation

- Memento Pattern
  - Save snapshot of each document state (complete or the "difference between" state) (save the model)
- Command Pattern
  - save commands to execute (un-execute) to change state. (save the command that changed the model)
