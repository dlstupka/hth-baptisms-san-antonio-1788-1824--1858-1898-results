### Execution optimizer summary

Detector: `contour_components`  
Optimizer run: **31404150763** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

<a id="table-of-contents"></a>

<details open>
<summary><strong>Navigation</strong></summary>

- [Preferred Detector Run Configuration](#preferred-detector-run-configuration)
- [Detector Run Profile Plot](#detector-run-profile-plot)
- [Detector Pipeline-Thread Shape Optimization Data](#detector-pipeline-thread-shape-optimization-data)

</details>

<a id="preferred-detector-run-configuration"></a>
<details open>
<summary><strong>1. Preferred Detector Run Configuration</strong></summary>

Compatible completed optimizer runs are coalesced by detector, workload, and concrete runner profile. Repeated shapes retain all observations; the preferred shape is selected canonically by throughput, then lower resource use for throughput-equivalent shapes.

| Detector | Runner | CPU | Physical | Logical | RAM | Preferred pipelines | Threads / pipeline | Preferred shape range (≤2%) | Search method | Optimization time | Allocated | Sets/s | Shape time | Observations |
|---|---|---|---:|---:|---:|---:|---:|---|---|---:|---:|---:|---:|---:|
| contour_components | 192t — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 19 | 20 | 18p/21t, 19p/20t, 20p/19t, 21p/18t, 32p/12t | adaptive | 24m 29s | 380 | 223.68 | 1m 28s | 1 |
| contour_components | e7k — rh8-al97 (96 vCPU) | AMD EPYC 74F3 24-Core Processor | 48 | 96 | 2003.9 GiB | 47 | 4 | 43p/4t, 44p/4t, 45p/4t, 46p/4t, 47p/4t, 48p/4t | adaptive | 1h 25m 28s | 188 | 111.21 | 2m 57s | 1 |
| contour_components | e9k — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 8 | 7p/9t, 8p/8t, 9p/7t | adaptive | 19m 31s | 64 | 123.03 | 2m 40s | 2 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-run-profile-plot"></a>
<details open>
<summary><strong>2. Detector Run Profile Plot</strong></summary>

Compatible completed measurements are plotted as detector pipelines versus parameter sets/second; thread count is annotated at each measured shape.
**Search method:** `adaptive`

![Detector Run Profile Plot](heatmap.svg)

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-pipeline-thread-shape-optimization-data"></a>
<details>
<summary><strong>3. Detector Pipeline-Thread Shape Optimization Data</strong></summary>

Shapes completed in this execution are shown below.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e7k — rh8-al97 (96 vCPU) | 1 | 1 | 16 | 16 | 14m 2s | 23.38 | 1.00× | -78.98% | 16.1 | 24.6 | 18.4% | 14.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 10 | 10 | 16 | 160 | 6m 6s | 53.78 | 2.30× | -51.64% | 454.6 | 792.4 | 79.4% | 17.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 30 | 30 | 6 | 180 | 3m 18s | 99.41 | 4.25× | -10.61% | 834.2 | 949.1 | 87.4% | 20.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 31 | 31 | 6 | 186 | 3m 15s | 100.94 | 4.32× | -9.23% | 715.4 | 1017.6 | 84.9% | 20.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 32 | 32 | 6 | 192 | 3m 12s | 102.52 | 4.39× | -7.81% | 954.6 | 1066.2 | 91.2% | 20.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 33 | 33 | 5 | 165 | 3m 10s | 103.60 | 4.43× | -6.84% | 895.0 | 998.6 | 87.2% | 20.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 34 | 34 | 5 | 170 | 3m 9s | 104.15 | 4.46× | -6.35% | 947.3 | 1128.1 | 87.3% | 20.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 35 | 35 | 5 | 175 | 3m 8s | 104.70 | 4.48× | -5.85% | 924.0 | 1096.1 | 86.7% | 21.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 36 | 36 | 5 | 180 | 3m 5s | 106.40 | 4.55× | -4.32% | 984.5 | 1169.9 | 87.1% | 21.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 37 | 37 | 5 | 185 | 3m 4s | 106.98 | 4.58× | -3.80% | 934.3 | 1115.4 | 86.3% | 21.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 38 | 38 | 5 | 190 | 3m 3s | 107.56 | 4.60× | -3.28% | 958.6 | 1229.5 | 81.2% | 21.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 39 | 39 | 4 | 156 | 3m 2s | 108.15 | 4.63× | -2.75% | 987.2 | 1155.3 | 87.1% | 21.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 40 | 40 | 4 | 160 | 3m 2s | 108.15 | 4.63× | -2.75% | 1032.7 | 1171.5 | 86.7% | 21.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 41 | 41 | 4 | 164 | 3m 2s | 108.15 | 4.63× | -2.75% | 1048.3 | 1242.9 | 85.8% | 21.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 42 | 42 | 4 | 168 | 3m 1s | 108.75 | 4.65× | -2.21% | 1046.8 | 1207.3 | 85.4% | 21.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 43 | 43 | 4 | 172 | 3m | 109.36 | 4.68× | -1.67% | 1094.2 | 1262.6 | 84.9% | 21.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 44 | 44 | 4 | 176 | 3m | 109.36 | 4.68× | -1.67% | 1093.6 | 1289.7 | 84.1% | 22.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 45 | 45 | 4 | 180 | 3m | 109.36 | 4.68× | -1.67% | 1094.0 | 1280.3 | 83.8% | 22.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 46 | 46 | 4 | 184 | 3m | 109.36 | 4.68× | -1.67% | 1123.7 | 1362.3 | 84.0% | 22.6 GiB |
| **e7k — rh8-al97 (96 vCPU)** | 47 | 47 | 4 | 188 | 2m 57s | 111.21 | 4.76× | 0.00% | 1155.0 | 1411.6 | 82.0% | 22.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 48 | 48 | 4 | 192 | 2m 58s | 110.58 | 4.73× | -0.56% | 1187.8 | 1341.9 | 97.1% | 23.0 GiB |
| e7k — rh8-al97 (96 vCPU) | 49 | 49 | 3 | 147 | 3m 8s | 104.70 | 4.48× | -5.85% | 1073.1 | 1384.4 | 78.4% | 22.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 96 | 96 | 2 | 192 | 3m 30s | 93.73 | 4.01× | -15.71% | 1499.2 | 1779.0 | 93.9% | 28.8 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
