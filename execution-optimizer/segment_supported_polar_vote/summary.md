### Execution optimizer summary

Detector: `segment_supported_polar_vote`  
Optimizer run: **31726390401** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| segment_supported_polar_vote | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 62 | 6 | 61p/6t, 62p/6t, 63p/6t, 64p/6t | adaptive | 2h 36m 48s | 372 | 140.59 | 2m 20s | 1 |

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

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 1h 53m 3s | 2.90 | 1.00× | -97.94% | 2.3 | 4.1 | 1.4% | 24.9 GiB |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 15m 54s | 20.63 | 7.11× | -85.32% | 51.1 | 335.8 | 11.3% | 25.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 23 | 23 | 16 | 368 | 7m 17s | 45.04 | 15.52× | -67.96% | 61.6 | 68.4 | 37.4% | 27.0 GiB |
| 192t — rh8-al318 (192 vCPU) | 38 | 38 | 10 | 380 | 3m 50s | 85.58 | 29.49× | -39.13% | 353.9 | 567.7 | 68.0% | 29.4 GiB |
| 192t — rh8-al318 (192 vCPU) | 49 | 49 | 7 | 343 | 2m 32s | 129.49 | 44.62× | -7.89% | 683.2 | 733.3 | 79.6% | 29.1 GiB |
| 192t — rh8-al318 (192 vCPU) | 56 | 56 | 6 | 336 | 2m 23s | 137.64 | 47.43× | -2.10% | 703.4 | 816.2 | 84.5% | 30.1 GiB |
| 192t — rh8-al318 (192 vCPU) | 60 | 60 | 6 | 360 | 2m 23s | 137.64 | 47.43× | -2.10% | 843.7 | 887.5 | 83.9% | 30.5 GiB |
| 192t — rh8-al318 (192 vCPU) | 61 | 61 | 6 | 366 | 2m 22s | 138.61 | 47.77× | -1.41% | 957.0 | 984.7 | 95.7% | 30.8 GiB |
| **192t — rh8-al318 (192 vCPU)** | 62 | 62 | 6 | 372 | 2m 20s | 140.59 | 48.45× | 0.00% | 755.7 | 885.2 | 74.0% | 31.9 GiB |
| 192t — rh8-al318 (192 vCPU) | 63 | 63 | 6 | 378 | 2m 21s | 139.60 | 48.11× | -0.71% | 895.5 | 925.7 | 80.4% | 31.7 GiB |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 2m 20s | 140.59 | 48.45× | 0.00% | 820.2 | 880.0 | 94.3% | 31.6 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
