# Process overview

I built an interactive weather and atmosphere simulator that lets users explore
temperature, pressure, wind, clouds, and terrain through a layered Canvas
visualisation. The final idea grew out of an earlier thermal-convection
prototype. My process was shaped by a repeated question: did the simulation
merely look plausible, or did its behaviour make physical and interactive sense?

## The moments that mattered

At the beginning, I made the main product and technical decisions before asking
the agent to implement them. I chose vanilla JavaScript, HTML5 Canvas, and
Tailwind CSS, and specified the initial module boundaries, responsive layout,
controls, and interaction model. I used Gemini to help turn these decisions
into the first `CLAUDE.md`, which gave Claude a shared vocabulary and explicit
constraints instead of leaving the project as an open-ended visual experiment.
The first harness and the initial simulation direction are visible in
[`f0e7eeb`](https://github.com/comp4020-agentic-coding-studio/comp4020-ass1-passionleader/commit/f0e7eeb)
and [`e3a5220`](https://github.com/comp4020-agentic-coding-studio/comp4020-ass1-passionleader/commit/e3a5220).

The first decisive breakthrough was recognising that the convection prototype
was not engaging enough, even after several rounds of tuning. I tested it by
watching the rendered flow, not just by reading the code: heat rose and cold
sank, but circulation was difficult to see and the experience felt too narrow.
I had also learned from the debugging that a visual change could accidentally
alter the physics. For example, changing a slider maximum changed an internal
normalisation value and made the flow too strong. Rather than continuing to
patch an uninteresting concept, I changed the problem: I asked Claude, with
`effort: max`, to build a weather simulator with visible heat, pressure, wind,
clouds, and a map-like terrain layer. This was a deliberate delegation after I
defined the experience I wanted, not a request for arbitrary feature growth.

The resulting implementation became a separate weather architecture. It added
an atmosphere grid, coupled temperature and pressure fields, Coriolis rotation,
wind streamlines with fading trails, procedural terrain, cloud coverage,
isobars, high/low pressure markers, a weather control panel, and a physics
explanation page. It also added tests for source behaviour, pressure extrema,
numerical stability at a risky slider corner, ambient temperature, the textbook
Coriolis formula, hemisphere-dependent rotation direction, colour mapping, and
responsive grid resolution. The transition to the final weather simulator is
recorded in [`6696eb9`](https://github.com/comp4020-agentic-coding-studio/comp4020-ass1-passionleader/commit/6696eb95100c05fac66d910a86a9802fbd191981).

Another important strategy was making changes reversible and narrow. When an
ambient-temperature fix changed more than intended, I explicitly rolled it
back, reconsidered the requirement, and later corrected the airflow direction
with a focused change ([`e7817be...2cff3bf`](https://github.com/comp4020-agentic-coding-studio/comp4020-ass1-passionleader/compare/e7817be...2cff3bf)). This taught me to constrain Claude's edits rather than repeatedly restating the same request.

The final `CLAUDE.md` now reflects the weather simulator rather than the
superseded convection app. It documents the weather module boundaries, physical
units, rendering responsibilities, numerical invariants, tests, and the rule
that the explanation page must stay consistent with the solver. In this way,
the harness records not only how Claude should code, but also what I decided
the project was actually trying to teach.
