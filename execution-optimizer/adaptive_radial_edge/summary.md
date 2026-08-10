### Execution optimizer summary

Detector: `adaptive_radial_edge`  
Optimizer run: **31349243699** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| adaptive_radial_edge | 192t — rh8-al323 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 60 | 6 | 60p/6t, 64p/6t | adaptive | 33m 4s | 360 | 152.60 | 43s | 1 |
| adaptive_radial_edge | e7k — rh8-al97 (96 vCPU) | AMD EPYC 74F3 24-Core Processor | 48 | 96 | 2003.9 GiB | 49 | 3 | 46p/4t, 49p/3t, 50p/3t, 51p/3t, 52p/3t | exhaustive | 3h 35m 57s | 147 | 70.56 | 1m 33s | 1 |

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
| 192t — rh8-al323 (192 vCPU) | 48 | 48 | 8 | 384 | 47s | 139.62 | — | -6.38% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 68 | 68 | 5 | 340 | 47s | 139.62 | — | -6.38% | 660.2 | 660.2 | 67.1% | 29.3 GiB |
| 192t — rh8-al323 (192 vCPU) | 80 | 80 | 4 | 320 | 48s | 136.71 | — | -8.33% | 715.1 | 715.1 | 52.4% | 11.2 GiB |
| **192t — rh8-al323 (192 vCPU)** | 81 | 81 | 4 | 324 | 44s | 149.14 | — | 0.00% | 798.7 | 798.7 | 68.7% | 17.9 GiB |
| 192t — rh8-al323 (192 vCPU) | 82 | 82 | 4 | 328 | 49s | 133.92 | — | -10.20% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 96 | 96 | 4 | 384 | 48s | 136.71 | — | -8.33% | 470.6 | 470.6 | 63.6% | 28.3 GiB |

**Stop reason:** `adaptive_search_complete`

</details>

[↑ Back to Navigation](#table-of-contents)
