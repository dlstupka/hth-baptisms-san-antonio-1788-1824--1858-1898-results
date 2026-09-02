### Execution optimizer summary

Detector: `adaptive_radial_edge`  
Optimizer run: **33674606921** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| adaptive_radial_edge | 192t — rh8-al318 (192 vCPU) | 33013480994 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 55 | 6 | 55p/6t | adaptive | 56s | 330 | 32.00 | 8s | 5 |
| adaptive_radial_edge | 192t — rh8-al320 (192 vCPU) | 33674606921 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 49 | 7 | 49p/7t | adaptive | 2m 42s | 343 | 36.57 | 7s | 11 |
| adaptive_radial_edge | 192t — rh8-al321 (192 vCPU) | 33007779343 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 55 | 6 | 16p/24t, 55p/6t | adaptive | 3m 11s | 330 | 15.06 | 17s | 9 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction coverage:** vCPU anchors `192`; readiness **low**; prediction checks **1 verified / 0 pending**.
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
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 1 | 1 | 384 | 384 | 1m 12s | 0s | 3.56 | 1.00× | -90.28% | 17.6 | 17.6 | 5.4% | 15.0 GiB |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 47 | 47 | 8 | 376 | 8s | 1s | 32.00 | 9.00× | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 48 | 48 | 8 | 384 | 8s | 1s | 32.00 | 9.00× | -12.50% | — | — | — | — |
| **192t — rh8-al320 (192 vCPU)** | 33674606921 | 49 | 49 | 7 | 343 | 7s | 1s | 36.57 | 10.29× | 0.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 50 | 50 | 7 | 350 | 8s | 1s | 32.00 | 9.00× | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 51 | 51 | 7 | 357 | 8s | 1s | 32.00 | 9.00× | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 52 | 52 | 7 | 364 | 8s | 1s | 32.00 | 9.00× | -12.50% | 295.9 | 295.9 | 23.4% | 10.8 GiB |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 53 | 53 | 7 | 371 | 8s | 1s | 32.00 | 9.00× | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 54 | 54 | 7 | 378 | 8s | 1s | 32.00 | 9.00× | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 55 | 55 | 6 | 330 | 8s | 1s | 32.00 | 9.00× | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 33674606921 | 192 | 192 | 2 | 384 | 13s | 4s | 19.69 | 5.54× | -46.15% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
