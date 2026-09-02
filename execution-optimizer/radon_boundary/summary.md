### Execution optimizer summary

Detector: `radon_boundary`  
Optimizer run: **33637621563** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| radon_boundary | 192t — rh8-al320 (192 vCPU) | 33637621563 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 7 | 54 | 3p/128t, 4p/96t, 5p/76t, 6p/64t, 7p/54t | adaptive | 59s | 378 | 64.00 | 4s | 10 |

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
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 1 | 1 | 384 | 384 | 6s | 0s | 42.67 | 1.00× | -33.33% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 2 | 2 | 192 | 384 | 5s | 0s | 51.20 | 1.20× | -20.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 3 | 3 | 128 | 384 | 4s | 0s | 64.00 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 4 | 4 | 96 | 384 | 4s | 0s | 64.00 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 5 | 5 | 76 | 380 | 4s | 0s | 64.00 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 6 | 6 | 64 | 384 | 4s | 0s | 64.00 | 1.50× | 0.00% | — | — | — | — |
| **192t — rh8-al320 (192 vCPU)** | 33637621563 | 7 | 7 | 54 | 378 | 4s | 0s | 64.00 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 8 | 8 | 48 | 384 | 5s | 0s | 51.20 | 1.20× | -20.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 9 | 9 | 42 | 378 | 5s | 0s | 51.20 | 1.20× | -20.00% | 109.4 | 109.4 | 25.7% | 7.7 GiB |
| 192t — rh8-al320 (192 vCPU) | 33637621563 | 192 | 192 | 2 | 384 | 11s | 3s | 23.27 | 0.55× | -63.64% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Stop reason:** `adaptive_search_complete`

</details>

[↑ Back to Navigation](#table-of-contents)
