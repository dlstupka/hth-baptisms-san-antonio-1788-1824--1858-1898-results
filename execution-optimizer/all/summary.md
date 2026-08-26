### Execution optimizer summary

Detector: `all`  
This report coalesces compatible measurements from completed optimizer runs only.

<a id="table-of-contents"></a>

<details open>
<summary><strong>Navigation</strong></summary>

- [Preferred Detector Run Configuration](#preferred-detector-run-configuration)
- [Detector Run Profile Plot](#detector-run-profile-plot)
  - [adaptive_multi_scale_radial_edge](#detector-run-profile-adaptive-multi-scale-radial-edge)
  - [adaptive_radial_edge](#detector-run-profile-adaptive-radial-edge)
  - [amsre_bfq_spbv_pbg](#detector-run-profile-amsre-bfq-spbv-pbg)
  - [amsre_doc_ufcn_fusion](#detector-run-profile-amsre-doc-ufcn-fusion)
  - [border_energy](#detector-run-profile-border-energy)
  - [border_fusion_quad](#detector-run-profile-border-fusion-quad)
  - [components](#detector-run-profile-components)
  - [consensus_quad](#detector-run-profile-consensus-quad)
  - [contour](#detector-run-profile-contour)
  - [contour_components](#detector-run-profile-contour-components)
  - [contour_grabcut](#detector-run-profile-contour-grabcut)
  - [contour_projection](#detector-run-profile-contour-projection)
  - [contour_quad](#detector-run-profile-contour-quad)
  - [convex_hull](#detector-run-profile-convex-hull)
  - [cross_edge_contour](#detector-run-profile-cross-edge-contour)
  - [dhsegment_page_mask](#detector-run-profile-dhsegment-page-mask)
  - [distance_transform](#detector-run-profile-distance-transform)
  - [distance_transform_rect](#detector-run-profile-distance-transform-rect)
  - [doc_ufcn_page_mask](#detector-run-profile-doc-ufcn-page-mask)
  - [docextractor_page_mask](#detector-run-profile-docextractor-page-mask)
  - [edge_contour](#detector-run-profile-edge-contour)
  - [eynollah_page_mask](#detector-run-profile-eynollah-page-mask)
  - [grabcut](#detector-run-profile-grabcut)
  - [grabcut_contour](#detector-run-profile-grabcut-contour)
  - [gradient_vote](#detector-run-profile-gradient-vote)
  - [hough](#detector-run-profile-hough)
  - [joint_rectangle_vote](#detector-run-profile-joint-rectangle-vote)
  - [kraken_page_mask](#detector-run-profile-kraken-page-mask)
  - [learned_page_mask](#detector-run-profile-learned-page-mask)
  - [lsd](#detector-run-profile-lsd)
  - [mask_rcnn_page_mask](#detector-run-profile-mask-rcnn-page-mask)
  - [msre_bfq_spbv_pbg](#detector-run-profile-msre-bfq-spbv-pbg)
  - [multi_scale_radial_edge](#detector-run-profile-multi-scale-radial-edge)
  - [orli_page_mask](#detector-run-profile-orli-page-mask)
  - [page_background](#detector-run-profile-page-background)
  - [pagenet_page_mask](#detector-run-profile-pagenet-page-mask)
  - [polar_boundary_vote](#detector-run-profile-polar-boundary-vote)
  - [projective_gradient_vote](#detector-run-profile-projective-gradient-vote)
  - [radial_edge](#detector-run-profile-radial-edge)
  - [radon_boundary](#detector-run-profile-radon-boundary)
  - [ransac](#detector-run-profile-ransac)
  - [scantailor_page_frame](#detector-run-profile-scantailor-page-frame)
  - [segment_supported_polar_vote](#detector-run-profile-segment-supported-polar-vote)
  - [signed_polar_boundary_vote](#detector-run-profile-signed-polar-boundary-vote)
  - [star_convex](#detector-run-profile-star-convex)
  - [text_flow](#detector-run-profile-text-flow)
  - [whitespace_frame](#detector-run-profile-whitespace-frame)
- [Detector Pipeline-Thread Shape Optimization Data](#detector-pipeline-thread-shape-optimization-data)
  - [adaptive_multi_scale_radial_edge](#detector-shape-data-adaptive-multi-scale-radial-edge)
  - [adaptive_radial_edge](#detector-shape-data-adaptive-radial-edge)
  - [amsre_bfq_spbv_pbg](#detector-shape-data-amsre-bfq-spbv-pbg)
  - [amsre_doc_ufcn_fusion](#detector-shape-data-amsre-doc-ufcn-fusion)
  - [border_energy](#detector-shape-data-border-energy)
  - [border_fusion_quad](#detector-shape-data-border-fusion-quad)
  - [components](#detector-shape-data-components)
  - [consensus_quad](#detector-shape-data-consensus-quad)
  - [contour](#detector-shape-data-contour)
  - [contour_components](#detector-shape-data-contour-components)
  - [contour_grabcut](#detector-shape-data-contour-grabcut)
  - [contour_projection](#detector-shape-data-contour-projection)
  - [contour_quad](#detector-shape-data-contour-quad)
  - [convex_hull](#detector-shape-data-convex-hull)
  - [cross_edge_contour](#detector-shape-data-cross-edge-contour)
  - [dhsegment_page_mask](#detector-shape-data-dhsegment-page-mask)
  - [distance_transform](#detector-shape-data-distance-transform)
  - [distance_transform_rect](#detector-shape-data-distance-transform-rect)
  - [doc_ufcn_page_mask](#detector-shape-data-doc-ufcn-page-mask)
  - [docextractor_page_mask](#detector-shape-data-docextractor-page-mask)
  - [edge_contour](#detector-shape-data-edge-contour)
  - [eynollah_page_mask](#detector-shape-data-eynollah-page-mask)
  - [grabcut](#detector-shape-data-grabcut)
  - [grabcut_contour](#detector-shape-data-grabcut-contour)
  - [gradient_vote](#detector-shape-data-gradient-vote)
  - [hough](#detector-shape-data-hough)
  - [joint_rectangle_vote](#detector-shape-data-joint-rectangle-vote)
  - [kraken_page_mask](#detector-shape-data-kraken-page-mask)
  - [learned_page_mask](#detector-shape-data-learned-page-mask)
  - [lsd](#detector-shape-data-lsd)
  - [mask_rcnn_page_mask](#detector-shape-data-mask-rcnn-page-mask)
  - [msre_bfq_spbv_pbg](#detector-shape-data-msre-bfq-spbv-pbg)
  - [multi_scale_radial_edge](#detector-shape-data-multi-scale-radial-edge)
  - [orli_page_mask](#detector-shape-data-orli-page-mask)
  - [page_background](#detector-shape-data-page-background)
  - [pagenet_page_mask](#detector-shape-data-pagenet-page-mask)
  - [polar_boundary_vote](#detector-shape-data-polar-boundary-vote)
  - [projective_gradient_vote](#detector-shape-data-projective-gradient-vote)
  - [radial_edge](#detector-shape-data-radial-edge)
  - [radon_boundary](#detector-shape-data-radon-boundary)
  - [ransac](#detector-shape-data-ransac)
  - [scantailor_page_frame](#detector-shape-data-scantailor-page-frame)
  - [segment_supported_polar_vote](#detector-shape-data-segment-supported-polar-vote)
  - [signed_polar_boundary_vote](#detector-shape-data-signed-polar-boundary-vote)
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
| adaptive_multi_scale_radial_edge | 192t — rh8-al319 (192 vCPU) | — | — | — | — | 48 | 8 | 24p/16t, 48p/8t | legacy | — | 384 | 24.94 | 6m 41s | 2 |
| adaptive_radial_edge | 32t — rh8-s32 (32 vCPU) | — | — | — | — | 22 | 2 | 21p/3t, 22p/2t, 23p/2t, 24p/2t, 25p/2t, 26p/2t, 27p/2t | legacy | — | 44 | 74.57 | 1m 28s | 12 |
| amsre_bfq_spbv_pbg | 192t — rh8-al307 (192 vCPU) | — | — | — | — | 42 | 9 | 42p/9t, 43p/8t, 44p/8t, 45p/8t, 46p/8t, 47p/8t, 48p/8t | legacy | — | 378 | 10.60 | 1h 18m 54s | 12 |
| amsre_doc_ufcn_fusion | 192t — rh8-al307 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 1 | 384 | 1p/384t | adaptive | 3m 6s | 384 | 1.32 | 22s | 4 |
| amsre_doc_ufcn_fusion | 192t — rh8-al307 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 1 | 384 | 1p/384t | exhaustive | 2m 20s | 384 | 1.32 | 22s | 4 |
| amsre_doc_ufcn_fusion | 192t — rh8-al308 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 4 | 96 | 3p/128t, 4p/96t | exhaustive | 1m 19s | 384 | 2.62 | 1m 20s | 6 |
| amsre_doc_ufcn_fusion | 192t — rh8-al308 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 6047.3 GiB | 1 | 384 | 1p/384t | exhaustive | 2m 18s | 384 | 1.32 | 22s | 5 |
| amsre_doc_ufcn_fusion | 192t — rh8-al316 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 2897.3 GiB | 2 | 192 | 2p/192t | exhaustive | 3m 7s | 384 | 0.85 | 34s | 4 |
| amsre_doc_ufcn_fusion | 192t — rh8-al317 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 3023.3 GiB | 1 | 384 | 1p/384t | exhaustive | 2m 19s | 384 | 1.45 | 20s | 8 |
| amsre_doc_ufcn_fusion | 192t — rh8-al320 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 2 | 192 | 2p/192t | adaptive | 5m 6s | 384 | 0.97 | 30s | 4 |
| border_energy | 192t — rh8-al325 (192 vCPU) | — | — | — | — | 8 | 48 | 7p/54t, 8p/48t, 9p/42t | legacy | — | 384 | 84.13 | 1m 18s | 7 |
| border_fusion_quad | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 11 | 34 | 10p/38t, 11p/34t, 12p/32t, 13p/29t, 14p/27t, 15p/25t | legacy | — | 374 | 18.77 | 13s | 12 |
| components | 192t — rh8-al324 (192 vCPU) | — | — | — | — | 8 | 48 | 8p/48t | legacy | — | 384 | 596.45 | 33s | 5 |
| consensus_quad | 192t — rh8-al323 (192 vCPU) | — | — | — | — | 5 | 76 | 5p/76t, 6p/64t | legacy | — | 380 | 27.00 | 9s | 10 |
| contour | 192t — rh8-al319 (192 vCPU) | — | — | — | — | 7 | 54 | 2p/192t, 3p/128t, 4p/96t, 5p/76t, 6p/64t, 7p/54t, 8p/48t | legacy | — | 378 | 364.50 | 4s | 10 |
| contour_components | 32t — rh8-s32 (32 vCPU) | — | — | — | — | 9 | 7 | 8p/8t, 9p/7t, 10p/6t | legacy | — | 63 | 106.98 | 3m 4s | 7 |
| contour_grabcut | 192t — rh8-al320 (192 vCPU) | — | — | — | — | 1 | 384 | 1p/384t, 2p/192t | legacy | — | 384 | 4.93 | 22m 10s | 5 |
| contour_projection | 192t — rh8-al321 (192 vCPU) | — | — | — | — | 21 | 18 | 21p/18t | legacy | — | 378 | 49.71 | 2m 12s | 15 |
| contour_quad | 192t — rh8-al324 (192 vCPU) | — | — | — | — | 8 | 48 | 6p/64t, 7p/54t, 8p/48t, 9p/42t, 10p/38t | legacy | — | 384 | 146.81 | 2h 40s | 9 |
| convex_hull | 192t — rh8-al319 (192 vCPU) | — | — | — | — | 8 | 48 | 8p/48t | legacy | — | 384 | 437.40 | 5s | 5 |
| cross_edge_contour | 192t — rh8-al321 (192 vCPU) | — | — | — | — | 7 | 54 | 7p/54t, 8p/48t, 9p/42t | legacy | — | 378 | 93.74 | 1m 10s | 7 |
| dhsegment_page_mask | 192t — rh8-al321 (192 vCPU) | — | — | — | — | 207 | 1 | 192p/2t, 207p/1t, 215p/1t, 219p/1t, 220p/1t, 221p/1t, 222p/1t, 223p/1t | legacy | — | 207 | 11.85 | 14m 4s | 8 |
| distance_transform | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 1 | 384 | 1p/384t, 64p/6t | legacy | — | 384 | 72.90 | 30s | 2 |
| distance_transform_rect | 192t — rh8-al319 (192 vCPU) | — | — | — | — | 5 | 76 | 1p/384t, 3p/128t, 5p/76t | legacy | — | 380 | 243.00 | 3s | 6 |
| doc_ufcn_page_mask | 192t — rh8-al317 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 3023.3 GiB | 3 | 128 | 3p/128t | exhaustive | 39s | 384 | 32.00 | 8s | 4 |
| doc_ufcn_page_mask | 192t — rh8-al321 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 5 | 76 | 3p/128t, 4p/96t, 5p/76t, 6p/64t | exhaustive | 53s | 380 | 32.00 | 8s | 6 |
| doc_ufcn_page_mask | 192t — rh8-al328 (192 vCPU) | AMD EPYC 9655 96-Core Processor | 192 | 192 | 503.3 GiB | 5 | 76 | 5p/76t | adaptive | 2m 5s | 380 | 36.57 | 7s | 13 |
| docextractor_page_mask | 192t — rh8-al317 (192 vCPU) | — | — | — | — | 3 | 128 | 3p/128t | legacy | — | 384 | 9.90 | 10s | 5 |
| edge_contour | 192t — rh8-al323 (192 vCPU) | — | — | — | — | 20 | 19 | 20p/19t, 21p/18t, 22p/17t, 23p/16t | legacy | — | 380 | 182.26 | 1m 12s | 9 |
| eynollah_page_mask | 192t — rh8-al316 (192 vCPU) | — | — | — | — | 2 | 192 | 2p/192t | legacy | — | 384 | 6.75 | 12s | 5 |
| grabcut | 192t — rh8-al320 (192 vCPU) | — | — | — | — | 2 | 192 | 2p/192t | legacy | — | 384 | 4.81 | 45m 30s | 1 |
| grabcut_contour | 192t — rh8-al317 (192 vCPU) | — | — | — | — | 2 | 192 | 2p/192t | legacy | — | 384 | 3.97 | 6m 7s | 5 |
| gradient_vote | 192t — rh8-al325 (192 vCPU) | — | — | — | — | 9 | 42 | 9p/42t, 10p/38t | legacy | — | 378 | 729.11 | 9s | 7 |
| hough | 192t — rh8-al324 (192 vCPU) | — | — | — | — | 23 | 16 | 18p/21t, 22p/17t, 23p/16t | legacy | — | 368 | 25.15 | 1m 27s | 21 |
| joint_rectangle_vote | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 23 | 16 | 22p/17t, 23p/16t | legacy | — | 368 | 75.41 | 29s | 7 |
| kraken_page_mask | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 17 | 22 | 15p/25t, 16p/24t, 17p/22t, 18p/21t, 19p/20t, 20p/19t, 21p/18t, 22p/17t, 23p/16t | legacy | — | 374 | 2.75 | 1h 40s | 17 |
| learned_page_mask | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 4 | 96 | 3p/128t, 4p/96t | legacy | — | 384 | 10.29 | 16m 12s | 6 |
| lsd | 192t — rh8-al321 (192 vCPU) | — | — | — | — | 9 | 42 | 9p/42t | legacy | — | 378 | 168.23 | 13s | 8 |
| mask_rcnn_page_mask | 192t — rh8-al308 (192 vCPU) | — | — | — | — | 11 | 34 | 10p/38t, 11p/34t | legacy | — | 374 | 100.00 | 20s | 6 |
| msre_bfq_spbv_pbg | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 36 | 10 | 29p/13t, 30p/12t, 31p/12t, 32p/12t, 33p/11t, 34p/11t, 35p/10t, 36p/10t, 37p/10t, 38p/10t | legacy | — | 360 | 11.10 | 3m 17s | 15 |
| multi_scale_radial_edge | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 9 | 42 | 9p/42t | legacy | — | 378 | 60.83 | 12s | 5 |
| orli_page_mask | 192t — rh8-al316 (192 vCPU) | — | — | — | — | 12 | 32 | 12p/32t | legacy | — | 384 | 303.03 | 33s | 8 |
| page_background | 192t — rh8-al307 (192 vCPU) | — | — | — | — | 5 | 76 | 4p/96t, 5p/76t | legacy | — | 380 | 136.75 | 16s | 8 |
| pagenet_page_mask | 192t — rh8-al307 (192 vCPU) | — | — | — | — | 7 | 54 | 5p/76t, 6p/64t, 7p/54t, 8p/48t | legacy | — | 378 | 641.03 | 39s | 7 |
| polar_boundary_vote | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 13 | 29 | 13p/29t | legacy | — | 377 | 60.75 | 12s | 10 |
| projective_gradient_vote | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 6 | 64 | 6p/64t | legacy | — | 384 | 91.25 | 8s | 6 |
| radial_edge | 192t — rh8-al323 (192 vCPU) | — | — | — | — | 26 | 14 | 23p/16t, 24p/16t, 25p/15t, 26p/14t, 27p/14t | legacy | — | 364 | 345.37 | 19s | 10 |
| radon_boundary | 192t — rh8-al319 (192 vCPU) | — | — | — | — | 7 | 54 | 5p/76t, 6p/64t, 7p/54t | legacy | — | 378 | 56.08 | 13s | 7 |
| ransac | 192t — rh8-al321 (192 vCPU) | — | — | — | — | 23 | 16 | 23p/16t | legacy | — | 368 | 145.80 | 10s | 6 |
| scantailor_page_frame | 192t — rh8-al308 (192 vCPU) | — | — | — | — | 11 | 34 | 11p/34t | legacy | — | 374 | 16.55 | 29s | 8 |
| segment_supported_polar_vote | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 76 | 5 | 73p/5t, 74p/5t, 75p/5t, 76p/5t | legacy | — | 380 | 137.64 | 2m 23s | 9 |
| signed_polar_boundary_vote | 192t — rh8-al319 (192 vCPU) | — | — | — | — | 40 | 9 | 40p/9t | legacy | — | 360 | 87.48 | 25s | 9 |
| star_convex | 192t — rh8-al319 (192 vCPU) | — | — | — | — | 10 | 38 | 10p/38t | legacy | — | 380 | 72.90 | 10s | 8 |
| text_flow | 192t — rh8-al319 (192 vCPU) | — | — | — | — | 1 | 384 | 1p/384t, 8p/48t | legacy | — | 384 | 145.80 | 5s | 7 |
| whitespace_frame | 192t — rh8-al318 (192 vCPU) | — | — | — | — | 1 | 384 | 1p/384t, 3p/128t, 4p/96t | legacy | — | 384 | 243.33 | 3s | 6 |

**Search method legend:** `adaptive` = sparse wide-range search with local refinement around the measured peak and ≤2% preferred-shape boundaries; `powers-of-2` = logarithmic power-of-two pipeline sweep; `exhaustive` = every legal pipeline count in the requested range.

**Shape-prediction / optimizer coverage**

| Detector | Observed vCPU anchors | Prediction readiness | Prediction checks | Desired / missing optimization data |
|---|---|---|---|---|
| adaptive_multi_scale_radial_edge | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| adaptive_radial_edge | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| amsre_bfq_spbv_pbg | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| amsre_doc_ufcn_fusion | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| border_energy | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| border_fusion_quad | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| components | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| consensus_quad | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| contour | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| contour_components | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| contour_grabcut | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| contour_projection | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| contour_quad | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| convex_hull | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| cross_edge_contour | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| dhsegment_page_mask | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| distance_transform | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| distance_transform_rect | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| doc_ufcn_page_mask | 192 | low | 0 verified / 0 pending | missing: a second vCPU size to establish shape scaling |
| docextractor_page_mask | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| edge_contour | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| eynollah_page_mask | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| grabcut | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| grabcut_contour | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| gradient_vote | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| hough | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| joint_rectangle_vote | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| kraken_page_mask | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| learned_page_mask | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| lsd | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| mask_rcnn_page_mask | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| msre_bfq_spbv_pbg | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| multi_scale_radial_edge | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| orli_page_mask | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| page_background | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| pagenet_page_mask | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| polar_boundary_vote | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| projective_gradient_vote | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| radial_edge | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| radon_boundary | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| ransac | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| scantailor_page_frame | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| segment_supported_polar_vote | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| signed_polar_boundary_vote | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| star_convex | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| text_flow | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |
| whitespace_frame | none | none | 0 verified / 0 pending | missing: at least one completed optimizer run |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-run-profile-plot"></a>
<details open>
<summary><strong>2. Detector Run Profile Plot</strong></summary>

Compatible completed measurements are plotted by detector; thread count is annotated at each measured shape.

<a id="detector-run-profile-adaptive-multi-scale-radial-edge"></a>
<details>
<summary><strong>adaptive_multi_scale_radial_edge</strong></summary>

**Search method(s):** `legacy`

![adaptive_multi_scale_radial_edge Detector Run Profile Plot](profiles/adaptive_multi_scale_radial_edge.svg)

</details>

<a id="detector-run-profile-adaptive-radial-edge"></a>
<details>
<summary><strong>adaptive_radial_edge</strong></summary>

**Search method(s):** `legacy`

![adaptive_radial_edge Detector Run Profile Plot](profiles/adaptive_radial_edge.svg)

</details>

<a id="detector-run-profile-amsre-bfq-spbv-pbg"></a>
<details>
<summary><strong>amsre_bfq_spbv_pbg</strong></summary>

**Search method(s):** `legacy`

![amsre_bfq_spbv_pbg Detector Run Profile Plot](profiles/amsre_bfq_spbv_pbg.svg)

</details>

<a id="detector-run-profile-amsre-doc-ufcn-fusion"></a>
<details>
<summary><strong>amsre_doc_ufcn_fusion</strong></summary>

**Search method(s):** `adaptive, exhaustive`

![amsre_doc_ufcn_fusion Detector Run Profile Plot](profiles/amsre_doc_ufcn_fusion.svg)

</details>

<a id="detector-run-profile-border-energy"></a>
<details>
<summary><strong>border_energy</strong></summary>

**Search method(s):** `legacy`

![border_energy Detector Run Profile Plot](profiles/border_energy.svg)

</details>

<a id="detector-run-profile-border-fusion-quad"></a>
<details>
<summary><strong>border_fusion_quad</strong></summary>

**Search method(s):** `legacy`

![border_fusion_quad Detector Run Profile Plot](profiles/border_fusion_quad.svg)

</details>

<a id="detector-run-profile-components"></a>
<details>
<summary><strong>components</strong></summary>

**Search method(s):** `legacy`

![components Detector Run Profile Plot](profiles/components.svg)

</details>

<a id="detector-run-profile-consensus-quad"></a>
<details>
<summary><strong>consensus_quad</strong></summary>

**Search method(s):** `legacy`

![consensus_quad Detector Run Profile Plot](profiles/consensus_quad.svg)

</details>

<a id="detector-run-profile-contour"></a>
<details>
<summary><strong>contour</strong></summary>

**Search method(s):** `legacy`

![contour Detector Run Profile Plot](profiles/contour.svg)

</details>

<a id="detector-run-profile-contour-components"></a>
<details>
<summary><strong>contour_components</strong></summary>

**Search method(s):** `legacy`

![contour_components Detector Run Profile Plot](profiles/contour_components.svg)

</details>

<a id="detector-run-profile-contour-grabcut"></a>
<details>
<summary><strong>contour_grabcut</strong></summary>

**Search method(s):** `legacy`

![contour_grabcut Detector Run Profile Plot](profiles/contour_grabcut.svg)

</details>

<a id="detector-run-profile-contour-projection"></a>
<details>
<summary><strong>contour_projection</strong></summary>

**Search method(s):** `legacy`

![contour_projection Detector Run Profile Plot](profiles/contour_projection.svg)

</details>

<a id="detector-run-profile-contour-quad"></a>
<details>
<summary><strong>contour_quad</strong></summary>

**Search method(s):** `legacy`

![contour_quad Detector Run Profile Plot](profiles/contour_quad.svg)

</details>

<a id="detector-run-profile-convex-hull"></a>
<details>
<summary><strong>convex_hull</strong></summary>

**Search method(s):** `legacy`

![convex_hull Detector Run Profile Plot](profiles/convex_hull.svg)

</details>

<a id="detector-run-profile-cross-edge-contour"></a>
<details>
<summary><strong>cross_edge_contour</strong></summary>

**Search method(s):** `legacy`

![cross_edge_contour Detector Run Profile Plot](profiles/cross_edge_contour.svg)

</details>

<a id="detector-run-profile-dhsegment-page-mask"></a>
<details>
<summary><strong>dhsegment_page_mask</strong></summary>

**Search method(s):** `legacy`

![dhsegment_page_mask Detector Run Profile Plot](profiles/dhsegment_page_mask.svg)

</details>

<a id="detector-run-profile-distance-transform"></a>
<details>
<summary><strong>distance_transform</strong></summary>

**Search method(s):** `legacy`

![distance_transform Detector Run Profile Plot](profiles/distance_transform.svg)

</details>

<a id="detector-run-profile-distance-transform-rect"></a>
<details>
<summary><strong>distance_transform_rect</strong></summary>

**Search method(s):** `legacy`

![distance_transform_rect Detector Run Profile Plot](profiles/distance_transform_rect.svg)

</details>

<a id="detector-run-profile-doc-ufcn-page-mask"></a>
<details>
<summary><strong>doc_ufcn_page_mask</strong></summary>

**Search method(s):** `adaptive, exhaustive`

![doc_ufcn_page_mask Detector Run Profile Plot](profiles/doc_ufcn_page_mask.svg)

</details>

<a id="detector-run-profile-docextractor-page-mask"></a>
<details>
<summary><strong>docextractor_page_mask</strong></summary>

**Search method(s):** `legacy`

![docextractor_page_mask Detector Run Profile Plot](profiles/docextractor_page_mask.svg)

</details>

<a id="detector-run-profile-edge-contour"></a>
<details>
<summary><strong>edge_contour</strong></summary>

**Search method(s):** `legacy`

![edge_contour Detector Run Profile Plot](profiles/edge_contour.svg)

</details>

<a id="detector-run-profile-eynollah-page-mask"></a>
<details>
<summary><strong>eynollah_page_mask</strong></summary>

**Search method(s):** `legacy`

![eynollah_page_mask Detector Run Profile Plot](profiles/eynollah_page_mask.svg)

</details>

<a id="detector-run-profile-grabcut"></a>
<details>
<summary><strong>grabcut</strong></summary>

**Search method(s):** `legacy`

![grabcut Detector Run Profile Plot](profiles/grabcut.svg)

</details>

<a id="detector-run-profile-grabcut-contour"></a>
<details>
<summary><strong>grabcut_contour</strong></summary>

**Search method(s):** `legacy`

![grabcut_contour Detector Run Profile Plot](profiles/grabcut_contour.svg)

</details>

<a id="detector-run-profile-gradient-vote"></a>
<details>
<summary><strong>gradient_vote</strong></summary>

**Search method(s):** `legacy`

![gradient_vote Detector Run Profile Plot](profiles/gradient_vote.svg)

</details>

<a id="detector-run-profile-hough"></a>
<details>
<summary><strong>hough</strong></summary>

**Search method(s):** `legacy`

![hough Detector Run Profile Plot](profiles/hough.svg)

</details>

<a id="detector-run-profile-joint-rectangle-vote"></a>
<details>
<summary><strong>joint_rectangle_vote</strong></summary>

**Search method(s):** `legacy`

![joint_rectangle_vote Detector Run Profile Plot](profiles/joint_rectangle_vote.svg)

</details>

<a id="detector-run-profile-kraken-page-mask"></a>
<details>
<summary><strong>kraken_page_mask</strong></summary>

**Search method(s):** `legacy`

![kraken_page_mask Detector Run Profile Plot](profiles/kraken_page_mask.svg)

</details>

<a id="detector-run-profile-learned-page-mask"></a>
<details>
<summary><strong>learned_page_mask</strong></summary>

**Search method(s):** `legacy`

![learned_page_mask Detector Run Profile Plot](profiles/learned_page_mask.svg)

</details>

<a id="detector-run-profile-lsd"></a>
<details>
<summary><strong>lsd</strong></summary>

**Search method(s):** `legacy`

![lsd Detector Run Profile Plot](profiles/lsd.svg)

</details>

<a id="detector-run-profile-mask-rcnn-page-mask"></a>
<details>
<summary><strong>mask_rcnn_page_mask</strong></summary>

**Search method(s):** `legacy`

![mask_rcnn_page_mask Detector Run Profile Plot](profiles/mask_rcnn_page_mask.svg)

</details>

<a id="detector-run-profile-msre-bfq-spbv-pbg"></a>
<details>
<summary><strong>msre_bfq_spbv_pbg</strong></summary>

**Search method(s):** `legacy`

![msre_bfq_spbv_pbg Detector Run Profile Plot](profiles/msre_bfq_spbv_pbg.svg)

</details>

<a id="detector-run-profile-multi-scale-radial-edge"></a>
<details>
<summary><strong>multi_scale_radial_edge</strong></summary>

**Search method(s):** `legacy`

![multi_scale_radial_edge Detector Run Profile Plot](profiles/multi_scale_radial_edge.svg)

</details>

<a id="detector-run-profile-orli-page-mask"></a>
<details>
<summary><strong>orli_page_mask</strong></summary>

**Search method(s):** `legacy`

![orli_page_mask Detector Run Profile Plot](profiles/orli_page_mask.svg)

</details>

<a id="detector-run-profile-page-background"></a>
<details>
<summary><strong>page_background</strong></summary>

**Search method(s):** `legacy`

![page_background Detector Run Profile Plot](profiles/page_background.svg)

</details>

<a id="detector-run-profile-pagenet-page-mask"></a>
<details>
<summary><strong>pagenet_page_mask</strong></summary>

**Search method(s):** `legacy`

![pagenet_page_mask Detector Run Profile Plot](profiles/pagenet_page_mask.svg)

</details>

<a id="detector-run-profile-polar-boundary-vote"></a>
<details>
<summary><strong>polar_boundary_vote</strong></summary>

**Search method(s):** `legacy`

![polar_boundary_vote Detector Run Profile Plot](profiles/polar_boundary_vote.svg)

</details>

<a id="detector-run-profile-projective-gradient-vote"></a>
<details>
<summary><strong>projective_gradient_vote</strong></summary>

**Search method(s):** `legacy`

![projective_gradient_vote Detector Run Profile Plot](profiles/projective_gradient_vote.svg)

</details>

<a id="detector-run-profile-radial-edge"></a>
<details>
<summary><strong>radial_edge</strong></summary>

**Search method(s):** `legacy`

![radial_edge Detector Run Profile Plot](profiles/radial_edge.svg)

</details>

<a id="detector-run-profile-radon-boundary"></a>
<details>
<summary><strong>radon_boundary</strong></summary>

**Search method(s):** `legacy`

![radon_boundary Detector Run Profile Plot](profiles/radon_boundary.svg)

</details>

<a id="detector-run-profile-ransac"></a>
<details>
<summary><strong>ransac</strong></summary>

**Search method(s):** `legacy`

![ransac Detector Run Profile Plot](profiles/ransac.svg)

</details>

<a id="detector-run-profile-scantailor-page-frame"></a>
<details>
<summary><strong>scantailor_page_frame</strong></summary>

**Search method(s):** `legacy`

![scantailor_page_frame Detector Run Profile Plot](profiles/scantailor_page_frame.svg)

</details>

<a id="detector-run-profile-segment-supported-polar-vote"></a>
<details>
<summary><strong>segment_supported_polar_vote</strong></summary>

**Search method(s):** `legacy`

![segment_supported_polar_vote Detector Run Profile Plot](profiles/segment_supported_polar_vote.svg)

</details>

<a id="detector-run-profile-signed-polar-boundary-vote"></a>
<details>
<summary><strong>signed_polar_boundary_vote</strong></summary>

**Search method(s):** `legacy`

![signed_polar_boundary_vote Detector Run Profile Plot](profiles/signed_polar_boundary_vote.svg)

</details>

<a id="detector-run-profile-star-convex"></a>
<details>
<summary><strong>star_convex</strong></summary>

**Search method(s):** `legacy`

![star_convex Detector Run Profile Plot](profiles/star_convex.svg)

</details>

<a id="detector-run-profile-text-flow"></a>
<details>
<summary><strong>text_flow</strong></summary>

**Search method(s):** `legacy`

![text_flow Detector Run Profile Plot](profiles/text_flow.svg)

</details>

<a id="detector-run-profile-whitespace-frame"></a>
<details>
<summary><strong>whitespace_frame</strong></summary>

**Search method(s):** `legacy`

![whitespace_frame Detector Run Profile Plot](profiles/whitespace_frame.svg)

</details>

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-pipeline-thread-shape-optimization-data"></a>
<details>
<summary><strong>3. Detector Pipeline-Thread Shape Optimization Data</strong></summary>

Coalesced compatible shape measurements from completed optimizer runs are shown below.

<a id="detector-shape-data-adaptive-multi-scale-radial-edge"></a>
<details>
<summary><strong>adaptive_multi_scale_radial_edge</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 24 | 24 | 16 | 384 | 6m 43s | — | 24.82 | — | -0.48% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 48 | 48 | 8 | 384 | 6m 41s | — | 24.94 | — | 0.00% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-adaptive-radial-edge"></a>
<details>
<summary><strong>adaptive_radial_edge</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 32t — rh8-s32 (32 vCPU) | 8 | 8 | 8 | 64 | 2m 58s | — | 36.87 | — | -50.56% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 16 | 16 | 4 | 64 | 1m 37s | — | 67.65 | — | -9.28% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 20 | 20 | 3 | 60 | 1m 30s | — | 72.91 | — | -2.23% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 21 | 21 | 3 | 63 | 1m 29s | — | 73.73 | — | -1.13% | — | — | — | — |
| **32t — rh8-s32 (32 vCPU)** | 22 | 22 | 2 | 44 | 1m 28s | — | 74.57 | — | 0.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 23 | 23 | 2 | 46 | 1m 29s | — | 73.73 | — | -1.13% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 24 | 24 | 2 | 48 | 1m 29s | — | 73.73 | — | -1.13% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 25 | 25 | 2 | 50 | 1m 29s | — | 73.73 | — | -1.13% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 26 | 26 | 2 | 52 | 1m 28s | — | 74.57 | — | 0.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 27 | 27 | 2 | 54 | 1m 29s | — | 73.73 | — | -1.13% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 28 | 28 | 2 | 56 | 1m 30s | — | 72.91 | — | -2.23% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 32 | 32 | 2 | 64 | 1m 31s | — | 72.11 | — | -3.30% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-amsre-bfq-spbv-pbg"></a>
<details>
<summary><strong>amsre_bfq_spbv_pbg</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al307 (192 vCPU) | 16 | 16 | 24 | 384 | 1h 59m 25s | — | 7.00 | — | -33.96% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 32 | 32 | 12 | 384 | 1h 22m 34s | — | 10.13 | — | -4.43% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 41 | 41 | 9 | 369 | 1h 20m 38s | — | 10.37 | — | -2.17% | — | — | — | — |
| **192t — rh8-al307 (192 vCPU)** | 42 | 42 | 9 | 378 | 1h 18m 54s | — | 10.60 | — | 0.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 43 | 43 | 8 | 344 | 1h 20m 26s | — | 10.40 | — | -1.89% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 44 | 44 | 8 | 352 | 1h 19m 51s | — | 10.47 | — | -1.23% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 45 | 45 | 8 | 360 | 1h 20m 9s | — | 10.43 | — | -1.60% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 46 | 46 | 8 | 368 | 1h 19m 1s | — | 10.58 | — | -0.19% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 47 | 47 | 8 | 376 | 1h 19m 45s | — | 10.49 | — | -1.04% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 48 | 48 | 8 | 384 | 1h 19m 18s | — | 10.55 | — | -0.47% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 49 | 49 | 7 | 343 | 1h 20m 44s | — | 10.36 | — | -2.26% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 64 | 64 | 6 | 384 | 1h 20m 42s | — | 10.36 | — | -2.26% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-amsre-doc-ufcn-fusion"></a>
<details>
<summary><strong>amsre_doc_ufcn_fusion</strong></summary>

**Search method(s):** `adaptive, exhaustive`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al307 (192 vCPU)** | 1 | 1 | 384 | 384 | 22s | 0s | 1.32 | 1.00× | 0.00% | — | — | — | — |
| **192t — rh8-al307 (192 vCPU)** | 1 | 1 | 384 | 384 | 22s | 0s | 1.32 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 1 | 1 | 384 | 384 | 2m 10s | 0s | 1.62 | 1.00× | -38.46% | 17.7 | 33.7 | 19.5% | 36.0 GiB |
| **192t — rh8-al308 (192 vCPU)** | 1 | 1 | 384 | 384 | 22s | 0s | 1.32 | 1.00× | -49.78% | — | — | — | — |
| **192t — rh8-al317 (192 vCPU)** | 1 | 1 | 384 | 384 | 20s | 0s | 1.45 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 2 | 2 | 192 | 384 | 31s | 0s | 0.94 | 0.71× | -29.03% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 2 | 2 | 192 | 384 | 33s | 0s | 0.88 | 0.67× | -33.33% | 267.9 | 267.9 | 83.7% | 26.3 GiB |
| 192t — rh8-al308 (192 vCPU) | 2 | 2 | 192 | 384 | 1m 31s | 0s | 2.31 | 1.43× | -12.09% | 77.2 | 77.2 | 44.9% | 36.2 GiB |
| 192t — rh8-al308 (192 vCPU) | 2 | 2 | 192 | 384 | 30s | 0s | 0.97 | 0.73× | -63.17% | — | — | — | — |
| **192t — rh8-al316 (192 vCPU)** | 2 | 2 | 192 | 384 | 34s | 0s | 0.85 | — | 0.00% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 2 | 2 | 192 | 384 | 30s | 0s | 0.97 | 0.67× | -33.33% | — | — | — | — |
| **192t — rh8-al320 (192 vCPU)** | 2 | 2 | 192 | 384 | 30s | 0s | 0.97 | — | 0.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 3 | 3 | 128 | 384 | 40s | 0s | 0.72 | 0.55× | -45.00% | 304.6 | 304.6 | 90.3% | 25.7 GiB |
| 192t — rh8-al307 (192 vCPU) | 3 | 3 | 128 | 384 | 39s | 0s | 0.74 | 0.56× | -43.59% | 82.0 | 82.0 | 45.8% | 23.5 GiB |
| 192t — rh8-al308 (192 vCPU) | 3 | 3 | 128 | 384 | 1m 21s | 0s | 2.59 | 1.60× | -1.23% | 176.2 | 182.5 | 51.0% | 37.5 GiB |
| 192t — rh8-al308 (192 vCPU) | 3 | 3 | 128 | 384 | 38s | 0s | 0.76 | 0.58× | -70.93% | 85.7 | 85.7 | 47.3% | 26.0 GiB |
| 192t — rh8-al316 (192 vCPU) | 3 | 3 | 128 | 384 | 42s | 0s | 0.69 | — | -19.05% | 162.2 | 162.2 | 66.8% | 18.1 GiB |
| 192t — rh8-al317 (192 vCPU) | 3 | 3 | 128 | 384 | 39s | 0s | 0.74 | 0.51× | -48.72% | 100.4 | 100.4 | 45.7% | 17.3 GiB |
| 192t — rh8-al320 (192 vCPU) | 3 | 3 | 128 | 384 | 39s | 0s | 0.74 | — | -23.08% | 414.1 | 414.1 | 92.4% | 8.7 GiB |
| 192t — rh8-al307 (192 vCPU) | 4 | 4 | 96 | 384 | 47s | 0s | 0.62 | 0.47× | -53.19% | 243.3 | 243.3 | 88.1% | 25.0 GiB |
| **192t — rh8-al308 (192 vCPU)** | 4 | 4 | 96 | 384 | 1m 20s | 0s | 2.62 | 1.62× | 0.00% | 267.5 | 267.5 | 74.5% | 37.7 GiB |
| 192t — rh8-al308 (192 vCPU) | 4 | 4 | 96 | 384 | 48s | 0s | 0.60 | 0.46× | -76.98% | 243.3 | 243.3 | 89.2% | 27.3 GiB |
| 192t — rh8-al316 (192 vCPU) | 4 | 4 | 96 | 384 | 50s | 0s | 0.58 | — | -32.00% | 261.8 | 261.8 | 85.4% | 18.6 GiB |
| 192t — rh8-al317 (192 vCPU) | 4 | 4 | 96 | 384 | 48s | 0s | 0.60 | 0.42× | -58.33% | 235.2 | 235.2 | 88.4% | 19.0 GiB |
| 192t — rh8-al308 (192 vCPU) | 5 | 5 | 76 | 380 | 1m 24s | 0s | 2.50 | 1.55× | -4.76% | 333.1 | 333.1 | 75.3% | 26.4 GiB |
| 192t — rh8-al316 (192 vCPU) | 5 | 5 | 76 | 380 | 1m 1s | 0s | 0.48 | — | -44.26% | 318.5 | 318.5 | 87.2% | 19.0 GiB |
| 192t — rh8-al308 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 30s | 0s | 2.33 | 1.44× | -11.11% | 324.4 | 354.9 | 84.3% | 38.8 GiB |
| 192t — rh8-al320 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 7s | 0s | 0.43 | — | -55.22% | 500.6 | 500.6 | 93.4% | 10.5 GiB |
| 192t — rh8-al308 (192 vCPU) | 7 | 7 | 54 | 378 | 1m 19s | 0s | 0.37 | 0.28× | -86.02% | 289.6 | 289.6 | 84.9% | 29.6 GiB |
| 192t — rh8-al307 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 29s | 0s | 0.33 | 0.25× | -75.28% | 207.0 | 207.0 | 57.2% | 29.2 GiB |
| 192t — rh8-al320 (192 vCPU) | 16 | 16 | 24 | 384 | 2m 48s | 0s | 0.17 | — | -82.14% | 361.9 | 488.8 | 90.9% | 15.5 GiB |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-border-energy"></a>
<details>
<summary><strong>border_energy</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al325 (192 vCPU) | 1 | 1 | 384 | 384 | 4m 23s | — | 24.95 | 1.00× | -70.34% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 25s | — | 77.20 | 3.09× | -8.24% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 7 | 7 | 54 | 378 | 1m 19s | — | 83.06 | 3.33× | -1.27% | — | — | — | — |
| **192t — rh8-al325 (192 vCPU)** | 8 | 8 | 48 | 384 | 1m 18s | — | 84.13 | 3.37× | 0.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 9 | 9 | 42 | 378 | 1m 19s | — | 83.06 | 3.33× | -1.27% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 10 | 10 | 38 | 380 | 1m 21s | — | 81.01 | 3.25× | -3.71% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 64 | 64 | 6 | 384 | 2m 21s | — | 46.54 | 1.87× | -44.68% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-border-fusion-quad"></a>
<details>
<summary><strong>border_fusion_quad</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 26s | — | 2.84 | 1.00× | -84.87% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 7 | 7 | 54 | 378 | 18s | — | 13.56 | 4.78× | -27.76% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 16s | — | 15.25 | 5.38× | -18.75% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 9 | 9 | 42 | 378 | 15s | — | 16.27 | 5.73× | -13.32% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 10 | 10 | 38 | 380 | 13s | — | 18.77 | 6.62× | 0.00% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 11 | 11 | 34 | 374 | 13s | — | 18.77 | 6.62× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 12 | 12 | 32 | 384 | 13s | — | 18.77 | 6.62× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 13 | 13 | 29 | 377 | 13s | — | 18.77 | 6.62× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 14 | 14 | 27 | 378 | 13s | — | 18.77 | 6.62× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 15 | 15 | 25 | 375 | 13s | — | 18.77 | 6.62× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 16 | 16 | 24 | 384 | 14s | — | 17.43 | 6.14× | -7.14% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 25s | — | 9.76 | 3.44× | -48.00% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-components"></a>
<details>
<summary><strong>components</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al324 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 5s | — | 302.82 | 1.00× | -49.23% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 7 | 7 | 54 | 378 | 34s | — | 578.91 | 1.91× | -2.94% | — | — | — | — |
| **192t — rh8-al324 (192 vCPU)** | 8 | 8 | 48 | 384 | 33s | — | 596.45 | 1.97× | 0.00% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 9 | 9 | 42 | 378 | 34s | — | 578.91 | 1.91× | -2.94% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 64 | 64 | 6 | 384 | 44s | — | 447.34 | 1.48× | -25.00% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-consensus-quad"></a>
<details>
<summary><strong>consensus_quad</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 21s | — | 11.57 | 1.00× | -57.15% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 4 | 4 | 96 | 384 | 10s | — | 24.30 | 2.10× | -10.00% | — | — | — | — |
| **192t — rh8-al323 (192 vCPU)** | 5 | 5 | 76 | 380 | 9s | — | 27.00 | 2.33× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 6 | 6 | 64 | 384 | 9s | — | 27.00 | 2.33× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 7 | 7 | 54 | 378 | 10s | — | 24.30 | 2.10× | -10.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 10s | — | 24.30 | 2.10× | -10.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 9 | 9 | 42 | 378 | 11s | — | 22.09 | 1.91× | -18.19% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 10 | 10 | 38 | 380 | 11s | — | 22.09 | 1.91× | -18.19% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 11 | 11 | 34 | 374 | 12s | — | 20.25 | 1.75× | -25.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 128 | 128 | 3 | 384 | 1m 2s | — | 3.92 | 0.34× | -85.48% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-contour"></a>
<details>
<summary><strong>contour</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 6s | — | 243.00 | 1.00× | -33.33% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 2 | 2 | 192 | 384 | 4s | — | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 3 | 3 | 128 | 384 | 4s | — | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 4 | 4 | 96 | 384 | 4s | — | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 5 | 5 | 76 | 380 | 4s | — | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 6 | 6 | 64 | 384 | 4s | — | 364.50 | 1.50× | 0.00% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 7 | 7 | 54 | 378 | 4s | — | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 4s | — | 364.50 | 1.50× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 5s | — | 291.60 | 1.20× | -20.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 32 | 32 | 12 | 384 | 12s | — | 121.50 | 0.50× | -66.67% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-contour-components"></a>
<details>
<summary><strong>contour_components</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 32t — rh8-s32 (32 vCPU) | 2 | 2 | 32 | 64 | 6m 29s | — | 50.60 | — | -52.70% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 7 | 7 | 9 | 63 | 3m 8s | — | 104.70 | — | -2.13% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 8 | 8 | 8 | 64 | 3m 6s | — | 105.83 | — | -1.07% | — | — | — | — |
| **32t — rh8-s32 (32 vCPU)** | 9 | 9 | 7 | 63 | 3m 4s | — | 106.98 | — | 0.00% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 10 | 10 | 6 | 60 | 3m 6s | — | 105.83 | — | -1.07% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 11 | 11 | 5 | 55 | 3m 9s | — | 104.15 | — | -2.65% | — | — | — | — |
| 32t — rh8-s32 (32 vCPU) | 32 | 32 | 2 | 64 | 3m 52s | — | 84.84 | — | -20.70% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-contour-grabcut"></a>
<details>
<summary><strong>contour_grabcut</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al320 (192 vCPU)** | 1 | 1 | 384 | 384 | 22m 10s | — | 4.93 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 2 | 2 | 192 | 384 | 22m 19s | — | 4.90 | 0.99× | -0.61% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 3 | 3 | 128 | 384 | 22m 56s | — | 4.77 | 0.97× | -3.25% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 11 | 11 | 34 | 374 | 30m 10s | — | 3.63 | 0.73× | -26.37% | — | — | — | — |
| 192t — rh8-al320 (192 vCPU) | 128 | 128 | 3 | 384 | 37m 9s | — | 2.94 | 0.60× | -40.37% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-contour-projection"></a>
<details>
<summary><strong>contour_projection</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 34m 26s | — | 3.18 | 1.00× | -93.60% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 10 | 10 | 38 | 380 | 3m 24s | — | 32.17 | 10.13× | -35.28% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 11 | 11 | 34 | 374 | 3m 2s | — | 36.05 | 11.35× | -27.48% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 12 | 12 | 32 | 384 | 2m 39s | — | 41.27 | 12.99× | -16.98% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 13 | 13 | 29 | 377 | 2m 31s | — | 43.46 | 13.68× | -12.57% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 14 | 14 | 27 | 378 | 2m 29s | — | 44.04 | 13.87× | -11.41% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 15 | 15 | 25 | 375 | 2m 24s | — | 45.57 | 14.35× | -8.33% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 16 | 16 | 24 | 384 | 2m 26s | — | 44.95 | 14.15× | -9.58% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 17 | 17 | 22 | 374 | 2m 18s | — | 47.55 | 14.97× | -4.35% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 18 | 18 | 21 | 378 | 2m 16s | — | 48.25 | 15.19× | -2.94% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 19 | 19 | 20 | 380 | 2m 15s | — | 48.61 | 15.30× | -2.21% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 20 | 20 | 19 | 380 | 2m 15s | — | 48.61 | 15.30× | -2.21% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 21 | 21 | 18 | 378 | 2m 12s | — | 49.71 | 15.65× | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 22 | 22 | 17 | 374 | 2m 15s | — | 48.61 | 15.30× | -2.21% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 128 | 128 | 3 | 384 | 3m 4s | — | 35.66 | 11.23× | -28.26% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-contour-quad"></a>
<details>
<summary><strong>contour_quad</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al324 (192 vCPU) | 1 | 1 | 384 | 384 | 7h 3m 20s | — | 41.85 | 1.00× | -71.49% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 5 | 5 | 76 | 380 | 2h 10m 13s | — | 136.04 | 3.25× | -7.34% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 6 | 6 | 64 | 384 | 2h 2m 31s | — | 144.59 | 3.46× | -1.51% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 7 | 7 | 54 | 378 | 2h 1m 25s | — | 145.90 | 3.49× | -0.62% | — | — | — | — |
| **192t — rh8-al324 (192 vCPU)** | 8 | 8 | 48 | 384 | 2h 40s | — | 146.81 | 3.51× | 0.00% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 9 | 9 | 42 | 378 | 2h 1m 28s | — | 145.84 | 3.49× | -0.66% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 10 | 10 | 38 | 380 | 2h 3m 7s | — | 143.89 | 3.44× | -1.99% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 11 | 11 | 34 | 374 | 2h 3m 56s | — | 142.94 | 3.42× | -2.64% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 128 | 128 | 3 | 384 | 3h 19m 3s | — | 89.00 | 2.13× | -39.38% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-convex-hull"></a>
<details>
<summary><strong>convex_hull</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 7s | — | 312.43 | 1.00× | -28.57% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 7 | 7 | 54 | 378 | 6s | — | 364.50 | 1.17× | -16.67% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 8 | 8 | 48 | 384 | 5s | — | 437.40 | 1.40× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 6s | — | 364.50 | 1.17× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 20s | — | 109.35 | 0.35× | -75.00% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-cross-edge-contour"></a>
<details>
<summary><strong>cross_edge_contour</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 4m 18s | — | 25.43 | 1.00× | -72.87% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 12s | — | 91.14 | 3.58× | -2.77% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 7 | 7 | 54 | 378 | 1m 10s | — | 93.74 | 3.69× | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 10s | — | 93.74 | 3.69× | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 9 | 9 | 42 | 378 | 1m 11s | — | 92.42 | 3.63× | -1.41% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 10 | 10 | 38 | 380 | 1m 12s | — | 91.14 | 3.58× | -2.77% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 64 | 64 | 6 | 384 | 2m 10s | — | 50.48 | 1.98× | -46.15% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-dhsegment-page-mask"></a>
<details>
<summary><strong>dhsegment_page_mask</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 192 | 192 | 2 | 384 | 14m 4s | — | 11.85 | — | 0.00% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 207 | 207 | 1 | 207 | 14m 4s | — | 11.85 | — | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 215 | 215 | 1 | 215 | 14m 6s | — | 11.82 | — | -0.25% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 219 | 219 | 1 | 219 | 14m 8s | — | 11.79 | — | -0.51% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 220 | 220 | 1 | 220 | 14m 10s | — | 11.76 | — | -0.76% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 221 | 221 | 1 | 221 | 14m 7s | — | 11.81 | — | -0.34% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 222 | 222 | 1 | 222 | 14m 8s | — | 11.79 | — | -0.51% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 223 | 223 | 1 | 223 | 14m 8s | — | 11.79 | — | -0.51% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-distance-transform"></a>
<details>
<summary><strong>distance_transform</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al318 (192 vCPU)** | 1 | 1 | 384 | 384 | 30s | — | 72.90 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 30s | — | 72.90 | 1.00× | 0.00% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-distance-transform-rect"></a>
<details>
<summary><strong>distance_transform_rect</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 3s | — | 243.00 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 3 | 3 | 128 | 384 | 3s | — | 243.00 | 1.00× | 0.00% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 5 | 5 | 76 | 380 | 3s | — | 243.00 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 6 | 6 | 64 | 384 | 4s | — | 182.25 | 0.75× | -25.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 5s | — | 145.80 | 0.60× | -40.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 21s | — | 34.71 | 0.14× | -85.72% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-doc-ufcn-page-mask"></a>
<details>
<summary><strong>doc_ufcn_page_mask</strong></summary>

**Search method(s):** `adaptive, exhaustive`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al328 (192 vCPU) | 1 | 1 | 96 | 96 | 11s | 1s | 23.27 | 1.00× | -36.36% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 1 | 1 | 384 | 384 | 10s | 1s | 25.60 | 1.00× | -20.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 10s | 1s | 25.60 | 1.00× | -20.00% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 2 | 2 | 192 | 384 | 9s | 5s | 28.44 | 1.11× | -11.11% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 2 | 2 | 192 | 384 | 9s | 5s | 28.44 | 1.11× | -11.11% | — | — | — | — |
| **192t — rh8-al317 (192 vCPU)** | 3 | 3 | 128 | 384 | 8s | 5s | 32.00 | 1.25× | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 3 | 3 | 128 | 384 | 8s | 5s | 32.00 | 1.25× | 0.00% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 4 | 4 | 96 | 384 | 10s | 7s | 25.60 | 1.00× | -20.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 4 | 4 | 96 | 384 | 8s | 5s | 32.00 | 1.25× | 0.00% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 4 | 4 | 96 | 384 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 5 | 5 | 76 | 380 | 8s | 5s | 32.00 | 1.25× | 0.00% | — | — | — | — |
| **192t — rh8-al328 (192 vCPU)** | 5 | 5 | 76 | 380 | 7s | 5s | 36.57 | 1.57× | 0.00% | 75.2 | 75.2 | 37.5% | 12.9 GiB |
| 192t — rh8-al321 (192 vCPU) | 6 | 6 | 64 | 384 | 8s | 5s | 32.00 | 1.25× | 0.00% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 6 | 6 | 64 | 384 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 7 | 7 | 54 | 378 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 8 | 8 | 48 | 384 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 9 | 9 | 42 | 378 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 10 | 10 | 38 | 380 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 11 | 11 | 34 | 374 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 12 | 12 | 32 | 384 | 8s | 5s | 32.00 | 1.38× | -12.50% | 82.3 | 82.3 | 41.1% | 7.7 GiB |
| 192t — rh8-al328 (192 vCPU) | 13 | 13 | 29 | 377 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 14 | 14 | 27 | 378 | 8s | 5s | 32.00 | 1.38× | -12.50% | — | — | — | — |
| 192t — rh8-al328 (192 vCPU) | 192 | 192 | 2 | 384 | 23s | 8s | 11.13 | 0.48× | -69.57% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-docextractor-page-mask"></a>
<details>
<summary><strong>docextractor_page_mask</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al317 (192 vCPU) | 2 | 2 | 192 | 384 | 21s | — | 4.71 | — | -52.42% | — | — | — | — |
| **192t — rh8-al317 (192 vCPU)** | 3 | 3 | 128 | 384 | 10s | — | 9.90 | — | 0.00% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 4 | 4 | 96 | 384 | 11s | — | 9.00 | — | -9.09% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 5 | 5 | 76 | 380 | 12s | — | 8.25 | — | -16.67% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 6 | 6 | 64 | 384 | 13s | — | 7.62 | — | -23.03% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-edge-contour"></a>
<details>
<summary><strong>edge_contour</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 8m 33s | — | 25.58 | 1.00× | -85.97% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 38s | — | 133.91 | 5.23× | -26.53% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 19 | 19 | 20 | 380 | 1m 14s | — | 177.34 | 6.93× | -2.70% | — | — | — | — |
| **192t — rh8-al323 (192 vCPU)** | 20 | 20 | 19 | 380 | 1m 12s | — | 182.26 | 7.12× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 21 | 21 | 18 | 378 | 1m 13s | — | 179.77 | 7.03× | -1.37% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 22 | 22 | 17 | 374 | 1m 13s | — | 179.77 | 7.03× | -1.37% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 23 | 23 | 16 | 368 | 1m 13s | — | 179.77 | 7.03× | -1.37% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 24 | 24 | 16 | 384 | 1m 14s | — | 177.34 | 6.93× | -2.70% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 64 | 64 | 6 | 384 | 1m 19s | — | 166.11 | 6.49× | -8.86% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-eynollah-page-mask"></a>
<details>
<summary><strong>eynollah_page_mask</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al316 (192 vCPU) | 1 | 1 | 384 | 384 | 29s | — | 2.79 | 1.00× | -58.67% | — | — | — | — |
| **192t — rh8-al316 (192 vCPU)** | 2 | 2 | 192 | 384 | 12s | — | 6.75 | 2.42× | 0.00% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 3 | 3 | 128 | 384 | 14s | — | 5.79 | 2.07× | -14.22% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 4 | 4 | 96 | 384 | 14s | — | 5.79 | 2.07× | -14.22% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 5 | 5 | 76 | 380 | 14s | — | 5.79 | 2.07× | -14.22% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-grabcut"></a>
<details>
<summary><strong>grabcut</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al320 (192 vCPU)** | 2 | 2 | 192 | 384 | 45m 30s | — | 4.81 | — | 0.00% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-grabcut-contour"></a>
<details>
<summary><strong>grabcut_contour</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al317 (192 vCPU) | 1 | 1 | 384 | 384 | 6m 38s | — | 3.66 | 1.00× | -7.81% | — | — | — | — |
| **192t — rh8-al317 (192 vCPU)** | 2 | 2 | 192 | 384 | 6m 7s | — | 3.97 | 1.08× | 0.00% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 3 | 3 | 128 | 384 | 6m 21s | — | 3.83 | 1.04× | -3.53% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 4 | 4 | 96 | 384 | 6m 37s | — | 3.67 | 1.00× | -7.56% | — | — | — | — |
| 192t — rh8-al317 (192 vCPU) | 5 | 5 | 76 | 380 | 6m 47s | — | 3.58 | 0.98× | -9.82% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-gradient-vote"></a>
<details>
<summary><strong>gradient_vote</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al325 (192 vCPU) | 1 | 1 | 384 | 384 | 30s | — | 218.73 | 1.00× | -70.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 7 | 7 | 54 | 378 | 12s | — | 546.83 | 2.50× | -25.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 8 | 8 | 48 | 384 | 10s | — | 656.20 | 3.00× | -10.00% | — | — | — | — |
| **192t — rh8-al325 (192 vCPU)** | 9 | 9 | 42 | 378 | 9s | — | 729.11 | 3.33× | 0.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 10 | 10 | 38 | 380 | 9s | — | 729.11 | 3.33× | 0.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 11 | 11 | 34 | 374 | 10s | — | 656.20 | 3.00× | -10.00% | — | — | — | — |
| 192t — rh8-al325 (192 vCPU) | 64 | 64 | 6 | 384 | 16s | — | 410.12 | 1.88× | -43.75% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-hough"></a>
<details>
<summary><strong>hough</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al324 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 37s | — | 22.56 | 1.00× | -10.30% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 6 | 6 | 64 | 384 | 1m 31s | — | 24.04 | 1.07× | -4.41% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 7 | 7 | 54 | 378 | 1m 31s | — | 24.04 | 1.07× | -4.41% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 30s | — | 24.31 | 1.08× | -3.34% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 9 | 9 | 42 | 378 | 1m 30s | — | 24.31 | 1.08× | -3.34% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 10 | 10 | 38 | 380 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 11 | 11 | 34 | 374 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 12 | 12 | 32 | 384 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 13 | 13 | 29 | 377 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 14 | 14 | 27 | 378 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 15 | 15 | 25 | 375 | 1m 30s | — | 24.31 | 1.08× | -3.34% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 16 | 16 | 24 | 384 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 17 | 17 | 22 | 374 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 18 | 18 | 21 | 378 | 1m 28s | — | 24.86 | 1.10× | -1.15% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 19 | 19 | 20 | 380 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 20 | 20 | 19 | 380 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 21 | 21 | 18 | 378 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 22 | 22 | 17 | 374 | 1m 27s | — | 25.15 | 1.11× | 0.00% | — | — | — | — |
| **192t — rh8-al324 (192 vCPU)** | 23 | 23 | 16 | 368 | 1m 27s | — | 25.15 | 1.11× | 0.00% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 24 | 24 | 16 | 384 | 1m 29s | — | 24.58 | 1.09× | -2.27% | — | — | — | — |
| 192t — rh8-al324 (192 vCPU) | 64 | 64 | 6 | 384 | 1m 33s | — | 23.53 | 1.04× | -6.44% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-joint-rectangle-vote"></a>
<details>
<summary><strong>joint_rectangle_vote</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 6m 33s | — | 5.56 | 1.00× | -92.63% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 50s | — | 43.74 | 7.86× | -42.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 21 | 21 | 18 | 378 | 30s | — | 72.90 | 13.10× | -3.33% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 22 | 22 | 17 | 374 | 29s | — | 75.41 | 13.55× | 0.00% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 23 | 23 | 16 | 368 | 29s | — | 75.41 | 13.55× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 24 | 24 | 16 | 384 | 30s | — | 72.90 | 13.10× | -3.33% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 39s | — | 56.08 | 10.08× | -25.63% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-kraken-page-mask"></a>
<details>
<summary><strong>kraken_page_mask</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 4 | 4 | 96 | 384 | 2h 2m 57s | — | 1.36 | — | -50.55% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 10 | 10 | 38 | 380 | 1h 8m 46s | — | 2.42 | — | -12.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 11 | 11 | 34 | 374 | 1h 5m 48s | — | 2.53 | — | -8.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 12 | 12 | 32 | 384 | 1h 5m 16s | — | 2.55 | — | -7.27% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 13 | 13 | 29 | 377 | 1h 3m 25s | — | 2.63 | — | -4.36% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 14 | 14 | 27 | 378 | 1h 2m 6s | — | 2.68 | — | -2.55% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 15 | 15 | 25 | 375 | 1h 1m 14s | — | 2.72 | — | -1.09% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 16 | 16 | 24 | 384 | 1h 1m 43s | — | 2.70 | — | -1.82% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 17 | 17 | 22 | 374 | 1h 40s | — | 2.75 | — | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 18 | 18 | 21 | 378 | 1h 1m 1s | — | 2.73 | — | -0.73% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 19 | 19 | 20 | 380 | 1h 1m 5s | — | 2.73 | — | -0.73% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 20 | 20 | 19 | 380 | 1h 1m 19s | — | 2.72 | — | -1.09% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 21 | 21 | 18 | 378 | 1h 1m 7s | — | 2.73 | — | -0.73% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 22 | 22 | 17 | 374 | 1h 1m 26s | — | 2.71 | — | -1.45% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 23 | 23 | 16 | 368 | 1h 1m 33s | — | 2.71 | — | -1.45% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 24 | 24 | 16 | 384 | 1h 3m 21s | — | 2.63 | — | -4.36% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 32 | 32 | 12 | 384 | 1h 9m 35s | — | 2.40 | — | -12.73% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-learned-page-mask"></a>
<details>
<summary><strong>learned_page_mask</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 19m 44s | — | 8.45 | 1.00× | -17.88% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 2 | 2 | 192 | 384 | 16m 41s | — | 9.99 | 1.18× | -2.92% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 3 | 3 | 128 | 384 | 16m 17s | — | 10.24 | 1.21× | -0.49% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 4 | 4 | 96 | 384 | 16m 12s | — | 10.29 | 1.22× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 5 | 5 | 76 | 380 | 16m 54s | — | 9.86 | 1.17× | -4.18% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 16 | 16 | 24 | 384 | 28m 12s | — | 5.91 | 0.70× | -42.57% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-lsd"></a>
<details>
<summary><strong>lsd</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 31s | — | 70.55 | 1.00× | -58.06% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 5 | 5 | 76 | 380 | 15s | — | 145.80 | 2.07× | -13.33% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 6 | 6 | 64 | 384 | 14s | — | 156.21 | 2.21× | -7.14% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 7 | 7 | 54 | 378 | 14s | — | 156.21 | 2.21× | -7.14% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 8 | 8 | 48 | 384 | 14s | — | 156.21 | 2.21× | -7.14% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 9 | 9 | 42 | 378 | 13s | — | 168.23 | 2.38× | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 10 | 10 | 38 | 380 | 14s | — | 156.21 | 2.21× | -7.14% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 64 | 64 | 6 | 384 | 22s | — | 99.41 | 1.41× | -40.91% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-mask-rcnn-page-mask"></a>
<details>
<summary><strong>mask_rcnn_page_mask</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al308 (192 vCPU) | 4 | 4 | 96 | 384 | 43s | — | 46.51 | — | -53.49% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 9 | 9 | 42 | 378 | 24s | — | 83.33 | — | -16.67% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 10 | 10 | 38 | 380 | 20s | — | 100.00 | — | 0.00% | — | — | — | — |
| **192t — rh8-al308 (192 vCPU)** | 11 | 11 | 34 | 374 | 20s | — | 100.00 | — | 0.00% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 12 | 12 | 32 | 384 | 21s | — | 95.24 | — | -4.76% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 32 | 32 | 12 | 384 | 37s | — | 54.05 | — | -45.95% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-msre-bfq-spbv-pbg"></a>
<details>
<summary><strong>msre_bfq_spbv_pbg</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 2 | 2 | 192 | 384 | 38m 24s | — | 0.95 | — | -91.44% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 14 | 14 | 27 | 378 | 5m 11s | — | 7.03 | — | -36.67% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 28 | 28 | 13 | 364 | 3m 22s | — | 10.83 | — | -2.43% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 29 | 29 | 13 | 377 | 3m 20s | — | 10.94 | — | -1.44% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 30 | 30 | 12 | 360 | 3m 21s | — | 10.88 | — | -1.98% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 31 | 31 | 12 | 372 | 3m 20s | — | 10.94 | — | -1.44% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 32 | 32 | 12 | 384 | 3m 18s | — | 11.05 | — | -0.45% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 33 | 33 | 11 | 363 | 3m 18s | — | 11.05 | — | -0.45% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 34 | 34 | 11 | 374 | 3m 17s | — | 11.10 | — | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 35 | 35 | 10 | 350 | 3m 20s | — | 10.94 | — | -1.44% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 36 | 36 | 10 | 360 | 3m 17s | — | 11.10 | — | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 37 | 37 | 10 | 370 | 3m 20s | — | 10.94 | — | -1.44% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 38 | 38 | 10 | 380 | 3m 19s | — | 10.99 | — | -0.99% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 39 | 39 | 9 | 351 | 3m 23s | — | 10.77 | — | -2.97% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 96 | 96 | 4 | 384 | 3m 48s | — | 9.59 | — | -13.60% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-multi-scale-radial-edge"></a>
<details>
<summary><strong>multi_scale_radial_edge</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 7s | — | 10.90 | 1.00× | -82.08% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 14s | — | 52.14 | 4.79× | -14.29% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 9 | 9 | 42 | 378 | 12s | — | 60.83 | 5.58× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 10 | 10 | 38 | 380 | 13s | — | 56.15 | 5.15× | -7.69% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 96 | 96 | 4 | 384 | 38s | — | 19.21 | 1.76× | -68.42% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-orli-page-mask"></a>
<details>
<summary><strong>orli_page_mask</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al316 (192 vCPU) | 8 | 8 | 48 | 384 | 3m 48s | — | 43.86 | — | -85.53% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 9 | 9 | 42 | 378 | 37s | — | 270.27 | — | -10.81% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 10 | 10 | 38 | 380 | 36s | — | 277.78 | — | -8.33% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 11 | 11 | 34 | 374 | 35s | — | 285.71 | — | -5.72% | — | — | — | — |
| **192t — rh8-al316 (192 vCPU)** | 12 | 12 | 32 | 384 | 33s | — | 303.03 | — | 0.00% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 13 | 13 | 29 | 377 | 34s | — | 294.12 | — | -2.94% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 14 | 14 | 27 | 378 | 34s | — | 294.12 | — | -2.94% | — | — | — | — |
| 192t — rh8-al316 (192 vCPU) | 15 | 15 | 25 | 375 | 34s | — | 294.12 | — | -2.94% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-page-background"></a>
<details>
<summary><strong>page_background</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al307 (192 vCPU) | 1 | 1 | 384 | 384 | 40s | — | 54.70 | 1.00× | -60.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 3 | 3 | 128 | 384 | 19s | — | 115.16 | 2.11× | -15.79% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 4 | 4 | 96 | 384 | 16s | — | 136.75 | 2.50× | 0.00% | — | — | — | — |
| **192t — rh8-al307 (192 vCPU)** | 5 | 5 | 76 | 380 | 16s | — | 136.75 | 2.50× | 0.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 6 | 6 | 64 | 384 | 17s | — | 128.71 | 2.35× | -5.88% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 7 | 7 | 54 | 378 | 18s | — | 121.56 | 2.22× | -11.11% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 8 | 8 | 48 | 384 | 18s | — | 121.56 | 2.22× | -11.11% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 64 | 64 | 6 | 384 | 37s | — | 59.14 | 1.08× | -56.75% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-pagenet-page-mask"></a>
<details>
<summary><strong>pagenet_page_mask</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al307 (192 vCPU) | 2 | 2 | 192 | 384 | 58s | — | 431.03 | — | -32.76% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 3 | 3 | 128 | 384 | 47s | — | 531.91 | — | -17.02% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 4 | 4 | 96 | 384 | 42s | — | 595.24 | — | -7.14% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 5 | 5 | 76 | 380 | 39s | — | 641.03 | — | 0.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 6 | 6 | 64 | 384 | 39s | — | 641.03 | — | 0.00% | — | — | — | — |
| **192t — rh8-al307 (192 vCPU)** | 7 | 7 | 54 | 378 | 39s | — | 641.03 | — | 0.00% | — | — | — | — |
| 192t — rh8-al307 (192 vCPU) | 8 | 8 | 48 | 384 | 39s | — | 641.03 | — | 0.00% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-polar-boundary-vote"></a>
<details>
<summary><strong>polar_boundary_vote</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 39s | — | 7.36 | 1.00× | -87.88% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 7 | 7 | 54 | 378 | 19s | — | 38.37 | 5.21× | -36.84% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 17s | — | 42.88 | 5.82× | -29.42% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 9 | 9 | 42 | 378 | 15s | — | 48.60 | 6.60× | -20.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 10 | 10 | 38 | 380 | 14s | — | 52.07 | 7.07× | -14.29% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 11 | 11 | 34 | 374 | 13s | — | 56.08 | 7.62× | -7.69% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 12 | 12 | 32 | 384 | 13s | — | 56.08 | 7.62× | -7.69% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 13 | 13 | 29 | 377 | 12s | — | 60.75 | 8.25× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 14 | 14 | 27 | 378 | 13s | — | 56.08 | 7.62× | -7.69% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 21s | — | 34.71 | 4.71× | -42.86% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-projective-gradient-vote"></a>
<details>
<summary><strong>projective_gradient_vote</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 1 | 1 | 384 | 384 | 24s | — | 30.42 | 1.00× | -66.66% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 5 | 5 | 76 | 380 | 9s | — | 81.11 | 2.67× | -11.11% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 6 | 6 | 64 | 384 | 8s | — | 91.25 | 3.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 7 | 7 | 54 | 378 | 9s | — | 81.11 | 2.67× | -11.11% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 10s | — | 73.00 | 2.40× | -20.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 27s | — | 27.04 | 0.89× | -70.37% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-radial-edge"></a>
<details>
<summary><strong>radial_edge</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al323 (192 vCPU) | 1 | 1 | 384 | 384 | 4m 20s | — | 25.24 | 1.00× | -92.69% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 8 | 8 | 48 | 384 | 45s | — | 145.82 | 5.78× | -57.78% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 22 | 22 | 17 | 374 | 20s | — | 328.10 | 13.00× | -5.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 23 | 23 | 16 | 368 | 19s | — | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 24 | 24 | 16 | 384 | 19s | — | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 25 | 25 | 15 | 375 | 19s | — | 345.37 | 13.68× | 0.00% | — | — | — | — |
| **192t — rh8-al323 (192 vCPU)** | 26 | 26 | 14 | 364 | 19s | — | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 27 | 27 | 14 | 378 | 19s | — | 345.37 | 13.68× | 0.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 28 | 28 | 13 | 364 | 20s | — | 328.10 | 13.00× | -5.00% | — | — | — | — |
| 192t — rh8-al323 (192 vCPU) | 64 | 64 | 6 | 384 | 23s | — | 285.30 | 11.30× | -17.39% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-radon-boundary"></a>
<details>
<summary><strong>radon_boundary</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 32s | — | 22.78 | 1.00× | -59.38% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 4 | 4 | 96 | 384 | 20s | — | 36.45 | 1.60× | -35.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 5 | 5 | 76 | 380 | 13s | — | 56.08 | 2.46× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 6 | 6 | 64 | 384 | 13s | — | 56.08 | 2.46× | 0.00% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 7 | 7 | 54 | 378 | 13s | — | 56.08 | 2.46× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 15s | — | 48.60 | 2.13× | -13.34% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 37s | — | 19.70 | 0.86× | -64.87% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-ransac"></a>
<details>
<summary><strong>ransac</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al321 (192 vCPU) | 1 | 1 | 384 | 384 | 1m 53s | — | 12.90 | 1.00× | -91.15% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 8 | 8 | 48 | 384 | 15s | — | 97.20 | 7.53× | -33.33% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 22 | 22 | 17 | 374 | 11s | — | 132.55 | 10.27× | -9.09% | — | — | — | — |
| **192t — rh8-al321 (192 vCPU)** | 23 | 23 | 16 | 368 | 10s | — | 145.80 | 11.30× | 0.00% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 24 | 24 | 16 | 384 | 11s | — | 132.55 | 10.27× | -9.09% | — | — | — | — |
| 192t — rh8-al321 (192 vCPU) | 64 | 64 | 6 | 384 | 12s | — | 121.50 | 9.42× | -16.67% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-scantailor-page-frame"></a>
<details>
<summary><strong>scantailor_page_frame</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al308 (192 vCPU) | 2 | 2 | 192 | 384 | 43s | — | 11.16 | — | -32.57% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 7 | 7 | 54 | 378 | 37s | — | 12.97 | — | -21.63% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 8 | 8 | 48 | 384 | 33s | — | 14.55 | — | -12.08% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 9 | 9 | 42 | 378 | 32s | — | 15.00 | — | -9.37% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 10 | 10 | 38 | 380 | 32s | — | 15.00 | — | -9.37% | — | — | — | — |
| **192t — rh8-al308 (192 vCPU)** | 11 | 11 | 34 | 374 | 29s | — | 16.55 | — | 0.00% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 12 | 12 | 32 | 384 | 31s | — | 15.48 | — | -6.47% | — | — | — | — |
| 192t — rh8-al308 (192 vCPU) | 32 | 32 | 12 | 384 | 47s | — | 10.21 | — | -38.31% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-segment-supported-polar-vote"></a>
<details>
<summary><strong>segment_supported_polar_vote</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al318 (192 vCPU) | 48 | 48 | 8 | 384 | 2m 40s | — | 123.02 | — | -10.62% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 72 | 72 | 5 | 360 | 2m 26s | — | 134.82 | — | -2.05% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 73 | 73 | 5 | 365 | 2m 25s | — | 135.74 | — | -1.38% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 74 | 74 | 5 | 370 | 2m 25s | — | 135.74 | — | -1.38% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 75 | 75 | 5 | 375 | 2m 24s | — | 136.69 | — | -0.69% | — | — | — | — |
| **192t — rh8-al318 (192 vCPU)** | 76 | 76 | 5 | 380 | 2m 23s | — | 137.64 | — | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 77 | 77 | 4 | 308 | 2m 27s | — | 133.90 | — | -2.72% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 78 | 78 | 4 | 312 | 2m 27s | — | 133.90 | — | -2.72% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 128 | 128 | 3 | 384 | 2m 35s | — | 126.99 | — | -7.74% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-signed-polar-boundary-vote"></a>
<details>
<summary><strong>signed_polar_boundary_vote</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 8m 3s | — | 4.53 | 1.00× | -94.82% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 1m 13s | — | 29.96 | 6.62× | -65.75% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 23 | 23 | 16 | 368 | 37s | — | 59.11 | 13.05× | -32.43% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 37 | 37 | 10 | 370 | 29s | — | 75.41 | 16.66× | -13.80% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 38 | 38 | 10 | 380 | 27s | — | 81.00 | 17.89× | -7.41% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 39 | 39 | 9 | 351 | 26s | — | 84.12 | 18.58× | -3.84% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 40 | 40 | 9 | 360 | 25s | — | 87.48 | 19.32× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 41 | 41 | 9 | 369 | 26s | — | 84.12 | 18.58× | -3.84% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 29s | — | 75.41 | 16.66× | -13.80% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-star-convex"></a>
<details>
<summary><strong>star_convex</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 192t — rh8-al319 (192 vCPU) | 1 | 1 | 384 | 384 | 58s | — | 12.57 | 1.00× | -82.76% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 6 | 6 | 64 | 384 | 13s | — | 56.08 | 4.46× | -23.07% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 7 | 7 | 54 | 378 | 11s | — | 66.27 | 5.27× | -9.09% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 11s | — | 66.27 | 5.27× | -9.09% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 11s | — | 66.27 | 5.27× | -9.09% | — | — | — | — |
| **192t — rh8-al319 (192 vCPU)** | 10 | 10 | 38 | 380 | 10s | — | 72.90 | 5.80× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 11 | 11 | 34 | 374 | 11s | — | 66.27 | 5.27× | -9.09% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 21s | — | 34.71 | 2.76× | -52.39% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-text-flow"></a>
<details>
<summary><strong>text_flow</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al319 (192 vCPU)** | 1 | 1 | 384 | 384 | 5s | — | 145.80 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 8 | 8 | 48 | 384 | 5s | — | 145.80 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 9 | 9 | 42 | 378 | 6s | — | 121.50 | 0.83× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 11 | 11 | 34 | 374 | 6s | — | 121.50 | 0.83× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 14 | 14 | 27 | 378 | 6s | — | 121.50 | 0.83× | -16.67% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 23 | 23 | 16 | 368 | 9s | — | 81.00 | 0.56× | -44.44% | — | — | — | — |
| 192t — rh8-al319 (192 vCPU) | 64 | 64 | 6 | 384 | 23s | — | 31.70 | 0.22× | -78.26% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

<a id="detector-shape-data-whitespace-frame"></a>
<details>
<summary><strong>whitespace_frame</strong></summary>

**Search method(s):** `legacy`

This table contains measurements from this optimizer execution only. Bold identifies this run’s measured throughput winner; the preferred configuration above is selected from all compatible coalesced optimizer evidence.

| Runner | Pipelines | Shards | Threads / pipeline | Allocated | Wall | Startup overhead | Sets/s | Speedup | Δ from run best | Avg load | Peak load | Avg CPU | Peak RAM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| **192t — rh8-al318 (192 vCPU)** | 1 | 1 | 384 | 384 | 3s | — | 243.33 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 3 | 3 | 128 | 384 | 3s | — | 243.33 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 4 | 4 | 96 | 384 | 3s | — | 243.33 | 1.00× | 0.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 5 | 5 | 76 | 380 | 4s | — | 182.50 | 0.75× | -25.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 8 | 8 | 48 | 384 | 4s | — | 182.50 | 0.75× | -25.00% | — | — | — | — |
| 192t — rh8-al318 (192 vCPU) | 64 | 64 | 6 | 384 | 21s | — | 34.76 | 0.14× | -85.71% | — | — | — | — |

**Startup-overhead note:** executor startup is measured from `run-detector-regressions` entry through detector lifecycle preparation, planning, shared learned-evidence resolution/preparation, and initial queue setup before pipeline fan-out. It remains included in **Wall** and therefore in shape-level **Sets/s** as a constant reminder of incurred end-to-end cost. Per-shard parameter-set throughput is timed after fan-out and does not include this pre-fan-out startup overhead.

</details>

</details>

[↑ Back to Navigation](#table-of-contents)
