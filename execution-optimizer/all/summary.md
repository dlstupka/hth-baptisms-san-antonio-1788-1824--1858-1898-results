### Execution optimizer summary

Detector: `all`  
This report coalesces compatible measurements from completed optimizer runs only.

<a id="table-of-contents"></a>

<details open>
<summary><strong>Navigation</strong></summary>

- [Preferred Detector Run Configuration](#preferred-detector-run-configuration)
- [Detector Run Profile Plot](#detector-run-profile-plot)
  - [adaptive_radial_edge](#detector-run-profile-adaptive-radial-edge)
  - [border_energy](#detector-run-profile-border-energy)
  - [components](#detector-run-profile-components)
  - [consensus_quad](#detector-run-profile-consensus-quad)
  - [contour](#detector-run-profile-contour)
  - [contour_components](#detector-run-profile-contour-components)
  - [contour_grabcut](#detector-run-profile-contour-grabcut)
  - [contour_projection](#detector-run-profile-contour-projection)
  - [contour_quad](#detector-run-profile-contour-quad)
  - [convex_hull](#detector-run-profile-convex-hull)
  - [cross_edge_contour](#detector-run-profile-cross-edge-contour)
  - [distance_transform](#detector-run-profile-distance-transform)
  - [distance_transform_rect](#detector-run-profile-distance-transform-rect)
  - [edge_contour](#detector-run-profile-edge-contour)
  - [grabcut](#detector-run-profile-grabcut)
  - [gradient_vote](#detector-run-profile-gradient-vote)
  - [hough](#detector-run-profile-hough)
  - [joint_rectangle_vote](#detector-run-profile-joint-rectangle-vote)
  - [learned_page_mask](#detector-run-profile-learned-page-mask)
  - [lsd](#detector-run-profile-lsd)
  - [polar_boundary_vote](#detector-run-profile-polar-boundary-vote)
  - [radial_edge](#detector-run-profile-radial-edge)
  - [radon_boundary](#detector-run-profile-radon-boundary)
  - [ransac](#detector-run-profile-ransac)
  - [star_convex](#detector-run-profile-star-convex)
  - [text_flow](#detector-run-profile-text-flow)
  - [whitespace_frame](#detector-run-profile-whitespace-frame)
- [Detector Pipeline-Thread Shape Optimization Data](#detector-pipeline-thread-shape-optimization-data)
  - [adaptive_radial_edge](#detector-shape-data-adaptive-radial-edge)
  - [border_energy](#detector-shape-data-border-energy)
  - [components](#detector-shape-data-components)
  - [consensus_quad](#detector-shape-data-consensus-quad)
  - [contour](#detector-shape-data-contour)
  - [contour_components](#detector-shape-data-contour-components)
  - [contour_grabcut](#detector-shape-data-contour-grabcut)
  - [contour_projection](#detector-shape-data-contour-projection)
  - [contour_quad](#detector-shape-data-contour-quad)
  - [convex_hull](#detector-shape-data-convex-hull)
  - [cross_edge_contour](#detector-shape-data-cross-edge-contour)
  - [distance_transform](#detector-shape-data-distance-transform)
  - [distance_transform_rect](#detector-shape-data-distance-transform-rect)
  - [edge_contour](#detector-shape-data-edge-contour)
  - [grabcut](#detector-shape-data-grabcut)
  - [gradient_vote](#detector-shape-data-gradient-vote)
  - [hough](#detector-shape-data-hough)
  - [joint_rectangle_vote](#detector-shape-data-joint-rectangle-vote)
  - [learned_page_mask](#detector-shape-data-learned-page-mask)
  - [lsd](#detector-shape-data-lsd)
  - [polar_boundary_vote](#detector-shape-data-polar-boundary-vote)
  - [radial_edge](#detector-shape-data-radial-edge)
  - [radon_boundary](#detector-shape-data-radon-boundary)
  - [ransac](#detector-shape-data-ransac)
  - [star_convex](#detector-shape-data-star-convex)
  - [text_flow](#detector-shape-data-text-flow)
  - [whitespace_frame](#detector-shape-data-whitespace-frame)

</details>

<a id="preferred-detector-run-configuration"></a>
<details open>
<summary><strong>1. Preferred Detector Run Configuration</strong></summary>

Compatible completed optimizer runs are coalesced by detector, workload, and concrete runner profile. Repeated shapes retain all observations; the preferred shape is selected canonically by throughput, then lower resource use for throughput-equivalent shapes.

| Detector | Runner | CPU | Physical | Logical | RAM | Preferred pipelines | Threads / pipeline | Preferred shape range (≤2%) | Search method | Optimization time | Allocated | Sets/s | Shape time | Observations |
|---|---|---|---:|---:|---:|---:|---:|---|---|---:|---:|---:|---:|---:|
| adaptive_radial_edge | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 63 | 6 | 63p/6t | adaptive | 4m 10s | 378 | 145.82 | 45s | 1 |
| adaptive_radial_edge | 192t — rh8-al323 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 60 | 6 | 60p/6t, 64p/6t | adaptive | 33m 4s | 360 | 152.60 | 43s | 1 |
| adaptive_radial_edge | 32t — rh8-s32 (32 vCPU) | AMD EPYC 9175F 16-Core Processor | 16 | 32 | 1511.3 GiB | 22 | 2 | 21p/3t, 22p/2t, 23p/2t, 24p/2t, 25p/2t, 26p/2t, 27p/2t | adaptive | 19m 31s | 44 | 74.57 | 1m 28s | 1 |
| adaptive_radial_edge | e7k — rh8-al97 (96 vCPU) | AMD EPYC 74F3 24-Core Processor | 48 | 96 | 2003.9 GiB | 49 | 3 | 46p/4t, 49p/3t, 50p/3t, 51p/3t, 52p/3t | exhaustive | 3h 35m 57s | 147 | 70.56 | 1m 33s | 1 |
| border_energy | 192t — rh8-al325 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 48 | 7p/54t, 8p/48t, 9p/42t | adaptive | 13m 27s | 384 | 84.13 | 1m 18s | 1 |
| components | 192t — rh8-al324 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 48 | 8p/48t | adaptive | 3m 31s | 384 | 596.45 | 33s | 1 |
| consensus_quad | 192t — rh8-al323 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 5 | 76 | 5p/76t, 6p/64t | adaptive | 2m 46s | 380 | 27.00 | 9s | 1 |
| contour | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 7 | 54 | 2p/192t, 3p/128t, 4p/96t, 5p/76t, 6p/64t, 7p/54t, 8p/48t | adaptive | 56s | 378 | 364.50 | 4s | 2 |
| contour_components | 192t — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 19 | 20 | 18p/21t, 19p/20t, 20p/19t, 21p/18t, 32p/12t | adaptive | 24m 29s | 380 | 223.68 | 1m 28s | 1 |
| contour_components | 32t — rh8-s32 (32 vCPU) | AMD EPYC 9175F 16-Core Processor | 16 | 32 | 1511.3 GiB | 9 | 7 | 8p/8t, 9p/7t, 10p/6t | adaptive | 25m 59s | 63 | 106.98 | 3m 4s | 1 |
| contour_components | e7k — rh8-al97 (96 vCPU) | AMD EPYC 74F3 24-Core Processor | 48 | 96 | 2003.9 GiB | 47 | 4 | 43p/4t, 44p/4t, 45p/4t, 46p/4t, 47p/4t, 48p/4t | adaptive | 1h 25m 28s | 188 | 111.21 | 2m 57s | 1 |
| contour_components | e9k — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 8 | 7p/9t, 8p/8t, 9p/7t | adaptive | 19m 31s | 64 | 123.03 | 2m 40s | 2 |
| contour_grabcut | 192t — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 2p/192t | adaptive | 2h 14m 47s | 384 | 4.93 | 22m 10s | 1 |
| contour_projection | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 21 | 18 | 21p/18t | adaptive | 1h 9m 57s | 378 | 49.71 | 2m 12s | 1 |
| contour_quad | 192t — rh8-al324 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 48 | 6p/64t, 7p/54t, 8p/48t, 9p/42t, 10p/38t | adaptive | 1d 45m 49s | 384 | 146.81 | 2h 40s | 1 |
| contour_quad | e9k — rh8-s32 (32 vCPU) | AMD EPYC 9175F 16-Core Processor | 16 | 32 | 1511.3 GiB | 3 | 21 | 2p/32t, 3p/21t, 4p/16t | exhaustive | 1d 13h 7m 7s | 63 | 52.24 | 5h 39m 5s | 1 |
| convex_hull | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 8 | 48 | 8p/48t | adaptive | 47s | 384 | 437.40 | 5s | 1 |
| cross_edge_contour | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 7 | 54 | 7p/54t, 8p/48t, 9p/42t | adaptive | 12m 27s | 378 | 93.74 | 1m 10s | 2 |
| distance_transform | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 64p/6t | adaptive | 1m 1s | 384 | 72.90 | 30s | 1 |
| distance_transform_rect | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 5 | 76 | 1p/384t, 3p/128t, 5p/76t | adaptive | 41s | 380 | 243.00 | 3s | 1 |
| edge_contour | 192t — rh8-al323 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 20 | 19 | 20p/19t, 21p/18t, 22p/17t, 23p/16t | adaptive | 18m 51s | 380 | 182.26 | 1m 12s | 1 |
| grabcut | 192t — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 2 | 192 | 2p/192t | adaptive | 45m 30s | 384 | 4.81 | 45m 30s | 1 |
| grabcut | 192t — rh8-al325 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 3p/128t | adaptive | 4h 7m 20s | 384 | 4.77 | 45m 52s | 1 |
| grabcut | e7k — rh8-al97 (96 vCPU) | AMD EPYC 74F3 24-Core Processor | 48 | 96 | 2003.9 GiB | 1 | 192 | 1p/192t, 2p/96t | exhaustive | 1h 54m | 192 | 1.92 | 1h 54m | 1 |
| gradient_vote | 192t — rh8-al325 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 9 | 42 | 9p/42t, 10p/38t | adaptive | 1m 38s | 378 | 729.11 | 9s | 1 |
| hough | 192t — rh8-al324 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 23 | 16 | 18p/21t, 22p/17t, 23p/16t | adaptive | 31m 29s | 368 | 25.15 | 1m 27s | 1 |
| joint_rectangle_vote | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 23 | 16 | 22p/17t, 23p/16t | adaptive | 10m 2s | 368 | 75.41 | 29s | 1 |
| learned_page_mask | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 2 | 192 | 2p/192t | adaptive | 16m 42s | 384 | 9.99 | 16m 41s | 1 |
| learned_page_mask | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 4 | 96 | 3p/128t, 4p/96t | exhaustive | 1h 8m 59s | 384 | 10.28 | 16m 13s | 2 |
| learned_page_mask | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 3p/128t | adaptive | 1m 2s | 384 | 8.10 | 30s | 2 |
| lsd | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 9 | 42 | 9p/42t | adaptive | 2m 19s | 378 | 168.23 | 13s | 1 |
| polar_boundary_vote | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 13 | 29 | 13p/29t | adaptive | 4m 2s | 377 | 60.75 | 12s | 1 |
| radial_edge | 192t — rh8-al323 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 26 | 14 | 23p/16t, 24p/16t, 25p/15t, 26p/14t, 27p/14t | adaptive | 7m 47s | 364 | 345.37 | 19s | 1 |
| radon_boundary | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 7 | 54 | 5p/76t, 6p/64t, 7p/54t | adaptive | 2m 26s | 378 | 56.08 | 13s | 1 |
| ransac | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 23 | 16 | 23p/16t | adaptive | 2m 54s | 368 | 145.80 | 10s | 1 |
| star_convex | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 10 | 38 | 10p/38t | adaptive | 2m 29s | 380 | 72.90 | 10s | 1 |
| text_flow | 192t — rh8-al319 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 8p/48t | adaptive | 1m 3s | 384 | 145.80 | 5s | 1 |
| whitespace_frame | 192t — rh8-al318 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 1511.3 GiB | 1 | 384 | 1p/384t, 3p/128t, 4p/96t | adaptive | 40s | 384 | 243.33 | 3s | 1 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction / optimizer coverage**

| Detector | Observed vCPU anchors | Prediction readiness | Prediction checks | Desired / missing optimization data |
|---|---|---|---|---|
| adaptive_radial_edge | 32, 96, 192 | high | 0 verified / 0 pending | basic vCPU shape coverage is sufficient; additional runner sizes are optional validation |
| border_energy | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| components | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| consensus_quad | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| contour | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| contour_components | 32, 96, 192 | high | 0 verified / 0 pending | basic vCPU shape coverage is sufficient; additional runner sizes are optional validation |
| contour_grabcut | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| contour_projection | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| contour_quad | 32, 192 | moderate | 0 verified / 0 pending | desired: a third vCPU size to validate interpolation/extrapolation |
| convex_hull | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| cross_edge_contour | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| distance_transform | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| distance_transform_rect | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| edge_contour | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| grabcut | 96, 192 | moderate | 0 verified / 0 pending | desired: a third vCPU size to validate interpolation/extrapolation |
| gradient_vote | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| hough | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| joint_rectangle_vote | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| learned_page_mask | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| lsd | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| polar_boundary_vote | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| radial_edge | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| radon_boundary | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| ransac | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| star_convex | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| text_flow | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| whitespace_frame | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-run-profile-plot"></a>
<details open>
<summary><strong>2. Detector Run Profile Plot</strong></summary>

Compatible completed measurements are plotted by detector; thread count is annotated at each measured shape.

<a id="detector-run-profile-adaptive-radial-edge"></a>
<details>
<summary><strong>adaptive_radial_edge</strong></summary>

**Search method(s):** `adaptive, exhaustive`

![adaptive_radial_edge Detector Run Profile Plot](profiles/adaptive_radial_edge.svg)

</details>

<a id="detector-run-profile-border-energy"></a>
<details>
<summary><strong>border_energy</strong></summary>

**Search method(s):** `adaptive`

![border_energy Detector Run Profile Plot](profiles/border_energy.svg)

</details>

<a id="detector-run-profile-components"></a>
<details>
<summary><strong>components</strong></summary>

**Search method(s):** `adaptive`

![components Detector Run Profile Plot](profiles/components.svg)

</details>

<a id="detector-run-profile-consensus-quad"></a>
<details>
<summary><strong>consensus_quad</strong></summary>

**Search method(s):** `adaptive`

![consensus_quad Detector Run Profile Plot](profiles/consensus_quad.svg)

</details>

<a id="detector-run-profile-contour"></a>
<details>
<summary><strong>contour</strong></summary>

**Search method(s):** `adaptive`

![contour Detector Run Profile Plot](profiles/contour.svg)

</details>

<a id="detector-run-profile-contour-components"></a>
<details>
<summary><strong>contour_components</strong></summary>

**Search method(s):** `adaptive`

![contour_components Detector Run Profile Plot](profiles/contour_components.svg)

</details>

<a id="detector-run-profile-contour-grabcut"></a>
<details>
<summary><strong>contour_grabcut</strong></summary>

**Search method(s):** `adaptive`

![contour_grabcut Detector Run Profile Plot](profiles/contour_grabcut.svg)

</details>

<a id="detector-run-profile-contour-projection"></a>
<details>
<summary><strong>contour_projection</strong></summary>

**Search method(s):** `adaptive`

![contour_projection Detector Run Profile Plot](profiles/contour_projection.svg)

</details>

<a id="detector-run-profile-contour-quad"></a>
<details>
<summary><strong>contour_quad</strong></summary>

**Search method(s):** `adaptive, exhaustive`

![contour_quad Detector Run Profile Plot](profiles/contour_quad.svg)

</details>

<a id="detector-run-profile-convex-hull"></a>
<details>
<summary><strong>convex_hull</strong></summary>

**Search method(s):** `adaptive`

![convex_hull Detector Run Profile Plot](profiles/convex_hull.svg)

</details>

<a id="detector-run-profile-cross-edge-contour"></a>
<details>
<summary><strong>cross_edge_contour</strong></summary>

**Search method(s):** `adaptive`

![cross_edge_contour Detector Run Profile Plot](profiles/cross_edge_contour.svg)

</details>

<a id="detector-run-profile-distance-transform"></a>
<details>
<summary><strong>distance_transform</strong></summary>

**Search method(s):** `adaptive`

![distance_transform Detector Run Profile Plot](profiles/distance_transform.svg)

</details>

<a id="detector-run-profile-distance-transform-rect"></a>
<details>
<summary><strong>distance_transform_rect</strong></summary>

**Search method(s):** `adaptive`

![distance_transform_rect Detector Run Profile Plot](profiles/distance_transform_rect.svg)

</details>

<a id="detector-run-profile-edge-contour"></a>
<details>
<summary><strong>edge_contour</strong></summary>

**Search method(s):** `adaptive`

![edge_contour Detector Run Profile Plot](profiles/edge_contour.svg)

</details>

<a id="detector-run-profile-grabcut"></a>
<details>
<summary><strong>grabcut</strong></summary>

**Search method(s):** `adaptive, exhaustive, powers-of-2`

![grabcut Detector Run Profile Plot](profiles/grabcut.svg)

</details>

<a id="detector-run-profile-gradient-vote"></a>
<details>
<summary><strong>gradient_vote</strong></summary>

**Search method(s):** `adaptive`

![gradient_vote Detector Run Profile Plot](profiles/gradient_vote.svg)

</details>

<a id="detector-run-profile-hough"></a>
<details>
<summary><strong>hough</strong></summary>

**Search method(s):** `adaptive`

![hough Detector Run Profile Plot](profiles/hough.svg)

</details>

<a id="detector-run-profile-joint-rectangle-vote"></a>
<details>
<summary><strong>joint_rectangle_vote</strong></summary>

**Search method(s):** `adaptive`

![joint_rectangle_vote Detector Run Profile Plot](profiles/joint_rectangle_vote.svg)

</details>

<a id="detector-run-profile-learned-page-mask"></a>
<details>
<summary><strong>learned_page_mask</strong></summary>

**Search method(s):** `adaptive, exhaustive`

![learned_page_mask Detector Run Profile Plot](profiles/learned_page_mask.svg)

</details>

<a id="detector-run-profile-lsd"></a>
<details>
<summary><strong>lsd</strong></summary>

**Search method(s):** `adaptive`

![lsd Detector Run Profile Plot](profiles/lsd.svg)

</details>

<a id="detector-run-profile-polar-boundary-vote"></a>
<details>
<summary><strong>polar_boundary_vote</strong></summary>

**Search method(s):** `adaptive`

![polar_boundary_vote Detector Run Profile Plot](profiles/polar_boundary_vote.svg)

</details>

<a id="detector-run-profile-radial-edge"></a>
<details>
<summary><strong>radial_edge</strong></summary>

**Search method(s):** `adaptive`

![radial_edge Detector Run Profile Plot](profiles/radial_edge.svg)

</details>

<a id="detector-run-profile-radon-boundary"></a>
<details>
<summary><strong>radon_boundary</strong></summary>

**Search method(s):** `adaptive`

![radon_boundary Detector Run Profile Plot](profiles/radon_boundary.svg)

</details>

<a id="detector-run-profile-ransac"></a>
<details>
<summary><strong>ransac</strong></summary>

**Search method(s):** `adaptive`

![ransac Detector Run Profile Plot](profiles/ransac.svg)

</details>

<a id="detector-run-profile-star-convex"></a>
<details>
<summary><strong>star_convex</strong></summary>

**Search method(s):** `adaptive`

![star_convex Detector Run Profile Plot](profiles/star_convex.svg)

</details>

<a id="detector-run-profile-text-flow"></a>
<details>
<summary><strong>text_flow</strong></summary>

**Search method(s):** `adaptive`

![text_flow Detector Run Profile Plot](profiles/text_flow.svg)

</details>

<a id="detector-run-profile-whitespace-frame"></a>
<details>
<summary><strong>whitespace_frame</strong></summary>

**Search method(s):** `adaptive`

![whitespace_frame Detector Run Profile Plot](profiles/whitespace_frame.svg)

</details>

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-pipeline-thread-shape-optimization-data"></a>
<details>
<summary><strong>3. Detector Pipeline-Thread Shape Optimization Data</strong></summary>

Coalesced compatible shape measurements from completed optimizer runs are shown below.

<a id="detector-shape-data-adaptive-radial-edge"></a>
<details>
<summary><strong>adaptive_radial_edge</strong></summary>

**Search method(s):** `adaptive, exhaustive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e7k — rh8-al97 (96 vCPU) | 1 | 1 | 96 | 96 | 42m 52s | 2.55 | 1.00× | -96.38% | 2.0 | 5.1 | 2.1% | 18.5 GiB |
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 23m 29s | 4.66 | 1.00× | -96.95% | 2.4 | 8.2 | 1.2% | 22.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 2 | 2 | 96 | 192 | 20m | 5.47 | 2.14× | -92.25% | 3.9 | 8.7 | 4.1% | 19.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 3 | 3 | 64 | 192 | 15m 15s | 7.17 | 2.81× | -89.84% | 5.3 | 8.3 | 5.5% | 19.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 4 | 4 | 48 | 192 | 10m 24s | 10.52 | 4.12× | -85.10% | 8.4 | 12.4 | 7.9% | 19.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 5 | 5 | 38 | 190 | 9m | 12.15 | 4.76× | -82.78% | 8.8 | 13.5 | 9.3% | 19.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 6 | 6 | 32 | 192 | 8m 3s | 13.59 | 5.33× | -80.75% | 8.6 | 10.2 | 10.1% | 19.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 7 | 7 | 27 | 189 | 6m 32s | 16.74 | 6.56× | -76.28% | 12.4 | 14.1 | 11.7% | 19.8 GiB |
| 32t — rh8-s32 (32 vCPU) | 8 | 8 | 8 | 64 | 2m 58s | 36.87 | — | -50.56% | 20.9 | 23.2 | 47.5% | 15.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 8 | 8 | 24 | 192 | 5m 33s | 19.71 | 7.72× | -72.07% | 13.6 | 16.3 | 15.0% | 20.0 GiB |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 3m 2s | 36.05 | 7.74× | -76.37% | 173.1 | 327.3 | 12.2% | 23.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 9 | 9 | 21 | 189 | 5m 29s | 19.95 | 7.82× | -71.73% | 12.9 | 15.2 | 14.0% | 19.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 10 | 10 | 19 | 190 | 4m 20s | 25.24 | 9.89× | -64.23% | 25.7 | 35.1 | 18.2% | 20.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 11 | 11 | 17 | 187 | 4m 7s | 26.57 | 10.41× | -62.35% | 20.9 | 23.0 | 19.6% | 20.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 12 | 12 | 16 | 192 | 4m 3s | 27.00 | 10.58× | -61.73% | 20.0 | 22.8 | 20.1% | 20.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 13 | 13 | 14 | 182 | 3m 25s | 32.01 | 12.55× | -54.63% | 21.0 | 24.2 | 20.6% | 20.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 14 | 14 | 13 | 182 | 3m 11s | 34.36 | 13.47× | -51.31% | 28.3 | 29.9 | 25.5% | 20.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 15 | 15 | 12 | 180 | 3m 20s | 32.81 | 12.86× | -53.50% | 34.8 | 42.0 | 25.6% | 20.4 GiB |
| 32t — rh8-s32 (32 vCPU) | 16 | 16 | 4 | 64 | 1m 37s | 67.65 | — | -9.28% | 101.3 | 106.9 | 85.5% | 16.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 16 | 16 | 12 | 192 | 2m 48s | 39.06 | 15.31× | -44.64% | 25.9 | 28.7 | 25.6% | 20.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 17 | 17 | 11 | 187 | 2m 44s | 40.01 | 15.68× | -43.29% | 28.0 | 32.1 | 28.9% | 20.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 18 | 18 | 10 | 180 | 2m 50s | 38.60 | 15.13× | -45.29% | 48.5 | 57.0 | 31.7% | 20.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 19 | 19 | 10 | 190 | 2m 30s | 43.75 | 17.15× | -38.00% | 60.8 | 89.0 | 30.0% | 21.2 GiB |
| 32t — rh8-s32 (32 vCPU) | 20 | 20 | 3 | 60 | 1m 30s | 72.91 | — | -2.22% | 112.0 | 119.7 | 88.8% | 16.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 20 | 20 | 9 | 180 | 2m 23s | 45.89 | 17.99× | -34.97% | 44.8 | 49.4 | 33.0% | 21.0 GiB |
| 32t — rh8-s32 (32 vCPU) | 21 | 21 | 3 | 63 | 1m 29s | 73.73 | — | -1.12% | 121.0 | 121.0 | 86.2% | 16.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 21 | 21 | 9 | 189 | 2m 28s | 44.34 | 17.38× | -37.16% | 36.4 | 38.9 | 34.8% | 21.3 GiB |
| **32t — rh8-s32 (32 vCPU)** | 22 | 22 | 2 | 44 | 1m 28s | 74.57 | — | 0.00% | 101.0 | 102.5 | 90.4% | 16.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 22 | 22 | 8 | 176 | 2m 13s | 49.34 | 19.34× | -30.08% | 37.9 | 43.0 | 36.2% | 21.2 GiB |
| 32t — rh8-s32 (32 vCPU) | 23 | 23 | 2 | 46 | 1m 29s | 73.73 | — | -1.12% | 112.5 | 112.5 | 86.9% | 16.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 23 | 23 | 8 | 184 | 2m 9s | 50.87 | 19.94× | -27.91% | 42.7 | 45.4 | 39.0% | 21.6 GiB |
| 192t — rh8-al323 (192 vCPU) | 23 | 23 | 16 | 368 | 1m 12s | 91.14 | 19.57× | -40.28% | 143.0 | 143.0 | 24.3% | 24.5 GiB |
| 32t — rh8-s32 (32 vCPU) | 24 | 24 | 2 | 48 | 1m 29s | 73.73 | — | -1.12% | 121.5 | 121.5 | 86.5% | 16.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 24 | 24 | 8 | 192 | 2m 16s | 48.25 | 18.91× | -31.62% | 49.2 | 56.3 | 40.7% | 21.8 GiB |
| 32t — rh8-s32 (32 vCPU) | 25 | 25 | 2 | 50 | 1m 29s | 73.73 | — | -1.12% | 153.2 | 166.3 | 90.5% | 16.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 25 | 25 | 7 | 175 | 2m | 54.68 | 21.43× | -22.50% | 40.7 | 43.1 | 37.9% | 21.4 GiB |
| 32t — rh8-s32 (32 vCPU) | 26 | 26 | 2 | 52 | 1m 28s | 74.57 | — | 0.00% | 137.2 | 137.2 | 88.8% | 16.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 26 | 26 | 7 | 182 | 1m 59s | 55.14 | 21.61× | -21.85% | 70.9 | 82.9 | 43.8% | 21.7 GiB |
| 32t — rh8-s32 (32 vCPU) | 27 | 27 | 2 | 54 | 1m 29s | 73.73 | — | -1.12% | 136.8 | 138.6 | 89.7% | 16.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 27 | 27 | 7 | 189 | 2m 6s | 52.08 | 20.41× | -26.19% | 87.1 | 102.5 | 45.1% | 22.1 GiB |
| 32t — rh8-s32 (32 vCPU) | 28 | 28 | 2 | 56 | 1m 30s | 72.91 | — | -2.22% | 133.1 | 133.1 | 92.5% | 17.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 28 | 28 | 6 | 168 | 1m 52s | 58.59 | 22.96× | -16.96% | 47.9 | 51.9 | 42.4% | 21.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 29 | 29 | 6 | 174 | 1m 52s | 58.59 | 22.96× | -16.96% | 53.4 | 55.3 | 49.2% | 21.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 30 | 30 | 6 | 180 | 1m 58s | 55.61 | 21.80× | -21.19% | 62.6 | 69.2 | 51.0% | 22.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 31 | 31 | 6 | 186 | 1m 46s | 61.91 | 24.26× | -12.26% | 55.0 | 59.4 | 48.0% | 22.6 GiB |
| 32t — rh8-s32 (32 vCPU) | 32 | 32 | 2 | 64 | 1m 31s | 72.11 | — | -3.30% | 102.1 | 102.1 | 92.9% | 17.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 32 | 32 | 6 | 192 | 1m 45s | 62.50 | 24.50× | -11.43% | 95.0 | 100.6 | 54.9% | 22.9 GiB |
| 192t — rh8-al321 (192 vCPU) | 32 | 32 | 12 | 384 | 58s | 113.14 | — | -22.41% | 311.6 | 311.6 | 48.2% | 11.0 GiB |
| e7k — rh8-al97 (96 vCPU) | 33 | 33 | 5 | 165 | 1m 50s | 59.65 | 23.38× | -15.45% | 90.2 | 104.6 | 51.0% | 22.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 34 | 34 | 5 | 170 | 1m 42s | 64.33 | 25.22× | -8.82% | 84.5 | 84.5 | 56.3% | 22.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 35 | 35 | 5 | 175 | 1m 42s | 64.33 | 25.22× | -8.82% | 128.1 | 133.0 | 59.1% | 22.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 36 | 36 | 5 | 180 | 1m 48s | 60.76 | 23.81× | -13.89% | 99.0 | 102.5 | 59.9% | 22.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 37 | 37 | 5 | 185 | 1m 39s | 66.28 | 25.98× | -6.06% | 135.0 | 135.0 | 49.8% | 23.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 38 | 38 | 5 | 190 | 1m 40s | 65.62 | 25.72× | -7.00% | 141.2 | 163.2 | 64.2% | 23.5 GiB |
| 192t — rh8-al323 (192 vCPU) | 38 | 38 | 10 | 380 | 50s | 131.24 | 28.18× | -14.00% | 265.3 | 265.3 | 43.3% | 26.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 39 | 39 | 4 | 156 | 1m 44s | 63.10 | 24.73× | -10.58% | 131.5 | 144.6 | 66.5% | 22.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 40 | 40 | 4 | 160 | 1m 36s | 68.35 | 26.79× | -3.12% | 109.4 | 109.4 | 53.8% | 22.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 41 | 41 | 4 | 164 | 1m 36s | 68.35 | 26.79× | -3.12% | 168.1 | 178.8 | 69.3% | 23.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 42 | 42 | 4 | 168 | 1m 40s | 65.62 | 25.72× | -7.00% | 221.3 | 232.5 | 70.6% | 23.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 43 | 43 | 4 | 172 | 1m 35s | 69.07 | 27.07× | -2.11% | 215.3 | 215.3 | 62.2% | 23.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 44 | 44 | 4 | 176 | 1m 35s | 69.07 | 27.07× | -2.11% | 176.1 | 185.0 | 74.7% | 23.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 45 | 45 | 4 | 180 | 1m 38s | 66.96 | 26.24× | -5.10% | 127.5 | 127.5 | 70.1% | 23.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 46 | 46 | 4 | 184 | 1m 34s | 69.81 | 27.36× | -1.06% | 159.2 | 170.2 | 72.8% | 24.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 47 | 47 | 4 | 188 | 1m 35s | 69.07 | 27.07× | -2.11% | 264.8 | 279.0 | 78.9% | 24.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 48 | 48 | 4 | 192 | 1m 37s | 67.65 | 26.52× | -4.12% | 249.0 | 249.0 | 72.6% | 24.7 GiB |
| 192t — rh8-al323 (192 vCPU) | 48 | 48 | 8 | 384 | 47s | 139.62 | 29.98× | -8.51% | — | — | — | — |
| **e7k — rh8-al97 (96 vCPU)** | 49 | 49 | 3 | 147 | 1m 33s | 70.56 | 27.66× | 0.00% | 253.8 | 287.8 | 78.6% | 23.6 GiB |
| 192t — rh8-al323 (192 vCPU) | 49 | 49 | 7 | 343 | 47s | 139.62 | 29.98× | -8.51% | 732.8 | 732.8 | 74.4% | 18.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 50 | 50 | 3 | 150 | 1m 33s | 70.56 | 27.66× | 0.00% | 329.1 | 329.1 | 75.7% | 23.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 51 | 51 | 3 | 153 | 1m 34s | 69.81 | 27.36× | -1.06% | 270.9 | 284.9 | 83.0% | 23.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 52 | 52 | 3 | 156 | 1m 33s | 70.56 | 27.66× | 0.00% | 270.5 | 270.5 | 74.2% | 24.0 GiB |
| 192t — rh8-al323 (192 vCPU) | 56 | 56 | 6 | 336 | 44s | 149.14 | 32.02× | -2.27% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 59 | 59 | 6 | 354 | 45s | 145.82 | 31.31× | -4.44% | 809.4 | 809.4 | 78.4% | 28.7 GiB |
| **192t — rh8-al323 (192 vCPU)** | 60 | 60 | 6 | 360 | 43s | 152.60 | 32.77× | 0.00% | 693.5 | 693.5 | 60.9% | 28.4 GiB |
| 192t — rh8-al323 (192 vCPU) | 61 | 61 | 6 | 366 | 45s | 145.82 | 31.31× | -4.44% | 1025.5 | 1025.5 | 71.5% | 11.3 GiB |
| 192t — rh8-al321 (192 vCPU) | 62 | 62 | 6 | 372 | 46s | 142.65 | — | -2.17% | 1020.8 | 1020.8 | 73.9% | 19.2 GiB |
| **192t — rh8-al321 (192 vCPU)** | 63 | 63 | 6 | 378 | 45s | 145.82 | — | 0.00% | 971.3 | 971.3 | 72.7% | 29.7 GiB |
| 192t — rh8-al321 (192 vCPU) | 64 | 64 | 6 | 384 | 47s | 139.62 | — | -4.26% | 503.1 | 503.1 | 59.5% | 29.2 GiB |
| 192t — rh8-al323 (192 vCPU) | 64 | 64 | 6 | 384 | 43s | 152.60 | 32.77× | 0.00% | 591.5 | 591.5 | 41.2% | 30.2 GiB |
| 192t — rh8-al323 (192 vCPU) | 68 | 68 | 5 | 340 | 47s | 139.62 | 29.98× | -8.51% | 660.2 | 660.2 | 67.1% | 29.3 GiB |
| 192t — rh8-al323 (192 vCPU) | 80 | 80 | 4 | 320 | 48s | 136.71 | 29.35× | -10.42% | 715.1 | 715.1 | 52.4% | 11.2 GiB |
| 192t — rh8-al323 (192 vCPU) | 81 | 81 | 4 | 324 | 44s | 149.14 | 32.02× | -2.27% | 798.7 | 798.7 | 68.7% | 17.9 GiB |
| 192t — rh8-al323 (192 vCPU) | 82 | 82 | 4 | 328 | 49s | 133.92 | 28.76× | -12.24% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 96 | 96 | 4 | 384 | 48s | 136.71 | 29.35× | -10.42% | 470.6 | 470.6 | 63.6% | 28.3 GiB |
| 192t — rh8-al321 (192 vCPU) | 128 | 128 | 3 | 384 | 52s | 126.19 | — | -13.46% | — | — | — | — |

</details>

<a id="detector-shape-data-border-energy"></a>
<details>
<summary><strong>border_energy</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al325 (192 vCPU) | 1 | 1 | 384 | 384 | 4m 23s | 24.95 | 1.00× | -70.34% | 52.4 | 56.7 | 38.2% | 22.9 GiB |
| 192t — rh8-al325 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 25s | 77.20 | 3.09× | -8.24% | 863.6 | 875.2 | 94.0% | 23.5 GiB |
| 192t — rh8-al325 (192 vCPU) | 7 | 7 | 54 | 378 | 1m 19s | 83.06 | 3.33× | -1.27% | 1087.8 | 1087.8 | 92.4% | 23.4 GiB |
| **192t — rh8-al325 (192 vCPU)** | 8 | 8 | 48 | 384 | 1m 18s | 84.13 | 3.37× | 0.00% | 1816.5 | 2193.8 | 92.8% | 23.8 GiB |
| 192t — rh8-al325 (192 vCPU) | 9 | 9 | 42 | 378 | 1m 19s | 83.06 | 3.33× | -1.27% | 975.8 | 975.8 | 92.6% | 23.8 GiB |
| 192t — rh8-al325 (192 vCPU) | 10 | 10 | 38 | 380 | 1m 21s | 81.01 | 3.25× | -3.70% | 963.7 | 963.7 | 92.0% | 24.0 GiB |
| 192t — rh8-al325 (192 vCPU) | 64 | 64 | 6 | 384 | 2m 21s | 46.54 | 1.87× | -44.68% | 1903.7 | 2504.5 | 84.3% | 32.9 GiB |

</details>

<a id="detector-shape-data-components"></a>
<details>
<summary><strong>components</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al324 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 5s | 302.82 | 1.00× | -49.23% | 29.3 | 29.3 | 24.9% | 15.6 GiB |
| 192t — rh8-al324 (192 vCPU) | 7 | 7 | 54 | 378 | 34s | 578.91 | 1.91× | -2.94% | 845.0 | 845.0 | 76.0% | 11.0 GiB |
| **192t — rh8-al324 (192 vCPU)** | 8 | 8 | 48 | 384 | 33s | 596.45 | 1.97× | 0.00% | 766.1 | 766.1 | 61.9% | 16.1 GiB |
| 192t — rh8-al324 (192 vCPU) | 9 | 9 | 42 | 378 | 34s | 578.91 | 1.91× | -2.94% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 64 | 64 | 6 | 384 | 44s | 447.34 | 1.48× | -25.00% | — | — | — | — |

</details>

<a id="detector-shape-data-consensus-quad"></a>
<details>
<summary><strong>consensus_quad</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 21s | 11.57 | 1.00× | -57.14% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 4 | 4 | 96 | 384 | 10s | 24.30 | 2.10× | -10.00% | — | — | — | — |
| **192t — rh8-al323 (192 vCPU)** | 5 | 5 | 76 | 380 | 9s | 27.00 | 2.33× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 6 | 6 | 64 | 384 | 9s | 27.00 | 2.33× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 7 | 7 | 54 | 378 | 10s | 24.30 | 2.10× | -10.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 10s | 24.30 | 2.10× | -10.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 9 | 9 | 42 | 378 | 11s | 22.09 | 1.91× | -18.18% | 991.7 | 991.7 | 82.6% | 11.7 GiB |
| 192t — rh8-al323 (192 vCPU) | 10 | 10 | 38 | 380 | 11s | 22.09 | 1.91× | -18.18% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 11 | 11 | 34 | 374 | 12s | 20.25 | 1.75× | -25.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 128 | 128 | 3 | 384 | 1m 2s | 3.92 | 0.34× | -85.48% | 1212.0 | 1212.0 | 61.8% | 14.8 GiB |

</details>

<a id="detector-shape-data-contour"></a>
<details>
<summary><strong>contour</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 6s | 243.00 | 1.00× | -33.33% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 2 | 2 | 192 | 384 | 4s | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 3 | 3 | 128 | 384 | 4s | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 4 | 4 | 96 | 384 | 4s | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 5 | 5 | 76 | 380 | 4s | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 6 | 6 | 64 | 384 | 4s | 364.50 | 1.50× | 0.00% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 7 | 7 | 54 | 378 | 4s | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 4s | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 5s | 291.60 | 1.20× | -20.00% | 62.2 | 62.2 | 11.3% | 10.9 GiB |
| 192t — rh8-al319 (192 vCPU) | 10 | 10 | 38 | 380 | 5s | 291.60 | 1.20× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 16 | 16 | 24 | 384 | 6s | 243.00 | 1.00× | -33.33% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 32 | 32 | 12 | 384 | 12s | 121.50 | 0.50× | -66.67% | — | — | — | — |

</details>

<a id="detector-shape-data-contour-components"></a>
<details>
<summary><strong>contour_components</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e7k — rh8-al97 (96 vCPU) | 1 | 1 | 16 | 16 | 14m 2s | 23.38 | 1.00× | -78.98% | 16.1 | 24.6 | 18.4% | 14.4 GiB |
| e9k — rh8-al320 (192 vCPU) | 1 | 1 | 64 | 64 | 8m 13s | 39.93 | 1.00× | -67.55% | 7.8 | 13.3 | 8.3% | 12.2 GiB |
| 192t — rh8-al320 (192 vCPU) | 1 | 1 | 384 | 384 | 9m 45s | 33.65 | 1.00× | -84.96% | 10.5 | 18.6 | 7.1% | 17.4 GiB |
| 32t — rh8-s32 (32 vCPU) | 2 | 2 | 32 | 64 | 6m 29s | 50.60 | — | -52.70% | 28.5 | 38.3 | 61.8% | 14.0 GiB |
| e9k — rh8-al320 (192 vCPU) | 3 | 3 | 21 | 63 | 3m 35s | 91.55 | 2.29× | -25.58% | 253.2 | 592.1 | 30.8% | 12.5 GiB |
| e9k — rh8-al320 (192 vCPU) | 4 | 4 | 16 | 64 | 3m 3s | 107.56 | 2.69× | -12.57% | 98.9 | 113.4 | 37.9% | 12.5 GiB |
| e9k — rh8-al320 (192 vCPU) | 6 | 6 | 10 | 60 | 2m 48s | 117.17 | 2.93× | -4.76% | 738.7 | 739.6 | 94.7% | 12.7 GiB |
| 192t — rh8-al320 (192 vCPU) | 6 | 6 | 64 | 384 | 2m 46s | 118.58 | 3.52× | -46.99% | 1146.1 | 1280.0 | 88.9% | 17.8 GiB |
| 32t — rh8-s32 (32 vCPU) | 7 | 7 | 9 | 63 | 3m 8s | 104.70 | — | -2.13% | 169.8 | 177.8 | 95.0% | 14.5 GiB |
| e9k — rh8-al320 (192 vCPU) | 7 | 7 | 9 | 63 | 2m 42s | 121.51 | 3.04× | -1.23% | 783.4 | 813.3 | 93.1% | 13.0 GiB |
| 32t — rh8-s32 (32 vCPU) | 8 | 8 | 8 | 64 | 3m 6s | 105.83 | — | -1.08% | 185.3 | 193.4 | 94.2% | 14.7 GiB |
| **e9k — rh8-al320 (192 vCPU)** | 8 | 8 | 8 | 64 | 2m 40s | 123.03 | 3.08× | 0.00% | 865.3 | 866.8 | 96.6% | 13.1 GiB |
| 192t — rh8-al320 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 58s | 166.81 | 4.96× | -25.42% | 1018.8 | 1133.4 | 90.6% | 18.0 GiB |
| **32t — rh8-s32 (32 vCPU)** | 9 | 9 | 7 | 63 | 3m 4s | 106.98 | — | 0.00% | 168.1 | 177.8 | 95.1% | 14.7 GiB |
| e9k — rh8-al320 (192 vCPU) | 9 | 9 | 7 | 63 | 2m 42s | 121.51 | 3.04× | -1.23% | 770.7 | 807.1 | 87.7% | 13.1 GiB |
| 32t — rh8-s32 (32 vCPU) | 10 | 10 | 6 | 60 | 3m 6s | 105.83 | — | -1.08% | 172.6 | 181.3 | 95.1% | 14.7 GiB |
| e9k — rh8-al320 (192 vCPU) | 10 | 10 | 6 | 60 | 2m 44s | 120.02 | 3.01× | -2.44% | 833.1 | 895.0 | 90.6% | 13.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 10 | 10 | 16 | 160 | 6m 6s | 53.78 | 2.30× | -51.64% | 454.6 | 792.4 | 79.4% | 17.6 GiB |
| 32t — rh8-s32 (32 vCPU) | 11 | 11 | 5 | 55 | 3m 9s | 104.15 | — | -2.65% | 171.6 | 178.2 | 95.1% | 14.8 GiB |
| e9k — rh8-al320 (192 vCPU) | 14 | 14 | 4 | 56 | 2m 59s | 109.97 | 2.75× | -10.61% | 1003.0 | 1036.5 | 93.4% | 13.9 GiB |
| 192t — rh8-al320 (192 vCPU) | 14 | 14 | 27 | 378 | 1m 31s | 216.31 | 6.43× | -3.30% | 1414.4 | 1414.4 | 93.9% | 18.9 GiB |
| e9k — rh8-al320 (192 vCPU) | 16 | 16 | 4 | 64 | 2m 52s | 114.44 | 2.87× | -6.98% | 837.0 | 968.7 | 89.5% | 14.2 GiB |
| 192t — rh8-al320 (192 vCPU) | 17 | 17 | 22 | 374 | 1m 31s | 216.31 | 6.43× | -3.30% | 1548.7 | 1548.7 | 83.1% | 19.0 GiB |
| 192t — rh8-al320 (192 vCPU) | 18 | 18 | 21 | 378 | 1m 29s | 221.17 | 6.57× | -1.12% | 1496.1 | 1613.3 | 91.4% | 19.6 GiB |
| **192t — rh8-al320 (192 vCPU)** | 19 | 19 | 20 | 380 | 1m 28s | 223.68 | 6.65× | 0.00% | 1471.0 | 1471.0 | 83.0% | 19.3 GiB |
| 192t — rh8-al320 (192 vCPU) | 20 | 20 | 19 | 380 | 1m 28s | 223.68 | 6.65× | 0.00% | 1570.0 | 1570.0 | 94.4% | 19.9 GiB |
| 192t — rh8-al320 (192 vCPU) | 21 | 21 | 18 | 378 | 1m 29s | 221.17 | 6.57× | -1.12% | 1394.6 | 1400.2 | 85.8% | 19.5 GiB |
| 192t — rh8-al320 (192 vCPU) | 22 | 22 | 17 | 374 | 1m 30s | 218.71 | 6.50× | -2.22% | 1500.4 | 1607.5 | 91.4% | 20.2 GiB |
| e9k — rh8-al320 (192 vCPU) | 23 | 23 | 2 | 46 | 3m 55s | 83.76 | 2.10× | -31.91% | 1063.9 | 1195.0 | 94.0% | 15.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 30 | 30 | 6 | 180 | 3m 18s | 99.41 | 4.25× | -10.61% | 834.2 | 949.1 | 87.4% | 20.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 31 | 31 | 6 | 186 | 3m 15s | 100.94 | 4.32× | -9.23% | 715.4 | 1017.6 | 84.9% | 20.7 GiB |
| 32t — rh8-s32 (32 vCPU) | 32 | 32 | 2 | 64 | 3m 52s | 84.84 | — | -20.69% | 218.8 | 283.7 | 92.0% | 17.0 GiB |
| e7k — rh8-al97 (96 vCPU) | 32 | 32 | 6 | 192 | 3m 12s | 102.52 | 4.39× | -7.81% | 954.6 | 1066.2 | 91.2% | 20.7 GiB |
| 192t — rh8-al320 (192 vCPU) | 32 | 32 | 12 | 384 | 1m 29s | 221.17 | 6.57× | -1.12% | 1055.8 | 1549.1 | 60.3% | 21.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 33 | 33 | 5 | 165 | 3m 10s | 103.60 | 4.43× | -6.84% | 895.0 | 998.6 | 87.2% | 20.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 34 | 34 | 5 | 170 | 3m 9s | 104.15 | 4.46× | -6.35% | 947.3 | 1128.1 | 87.3% | 20.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 35 | 35 | 5 | 175 | 3m 8s | 104.70 | 4.48× | -5.85% | 924.0 | 1096.1 | 86.7% | 21.1 GiB |
| e7k — rh8-al97 (96 vCPU) | 36 | 36 | 5 | 180 | 3m 5s | 106.40 | 4.55× | -4.32% | 984.5 | 1169.9 | 87.1% | 21.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 37 | 37 | 5 | 185 | 3m 4s | 106.98 | 4.58× | -3.80% | 934.3 | 1115.4 | 86.3% | 21.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 38 | 38 | 5 | 190 | 3m 3s | 107.56 | 4.60× | -3.28% | 958.6 | 1229.5 | 81.2% | 21.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 39 | 39 | 4 | 156 | 3m 2s | 108.15 | 4.63× | -2.75% | 987.2 | 1155.3 | 87.1% | 21.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 40 | 40 | 4 | 160 | 3m 2s | 108.15 | 4.63× | -2.75% | 1032.7 | 1171.5 | 86.7% | 21.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 41 | 41 | 4 | 164 | 3m 2s | 108.15 | 4.63× | -2.75% | 1048.3 | 1242.9 | 85.8% | 21.6 GiB |
| e7k — rh8-al97 (96 vCPU) | 42 | 42 | 4 | 168 | 3m 1s | 108.75 | 4.65× | -2.21% | 1046.8 | 1207.3 | 85.4% | 21.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 43 | 43 | 4 | 172 | 3m | 109.36 | 4.68× | -1.67% | 1094.2 | 1262.6 | 84.9% | 21.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 44 | 44 | 4 | 176 | 3m | 109.36 | 4.68× | -1.67% | 1093.6 | 1289.7 | 84.1% | 22.2 GiB |
| e7k — rh8-al97 (96 vCPU) | 45 | 45 | 4 | 180 | 3m | 109.36 | 4.68× | -1.67% | 1094.0 | 1280.3 | 83.8% | 22.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 46 | 46 | 4 | 184 | 3m | 109.36 | 4.68× | -1.67% | 1123.7 | 1362.3 | 84.0% | 22.6 GiB |
| **e7k — rh8-al97 (96 vCPU)** | 47 | 47 | 4 | 188 | 2m 57s | 111.21 | 4.76× | 0.00% | 1155.0 | 1411.6 | 82.0% | 22.8 GiB |
| e7k — rh8-al97 (96 vCPU) | 48 | 48 | 4 | 192 | 2m 58s | 110.58 | 4.73× | -0.56% | 1187.8 | 1341.9 | 97.1% | 23.0 GiB |
| e7k — rh8-al97 (96 vCPU) | 49 | 49 | 3 | 147 | 3m 8s | 104.70 | 4.48× | -5.85% | 1073.1 | 1384.4 | 78.4% | 22.4 GiB |
| e9k — rh8-al320 (192 vCPU) | 64 | 64 | 1 | 64 | 4m 43s | 69.55 | 1.74× | -43.46% | 1677.1 | 1997.1 | 92.3% | 20.5 GiB |
| e7k — rh8-al97 (96 vCPU) | 96 | 96 | 2 | 192 | 3m 30s | 93.73 | 4.01× | -15.71% | 1499.2 | 1779.0 | 93.9% | 28.8 GiB |
| 192t — rh8-al320 (192 vCPU) | 96 | 96 | 4 | 384 | 1m 59s | 165.41 | 4.92× | -26.05% | 1913.1 | 2187.2 | 83.6% | 30.0 GiB |

</details>

<a id="detector-shape-data-contour-grabcut"></a>
<details>
<summary><strong>contour_grabcut</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al320 (192 vCPU)** | 1 | 1 | 384 | 384 | 22m 10s | 4.93 | 1.00× | 0.00% | 366.6 | 429.7 | 91.5% | 60.2 GiB |
| 192t — rh8-al320 (192 vCPU) | 2 | 2 | 192 | 384 | 22m 19s | 4.90 | 0.99× | -0.67% | 504.4 | 550.8 | 94.2% | 62.0 GiB |
| 192t — rh8-al320 (192 vCPU) | 3 | 3 | 128 | 384 | 22m 56s | 4.77 | 0.97× | -3.34% | 599.2 | 700.1 | 93.7% | 75.1 GiB |
| 192t — rh8-al320 (192 vCPU) | 11 | 11 | 34 | 374 | 30m 10s | 3.63 | 0.73× | -26.52% | 1096.2 | 1233.8 | 96.8% | 84.6 GiB |
| 192t — rh8-al320 (192 vCPU) | 128 | 128 | 3 | 384 | 37m 9s | 2.94 | 0.60× | -40.33% | 1782.4 | 2079.5 | 98.5% | 105.1 GiB |

</details>

<a id="detector-shape-data-contour-projection"></a>
<details>
<summary><strong>contour_projection</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 34m 26s | 3.18 | 1.00× | -93.61% | 7.1 | 28.3 | 4.0% | 16.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 10 | 10 | 38 | 380 | 3m 24s | 32.17 | 10.13× | -35.29% | 1322.6 | 1398.2 | 83.4% | 17.3 GiB |
| 192t — rh8-al321 (192 vCPU) | 11 | 11 | 34 | 374 | 3m 2s | 36.05 | 11.35× | -27.47% | 1631.2 | 1749.7 | 91.5% | 17.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 12 | 12 | 32 | 384 | 2m 39s | 41.27 | 12.99× | -16.98% | 1316.0 | 1518.0 | 92.2% | 17.6 GiB |
| 192t — rh8-al321 (192 vCPU) | 13 | 13 | 29 | 377 | 2m 31s | 43.46 | 13.68× | -12.58% | 1397.5 | 1502.5 | 91.9% | 17.6 GiB |
| 192t — rh8-al321 (192 vCPU) | 14 | 14 | 27 | 378 | 2m 29s | 44.04 | 13.87× | -11.41% | 1483.2 | 1541.3 | 97.8% | 17.7 GiB |
| 192t — rh8-al321 (192 vCPU) | 15 | 15 | 25 | 375 | 2m 24s | 45.57 | 14.35× | -8.33% | 1423.3 | 1483.7 | 92.9% | 17.7 GiB |
| 192t — rh8-al321 (192 vCPU) | 16 | 16 | 24 | 384 | 2m 26s | 44.95 | 14.15× | -9.59% | 1565.7 | 1609.1 | 95.4% | 18.0 GiB |
| 192t — rh8-al321 (192 vCPU) | 17 | 17 | 22 | 374 | 2m 18s | 47.55 | 14.97× | -4.35% | 1408.5 | 1466.7 | 89.9% | 17.9 GiB |
| 192t — rh8-al321 (192 vCPU) | 18 | 18 | 21 | 378 | 2m 16s | 48.25 | 15.19× | -2.94% | 1396.7 | 1472.8 | 92.8% | 18.1 GiB |
| 192t — rh8-al321 (192 vCPU) | 19 | 19 | 20 | 380 | 2m 15s | 48.61 | 15.30× | -2.22% | 1373.0 | 1507.7 | 94.8% | 18.2 GiB |
| 192t — rh8-al321 (192 vCPU) | 20 | 20 | 19 | 380 | 2m 15s | 48.61 | 15.30× | -2.22% | 1538.1 | 1577.0 | 96.6% | 18.4 GiB |
| **192t — rh8-al321 (192 vCPU)** | 21 | 21 | 18 | 378 | 2m 12s | 49.71 | 15.65× | 0.00% | 1516.3 | 1567.4 | 92.8% | 18.4 GiB |
| 192t — rh8-al321 (192 vCPU) | 22 | 22 | 17 | 374 | 2m 15s | 48.61 | 15.30× | -2.22% | 1508.4 | 1532.1 | 94.7% | 18.5 GiB |
| 192t — rh8-al321 (192 vCPU) | 128 | 128 | 3 | 384 | 3m 4s | 35.66 | 11.23× | -28.26% | 1817.4 | 2605.0 | 82.9% | 30.3 GiB |

</details>

<a id="detector-shape-data-contour-quad"></a>
<details>
<summary><strong>contour_quad</strong></summary>

**Search method(s):** `adaptive, exhaustive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| e9k — rh8-s32 (32 vCPU) | 1 | 1 | 64 | 64 | 7h 43m 45s | 38.20 | 1.00× | -26.88% | 55.9 | 66.6 | 90.0% | 38.4 GiB |
| 192t — rh8-al324 (192 vCPU) | 1 | 1 | 384 | 384 | 7h 3m 20s | 41.85 | 1.00× | -71.50% | 68.4 | 97.7 | 40.3% | 43.1 GiB |
| e9k — rh8-s32 (32 vCPU) | 2 | 2 | 32 | 64 | 5h 44m 51s | 51.37 | 1.34× | -1.67% | 101.7 | 111.7 | 97.2% | 38.1 GiB |
| **e9k — rh8-s32 (32 vCPU)** | 3 | 3 | 21 | 63 | 5h 39m 5s | 52.24 | 1.37× | 0.00% | 111.3 | 123.6 | 97.4% | 38.3 GiB |
| e9k — rh8-s32 (32 vCPU) | 4 | 4 | 16 | 64 | 5h 41m 43s | 51.84 | 1.36× | -0.77% | 120.2 | 134.3 | 97.7% | 39.8 GiB |
| e9k — rh8-s32 (32 vCPU) | 5 | 5 | 12 | 60 | 5h 59m 23s | 49.29 | 1.29× | -5.65% | 125.6 | 146.2 | 97.5% | 39.0 GiB |
| 192t — rh8-al324 (192 vCPU) | 5 | 5 | 76 | 380 | 2h 10m 13s | 136.04 | 3.25× | -7.33% | 716.6 | 849.0 | 90.6% | 44.2 GiB |
| e9k — rh8-s32 (32 vCPU) | 6 | 6 | 10 | 60 | 6h 18m 20s | 46.82 | 1.23× | -10.37% | 135.6 | 155.2 | 97.8% | 39.3 GiB |
| 192t — rh8-al324 (192 vCPU) | 6 | 6 | 64 | 384 | 2h 2m 31s | 144.59 | 3.46× | -1.51% | 810.0 | 942.6 | 92.4% | 43.5 GiB |
| 192t — rh8-al324 (192 vCPU) | 7 | 7 | 54 | 378 | 2h 1m 25s | 145.90 | 3.49× | -0.62% | 838.8 | 1010.0 | 92.0% | 42.7 GiB |
| **192t — rh8-al324 (192 vCPU)** | 8 | 8 | 48 | 384 | 2h 40s | 146.81 | 3.51× | 0.00% | 912.3 | 1088.9 | 93.2% | 44.6 GiB |
| 192t — rh8-al324 (192 vCPU) | 9 | 9 | 42 | 378 | 2h 1m 28s | 145.84 | 3.49× | -0.66% | 969.3 | 1174.2 | 93.5% | 45.3 GiB |
| 192t — rh8-al324 (192 vCPU) | 10 | 10 | 38 | 380 | 2h 3m 7s | 143.89 | 3.44× | -1.99% | 978.4 | 1149.2 | 93.4% | 43.7 GiB |
| 192t — rh8-al324 (192 vCPU) | 11 | 11 | 34 | 374 | 2h 3m 56s | 142.94 | 3.42× | -2.64% | 1056.6 | 1212.6 | 94.3% | 47.5 GiB |
| 192t — rh8-al324 (192 vCPU) | 128 | 128 | 3 | 384 | 3h 19m 3s | 89.00 | 2.13× | -39.38% | 6124.3 | 6996.3 | 97.3% | 127.1 GiB |

</details>

<a id="detector-shape-data-convex-hull"></a>
<details>
<summary><strong>convex_hull</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 7s | 312.43 | 1.00× | -28.57% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 7 | 7 | 54 | 378 | 6s | 364.50 | 1.17× | -16.67% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 8 | 8 | 48 | 384 | 5s | 437.40 | 1.40× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 6s | 364.50 | 1.17× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 20s | 109.35 | 0.35× | -75.00% | — | — | — | — |

</details>

<a id="detector-shape-data-cross-edge-contour"></a>
<details>
<summary><strong>cross_edge_contour</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 4m 18s | 25.43 | 1.00× | -72.87% | 142.1 | 270.3 | 37.4% | 18.6 GiB |
| 192t — rh8-al321 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 12s | 91.14 | 3.58× | -2.78% | 972.7 | 1008.8 | 95.3% | 17.9 GiB |
| **192t — rh8-al321 (192 vCPU)** | 7 | 7 | 54 | 378 | 1m 10s | 93.74 | 3.69× | 0.00% | 1251.6 | 1251.6 | 92.7% | 17.5 GiB |
| 192t — rh8-al321 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 10s | 93.74 | 3.69× | 0.00% | 1904.2 | 1904.2 | 88.9% | 17.8 GiB |
| 192t — rh8-al321 (192 vCPU) | 9 | 9 | 42 | 378 | 1m 11s | 92.42 | 3.63× | -1.41% | 991.8 | 991.8 | 93.2% | 18.0 GiB |
| 192t — rh8-al321 (192 vCPU) | 10 | 10 | 38 | 380 | 1m 12s | 91.14 | 3.58× | -2.78% | 1072.3 | 1072.3 | 93.2% | 18.1 GiB |
| 192t — rh8-al321 (192 vCPU) | 64 | 64 | 6 | 384 | 2m 9s | 50.87 | 2.00× | -45.74% | 1840.6 | 2486.0 | 85.3% | 26.4 GiB |

</details>

<a id="detector-shape-data-distance-transform"></a>
<details>
<summary><strong>distance_transform</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al318 (192 vCPU)** | 1 | 1 | 384 | 384 | 30s | 72.90 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 30s | 72.90 | 1.00× | 0.00% | 380.5 | 380.5 | 32.5% | 11.2 GiB |

</details>

<a id="detector-shape-data-distance-transform-rect"></a>
<details>
<summary><strong>distance_transform_rect</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 3s | 243.00 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 3 | 3 | 128 | 384 | 3s | 243.00 | 1.00× | 0.00% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 5 | 5 | 76 | 380 | 3s | 243.00 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 6 | 6 | 64 | 384 | 4s | 182.25 | 0.75× | -25.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 5s | 145.80 | 0.60× | -40.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 21s | 34.71 | 0.14× | -85.71% | — | — | — | — |

</details>

<a id="detector-shape-data-edge-contour"></a>
<details>
<summary><strong>edge_contour</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 8m 33s | 25.58 | 1.00× | -85.96% | 12.8 | 14.7 | 6.9% | 29.5 GiB |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 38s | 133.91 | 5.23× | -26.53% | 543.9 | 741.2 | 71.3% | 30.7 GiB |
| 192t — rh8-al323 (192 vCPU) | 19 | 19 | 20 | 380 | 1m 14s | 177.34 | 6.93× | -2.70% | 795.3 | 795.3 | 88.2% | 33.5 GiB |
| **192t — rh8-al323 (192 vCPU)** | 20 | 20 | 19 | 380 | 1m 12s | 182.26 | 7.12× | 0.00% | 703.5 | 703.5 | 87.8% | 34.0 GiB |
| 192t — rh8-al323 (192 vCPU) | 21 | 21 | 18 | 378 | 1m 13s | 179.77 | 7.03× | -1.37% | 762.3 | 762.3 | 95.7% | 34.4 GiB |
| 192t — rh8-al323 (192 vCPU) | 22 | 22 | 17 | 374 | 1m 13s | 179.77 | 7.03× | -1.37% | 655.1 | 710.6 | 89.3% | 33.7 GiB |
| 192t — rh8-al323 (192 vCPU) | 23 | 23 | 16 | 368 | 1m 13s | 179.77 | 7.03× | -1.37% | 408.9 | 408.9 | 68.0% | 33.7 GiB |
| 192t — rh8-al323 (192 vCPU) | 24 | 24 | 16 | 384 | 1m 14s | 177.34 | 6.93× | -2.70% | 725.2 | 725.2 | 87.3% | 34.8 GiB |
| 192t — rh8-al323 (192 vCPU) | 64 | 64 | 6 | 384 | 1m 19s | 166.11 | 6.49× | -8.86% | 384.2 | 384.2 | 38.1% | 38.9 GiB |

</details>

<a id="detector-shape-data-grabcut"></a>
<details>
<summary><strong>grabcut</strong></summary>

**Search method(s):** `adaptive, exhaustive, powers-of-2`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **e7k — rh8-al97 (96 vCPU)** | 1 | 1 | 192 | 192 | 1h 54m | 1.92 | 1.00× | -0.29% | 232.1 | 258.1 | 97.2% | 53.1 GiB |
| **192t — rh8-al325 (192 vCPU)** | 1 | 1 | 384 | 384 | 45m 52s | 4.77 | 1.00× | 0.00% | 465.3 | 518.7 | 91.4% | 69.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 2 | 2 | 96 | 192 | 1h 53m 40s | 1.92 | 1.00× | 0.00% | 281.1 | 317.0 | 98.3% | 53.4 GiB |
| **192t — rh8-al320 (192 vCPU)** | 2 | 2 | 192 | 384 | 45m 30s | 4.81 | — | 0.00% | 581.1 | 641.2 | 95.8% | 74.2 GiB |
| 192t — rh8-al325 (192 vCPU) | 3 | 3 | 128 | 384 | 46m 32s | 4.70 | 0.99× | -1.43% | 676.4 | 745.0 | 95.5% | 88.3 GiB |
| e7k — rh8-al97 (96 vCPU) | 4 | 4 | 48 | 192 | 1h 57m 14s | 1.87 | 0.97× | -3.04% | 321.1 | 377.9 | 99.3% | 53.9 GiB |
| 192t — rh8-al325 (192 vCPU) | 4 | 4 | 96 | 384 | 48m 18s | 4.53 | 0.95× | -5.04% | 779.8 | 874.1 | 96.8% | 82.2 GiB |
| 192t — rh8-al325 (192 vCPU) | 5 | 5 | 76 | 380 | 50m 34s | 4.32 | 0.91× | -9.29% | 830.7 | 939.7 | 97.7% | 88.7 GiB |
| e7k — rh8-al97 (96 vCPU) | 8 | 8 | 24 | 192 | 1h 57m 47s | 1.86 | 0.97× | -3.50% | 328.4 | 420.9 | 99.2% | 54.3 GiB |
| 192t — rh8-al325 (192 vCPU) | 8 | 8 | 48 | 384 | 56m 4s | 3.90 | 0.82× | -18.19% | 976.4 | 1132.0 | 98.6% | 86.4 GiB |
| e7k — rh8-al97 (96 vCPU) | 16 | 16 | 12 | 192 | 1h 58m 17s | 1.85 | 0.96× | -3.90% | 343.3 | 435.7 | 99.3% | 54.9 GiB |
| e7k — rh8-al97 (96 vCPU) | 49 | 49 | 3 | 147 | 2h 53s | 1.81 | 0.94× | -5.97% | 316.9 | 407.2 | 98.7% | 49.1 GiB |

</details>

<a id="detector-shape-data-gradient-vote"></a>
<details>
<summary><strong>gradient_vote</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al325 (192 vCPU) | 1 | 1 | 384 | 384 | 30s | 218.73 | 1.00× | -70.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 7 | 7 | 54 | 378 | 12s | 546.83 | 2.50× | -25.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 8 | 8 | 48 | 384 | 10s | 656.20 | 3.00× | -10.00% | 331.5 | 331.5 | 27.5% | 10.7 GiB |
| **192t — rh8-al325 (192 vCPU)** | 9 | 9 | 42 | 378 | 9s | 729.11 | 3.33× | 0.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 10 | 10 | 38 | 380 | 9s | 729.11 | 3.33× | 0.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 11 | 11 | 34 | 374 | 10s | 656.20 | 3.00× | -10.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 64 | 64 | 6 | 384 | 16s | 410.12 | 1.88× | -43.75% | — | — | — | — |

</details>

<a id="detector-shape-data-hough"></a>
<details>
<summary><strong>hough</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al324 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 37s | 22.56 | 1.00× | -10.31% | 209.0 | 209.0 | 87.2% | 27.4 GiB |
| 192t — rh8-al324 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 31s | 24.04 | 1.07× | -4.40% | 513.9 | 549.5 | 96.0% | 28.8 GiB |
| 192t — rh8-al324 (192 vCPU) | 7 | 7 | 54 | 378 | 1m 31s | 24.04 | 1.07× | -4.40% | 557.6 | 559.4 | 96.0% | 29.1 GiB |
| 192t — rh8-al324 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 30s | 24.31 | 1.08× | -3.33% | 602.3 | 602.3 | 88.6% | 29.5 GiB |
| 192t — rh8-al324 (192 vCPU) | 9 | 9 | 42 | 378 | 1m 30s | 24.31 | 1.08× | -3.33% | 532.6 | 532.6 | 92.1% | 29.0 GiB |
| 192t — rh8-al324 (192 vCPU) | 10 | 10 | 38 | 380 | 1m 29s | 24.58 | 1.09× | -2.25% | 560.5 | 560.5 | 92.1% | 29.4 GiB |
| 192t — rh8-al324 (192 vCPU) | 11 | 11 | 34 | 374 | 1m 29s | 24.58 | 1.09× | -2.25% | 617.0 | 666.1 | 95.8% | 29.1 GiB |
| 192t — rh8-al324 (192 vCPU) | 12 | 12 | 32 | 384 | 1m 29s | 24.58 | 1.09× | -2.25% | 670.0 | 670.0 | 91.8% | 29.8 GiB |
| 192t — rh8-al324 (192 vCPU) | 13 | 13 | 29 | 377 | 1m 29s | 24.58 | 1.09× | -2.25% | 634.9 | 647.8 | 95.1% | 29.8 GiB |
| 192t — rh8-al324 (192 vCPU) | 14 | 14 | 27 | 378 | 1m 29s | 24.58 | 1.09× | -2.25% | 599.5 | 599.5 | 91.6% | 29.9 GiB |
| 192t — rh8-al324 (192 vCPU) | 15 | 15 | 25 | 375 | 1m 30s | 24.31 | 1.08× | -3.33% | 576.3 | 631.9 | 95.8% | 30.6 GiB |
| 192t — rh8-al324 (192 vCPU) | 16 | 16 | 24 | 384 | 1m 29s | 24.58 | 1.09× | -2.25% | 641.7 | 641.7 | 91.4% | 31.1 GiB |
| 192t — rh8-al324 (192 vCPU) | 17 | 17 | 22 | 374 | 1m 29s | 24.58 | 1.09× | -2.25% | 658.3 | 672.6 | 95.6% | 31.4 GiB |
| 192t — rh8-al324 (192 vCPU) | 18 | 18 | 21 | 378 | 1m 28s | 24.86 | 1.10× | -1.14% | 666.9 | 666.9 | 91.2% | 31.0 GiB |
| 192t — rh8-al324 (192 vCPU) | 19 | 19 | 20 | 380 | 1m 29s | 24.58 | 1.09× | -2.25% | 689.3 | 789.5 | 94.9% | 31.7 GiB |
| 192t — rh8-al324 (192 vCPU) | 20 | 20 | 19 | 380 | 1m 29s | 24.58 | 1.09× | -2.25% | 693.0 | 693.0 | 92.3% | 31.0 GiB |
| 192t — rh8-al324 (192 vCPU) | 21 | 21 | 18 | 378 | 1m 29s | 24.58 | 1.09× | -2.25% | 610.0 | 611.0 | 93.3% | 31.7 GiB |
| 192t — rh8-al324 (192 vCPU) | 22 | 22 | 17 | 374 | 1m 27s | 25.15 | 1.11× | 0.00% | 695.8 | 695.8 | 94.3% | 31.4 GiB |
| **192t — rh8-al324 (192 vCPU)** | 23 | 23 | 16 | 368 | 1m 27s | 25.15 | 1.11× | 0.00% | 610.3 | 610.3 | 90.7% | 31.9 GiB |
| 192t — rh8-al324 (192 vCPU) | 24 | 24 | 16 | 384 | 1m 29s | 24.58 | 1.09× | -2.25% | 661.8 | 696.0 | 95.3% | 32.2 GiB |
| 192t — rh8-al324 (192 vCPU) | 64 | 64 | 6 | 384 | 1m 33s | 23.53 | 1.04× | -6.45% | 532.6 | 623.4 | 96.5% | 38.2 GiB |

</details>

<a id="detector-shape-data-joint-rectangle-vote"></a>
<details>
<summary><strong>joint_rectangle_vote</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 6m 33s | 5.56 | 1.00× | -92.62% | 8.7 | 22.4 | 2.1% | 16.1 GiB |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 50s | 43.74 | 7.86× | -42.00% | 247.5 | 247.5 | 16.4% | 18.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 21 | 21 | 18 | 378 | 30s | 72.90 | 13.10× | -3.33% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 22 | 22 | 17 | 374 | 29s | 75.41 | 13.55× | 0.00% | 533.6 | 533.6 | 66.5% | 11.3 GiB |
| **192t — rh8-al318 (192 vCPU)** | 23 | 23 | 16 | 368 | 29s | 75.41 | 13.55× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 24 | 24 | 16 | 384 | 30s | 72.90 | 13.10× | -3.33% | 646.5 | 646.5 | 65.6% | 11.3 GiB |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 39s | 56.08 | 10.08× | -25.64% | 589.3 | 589.3 | 33.1% | 11.7 GiB |

</details>

<a id="detector-shape-data-learned-page-mask"></a>
<details>
<summary><strong>learned_page_mask</strong></summary>

**Search method(s):** `adaptive, exhaustive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 19m 43s | 8.45 | 1.00× | -17.75% | 381.0 | 404.3 | 62.7% | 75.6 GiB |
| **192t — rh8-al319 (192 vCPU)** | 1 | 1 | 384 | 384 | 30s | 8.10 | 1.00× | 0.00% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 2 | 2 | 192 | 384 | 16m 41s | 9.99 | — | -2.80% | 412.5 | 452.0 | 78.5% | 72.3 GiB |
| 192t — rh8-al318 (192 vCPU) | 2 | 2 | 192 | 384 | 16m 40s | 10.00 | 1.18× | -2.70% | 419.5 | 446.8 | 77.6% | 75.1 GiB |
| 192t — rh8-al318 (192 vCPU) | 3 | 3 | 128 | 384 | 16m 19s | 10.21 | 1.21× | -0.61% | 481.0 | 528.9 | 82.9% | 72.2 GiB |
| 192t — rh8-al319 (192 vCPU) | 3 | 3 | 128 | 384 | 30s | 8.10 | 1.00× | 0.00% | 180.8 | 180.8 | 66.8% | 48.6 GiB |
| **192t — rh8-al318 (192 vCPU)** | 4 | 4 | 96 | 384 | 16m 13s | 10.28 | 1.22× | 0.00% | 523.1 | 578.0 | 87.2% | 73.5 GiB |
| 192t — rh8-al319 (192 vCPU) | 4 | 4 | 96 | 384 | 33s | 7.36 | 0.91× | -9.09% | 638.4 | 638.4 | 79.4% | 49.8 GiB |
| 192t — rh8-al318 (192 vCPU) | 5 | 5 | 76 | 380 | 16m 53s | 9.87 | 1.17× | -3.95% | 607.3 | 649.1 | 88.9% | 71.9 GiB |
| 192t — rh8-al319 (192 vCPU) | 5 | 5 | 76 | 380 | 36s | 6.75 | 0.83× | -16.67% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 6 | 6 | 64 | 384 | 17m 35s | 9.48 | 1.12× | -7.77% | 640.6 | 680.2 | 89.4% | 71.0 GiB |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 19m 35s | 8.51 | 1.01× | -17.19% | 801.9 | 872.2 | 89.6% | 74.3 GiB |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 48s | 5.06 | 0.62× | -37.50% | 1816.9 | 1816.9 | 67.1% | 48.2 GiB |
| 192t — rh8-al318 (192 vCPU) | 16 | 16 | 24 | 384 | 28m 9s | 5.92 | 0.70× | -42.39% | 1201.2 | 1317.4 | 92.0% | 74.6 GiB |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 2m 10s | 1.87 | 0.23× | -76.92% | 2031.1 | 2855.7 | 85.6% | 57.7 GiB |

</details>

<a id="detector-shape-data-lsd"></a>
<details>
<summary><strong>lsd</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 31s | 70.55 | 1.00× | -58.06% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 5 | 5 | 76 | 380 | 15s | 145.80 | 2.07× | -13.33% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 6 | 6 | 64 | 384 | 14s | 156.21 | 2.21× | -7.14% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 7 | 7 | 54 | 378 | 14s | 156.21 | 2.21× | -7.14% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 8 | 8 | 48 | 384 | 14s | 156.21 | 2.21× | -7.14% | 243.3 | 243.3 | 34.4% | 11.9 GiB |
| **192t — rh8-al321 (192 vCPU)** | 9 | 9 | 42 | 378 | 13s | 168.23 | 2.38× | 0.00% | 401.0 | 401.0 | 75.2% | 31.8 GiB |
| 192t — rh8-al321 (192 vCPU) | 10 | 10 | 38 | 380 | 14s | 156.21 | 2.21× | -7.14% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 64 | 64 | 6 | 384 | 22s | 99.41 | 1.41× | -40.91% | — | — | — | — |

</details>

<a id="detector-shape-data-polar-boundary-vote"></a>
<details>
<summary><strong>polar_boundary_vote</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 39s | 7.36 | 1.00× | -87.88% | 0.9 | 0.9 | 0.9% | 19.1 GiB |
| 192t — rh8-al318 (192 vCPU) | 7 | 7 | 54 | 378 | 19s | 38.37 | 5.21× | -36.84% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 17s | 42.88 | 5.82× | -29.41% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 9 | 9 | 42 | 378 | 15s | 48.60 | 6.60× | -20.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 10 | 10 | 38 | 380 | 14s | 52.07 | 7.07× | -14.29% | 77.7 | 77.7 | 8.1% | 18.4 GiB |
| 192t — rh8-al318 (192 vCPU) | 11 | 11 | 34 | 374 | 13s | 56.08 | 7.62× | -7.69% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 12 | 12 | 32 | 384 | 13s | 56.08 | 7.62× | -7.69% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 13 | 13 | 29 | 377 | 12s | 60.75 | 8.25× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 14 | 14 | 27 | 378 | 13s | 56.08 | 7.62× | -7.69% | 175.2 | 175.2 | 11.2% | 20.4 GiB |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 21s | 34.71 | 4.71× | -42.86% | 196.0 | 196.0 | 6.1% | 11.2 GiB |

</details>

<a id="detector-shape-data-radial-edge"></a>
<details>
<summary><strong>radial_edge</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 4m 20s | 25.24 | 1.00× | -92.69% | 7.8 | 12.5 | 3.6% | 23.4 GiB |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 45s | 145.82 | 5.78× | -57.78% | 292.9 | 292.9 | 27.0% | 23.3 GiB |
| 192t — rh8-al323 (192 vCPU) | 22 | 22 | 17 | 374 | 20s | 328.10 | 13.00× | -5.00% | 396.7 | 396.7 | 52.7% | 25.2 GiB |
| 192t — rh8-al323 (192 vCPU) | 23 | 23 | 16 | 368 | 19s | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 24 | 24 | 16 | 384 | 19s | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 25 | 25 | 15 | 375 | 19s | 345.37 | 13.68× | 0.00% | — | — | — | — |
| **192t — rh8-al323 (192 vCPU)** | 26 | 26 | 14 | 364 | 19s | 345.37 | 13.68× | 0.00% | 740.9 | 740.9 | 71.2% | 25.4 GiB |
| 192t — rh8-al323 (192 vCPU) | 27 | 27 | 14 | 378 | 19s | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 28 | 28 | 13 | 364 | 20s | 328.10 | 13.00× | -5.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 64 | 64 | 6 | 384 | 23s | 285.30 | 11.30× | -17.39% | — | — | — | — |

</details>

<a id="detector-shape-data-radon-boundary"></a>
<details>
<summary><strong>radon_boundary</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 32s | 22.78 | 1.00× | -59.38% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 4 | 4 | 96 | 384 | 20s | 36.45 | 1.60× | -35.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 5 | 5 | 76 | 380 | 13s | 56.08 | 2.46× | 0.00% | 628.0 | 628.0 | 56.9% | 25.1 GiB |
| 192t — rh8-al319 (192 vCPU) | 6 | 6 | 64 | 384 | 13s | 56.08 | 2.46× | 0.00% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 7 | 7 | 54 | 378 | 13s | 56.08 | 2.46× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 15s | 48.60 | 2.13× | -13.33% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 37s | 19.70 | 0.86× | -64.86% | 609.0 | 609.0 | 45.0% | 11.5 GiB |

</details>

<a id="detector-shape-data-ransac"></a>
<details>
<summary><strong>ransac</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 53s | 12.90 | 1.00× | -91.15% | 1.2 | 1.2 | 0.8% | 11.8 GiB |
| 192t — rh8-al321 (192 vCPU) | 8 | 8 | 48 | 384 | 15s | 97.20 | 7.53× | -33.33% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 22 | 22 | 17 | 374 | 11s | 132.55 | 10.27× | -9.09% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 23 | 23 | 16 | 368 | 10s | 145.80 | 11.30× | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 24 | 24 | 16 | 384 | 11s | 132.55 | 10.27× | -9.09% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 64 | 64 | 6 | 384 | 12s | 121.50 | 9.42× | -16.67% | 1.3 | 1.3 | 0.7% | 11.0 GiB |

</details>

<a id="detector-shape-data-star-convex"></a>
<details>
<summary><strong>star_convex</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 58s | 12.57 | 1.00× | -82.76% | 72.0 | 72.0 | 1.1% | 18.4 GiB |
| 192t — rh8-al319 (192 vCPU) | 6 | 6 | 64 | 384 | 13s | 56.08 | 4.46× | -23.08% | 41.0 | 41.0 | 10.6% | 13.7 GiB |
| 192t — rh8-al319 (192 vCPU) | 7 | 7 | 54 | 378 | 11s | 66.27 | 5.27× | -9.09% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 11s | 66.27 | 5.27× | -9.09% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 11s | 66.27 | 5.27× | -9.09% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 10 | 10 | 38 | 380 | 10s | 72.90 | 5.80× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 11 | 11 | 34 | 374 | 11s | 66.27 | 5.27× | -9.09% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 21s | 34.71 | 2.76× | -52.38% | — | — | — | — |

</details>

<a id="detector-shape-data-text-flow"></a>
<details>
<summary><strong>text_flow</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al319 (192 vCPU)** | 1 | 1 | 384 | 384 | 5s | 145.80 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 5s | 145.80 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 6s | 121.50 | 0.83× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 11 | 11 | 34 | 374 | 6s | 121.50 | 0.83× | -16.67% | 394.0 | 394.0 | 20.1% | 11.0 GiB |
| 192t — rh8-al319 (192 vCPU) | 14 | 14 | 27 | 378 | 6s | 121.50 | 0.83× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 23 | 23 | 16 | 368 | 9s | 81.00 | 0.56× | -44.44% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 23s | 31.70 | 0.22× | -78.26% | — | — | — | — |

</details>

<a id="detector-shape-data-whitespace-frame"></a>
<details>
<summary><strong>whitespace_frame</strong></summary>

**Search method(s):** `adaptive`

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Sets/s | Speedup | Δ from best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al318 (192 vCPU)** | 1 | 1 | 384 | 384 | 3s | 243.33 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 3 | 3 | 128 | 384 | 3s | 243.33 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 4 | 4 | 96 | 384 | 3s | 243.33 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 5 | 5 | 76 | 380 | 4s | 182.50 | 0.75× | -25.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 4s | 182.50 | 0.75× | -25.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 21s | 34.76 | 0.14× | -85.71% | — | — | — | — |

</details>

</details>

[↑ Back to Navigation](#table-of-contents)
