# Benchmark Methodology — v0.1

## Required benchmark categories
B01 BFS vs DFS vs iterative deepening; B02 full concatenation vs residual representation; B03 prefix pruning; B04 arithmetic necessary-condition filters; B05 deduplication; B06 residual growth; B07 invariant synthesis; B08 ranking-function synthesis; B09 nontermination proof methods; B10 guided vs classical search.

## Measurement protocol
Record input family, exact instance hash, algorithm and version, parameters, machine/OS/CPU/RAM, compiler flags, warm-up policy, seed, timeout, memory budget, wall-clock time, peak memory, explored states, verified proof outcome, and exit reason. Repeat randomized experiments and report variability. Preserve raw records and scripts.

## Visualization
- Heatmaps: e.g. states explored versus tile count and depth.
- Contour/3D surfaces: runtime versus controlled parameters.
- Polar charts: explicitly normalized comparable metrics, with normalization disclosed.
- State graphs: real transitions with accurate labels and filters.
- Fractal-like visualizations: optional exploratory art/math only; never substitute for measured benchmark data.

## Research integrity
Use independent known-answer test corpora where possible; distinguish synthetic from real instances; prevent training/test leakage in ML experiments; report UNKNOWN separately; never fabricate performance data.

## Current status
Benchmark suite definitions only; no measured results yet.
