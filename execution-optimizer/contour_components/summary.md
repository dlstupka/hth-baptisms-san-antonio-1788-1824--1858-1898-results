### Execution optimizer summary

Detector: `contour_components`  
Optimizer run: **31418703875** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| contour_components | 32t — rh8-s32 (32 vCPU) | AMD EPYC 9175F 16-Core Processor | 16 | 32 | 1511.3 GiB | 9 | 7 | 8p/8t, 9p/7t, 10p/6t | adaptive | 25m 59s | 63 | 106.98 | 3m 4s | 1 |
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
| 32t — rh8-s32 (32 vCPU) | 2 | 2 | 32 | 64 | 6m 29s | 50.60 | — | -52.70% | 28.5 | 38.3 | 61.8% | 14.0 GiB |
| 32t — rh8-s32 (32 vCPU) | 7 | 7 | 9 | 63 | 3m 8s | 104.70 | — | -2.13% | 169.8 | 177.8 | 95.0% | 14.5 GiB |
| 32t — rh8-s32 (32 vCPU) | 8 | 8 | 8 | 64 | 3m 6s | 105.83 | — | -1.08% | 185.3 | 193.4 | 94.2% | 14.7 GiB |
| **32t — rh8-s32 (32 vCPU)** | 9 | 9 | 7 | 63 | 3m 4s | 106.98 | — | 0.00% | 168.1 | 177.8 | 95.1% | 14.7 GiB |
| 32t — rh8-s32 (32 vCPU) | 10 | 10 | 6 | 60 | 3m 6s | 105.83 | — | -1.08% | 172.6 | 181.3 | 95.1% | 14.7 GiB |
| 32t — rh8-s32 (32 vCPU) | 11 | 11 | 5 | 55 | 3m 9s | 104.15 | — | -2.65% | 171.6 | 178.2 | 95.1% | 14.8 GiB |
| 32t — rh8-s32 (32 vCPU) | 32 | 32 | 2 | 64 | 3m 52s | 84.84 | — | -20.69% | 218.8 | 283.7 | 92.0% | 17.0 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
