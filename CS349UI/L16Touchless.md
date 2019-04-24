Hard to build fustration sensor

What would we want to sense?

- Occupancy (existance) and motion
- Range/Distrance
- Position
- Movement/Orientation
- Gaze
- Speech
- Brain Wave

We can use this to support gestures, identify people, determine context and affect

Hard to use computer vision, very costly and very noisey

Signal to Command systems

- Pre-processing (compress, smooth, thresholding, downsample and handle latency)
- Feature selection
- Classification

People prefer speech, but the words used varies

Theres Explicit Interaction (siri, cortana) and implicit ones (creepy ones)

False Positive Error: user didnt want to do anything, the system just seems erratic or overly sensitive

False Negative Error: user did something but the system did not do it, unresponsive

Key Challenge: Errors is hard to balance

- user needs to feel a sense of control and are very intolerant of errors

"Live Mic" problem

Problem: mouse 3 states, touch 2 states, gesture 1 state... how to differentiate

Solution: reserving gesture: have to do a "delimiter" first (use a simple one)

- disadvantage: cant use gesture for anything else.

Solution: Multi-Modal Input

- reserved action (clutch) like a home button

Should always give feedback

## Speech Interfaces (SUI)

Challenges

- how to do navigation??
- people have human language with context
- What to use for confirmation
- lack of visual feedback
- short term memory

Type of errors

- Rejection errors (should not have rejected but computer didn't understand)
- Substitution Error (mistaken a word for another)
- Insertion Error (noises counted as legal words)

In designing touchless interfaces, a key objective is to ensure that the system fails gracefully, and errors are managed properly.
