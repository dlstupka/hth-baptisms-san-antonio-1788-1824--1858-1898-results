### Execution optimizer summary

Detector: `contour_components`  
Optimizer run: **31329274497** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| contour_components | e9k — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 8 | 7p/9t, 8p/8t, 9p/7t | 64 | 123.03 | 2m 40s | 2 |

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
| e9k — rh8-al320 (192 vCPU) | 4 | 4 | 16 | 64 | 3m 3s | 107.56 | — | -12.57% | 98.9 | 113.4 | 37.9% | 12.5 GiB |
| e9k — rh8-al320 (192 vCPU) | 16 | 16 | 4 | 64 | 2m 52s | 114.44 | — | -6.98% | 837.0 | 968.7 | 89.5% | 14.2 GiB |
| **e9k — rh8-al320 (192 vCPU)** | 8 | 8 | 8 | 64 | 2m 40s | 123.03 | — | 0.00% | 865.3 | 866.8 | 96.6% | 13.1 GiB |
| e9k — rh8-al320 (192 vCPU) | 7 | 7 | 9 | 63 | 2m 42s | 121.51 | — | -1.23% | 783.4 | 813.3 | 93.1% | 13.0 GiB |
| e9k — rh8-al320 (192 vCPU) | 9 | 9 | 7 | 63 | 2m 42s | 121.51 | — | -1.23% | 770.7 | 807.1 | 87.7% | 13.1 GiB |
| e9k — rh8-al320 (192 vCPU) | 6 | 6 | 10 | 60 | 2m 48s | 117.17 | — | -4.76% | 738.7 | 739.6 | 94.7% | 12.7 GiB |
| e9k — rh8-al320 (192 vCPU) | 10 | 10 | 6 | 60 | 2m 44s | 120.02 | — | -2.44% | 833.1 | 895.0 | 90.6% | 13.3 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 1.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
