### Execution optimizer summary

Detector: `amsre_doc_ufcn_fusion`  
Optimizer run: **32783190237** — resumed from optimizer run **32572206642**; execution data below contains shapes completed in this execution or reused from that compatible local checkpoint; the preferred configuration may use all compatible completed optimizer evidence.

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
| amsre_doc_ufcn_fusion | 192t — rh8-al308 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 4 | 96 | 3p/128t, 4p/96t | legacy | 10m 35s | 384 | 2.62 | 1m 20s | 1 |
| amsre_doc_ufcn_fusion | 192t — rh8-al308 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 7 | 54 | 7p/54t | legacy | 10m 35s | 378 | 0.37 | 1m 19s | 1 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction coverage:** vCPU anchors `192`; readiness **low**; prediction checks **0 verified / 0 pending**.
**Desired / missing optimization data:** missing: a second vCPU size to establish shape scaling.

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-run-profile-plot"></a>
<details open>
<summary><strong>2. Detector Run Profile Plot</strong></summary>

Compatible completed measurements are plotted as detector pipelines versus parameter sets/second; thread count is annotated at each measured shape.
**Search method:** `exhaustive`

![Detector Run Profile Plot](heatmap.svg)

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-pipeline-thread-shape-optimization-data"></a>
<details>
<summary><strong>3. Detector Pipeline-Thread Shape Optimization Data</strong></summary>

Shapes completed in this execution or reused from its compatible checkpoint are shown below.

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al308 (192 vCPU) | 1 | 1 | 384 | 384 | 2m 10s | 0s | 1.62 | 1.00× | -38.46% | 17.7 | 33.7 | 19.5% | 36.0 GiB |
| 192t — rh8-al308 (192 vCPU) | 2 | 2 | 192 | 384 | 1m 31s | 0s | 2.31 | 1.43× | -12.09% | 77.2 | 77.2 | 44.9% | 36.2 GiB |
| 192t — rh8-al308 (192 vCPU) | 3 | 3 | 128 | 384 | 1m 21s | 0s | 2.59 | 1.60× | -1.23% | 176.2 | 182.5 | 51.0% | 37.5 GiB |
| **192t — rh8-al308 (192 vCPU)** | 4 | 4 | 96 | 384 | 1m 20s | 0s | 2.62 | 1.62× | 0.00% | 267.5 | 267.5 | 74.5% | 37.7 GiB |
| 192t — rh8-al308 (192 vCPU) | 5 | 5 | 76 | 380 | 1m 24s | 0s | 2.50 | 1.55× | -4.76% | 333.1 | 333.1 | 75.3% | 26.4 GiB |
| 192t — rh8-al308 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 30s | 0s | 2.33 | 1.44× | -11.11% | 324.4 | 354.9 | 84.3% | 38.8 GiB |
| **192t — rh8-al308 (192 vCPU)** | 7 | 7 | 54 | 378 | 1m 19s | 0s | 0.37 | — | -86.02% | 289.6 | 289.6 | 84.9% | 29.6 GiB |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 2.0% from the perceived maximum.

</details>

[↑ Back to Navigation](#table-of-contents)
