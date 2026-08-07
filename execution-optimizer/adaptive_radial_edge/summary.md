### Execution optimizer summary

Detector: `adaptive_radial_edge`  
Compatible observations: **15** across **2** runner profiles.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated threads | Fastest wall | Median wall | Sets/s | Speedup vs 1 pipeline | Efficiency | Runs |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e7k — rh8-al97 (96 vCPU) | 1 | 1 | 192 | 192 | 44m 32s | 44m 32s | 2.46 | 1.00× | unknown | 1 |
| e7k — rh8-al97 (96 vCPU) | 2 | 2 | 96 | 192 | 20m 17s | 20m 17s | 5.39 | 2.20× | 98.6% | 1 |
| e7k — rh8-al97 (96 vCPU) | 4 | 4 | 48 | 192 | 10m 34s | 10m 34s | 10.35 | 4.21× | 96.7% | 1 |
| e7k — rh8-al97 (96 vCPU) | 8 | 8 | 24 | 192 | 5m 35s | 5m 35s | 19.59 | 7.98× | 94.1% | 1 |
| e7k — rh8-al97 (96 vCPU) | 16 | 16 | 12 | 192 | 2m 50s | 2m 50s | 38.60 | 15.72× | 93.8% | 1 |
| e7k — rh8-al97 (96 vCPU) | 32 | 32 | 6 | 192 | 1m 47s | 1m 47s | 61.33 | 24.97× | 89.5% | 1 |
| **e7k — rh8-al97 (96 vCPU)** | 64 | 64 | 3 | 192 | 1m 32s | 1m 32s | 71.33 | 29.04× | 84.9% | 1 |
| e7k — rh8-al97 (96 vCPU) | 96 | 96 | 2 | 192 | 1m 33s | 1m 33s | 70.56 | 28.73× | 79.5% | 1 |
| e7k — rh8-al97 (96 vCPU) | 128 | 128 | 1 | 128 | 1m 43s | 1m 43s | 63.71 | 25.94× | 73.0% | 1 |
| e7k — rh8-al97 (96 vCPU) | 192 | 192 | 1 | 192 | 1m 58s | 1m 58s | 55.61 | 22.64× | 43.5% | 1 |
| unknown — rh8-al97 (96 vCPU) | 1 | 1 | 192 | 192 | 45m 27s | 45m 27s | 2.41 | 1.00× | unknown | 1 |
| **unknown — rh8-al97 (96 vCPU)** | 64 | 64 | 1 | 64 | 1m 28s | 1m 58s | unknown | 31.02× | unknown | 4 |

**Bold runner rows mark that runner profile's fastest measured execution shape.**
