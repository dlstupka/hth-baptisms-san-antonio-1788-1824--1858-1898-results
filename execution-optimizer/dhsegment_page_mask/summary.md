### Execution optimizer summary

Detector: `dhsegment_page_mask`  
Optimizer run: **31959818925** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| dhsegment_page_mask | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 192 | 2 | 162p/2t, 163p/2t, 164p/2t, 165p/2t, 174p/2t, 192p/2t | adaptive | 2h 9m 17s | 384 | 11.90 | 14m | 1 |
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
| 192t — rh8-al321 (192 vCPU) | 128 | 128 | 3 | 384 | 15m 32s | 10.73 | — | -9.87% | 166.2 | 188.9 | 73.1% | 152.8 GiB |
| 192t — rh8-al321 (192 vCPU) | 157 | 157 | 2 | 314 | 14m 21s | 11.61 | — | -2.44% | 284.6 | 358.1 | 86.4% | 181.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 161 | 161 | 2 | 322 | 14m 18s | 11.66 | — | -2.10% | 327.9 | 398.3 | 88.5% | 186.3 GiB |
| 192t — rh8-al321 (192 vCPU) | 162 | 162 | 2 | 324 | 14m 15s | 11.70 | — | -1.75% | 306.1 | 391.5 | 83.7% | 187.3 GiB |
| 192t — rh8-al321 (192 vCPU) | 163 | 163 | 2 | 326 | 14m 15s | 11.70 | — | -1.75% | 309.0 | 392.3 | 89.1% | 188.0 GiB |
| 192t — rh8-al321 (192 vCPU) | 164 | 164 | 2 | 328 | 14m 15s | 11.70 | — | -1.75% | 326.9 | 400.7 | 88.4% | 189.2 GiB |
| 192t — rh8-al321 (192 vCPU) | 165 | 165 | 2 | 330 | 14m 12s | 11.74 | — | -1.41% | 325.7 | 412.2 | 85.1% | 190.3 GiB |
| 192t — rh8-al321 (192 vCPU) | 174 | 174 | 2 | 348 | 14m 2s | 11.88 | — | -0.24% | 350.0 | 433.9 | 91.1% | 200.0 GiB |
| **192t — rh8-al321 (192 vCPU)** | 192 | 192 | 2 | 384 | 14m | 11.90 | — | 0.00% | 427.6 | 532.2 | 92.9% | 219.6 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
