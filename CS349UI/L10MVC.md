##L10, MVC

People express intention and the artifact gives feedback

Model View Controller pattern
- Standard pattern for GUIs, started in 1979

variations: MVP, MVA, MVC hierarchy

Why?
- Seperation of business logic and UI logic
- Support multiple views from same model
- Support multiple input (controller) from same model
- Separation for easier testing

express->translate->Controller->change->Model->notify->View->present->perceive

MVC uses Observer design pattern (Pub-Sub)

Model: manages application data
View: manages interface to present data
Controller: manages interaction to modify data

Usually view and Controller coupled (input and output often coupled)

Problems:
- View should handle input and output (why is controller needed)
- Additional info needed on top of Model (a seperate model between Model and View needed at times)

```java
notifyObservers();
setChanged();
addListener();
```

Usually just update the whole interface (optimization should come later)

Widgets -> logical device with appearance
- the Model represents connects to the actual logical device (toggle button's on/off)
- 