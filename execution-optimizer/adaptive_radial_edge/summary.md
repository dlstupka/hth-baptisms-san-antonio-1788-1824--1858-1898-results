### Execution optimizer summary

Detector: `adaptive_radial_edge`  
Optimizer run: **33007779343** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| adaptive_radial_edge | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 55 | 6 | 16p/24t, 55p/6t | legacy | 3m 5s | 330 | 15.06 | 17s | 9 |

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
| 192t — rh8-al321 (192 vCPU) | 16 | 16 | 24 | 384 | 17s | 1s | 15.06 | — | 0.00% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 55 | 55 | 6 | 330 | 17s | 1s | 15.06 | — | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 56 | 56 | 6 | 336 | 18s | 1s | 14.22 | — | -5.56% | 238.5 | 238.5 | 37.3% | 10.6 GiB |
| 192t — rh8-al321 (192 vCPU) | 57 | 57 | 6 | 342 | 18s | 1s | 14.22 | — | -5.56% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 59 | 59 | 6 | 354 | 19s | 1s | 13.47 | — | -10.53% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 64 | 64 | 6 | 384 | 18s | 1s | 14.22 | — | -5.56% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 75 | 75 | 5 | 375 | 19s | 2s | 13.47 | — | -10.53% | 145.2 | 145.2 | 44.9% | 8.7 GiB |
| 192t — rh8-al321 (192 vCPU) | 103 | 103 | 3 | 309 | 22s | 2s | 11.64 | — | -22.73% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 192 | 192 | 2 | 384 | 37s | 3s | 6.92 | — | -54.05% | 98.1 | 98.1 | 41.6% | 7.8 GiB |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
