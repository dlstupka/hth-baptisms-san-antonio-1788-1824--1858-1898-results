### Execution optimizer summary

Detector: `orli_page_mask`  
Optimizer run: **32160375460** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| orli_page_mask | 192t — rh8-al316 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 2897.3 GiB | 12 | 32 | 12p/32t | legacy | 7m 51s | 384 | 303.03 | 33s | 1 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction coverage:** vCPU anchors `192`; readiness **low**; prediction checks **0 verified / 0 pending**.
**Desired / missing optimization data:** missing: a second vCPU size to establish shape scaling.

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-run-profile-plot"></a>
<details open>
<summary><strong>2. Detector Run Profile Plot</strong></summary>

Compatible completed measurements are plotted as detector pipelines versus parameter sets/second; thread count is annotated at each measured shape.
**Search method:** `exhaustive`

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
| 192t — rh8-al316 (192 vCPU) | 8 | 8 | 48 | 384 | 3m 48s | 43.86 | — | -85.53% | 0.2 | 0.3 | 0.1% | 16.3 GiB |
| 192t — rh8-al316 (192 vCPU) | 9 | 9 | 42 | 378 | 37s | 270.27 | — | -10.81% | 6.8 | 6.8 | 10.4% | 16.4 GiB |
| 192t — rh8-al316 (192 vCPU) | 10 | 10 | 38 | 380 | 36s | 277.78 | — | -8.33% | 18.4 | 18.4 | 18.9% | 16.4 GiB |
| 192t — rh8-al316 (192 vCPU) | 11 | 11 | 34 | 374 | 35s | 285.71 | — | -5.71% | — | — | — | — |
| **192t — rh8-al316 (192 vCPU)** | 12 | 12 | 32 | 384 | 33s | 303.03 | — | 0.00% | 81.4 | 81.4 | 18.7% | 21.3 GiB |
| 192t — rh8-al316 (192 vCPU) | 13 | 13 | 29 | 377 | 34s | 294.12 | — | -2.94% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 14 | 14 | 27 | 378 | 34s | 294.12 | — | -2.94% | 64.8 | 64.8 | 16.3% | 20.3 GiB |
| 192t — rh8-al316 (192 vCPU) | 15 | 15 | 25 | 375 | 34s | 294.12 | — | -2.94% | 63.7 | 63.7 | 17.9% | 16.4 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
