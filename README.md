# Digital Wind Tunnel

An interactive, browser-based wind tunnel for learning aerodynamics. A real
fluid simulation runs live in the page, with tooltips, plain-language concept
explanations, and a guided tour of classic experiments.

**Live demo:** open `index.html` in any browser. No build step, no dependencies.

## What it does

- **Real fluid physics.** A D2Q9 lattice-Boltzmann solver (BGK collision with
  Smagorinsky turbulence stabilization) computes the flow every frame. Vortices,
  wakes, stall, and lift emerge from the simulation, not from canned animation.
- **Test bodies:** NACA 4-digit airfoils (with a custom code input), a cylinder,
  a flat plate, or an empty tunnel.
- **Controls:** angle of attack, wind speed (including Mach 0.5 and Mach 1
  presets), working fluid (air / water / syrup), and simulation quality.
- **Visualization:** smoke trails, air speed, pressure coefficient, and
  vorticity, with a color legend and a photographic test-section look.
- **Live instruments:** lift and drag coefficients, L/D, Reynolds number, Mach
  number, a force-history chart, and a lift curve you draw yourself by sweeping
  the angle of attack.
- **Learning layer:** a tooltip on every control, a "Learn" glossary with
  one-click demos, an animated wind-tunnel anatomy diagram, and a step-by-step
  guided tour.

## How the numbers are made (honest note)

Lift is measured directly from the flow (momentum exchange on the body surface)
and tracks thin-airfoil theory (C_L is about 2*pi*alpha). A streamlined shape's
profile drag is smaller than a real-time browser grid can resolve, so drag is
reported from a standard drag polar (base profile drag, a rise with lift
squared, and a separation penalty) driven by the simulated lift and the measured
flow separation. It is a 2-D, low-Reynolds-number, incompressible model, so the
trends are physically faithful but the exact numbers are a smoke-tunnel guide,
not flight-test data.

## Keyboard shortcuts

`Space` pause/resume, `R` reset flow, arrow keys change angle of attack, `V`
cycle view modes, `S` toggle smoke, `?` show help.

## Tech

Single self-contained HTML file: inline CSS and vanilla JavaScript, Canvas 2D
rendering. Nothing to install.
