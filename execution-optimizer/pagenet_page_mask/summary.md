### Execution optimizer summary

Detector: `pagenet_page_mask`  
Optimizer run: **32484937174** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| pagenet_page_mask | 192t — rh8-al307 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 7 | 54 | 5p/76t, 6p/64t, 7p/54t, 8p/48t | legacy | 5m 3s | 378 | 641.03 | 39s | 1 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction coverage:** vCPU anchors `192`; readiness **low**; prediction checks **0 verified / 0 pending**.
**Desired / missing optimization data:** missing: a second vCPU size to establish shape scaling.

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-run-profile-plot"></a>
<details open>
<summary><strong>2. Detector Run Profile Plot</strong></summary>

Compatible completed measurements are plotted as detector pipelines versus parameter sets/second; thread count is annotated at each measured shape.
**Search method:** `exhaustive`

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
| 192t — rh8-al307 (192 vCPU) | 2 | 2 | 192 | 384 | 58s | 2s | 431.03 | — | -32.76% | 11.7 | 11.7 | 6.0% | 24.1 GiB |
| 192t — rh8-al307 (192 vCPU) | 3 | 3 | 128 | 384 | 47s | 2s | 531.91 | — | -17.02% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 4 | 4 | 96 | 384 | 42s | 2s | 595.24 | — | -7.14% | 29.6 | 29.6 | 9.4% | 24.9 GiB |
| 192t — rh8-al307 (192 vCPU) | 5 | 5 | 76 | 380 | 39s | 2s | 641.03 | — | 0.00% | 18.3 | 18.3 | 9.6% | 24.1 GiB |
| 192t — rh8-al307 (192 vCPU) | 6 | 6 | 64 | 384 | 39s | 2s | 641.03 | — | 0.00% | — | — | — | — |
| **192t — rh8-al307 (192 vCPU)** | 7 | 7 | 54 | 378 | 39s | 2s | 641.03 | — | 0.00% | 49.8 | 49.8 | 9.3% | 25.2 GiB |
| 192t — rh8-al307 (192 vCPU) | 8 | 8 | 48 | 384 | 39s | 2s | 641.03 | — | 0.00% | 25.9 | 25.9 | 10.9% | 24.3 GiB |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
