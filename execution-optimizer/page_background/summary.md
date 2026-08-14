### Execution optimizer summary

Detector: `page_background`  
Optimizer run: **31763872761** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| page_background | 192t — rh8-al307 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 5 | 76 | 4p/96t, 5p/76t | adaptive | 3m 6s | 380 | 136.75 | 16s | 1 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction coverage:** vCPU anchors `192`; readiness **low**; prediction checks **0 verified / 0 pending**.
**Desired / missing optimization data:** missing: a second vCPU size to establish shape scaling.

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
| 192t — rh8-al307 (192 vCPU) | 1 | 1 | 384 | 384 | 40s | 54.70 | 1.00× | -60.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 3 | 3 | 128 | 384 | 19s | 115.16 | 2.11× | -15.79% | 138.7 | 138.7 | 41.0% | 41.3 GiB |
| 192t — rh8-al307 (192 vCPU) | 4 | 4 | 96 | 384 | 16s | 136.75 | 2.50× | 0.00% | — | — | — | — |
| **192t — rh8-al307 (192 vCPU)** | 5 | 5 | 76 | 380 | 16s | 136.75 | 2.50× | 0.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 6 | 6 | 64 | 384 | 17s | 128.71 | 2.35× | -5.88% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 7 | 7 | 54 | 378 | 18s | 121.56 | 2.22× | -11.11% | 224.1 | 224.1 | 36.3% | 22.3 GiB |
| 192t — rh8-al307 (192 vCPU) | 8 | 8 | 48 | 384 | 18s | 121.56 | 2.22× | -11.11% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 64 | 64 | 6 | 384 | 37s | 59.14 | 1.08× | -56.76% | 313.5 | 313.5 | 27.4% | 22.8 GiB |

**Stop reason:** `adaptive_search_complete`

</details>

[↑ Back to Navigation](#table-of-contents)
