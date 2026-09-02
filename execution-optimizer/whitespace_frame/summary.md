### Execution optimizer summary

Detector: `whitespace_frame`  
Optimizer run: **33635891782** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| whitespace_frame | 192t — rh8-al318 (192 vCPU) | 33635891782 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 11 | 34 | 2p/192t, 4p/96t, 5p/76t, 6p/64t, 7p/54t, 8p/48t, 9p/42t, 10p/38t, 11p/34t, 12p/32t, 13p/29t, 14p/27t, 15p/25t, 16p/24t, 17p/22t, 18p/21t | adaptive | 1m 26s | 374 | 85.33 | 3s | 21 |

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
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 1 | 1 | 384 | 384 | 4s | 0s | 64.00 | 1.00× | -25.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 2 | 2 | 192 | 384 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 3 | 3 | 128 | 384 | 4s | 0s | 64.00 | 1.00× | -25.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 4 | 4 | 96 | 384 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 5 | 5 | 76 | 380 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 6 | 6 | 64 | 384 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 7 | 7 | 54 | 378 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 8 | 8 | 48 | 384 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 9 | 9 | 42 | 378 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 10 | 10 | 38 | 380 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 33635891782 | 11 | 11 | 34 | 374 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 12 | 12 | 32 | 384 | 3s | 0s | 85.33 | 1.33× | 0.00% | 314.5 | 314.5 | 22.0% | 7.8 GiB |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 13 | 13 | 29 | 377 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 14 | 14 | 27 | 378 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 15 | 15 | 25 | 375 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 16 | 16 | 24 | 384 | 3s | 0s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 17 | 17 | 22 | 374 | 3s | 1s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 18 | 18 | 21 | 378 | 3s | 1s | 85.33 | 1.33× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 19 | 19 | 20 | 380 | 4s | 1s | 64.00 | 1.00× | -25.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 20 | 20 | 19 | 380 | 4s | 1s | 64.00 | 1.00× | -25.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33635891782 | 192 | 192 | 2 | 384 | 11s | 3s | 23.27 | 0.36× | -72.73% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Stop reason:** `adaptive_search_complete`

</details>

[↑ Back to Navigation](#table-of-contents)
