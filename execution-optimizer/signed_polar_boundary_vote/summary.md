### Execution optimizer summary

Detector: `signed_polar_boundary_vote`  
Optimizer run: **33334407643** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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

| Detector | Runner | Optimizer run | CPU | Physical | Logical | RAM | Preferred pipelines | Threads / pipeline | Preferred shape range (≤2%) | Search method | Optimization time | Allocated | Sets/s | Shape time | Observations |
|---|---|---|---|---:|---:|---:|---:|---:|---|---|---:|---:|---:|---:|---:|
| signed_polar_boundary_vote | 192t — rh8-al319 (192 vCPU) | 33334407643 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 16 | 24 | 16p/24t | legacy | 1m 42s | 384 | 64.00 | 4s | 16 |

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

| Runner | Optimizer run | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 1 | 1 | 384 | 384 | 19s | 0s | 13.47 | 1.00× | -78.95% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 5 | 5 | 76 | 380 | 6s | 1s | 42.67 | 3.17× | -33.33% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 6 | 6 | 64 | 384 | 6s | 1s | 42.67 | 3.17× | -33.33% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 7 | 7 | 54 | 378 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 8 | 8 | 48 | 384 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 9 | 9 | 42 | 378 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 10 | 10 | 38 | 380 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 11 | 11 | 34 | 374 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 12 | 12 | 32 | 384 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 13 | 13 | 29 | 377 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 14 | 14 | 27 | 378 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 15 | 15 | 25 | 375 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 33334407643 | 16 | 16 | 24 | 384 | 4s | 1s | 64.00 | 4.75× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 17 | 17 | 22 | 374 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 18 | 18 | 21 | 378 | 5s | 1s | 51.20 | 3.80× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 33334407643 | 192 | 192 | 2 | 384 | 12s | 4s | 21.33 | 1.58× | -66.67% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
