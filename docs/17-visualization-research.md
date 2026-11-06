# Visualization research protocol

Every benchmark visualization must map real numerical data to visible axes, colors, and geometry.

## Planned chart families
- Heatmap: explored states across tile count and depth.
- Contour: equal runtime or equal memory lines over two controlled parameters.
- 3D surface: log-scaled runtime or state count as a function of input parameters.
- Polar/radar: normalized multi-metric comparisons, clearly noting different units and normalization.
- State graph: directed labeled transitions with residuals and proof state.
- Experimental fractal/recursive geometry: only when a specific recurrence or measured state-space structure is defined.

The colorful 3D reference image may resemble fractal rendering, but its generating equation is unknown. Do not label a decorative fractal as benchmark evidence.

## Required plot metadata
Dataset version, algorithm revision, instance generator seed, machine specs, compiler settings, sample size, timeout, units, axis definitions, aggregation method, and confidence/variance reporting where applicable.

## Visualization quality gates
Accessible color scales, legends, no deceptive axes, downloadable source data, and a clear separation between illustrative and measured plots.
