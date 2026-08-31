### Execution optimizer summary

Detector: `radial_edge`  
Optimizer run: **33396773893** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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

Compatible completed optimizer runs are coalesced by stable detector evidence identity and concrete runner profile; search scope is retained only as informational provenance. Repeated shapes retain all observations; the preferred shape is selected canonically by throughput, then newest compatible optimizer run, then lower resource use within a run.

| Detector | Runner | Optimizer run | CPU | Physical | Logical | RAM | Preferred pipelines | Threads / pipeline | Preferred shape range (≤2%) | Search method | Optimization time | Allocated | Sets/s | Shape time | Observations |
|---|---|---|---|---:|---:|---:|---:|---:|---|---|---:|---:|---:|---:|---:|
| radial_edge | 192t — rh8-al316 (192 vCPU) | 33340290180 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 2897.3 GiB | 24 | 16 | 24p/16t | adaptive | 48s | 384 | 64.00 | 4s | 7 |
| radial_edge | 32t — rh8-s32 (32 vCPU) | 33396773893 | AMD EPYC 9175F 16-Core Processor | 16 | 32 | 1511.3 GiB | 10 | 6 | 10p/6t | adaptive | 1m 16s | 60 | 64.00 | 4s | 13 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction coverage:** vCPU anchors `32, 192`; readiness **moderate**; prediction checks **1 verified / 0 pending**.
**Desired / missing optimization data:** desired: a third vCPU size to validate interpolation/extrapolation.

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
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 1 | 1 | 64 | 64 | 8s | 0s | 32.00 | 1.00× | -50.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 2 | 2 | 32 | 64 | 7s | 0s | 36.57 | 1.14× | -42.86% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 3 | 3 | 21 | 63 | 6s | 0s | 42.67 | 1.33× | -33.33% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 4 | 4 | 16 | 64 | 5s | 0s | 51.20 | 1.60× | -20.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 5 | 5 | 12 | 60 | 5s | 0s | 51.20 | 1.60× | -20.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 6 | 6 | 10 | 60 | 5s | 1s | 51.20 | 1.60× | -20.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 7 | 7 | 9 | 63 | 5s | 1s | 51.20 | 1.60× | -20.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 8 | 8 | 8 | 64 | 5s | 1s | 51.20 | 1.60× | -20.00% | 35.7 | 35.7 | 35.2% | 13.7 GiB |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 9 | 9 | 7 | 63 | 5s | 1s | 51.20 | 1.60× | -20.00% | — | — | — | — |
| **32t — rh8-s32 (32 vCPU)** | 33396773893 | 10 | 10 | 6 | 60 | 4s | 1s | 64.00 | 2.00× | 0.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 11 | 11 | 5 | 55 | 5s | 1s | 51.20 | 1.60× | -20.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 12 | 12 | 5 | 60 | 5s | 1s | 51.20 | 1.60× | -20.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 33396773893 | 32 | 32 | 2 | 64 | 7s | 1s | 36.57 | 1.14× | -42.86% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
