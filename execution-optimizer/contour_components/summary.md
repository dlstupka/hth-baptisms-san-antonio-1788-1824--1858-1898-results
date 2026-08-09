### Execution optimizer summary

Detector: `contour_components`  
Optimizer run: **31325710777** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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

Compatible completed optimizer runs are coalesced by detector, workload, and concrete runner profile. Repeated shapes retain all observations; the preferred shape is the fastest measured compatible shape.

| Detector | Runner | CPU | Physical | Logical | RAM | Preferred pipelines | Threads / pipeline | Preferred shape range (≤2%) | Allocated | Sets/s | Wall | Observations |
|---|---|---|---:|---:|---:|---:|---:|---|---:|---:|---:|---:|
| contour_components | e9k — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 8 | 8p/8t | 64 | 122.26 | 2m 41s | 1 |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-run-profile-plot"></a>
<details open>
<summary><strong>2. Detector Run Profile Plot</strong></summary>

Compatible completed measurements are plotted as detector pipelines versus parameter sets/second; thread count is annotated at each measured shape.

![Detector Run Profile Plot](heatmap.svg)

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-pipeline-thread-shape-optimization-data"></a>
<details>
<summary><strong>3. Detector Pipeline-Thread Shape Optimization Data</strong></summary>

Shapes completed in this execution are shown below.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e9k — rh8-al320 (192 vCPU) | 1 | 1 | 64 | 64 | 8m 13s | 39.93 | 1.00× | -67.34% | 7.8 | 13.3 | 8.3% | 12.2 GiB |
| e9k — rh8-al320 (192 vCPU) | 64 | 64 | 1 | 64 | 4m 43s | 69.55 | 1.74× | -43.11% | 1677.1 | 1997.1 | 92.3% | 20.5 GiB |
| **e9k — rh8-al320 (192 vCPU)** | 8 | 8 | 8 | 64 | 2m 41s | 122.26 | 3.06× | 0.00% | 1183.6 | 1541.6 | 93.4% | 13.1 GiB |
| e9k — rh8-al320 (192 vCPU) | 23 | 23 | 2 | 46 | 3m 55s | 83.76 | 2.10× | -31.49% | 1063.9 | 1195.0 | 94.0% | 15.1 GiB |
| e9k — rh8-al320 (192 vCPU) | 14 | 14 | 4 | 56 | 2m 59s | 109.97 | 2.75× | -10.06% | 1003.0 | 1036.5 | 93.4% | 13.9 GiB |
| e9k — rh8-al320 (192 vCPU) | 3 | 3 | 21 | 63 | 3m 35s | 91.55 | 2.29× | -25.12% | 253.2 | 592.1 | 30.8% | 12.5 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 1.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
