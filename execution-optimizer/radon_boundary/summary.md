### Execution optimizer summary

Detector: `radon_boundary`  
Optimizer run: **35524389164** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| radon_boundary | 192t — rh8-al318 (192 vCPU) | 35524389164 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 7 | 54 | 5p/76t, 7p/54t, 8p/48t | adaptive | 3m 22s | 378 | 16.00 | 16s | 10 |
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
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 1 | 1 | 384 | 384 | 28s | 1s | 9.14 | 1.00× | -42.86% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 3 | 3 | 128 | 384 | 18s | 1s | 14.22 | 1.56× | -11.11% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 4 | 4 | 96 | 384 | 17s | 1s | 15.06 | 1.65× | -5.88% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 5 | 5 | 76 | 380 | 16s | 1s | 16.00 | 1.75× | 0.00% | 382.2 | 382.2 | 52.8% | 29.3 GiB |
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 6 | 6 | 64 | 384 | 17s | 1s | 15.06 | 1.65× | -5.88% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 35524389164 | 7 | 7 | 54 | 378 | 16s | 1s | 16.00 | 1.75× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 8 | 8 | 48 | 384 | 16s | 1s | 16.00 | 1.75× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 9 | 9 | 42 | 378 | 17s | 1s | 15.06 | 1.65× | -5.88% | 183.7 | 183.7 | 35.4% | 27.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 10 | 10 | 38 | 380 | 17s | 1s | 15.06 | 1.65× | -5.88% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 35524389164 | 192 | 192 | 2 | 384 | 28s | 4s | 9.14 | 1.00× | -42.86% | 717.4 | 717.4 | 26.7% | 26.2 GiB |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
