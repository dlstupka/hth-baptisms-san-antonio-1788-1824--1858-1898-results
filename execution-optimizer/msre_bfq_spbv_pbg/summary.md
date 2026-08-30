### Execution optimizer summary

Detector: `msre_bfq_spbv_pbg`  
Optimizer run: **33326002993** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| msre_bfq_spbv_pbg | 192t — rh8-al321 (192 vCPU) | 33326002993 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 37 | 10 | 37p/10t | legacy | 13m 15s | 370 | 8.83 | 29s | 11 |

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
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 1 | 1 | 384 | 384 | 7m 55s | 0s | 0.54 | 1.00× | -93.89% | 102.8 | 433.4 | 12.2% | 23.8 GiB |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 31 | 31 | 12 | 372 | 31s | 1s | 8.26 | 15.32× | -6.45% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 32 | 32 | 12 | 384 | 31s | 1s | 8.26 | 15.32× | -6.45% | 1753.8 | 1753.8 | 76.3% | 31.6 GiB |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 33 | 33 | 11 | 363 | 30s | 1s | 8.53 | 15.83× | -3.33% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 34 | 34 | 11 | 374 | 30s | 1s | 8.53 | 15.83× | -3.33% | 2258.1 | 2258.1 | 78.1% | 32.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 35 | 35 | 10 | 350 | 30s | 1s | 8.53 | 15.83× | -3.33% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 36 | 36 | 10 | 360 | 30s | 1s | 8.53 | 15.83× | -3.33% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 33326002993 | 37 | 37 | 10 | 370 | 29s | 1s | 8.83 | 16.38× | 0.00% | 1377.8 | 1377.8 | 76.7% | 32.9 GiB |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 38 | 38 | 10 | 380 | 30s | 1s | 8.53 | 15.83× | -3.33% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 39 | 39 | 9 | 351 | 31s | 1s | 8.26 | 15.32× | -6.45% | 1291.6 | 1291.6 | 79.7% | 33.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 33326002993 | 192 | 192 | 2 | 384 | 48s | 3s | 5.33 | 9.90× | -39.58% | 3328.4 | 3328.4 | 43.8% | 71.7 GiB |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
