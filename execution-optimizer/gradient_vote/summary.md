### Execution optimizer summary

Detector: `gradient_vote`  
Optimizer run: **31336973065** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| gradient_vote | 192t — rh8-al325 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 9 | 42 | 9p/42t, 10p/38t | adaptive | 1m 38s | 378 | 729.11 | 9s | 1 |

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
| 192t — rh8-al325 (192 vCPU) | 1 | 1 | 384 | 384 | 30s | 218.73 | 1.00× | -70.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 7 | 7 | 54 | 378 | 12s | 546.83 | 2.50× | -25.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 8 | 8 | 48 | 384 | 10s | 656.20 | 3.00× | -10.00% | 331.5 | 331.5 | 27.5% | 10.7 GiB |
| **192t — rh8-al325 (192 vCPU)** | 9 | 9 | 42 | 378 | 9s | 729.11 | 3.33× | 0.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 10 | 10 | 38 | 380 | 9s | 729.11 | 3.33× | 0.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 11 | 11 | 34 | 374 | 10s | 656.20 | 3.00× | -10.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 64 | 64 | 6 | 384 | 16s | 410.12 | 1.88× | -43.75% | — | — | — | — |

**Stop reason:** `adaptive_search_complete`

</details>

[↑ Back to Navigation](#table-of-contents)
