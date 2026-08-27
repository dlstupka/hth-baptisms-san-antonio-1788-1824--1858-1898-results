### Execution optimizer summary

Detector: `dhsegment_page_mask`  
Optimizer run: **33078880307** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| dhsegment_page_mask | 32t — rh8-s32 (32 vCPU) | AMD EPYC 9175F 16-Core Processor | 16 | 32 | 1511.3 GiB | 15 | 4 | 15p/4t | legacy | 1m 31s | 60 | 21.33 | 12s | 7 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction coverage:** vCPU anchors `32`; readiness **low**; prediction checks **0 verified / 0 pending**.
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

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 32t — rh8-s32 (32 vCPU) | 1 | 1 | 64 | 64 | 13s | 2s | 19.69 | 1.00× | -7.69% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 6 | 6 | 10 | 60 | 13s | 9s | 19.69 | 1.00× | -7.69% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 14 | 14 | 4 | 56 | 13s | 9s | 19.69 | 1.00× | -7.69% | — | — | — | — |
| **32t — rh8-s32 (32 vCPU)** | 15 | 15 | 4 | 60 | 12s | 9s | 21.33 | 1.08× | 0.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 16 | 16 | 4 | 64 | 13s | 9s | 19.69 | 1.00× | -7.69% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 17 | 17 | 3 | 51 | 13s | 10s | 19.69 | 1.00× | -7.69% | 24.9 | 24.9 | 18.6% | 13.6 GiB |
| 32t — rh8-s32 (32 vCPU) | 21 | 21 | 3 | 63 | 14s | 10s | 18.29 | 0.93× | -14.29% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
