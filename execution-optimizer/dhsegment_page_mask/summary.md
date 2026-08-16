### Execution optimizer summary

Detector: `dhsegment_page_mask`  
Optimizer run: **31967269409** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| dhsegment_page_mask | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 192 | 2 | 162p/2t, 163p/2t, 164p/2t, 165p/2t, 174p/2t, 192p/2t, 207p/1t, 215p/1t, 219p/1t, 220p/1t, 221p/1t, 222p/1t, 223p/1t | adaptive | 2h 9m 17s | 384 | 11.90 | 14m | 2 |
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
| 192t — rh8-al321 (192 vCPU) | 192 | 192 | 2 | 384 | 14m 4s | 11.85 | — | 0.00% | 430.8 | 520.7 | 93.2% | 220.2 GiB |
| **192t — rh8-al321 (192 vCPU)** | 207 | 207 | 1 | 207 | 14m 4s | 11.85 | — | 0.00% | 411.9 | 495.3 | 92.7% | 230.0 GiB |
| 192t — rh8-al321 (192 vCPU) | 215 | 215 | 1 | 215 | 14m 6s | 11.82 | — | -0.24% | 392.9 | 452.9 | 92.4% | 238.6 GiB |
| 192t — rh8-al321 (192 vCPU) | 219 | 219 | 1 | 219 | 14m 8s | 11.79 | — | -0.47% | 396.4 | 573.1 | 92.1% | 242.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 220 | 220 | 1 | 220 | 14m 10s | 11.76 | — | -0.71% | 412.9 | 492.5 | 91.6% | 243.2 GiB |
| 192t — rh8-al321 (192 vCPU) | 221 | 221 | 1 | 221 | 14m 7s | 11.81 | — | -0.35% | 404.0 | 527.3 | 92.1% | 244.8 GiB |
| 192t — rh8-al321 (192 vCPU) | 222 | 222 | 1 | 222 | 14m 8s | 11.79 | — | -0.47% | 450.6 | 567.2 | 92.2% | 245.3 GiB |
| 192t — rh8-al321 (192 vCPU) | 223 | 223 | 1 | 223 | 14m 8s | 11.79 | — | -0.47% | 431.8 | 558.4 | 92.2% | 246.9 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
