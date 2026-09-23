### Execution optimizer summary

Detector: `multi_scale_radial_edge`  
Optimizer run: **35878561358** — execution data below contains only shapes completed in this execution; the preferred configuration may use all compatible completed optimizer evidence.

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
| multi_scale_radial_edge | 192t — rh8-al316 (192 vCPU) | 33207798869 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 2897.3 GiB | 30 | 12 | 10p/38t, 11p/34t, 12p/32t, 13p/29t, 14p/27t, 15p/25t, 16p/24t, 17p/22t, 18p/21t, 19p/20t, 20p/19t, 21p/18t, 22p/17t, 23p/16t, 24p/16t, 25p/15t, 26p/14t, 27p/14t, 28p/13t, 29p/13t, 30p/12t, 31p/12t, 32p/12t, 33p/11t | adaptive | 3m 11s | 360 | 42.67 | 6s | 28 |
| multi_scale_radial_edge | 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 35 | 10 | 35p/10t | adaptive | 6m 51s | 350 | 11.13 | 23s | 13 |

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
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 1 | 1 | 384 | 384 | 1m 38s | 1s | 2.61 | 1.00× | -76.53% | 130.7 | 187.1 | 18.3% | 26.9 GiB |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 27 | 27 | 14 | 378 | 25s | 1s | 10.24 | 3.92× | -8.00% | — | — | — | — |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 28 | 28 | 13 | 364 | 25s | 1s | 10.24 | 3.92× | -8.00% | — | — | — | — |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 29 | 29 | 13 | 377 | 24s | 1s | 10.67 | 4.08× | -4.17% | 762.3 | 762.3 | 62.7% | 35.7 GiB |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 30 | 30 | 12 | 360 | 24s | 1s | 10.67 | 4.08× | -4.17% | — | — | — | — |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 31 | 31 | 12 | 372 | 24s | 1s | 10.67 | 4.08× | -4.17% | 764.7 | 764.7 | 63.5% | 11.1 GiB |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 32 | 32 | 12 | 384 | 25s | 1s | 10.24 | 3.92× | -8.00% | — | — | — | — |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 33 | 33 | 11 | 363 | 24s | 1s | 10.67 | 4.08× | -4.17% | 983.5 | 983.5 | 68.1% | 37.3 GiB |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 34 | 34 | 11 | 374 | 25s | 1s | 10.24 | 3.92× | -8.00% | — | — | — | — |
| **192vcpu — rh8-al322 (192 vCPU)** | 35878561358 | 35 | 35 | 10 | 350 | 23s | 1s | 11.13 | 4.26× | 0.00% | 992.9 | 992.9 | 72.5% | 31.6 GiB |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 36 | 36 | 10 | 360 | 24s | 1s | 10.67 | 4.08× | -4.17% | — | — | — | — |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 37 | 37 | 10 | 370 | 25s | 1s | 10.24 | 3.92× | -8.00% | — | — | — | — |
| 192vcpu — rh8-al322 (192 vCPU) | 35878561358 | 192 | 192 | 2 | 384 | 31s | 4s | 8.26 | 3.16× | -25.81% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** perceived throughput peak/plateau bracketed by completed shapes more than 2.0% below the peak on both available sides.

</details>

[↑ Back to Navigation](#table-of-contents)
