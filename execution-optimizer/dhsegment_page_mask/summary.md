### Execution optimizer summary

Detector: `dhsegment_page_mask`  
Optimizer run: **31950549151** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| dhsegment_page_mask | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 128 | 3 | 124p/3t, 125p/3t, 126p/3t, 127p/3t, 128p/3t | adaptive | 2h 47m 34s | 384 | 10.82 | 15m 24s | 1 |
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
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 22m 54s | 7.28 | — | -32.75% | 66.6 | 79.5 | 34.8% | 86.0 GiB |
| 192t — rh8-al318 (192 vCPU) | 91 | 91 | 4 | 364 | 18m 20s | 9.09 | — | -16.00% | 103.9 | 147.9 | 50.1% | 113.7 GiB |
| 192t — rh8-al318 (192 vCPU) | 108 | 108 | 3 | 324 | 16m 42s | 9.98 | — | -7.78% | 134.8 | 170.0 | 58.2% | 131.0 GiB |
| 192t — rh8-al318 (192 vCPU) | 118 | 118 | 3 | 354 | 15m 59s | 10.43 | — | -3.65% | 164.6 | 204.4 | 64.7% | 141.9 GiB |
| 192t — rh8-al318 (192 vCPU) | 123 | 123 | 3 | 369 | 15m 44s | 10.59 | — | -2.12% | 157.2 | 208.4 | 66.3% | 147.3 GiB |
| 192t — rh8-al318 (192 vCPU) | 124 | 124 | 3 | 372 | 15m 39s | 10.65 | — | -1.60% | 160.3 | 201.9 | 67.2% | 148.8 GiB |
| 192t — rh8-al318 (192 vCPU) | 125 | 125 | 3 | 375 | 15m 41s | 10.63 | — | -1.81% | 173.5 | 211.0 | 71.4% | 149.5 GiB |
| 192t — rh8-al318 (192 vCPU) | 126 | 126 | 3 | 378 | 15m 33s | 10.72 | — | -0.96% | 166.8 | 227.8 | 67.7% | 150.6 GiB |
| 192t — rh8-al318 (192 vCPU) | 127 | 127 | 3 | 381 | 15m 29s | 10.76 | — | -0.54% | 179.8 | 225.0 | 71.8% | 151.9 GiB |
| **192t — rh8-al318 (192 vCPU)** | 128 | 128 | 3 | 384 | 15m 24s | 10.82 | — | 0.00% | 171.0 | 217.7 | 69.0% | 153.1 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
