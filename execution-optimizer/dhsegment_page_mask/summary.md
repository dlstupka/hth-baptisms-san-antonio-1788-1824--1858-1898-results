### Execution optimizer summary

Detector: `dhsegment_page_mask`  
Optimizer run: **31929221592** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| dhsegment_page_mask | 192t — rh8-al308 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 32 | 12 | 32p/12t | adaptive | 1d 3h 48m 24s | 384 | 4.24 | 39m 18s | 1 |
| dhsegment_page_mask | e9k — rh8-al316 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 2897.3 GiB | 64 | 6 | 63p/6t, 64p/6t | adaptive | 3h 36m 33s | 384 | 7.13 | 23m 23s | 1 |

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

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e9k — rh8-al316 (192 vCPU) | 32 | 32 | 12 | 384 | 39m 13s | 4.25 | — | -40.37% | 33.7 | 42.8 | 17.4% | 56.3 GiB |
| e9k — rh8-al316 (192 vCPU) | 45 | 45 | 8 | 360 | 30m 54s | 5.39 | — | -24.33% | 48.0 | 67.0 | 23.8% | 69.7 GiB |
| e9k — rh8-al316 (192 vCPU) | 54 | 54 | 7 | 378 | 26m 12s | 6.36 | — | -10.75% | 57.1 | 64.6 | 29.1% | 79.6 GiB |
| e9k — rh8-al316 (192 vCPU) | 59 | 59 | 6 | 354 | 24m 52s | 6.70 | — | -5.97% | 61.1 | 65.4 | 31.8% | 84.5 GiB |
| e9k — rh8-al316 (192 vCPU) | 61 | 61 | 6 | 366 | 24m 21s | 6.84 | — | -3.97% | 66.4 | 77.9 | 32.8% | 87.0 GiB |
| e9k — rh8-al316 (192 vCPU) | 62 | 62 | 6 | 372 | 23m 52s | 6.98 | — | -2.03% | 66.0 | 82.2 | 33.2% | 87.9 GiB |
| e9k — rh8-al316 (192 vCPU) | 63 | 63 | 6 | 378 | 23m 40s | 7.04 | — | -1.20% | 69.7 | 102.5 | 34.0% | 89.3 GiB |
| **e9k — rh8-al316 (192 vCPU)** | 64 | 64 | 6 | 384 | 23m 23s | 7.13 | — | 0.00% | 69.1 | 104.3 | 34.8% | 90.3 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
