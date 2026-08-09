### Execution optimizer summary

Detector: `radial_edge`  
Optimizer run: **31337056613** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| radial_edge | 192t — rh8-al323 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 26 | 14 | 23p/16t, 24p/16t, 25p/15t, 26p/14t, 27p/14t | adaptive | 7m 47s | 364 | 345.37 | 19s | 1 |

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
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 4m 20s | 25.24 | 1.00× | -92.69% | 7.8 | 12.5 | 3.6% | 23.4 GiB |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 45s | 145.82 | 5.78× | -57.78% | 292.9 | 292.9 | 27.0% | 23.3 GiB |
| 192t — rh8-al323 (192 vCPU) | 22 | 22 | 17 | 374 | 20s | 328.10 | 13.00× | -5.00% | 396.7 | 396.7 | 52.7% | 25.2 GiB |
| 192t — rh8-al323 (192 vCPU) | 23 | 23 | 16 | 368 | 19s | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 24 | 24 | 16 | 384 | 19s | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 25 | 25 | 15 | 375 | 19s | 345.37 | 13.68× | 0.00% | — | — | — | — |
| **192t — rh8-al323 (192 vCPU)** | 26 | 26 | 14 | 364 | 19s | 345.37 | 13.68× | 0.00% | 740.9 | 740.9 | 71.2% | 25.4 GiB |
| 192t — rh8-al323 (192 vCPU) | 27 | 27 | 14 | 378 | 19s | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 28 | 28 | 13 | 364 | 20s | 328.10 | 13.00× | -5.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 64 | 64 | 6 | 384 | 23s | 285.30 | 11.30× | -17.39% | — | — | — | — |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
