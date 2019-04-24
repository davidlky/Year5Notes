# 2.27.2018, Layout

2 Main Tasks

- Designing and Adjusting the Spatial Layout

Dynamic Layout

- Resized Window
  - maximize use of available space to display widgets
  - Maintain consistency and preserve visual quality
- Hence: dynamically modify the layout
  - reallocate space for widget, adjust location and size (or even look, feel)

Tree/Hierarchy

Dynamic Sizing: Min, Preferred, Max size!

Layout Manager - Strategy that factors out the layout algo to size and position widget

- diff manager = diff algos.

Different Strategy

- Fixed Layout: widgets have fixed size and position (null as layout manager)
- Intrinsic Size: Query the preferred size and grow widgets to contain each item
  - bottom up (top widget size based on the bottoms)
  - Box, Flow Layout
- Variable Intrinsic Size Layout
  - Get preferred size, then decide on a layout that satisfy everyone
  - Gridbag, BorderLayout
- Struts and Springs Layout
  - Marking spaces as stretchable
  - Strut: fixed Space!
  - Spring: stretchable space! (aka glue)
  - Spring/BoxLayout
  - Used a lot in GUIs
- Relative Layout
  - relative position constraint (East of another widget)
  - Spring Layout

Mouse has a 2 DOF device

- set X, Y, Z, rotation around each axis => 6 DOF
