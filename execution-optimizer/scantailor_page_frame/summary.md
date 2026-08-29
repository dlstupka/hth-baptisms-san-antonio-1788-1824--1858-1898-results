### Execution optimizer summary

Detector: `scantailor_page_frame`  
Optimizer run: **33279699408** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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

Compatible completed optimizer runs are coalesced by detector, workload, and concrete runner profile. Repeated shapes retain all observations; the preferred shape is selected canonically by throughput, then newest compatible optimizer run, then lower resource use within a run.

| Detector | Runner | CPU | Physical | Logical | RAM | Preferred pipelines | Threads / pipeline | Preferred shape range (≤2%) | Search method | Optimization time | Allocated | Sets/s | Shape time | Observations |
|---|---|---|---:|---:|---:|---:|---:|---|---|---:|---:|---:|---:|---:|
| scantailor_page_frame | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 2 | 192 | 2p/192t | legacy | 1m 8s | 384 | 5.00 | 11s | 4 |

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

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al318 (192 vCPU)** | 2 | 2 | 192 | 384 | 11s | 0s | 5.00 | — | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 3 | 3 | 128 | 384 | 12s | 0s | 4.58 | — | -8.33% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 6 | 6 | 64 | 384 | 15s | 0s | 3.67 | — | -26.67% | 473.4 | 473.4 | 64.9% | 10.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 20 | 20 | 19 | 380 | 30s | 1s | 1.83 | — | -63.33% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Stop reason:** `adaptive_search_complete`

</details>

[↑ Back to Navigation](#table-of-contents)
