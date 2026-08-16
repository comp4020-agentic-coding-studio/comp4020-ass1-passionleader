# Weather & Atmosphere Simulator

**COMP4020 Assignment 1** --- an interactive explainer for how weather forms:
place warm/cool zones and high/low-pressure systems, change latitude and
physical parameters, and toggle temperature, pressure, cloud, and wind layers
over a coupled atmosphere driven by a real grid-based CFD solver (Coriolis
rotation included).

**Live:** https://comp4020-agentic-coding-studio.github.io/comp4020-ass1-passionleader/
**Explainer:** [`weather-physics.html`](https://comp4020-agentic-coding-studio.github.io/comp4020-ass1-passionleader/weather-physics.html)
walks through the equations and implementation choices.

An earlier thermal-convection prototype (single heat/cold sources driving a
convection cell) is still reachable at
[`convection.html`](https://comp4020-agentic-coding-studio.github.io/comp4020-ass1-passionleader/convection.html)
--- it's what the weather simulator grew out of, but it is not the graded
deliverable.

See [`PROCESS.md`](./PROCESS.md) for how the work came together and
[`reflections/assignment-1.md`](./reflections/assignment-1.md) for the retro.

## Stack

Vanilla JavaScript ES modules, HTML5 Canvas 2D, and Tailwind CSS via CDN --- no
framework, no runtime npm dependency. Vite is only the course's static
build/dev pipeline; see `CLAUDE.md` for the module architecture.

## Local development

```sh
mise install    # installs the tested Node and pnpm versions
pnpm install
pnpm dev        # local dev server
pnpm check      # typecheck, build, lint, and the spec suite
pnpm build      # produce dist/ (what gets deployed)
```
