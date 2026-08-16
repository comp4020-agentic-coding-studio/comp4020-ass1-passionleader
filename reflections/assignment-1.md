# Assignment 1 Reflection

The breakthrough was realising that the convection simulator was not engaging
enough as an experience. I had spent time checking whether the flow was
physically convincing: whether heat rose, whether cold sank, whether a central
heat source produced circulation, and whether the direction of the flow made
sense. However, the result still felt too narrow. Instead of continuing to
ask Claude for small visual adjustments, I changed the concept and asked for a
weather and atmosphere simulator with temperature, pressure, wind, clouds, and
terrain. I increased Claude's effort setting to maximum and delegated the large
implementation after defining the behaviour I wanted. The resulting simulator
added coupled fields, Coriolis rotation, wind trails, pressure contours, and a
test suite for the important physical relationships.

This work changed how I want to be as a software developer. I learned that
giving an agent more authority does not remove my responsibility. I still need
to know what the product should communicate, which behaviours are physically
meaningful, and which changes are outside the requested scope. I also learned
that harnessing is more effective than repeating warnings in individual
prompts. My first `CLAUDE.md`, created with help from Gemini, gave Claude a
useful set of project constraints. In future work I want to update that
harness as the product changes, use branches for risky experiments, ask for
commit boundaries, and keep changes easy to reverse. I want to act more like a
manager of the system: setting direction and acceptance criteria, while letting
the agent explore implementation details within clear boundaries.
