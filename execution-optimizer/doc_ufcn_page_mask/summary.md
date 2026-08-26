### Execution optimizer summary

Detector: `doc_ufcn_page_mask`  
Optimizer run: **33014366532** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| doc_ufcn_page_mask | 192t — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 11 | 34 | 9p/42t, 10p/38t, 11p/34t | legacy | 2m 17s | 374 | 36.57 | 7s | 17 |

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
| 192t — rh8-al320 (192 vCPU) | 2 | 2 | 192 | 384 | 9s | 5s | 28.44 | — | -22.22% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 3 | 3 | 128 | 384 | 9s | 5s | 28.44 | — | -22.22% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 4 | 4 | 96 | 384 | 8s | 5s | 32.00 | — | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 5 | 5 | 76 | 380 | 8s | 5s | 32.00 | — | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 6 | 6 | 64 | 384 | 8s | 5s | 32.00 | — | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 7 | 7 | 54 | 378 | 8s | 5s | 32.00 | — | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 8 | 8 | 48 | 384 | 8s | 5s | 32.00 | — | -12.50% | 183.0 | 183.0 | 35.9% | 7.3 GiB |
| 192t — rh8-al320 (192 vCPU) | 9 | 9 | 42 | 378 | 7s | 5s | 36.57 | — | 0.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 10 | 10 | 38 | 380 | 7s | 5s | 36.57 | — | 0.00% | — | — | — | — |
| **192t — rh8-al320 (192 vCPU)** | 11 | 11 | 34 | 374 | 7s | 5s | 36.57 | — | 0.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 12 | 12 | 32 | 384 | 8s | 5s | 32.00 | — | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 19 | 19 | 20 | 380 | 8s | 5s | 32.00 | — | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 24 | 24 | 16 | 384 | 8s | 5s | 32.00 | — | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 25 | 25 | 15 | 375 | 8s | 5s | 32.00 | — | -12.50% | 92.1 | 92.1 | 35.3% | 7.6 GiB |
| 192t — rh8-al320 (192 vCPU) | 26 | 26 | 14 | 364 | 9s | 5s | 28.44 | — | -22.22% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 27 | 27 | 14 | 378 | 8s | 5s | 32.00 | — | -12.50% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 31 | 31 | 12 | 372 | 9s | 5s | 28.44 | — | -22.22% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
