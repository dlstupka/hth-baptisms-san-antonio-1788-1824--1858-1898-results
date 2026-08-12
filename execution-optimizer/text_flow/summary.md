### Execution optimizer summary

Detector: `text_flow`  
Optimizer run: **31632959290** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| text_flow | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 8p/48t | adaptive | 1m 3s | 384 | 145.80 | 5s | 1 |

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
| **192t — rh8-al319 (192 vCPU)** | 1 | 1 | 384 | 384 | 5s | 145.80 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 5s | 145.80 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 6s | 121.50 | 0.83× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 11 | 11 | 34 | 374 | 6s | 121.50 | 0.83× | -16.67% | 394.0 | 394.0 | 20.1% | 11.0 GiB |
| 192t — rh8-al319 (192 vCPU) | 14 | 14 | 27 | 378 | 6s | 121.50 | 0.83× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 23 | 23 | 16 | 368 | 9s | 81.00 | 0.56× | -44.44% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 23s | 31.70 | 0.22× | -78.26% | — | — | — | — |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
