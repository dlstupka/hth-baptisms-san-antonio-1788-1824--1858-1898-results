### Execution optimizer summary

Detector: `dhsegment_page_mask`  
Optimizer run: **33075352091** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| dhsegment_page_mask | 192t — rh8-al316 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 2897.3 GiB | 7 | 54 | 4p/96t, 5p/76t, 6p/64t, 7p/54t, 8p/48t, 9p/42t, 14p/27t | legacy | 3m 46s | 378 | 19.69 | 13s | 15 |

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
| 192t — rh8-al316 (192 vCPU) | 2 | 2 | 192 | 384 | 14s | 11s | 18.29 | — | -7.14% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 3 | 3 | 128 | 384 | 14s | 11s | 18.29 | — | -7.14% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 4 | 4 | 96 | 384 | 13s | 11s | 19.69 | — | 0.00% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 5 | 5 | 76 | 380 | 13s | 11s | 19.69 | — | 0.00% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 6 | 6 | 64 | 384 | 13s | 11s | 19.69 | — | 0.00% | 61.8 | 61.8 | 7.6% | 17.5 GiB |
| **192t — rh8-al316 (192 vCPU)** | 7 | 7 | 54 | 378 | 13s | 11s | 19.69 | — | 0.00% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 8 | 8 | 48 | 384 | 13s | 11s | 19.69 | — | 0.00% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 9 | 9 | 42 | 378 | 13s | 11s | 19.69 | — | 0.00% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 10 | 10 | 38 | 380 | 14s | 11s | 18.29 | — | -7.14% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 14 | 14 | 27 | 378 | 13s | 11s | 19.69 | — | 0.00% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 16 | 16 | 24 | 384 | 14s | 11s | 18.29 | — | -7.14% | 100.4 | 100.4 | 14.0% | 17.5 GiB |
| 192t — rh8-al316 (192 vCPU) | 19 | 19 | 20 | 380 | 14s | 11s | 18.29 | — | -7.14% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 27 | 27 | 14 | 378 | 15s | 11s | 17.07 | — | -13.33% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 52 | 52 | 7 | 364 | 17s | 12s | 15.06 | — | -23.53% | 109.6 | 109.6 | 23.6% | 17.5 GiB |
| 192t — rh8-al316 (192 vCPU) | 192 | 192 | 2 | 384 | 33s | 18s | 7.76 | — | -60.61% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
