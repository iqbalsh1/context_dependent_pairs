Time-Dependent Synthetic Datasets (Pairs 01–08)

Overview
--------
- Nine synthetic time-series datasets (pair01–pair09), each with two variables (X, Y).
- Causal direction changes at t = 200:
  - X → Y for t = 1–199
  - Y → X for t = 200–499
- Each dataset contains 500 time steps (t = 0–499), is regularly sampled, and has no missing values.

Variations
----------
- Functional form: Linear or nonlinear 
- Causal strength: Low, medium, high
- Noise types:
  - Gaussian: ε ~ N(0, σ²)
  - Student’s t: ε ~ t(df=3) × σ
  - Mixed: ε = 0.5 × N(0, σ²) + 0.5 × Laplace(0, σ/√2)

Causal Models
-------------
- Linear:
  - Segment 1: Yₜ = a × X[t-1] + ε_Y
  - Segment 2: Xₜ = a × Y[t-1] + ε_X
- Nonlinear:
  - Segment 1: Yₜ = a × X[t-1] + b × X[t-1]² + ε_Y
  - Segment 2: Xₜ = a × Y[t-1] + b × Y[t-1]² + ε_X

Special Cases
-------------
- Pair07: Linear, mixed noise
- Pair08: Linear, Student’s t noise
- Both use multimodal inputs (mixture of Gaussians)

Parameters
----------
- Initial values: X₀ = 0, Y₀ = 0
- Random seed: 42
- Sampling: Regular (1/unit time)

Format
------
- .txt files: time, X, Y
- Metadata: pair##_des.txt
- Plots:
  - pair##_1.pdf: scatter plot
  - pair##_2.pdf: switch points
