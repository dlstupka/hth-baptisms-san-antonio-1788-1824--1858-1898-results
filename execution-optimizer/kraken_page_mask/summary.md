### Execution optimizer summary

Detector: `kraken_page_mask`  
Optimizer run: **31892561260** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| kraken_page_mask | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 17 | 22 | 15p/25t, 16p/24t, 17p/22t, 18p/21t, 19p/20t, 20p/19t, 21p/18t, 22p/17t, 23p/16t | adaptive | 18h 52m 35s | 374 | 2.75 | 1h 40s | 1 |

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
| 192t — rh8-al318 (192 vCPU) | 4 | 4 | 96 | 384 | 2h 2m 57s | 1.36 | — | -50.66% | 37.6 | 347.7 | 16.0% | 41.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 10 | 10 | 38 | 380 | 1h 8m 46s | 2.42 | — | -11.78% | 136.6 | 508.7 | 38.5% | 57.6 GiB |
| 192t — rh8-al318 (192 vCPU) | 11 | 11 | 34 | 374 | 1h 5m 48s | 2.53 | — | -7.80% | 162.5 | 532.6 | 41.8% | 62.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 12 | 12 | 32 | 384 | 1h 5m 16s | 2.55 | — | -7.05% | 172.1 | 492.6 | 44.6% | 61.0 GiB |
| 192t — rh8-al318 (192 vCPU) | 13 | 13 | 29 | 377 | 1h 3m 25s | 2.63 | — | -4.34% | 201.8 | 554.8 | 48.1% | 67.7 GiB |
| 192t — rh8-al318 (192 vCPU) | 14 | 14 | 27 | 378 | 1h 2m 6s | 2.68 | — | -2.31% | 218.4 | 570.8 | 50.8% | 70.9 GiB |
| 192t — rh8-al318 (192 vCPU) | 15 | 15 | 25 | 375 | 1h 1m 14s | 2.72 | — | -0.93% | 243.4 | 568.5 | 53.9% | 69.7 GiB |
| 192t — rh8-al318 (192 vCPU) | 16 | 16 | 24 | 384 | 1h 1m 43s | 2.70 | — | -1.70% | 247.2 | 551.3 | 56.1% | 72.0 GiB |
| **192t — rh8-al318 (192 vCPU)** | 17 | 17 | 22 | 374 | 1h 40s | 2.75 | — | 0.00% | 285.3 | 604.7 | 58.9% | 78.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 18 | 18 | 21 | 378 | 1h 1m 1s | 2.73 | — | -0.57% | 295.0 | 627.6 | 60.7% | 73.9 GiB |
| 192t — rh8-al318 (192 vCPU) | 19 | 19 | 20 | 380 | 1h 1m 5s | 2.73 | — | -0.68% | 312.3 | 639.4 | 62.9% | 80.0 GiB |
| 192t — rh8-al318 (192 vCPU) | 20 | 20 | 19 | 380 | 1h 1m 19s | 2.72 | — | -1.06% | 334.7 | 656.9 | 65.0% | 84.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 21 | 21 | 18 | 378 | 1h 1m 7s | 2.73 | — | -0.74% | 355.9 | 672.8 | 66.7% | 84.6 GiB |
| 192t — rh8-al318 (192 vCPU) | 22 | 22 | 17 | 374 | 1h 1m 26s | 2.71 | — | -1.25% | 393.9 | 712.7 | 69.2% | 89.1 GiB |
| 192t — rh8-al318 (192 vCPU) | 23 | 23 | 16 | 368 | 1h 1m 33s | 2.71 | — | -1.44% | 418.2 | 726.5 | 70.3% | 89.3 GiB |
| 192t — rh8-al318 (192 vCPU) | 24 | 24 | 16 | 384 | 1h 3m 21s | 2.63 | — | -4.24% | 429.3 | 775.3 | 71.9% | 92.4 GiB |
| 192t — rh8-al318 (192 vCPU) | 32 | 32 | 12 | 384 | 1h 9m 35s | 2.40 | — | -12.81% | 607.4 | 868.4 | 80.3% | 110.3 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
