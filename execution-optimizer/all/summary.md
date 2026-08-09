### Execution optimizer summary

Detector: `all`  
This report coalesces compatible measurements from completed optimizer runs only.

<a id="table-of-contents"></a>

<details open>
<summary><strong>Navigation</strong></summary>

- [Preferred Detector Run Configuration](#preferred-detector-run-configuration)
- [Detector Run Profile Plot](#detector-run-profile-plot)
  - [adaptive_radial_edge](#detector-run-profile-adaptive-radial-edge)
  - [consensus_quad](#detector-run-profile-consensus-quad)
  - [contour_components](#detector-run-profile-contour-components)
  - [contour_projection](#detector-run-profile-contour-projection)
  - [grabcut](#detector-run-profile-grabcut)
- [Detector Pipeline-Thread Shape Optimization Data](#detector-pipeline-thread-shape-optimization-data)
  - [adaptive_radial_edge](#detector-shape-data-adaptive-radial-edge)
  - [consensus_quad](#detector-shape-data-consensus-quad)
  - [contour_components](#detector-shape-data-contour-components)
  - [contour_projection](#detector-shape-data-contour-projection)
  - [grabcut](#detector-shape-data-grabcut)

</details>

<a id="preferred-detector-run-configuration"></a>
<details open>
<summary><strong>1. Preferred Detector Run Configuration</strong></summary>

Compatible completed optimizer runs are coalesced by detector, workload, and concrete runner profile. Repeated shapes retain all observations; the preferred shape is selected canonically by throughput, then lower resource use for throughput-equivalent shapes.

| Detector | Runner | CPU | Physical | Logical | RAM | Preferred pipelines | Threads / pipeline | Preferred shape range (≤2%) | Search method | Optimization time | Allocated | Sets/s | Shape time | Observations |
|---|---|---|---:|---:|---:|---:|---:|---|---|---:|---:|---:|---:|---:|
| adaptive_radial_edge | e7k — rh8-al97 (96 vCPU) | AMD EPYC 74F3 24-Core Processor | 48 | 96 | 2003.9 GiB | 49 | 3 | 46p/4t, 49p/3t, 50p/3t, 51p/3t, 52p/3t | exhaustive | 3h 35m 57s | 147 | 70.56 | 1m 33s | 1 |
| consensus_quad | 192t — rh8-al323 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 5 | 76 | 5p/76t, 6p/64t | adaptive | 2m 46s | 380 | 27.00 | 9s | 1 |
| contour_components | e9k — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 8 | 7p/9t, 8p/8t, 9p/7t | adaptive | 19m 31s | 64 | 123.03 | 2m 40s | 2 |
| contour_projection | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 21 | 18 | 21p/18t | adaptive | 1h 9m 57s | 378 | 49.71 | 2m 12s | 1 |
| grabcut | e7k — rh8-al97 (96 vCPU) | AMD EPYC 74F3 24-Core Processor | 48 | 96 | 2003.9 GiB | 1 | 192 | 1p/192t, 2p/96t | exhaustive | 1h 54m | 192 | 1.92 | 1h 54m | 1 |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-run-profile-plot"></a>
<details open>
<summary><strong>2. Detector Run Profile Plot</strong></summary>

Compatible completed measurements are plotted by detector; thread count is annotated at each measured shape.

<a id="detector-run-profile-adaptive-radial-edge"></a>
<details>
<summary><strong>adaptive_radial_edge</strong></summary>

**Search method(s):** `exhaustive`

![adaptive_radial_edge Detector Run Profile Plot](profiles/adaptive_radial_edge.svg)

</details>

<a id="detector-run-profile-consensus-quad"></a>
<details>
<summary><strong>consensus_quad</strong></summary>

**Search method(s):** `adaptive`

![consensus_quad Detector Run Profile Plot](profiles/consensus_quad.svg)

</details>

<a id="detector-run-profile-contour-components"></a>
<details>
<summary><strong>contour_components</strong></summary>

**Search method(s):** `adaptive`

![contour_components Detector Run Profile Plot](profiles/contour_components.svg)

</details>

<a id="detector-run-profile-contour-projection"></a>
<details>
<summary><strong>contour_projection</strong></summary>

**Search method(s):** `adaptive`

![contour_projection Detector Run Profile Plot](profiles/contour_projection.svg)

</details>

<a id="detector-run-profile-grabcut"></a>
<details>
<summary><strong>grabcut</strong></summary>

**Search method(s):** `exhaustive, powers-of-2`

![grabcut Detector Run Profile Plot](profiles/grabcut.svg)

</details>

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-pipeline-thread-shape-optimization-data"></a>
<details>
<summary><strong>3. Detector Pipeline-Thread Shape Optimization Data</strong></summary>

Coalesced compatible shape measurements from completed optimizer runs are shown below.

<a id="detector-shape-data-adaptive-radial-edge"></a>
<details>
<summary><strong>adaptive_radial_edge</strong></summary>

**Search method(s):** `exhaustive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e7k — rh8-al97 (96 vCPU) | 1 | 1 | 96 | 96 | 42m 52s | 2.55 | 1.00× | -96.38% | 2.0 | 5.1 | 2.1% | 18.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 2 | 2 | 96 | 192 | 20m | 5.47 | 2.14× | -92.25% | 3.9 | 8.7 | 4.1% | 19.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 3 | 3 | 64 | 192 | 15m 15s | 7.17 | 2.81× | -89.84% | 5.3 | 8.3 | 5.5% | 19.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 4 | 4 | 48 | 192 | 10m 24s | 10.52 | 4.12× | -85.10% | 8.4 | 12.4 | 7.9% | 19.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 5 | 5 | 38 | 190 | 9m | 12.15 | 4.76× | -82.78% | 8.8 | 13.5 | 9.3% | 19.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 6 | 6 | 32 | 192 | 8m 3s | 13.59 | 5.33× | -80.75% | 8.6 | 10.2 | 10.1% | 19.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 7 | 7 | 27 | 189 | 6m 32s | 16.74 | 6.56× | -76.28% | 12.4 | 14.1 | 11.7% | 19.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 8 | 8 | 24 | 192 | 5m 33s | 19.71 | 7.72× | -72.07% | 13.6 | 16.3 | 15.0% | 20.0 GiB |
| e7k — rh8-al97 (96 vCPU) | 9 | 9 | 21 | 189 | 5m 29s | 19.95 | 7.82× | -71.73% | 12.9 | 15.2 | 14.0% | 19.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 10 | 10 | 19 | 190 | 4m 20s | 25.24 | 9.89× | -64.23% | 25.7 | 35.1 | 18.2% | 20.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 11 | 11 | 17 | 187 | 4m 7s | 26.57 | 10.41× | -62.35% | 20.9 | 23.0 | 19.6% | 20.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 12 | 12 | 16 | 192 | 4m 3s | 27.00 | 10.58× | -61.73% | 20.0 | 22.8 | 20.1% | 20.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 13 | 13 | 14 | 182 | 3m 25s | 32.01 | 12.55× | -54.63% | 21.0 | 24.2 | 20.6% | 20.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 14 | 14 | 13 | 182 | 3m 11s | 34.36 | 13.47× | -51.31% | 28.3 | 29.9 | 25.5% | 20.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 15 | 15 | 12 | 180 | 3m 20s | 32.81 | 12.86× | -53.50% | 34.8 | 42.0 | 25.6% | 20.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 16 | 16 | 12 | 192 | 2m 48s | 39.06 | 15.31× | -44.64% | 25.9 | 28.7 | 25.6% | 20.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 17 | 17 | 11 | 187 | 2m 44s | 40.01 | 15.68× | -43.29% | 28.0 | 32.1 | 28.9% | 20.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 18 | 18 | 10 | 180 | 2m 50s | 38.60 | 15.13× | -45.29% | 48.5 | 57.0 | 31.7% | 20.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 19 | 19 | 10 | 190 | 2m 30s | 43.75 | 17.15× | -38.00% | 60.8 | 89.0 | 30.0% | 21.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 20 | 20 | 9 | 180 | 2m 23s | 45.89 | 17.99× | -34.97% | 44.8 | 49.4 | 33.0% | 21.0 GiB |
| e7k — rh8-al97 (96 vCPU) | 21 | 21 | 9 | 189 | 2m 28s | 44.34 | 17.38× | -37.16% | 36.4 | 38.9 | 34.8% | 21.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 22 | 22 | 8 | 176 | 2m 13s | 49.34 | 19.34× | -30.08% | 37.9 | 43.0 | 36.2% | 21.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 23 | 23 | 8 | 184 | 2m 9s | 50.87 | 19.94× | -27.91% | 42.7 | 45.4 | 39.0% | 21.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 24 | 24 | 8 | 192 | 2m 16s | 48.25 | 18.91× | -31.62% | 49.2 | 56.3 | 40.7% | 21.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 25 | 25 | 7 | 175 | 2m | 54.68 | 21.43× | -22.50% | 40.7 | 43.1 | 37.9% | 21.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 26 | 26 | 7 | 182 | 1m 59s | 55.14 | 21.61× | -21.85% | 70.9 | 82.9 | 43.8% | 21.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 27 | 27 | 7 | 189 | 2m 6s | 52.08 | 20.41× | -26.19% | 87.1 | 102.5 | 45.1% | 22.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 28 | 28 | 6 | 168 | 1m 52s | 58.59 | 22.96× | -16.96% | 47.9 | 51.9 | 42.4% | 21.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 29 | 29 | 6 | 174 | 1m 52s | 58.59 | 22.96× | -16.96% | 53.4 | 55.3 | 49.2% | 21.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 30 | 30 | 6 | 180 | 1m 58s | 55.61 | 21.80× | -21.19% | 62.6 | 69.2 | 51.0% | 22.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 31 | 31 | 6 | 186 | 1m 46s | 61.91 | 24.26× | -12.26% | 55.0 | 59.4 | 48.0% | 22.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 32 | 32 | 6 | 192 | 1m 45s | 62.50 | 24.50× | -11.43% | 95.0 | 100.6 | 54.9% | 22.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 33 | 33 | 5 | 165 | 1m 50s | 59.65 | 23.38× | -15.45% | 90.2 | 104.6 | 51.0% | 22.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 34 | 34 | 5 | 170 | 1m 42s | 64.33 | 25.22× | -8.82% | 84.5 | 84.5 | 56.3% | 22.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 35 | 35 | 5 | 175 | 1m 42s | 64.33 | 25.22× | -8.82% | 128.1 | 133.0 | 59.1% | 22.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 36 | 36 | 5 | 180 | 1m 48s | 60.76 | 23.81× | -13.89% | 99.0 | 102.5 | 59.9% | 22.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 37 | 37 | 5 | 185 | 1m 39s | 66.28 | 25.98× | -6.06% | 135.0 | 135.0 | 49.8% | 23.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 38 | 38 | 5 | 190 | 1m 40s | 65.62 | 25.72× | -7.00% | 141.2 | 163.2 | 64.2% | 23.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 39 | 39 | 4 | 156 | 1m 44s | 63.10 | 24.73× | -10.58% | 131.5 | 144.6 | 66.5% | 22.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 40 | 40 | 4 | 160 | 1m 36s | 68.35 | 26.79× | -3.12% | 109.4 | 109.4 | 53.8% | 22.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 41 | 41 | 4 | 164 | 1m 36s | 68.35 | 26.79× | -3.12% | 168.1 | 178.8 | 69.3% | 23.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 42 | 42 | 4 | 168 | 1m 40s | 65.62 | 25.72× | -7.00% | 221.3 | 232.5 | 70.6% | 23.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 43 | 43 | 4 | 172 | 1m 35s | 69.07 | 27.07× | -2.11% | 215.3 | 215.3 | 62.2% | 23.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 44 | 44 | 4 | 176 | 1m 35s | 69.07 | 27.07× | -2.11% | 176.1 | 185.0 | 74.7% | 23.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 45 | 45 | 4 | 180 | 1m 38s | 66.96 | 26.24× | -5.10% | 127.5 | 127.5 | 70.1% | 23.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 46 | 46 | 4 | 184 | 1m 34s | 69.81 | 27.36× | -1.06% | 159.2 | 170.2 | 72.8% | 24.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 47 | 47 | 4 | 188 | 1m 35s | 69.07 | 27.07× | -2.11% | 264.8 | 279.0 | 78.9% | 24.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 48 | 48 | 4 | 192 | 1m 37s | 67.65 | 26.52× | -4.12% | 249.0 | 249.0 | 72.6% | 24.7 GiB |
| **e7k — rh8-al97 (96 vCPU)** | 49 | 49 | 3 | 147 | 1m 33s | 70.56 | 27.66× | 0.00% | 253.8 | 287.8 | 78.6% | 23.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 50 | 50 | 3 | 150 | 1m 33s | 70.56 | 27.66× | 0.00% | 329.1 | 329.1 | 75.7% | 23.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 51 | 51 | 3 | 153 | 1m 34s | 69.81 | 27.36× | -1.06% | 270.9 | 284.9 | 83.0% | 23.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 52 | 52 | 3 | 156 | 1m 33s | 70.56 | 27.66× | 0.00% | 270.5 | 270.5 | 74.2% | 24.0 GiB |

</details>

<a id="detector-shape-data-consensus-quad"></a>
<details>
<summary><strong>consensus_quad</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 21s | 11.57 | 1.00× | -57.14% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 4 | 4 | 96 | 384 | 10s | 24.30 | 2.10× | -10.00% | — | — | — | — |
| **192t — rh8-al323 (192 vCPU)** | 5 | 5 | 76 | 380 | 9s | 27.00 | 2.33× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 6 | 6 | 64 | 384 | 9s | 27.00 | 2.33× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 7 | 7 | 54 | 378 | 10s | 24.30 | 2.10× | -10.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 10s | 24.30 | 2.10× | -10.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 9 | 9 | 42 | 378 | 11s | 22.09 | 1.91× | -18.18% | 991.7 | 991.7 | 82.6% | 11.7 GiB |
| 192t — rh8-al323 (192 vCPU) | 10 | 10 | 38 | 380 | 11s | 22.09 | 1.91× | -18.18% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 11 | 11 | 34 | 374 | 12s | 20.25 | 1.75× | -25.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 128 | 128 | 3 | 384 | 1m 2s | 3.92 | 0.34× | -85.48% | 1212.0 | 1212.0 | 61.8% | 14.8 GiB |

</details>

<a id="detector-shape-data-contour-components"></a>
<details>
<summary><strong>contour_components</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e9k — rh8-al320 (192 vCPU) | 1 | 1 | 64 | 64 | 8m 13s | 39.93 | 1.00× | -67.55% | 7.8 | 13.3 | 8.3% | 12.2 GiB |
| e9k — rh8-al320 (192 vCPU) | 3 | 3 | 21 | 63 | 3m 35s | 91.55 | 2.29× | -25.58% | 253.2 | 592.1 | 30.8% | 12.5 GiB |
| e9k — rh8-al320 (192 vCPU) | 4 | 4 | 16 | 64 | 3m 3s | 107.56 | 2.69× | -12.57% | 98.9 | 113.4 | 37.9% | 12.5 GiB |
| e9k — rh8-al320 (192 vCPU) | 6 | 6 | 10 | 60 | 2m 48s | 117.17 | 2.93× | -4.76% | 738.7 | 739.6 | 94.7% | 12.7 GiB |
| e9k — rh8-al320 (192 vCPU) | 7 | 7 | 9 | 63 | 2m 42s | 121.51 | 3.04× | -1.23% | 783.4 | 813.3 | 93.1% | 13.0 GiB |
| **e9k — rh8-al320 (192 vCPU)** | 8 | 8 | 8 | 64 | 2m 40s | 123.03 | 3.08× | 0.00% | 865.3 | 866.8 | 96.6% | 13.1 GiB |
| e9k — rh8-al320 (192 vCPU) | 9 | 9 | 7 | 63 | 2m 42s | 121.51 | 3.04× | -1.23% | 770.7 | 807.1 | 87.7% | 13.1 GiB |
| e9k — rh8-al320 (192 vCPU) | 10 | 10 | 6 | 60 | 2m 44s | 120.02 | 3.01× | -2.44% | 833.1 | 895.0 | 90.6% | 13.3 GiB |
| e9k — rh8-al320 (192 vCPU) | 14 | 14 | 4 | 56 | 2m 59s | 109.97 | 2.75× | -10.61% | 1003.0 | 1036.5 | 93.4% | 13.9 GiB |
| e9k — rh8-al320 (192 vCPU) | 16 | 16 | 4 | 64 | 2m 52s | 114.44 | 2.87× | -6.98% | 837.0 | 968.7 | 89.5% | 14.2 GiB |
| e9k — rh8-al320 (192 vCPU) | 23 | 23 | 2 | 46 | 3m 55s | 83.76 | 2.10× | -31.91% | 1063.9 | 1195.0 | 94.0% | 15.1 GiB |
| e9k — rh8-al320 (192 vCPU) | 64 | 64 | 1 | 64 | 4m 43s | 69.55 | 1.74× | -43.46% | 1677.1 | 1997.1 | 92.3% | 20.5 GiB |

</details>

<a id="detector-shape-data-contour-projection"></a>
<details>
<summary><strong>contour_projection</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 34m 26s | 3.18 | 1.00× | -93.61% | 7.1 | 28.3 | 4.0% | 16.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 10 | 10 | 38 | 380 | 3m 24s | 32.17 | 10.13× | -35.29% | 1322.6 | 1398.2 | 83.4% | 17.3 GiB |
| 192t — rh8-al321 (192 vCPU) | 11 | 11 | 34 | 374 | 3m 2s | 36.05 | 11.35× | -27.47% | 1631.2 | 1749.7 | 91.5% | 17.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 12 | 12 | 32 | 384 | 2m 39s | 41.27 | 12.99× | -16.98% | 1316.0 | 1518.0 | 92.2% | 17.6 GiB |
| 192t — rh8-al321 (192 vCPU) | 13 | 13 | 29 | 377 | 2m 31s | 43.46 | 13.68× | -12.58% | 1397.5 | 1502.5 | 91.9% | 17.6 GiB |
| 192t — rh8-al321 (192 vCPU) | 14 | 14 | 27 | 378 | 2m 29s | 44.04 | 13.87× | -11.41% | 1483.2 | 1541.3 | 97.8% | 17.7 GiB |
| 192t — rh8-al321 (192 vCPU) | 15 | 15 | 25 | 375 | 2m 24s | 45.57 | 14.35× | -8.33% | 1423.3 | 1483.7 | 92.9% | 17.7 GiB |
| 192t — rh8-al321 (192 vCPU) | 16 | 16 | 24 | 384 | 2m 26s | 44.95 | 14.15× | -9.59% | 1565.7 | 1609.1 | 95.4% | 18.0 GiB |
| 192t — rh8-al321 (192 vCPU) | 17 | 17 | 22 | 374 | 2m 18s | 47.55 | 14.97× | -4.35% | 1408.5 | 1466.7 | 89.9% | 17.9 GiB |
| 192t — rh8-al321 (192 vCPU) | 18 | 18 | 21 | 378 | 2m 16s | 48.25 | 15.19× | -2.94% | 1396.7 | 1472.8 | 92.8% | 18.1 GiB |
| 192t — rh8-al321 (192 vCPU) | 19 | 19 | 20 | 380 | 2m 15s | 48.61 | 15.30× | -2.22% | 1373.0 | 1507.7 | 94.8% | 18.2 GiB |
| 192t — rh8-al321 (192 vCPU) | 20 | 20 | 19 | 380 | 2m 15s | 48.61 | 15.30× | -2.22% | 1538.1 | 1577.0 | 96.6% | 18.4 GiB |
| **192t — rh8-al321 (192 vCPU)** | 21 | 21 | 18 | 378 | 2m 12s | 49.71 | 15.65× | 0.00% | 1516.3 | 1567.4 | 92.8% | 18.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 22 | 22 | 17 | 374 | 2m 15s | 48.61 | 15.30× | -2.22% | 1508.4 | 1532.1 | 94.7% | 18.5 GiB |
| 192t — rh8-al321 (192 vCPU) | 128 | 128 | 3 | 384 | 3m 4s | 35.66 | 11.23× | -28.26% | 1817.4 | 2605.0 | 82.9% | 30.3 GiB |

</details>

<a id="detector-shape-data-grabcut"></a>
<details>
<summary><strong>grabcut</strong></summary>

**Search method(s):** `exhaustive, powers-of-2`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **e7k — rh8-al97 (96 vCPU)** | 1 | 1 | 192 | 192 | 1h 54m | 1.92 | 1.00× | -0.29% | 232.1 | 258.1 | 97.2% | 53.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 2 | 2 | 96 | 192 | 1h 53m 40s | 1.92 | 1.00× | 0.00% | 281.1 | 317.0 | 98.3% | 53.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 4 | 4 | 48 | 192 | 1h 57m 14s | 1.87 | 0.97× | -3.04% | 321.1 | 377.9 | 99.3% | 53.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 8 | 8 | 24 | 192 | 1h 57m 47s | 1.86 | 0.97× | -3.50% | 328.4 | 420.9 | 99.2% | 54.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 16 | 16 | 12 | 192 | 1h 58m 17s | 1.85 | 0.96× | -3.90% | 343.3 | 435.7 | 99.3% | 54.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 49 | 49 | 3 | 147 | 2h 53s | 1.81 | 0.94× | -5.97% | 316.9 | 407.2 | 98.7% | 49.1 GiB |

</details>

</details>

[↑ Back to Navigation](#table-of-contents)
