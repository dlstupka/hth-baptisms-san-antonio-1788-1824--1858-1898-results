### Execution optimizer summary

Detector: `learned_page_mask`  
Optimizer run: **31698713628** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| learned_page_mask | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 2 | 192 | 2p/192t | adaptive | 16m 42s | 384 | 9.99 | 16m 41s | 1 |
| learned_page_mask | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 4 | 96 | 3p/128t, 4p/96t | adaptive | 1h 54m 3s | 384 | 10.29 | 16m 12s | 3 |
| learned_page_mask | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 3p/128t | adaptive | 1m 2s | 384 | 8.10 | 30s | 2 |

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
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 19m 44s | 8.45 | 1.00× | -17.91% | 379.5 | 406.5 | 62.7% | 76.3 GiB |
| 192t — rh8-al318 (192 vCPU) | 2 | 2 | 192 | 384 | 16m 41s | 9.99 | 1.18× | -2.90% | 442.6 | 481.9 | 78.4% | 71.0 GiB |
| 192t — rh8-al318 (192 vCPU) | 3 | 3 | 128 | 384 | 16m 17s | 10.24 | 1.21× | -0.51% | 481.5 | 527.3 | 83.4% | 70.4 GiB |
| **192t — rh8-al318 (192 vCPU)** | 4 | 4 | 96 | 384 | 16m 12s | 10.29 | 1.22× | 0.00% | 575.8 | 847.5 | 87.8% | 72.9 GiB |
| 192t — rh8-al318 (192 vCPU) | 5 | 5 | 76 | 380 | 16m 54s | 9.86 | 1.17× | -4.14% | 583.6 | 655.0 | 88.9% | 71.8 GiB |
| 192t — rh8-al318 (192 vCPU) | 16 | 16 | 24 | 384 | 28m 12s | 5.91 | 0.70× | -42.55% | 1202.7 | 1387.6 | 91.3% | 75.9 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
