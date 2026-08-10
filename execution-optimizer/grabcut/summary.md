### Execution optimizer summary

Detector: `grabcut`  
Optimizer run: **31337889215** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| grabcut | 192t — rh8-al325 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 3p/128t | adaptive | 4h 7m 20s | 384 | 4.77 | 45m 52s | 1 |
| grabcut | e7k — rh8-al97 (96 vCPU) | AMD EPYC 74F3 24-Core Processor | 48 | 96 | 2003.9 GiB | 1 | 192 | 1p/192t, 2p/96t | exhaustive | 1h 54m | 192 | 1.92 | 1h 54m | 1 |

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
| **192t — rh8-al325 (192 vCPU)** | 1 | 1 | 384 | 384 | 45m 52s | 4.77 | 1.00× | 0.00% | 465.3 | 518.7 | 91.4% | 69.7 GiB |
| 192t — rh8-al325 (192 vCPU) | 3 | 3 | 128 | 384 | 46m 32s | 4.70 | 0.99× | -1.43% | 676.4 | 745.0 | 95.5% | 88.3 GiB |
| 192t — rh8-al325 (192 vCPU) | 4 | 4 | 96 | 384 | 48m 18s | 4.53 | 0.95× | -5.04% | 779.8 | 874.1 | 96.8% | 82.2 GiB |
| 192t — rh8-al325 (192 vCPU) | 5 | 5 | 76 | 380 | 50m 34s | 4.32 | 0.91× | -9.29% | 830.7 | 939.7 | 97.7% | 88.7 GiB |
| 192t — rh8-al325 (192 vCPU) | 8 | 8 | 48 | 384 | 56m 4s | 3.90 | 0.82× | -18.19% | 976.4 | 1132.0 | 98.6% | 86.4 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
