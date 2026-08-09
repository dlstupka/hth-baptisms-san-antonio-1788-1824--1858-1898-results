### Execution optimizer summary

Detector: `contour_components`  
Optimizer run: **31339803325** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| contour_components | 192t — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 19 | 20 | 18p/21t, 19p/20t, 20p/19t, 21p/18t, 32p/12t | adaptive | 24m 29s | 380 | 223.68 | 1m 28s | 1 |
| contour_components | e9k — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 8 | 7p/9t, 8p/8t, 9p/7t | adaptive | 19m 31s | 64 | 123.03 | 2m 40s | 2 |

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
| 192t — rh8-al320 (192 vCPU) | 1 | 1 | 384 | 384 | 9m 45s | 33.65 | 1.00× | -84.96% | 10.5 | 18.6 | 7.1% | 17.4 GiB |
| 192t — rh8-al320 (192 vCPU) | 6 | 6 | 64 | 384 | 2m 46s | 118.58 | 3.52× | -46.99% | 1146.1 | 1280.0 | 88.9% | 17.8 GiB |
| 192t — rh8-al320 (192 vCPU) | 14 | 14 | 27 | 378 | 1m 31s | 216.31 | 6.43× | -3.30% | 1414.4 | 1414.4 | 93.9% | 18.9 GiB |
| 192t — rh8-al320 (192 vCPU) | 17 | 17 | 22 | 374 | 1m 31s | 216.31 | 6.43× | -3.30% | 1548.7 | 1548.7 | 83.1% | 19.0 GiB |
| 192t — rh8-al320 (192 vCPU) | 18 | 18 | 21 | 378 | 1m 29s | 221.17 | 6.57× | -1.12% | 1496.1 | 1613.3 | 91.4% | 19.6 GiB |
| **192t — rh8-al320 (192 vCPU)** | 19 | 19 | 20 | 380 | 1m 28s | 223.68 | 6.65× | 0.00% | 1471.0 | 1471.0 | 83.0% | 19.3 GiB |
| 192t — rh8-al320 (192 vCPU) | 20 | 20 | 19 | 380 | 1m 28s | 223.68 | 6.65× | 0.00% | 1570.0 | 1570.0 | 94.4% | 19.9 GiB |
| 192t — rh8-al320 (192 vCPU) | 21 | 21 | 18 | 378 | 1m 29s | 221.17 | 6.57× | -1.12% | 1394.6 | 1400.2 | 85.8% | 19.5 GiB |
| 192t — rh8-al320 (192 vCPU) | 22 | 22 | 17 | 374 | 1m 30s | 218.71 | 6.50× | -2.22% | 1500.4 | 1607.5 | 91.4% | 20.2 GiB |
| 192t — rh8-al320 (192 vCPU) | 32 | 32 | 12 | 384 | 1m 29s | 221.17 | 6.57× | -1.12% | 1055.8 | 1549.1 | 60.3% | 21.9 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
