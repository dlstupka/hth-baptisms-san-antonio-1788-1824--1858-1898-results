### Execution optimizer summary

Detector: `msre_bfq_spbv_pbg`  
Optimizer run: **35890388544** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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

Compatible completed optimizer runs are coalesced by stable detector evidence identity and concrete runner profile; search scope is retained only as informational provenance. Repeated shapes retain all observations; the preferred shape is selected canonically by throughput, then newest compatible optimizer run, then lower resource use within a run.

| Detector | Runner | Optimizer run | CPU | Physical | Logical | RAM | Preferred pipelines | Threads / pipeline | Preferred shape range (≤2%) | Search method | Optimization time | Allocated | Sets/s | Shape time | Observations |
|---|---|---|---|---:|---:|---:|---:|---:|---|---|---:|---:|---:|---:|---:|
| msre_bfq_spbv_pbg | 192t — rh8-al321 (192 vCPU) | 33326002993 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 37 | 10 | 37p/10t | adaptive | 13m 18s | 370 | 8.83 | 29s | 11 |
| msre_bfq_spbv_pbg | 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 43 | 8 | 33p/11t, 34p/11t, 36p/10t, 37p/10t, 38p/10t, 39p/9t, 40p/9t, 41p/9t, 43p/8t, 44p/8t, 45p/8t, 46p/8t | adaptive | 1h 8m 44s | 344 | 2.15 | 1m 59s | 20 |

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

| Runner | Optimizer run | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 1 | 1 | 384 | 384 | 29m 1s | 1s | 0.15 | 1.00× | -93.16% | 50.8 | 426.4 | 9.1% | 37.4 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 31 | 31 | 12 | 372 | 2m 2s | 1s | 2.10 | 14.27× | -2.46% | 1252.8 | 1358.8 | 82.2% | 49.8 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 32 | 32 | 12 | 384 | 2m 4s | 1s | 2.06 | 14.04× | -4.03% | 1443.3 | 1546.8 | 84.7% | 48.0 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 33 | 33 | 11 | 363 | 2m | 1s | 2.13 | 14.51× | -0.83% | 1370.8 | 1452.9 | 84.0% | 48.6 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 34 | 34 | 11 | 374 | 2m | 1s | 2.13 | 14.51× | -0.83% | 1326.1 | 1397.5 | 84.8% | 50.7 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 35 | 35 | 10 | 350 | 2m 4s | 1s | 2.06 | 14.04× | -4.03% | 1337.9 | 1424.0 | 85.3% | 52.0 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 36 | 36 | 10 | 360 | 2m 1s | 1s | 2.12 | 14.39× | -1.65% | 2410.2 | 3427.9 | 84.8% | 53.7 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 37 | 37 | 10 | 370 | 1m 59s | 1s | 2.15 | 14.63× | 0.00% | 1017.9 | 1156.1 | 84.4% | 53.4 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 38 | 38 | 10 | 380 | 2m 1s | 1s | 2.12 | 14.39× | -1.65% | 1406.0 | 1484.1 | 85.8% | 53.5 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 39 | 39 | 9 | 351 | 2m | 1s | 2.13 | 14.51× | -0.83% | 1471.1 | 1478.9 | 84.9% | 53.1 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 40 | 40 | 9 | 360 | 2m 1s | 1s | 2.12 | 14.39× | -1.65% | 1581.6 | 1600.7 | 85.0% | 53.0 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 41 | 41 | 9 | 369 | 2m | 1s | 2.13 | 14.51× | -0.83% | 1501.8 | 1627.4 | 85.2% | 51.8 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 42 | 42 | 9 | 378 | 2m 3s | 1s | 2.08 | 14.15× | -3.25% | 1518.0 | 1619.8 | 83.1% | 50.7 GiB |
| **192vcpu — rh8-al320 (192 vCPU)** | 35890388544 | 43 | 43 | 8 | 344 | 1m 59s | 1s | 2.15 | 14.63× | 0.00% | 1499.3 | 1680.8 | 84.2% | 54.9 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 44 | 44 | 8 | 352 | 2m | 1s | 2.13 | 14.51× | -0.83% | 1666.2 | 1769.0 | 85.2% | 55.1 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 45 | 45 | 8 | 360 | 2m | 1s | 2.13 | 14.51× | -0.83% | 1535.8 | 1761.1 | 84.8% | 56.0 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 46 | 46 | 8 | 368 | 2m 1s | 1s | 2.12 | 14.39× | -1.65% | 1726.6 | 1870.2 | 85.1% | 57.1 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 47 | 47 | 8 | 376 | 2m 3s | 1s | 2.08 | 14.15× | -3.25% | 1824.7 | 1932.4 | 84.8% | 57.3 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 48 | 48 | 8 | 384 | 2m 6s | 1s | 2.03 | 13.82× | -5.56% | 1884.2 | 1900.8 | 83.7% | 58.3 GiB |
| 192vcpu — rh8-al320 (192 vCPU) | 35890388544 | 192 | 192 | 2 | 384 | 2m 54s | 4s | 1.47 | 10.01× | -31.61% | 4874.8 | 5360.1 | 87.7% | 122.7 GiB |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
