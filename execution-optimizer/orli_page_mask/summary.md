### Execution optimizer summary

Detector: `orli_page_mask`  
Optimizer run: **32152806852** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| orli_page_mask | 192t — rh8-al307 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 14 | 27 | 14p/27t | legacy | 10m 20s | 378 | 303.03 | 33s | 1 |

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

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al307 (192 vCPU) | 2 | 2 | 192 | 384 | 6m 4s | 27.47 | — | -90.93% | 2.2 | 6.7 | 1.4% | 27.8 GiB |
| 192t — rh8-al307 (192 vCPU) | 10 | 10 | 38 | 380 | 35s | 285.71 | — | -5.71% | 77.6 | 77.6 | 18.9% | 28.8 GiB |
| 192t — rh8-al307 (192 vCPU) | 11 | 11 | 34 | 374 | 34s | 294.12 | — | -2.94% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 12 | 12 | 32 | 384 | 34s | 294.12 | — | -2.94% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 13 | 13 | 29 | 377 | 34s | 294.12 | — | -2.94% | 83.7 | 83.7 | 17.5% | 29.0 GiB |
| **192t — rh8-al307 (192 vCPU)** | 14 | 14 | 27 | 378 | 33s | 303.03 | — | 0.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 15 | 15 | 25 | 375 | 34s | 294.12 | — | -2.94% | 76.0 | 76.0 | 14.9% | 24.3 GiB |
| 192t — rh8-al307 (192 vCPU) | 64 | 64 | 6 | 384 | 52s | 192.31 | — | -36.54% | 42.3 | 42.3 | 15.8% | 24.1 GiB |

**Stop reason:** `adaptive_search_complete`

</details>

[↑ Back to Navigation](#table-of-contents)
