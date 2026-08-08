### Execution optimizer summary

Detector: `grabcut`  
Optimizer run: **31260612862** — this table contains only shapes completed in this execution.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **e7k — rh8-al97 (96 vCPU)** | 2 | 2 | 96 | 192 | 1h 53m 40s | 1.92 | — | 281.1 | 317.0 | 98.3% | 53.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 4 | 4 | 48 | 192 | 1h 57m 14s | 1.87 | — | 321.1 | 377.9 | 99.3% | 53.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 8 | 8 | 24 | 192 | 1h 57m 47s | 1.86 | — | 328.4 | 420.9 | 99.2% | 54.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 16 | 16 | 12 | 192 | 1h 58m 17s | 1.85 | — | 343.3 | 435.7 | 99.3% | 54.9 GiB |

**Early stop:** throughput plateau detected after 3 consecutive completed shapes improved by less than 1.0% from the perceived maximum.
