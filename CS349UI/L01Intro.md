# L01, 1/7

UI: Human view of the computer
- the place where a person expresses intention to artifact, and artifact presents feedback to person
  - cycle

- Interaction: action by user and system over time - dialog between user and system, alternate between input/output
  
- Interface: external representation to user that support interaction
  - controls and feedback

Basically trying to make input and output language easiest to understand for the tasks

favoring machine -> favoring user

## History
Batch Interface (1945)
- set of instruction via Punch Cards, tape, magnetic tape
- receives response much later

Conversational Interface (1965)
- issue command -> await response
  - need t learn command, hard to discover

Both require trained personnel

Command Line: flexible, but requires knowledge

Interaction was closer to system than tasks themselves, figure how a task fit the system

Xerox Star: first information system - GUI!
- Xerox Alto research based (1981)

Macintosh: 1984

Windows eventually, 95 (1995)

GUI:
- Hardware interface: high resolution and refresh rate, keyboard + pointing device
- Software interface to help these IO

WIMP: Windows, Icons, Menu and Pointer format!
- does not have to look like MacOs or Windows, takes many forms (Android, iOS, watchOS)

Advantages
- remain in control, recognition of interface vs commands, metaphors to make it easier

# L02, 1/9

GUI
- needs to handle input, provide output and handle response times
- System gives isolation between applications and each have seperate access to own memory, resources etc. have strong isolation
- System gives method to move, resize, reorder etc.
  - provide common GUI elements to build apps looking similarly
    - recognize, common themes

Windowing system: provide separate, top level functionalities to manage them
- software layer that provides the capabilities to OS

## Base Window System (WS):
- provide OS level routines for creating, destroying and managing active windows
- Route input to correct window
- Manage access to graphics hardware (talks and restricts apps)

- Provides Drawing Canvas Abstraction
  - apps are shielded from details of frame buffer, visibility of window etc.
  - each gets a canvas, acts independently
  - own coordinate system, assume top left (0,0)

## Window Manager
- layered on top of WS, provides interactive components for windows
- provide common look and feel
- WS and WM own app window, apps own content

- for inputs: focus based dispatch vs positional based dispatch

X Windows framework
- Unix's standard WS
- supports pluggable WM, which can change look and feel of apps
  - mac and Windows dont because better for consolidation
- Local "Services/Client" would send draw calls to the "Server" which will draw to the screen

Benefits of Direct Manipulation
- because we are bad at multitasking, swapping between what you want to do and what interface needs to be reached to accomplish it makes the experience worse
- focus on task rather than tech
- Ivan Sutherland's Sketchpad (futuristic, but already realize this is better)

Desktop interfaces doesn't do direct manipulation well
- commands are invoked indirectly (menu, boxes, toolbar, things are hidden)

Issues with Direct Manipulation
- visually, physically impaired
- forces some info offscreen
- analogies are not clear and sometimes misleading

### Interaction Model
- make principles and techniques that is meaningful and consistent

Instrumental Interaction
- Interfaces have 
  - Interaction Instruments: necessary mediator between user and domain objects
  - Domain Objects: thing of interest, etc.

To modify a "Shape", we might use a drag instrument.

Instrument Activation
- when instrument is under control
- activated spatially (movement cost) and temporally (time cost)
  - trade off between these costs
- hard to find things: takes time and/or movement

Reification + Meta-Instruments
- Reification: turning concept to something concrete (instrument is reification of command)
- Meta-Instrument: acts on behalf of another one
  - basically the area of interest is the other instrument, you want to accomplish something by doing something else
- reorganizes the toolbar for example

Object Reification: color swatches, font etc.
- attributes of primary object are the new object

How to evaluate instrument
- degree of indirection (spatial and temporal offset)
- integration (degree of freedom of instrument vs input)
- compatibility (similar of action on device vs instrument to object)
  - dialog sucks lmao

Direct Manipulation
- allow a user to directly act on a set of objects in interface: good at all 3
- basically visually indistinguishable
- ie. drag to delete

