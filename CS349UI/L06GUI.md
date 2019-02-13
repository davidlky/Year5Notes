## L05 GUI

Operating systems include basic capabilities for input, output, graphics
- low level capabilities are exposed, make libraries, hard to make apps

Toolkit is a set of reusable classes/components for building UIs
- widget toolkits
- provide graphics, collection of common widgets
  - other things too, event handling, audio, system services etc.

Types
- Low Level: built into underlying OS (native)
  - Win32, Cocoa for Mac
- High Level: 3rd party, lightweight as not tightly coupled, may not have native look

Cross Platform is rare

How to build UI?
1. Imperative: constructed in code (procedural)
   - tedious, but versatile and common
2. Direct: drag and drop - constructed with GUI
   - note: NOT GENERATE INTO XML, STORED AS BINARY!!
   - bad, hard to debug
3. Declarative: described in some human readable layout file
  - clear separation between layout and cde

Java
- compiles to bytecode that can be executed by JVM on different OS
- Just-in-time byte code gives near native performance (JIT)
  - can run other languages as well, runs everywhere


## L06, 1/21
- Java does everything by references not pointers, no destructor cuz of garbage collection
- classes belongs to packages (not needed), have default Object class!

- `awt` vs `swing` (swing provides lightweight components that works the same on all platforms)

- primitives are passed by value, addresses are passed by value for objects

Gradle: change mainClassName to have the path too (the package)
