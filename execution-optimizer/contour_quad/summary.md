### Execution optimizer summary

Detector: `contour_quad`  
Optimizer run: **31276041742** — this table contains only shapes completed in this execution.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e9k — rh8-s32 (32 vCPU) | 1 | 1 | 64 | 64 | 7h 43m 45s | 38.20 | 1.00× | 55.9 | 66.6 | 90.0% | 38.4 GiB |
| e9k — rh8-s32 (32 vCPU) | 2 | 2 | 32 | 64 | 5h 44m 51s | 51.37 | 1.34× | 101.7 | 111.7 | 97.2% | 38.1 GiB |
| **e9k — rh8-s32 (32 vCPU)** | 3 | 3 | 21 | 63 | 5h 39m 5s | 52.24 | 1.37× | 111.3 | 123.6 | 97.4% | 38.3 GiB |
| e9k — rh8-s32 (32 vCPU) | 4 | 4 | 16 | 64 | 5h 41m 43s | 51.84 | 1.36× | 120.2 | 134.3 | 97.7% | 39.8 GiB |
| e9k — rh8-s32 (32 vCPU) | 5 | 5 | 12 | 60 | 5h 59m 23s | 49.29 | 1.29× | 125.6 | 146.2 | 97.5% | 39.0 GiB |
| e9k — rh8-s32 (32 vCPU) | 6 | 6 | 10 | 60 | 6h 18m 20s | 46.82 | 1.23× | 135.6 | 155.2 | 97.8% | 39.3 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 1.0% from the perceived maximum.
