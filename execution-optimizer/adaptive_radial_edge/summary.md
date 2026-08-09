### Execution optimizer summary

Detector: `adaptive_radial_edge`  
Optimizer run: **31338290101** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 23m 29s | 4.66 | 1.00× | -96.95% | 2.4 | 8.2 | 1.2% | 22.1 GiB |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 3m 2s | 36.05 | 7.74× | -76.37% | 173.1 | 327.3 | 12.2% | 23.1 GiB |
| 192t — rh8-al323 (192 vCPU) | 23 | 23 | 16 | 368 | 1m 12s | 91.14 | 19.57× | -40.28% | 143.0 | 143.0 | 24.3% | 24.5 GiB |
| 192t — rh8-al323 (192 vCPU) | 38 | 38 | 10 | 380 | 50s | 131.24 | 28.18× | -14.00% | 265.3 | 265.3 | 43.3% | 26.8 GiB |
| 192t — rh8-al323 (192 vCPU) | 49 | 49 | 7 | 343 | 47s | 139.62 | 29.98× | -8.51% | 732.8 | 732.8 | 74.4% | 18.1 GiB |
| 192t — rh8-al323 (192 vCPU) | 56 | 56 | 6 | 336 | 44s | 149.14 | 32.02× | -2.27% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 59 | 59 | 6 | 354 | 45s | 145.82 | 31.31× | -4.44% | 809.4 | 809.4 | 78.4% | 28.7 GiB |
| **192t — rh8-al323 (192 vCPU)** | 60 | 60 | 6 | 360 | 43s | 152.60 | 32.77× | 0.00% | 693.5 | 693.5 | 60.9% | 28.4 GiB |
| 192t — rh8-al323 (192 vCPU) | 61 | 61 | 6 | 366 | 45s | 145.82 | 31.31× | -4.44% | 1025.5 | 1025.5 | 71.5% | 11.3 GiB |
| 192t — rh8-al323 (192 vCPU) | 64 | 64 | 6 | 384 | 43s | 152.60 | 32.77× | 0.00% | 591.5 | 591.5 | 41.2% | 30.2 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
