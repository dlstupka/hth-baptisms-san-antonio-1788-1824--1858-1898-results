### Execution optimizer summary

Detector: `adaptive_multi_scale_radial_edge`  
Optimizer run: **31827149276** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| adaptive_multi_scale_radial_edge | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 25 | 15 | 23p/16t, 24p/16t, 25p/15t, 26p/14t, 27p/14t, 28p/13t, 29p/13t, 30p/12t, 31p/12t, 32p/12t | adaptive | 1h 44m 25s | 375 | 26.04 | 6m 24s | 1 |

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
| 192t — rh8-al319 (192 vCPU) | 4 | 4 | 96 | 384 | 18m 10s | 9.18 | — | -64.77% | 380.8 | 584.4 | 74.5% | 34.4 GiB |
| 192t — rh8-al319 (192 vCPU) | 11 | 11 | 34 | 374 | 8m 22s | 19.92 | — | -23.51% | 1176.9 | 1282.4 | 96.2% | 36.1 GiB |
| 192t — rh8-al319 (192 vCPU) | 19 | 19 | 20 | 380 | 6m 46s | 24.63 | — | -5.42% | 1373.0 | 1556.6 | 97.6% | 38.5 GiB |
| 192t — rh8-al319 (192 vCPU) | 22 | 22 | 17 | 374 | 6m 34s | 25.38 | — | -2.54% | 1454.9 | 1682.9 | 96.8% | 38.7 GiB |
| 192t — rh8-al319 (192 vCPU) | 23 | 23 | 16 | 368 | 6m 27s | 25.84 | — | -0.78% | 1632.5 | 1765.9 | 98.1% | 38.7 GiB |
| 192t — rh8-al319 (192 vCPU) | 24 | 24 | 16 | 384 | 6m 26s | 25.91 | — | -0.52% | 1616.7 | 1788.8 | 98.4% | 39.8 GiB |
| **192t — rh8-al319 (192 vCPU)** | 25 | 25 | 15 | 375 | 6m 24s | 26.04 | — | 0.00% | 1680.7 | 2038.6 | 96.4% | 39.6 GiB |
| 192t — rh8-al319 (192 vCPU) | 26 | 26 | 14 | 364 | 6m 26s | 25.91 | — | -0.52% | 1704.4 | 1885.0 | 96.2% | 39.2 GiB |
| 192t — rh8-al319 (192 vCPU) | 27 | 27 | 14 | 378 | 6m 28s | 25.78 | — | -1.03% | 1861.0 | 2006.0 | 97.4% | 40.4 GiB |
| 192t — rh8-al319 (192 vCPU) | 28 | 28 | 13 | 364 | 6m 25s | 25.98 | — | -0.26% | 1787.3 | 2000.0 | 97.4% | 39.6 GiB |
| 192t — rh8-al319 (192 vCPU) | 29 | 29 | 13 | 377 | 6m 29s | 25.71 | — | -1.29% | 1856.2 | 2094.0 | 96.3% | 40.9 GiB |
| 192t — rh8-al319 (192 vCPU) | 30 | 30 | 12 | 360 | 6m 26s | 25.91 | — | -0.52% | 1980.2 | 2214.9 | 97.9% | 40.1 GiB |
| 192t — rh8-al319 (192 vCPU) | 31 | 31 | 12 | 372 | 6m 26s | 25.91 | — | -0.52% | 1995.8 | 2200.2 | 97.2% | 41.3 GiB |
| 192t — rh8-al319 (192 vCPU) | 32 | 32 | 12 | 384 | 6m 25s | 25.98 | — | -0.26% | 1929.5 | 2167.1 | 96.8% | 41.8 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
