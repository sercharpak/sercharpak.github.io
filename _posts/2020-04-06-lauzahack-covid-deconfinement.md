---
layout: post
section-type: post
title: "Simulation of Deconfinement Strategies — LauzHack Against COVID-19"
category: Side
tags: ['hackathon', 'simulation']
---

In April 2020, at the height of the COVID-19 pandemic, I participated in the **[LauzHack Against COVID-19](https://devpost.com/software/proposal-simulation-of-deconfinement-strategies-jy3ctf)** hackathon — a 72-hour remote event bringing together people who wanted to contribute to the pandemic response.

Our team was a wonderfull mix: a group of computational scientists  and a vet — Didier Bieler, Florence Le Sueur, Romain Vandemeulebrouck, Cécile Le Sueur, Laurent Colbois, and myself.

---

We built on top of the stunning epidemic simulator created by [3Blue1Brown](https://www.3blue1brown.com/) — all credit for the original concept goes to the 3Blue1Brown team and the developers of [Manim](https://github.com/3b1b/manim), the mathematical animation library that powers it. That original work is simply remarkable.

Our contribution was to extend the simulator to explore **deconfinement strategies**: what happens when you progressively reopen different segments of the population? We modelled scenarios such as phased reopening by age group, facility-specific reopenings (schools, markets), alternating confinement cycles triggered by infection thresholds, and multi-regional policy timing differences. The goal was to provide intuitive visualizations that could make these complex tradeoffs more legible for a general audience.

The project was implemented in Python using the Manim animation library. You can find the full submission on [Devpost](https://devpost.com/software/proposal-simulation-of-deconfinement-strategies-jy3ctf).

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; margin-top: 1.5em;">
  <iframe src="https://www.youtube.com/embed/1HKNcNFiqn4"
          style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;"
          allowfullscreen></iframe>
</div>
