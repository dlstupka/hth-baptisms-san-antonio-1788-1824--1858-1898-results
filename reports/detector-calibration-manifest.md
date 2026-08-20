# Detector Regression Manifest

<a id="table-of-contents"></a>

<details open>
<summary><strong>Navigation</strong></summary>

- [Source document](#source-document)
- [Detector Recommendation for this Golden Set](#detector-recommendation-for-this-golden-set)
- [Ranked Detector Smoke Test Results](#ranked-detector-smoke-test-results)
  - [Metric Definitions](#metric-definitions)
- [Detector Calibration Report](#detector-calibration-report)
  - [Best Known Detector Calibrations](#best-known-detector-calibrations)
  - [Calibration Report Legend](#calibration-report-legend)
  - [Per-Detector Calibration Reports](#per-detector-calibration-reports)
    - [Adaptive Multi-Scale Radial Edge Search (`adaptive_multi_scale_radial_edge`)](#adaptive-multi-scale-radial-edge-search-adaptivemultiscaleradialedge)
    - [Multi-Scale Radial Edge Search (`multi_scale_radial_edge`)](#multi-scale-radial-edge-search-multiscaleradialedge)
    - [Fusion Gen1 — MSRE + BFQ + SPBV + Page Background (`msre_bfq_spbv_pbg`)](#fusion-gen1-msre-bfq-spbv-page-background-msrebfqspbvpbg)
    - [Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background (`amsre_bfq_spbv_pbg`)](#fusion-gen2-amsre-bfq-spbv-page-background-amsrebfqspbvpbg)
    - [dhSegment Page-Mask Detector (`dhsegment_page_mask`)](#dhsegment-page-mask-detector-dhsegmentpagemask)
    - [Adaptive Radial Edge Search (`adaptive_radial_edge`)](#adaptive-radial-edge-search-adaptiveradialedge)
    - [Signed Polar Boundary Voting (`signed_polar_boundary_vote`)](#signed-polar-boundary-voting-signedpolarboundaryvote)
    - [Border Fusion Quad (`border_fusion_quad`)](#border-fusion-quad-borderfusionquad)
    - [Page Background (`page_background`)](#page-background-pagebackground)
    - [Polar Boundary Voting (`polar_boundary_vote`)](#polar-boundary-voting-polarboundaryvote)
    - [Gradient Boundary Voting (`gradient_vote`)](#gradient-boundary-voting-gradientvote)
    - [Radial Edge Search (`radial_edge`)](#radial-edge-search-radialedge)
    - [Segment-Supported Polar Voting (`segment_supported_polar_vote`)](#segment-supported-polar-voting-segmentsupportedpolarvote)
    - [Doc-UFCN Page-Mask Detector (`doc_ufcn_page_mask`)](#doc-ufcn-page-mask-detector-docufcnpagemask)
    - [Orli Page Mask (`orli_page_mask`)](#orli-page-mask-orlipagemask)
    - [GrabCut Segmentation (`grabcut`)](#grabcut-segmentation-grabcut)
    - [Contour Quadrilateral (`contour_quad`)](#contour-quadrilateral-contourquad)
    - [Learned Page-Mask Detector (`learned_page_mask`)](#learned-page-mask-detector-learnedpagemask)
    - [GrabCut + Contour (`grabcut_contour`)](#grabcut-contour-grabcutcontour)
    - [Cross-Edge Contour (`cross_edge_contour`)](#cross-edge-contour-crossedgecontour)
    - [Contour + Projection (`contour_projection`)](#contour-projection-contourprojection)
    - [Edge-Supported Contour (`edge_contour`)](#edge-supported-contour-edgecontour)
    - [Contour + GrabCut (`contour_grabcut`)](#contour-grabcut-contourgrabcut)
    - [Contour + Components (`contour_components`)](#contour-components-contourcomponents)
    - [Contour Envelope (`contour`)](#contour-envelope-contour)
    - [Kraken Page Mask (`kraken_page_mask`)](#kraken-page-mask-krakenpagemask)
    - [Distance Transform Detector (`distance_transform`)](#distance-transform-detector-distancetransform)
    - [Star-Convex Boundary Optimization (`star_convex`)](#star-convex-boundary-optimization-starconvex)
    - [Connected Components (`components`)](#connected-components-components)
    - [RANSAC Border Fit (`ransac`)](#ransac-border-fit-ransac)
    - [Line Segment Detector (`lsd`)](#line-segment-detector-lsd)
    - [Convex Hull Detector (`convex_hull`)](#convex-hull-detector-convexhull)
    - [Border Energy Validator (`border_energy`)](#border-energy-validator-borderenergy)
    - [Distance-Transform Rectangle Proposal (`distance_transform_rect`)](#distance-transform-rectangle-proposal-distancetransformrect)
    - [Hough Line Borders (`hough`)](#hough-line-borders-hough)
    - [Projective Gradient Vote (`projective_gradient_vote`)](#projective-gradient-vote-projectivegradientvote)
    - [Consensus Quadrilateral (`consensus_quad`)](#consensus-quadrilateral-consensusquad)
    - [Radon Boundary Projection (`radon_boundary`)](#radon-boundary-projection-radonboundary)
    - [Joint Rectangle Voting (`joint_rectangle_vote`)](#joint-rectangle-voting-jointrectanglevote)
    - [Text Flow Envelope (`text_flow`)](#text-flow-envelope-textflow)
    - [Whitespace Frame (`whitespace_frame`)](#whitespace-frame-whitespaceframe)
- [Detector Regression Reports](#detector-regression-reports)
  - [Regression Completion Summary](#regression-completion-summary)
  - [Regression Execution and Detector Queueing](#regression-execution-and-detector-queueing)
  - [Regression Recommendations Summary](#regression-recommendations-summary)
  - [Per-Detector Regression Reports](#per-detector-regression-reports)
    - [Adaptive Multi-Scale Radial Edge Search (`adaptive_multi_scale_radial_edge`)](#adaptive-multi-scale-radial-edge-search-adaptivemultiscaleradialedge-2)
    - [Adaptive Radial Edge Search (`adaptive_radial_edge`)](#adaptive-radial-edge-search-adaptiveradialedge-2)
    - [Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background (`amsre_bfq_spbv_pbg`)](#fusion-gen2-amsre-bfq-spbv-page-background-amsrebfqspbvpbg-2)
    - [Border Energy Validator (`border_energy`)](#border-energy-validator-borderenergy-2)
    - [Border Fusion Quad (`border_fusion_quad`)](#border-fusion-quad-borderfusionquad-2)
    - [Connected Components (`components`)](#connected-components-components-2)
    - [Consensus Quadrilateral (`consensus_quad`)](#consensus-quadrilateral-consensusquad-2)
    - [Contour Envelope (`contour`)](#contour-envelope-contour-2)
    - [Contour + Components (`contour_components`)](#contour-components-contourcomponents-2)
    - [Contour + GrabCut (`contour_grabcut`)](#contour-grabcut-contourgrabcut-2)
    - [Contour + Projection (`contour_projection`)](#contour-projection-contourprojection-2)
    - [Contour Quadrilateral (`contour_quad`)](#contour-quadrilateral-contourquad-2)
    - [Convex Hull Detector (`convex_hull`)](#convex-hull-detector-convexhull-2)
    - [Cross-Edge Contour (`cross_edge_contour`)](#cross-edge-contour-crossedgecontour-2)
    - [dhSegment Page-Mask Detector (`dhsegment_page_mask`)](#dhsegment-page-mask-detector-dhsegmentpagemask-2)
    - [Distance Transform Detector (`distance_transform`)](#distance-transform-detector-distancetransform-2)
    - [Distance-Transform Rectangle Proposal (`distance_transform_rect`)](#distance-transform-rectangle-proposal-distancetransformrect-2)
    - [Doc-UFCN Page-Mask Detector (`doc_ufcn_page_mask`)](#doc-ufcn-page-mask-detector-docufcnpagemask-2)
    - [Edge-Supported Contour (`edge_contour`)](#edge-supported-contour-edgecontour-2)
    - [GrabCut Segmentation (`grabcut`)](#grabcut-segmentation-grabcut-2)
    - [GrabCut + Contour (`grabcut_contour`)](#grabcut-contour-grabcutcontour-2)
    - [Gradient Boundary Voting (`gradient_vote`)](#gradient-boundary-voting-gradientvote-2)
    - [Hough Line Borders (`hough`)](#hough-line-borders-hough-2)
    - [Joint Rectangle Voting (`joint_rectangle_vote`)](#joint-rectangle-voting-jointrectanglevote-2)
    - [Kraken Page Mask (`kraken_page_mask`)](#kraken-page-mask-krakenpagemask-2)
    - [Learned Page-Mask Detector (`learned_page_mask`)](#learned-page-mask-detector-learnedpagemask-2)
    - [Line Segment Detector (`lsd`)](#line-segment-detector-lsd-2)
    - [Fusion Gen1 — MSRE + BFQ + SPBV + Page Background (`msre_bfq_spbv_pbg`)](#fusion-gen1-msre-bfq-spbv-page-background-msrebfqspbvpbg-2)
    - [Multi-Scale Radial Edge Search (`multi_scale_radial_edge`)](#multi-scale-radial-edge-search-multiscaleradialedge-2)
    - [Orli Page Mask (`orli_page_mask`)](#orli-page-mask-orlipagemask-2)
    - [Page Background (`page_background`)](#page-background-pagebackground-2)
    - [Polar Boundary Voting (`polar_boundary_vote`)](#polar-boundary-voting-polarboundaryvote-2)
    - [Projective Gradient Vote (`projective_gradient_vote`)](#projective-gradient-vote-projectivegradientvote-2)
    - [Radial Edge Search (`radial_edge`)](#radial-edge-search-radialedge-2)
    - [Radon Boundary Projection (`radon_boundary`)](#radon-boundary-projection-radonboundary-2)
    - [RANSAC Border Fit (`ransac`)](#ransac-border-fit-ransac-2)
    - [Segment-Supported Polar Voting (`segment_supported_polar_vote`)](#segment-supported-polar-voting-segmentsupportedpolarvote-2)
    - [Signed Polar Boundary Voting (`signed_polar_boundary_vote`)](#signed-polar-boundary-voting-signedpolarboundaryvote-2)
    - [Star-Convex Boundary Optimization (`star_convex`)](#star-convex-boundary-optimization-starconvex-2)
    - [Text Flow Envelope (`text_flow`)](#text-flow-envelope-textflow-2)
    - [Whitespace Frame (`whitespace_frame`)](#whitespace-frame-whitespaceframe-2)
- [Engineering Continuous Improvement](#engineering-continuous-improvement)
  - [Calibration Intelligence Persistence](#calibration-intelligence-persistence)
  - [Runtime Intelligence Persistence](#runtime-intelligence-persistence)
  - [Engineering Notes](#engineering-notes)

</details>


**Detectors evaluated:** 41

<a id="source-document"></a>
## Source document

- **Document:** Baptisms: San Antonio. Baptism Records 1788–1824, 1858–1898
- **Images:** 929

[↑ Back to Navigation](#table-of-contents)

<a id="detector-recommendation-for-this-golden-set"></a>
## Detector Recommendation for this Golden Set

- **Recommended detector:** Adaptive Multi-Scale Radial Edge Search
- **Detector short name:** Adaptive Multi-Scale Radial
- **Detector ID:** `adaptive_multi_scale_radial_edge`
- **Best observed Avg IoU:** `0.9781`
- **Worst Golden Set page (Min IoU):** `0.9564`
- **Page-to-page StdDev:** `0.0182`
- **Role:** `Generator`
- **Engineering Recommendation:** Retain this detector as the current Golden Set recommendation. Additional tuning should be driven by unresolved page failures, late winner changes, or a plausible untested parameter region rather than by search expansion alone.

**Recommendation basis:**

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 13 of 18 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

This recommendation is specific to the evaluated Golden Set and parameter grid and should be revisited when the Golden Set, parameter grid, or source document changes.

[↑ Back to Navigation](#table-of-contents)

<a id="ranked-detector-smoke-test-results"></a>
## Ranked Detector Smoke Test Results

| Rank | Detector | Detector ID | Role | Golden Set ID | Status | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Parameter Sets | Eval Rate | Doc Time | Run Elapsed |
|---:|---|---|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | Adaptive Multi-Scale Radial Edge Search | `adaptive_multi_scale_radial_edge` | Generator | `HTH-0001` | complete | `unknown` | `21ea516c3c5a` | `21ea516c3c5a` | 0.9781 | 0.9564 | 0.0182 | 0.9781 | 0 | 50001 | 0.3711 pg/s | 41m 43s | 33m 13s |
| 2 | Multi-Scale Radial Edge Search | `multi_scale_radial_edge` | Generator | `HTH-0001` | complete | `unknown` | `ddb7623ebb92` | `ddb7623ebb92` | 0.9765 | 0.9566 | 0.0175 | 0.9765 | 0 | 384077 | 5.216 pg/s | 2m 58s | 3h 50m 18s |
| 3 | Fusion Gen1 — MSRE + BFQ + SPBV + Page Background | `msre_bfq_spbv_pbg` | Hybrid (MSRE + BFQ + SPBV + Page Background) | `HTH-0001` | complete | `unknown` | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9747 | 0.9638 | 0.0101 | 0.9747 | 0 | 50176 | 0.2677 pg/s | 57m 50s | 1h 8m 47s |
| 4 | Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background | `amsre_bfq_spbv_pbg` | Hybrid (AMSRE + BFQ + SPBV + Page Background) | `HTH-0001` | complete | `unknown` | `156ff0241cc1` | `baseline` | 0.9743 | 0.9638 | 0.0103 | 0.9743 | 0 | 50177 | 2.734 pg/s | 5m 40s | 1h 18m 41s |
| 5 | dhSegment Page-Mask Detector | `dhsegment_page_mask` | Generator | `HTH-0001` | complete | `unknown` | `15434712cddf` | `15434712cddf` | 0.9735 | 0.9634 | 0.0100 | 0.9735 | 0 | 10000 | 0.2909 pg/s | 53m 14s | 13m 37s |
| 6 | Adaptive Radial Edge Search | `adaptive_radial_edge` | Generator | `HTH-0001` | complete | `unknown` | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9726 | 0.9557 | 0.0159 | 0.9726 | 0 | 750001 | 2.707 pg/s | 5m 43s | 1h 8m 48s |
| 7 | Signed Polar Boundary Voting | `signed_polar_boundary_vote` | Generator | `HTH-0001` | complete | `unknown` | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.9717 | 0.9506 | 0.0193 | 0.9717 | 0 | 453600 | 27.85 pg/s | 33.4s | 4h 1m 25s |
| 8 | Border Fusion Quad | `border_fusion_quad` | Hybrid (Radial + Polar + Gradient) | `HTH-0001` | complete | `unknown` | `2370e6cea486` | `2370e6cea486` | 0.9707 | 0.9588 | 0.0112 | 0.9707 | 0 | 539001 | 4.537 pg/s | 3m 25s | 11h 28m 47s |
| 9 | Page Background | `page_background` | Generator | `HTH-0001` | complete | `unknown` | `afbe81a796a1` | `afbe81a796a1` | 0.9692 | 0.9498 | 0.0171 | 0.9692 | 0 | 200001 | 2.010 pg/s | 7m 42s | 16m 17s |
| 10 | Polar Boundary Voting | `polar_boundary_vote` | Generator | `HTH-0001` | complete | `unknown` | `935369155754` | `935369155754` | 0.9691 | 0.9524 | 0.0154 | 0.9691 | 0 | 19636 | 0.2410 pg/s | 1h 4m 14s | 26m 49s |
| 11 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | complete | `unknown` | `cf581d27715b` | `cf581d27715b` | 0.9622 | 0.9384 | 0.0160 | 0.9622 | 0 | 22 | 502.61 pg/s | 1.8s | 809 ms |
| 12 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | complete | `unknown` | `837321a04ccf` | `837321a04ccf` | 0.9571 | 0.9261 | 0.0183 | 0.9571 | 0 | 400001 | 6.470 pg/s | 2m 24s | 13m 28s |
| 13 | Segment-Supported Polar Voting | `segment_supported_polar_vote` | Hybrid (Polar + LSD) | `HTH-0001` | complete | `unknown` | `4546643c94a4` | `4546643c94a4` | 0.9470 | 0.8447 | 0.0536 | 0.9470 | 0 | 180001 | 2.286 pg/s | 6m 46s | 22m 54s |
| 14 | Doc-UFCN Page-Mask Detector | `doc_ufcn_page_mask` | Generator | `HTH-0001` | complete | `595002645fcc` | `595002645fcc` | `595002645fcc` | 0.9371 | 0.7663 | 0.0856 | 0.9371 | 0 | 2000 | 33.08 pg/s | 28.1s | 4.5s |
| 15 | Orli Page Mask | `orli_page_mask` | Generator | `HTH-0001` | complete | `d58e03537115` | `bd0c02b4f4fe` | `bd0c02b4f4fe` | 0.9185 | 0.8557 | 0.0411 | 0.9185 | 0 | 1680 | 21.89 pg/s | 42.4s | 13.7s |
| 16 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | complete | `unknown` | `110867d137a9` | `110867d137a9` | 0.9137 | 0.7378 | 0.0886 | 0.9137 | 0 | 13122 | 0.0489 pg/s | 5h 16m 39s | 46m 8s |
| 17 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | complete | `unknown` | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | 0.8874 | 0 | 1062882 | 12.52 pg/s | 1m 14s | 10h 40m 34s |
| 18 | Learned Page-Mask Detector | `learned_page_mask` | Generator | `HTH-0001` | complete | `unknown` | `275078578cee` | `275078578cee` | 0.8868 | 0.8122 | 0.0470 | 0.8868 | 0 | 50000 | 0.1360 pg/s | 1h 53m 52s | 1h 19m 22s |
| 19 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | complete | `unknown` | `3a1623be3b6e` | `3a1623be3b6e` | 0.8781 | 0.7198 | 0.0900 | 0.8781 | 0 | 46657 | 0.0676 pg/s | 3h 49m 11s | 3h 22m 55s |
| 20 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | complete | `unknown` | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 6562 | 23.42 pg/s | 39.7s | 3m 28s |
| 21 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | complete | `unknown` | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 6562 | 10.92 pg/s | 1m 25s | 7m 22s |
| 22 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | complete | `unknown` | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 13123 | 4.823 pg/s | 3m 13s | 1m 8s |
| 23 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | complete | `unknown` | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 6562 | 0.1764 pg/s | 1h 27m 47s | 3h 9m 30s |
| 24 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | complete | `unknown` | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | 19684 | 83.60 pg/s | 11.1s | 3m 48s |
| 25 | Contour Envelope | `contour` | Generator | `HTH-0001` | complete | `unknown` | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | 1458 | 145.59 pg/s | 6.4s | 4.6s |
| 26 | Kraken Page Mask | `kraken_page_mask` | Generator | `HTH-0001` | complete | `unknown` | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8396 | 0.5596 | 0.1531 | 0.8396 | 0 | 10000 | 93.31 pg/s | 10s | 9.4s |
| 27 | Distance Transform Detector | `distance_transform` | Generator | `HTH-0001` | complete | `unknown` | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | 0.8388 | 0 | 2187 | 2.026 pg/s | 7m 39s | 28.6s |
| 28 | Star-Convex Boundary Optimization | `star_convex` | Generator | `HTH-0001` | complete | `unknown` | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | 0.8179 | 0 | 729 | 1.314 pg/s | 11m 47s | 7.2s |
| 29 | Connected Components | `components` | Generator | `HTH-0001` | complete | `unknown` | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | 0.7897 | 0 | 19683 | 237.69 pg/s | 3.9s | 40.8s |
| 30 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | complete | `unknown` | `9647b030702e` | `9647b030702e` | 0.7541 | 0.3558 | 0.2541 | 0.7541 | 0 | 1458 | 4.771 pg/s | 3m 15s | 1m 31s |
| 31 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | complete | `unknown` | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | 0.9222 | 1 | 2187 | 13.20 pg/s | 1m 10s | 59s |
| 32 | Convex Hull Detector | `convex_hull` | Generator | `HTH-0001` | complete | `unknown` | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | 0.9156 | 1 | 2187 | 28.47 pg/s | 32.6s | 2s |
| 33 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | complete | `unknown` | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | 0.9063 | 1 | 6562 | 9.159 pg/s | 1m 41s | 3m 59s |
| 34 | Distance-Transform Rectangle Proposal | `distance_transform_rect` | Generator | `HTH-0001` | complete | `unknown` | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | 0.7243 | 0 | 729 | 12.21 pg/s | 1m 16s | 1.2s |
| 35 | Hough Line Borders | `hough` | Generator | `HTH-0001` | complete | `unknown` | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | 0.7563 | 1 | 2188 | 3.685 pg/s | 4m 12s | 3m 4s |
| 36 | Projective Gradient Vote | `projective_gradient_vote` | Generator | `HTH-0001` | complete | `unknown` | `e536a07cca54` | `e536a07cca54` | 0.5541 | 0.0000 | 0.4546 | 0.9235 | 2 | 730 | 2.461 pg/s | 6m 17s | 6.1s |
| 37 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | complete | `unknown` | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | 0.9213 | 2 | 243 | 3.487 pg/s | 4m 26s | 21.3s |
| 38 | Radon Boundary Projection | `radon_boundary` | Generator | `HTH-0001` | complete | `unknown` | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | 0.4983 | 0 | 729 | 2.105 pg/s | 7m 21s | 10.4s |
| 39 | Joint Rectangle Voting | `joint_rectangle_vote` | Generator | `HTH-0001` | complete | `unknown` | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | 0.9899 | 4 | 2187 | 2.064 pg/s | 7m 30s | 22.3s |
| 40 | Text Flow Envelope | `text_flow` | Generator | `HTH-0001` | complete | `unknown` | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | 0.8170 | 4 | 729 | 13.12 pg/s | 1m 11s | 3.5s |
| 41 | Whitespace Frame | `whitespace_frame` | Generator | `HTH-0001` | complete | `unknown` | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 730 | 721.81 pg/s | 1.3s | 1.3s |

[↑ Back to Navigation](#table-of-contents)

<a id="metric-definitions"></a>
### Metric Definitions

- **Avg IoU:** Arithmetic mean across every Golden Set page; failed/no-candidate pages contribute `0.0000` and remain in the denominator. This is the primary ranking metric.
- **Avg IoU Success:** Arithmetic mean across successful Golden Set page evaluations only; failed/no-candidate pages are excluded.
- **Min IoU:** Lowest single-page IoU produced by that winner across the Golden Set. It exposes the detector's weakest evaluated page; it is not the minimum Avg IoU across parameter sets.
- **StdDev:** Population standard deviation of the winner's page IoUs. Lower values indicate more even page-to-page performance, but a uniformly poor detector can also have a low StdDev, so read it with Avg IoU and Min IoU.
- **Failures:** Number of Golden Set pages the winning parameter set could not evaluate successfully.
- **Ranking order:** Avg IoU descending, then Min IoU descending, failures ascending, StdDev ascending, and evaluation rate descending.
- **Δ Baseline Avg IoU:** Winning Avg IoU minus the named baseline profile's Avg IoU for the same detector run.

[↑ Back to Navigation](#table-of-contents)

<a id="detector-calibration-report"></a>
<details open>
<summary><h2>Detector Calibration Report</h2></summary>

This section characterizes the evaluated calibration landscapes, parameter influence, interactions, near-best coverage width, page sensitivity, and opportunities to reduce future search cost. All findings are Golden Set- and grid-specific and must be revalidated when the Golden Set or parameter space changes.

[↑ Back to Navigation](#table-of-contents)

<a id="best-known-detector-calibrations"></a>
### Best Known Detector Calibrations

**Engineering Decision**

This table is the authoritative detector ranking for this Golden Set. The Rank #1 detector is the current engineering recommendation based on the best approved calibration available for this Golden Set.

This table prefers compatible full calibrations when available and falls back to the latest smoke evidence for detectors without a full calibration on this Golden Set.

**Parameter-space note:** `Parameter Sets` is the declared discrete calibration grid for that run. `exhaustive` means every valid set in that declared grid was evaluated; it does not imply every value in an underlying continuous mathematical domain was tested. Invalid combinations should be rejected before evaluation, while behaviorally redundant/no-op combinations should be canonicalized so they do not inflate search or basin statistics.

| Rank | Detector | Detector ID | Role | Golden Set ID | Date | Build* | Est. Serial Runtime** | Family ID | Parameter Set ID | Parameter Sets | Search Type | Successful Parameter Sets | Best Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Δ Baseline Avg IoU | Near-best Coverage (Basin) | Equivalent Best Configurations | Calibration Evidence | Approval Level |
|---:|---|---|---|---|---|---|---:|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---|
| **1** | **Adaptive Multi-Scale Radial Edge Search** | **`adaptive_multi_scale_radial_edge`** | **Generator** | **`HTH-0001`** | **2026-08-15** | **[#424](https://github.com/dlstupka/hth/actions/runs/31892318300)** | **33m 13s** | **`unknown`** | **`21ea516c3c5a`** | **50001** | **exhaustive** | **100.0%** | **0.9781** | **0.9564** | **0.0182** | **0.9781** | **0** | **+0.0013** | **0.0%** | **0.0%** | **Medium** | **Recommended** |
| 2 | Multi-Scale Radial Edge Search | `multi_scale_radial_edge` | Generator | `HTH-0001` | 2026-08-13 | [#371](https://github.com/dlstupka/hth/actions/runs/31748488486) | 3h 50m 18s | `unknown` | `ddb7623ebb92` | 384077 | exhaustive | 100.0% | 0.9765 | 0.9566 | 0.0175 | 0.9765 | 0 | +0.3245 | 0.0% | 0.0% | Medium | Recommended |
| 3 | Fusion Gen1 — MSRE + BFQ + SPBV + Page Background | `msre_bfq_spbv_pbg` | Hybrid (MSRE + BFQ + SPBV + Page Background) | `HTH-0001` | 2026-08-14 | [#387](https://github.com/dlstupka/hth/actions/runs/31824453163) | 1h 8m 47s | `unknown` | `7b7dbac43ea6` | 50176 | exhaustive | 84.5% | 0.9747 | 0.9638 | 0.0101 | 0.9747 | 0 | +0.0009 | 31.0% | 0.0% | Medium | Recommended |
| 4 | Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background | `amsre_bfq_spbv_pbg` | Hybrid (AMSRE + BFQ + SPBV + Page Background) | `HTH-0001` | 2026-08-15 | [#428](https://github.com/dlstupka/hth/actions/runs/31899010020) | 1h 18m 41s | `unknown` | `156ff0241cc1` | 50177 | exhaustive | 99.4% | 0.9743 | 0.9638 | 0.0103 | 0.9743 | 0 | +0.0000 | 90.2% | 61.6% | High | Approved |
| 5 | dhSegment Page-Mask Detector | `dhsegment_page_mask` | Generator | `HTH-0001` | 2026-08-16 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | 13m 37s | `unknown` | `15434712cddf` | 10000 | exhaustive | 100.0% | 0.9735 | 0.9634 | 0.0100 | 0.9735 | 0 | +0.0065 | 7.7% | 1.3% | High | Approved |
| 6 | Adaptive Radial Edge Search | `adaptive_radial_edge` | Generator | `HTH-0001` | 2026-08-13 | [#370](https://github.com/dlstupka/hth/actions/runs/31748441601) | 1h 8m 48s | `unknown` | `bcd9a1d083cf` | 750001 | exhaustive | 100.0% | 0.9726 | 0.9557 | 0.0159 | 0.9726 | 0 | +0.0397 | 0.0% | 0.0% | Medium | Recommended |
| 7 | Signed Polar Boundary Voting | `signed_polar_boundary_vote` | Generator | `HTH-0001` | 2026-08-13 | [#374](https://github.com/dlstupka/hth/actions/runs/31748657986) | 4h 1m 25s | `unknown` | `8ddbe5f468cd` | 453600 | exhaustive | 100.0% | 0.9717 | 0.9506 | 0.0193 | 0.9717 | 0 | +0.1235 | 0.0% | 0.0% | Medium | Recommended |
| 8 | Border Fusion Quad | `border_fusion_quad` | Hybrid (Radial + Polar + Gradient) | `HTH-0001` | 2026-08-13 | [#372](https://github.com/dlstupka/hth/actions/runs/31748550347) | 11h 28m 47s | `unknown` | `2370e6cea486` | 539001 | exhaustive | 99.1% | 0.9707 | 0.9588 | 0.0112 | 0.9707 | 0 | +0.0817 | 5.4% | 0.8% | High | Approved |
| 9 | Page Background | `page_background` | Generator | `HTH-0001` | 2026-08-14 | [#383](https://github.com/dlstupka/hth/actions/runs/31806184641) | 16m 17s | `unknown` | `afbe81a796a1` | 200001 | exhaustive | 46.0% | 0.9692 | 0.9498 | 0.0171 | 0.9692 | 0 | +0.2074 | 0.6% | 0.1% | Medium | Recommended |
| 10 | Polar Boundary Voting | `polar_boundary_vote` | Generator | `HTH-0001` | 2026-08-15 | [#416](https://github.com/dlstupka/hth/actions/runs/31891034843) | 26m 49s | `unknown` | `935369155754` | 19636 | exhaustive | 100.0% | 0.9691 | 0.9524 | 0.0154 | 0.9691 | 0 | +0.0013 | 0.0% | 0.0% | Medium | Recommended |
| 11 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | 2026-08-15 | [#421](https://github.com/dlstupka/hth/actions/runs/31891526961) | 809 ms | `unknown` | `cf581d27715b` | 22 | exhaustive | 54.5% | 0.9622 | 0.9384 | 0.0160 | 0.9622 | 0 | +0.0155 | 18.2% | 13.6% | Medium | Recommended |
| 12 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | 2026-08-13 | [#369](https://github.com/dlstupka/hth/actions/runs/31748401024) | 13m 28s | `unknown` | `837321a04ccf` | 400001 | exhaustive | 100.0% | 0.9571 | 0.9261 | 0.0183 | 0.9571 | 0 | +0.0068 | 0.1% | 0.0% | Medium | Recommended |
| 13 | Segment-Supported Polar Voting | `segment_supported_polar_vote` | Hybrid (Polar + LSD) | `HTH-0001` | 2026-08-14 | [#382](https://github.com/dlstupka/hth/actions/runs/31806152306) | 22m 54s | `unknown` | `4546643c94a4` | 180001 | exhaustive | 80.0% | 0.9470 | 0.8447 | 0.0536 | 0.9470 | 0 | +0.2496 | 0.0% | 0.0% | Medium | Recommended |
| 14 | Doc-UFCN Page-Mask Detector | `doc_ufcn_page_mask` | Generator | `HTH-0001` | 2026-08-20 | [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | 4.5s | `595002645fcc` | `595002645fcc` | 2000 | exhaustive | 100.0% | 0.9371 | 0.7663 | 0.0856 | 0.9371 | 0 | +0.0716 | 10.0% | 10.0% | High | Approved |
| 15 | Orli Page Mask | `orli_page_mask` | Generator | `HTH-0001` | 2026-08-20 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | 13.7s | `d58e03537115` | `bd0c02b4f4fe` | 1680 | exhaustive | 50.0% | 0.9185 | 0.8557 | 0.0411 | 0.9185 | 0 | +0.1122 | 0.8% | 0.4% | Medium | Recommended |
| 16 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | 2026-08-16 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | 46m 8s | `unknown` | `110867d137a9` | 13122 | exhaustive | 95.4% | 0.9137 | 0.7378 | 0.0886 | 0.9137 | 0 | +0.1006 | 0.0% | 0.0% | Medium | Recommended |
| 17 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | 2026-08-10 | [#287](https://github.com/dlstupka/hth/actions/runs/31424165043) | 10h 40m 34s | `unknown` | `49095b866d0d` | 1062882 | exhaustive | 33.3% | 0.8874 | 0.7589 | 0.0731 | 0.8874 | 0 | +0.0105 | 15.5% | 5.3% | Medium | Recommended |
| 18 | Learned Page-Mask Detector | `learned_page_mask` | Generator | `HTH-0001` | 2026-08-13 | [#355](https://github.com/dlstupka/hth/actions/runs/31711919948) | 1h 19m 22s | `unknown` | `275078578cee` | 50000 | exhaustive | 100.0% | 0.8868 | 0.8122 | 0.0470 | 0.8868 | 0 | +0.0494 | 1.0% | 0.1% | High | Approved |
| 19 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | 2026-08-18 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | 3h 22m 55s | `unknown` | `3a1623be3b6e` | 46657 | exhaustive | 100.0% | 0.8781 | 0.7198 | 0.0900 | 0.8781 | 0 | +0.0651 | 6.2% | 6.2% | High | Approved |
| 20 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | 2026-08-10 | [#285](https://github.com/dlstupka/hth/actions/runs/31424162073) | 3h 9m 30s | `unknown` | `3eec8a03f1de` | 6562 | exhaustive | 100.0% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 100.0% | 100.0% | High | Approved |
| 21 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | 2026-08-10 | [#286](https://github.com/dlstupka/hth/actions/runs/31424163624) | 7m 22s | `unknown` | `0cd13eb1a471` | 6562 | exhaustive | 100.0% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 92.6% | 92.6% | High | Approved |
| 22 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | 2026-08-10 | [#288](https://github.com/dlstupka/hth/actions/runs/31424166301) | 3m 28s | `unknown` | `a5450e58ec9e` | 6562 | exhaustive | 29.6% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 29.6% | 29.6% | Medium | Recommended |
| 23 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | 2026-08-10 | [#301](https://github.com/dlstupka/hth/actions/runs/31437186835) | 1m 8s | `unknown` | `4e5bc37a649a` | 13123 | exhaustive | 12.3% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.3377 | 8.6% | 8.6% | Medium | Recommended |
| 24 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | 2026-08-10 | [#284](https://github.com/dlstupka/hth/actions/runs/31424160561) | 3m 48s | `unknown` | `14818b491952` | 19684 | exhaustive | 100.0% | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | +0.0000 | 100.0% | 100.0% | High | Approved |
| 25 | Contour Envelope | `contour` | Generator | `HTH-0001` | 2026-08-10 | [#283](https://github.com/dlstupka/hth/actions/runs/31424159190) | 4.6s | `unknown` | `7aed2fc501c5` | 1458 | exhaustive | 50.0% | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | +0.1776 | 1.9% | 1.9% | Medium | Recommended |
| 26 | Kraken Page Mask | `kraken_page_mask` | Generator | `HTH-0001` | 2026-08-17 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | 9.4s | `unknown` | `c4845fd6c6b6` | 10000 | exhaustive | 100.0% | 0.8396 | 0.5596 | 0.1531 | 0.8396 | 0 | +0.0328 | 1.0% | 0.4% | High | Approved |
| 27 | Distance Transform Detector | `distance_transform` | Generator | `HTH-0001` | 2026-08-12 | [#322](https://github.com/dlstupka/hth/actions/runs/31606269618) | 28.6s | `unknown` | `e66a7546e1a7` | 2187 | exhaustive | 51.2% | 0.8388 | 0.5001 | 0.1745 | 0.8388 | 0 | +0.0795 | 6.6% | 6.6% | Medium | Recommended |
| 28 | Star-Convex Boundary Optimization | `star_convex` | Generator | `HTH-0001` | 2026-08-12 | [#328](https://github.com/dlstupka/hth/actions/runs/31614832224) | 7.2s | `unknown` | `024732f5e631` | 729 | exhaustive | 100.0% | 0.8179 | 0.5367 | 0.1827 | 0.8179 | 0 | +0.0422 | 0.4% | 0.4% | Medium | Recommended |
| 29 | Connected Components | `components` | Generator | `HTH-0001` | 2026-08-10 | [#281](https://github.com/dlstupka/hth/actions/runs/31424156590) | 40.8s | `unknown` | `f1929c8e2655` | 19683 | exhaustive | 75.8% | 0.7897 | 0.5725 | 0.1665 | 0.7897 | 0 | +0.0712 | 0.8% | 0.8% | Medium | Recommended |
| 30 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | 2026-08-10 | [#296](https://github.com/dlstupka/hth/actions/runs/31424177450) | 1m 31s | `unknown` | `9647b030702e` | 1458 | exhaustive | 5.3% | 0.7541 | 0.3558 | 0.2541 | 0.7541 | 0 | +0.0710 | 0.4% | 0.4% | Medium | Recommended |
| 31 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | 2026-08-10 | [#294](https://github.com/dlstupka/hth/actions/runs/31424174875) | 59s | `unknown` | `7546c5067527` | 2187 | exhaustive | 0.0% | 0.7378 | 0.0000 | 0.3721 | 0.9222 | 1 | +0.1964 | 1.2% | 0.4% | Medium | Recommended |
| 32 | Convex Hull Detector | `convex_hull` | Generator | `HTH-0001` | 2026-08-12 | [#321](https://github.com/dlstupka/hth/actions/runs/31606215160) | 2s | `unknown` | `04fd0a6e4bc2` | 2187 | exhaustive | 0.0% | 0.7325 | 0.0000 | 0.3683 | 0.9156 | 1 | +0.0692 | 6.6% | 6.6% | Medium | Recommended |
| 33 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | 2026-08-10 | [#278](https://github.com/dlstupka/hth/actions/runs/31423513220) | 3m 59s | `unknown` | `74e2112aac01` | 6562 | exhaustive | 0.0% | 0.7250 | 0.0000 | 0.3651 | 0.9063 | 1 | +0.1708 | 19.8% | 19.8% | Medium | Recommended |
| 34 | Distance-Transform Rectangle Proposal | `distance_transform_rect` | Generator | `HTH-0001` | 2026-08-12 | [#326](https://github.com/dlstupka/hth/actions/runs/31614704921) | 1.2s | `unknown` | `0a8482550c35` | 729 | exhaustive | 9.9% | 0.7243 | 0.4499 | 0.2245 | 0.7243 | 0 | +0.0896 | 0.8% | 0.8% | Medium | Recommended |
| 35 | Hough Line Borders | `hough` | Generator | `HTH-0001` | 2026-08-10 | [#293](https://github.com/dlstupka/hth/actions/runs/31424173458) | 3m 4s | `unknown` | `c2c117479e3f` | 2188 | exhaustive | 0.0% | 0.6050 | 0.0000 | 0.3217 | 0.7563 | 1 | +0.1266 | 0.0% | 0.0% | Medium | Recommended |
| 36 | Projective Gradient Vote | `projective_gradient_vote` | Generator | `HTH-0001` | 2026-08-13 | [#358](https://github.com/dlstupka/hth/actions/runs/31715583665) | 6.1s | `unknown` | `e536a07cca54` | 730 | exhaustive | 0.0% | 0.5541 | 0.0000 | 0.4546 | 0.9235 | 2 | +0.1067 | 11.1% | 3.7% | Medium | Recommended |
| 37 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | 2026-08-10 | [#282](https://github.com/dlstupka/hth/actions/runs/31424157793) | 21.3s | `unknown` | `f387da7ebb7e` | 243 | exhaustive | 0.0% | 0.5528 | 0.0000 | 0.4526 | 0.9213 | 2 | +0.0015 | 9.9% | 4.9% | Medium | Recommended |
| 38 | Radon Boundary Projection | `radon_boundary` | Generator | `HTH-0001` | 2026-08-12 | [#331](https://github.com/dlstupka/hth/actions/runs/31633124269) | 10.4s | `unknown` | `dd6b2601d568` | 729 | exhaustive | 58.0% | 0.4983 | 0.2028 | 0.2509 | 0.4983 | 0 | +0.0756 | 1.2% | 1.2% | Medium | Recommended |
| 39 | Joint Rectangle Voting | `joint_rectangle_vote` | Generator | `HTH-0001` | 2026-08-12 | [#336](https://github.com/dlstupka/hth/actions/runs/31635559108) | 22.3s | `unknown` | `5c9509e05f14` | 2187 | exhaustive | 0.0% | 0.1980 | 0.0000 | 0.3960 | 0.9899 | 4 | +0.1980 | 1.2% | 1.2% | Medium | Recommended |
| 40 | Text Flow Envelope | `text_flow` | Generator | `HTH-0001` | 2026-08-12 | [#335](https://github.com/dlstupka/hth/actions/runs/31635508472) | 3.5s | `unknown` | `a2bbfc162f9e` | 729 | exhaustive | 0.0% | 0.1634 | 0.0000 | 0.3268 | 0.8170 | 4 | +0.0038 | 4.7% | 4.7% | Medium | Recommended |
| 41 | Whitespace Frame | `whitespace_frame` | Generator | `HTH-0001` | 2026-08-12 | [#333](https://github.com/dlstupka/hth/actions/runs/31633282476) | 1.3s | `unknown` | `9ef715dda063` | 730 | exhaustive | 0.0% | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | +0.0000 | 100.0% | 100.0% | Medium | Recommended |

[↑ Back to Navigation](#table-of-contents)

<a id="calibration-report-legend"></a>
### Calibration Report Legend

- **Generator:** proposes an original page boundary from its primary visual evidence.
- **Validator:** scores or confirms a hypothesis generated elsewhere without normally proposing a competing boundary.
- **Hybrid (detectors):** combines the named generator and validator or fuses the named generators.
- **Critical / Important / Moderate / Low / Dormant:** plain-English parameter-influence classes, from dominant measured association to no material measured effect in this grid.
- **Near-best coverage (basin):** share of tested parameter sets within the displayed tolerance of the best Avg IoU; broader coverage indicates more forgiving calibration.
- **Equivalent best configurations:** share of tested sets effectively tied with the best result at the stricter displayed tolerance.
- **Calibration Evidence:** deterministic evidence score for how completely this run characterizes the evaluated Golden Set and parameter grid. Score 2 points for complete exhaustive coverage, 1 point when at least 90% of parameter sets succeed on every page, and 1 point when at least 1% of tested sets are within 0.001 Avg IoU of the winner. **Low** = 0–1 points, **Medium** = 2–3 points, and **High** = 4 points. This is not confidence that the detector generalizes beyond this Golden Set and grid.
- **Approval Level:** automatic Golden Set-scoped engineering status derived from Search Type and Calibration Evidence. **Provisional** = smoke or unavailable evidence; **Candidate** = any reduced search or exhaustive search with Low evidence; **Recommended** = exhaustive search with Medium evidence; **Approved** = exhaustive search with High evidence. A different Golden Set requires its own calibration and approval.
- **Evidence tables:** identify what each detector actually observes and whether that evidence generates, validates, filters, or scores a page hypothesis.
- **Build*:** `#run` links open GitHub Actions logs and artifacts and expire according to repository retention; the calibration data persists in [calibration-intelligence.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/64f5f3fa38718b5808b2c6a2471e9904d8634477/source-documents/baptisms-san-antonio-baptism-records-1788-1824-1858-1898/golden-sets/hth-0001/135c0ff57687/calibrations/adaptive_multi_scale_radial_edge/run-20260815-155156/calibration-intelligence.json).
- **Est. Serial Runtime\*\*:** Estimated single-detector serial runtime derived from recorded regression evidence; actual wall time varies with parallelism and scheduling.

[↑ Back to Navigation](#table-of-contents)

<a id="per-detector-calibration-reports"></a>
<details open>
<summary><h3>Per-Detector Calibration Reports</h3></summary>


[↑ Back to Navigation](#table-of-contents)

<a id="adaptive-multi-scale-radial-edge-search-adaptivemultiscaleradialedge"></a>
<details>
<summary><strong>Adaptive Multi-Scale Radial Edge Search (`adaptive_multi_scale_radial_edge`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 13 of 18 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 50001 |
| Parameter sets evaluated | 50001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 50001 (100.0%) |
| Best Avg IoU | 0.9781 |
| Minimum Avg IoU | 0.9624 |
| Avg IoU StdDev | 0.0028 |
| Winner stabilized after | 26475 parameter sets |
| Winner stabilized | 16m 31s (53% of search) |
| Near-best coverage (basin; within 0.0010) | 6 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 50001 | 100.0% | 7d 19h 6m 38s | 1.0× |
| Non-dormant | 50000 | 100.0% | 7d 19h 6m 25s | 1.0× |
| Low+ | 50000 | 100.0% | 7d 19h 6m 25s | 1.0× |
| Moderate+ | 500 | 1.0% | 1h 52m 16s | 100.0× |
| Important+ | 50 | 0.1% | 11m 14s | 1000.0× |
| Critical | 10 | 0.0% | 2m 15s | 5000.1× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `coarse_angle_step_degrees` | Critical | 0.4927 | 0.0071 | 10.0% | `2.04545` (0.9754), `1.9` (0.9725), `2.025` (0.9713) | current run |
| `maximum_refined_sides` | Important | 0.1383 | 0.0029 | 40.0% | `4` (0.9719), `3` (0.9718), `2` (0.9708) | current run |
| `refined_angle_step_degrees` | Moderate | 0.0450 | 0.0022 | 10.0% | `0.5` (0.9715), `1` (0.9714), `0.8` (0.9712) | current run |
| `side_assignment_tolerance_fraction` | Low | 0.0071 | 0.0008 | 10.0% | `0.0075` (0.9712), `0.01` (0.9710), `0.0125` (0.9710) | current run |
| `weak_side_support_fraction` | Low | 0.0026 | 0.0004 | 30.0% | `0.55` (0.9709), `0.6` (0.9709), `0.5` (0.9709) | current run |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.2` (0.9767) | current run |
| `base_sigma` | Dormant | 0.0001 | 0.0000 | 0.0% | `1` (0.9767) | current run |
| `bbox_padding_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0` (0.9767) | current run |
| `gradient_percentile` | Dormant | 0.0001 | 0.0000 | 0.0% | `96.875` (0.9767) | current run |
| `maximum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.98` (0.9767) | current run |
| `maximum_radius_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.78` (0.9767) | current run |
| `minimum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.18` (0.9767) | current run |
| `minimum_radius_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.16` (0.9767) | current run |
| `minimum_ray_support` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.36` (0.9767) | current run |
| `scale_count` | Dormant | 0.0001 | 0.0000 | 0.0% | `4` (0.9767) | current run |
| `scale_ratio` | Dormant | 0.0001 | 0.0000 | 0.0% | `3.5` (0.9767) | current run |
| `strength_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.3` (0.9767) | current run |
| `support_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.5` (0.9767) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `base_sigma`, `bbox_padding_fraction`, `gradient_percentile`, `maximum_area_fraction`, `maximum_radius_fraction`, `minimum_area_fraction`, `minimum_radius_fraction`, `minimum_ray_support`, `scale_count`, `scale_ratio`, `strength_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `coarse_angle_step_degrees` × `maximum_refined_sides` | 0.8115 | 0.3186 | 25001 |
| `coarse_angle_step_degrees` × `side_assignment_tolerance_fraction` | 0.5748 | 0.0819 | 25001 |
| `maximum_refined_sides` × `refined_angle_step_degrees` | 0.2130 | 0.0747 | 25001 |
| `coarse_angle_step_degrees` × `refined_angle_step_degrees` | 0.5542 | 0.0613 | 25001 |
| `refined_angle_step_degrees` × `side_assignment_tolerance_fraction` | 0.1008 | 0.0494 | 25001 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9724 | 0.9464 | 0.9860 | 0.0080 | 100.0% |
| 5 | 0.9751 | 0.9617 | 0.9973 | 0.0088 | 100.0% |
| 6 | 0.9943 | 0.9856 | 0.9989 | 0.0030 | 100.0% |
| 9 | 0.9563 | 0.9544 | 0.9576 | 0.0010 | 100.0% |
| 10 | 0.9558 | 0.9541 | 0.9574 | 0.0009 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="multi-scale-radial-edge-search-multiscaleradialedge"></a>
<details>
<summary><strong>Multi-Scale Radial Edge Search (`multi_scale_radial_edge`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 9 of 14 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 384077 |
| Parameter sets evaluated | 384077 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 383901 (100.0%) |
| Best Avg IoU | 0.9765 |
| Minimum Avg IoU | 0.4493 |
| Avg IoU StdDev | 0.0480 |
| Winner stabilized after | 362950 parameter sets |
| Winner stabilized | 3h 34m 22s (94% of search) |
| Near-best coverage (basin; within 0.0010) | 75 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 384077 | 100.0% | 4d 6h 16m 47s | 1.0× |
| Non-dormant | 384076 | 100.0% | 4d 6h 16m 46s | 1.0× |
| Low+ | 384076 | 100.0% | 4d 6h 16m 46s | 1.0× |
| Moderate+ | 43 | 0.0% | 41.2s | 8932.0× |
| Important+ | 43 | 0.0% | 41.2s | 8932.0× |
| Critical | 43 | 0.0% | 41.2s | 8932.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_percentile` | Critical | 0.8335 | 0.2814 | 39.5% | `95.5` (0.9614), `95.625` (0.9613), `95.375` (0.9611) | current run |
| `base_sigma` | Low | 0.0281 | 0.0241 | 27.6% | `1.3` (0.9540), `1.475` (0.9538), `1.35` (0.9535) | current run |
| `ray_count` | Low | 0.0135 | 0.0166 | 28.6% | `240` (0.9536), `192` (0.9521), `96` (0.9517) | current run |
| `scale_ratio` | Low | 0.0079 | 0.0142 | 54.5% | `2.875` (0.9512), `3` (0.9508), `2.75` (0.9504) | current run |
| `scale_count` | Low | 0.0017 | 0.0039 | 100.0% | `4` (0.9483), `3` (0.9444) | current run |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.2` (0.6520) | current run |
| `bbox_padding_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0` (0.6520) | current run |
| `maximum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.98` (0.6520) | current run |
| `maximum_radius_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.78` (0.6520) | current run |
| `minimum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.18` (0.6520) | current run |
| `minimum_radius_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.16` (0.6520) | current run |
| `minimum_ray_support` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.36` (0.6520) | current run |
| `strength_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.3` (0.6520) | current run |
| `support_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.5` (0.6520) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `bbox_padding_fraction`, `maximum_area_fraction`, `maximum_radius_fraction`, `minimum_area_fraction`, `minimum_radius_fraction`, `minimum_ray_support`, `strength_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `gradient_percentile` × `base_sigma` | 0.8977 | 0.0639 | 48010 |
| `base_sigma` × `scale_ratio` | 0.0539 | 0.0257 | 48010 |
| `base_sigma` × `ray_count` | 0.0529 | 0.0246 | 48010 |
| `gradient_percentile` × `ray_count` | 0.8555 | 0.0216 | 48010 |
| `ray_count` × `scale_ratio` | 0.0251 | 0.0120 | 48010 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9542 | 0.2997 | 0.9963 | 0.0525 | 100.0% |
| 5 | 0.9544 | 0.5614 | 0.9971 | 0.0468 | 100.0% |
| 6 | 0.9220 | 0.2904 | 1.0000 | 0.1288 | 100.0% |
| 9 | 0.9496 | 0.0000 | 0.9616 | 0.0383 | 100.0% |
| 10 | 0.9516 | 0.7940 | 0.9820 | 0.0134 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="fusion-gen1-msre-bfq-spbv-page-background-msrebfqspbvpbg"></a>
<details>
<summary><strong>Fusion Gen1 — MSRE + BFQ + SPBV + Page Background (`msre_bfq_spbv_pbg`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 5 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 50176 |
| Parameter sets evaluated | 50176 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 42395 (84.5%) |
| Best Avg IoU | 0.9747 |
| Minimum Avg IoU | 0.1984 |
| Avg IoU StdDev | 0.1319 |
| Winner stabilized after | 49773 parameter sets |
| Winner stabilized | 1h 7m 13s (99% of search) |
| Near-best coverage (basin; within 0.0010) | 15544 (31.0%) |
| Equivalent-best configurations (within 0.0001) | 4 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Non-dormant | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Low+ | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Moderate+ | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Important+ | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Critical | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_side_consensus` | Critical | 0.2704 | 0.2601 | 93.8% | `0.487444` (0.9736), `0.483857` (0.9735), `0.480269` (0.9735) | current run |
| `consensus_tolerance_fraction` | Critical | 0.2696 | 0.2502 | 42.9% | `0.037623` (0.9736), `0.03783` (0.9736), `0.038036` (0.9736) | current run |
| `consensus_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.6` (0.9201) | current run |
| `gradient_percentile` | Dormant | 0.0000 | 0.0000 | 100.0% | `76` (0.9201) | current run |
| `gradient_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.9201) | current run |
| `minimum_side_gradient_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.9201) | current run |
| `source_diversity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.9201) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consensus_weight`, `gradient_percentile`, `gradient_weight`, `minimum_side_gradient_support`, `source_diversity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_side_consensus` × `consensus_tolerance_fraction` | 1.0000 | 0.7256 | 25088 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8227 | 0.0000 | 0.9785 | 0.3515 | 84.6% |
| 5 | 0.8664 | 0.0000 | 0.9913 | 0.3083 | 88.8% |
| 6 | 0.9915 | 0.9911 | 0.9931 | 0.0005 | 100.0% |
| 9 | 0.9597 | 0.0000 | 0.9638 | 0.0565 | 99.7% |
| 10 | 0.9603 | 0.0000 | 0.9643 | 0.0567 | 99.7% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="fusion-gen2-amsre-bfq-spbv-page-background-amsrebfqspbvpbg"></a>
<details>
<summary><strong>Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background (`amsre_bfq_spbv_pbg`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- 5 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 50177 |
| Parameter sets evaluated | 50177 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 49898 (99.4%) |
| Best Avg IoU | 0.9743 |
| Minimum Avg IoU | 0.5807 |
| Avg IoU StdDev | 0.0270 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 45274 (90.2%) |
| Equivalent-best configurations (within 0.0001) | 30913 (61.6%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 50177 | 100.0% | 1d 1h 29m 11s | 1.0× |
| Non-dormant | 50625 | 100.9% | 1d 1h 42m 50s | 1.0× |
| Low+ | 50625 | 100.9% | 1d 1h 42m 50s | 1.0× |
| Moderate+ | 50625 | 100.9% | 1d 1h 42m 50s | 1.0× |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `consensus_tolerance_fraction` | Moderate | 0.0837 | 0.0409 | 94.7% | `0.00896` (0.9743), `0.009094` (0.9743), `0.009229` (0.9743) | current run |
| `minimum_side_consensus` | Moderate | 0.0603 | 0.0343 | 100.0% | `0.1` (0.9743), `0.49843` (0.9740), `0.496188` (0.9740) | current run |
| `consensus_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.6` (0.9743) | current run |
| `gradient_percentile` | Dormant | 0.0000 | 0.0000 | 100.0% | `76` (0.9743) | current run |
| `gradient_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.9743) | current run |
| `minimum_side_gradient_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.9743) | current run |
| `source_diversity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.9743) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consensus_weight`, `gradient_percentile`, `gradient_weight`, `minimum_side_gradient_support`, `source_diversity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `consensus_tolerance_fraction` × `minimum_side_consensus` | 1.0000 | 0.9169 | 25089 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9707 | 0.0000 | 0.9751 | 0.0653 | 99.5% |
| 5 | 0.9707 | 0.0000 | 0.9913 | 0.0725 | 99.4% |
| 6 | 0.9917 | 0.9911 | 0.9920 | 0.0004 | 100.0% |
| 9 | 0.9633 | 0.9539 | 0.9638 | 0.0022 | 100.0% |
| 10 | 0.9636 | 0.9574 | 0.9643 | 0.0021 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="dhsegment-page-mask-detector-dhsegmentpagemask"></a>
<details>
<summary><strong>dhSegment Page-Mask Detector (`dhsegment_page_mask`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 3 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 10000 |
| Parameter sets evaluated | 10000 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 10000 (100.0%) |
| Best Avg IoU | 0.9735 |
| Minimum Avg IoU | 0.9581 |
| Avg IoU StdDev | 0.0034 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 28.4s (0% of search) |
| Near-best coverage (basin; within 0.0010) | 770 (7.7%) |
| Equivalent-best configurations (within 0.0001) | 130 (1.3%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 10000 | 100.0% | 1d 23h 44m 42s | 1.0× |
| Non-dormant | 200 | 2.0% | 57m 18s | 50.0× |
| Low+ | 200 | 2.0% | 57m 18s | 50.0× |
| Moderate+ | 40 | 0.4% | 11m 28s | 250.0× |
| Important+ | 40 | 0.4% | 11m 28s | 250.0× |
| Critical | 4 | 0.0% | 1m 9s | 2500.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `contour_offset_fraction` | Critical | 0.6663 | 0.0075 | 25.0% | `0.008` (0.9707), `0.004` (0.9683), `0` (0.9659) | current run |
| `probability_threshold` | Important | 0.2246 | 0.0052 | 50.0% | `0.35` (0.9689), `0.4` (0.9684), `-1` (0.9683) | current run |
| `close_kernel_fraction` | Low | 0.0022 | 0.0004 | 100.0% | `0` (0.9673), `0.0025` (0.9672), `0.005` (0.9670) | current run |
| `open_kernel_fraction` | Dormant | 0.0003 | 0.0002 | 100.0% | `0.0045` (0.9671), `0.006` (0.9671), `0.0015` (0.9670) | current run |
| `fill_holes` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.9670), `0` (0.9670) | current run |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.9670), `0.15` (0.9670), `0.2` (0.9670) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`open_kernel_fraction`, `fill_holes`, `minimum_page_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `contour_offset_fraction` × `probability_threshold` | 0.9660 | 0.2997 | 10000 |
| `probability_threshold` × `close_kernel_fraction` | 0.2462 | 0.0216 | 10000 |
| `probability_threshold` × `open_kernel_fraction` | 0.2285 | 0.0039 | 10000 |
| `contour_offset_fraction` × `close_kernel_fraction` | 0.6686 | 0.0023 | 10000 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9696 | 0.9534 | 0.9795 | 0.0053 | 100.0% |
| 5 | 0.9449 | 0.9192 | 0.9793 | 0.0124 | 100.0% |
| 6 | 0.9898 | 0.9811 | 0.9951 | 0.0036 | 100.0% |
| 9 | 0.9643 | 0.9532 | 0.9719 | 0.0052 | 100.0% |
| 10 | 0.9667 | 0.9600 | 0.9726 | 0.0022 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="adaptive-radial-edge-search-adaptiveradialedge"></a>
<details>
<summary><strong>Adaptive Radial Edge Search (`adaptive_radial_edge`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 11 of 16 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 750001 |
| Parameter sets evaluated | 750001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 750001 (100.0%) |
| Best Avg IoU | 0.9726 |
| Minimum Avg IoU | 0.7773 |
| Avg IoU StdDev | 0.0406 |
| Winner stabilized after | 686657 parameter sets |
| Winner stabilized | 55m 27s (92% of search) |
| Near-best coverage (basin; within 0.0010) | 149 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 29 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 750001 | 100.0% | 16d 50m 48s | 1.0× |
| Non-dormant | 3750 | 0.5% | 1h 55m 27s | 200.0× |
| Low+ | 3750 | 0.5% | 1h 55m 27s | 200.0× |
| Moderate+ | 250 | 0.0% | 7m 42s | 3000.0× |
| Important+ | 25 | 0.0% | 46.2s | 30000.0× |
| Critical | 5 | 0.0% | 9.2s | 150000.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `maximum_radius_fraction` | Critical | 0.6214 | 0.0893 | 40.0% | `0.72` (0.9266), `0.78` (0.9187), `0.84` (0.9120) | current run |
| `minimum_radius_fraction` | Important | 0.1201 | 0.0318 | 20.0% | `0.22` (0.9150), `0.26` (0.9143), `0.18` (0.8928) | current run |
| `gaussian_sigma` | Moderate | 0.0526 | 0.0363 | 20.0% | `2.4` (0.9121), `2` (0.9057), `2.2` (0.9051) | current run |
| `maximum_refined_sides` | Low | 0.0178 | 0.0132 | 33.3% | `4` (0.9049), `2` (0.8971), `1` (0.8917) | current run |
| `refined_angle_step_degrees` | Low | 0.0068 | 0.0099 | 20.0% | `0.35` (0.9033), `0.5` (0.8995), `0.75` (0.8973) | current run |
| `gradient_percentile` | Dormant | 0.0008 | 0.0038 | 100.0% | `74` (0.9008), `78` (0.8988), `80` (0.8986) | current run |
| `side_assignment_tolerance_fraction` | Dormant | 0.0003 | 0.0016 | 100.0% | `0.015` (0.8986), `0.025` (0.8984), `0.035` (0.8978) | current run |
| `weak_side_support_fraction` | Dormant | 0.0000 | 0.0003 | 100.0% | `0.55` (0.8980), `0.35` (0.8980), `0.45` (0.8979) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.35` (0.9329) | current run |
| `coarse_angle_step_degrees` | Dormant | 0.0000 | 0.0000 | 0.0% | `3` (0.9329) | current run |
| `maximum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.9329) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.18` (0.9329) | current run |
| `minimum_ray_support` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.45` (0.9329) | current run |
| `ray_count` | Dormant | 0.0000 | 0.0000 | 0.0% | `120` (0.9329) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.9329) | current run |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.45` (0.9329) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`gradient_percentile`, `side_assignment_tolerance_fraction`, `weak_side_support_fraction`, `area_weight`, `coarse_angle_step_degrees`, `maximum_area_fraction`, `minimum_area_fraction`, `minimum_ray_support`, `ray_count`, `rectangularity_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_radius_fraction` × `minimum_radius_fraction` | 0.7647 | 0.1445 | 46876 |
| `maximum_radius_fraction` × `gaussian_sigma` | 0.7178 | 0.0976 | 46876 |
| `minimum_radius_fraction` × `gaussian_sigma` | 0.1788 | 0.0580 | 46876 |
| `gaussian_sigma` × `maximum_refined_sides` | 0.0768 | 0.0241 | 46876 |
| `maximum_radius_fraction` × `maximum_refined_sides` | 0.6412 | 0.0211 | 46876 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9067 | 0.7146 | 0.9841 | 0.0511 | 100.0% |
| 5 | 0.9351 | 0.7520 | 0.9931 | 0.0456 | 100.0% |
| 6 | 0.8210 | 0.5665 | 0.9979 | 0.0923 | 100.0% |
| 9 | 0.8965 | 0.7134 | 0.9575 | 0.0687 | 100.0% |
| 10 | 0.9303 | 0.7929 | 0.9787 | 0.0430 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="signed-polar-boundary-voting-signedpolarboundaryvote"></a>
<details>
<summary><strong>Signed Polar Boundary Voting (`signed_polar_boundary_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 453600 |
| Parameter sets evaluated | 453600 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 453600 (100.0%) |
| Best Avg IoU | 0.9717 |
| Minimum Avg IoU | 0.7926 |
| Avg IoU StdDev | 0.0394 |
| Winner stabilized after | 13680 parameter sets |
| Winner stabilized | 6m 28s (3% of search) |
| Near-best coverage (basin; within 0.0010) | 18 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 6 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 453600 | 100.0% | 22h 37m 14s | 1.0× |
| Non-dormant | 10800 | 2.4% | 32m 19s | 42.0× |
| Low+ | 10800 | 2.4% | 32m 19s | 42.0× |
| Moderate+ | 450 | 0.1% | 1m 21s | 1008.0× |
| Important+ | 9 | 0.0% | 1.6s | 50400.0× |
| Critical | 9 | 0.0% | 1.6s | 50400.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `outer_radius_fraction` | Critical | 0.7674 | 0.1051 | 11.1% | `0.575` (0.9381), `0.6` (0.9355), `0.55` (0.9302) | current run |
| `bbox_padding_fraction` | Moderate | 0.0436 | 0.0230 | 20.0% | `0` (0.9068), `0.002` (0.9041), `0.004` (0.9010) | current run |
| `gradient_percentile` | Moderate | 0.0330 | 0.0245 | 10.0% | `95` (0.9079), `94` (0.9058), `93` (0.9034) | current run |
| `polarity` | Low | 0.0169 | 0.0125 | 33.3% | `absolute` (0.9046), `bright_inside` (0.8973), `dark_inside` (0.8921) | current run |
| `ray_count` | Low | 0.0095 | 0.0099 | 12.5% | `72` (0.9019), `144` (0.9014), `120` (0.9012) | current run |
| `inner_radius_fraction` | Dormant | 0.0000 | 0.0009 | 42.9% | `0.18` (0.8984), `0.1` (0.8983), `0.14` (0.8981) | current run |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8980), `0.25` (0.8980), `0.3` (0.8980) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`inner_radius_fraction`, `minimum_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_radius_fraction` × `bbox_padding_fraction` | 0.8309 | 0.0635 | 45360 |
| `outer_radius_fraction` × `gradient_percentile` | 0.8165 | 0.0491 | 45360 |
| `outer_radius_fraction` × `polarity` | 0.8077 | 0.0402 | 45360 |
| `bbox_padding_fraction` × `gradient_percentile` | 0.0766 | 0.0322 | 45360 |
| `outer_radius_fraction` × `ray_count` | 0.7907 | 0.0233 | 45360 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8902 | 0.7175 | 0.9840 | 0.0537 | 100.0% |
| 5 | 0.9214 | 0.6838 | 0.9962 | 0.0568 | 100.0% |
| 6 | 0.9471 | 0.7115 | 0.9981 | 0.0160 | 100.0% |
| 9 | 0.8391 | 0.7134 | 0.9582 | 0.0738 | 100.0% |
| 10 | 0.8924 | 0.7523 | 0.9714 | 0.0477 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="border-fusion-quad-borderfusionquad"></a>
<details>
<summary><strong>Border Fusion Quad (`border_fusion_quad`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 9 of 12 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 539001 |
| Parameter sets evaluated | 539001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 534381 (99.1%) |
| Best Avg IoU | 0.9707 |
| Minimum Avg IoU | 0.6649 |
| Avg IoU StdDev | 0.0394 |
| Winner stabilized after | 115 parameter sets |
| Winner stabilized | 9.6s (0% of search) |
| Near-best coverage (basin; within 0.0010) | 28900 (5.4%) |
| Equivalent-best configurations (within 0.0001) | 4410 (0.8%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 539001 | 100.0% | 6d 20h 59m 57s | 1.0× |
| Non-dormant | 4004 | 0.7% | 1h 13m 33s | 134.6× |
| Low+ | 4004 | 0.7% | 1h 13m 33s | 134.6× |
| Moderate+ | 4004 | 0.7% | 1h 13m 33s | 134.6× |
| Important+ | 154 | 0.0% | 2m 50s | 3500.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_weight` | Important | 0.2369 | 0.0553 | 63.6% | `0.225` (0.9419), `0.2` (0.9403), `0.15` (0.9273) | current run |
| `minimum_side_gradient_support` | Important | 0.1783 | 0.0564 | 78.6% | `0.01` (0.9267), `0` (0.9262), `0.02` (0.9257) | current run |
| `gradient_percentile` | Moderate | 0.0459 | 0.0397 | 92.3% | `69` (0.9159), `68` (0.9158), `76` (0.9154) | current run |
| `source_confidence_weight` | Dormant | 0.0009 | 0.0034 | 100.0% | `0.45` (0.9126), `0.5` (0.9125), `0.55` (0.9125) | current run |
| `source_diversity_weight` | Dormant | 0.0001 | 0.0010 | 75.0% | `0.15` (0.9121), `0.05` (0.9114), `0` (0.9111) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.15` (0.8890) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0` (0.8890) | current run |
| `maximum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.8890) | current run |
| `minimum_child_candidates` | Dormant | 0.0000 | 0.0000 | 0.0% | `2` (0.8890) | current run |
| `minimum_child_confidence` | Dormant | 0.0000 | 0.0000 | 0.0% | `0` (0.8890) | current run |
| `minimum_distinct_sources` | Dormant | 0.0000 | 0.0000 | 0.0% | `2` (0.8890) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.9114), `0.12` (0.9114), `0.26` (0.9114) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`source_confidence_weight`, `source_diversity_weight`, `area_weight`, `bbox_padding_fraction`, `maximum_area_fraction`, `minimum_child_candidates`, `minimum_child_confidence`, `minimum_distinct_sources`, `minimum_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `gradient_weight` × `minimum_side_gradient_support` | 0.5152 | 0.2772 | 49001 |
| `minimum_side_gradient_support` × `gradient_percentile` | 0.4418 | 0.2621 | 49001 |
| `gradient_weight` × `gradient_percentile` | 0.3552 | 0.1172 | 49001 |
| `gradient_weight` × `source_confidence_weight` | 0.2518 | 0.0139 | 49001 |
| `gradient_percentile` × `source_confidence_weight` | 0.0521 | 0.0055 | 49001 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9565 | 0.8681 | 0.9686 | 0.0176 | 100.0% |
| 5 | 0.7249 | 0.5776 | 0.9734 | 0.1812 | 100.0% |
| 6 | 0.9804 | 0.0000 | 0.9911 | 0.0913 | 99.1% |
| 9 | 0.9374 | 0.8238 | 0.9588 | 0.0459 | 100.0% |
| 10 | 0.9579 | 0.8854 | 0.9660 | 0.0167 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="page-background-pagebackground"></a>
<details>
<summary><strong>Page Background (`page_background`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 5 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 107968 of 200001 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 200001 |
| Parameter sets evaluated | 200001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 92033 (46.0%) |
| Best Avg IoU | 0.9692 |
| Minimum Avg IoU | 0.6924 |
| Avg IoU StdDev | 0.1014 |
| Winner stabilized after | 4026 parameter sets |
| Winner stabilized | 18.6s (2% of search) |
| Near-best coverage (basin; within 0.0010) | 1185 (0.6%) |
| Equivalent-best configurations (within 0.0001) | 110 (0.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 200001 | 100.0% | 5d 18h 13m 52s | 1.0× |
| Non-dormant | 25000 | 12.5% | 17h 16m 44s | 8.0× |
| Low+ | 25000 | 12.5% | 17h 16m 44s | 8.0× |
| Moderate+ | 500 | 0.2% | 20m 44s | 400.0× |
| Important+ | 20 | 0.0% | 49.8s | 10000.0× |
| Critical | 20 | 0.0% | 49.8s | 10000.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `border_band_fraction` | Critical | 0.8776 | 0.1988 | 50.0% | `0.015` (0.9534), `0.02` (0.9534), `0.0225` (0.9534) | current run |
| `color_distance_threshold` | Moderate | 0.0411 | 0.0725 | 48.0% | `9.5` (0.8609), `9` (0.8606), `6` (0.8605) | current run |
| `blur_sigma` | Low | 0.0044 | 0.0223 | 90.0% | `0` (0.8543), `0.2` (0.8543), `0.4` (0.8525) | current run |
| `close_kernel_fraction` | Low | 0.0011 | 0.0108 | 100.0% | `0.008` (0.8517), `0.0005` (0.8461), `0.001` (0.8461) | current run |
| `open_kernel_fraction` | Dormant | 0.0003 | 0.0053 | 100.0% | `0` (0.8477), `0.0015` (0.8470), `0.002` (0.8470) | current run |
| `minimum_border_background_fraction` | Dormant | 0.0000 | 0.0843 | 50.0% | `0.15` (0.8462), `0.5` (0.7618) | current run |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0843 | 50.0% | `0.15` (0.8462), `0.25` (0.7618) | current run |
| `maximum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.7618) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.6` (0.7618) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`open_kernel_fraction`, `minimum_border_background_fraction`, `minimum_page_area_fraction`, `maximum_page_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `border_band_fraction` × `blur_sigma` | 0.9280 | 0.0501 | 40001 |
| `border_band_fraction` × `color_distance_threshold` | 0.9247 | 0.0467 | 40001 |
| `color_distance_threshold` × `blur_sigma` | 0.0485 | 0.0073 | 40001 |
| `color_distance_threshold` × `close_kernel_fraction` | 0.0460 | 0.0049 | 40001 |
| `color_distance_threshold` × `open_kernel_fraction` | 0.0436 | 0.0024 | 40001 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9569 | 0.9243 | 0.9952 | 0.0093 | 100.0% |
| 5 | 0.9146 | 0.5678 | 0.9920 | 0.1126 | 100.0% |
| 6 | 0.4565 | 0.0000 | 0.9991 | 0.4945 | 46.0% |
| 9 | 0.9506 | 0.9317 | 0.9736 | 0.0031 | 100.0% |
| 10 | 0.9523 | 0.9280 | 0.9792 | 0.0049 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="polar-boundary-voting-polarboundaryvote"></a>
<details>
<summary><strong>Polar Boundary Voting (`polar_boundary_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 19636 |
| Parameter sets evaluated | 19636 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 19636 (100.0%) |
| Best Avg IoU | 0.9691 |
| Minimum Avg IoU | 0.6602 |
| Avg IoU StdDev | 0.0410 |
| Winner stabilized after | 3885 parameter sets |
| Winner stabilized | 3m 21s (20% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19636 | 100.0% | 4d 17h 9m 3s | 1.0× |
| Non-dormant | 19635 | 100.0% | 4d 17h 8m 42s | 1.0× |
| Low+ | 19635 | 100.0% | 4d 17h 8m 42s | 1.0× |
| Moderate+ | 357 | 1.8% | 2h 3m 26s | 55.0× |
| Important+ | 357 | 1.8% | 2h 3m 26s | 55.0× |
| Critical | 21 | 0.1% | 7m 16s | 935.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `outer_radius_fraction` | Critical | 0.6383 | 0.0975 | 9.5% | `0.58` (0.9389), `0.59` (0.9389), `0.6` (0.9372) | current run |
| `gradient_percentile` | Important | 0.1934 | 0.0782 | 11.8% | `94` (0.9034), `93` (0.9026), `92` (0.9004) | current run |
| `ray_count` | Low | 0.0034 | 0.0064 | 40.0% | `240` (0.8958), `180` (0.8955), `90` (0.8938) | current run |
| `bbox_padding_fraction` | Low | 0.0012 | 0.0043 | 9.1% | `0.001` (0.8946), `0.002` (0.8946), `0` (0.8946) | current run |
| `inner_radius_fraction` | Dormant | 0.0002 | 0.0000 | 0.0% | `0.06` (0.9678) | current run |
| `minimum_support_fraction` | Dormant | 0.0002 | 0.0000 | 0.0% | `0.25` (0.9678) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`inner_radius_fraction`, `minimum_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_radius_fraction` × `gradient_percentile` | 0.8647 | 0.2264 | 19636 |
| `outer_radius_fraction` × `ray_count` | 0.6650 | 0.0267 | 19636 |
| `outer_radius_fraction` × `bbox_padding_fraction` | 0.6545 | 0.0162 | 19636 |
| `gradient_percentile` × `ray_count` | 0.2083 | 0.0149 | 19636 |
| `gradient_percentile` × `bbox_padding_fraction` | 0.1972 | 0.0037 | 19636 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8575 | 0.4953 | 0.9819 | 0.0664 | 100.0% |
| 5 | 0.9126 | 0.5381 | 0.9952 | 0.0628 | 100.0% |
| 6 | 0.9149 | 0.5503 | 0.9874 | 0.0653 | 100.0% |
| 9 | 0.8754 | 0.5444 | 0.9893 | 0.0523 | 100.0% |
| 10 | 0.9062 | 0.5745 | 0.9918 | 0.0494 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="gradient-boundary-voting-gradientvote"></a>
<details>
<summary><strong>Gradient Boundary Voting (`gradient_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 10 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 22 |
| Parameter sets evaluated | 22 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 12 (54.5%) |
| Best Avg IoU | 0.9622 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.4725 |
| Winner stabilized after | 14 parameter sets |
| Winner stabilized | 118 ms (67% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (18.2%) |
| Equivalent-best configurations (within 0.0001) | 3 (13.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 22 | 100.0% | 219 ms | 1.0× |
| Non-dormant | 21 | 95.5% | 209 ms | 1.0× |
| Low+ | 21 | 95.5% | 209 ms | 1.0× |
| Moderate+ | 21 | 95.5% | 209 ms | 1.0× |
| Important+ | 21 | 95.5% | 209 ms | 1.0× |
| Critical | 21 | 95.5% | 209 ms | 1.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `border_search_fraction` | Critical | 1.0000 | 0.9622 | 19.0% | `0.13` (0.9622), `0.135` (0.9622), `0.14` (0.9622) | current run |
| `area_weight` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.25` (0.9467) | current run |
| `central_band_fraction` | Dormant | 0.0375 | 0.0000 | 0.0% | `1` (0.9467) | current run |
| `gaussian_sigma` | Dormant | 0.0375 | 0.0000 | 0.0% | `1.2` (0.9467) | current run |
| `gradient_percentile` | Dormant | 0.0375 | 0.0000 | 0.0% | `70` (0.9467) | current run |
| `minimum_area_fraction` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.2` (0.9467) | current run |
| `minimum_span_fraction` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.15` (0.9467) | current run |
| `minimum_vote_support` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.08` (0.9467) | current run |
| `rectangularity_weight` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.2` (0.9467) | current run |
| `support_weight` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.45` (0.9467) | current run |
| `vote_smooth_fraction` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.012` (0.9467) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `central_band_fraction`, `gaussian_sigma`, `gradient_percentile`, `minimum_area_fraction`, `minimum_span_fraction`, `minimum_vote_support`, `rectangularity_weight`, `support_weight`, `vote_smooth_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.5243 | 0.0000 | 0.9613 | 0.4787 | 54.5% |
| 5 | 0.5012 | 0.0000 | 0.9384 | 0.4582 | 54.5% |
| 6 | 0.5394 | 0.0000 | 0.9889 | 0.4924 | 54.5% |
| 9 | 0.4986 | 0.0000 | 0.9612 | 0.4570 | 54.5% |
| 10 | 0.5242 | 0.0000 | 0.9611 | 0.4785 | 54.5% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="radial-edge-search-radialedge"></a>
<details>
<summary><strong>Radial Edge Search (`radial_edge`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 7 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 400001 |
| Parameter sets evaluated | 400001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 400001 (100.0%) |
| Best Avg IoU | 0.9571 |
| Minimum Avg IoU | 0.7182 |
| Avg IoU StdDev | 0.0469 |
| Winner stabilized after | 395128 parameter sets |
| Winner stabilized | 12m 42s (99% of search) |
| Near-best coverage (basin; within 0.0010) | 400 (0.1%) |
| Equivalent-best configurations (within 0.0001) | 200 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 400001 | 100.0% | 3d 13h 51m 54s | 1.0× |
| Non-dormant | 2000 | 0.5% | 25m 46s | 200.0× |
| Low+ | 2000 | 0.5% | 25m 46s | 200.0× |
| Moderate+ | 2000 | 0.5% | 25m 46s | 200.0× |
| Important+ | 25 | 0.0% | 19.3s | 16000.0× |
| Critical | 5 | 0.0% | 3.9s | 80000.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `maximum_radius_fraction` | Critical | 0.5481 | 0.0935 | 40.0% | `0.72` (0.9121), `0.78` (0.9065), `0.84` (0.8979) | current run |
| `minimum_radius_fraction` | Important | 0.1192 | 0.0403 | 40.0% | `0.26` (0.9005), `0.22` (0.8981), `0.18` (0.8732) | current run |
| `ray_count` | Moderate | 0.0770 | 0.0368 | 25.0% | `96` (0.8962), `224` (0.8901), `144` (0.8898) | current run |
| `gaussian_sigma` | Moderate | 0.0614 | 0.0398 | 10.0% | `1.6` (0.8921), `2.4` (0.8903), `2` (0.8865) | current run |
| `gradient_percentile` | Dormant | 0.0001 | 0.0018 | 100.0% | `74` (0.8814), `78` (0.8808), `80` (0.8804) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.35` (0.9503) | current run |
| `maximum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.9503) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.18` (0.9503) | current run |
| `minimum_ray_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8802), `0.35` (0.8802), `0.25` (0.8802) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8802), `0.3` (0.8802) | current run |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8802), `0.35` (0.8802) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`gradient_percentile`, `area_weight`, `maximum_area_fraction`, `minimum_area_fraction`, `minimum_ray_support`, `rectangularity_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_radius_fraction` × `minimum_radius_fraction` | 0.6895 | 0.1416 | 44445 |
| `maximum_radius_fraction` × `gaussian_sigma` | 0.6532 | 0.1053 | 44445 |
| `maximum_radius_fraction` × `ray_count` | 0.6418 | 0.0939 | 44445 |
| `minimum_radius_fraction` × `ray_count` | 0.2079 | 0.0880 | 44445 |
| `ray_count` × `gaussian_sigma` | 0.1539 | 0.0769 | 44445 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8758 | 0.6585 | 0.9786 | 0.0675 | 100.0% |
| 5 | 0.9265 | 0.7115 | 0.9861 | 0.0580 | 100.0% |
| 6 | 0.7966 | 0.4658 | 0.9542 | 0.1005 | 100.0% |
| 9 | 0.8861 | 0.6453 | 0.9849 | 0.0747 | 100.0% |
| 10 | 0.9158 | 0.7679 | 0.9763 | 0.0534 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="segment-supported-polar-voting-segmentsupportedpolarvote"></a>
<details>
<summary><strong>Segment-Supported Polar Voting (`segment_supported_polar_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 5 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 180001 |
| Parameter sets evaluated | 180001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 144000 (80.0%) |
| Best Avg IoU | 0.9470 |
| Minimum Avg IoU | 0.5149 |
| Avg IoU StdDev | 0.0991 |
| Winner stabilized after | 3511 parameter sets |
| Winner stabilized | 22.6s (2% of search) |
| Near-best coverage (basin; within 0.0010) | 38 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 180001 | 100.0% | 4d 13h 22m 46s | 1.0× |
| Non-dormant | 5000 | 2.8% | 3h 2m 18s | 36.0× |
| Low+ | 5000 | 2.8% | 3h 2m 18s | 36.0× |
| Moderate+ | 5 | 0.0% | 10.9s | 36000.2× |
| Important+ | 5 | 0.0% | 10.9s | 36000.2× |
| Critical | 5 | 0.0% | 10.9s | 36000.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_segment_length_fraction` | Critical | 0.9390 | 0.2496 | 20.0% | `0.03` (0.9093), `0.0225` (0.9076), `0.015` (0.9040) | current run |
| `outer_radius_fraction` | Low | 0.0153 | 0.0323 | 20.0% | `0.72` (0.8539), `0.74` (0.8531), `0.76` (0.8520) | current run |
| `gradient_percentile` | Low | 0.0021 | 0.0144 | 20.0% | `92` (0.8491), `90` (0.8480), `88` (0.8453) | current run |
| `ray_count` | Low | 0.0010 | 0.0113 | 50.0% | `72` (0.8483), `54` (0.8445), `60` (0.8436) | current run |
| `segment_distance_fraction` | Dormant | 0.0003 | 0.0053 | 66.7% | `0.0035` (0.8434), `0.005` (0.8428), `0.0065` (0.8426) | current run |
| `inner_radius_fraction` | Dormant | 0.0000 | 0.0014 | 100.0% | `0.1` (0.8421), `0.08` (0.8419), `0.12` (0.8416) | current run |
| `minimum_segment_support_fraction` | Dormant | 0.0000 | 0.1441 | 50.0% | `0.1` (0.8415), `0.3` (0.6974) | current run |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.1441 | 50.0% | `0.2` (0.8415), `0.35` (0.6974) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.8415) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`segment_distance_fraction`, `inner_radius_fraction`, `minimum_segment_support_fraction`, `minimum_support_fraction`, `bbox_padding_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_segment_length_fraction` × `outer_radius_fraction` | 0.9727 | 0.0338 | 45001 |
| `minimum_segment_length_fraction` × `gradient_percentile` | 0.9443 | 0.0054 | 45001 |
| `outer_radius_fraction` × `ray_count` | 0.0194 | 0.0049 | 45001 |
| `minimum_segment_length_fraction` × `ray_count` | 0.9434 | 0.0046 | 45001 |
| `outer_radius_fraction` × `gradient_percentile` | 0.0182 | 0.0037 | 45001 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8629 | 0.0014 | 0.9676 | 0.1319 | 100.0% |
| 5 | 0.6598 | 0.0000 | 0.9808 | 0.3706 | 80.0% |
| 6 | 0.9789 | 0.8244 | 1.0000 | 0.0244 | 100.0% |
| 9 | 0.8090 | 0.7134 | 0.8463 | 0.0353 | 100.0% |
| 10 | 0.8968 | 0.7113 | 0.9654 | 0.0388 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="doc-ufcn-page-mask-detector-docufcnpagemask"></a>
<details>
<summary><strong>Doc-UFCN Page-Mask Detector (`doc_ufcn_page_mask`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2000 |
| Parameter sets evaluated | 2000 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 2000 (100.0%) |
| Best Avg IoU | 0.9371 |
| Minimum Avg IoU | 0.8198 |
| Avg IoU StdDev | 0.0403 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 246 ms (0% of search) |
| Near-best coverage (basin; within 0.0010) | 200 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 200 (10.0%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2000 | 100.0% | 5m 2s | 1.0× |
| Exhaustive | 2000 | 100.0% | 5m 2s | 1.0× |
| Non-dormant | 10 | 0.5% | 1.5s | 200.0× |
| Low+ | 10 | 0.5% | 1.5s | 200.0× |
| Moderate+ | 10 | 0.5% | 1.5s | 200.0× |
| Important+ | 10 | 0.5% | 1.5s | 200.0× |
| Critical | 10 | 0.5% | 1.5s | 200.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `page_padding_fraction` | Critical | 1.0000 | 0.1173 | 10.0% | `0.01` (0.9371), `0` (0.9294), `0.02` (0.9127) | current run |
| `minimum_component_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.8747), `0.0001` (0.8747), `0.0005` (0.8747) | current run |
| `minimum_page_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8747), `0.12` (0.8747), `0.16` (0.8747) | current run |
| `minimum_confidence` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.8747), `0.25` (0.8747), `0.4` (0.8747) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8734 | 0.7782 | 0.9770 | 0.0721 | 100.0% |
| 5 | 0.8038 | 0.7370 | 0.8370 | 0.0325 | 100.0% |
| 6 | 0.9432 | 0.9327 | 0.9899 | 0.0193 | 100.0% |
| 9 | 0.8699 | 0.7569 | 0.9900 | 0.0807 | 100.0% |
| 10 | 0.8832 | 0.7940 | 0.9814 | 0.0653 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="orli-page-mask-orlipagemask"></a>
<details>
<summary><strong>Orli Page Mask (`orli_page_mask`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 1680 |
| Parameter sets evaluated | 1680 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 840 (50.0%) |
| Best Avg IoU | 0.9185 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.4106 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 602 ms (0% of search) |
| Near-best coverage (basin; within 0.0010) | 14 (0.8%) |
| Equivalent-best configurations (within 0.0001) | 7 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 16800 | 100.0% | 1h 3m 58s | 1.0× |
| Exhaustive | 1680 | 10.0% | 6m 24s | 10.0× |
| Non-dormant | 24 | 0.1% | 5.5s | 700.0× |
| Low+ | 24 | 0.1% | 5.5s | 700.0× |
| Moderate+ | 2 | 0.0% | 457 ms | 8400.0× |
| Important+ | 2 | 0.0% | 457 ms | 8400.0× |
| Critical | 2 | 0.0% | 457 ms | 8400.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `include_lines` | Critical | 0.9856 | 0.8153 | 50.0% | `1` (0.8153), `0` (0.0000) | current run |
| `page_padding_fraction` | Low | 0.0070 | 0.1039 | 8.3% | `0.16` (0.4569), `0.14` (0.4540), `0.12` (0.4462) | current run |
| `dilation_fraction` | Dormant | 0.0001 | 0.0108 | 20.0% | `0.06` (0.4146), `0.04` (0.4110), `0.03` (0.4100) | current run |
| `minimum_page_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.4077), `0.06` (0.4077), `0.08` (0.4077) | current run |
| `close_kernel_fraction` | Zombie | 0.0000 | 0.0001 | 100.0% | unknown | retained HTH-0001 10,000-set exhaustive-with-zombies calibration (2026-08-18) |
| `fill_holes` | Zombie | 0.0000 | 0.0000 | 100.0% | unknown | retained HTH-0001 10,000-set exhaustive-with-zombies calibration (2026-08-18) |

*Dormant and Zombie are canonical measured effect-size classifications, not synonyms. Retained rows were not varied in this run: their last compatible audited measurements are shown for visibility only and do not contribute to this run's search-space counts, influence calculations, interactions, or winner selection.*

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`dilation_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `include_lines` × `page_padding_fraction` | 0.9997 | 0.0141 | 1680 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.4034 | 0.0000 | 0.9357 | 0.4074 | 50.0% |
| 5 | 0.4445 | 0.0000 | 0.9580 | 0.4468 | 50.0% |
| 6 | 0.3477 | 0.0000 | 0.8557 | 0.3531 | 50.0% |
| 9 | 0.3848 | 0.0000 | 0.8959 | 0.3901 | 50.0% |
| 10 | 0.4578 | 0.0000 | 0.9834 | 0.4591 | 50.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-segmentation-grabcut"></a>
<details>
<summary><strong>GrabCut Segmentation (`grabcut`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 3 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 13122 |
| Parameter sets evaluated | 13122 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 12515 (95.4%) |
| Best Avg IoU | 0.9137 |
| Minimum Avg IoU | 0.4353 |
| Avg IoU StdDev | 0.0712 |
| Winner stabilized after | 1355 parameter sets |
| Winner stabilized | 6m 3s (10% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13122 | 100.0% | 15d 12h 43m 31s | 1.0× |
| Non-dormant | 486 | 3.7% | 13h 48m 17s | 27.0× |
| Low+ | 486 | 3.7% | 13h 48m 17s | 27.0× |
| Moderate+ | 81 | 0.6% | 2h 18m 3s | 162.0× |
| Important+ | 27 | 0.2% | 46m 1s | 486.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `erosion_iterations` | Important | 0.2068 | 0.0763 | 33.3% | `1` (0.7946), `2` (0.7753), `0` (0.7183) | current run |
| `border_fraction` | Important | 0.1542 | 0.0611 | 33.3% | `0.01` (0.8022), `0.03` (0.7449), `0.02` (0.7411) | current run |
| `grabcut_iterations` | Important | 0.1207 | 0.0547 | 33.3% | `5` (0.7825), `3` (0.7778), `1` (0.7279) | current run |
| `erosion_kernel_fraction` | Moderate | 0.0329 | 0.0316 | 33.3% | `0.0075` (0.7789), `0.015` (0.7620), `0.025` (0.7473) | current run |
| `close_kernel_fraction` | Low | 0.0162 | 0.0209 | 33.3% | `0.01` (0.7711), `0.02` (0.7670), `0.035` (0.7501) | current run |
| `close_iterations` | Low | 0.0107 | 0.0147 | 50.0% | `1` (0.7701), `2` (0.7554) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0009 | 33.3% | `0.15` (0.7633), `0.07` (0.7626), `0.1` (0.7624) | current run |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0006 | 33.3% | `0.03` (0.7630), `0.018` (0.7627), `0.01` (0.7624) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0002 | 33.3% | `0.02` (0.7629), `0.04` (0.7627), `0.07` (0.7626) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `polygon_epsilon_fraction`, `minimum_contour_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `erosion_iterations` × `border_fraction` | 0.4096 | 0.2028 | 13122 |
| `erosion_iterations` × `grabcut_iterations` | 0.3374 | 0.1306 | 13122 |
| `border_fraction` × `grabcut_iterations` | 0.2832 | 0.1291 | 13122 |
| `erosion_iterations` × `erosion_kernel_fraction` | 0.3027 | 0.0959 | 13122 |
| `border_fraction` × `erosion_kernel_fraction` | 0.1964 | 0.0422 | 13122 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8946 | 0.0000 | 0.9904 | 0.2046 | 95.9% |
| 5 | 0.5491 | 0.2980 | 0.9755 | 0.1047 | 100.0% |
| 6 | 0.5056 | 0.0000 | 0.8217 | 0.1758 | 99.2% |
| 9 | 0.9307 | 0.8522 | 0.9433 | 0.0288 | 100.0% |
| 10 | 0.9336 | 0.8355 | 0.9661 | 0.0228 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="contour-quadrilateral-contourquad"></a>
<details>
<summary><strong>Contour Quadrilateral (`contour_quad`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 11 of 13 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 708588 of 1062882 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 1062882 |
| Parameter sets evaluated | 1062882 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 354294 (33.3%) |
| Best Avg IoU | 0.8874 |
| Minimum Avg IoU | 0.5629 |
| Avg IoU StdDev | 0.1192 |
| Winner stabilized after | 1708 parameter sets |
| Winner stabilized | 57.3s (0% of search) |
| Near-best coverage (basin; within 0.0010) | 164754 (15.5%) |
| Equivalent-best configurations (within 0.0001) | 55890 (5.3%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1062882 | 100.0% | 4d 21h 52m 55s | 1.0× |
| Non-dormant | 6 | 0.0% | 2.4s | 177147.0× |
| Low+ | 6 | 0.0% | 2.4s | 177147.0× |
| Moderate+ | 6 | 0.0% | 2.4s | 177147.0× |
| Important+ | 6 | 0.0% | 2.4s | 177147.0× |
| Critical | 6 | 0.0% | 2.4s | 177147.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `merge_fragmented_contours` | Critical | 0.7000 | 0.1995 | 50.0% | `true` (0.8241), `false` (0.6246) | current run |
| `epsilon_max_fraction` | Critical | 0.2737 | 0.1323 | 66.7% | `0.04` (0.7685), `0.06` (0.7685), `0.025` (0.6362) | current run |
| `close_kernel_fraction` | Dormant | 0.0001 | 0.0027 | 100.0% | `0.018` (0.7260), `0.008` (0.7237), `0` (0.7233) | current run |
| `close_iterations` | Dormant | 0.0001 | 0.0025 | 100.0% | `2` (0.7259), `1` (0.7238), `0` (0.7233) | current run |
| `edge_support_weight` | Dormant | 0.0001 | 0.0024 | 100.0% | `0.25` (0.7256), `0.15` (0.7242), `0.1` (0.7233) | current run |
| `edge_support_dilation_fraction` | Dormant | 0.0001 | 0.0022 | 100.0% | `0.008` (0.7256), `0.004` (0.7240), `0.002` (0.7234) | current run |
| `area_weight` | Dormant | 0.0001 | 0.0021 | 100.0% | `0.25` (0.7255), `0.35` (0.7242), `0.45` (0.7234) | current run |
| `angle_weight` | Dormant | 0.0000 | 0.0012 | 100.0% | `0.3` (0.7249), `0.2` (0.7244), `0.1` (0.7237) | current run |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.004` (0.7244), `0.008` (0.7244), `0.012` (0.7244) | current run |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 100.0% | `13` (0.7244), `5` (0.7244), `9` (0.7244) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.06` (0.7244), `0.12` (0.7244), `0.2` (0.7244) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.7244), `0.55` (0.7244), `0.7` (0.7244) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.7244), `0.3` (0.7244), `0.4` (0.7244) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_kernel_fraction`, `close_iterations`, `edge_support_weight`, `edge_support_dilation_fraction`, `area_weight`, `angle_weight`, `epsilon_min_fraction`, `epsilon_steps`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `rectangularity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `merge_fragmented_contours` × `epsilon_max_fraction` | 0.9988 | 0.2987 | 48313 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8921 | 0.8383 | 0.9069 | 0.0233 | 100.0% |
| 5 | 0.4410 | 0.0000 | 0.8618 | 0.3522 | 66.7% |
| 6 | 0.3795 | 0.0000 | 0.7589 | 0.3795 | 50.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="learned-page-mask-detector-learnedpagemask"></a>
<details>
<summary><strong>Learned Page-Mask Detector (`learned_page_mask`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 5 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 50000 |
| Parameter sets evaluated | 50000 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 50000 (100.0%) |
| Best Avg IoU | 0.8868 |
| Minimum Avg IoU | 0.8158 |
| Avg IoU StdDev | 0.0066 |
| Winner stabilized after | 22390 parameter sets |
| Winner stabilized | 35m 56s (45% of search) |
| Near-best coverage (basin; within 0.0010) | 510 (1.0%) |
| Equivalent-best configurations (within 0.0001) | 56 (0.1%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 50000 | 100.0% | 21d 6h 42m 26s | 1.0× |
| Non-dormant | 25000 | 50.0% | 10d 15h 21m 13s | 2.0× |
| Low+ | 25000 | 50.0% | 10d 15h 21m 13s | 2.0× |
| Moderate+ | 12500 | 25.0% | 5d 7h 40m 36s | 4.0× |
| Important+ | 12500 | 25.0% | 5d 7h 40m 36s | 4.0× |
| Critical | 625 | 1.2% | 6h 23m 2s | 80.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `bbox_padding_fraction` | Critical | 0.2994 | 0.0184 | 52.0% | `0.027` (0.8788), `0.028` (0.8788), `0.029` (0.8788) | current run |
| `mask_threshold` | Critical | 0.2921 | 0.0175 | 28.0% | `0.214` (0.8789), `0.21` (0.8789), `0.212` (0.8788) | current run |
| `polygon_epsilon_fraction` | Important | 0.1620 | 0.0076 | 55.0% | `0.0195` (0.8805), `0.019` (0.8803), `0.02` (0.8802) | current run |
| `close_kernel_fraction` | Low | 0.0041 | 0.0009 | 100.0% | `0` (0.8768), `0.006` (0.8759) | current run |
| `minimum_mask_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8763), `0.15` (0.8763) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_mask_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `bbox_padding_fraction` × `mask_threshold` | 0.6362 | 0.3368 | 50000 |
| `mask_threshold` × `polygon_epsilon_fraction` | 0.5219 | 0.2298 | 50000 |
| `bbox_padding_fraction` × `polygon_epsilon_fraction` | 0.5259 | 0.2265 | 50000 |
| `polygon_epsilon_fraction` × `close_kernel_fraction` | 0.1866 | 0.0246 | 50000 |
| `mask_threshold` × `close_kernel_fraction` | 0.3115 | 0.0194 | 50000 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8951 | 0.8593 | 0.9528 | 0.0228 | 100.0% |
| 5 | 0.9143 | 0.9021 | 0.9242 | 0.0065 | 100.0% |
| 6 | 0.8066 | 0.7029 | 0.8221 | 0.0191 | 100.0% |
| 9 | 0.8410 | 0.7701 | 0.8587 | 0.0146 | 100.0% |
| 10 | 0.9247 | 0.8240 | 0.9511 | 0.0193 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-contour-grabcutcontour"></a>
<details>
<summary><strong>GrabCut + Contour (`grabcut_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 14 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 46657 |
| Parameter sets evaluated | 46657 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 46657 (100.0%) |
| Best Avg IoU | 0.8781 |
| Minimum Avg IoU | 0.7426 |
| Avg IoU StdDev | 0.0452 |
| Winner stabilized after | 294 parameter sets |
| Winner stabilized | 2m 18s (1% of search) |
| Near-best coverage (basin; within 0.0010) | 2916 (6.2%) |
| Equivalent-best configurations (within 0.0001) | 2916 (6.2%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 46657 | 100.0% | 39d 23h 10m 57s | 1.0× |
| Non-dormant | 8 | 0.0% | 9m 52s | 5832.1× |
| Low+ | 8 | 0.0% | 9m 52s | 5832.1× |
| Moderate+ | 8 | 0.0% | 9m 52s | 5832.1× |
| Important+ | 2 | 0.0% | 2m 28s | 23328.5× |
| Critical | 2 | 0.0% | 2m 28s | 23328.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `grabcut_erosion_kernel_fraction` | Critical | 0.8010 | 0.0808 | 50.0% | `0.015` (0.8286), `0.025` (0.7478) | current run |
| `grabcut_border_fraction` | Moderate | 0.0441 | 0.0190 | 50.0% | `0.02` (0.7977), `0.03` (0.7787) | current run |
| `grabcut_iterations` | Moderate | 0.0393 | 0.0179 | 50.0% | `5` (0.7972), `3` (0.7793) | current run |
| `contour_epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.04` (0.8130) | current run |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.8130) | current run |
| `grabcut_close_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.8130) | current run |
| `grabcut_erosion_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.8130) | current run |
| `grabcut_minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.1` (0.8130) | current run |
| `grabcut_close_kernel_fraction` | Dormant | 0.0000 | 0.0002 | 50.0% | `0.03` (0.7883), `0.02` (0.7881) | current run |
| `agreement_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.7882), `0.15` (0.7882), `0.35` (0.7882) | current run |
| `grabcut_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.7882), `0.45` (0.7882), `0.65` (0.7882) | current run |
| `contour_minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.7882), `0.08` (0.7882), `0.18` (0.7882) | current run |
| `contour_minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.7882), `0.45` (0.7882), `0.7` (0.7882) | current run |
| `grabcut_polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.018` (0.7882), `0.01` (0.7882), `0.03` (0.7882) | current run |
| `minimum_agreement_iou` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.7882), `0.05` (0.7882), `0.3` (0.7882) | current run |
| `grabcut_minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.7882), `0.08` (0.7882) | current run |
| `require_contour` | Dormant | 0.0000 | 0.0000 | 100.0% | `false` (0.7882), `true` (0.7882) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_epsilon_max_fraction`, `contour_weight`, `grabcut_close_iterations`, `grabcut_erosion_iterations`, `grabcut_minimum_bbox_area_fraction`, `grabcut_close_kernel_fraction`, `agreement_weight`, `grabcut_weight`, `contour_minimum_area_fraction`, `contour_minimum_rectangularity`, `grabcut_polygon_epsilon_fraction`, `minimum_agreement_iou`, `grabcut_minimum_contour_area_fraction`, `require_contour`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `grabcut_erosion_kernel_fraction` × `grabcut_iterations` | 0.8810 | 0.0800 | 46657 |
| `grabcut_border_fraction` × `grabcut_iterations` | 0.1176 | 0.0735 | 46657 |
| `grabcut_erosion_kernel_fraction` × `grabcut_border_fraction` | 0.8696 | 0.0686 | 46657 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9517 | 0.9467 | 0.9568 | 0.0041 | 100.0% |
| 5 | 0.5973 | 0.5532 | 0.8348 | 0.0889 | 100.0% |
| 6 | 0.5077 | 0.3232 | 0.7198 | 0.1781 | 100.0% |
| 9 | 0.9425 | 0.9422 | 0.9433 | 0.0005 | 100.0% |
| 10 | 0.9418 | 0.9389 | 0.9447 | 0.0029 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="cross-edge-contour-crossedgecontour"></a>
<details>
<summary><strong>Cross-Edge Contour (`cross_edge_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 7 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 4617 of 6562 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 1945 (29.6%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.3818 |
| Avg IoU StdDev | 0.2038 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1945 (29.6%) |
| Equivalent-best configurations (within 0.0001) | 1945 (29.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 23m 21s | 1.0× |
| Non-dormant | 36 | 0.5% | 7.7s | 182.3× |
| Low+ | 36 | 0.5% | 7.7s | 182.3× |
| Moderate+ | 4 | 0.1% | 854 ms | 1640.5× |
| Important+ | 4 | 0.1% | 854 ms | 1640.5× |
| Critical | 4 | 0.1% | 854 ms | 1640.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_polarity_consistency` | Critical | 0.9288 | 0.4950 | 50.0% | `0.55` (0.8768), `0.5` (0.8600), `0.65` (0.6676) | current run |
| `sample_offset_fraction` | Low | 0.0296 | 0.0744 | 100.0% | `0.008` (0.6613), `0.014` (0.6612), `0.004` (0.5869) | current run |
| `minimum_cross_edge_contrast` | Low | 0.0015 | 0.0170 | 100.0% | `0.045` (0.6422), `0.02` (0.6421), `0.08` (0.6252) | current run |
| `contour_weight` | Dormant | 0.0002 | 0.0000 | 100.0% | `0.45` (0.8768) | current run |
| `polarity_weight` | Dormant | 0.0002 | 0.0000 | 100.0% | `0.15` (0.8768) | current run |
| `contrast_weight` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.4` (0.6366), `0.3` (0.6365), `0.5` (0.6365) | current run |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.04` (0.6366), `0.03` (0.6365), `0.06` (0.6365) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.12` (0.6366), `0.08` (0.6365), `0.18` (0.6365) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.55` (0.6366), `0.45` (0.6365), `0.7` (0.6365) | current run |
| `samples_per_edge` | Dormant | 0.0000 | 0.0001 | 100.0% | `48` (0.6366), `24` (0.6365), `72` (0.6365) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_weight`, `polarity_weight`, `contrast_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `samples_per_edge`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_polarity_consistency` × `sample_offset_fraction` | 0.9863 | 0.0575 | 6562 |
| `sample_offset_fraction` × `minimum_cross_edge_contrast` | 0.0341 | 0.0046 | 6562 |
| `minimum_polarity_consistency` × `minimum_cross_edge_contrast` | 0.9334 | 0.0046 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.5695 | 0.0000 | 0.8542 | 0.4027 | 66.7% |
| 5 | 0.4788 | 0.0000 | 0.8618 | 0.4282 | 55.6% |
| 6 | 0.2249 | 0.0000 | 0.7589 | 0.3466 | 29.6% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="contour-projection-contourprojection"></a>
<details>
<summary><strong>Contour + Projection (`contour_projection`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- 12 of 16 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 6562 (100.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.7946 |
| Avg IoU StdDev | 0.0215 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 6076 (92.6%) |
| Equivalent-best configurations (within 0.0001) | 6076 (92.6%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 50m 5s | 1.0× |
| Non-dormant | 81 | 1.2% | 37.1s | 81.0× |
| Low+ | 81 | 1.2% | 37.1s | 81.0× |
| Moderate+ | 27 | 0.4% | 12.4s | 243.0× |
| Important+ | 3 | 0.0% | 1.4s | 2187.3× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `projection_threshold_block_fraction` | Important | 0.1600 | 0.0183 | 100.0% | `0.05` (0.8768), `0.08` (0.8768), `0.12` (0.8586) | current run |
| `projection_weight` | Moderate | 0.0933 | 0.0152 | 100.0% | `0.2` (0.8768), `0.3` (0.8738), `0.4` (0.8616) | current run |
| `projection_threshold_c` | Moderate | 0.0400 | 0.0091 | 100.0% | `13` (0.8738), `5` (0.8738), `9` (0.8646) | current run |
| `projection_margin_fraction` | Low | 0.0133 | 0.0061 | 100.0% | `0.06` (0.8738), `0.1` (0.8707), `0.03` (0.8677) | current run |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) | current run |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8768) | current run |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) | current run |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) | current run |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 100.0% | `9` (0.8768) | current run |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 100.0% | `true` (0.8768) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) | current run |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8707), `0.03` (0.8707), `0.06` (0.8707) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.8707), `0.08` (0.8707), `0.18` (0.8707) | current run |
| `minimum_projection_score` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8707), `0.05` (0.8707), `0.15` (0.8707) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.8707), `0.45` (0.8707), `0.7` (0.8707) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_projection_score`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `projection_threshold_block_fraction` × `projection_weight` | 0.4400 | 0.2800 | 6562 |
| `projection_threshold_block_fraction` × `projection_threshold_c` | 0.2800 | 0.1200 | 6562 |
| `projection_weight` × `projection_threshold_c` | 0.1600 | 0.0666 | 6562 |
| `projection_threshold_c` × `projection_margin_fraction` | 0.0800 | 0.0400 | 6562 |
| `projection_threshold_block_fraction` × `projection_margin_fraction` | 0.2000 | 0.0400 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8542 | 0.8542 | 0.8542 | 0.0000 | 100.0% |
| 5 | 0.8313 | 0.4508 | 0.8618 | 0.1076 | 100.0% |
| 6 | 0.7589 | 0.7589 | 0.7589 | 0.0000 | 100.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="edge-supported-contour-edgecontour"></a>
<details>
<summary><strong>Edge-Supported Contour (`edge_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 12 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 11503 of 13123 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 13123 |
| Parameter sets evaluated | 13123 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 1620 (12.3%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.2495 |
| Winner stabilized after | 27 parameter sets |
| Winner stabilized | 1.5s (0% of search) |
| Near-best coverage (basin; within 0.0010) | 1134 (8.6%) |
| Equivalent-best configurations (within 0.0001) | 1134 (8.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13123 | 100.0% | 3h 46m 46s | 1.0× |
| Non-dormant | 162 | 1.2% | 2m 48s | 81.0× |
| Low+ | 162 | 1.2% | 2m 48s | 81.0× |
| Moderate+ | 162 | 1.2% | 2m 48s | 81.0× |
| Important+ | 81 | 0.6% | 1m 24s | 162.0× |
| Critical | 3 | 0.0% | 3.1s | 4374.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_edge_support` | Critical | 0.3207 | 0.3412 | 66.7% | `0.05` (0.6504), `0.12` (0.4293), `0.2` (0.3092) | current run |
| `edge_support_dilation_fraction` | Important | 0.1807 | 0.2557 | 100.0% | `0.01` (0.5775), `0.006` (0.4895), `0.003` (0.3218) | current run |
| `minimum_segment_length_fraction` | Important | 0.1417 | 0.2229 | 33.3% | `0.03` (0.5908), `0.06` (0.4301), `0.1` (0.3679) | current run |
| `lsd_scale` | Important | 0.1119 | 0.1922 | 66.7% | `0.6` (0.5390), `0.8` (0.5031), `1` (0.3468) | current run |
| `lsd_refine_mode` | Moderate | 0.0518 | 0.1136 | 100.0% | `none` (0.5197), `std` (0.4062) | current run |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.5392) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.5392) | current run |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.5392) | current run |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.5392) | current run |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.5392) | current run |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 0.0% | `9` (0.5392) | current run |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 0.0% | `true` (0.5392) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.5392) | current run |
| `edge_support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.3` (0.4630), `0.2` (0.4629), `0.4` (0.4629) | current run |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.4630), `0.03` (0.4629), `0.06` (0.4629) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.4630), `0.08` (0.4629), `0.18` (0.4629) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.4630), `0.45` (0.4629), `0.7` (0.4629) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`, `edge_support_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_edge_support` × `edge_support_dilation_fraction` | 0.5279 | 0.2072 | 13123 |
| `minimum_edge_support` × `minimum_segment_length_fraction` | 0.4739 | 0.1532 | 13123 |
| `edge_support_dilation_fraction` × `minimum_segment_length_fraction` | 0.3245 | 0.1438 | 13123 |
| `edge_support_dilation_fraction` × `lsd_scale` | 0.2965 | 0.1158 | 13123 |
| `minimum_segment_length_fraction` × `lsd_scale` | 0.2562 | 0.1145 | 13123 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.2478 | 0.0000 | 0.8542 | 0.3877 | 29.0% |
| 5 | 0.4735 | 0.0000 | 0.8618 | 0.4288 | 54.9% |
| 6 | 0.0937 | 0.0000 | 0.7589 | 0.2496 | 12.3% |
| 9 | 0.9281 | 0.0000 | 0.9638 | 0.1820 | 96.3% |
| 10 | 0.5717 | 0.0000 | 0.9454 | 0.4278 | 64.2% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="contour-grabcut-contourgrabcut"></a>
<details>
<summary><strong>Contour + GrabCut (`contour_grabcut`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- Every measured parameter was dormant for this Golden Set and grid.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 6562 (100.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.8768 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 6562 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 6562 (100.0%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 2d 3h 40m 13s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `agreement_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) | current run |
| `contour_epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768), `0.06` (0.8768) | current run |
| `contour_minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768), `0.18` (0.8768) | current run |
| `contour_minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768), `0.7` (0.8768) | current run |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768) | current run |
| `grabcut_border_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.01` (0.8768), `0.02` (0.8768), `0.03` (0.8768) | current run |
| `grabcut_erosion_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8768) | current run |
| `grabcut_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8768), `3` (0.8768), `5` (0.8768) | current run |
| `grabcut_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.25` (0.8768), `0.35` (0.8768) | current run |
| `minimum_agreement_iou` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.3` (0.8768), `0.5` (0.8768) | current run |
| `require_grabcut` | Dormant | 0.0000 | 0.0000 | 100.0% | `false` (0.8768) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`agreement_weight`, `contour_epsilon_max_fraction`, `contour_minimum_area_fraction`, `contour_minimum_rectangularity`, `contour_weight`, `grabcut_border_fraction`, `grabcut_erosion_kernel_fraction`, `grabcut_iterations`, `grabcut_weight`, `minimum_agreement_iou`, `require_grabcut`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8542 | 0.8542 | 0.8542 | 0.0000 | 100.0% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.7589 | 0.7589 | 0.7589 | 0.0000 | 100.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="contour-components-contourcomponents"></a>
<details>
<summary><strong>Contour + Components (`contour_components`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- Every measured parameter was dormant for this Golden Set and grid.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 19684 |
| Parameter sets evaluated | 19684 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 19684 (100.0%) |
| Best Avg IoU | 0.8617 |
| Minimum Avg IoU | 0.8617 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 19684 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 19684 (100.0%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19684 | 100.0% | 19m 37s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `component_close_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.004` (0.8617), `0.012` (0.8617), `0.008` (0.8617) | current run |
| `component_dilate_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.008` (0.8617), `0.025` (0.8617), `0.015` (0.8617) | current run |
| `component_merge_gap_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.06` (0.8617), `0.035` (0.8617) | current run |
| `component_minimum_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.0008` (0.8617), `0.003` (0.8617), `0.0015` (0.8617) | current run |
| `component_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.25` (0.8617), `0.55` (0.8617), `0.4` (0.8617) | current run |
| `epsilon_max_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8617), `0.06` (0.8617), `0.04` (0.8617) | current run |
| `minimum_component_score` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.12` (0.8617), `0.05` (0.8617) | current run |
| `minimum_contour_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.08` (0.8617), `0.18` (0.8617), `0.12` (0.8617) | current run |
| `minimum_rectangularity` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.45` (0.8617), `0.7` (0.8617), `0.55` (0.8617) | current run |
| `angle_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.15` (0.8617) | current run |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.25` (0.8617) | current run |
| `close_iterations` | Dormant | 0.0001 | 0.0000 | 100.0% | `1` (0.8617) | current run |
| `close_kernel_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.008` (0.8617) | current run |
| `component_bbox_padding_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0` (0.8617) | current run |
| `component_merge_area_ratio` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.02` (0.8617) | current run |
| `component_minimum_area_px` | Dormant | 0.0001 | 0.0000 | 100.0% | `25` (0.8617) | current run |
| `component_minimum_bbox_area_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.12` (0.8617) | current run |
| `component_minimum_selected_area_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.04` (0.8617) | current run |
| `epsilon_min_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.008` (0.8617) | current run |
| `epsilon_steps` | Dormant | 0.0001 | 0.0000 | 100.0% | `9` (0.8617) | current run |
| `merge_fragmented_contours` | Dormant | 0.0001 | 0.0000 | 100.0% | `true` (0.8617) | current run |
| `rectangularity_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.2` (0.8617) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`component_close_fraction`, `component_dilate_fraction`, `component_merge_gap_fraction`, `component_minimum_area_fraction`, `component_weight`, `epsilon_max_fraction`, `minimum_component_score`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `component_bbox_padding_fraction`, `component_merge_area_ratio`, `component_minimum_area_px`, `component_minimum_bbox_area_fraction`, `component_minimum_selected_area_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8540 | 0.8540 | 0.8540 | 0.0000 | 100.0% |
| 5 | 0.8616 | 0.8616 | 0.8616 | 0.0000 | 100.0% |
| 6 | 0.7572 | 0.7572 | 0.7572 | 0.0000 | 100.0% |
| 9 | 0.9636 | 0.9636 | 0.9636 | 0.0000 | 100.0% |
| 10 | 0.8719 | 0.8719 | 0.8719 | 0.0000 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="contour-envelope-contour"></a>
<details>
<summary><strong>Contour Envelope (`contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 5 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 1458 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 729 (50.0%) |
| Best Avg IoU | 0.8498 |
| Minimum Avg IoU | 0.6586 |
| Avg IoU StdDev | 0.0847 |
| Winner stabilized after | 150 parameter sets |
| Winner stabilized | 468 ms (10% of search) |
| Near-best coverage (basin; within 0.0010) | 27 (1.9%) |
| Equivalent-best configurations (within 0.0001) | 27 (1.9%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1458 | 100.0% | 50.1s | 1.0× |
| Non-dormant | 6 | 0.4% | 206 ms | 243.0× |
| Low+ | 6 | 0.4% | 206 ms | 243.0× |
| Moderate+ | 2 | 0.1% | 69 ms | 729.0× |
| Important+ | 2 | 0.1% | 69 ms | 729.0× |
| Critical | 2 | 0.1% | 69 ms | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `merge_fragmented_contours` | Critical | 0.9954 | 0.1691 | 50.0% | `true` (0.8377), `false` (0.6686) | current run |
| `bbox_padding_fraction` | Low | 0.0023 | 0.0091 | 33.3% | `0.005` (0.7565), `0` (0.7555), `0.015` (0.7474) | current run |
| `close_iterations` | Dormant | 0.0004 | 0.0035 | 33.3% | `2` (0.7555), `0` (0.7519), `1` (0.7519) | current run |
| `close_kernel_fraction` | Dormant | 0.0004 | 0.0035 | 33.3% | `0.018` (0.7555), `0` (0.7519), `0.008` (0.7519) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.06` (0.7531), `0.12` (0.7531), `0.2` (0.7531) | current run |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.7531), `0.018` (0.7531), `0.035` (0.7531) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.7531), `0.25` (0.7531), `0.4` (0.7531) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_iterations`, `close_kernel_fraction`, `minimum_contour_area_fraction`, `polygon_epsilon_fraction`, `rectangularity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `merge_fragmented_contours` × `bbox_padding_fraction` | 0.9984 | 0.0030 | 1458 |
| `close_iterations` × `close_kernel_fraction` | 0.0015 | 0.0012 | 1458 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9638 | 0.9533 | 0.9734 | 0.0082 | 100.0% |
| 5 | 0.5020 | 0.4784 | 0.5725 | 0.0236 | 100.0% |
| 6 | 0.4227 | 0.0000 | 0.8763 | 0.4231 | 50.0% |
| 9 | 0.9331 | 0.9018 | 0.9585 | 0.0235 | 100.0% |
| 10 | 0.9439 | 0.9192 | 0.9593 | 0.0171 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="kraken-page-mask-krakenpagemask"></a>
<details>
<summary><strong>Kraken Page Mask (`kraken_page_mask`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 3 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 10000 |
| Parameter sets evaluated | 10000 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 10000 (100.0%) |
| Best Avg IoU | 0.8396 |
| Minimum Avg IoU | 0.7728 |
| Avg IoU StdDev | 0.0205 |
| Winner stabilized after | 252 parameter sets |
| Winner stabilized | 474 ms (3% of search) |
| Near-best coverage (basin; within 0.0010) | 100 (1.0%) |
| Equivalent-best configurations (within 0.0001) | 40 (0.4%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 10000 | 100.0% | 8m 56s | 1.0× |
| Non-dormant | 200 | 2.0% | 10.7s | 50.0× |
| Low+ | 200 | 2.0% | 10.7s | 50.0× |
| Moderate+ | 100 | 1.0% | 5.4s | 100.0× |
| Important+ | 10 | 0.1% | 536 ms | 1000.0× |
| Critical | 10 | 0.1% | 536 ms | 1000.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `page_padding_fraction` | Critical | 0.8934 | 0.0588 | 10.0% | `0` (0.8336), `0.01` (0.8303), `0.02` (0.8232) | current run |
| `dilation_fraction` | Moderate | 0.0771 | 0.0183 | 20.0% | `0` (0.8108), `0.0025` (0.8103), `0.005` (0.8100) | current run |
| `include_lines` | Low | 0.0036 | 0.0025 | 50.0% | `1` (0.8067), `0` (0.8042) | current run |
| `close_kernel_fraction` | Dormant | 0.0002 | 0.0008 | 100.0% | `0.012` (0.8058), `0.006` (0.8056), `0.003` (0.8055) | current run |
| `fill_holes` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.8055), `1` (0.8055) | current run |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8055), `0.12` (0.8055), `0.16` (0.8055) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_kernel_fraction`, `fill_holes`, `minimum_page_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `page_padding_fraction` × `dilation_fraction` | 0.9908 | 0.0974 | 10000 |
| `page_padding_fraction` × `include_lines` | 0.8981 | 0.0047 | 10000 |
| `dilation_fraction` × `include_lines` | 0.0808 | 0.0037 | 10000 |
| `dilation_fraction` × `close_kernel_fraction` | 0.0791 | 0.0020 | 10000 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8743 | 0.7782 | 0.9788 | 0.0598 | 100.0% |
| 5 | 0.6190 | 0.5226 | 0.6752 | 0.0432 | 100.0% |
| 6 | 0.8293 | 0.7560 | 0.8855 | 0.0306 | 100.0% |
| 9 | 0.8410 | 0.7399 | 0.9622 | 0.0647 | 100.0% |
| 10 | 0.8637 | 0.7940 | 0.9599 | 0.0505 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="distance-transform-detector-distancetransform"></a>
<details>
<summary><strong>Distance Transform Detector (`distance_transform`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 2187 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 1119 (51.2%) |
| Best Avg IoU | 0.8388 |
| Minimum Avg IoU | 0.6568 |
| Avg IoU StdDev | 0.0728 |
| Winner stabilized after | 47 parameter sets |
| Winner stabilized | 5.1s (2% of search) |
| Near-best coverage (basin; within 0.0010) | 144 (6.6%) |
| Equivalent-best configurations (within 0.0001) | 144 (6.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 1h 29m 58s | 1.0× |
| Non-dormant | 729 | 33.3% | 29m 59s | 3.0× |
| Low+ | 729 | 33.3% | 29m 59s | 3.0× |
| Moderate+ | 81 | 3.7% | 3m 20s | 27.0× |
| Important+ | 9 | 0.4% | 22.2s | 243.0× |
| Critical | 3 | 0.1% | 7.4s | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `distance_threshold_fraction` | Critical | 0.5293 | 0.1276 | 33.3% | `0.1` (0.8039), `0.18` (0.7195), `0.3` (0.6763) | current run |
| `minimum_core_area_fraction` | Important | 0.1010 | 0.0534 | 100.0% | `0.004` (0.7545), `0.01` (0.7442), `0.025` (0.7011) | current run |
| `minimum_rectangularity` | Moderate | 0.0335 | 0.0283 | 100.0% | `0.35` (0.7427), `0.5` (0.7427), `0.7` (0.7144) | current run |
| `minimum_component_core_overlap` | Moderate | 0.0319 | 0.0289 | 66.7% | `0.03` (0.7438), `0.08` (0.7410), `0.16` (0.7149) | current run |
| `close_kernel_fraction` | Low | 0.0160 | 0.0215 | 100.0% | `0.016` (0.7421), `0.008` (0.7371), `0` (0.7205) | current run |
| `bbox_padding_fraction` | Low | 0.0042 | 0.0102 | 33.3% | `0` (0.7367), `0.008` (0.7364), `0.016` (0.7266) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0004 | 100.0% | `0.1` (0.7335), `0.16` (0.7331), `0.24` (0.7331) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `distance_threshold_fraction` × `minimum_core_area_fraction` | 0.6662 | 0.1368 | 2187 |
| `distance_threshold_fraction` × `close_kernel_fraction` | 0.5805 | 0.0512 | 2187 |
| `minimum_core_area_fraction` × `minimum_rectangularity` | 0.1466 | 0.0456 | 2187 |
| `minimum_rectangularity` × `minimum_component_core_overlap` | 0.0763 | 0.0428 | 2187 |
| `minimum_core_area_fraction` × `minimum_component_core_overlap` | 0.1420 | 0.0411 | 2187 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9626 | 0.9496 | 0.9734 | 0.0098 | 100.0% |
| 5 | 0.4994 | 0.4784 | 0.5197 | 0.0169 | 100.0% |
| 6 | 0.3357 | 0.0000 | 0.8772 | 0.3635 | 51.2% |
| 9 | 0.9281 | 0.8982 | 0.9585 | 0.0246 | 100.0% |
| 10 | 0.9404 | 0.9165 | 0.9593 | 0.0178 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="star-convex-boundary-optimization-starconvex"></a>
<details>
<summary><strong>Star-Convex Boundary Optimization (`star_convex`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 729 (100.0%) |
| Best Avg IoU | 0.8179 |
| Minimum Avg IoU | 0.7309 |
| Avg IoU StdDev | 0.0213 |
| Winner stabilized after | 719 parameter sets |
| Winner stabilized | 6.8s (99% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (0.4%) |
| Equivalent-best configurations (within 0.0001) | 3 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 46m 14s | 1.0× |
| Non-dormant | 243 | 33.3% | 15m 25s | 3.0× |
| Low+ | 243 | 33.3% | 15m 25s | 3.0× |
| Moderate+ | 27 | 3.7% | 1m 43s | 27.0× |
| Important+ | 3 | 0.4% | 11.4s | 243.0× |
| Critical | 3 | 0.4% | 11.4s | 243.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `smoothing_window` | Critical | 0.6484 | 0.0365 | 33.3% | `1` (0.8009), `9` (0.7645), `5` (0.7644) | current run |
| `maximum_radius_fraction` | Moderate | 0.0970 | 0.0150 | 33.3% | `0.6` (0.7822), `0.72` (0.7803), `0.84` (0.7673) | current run |
| `bbox_padding_fraction` | Moderate | 0.0312 | 0.0084 | 33.3% | `0` (0.7797), `0.008` (0.7788), `0.016` (0.7713) | current run |
| `ray_count` | Low | 0.0171 | 0.0065 | 33.3% | `360` (0.7804), `180` (0.7755), `90` (0.7739) | current run |
| `minimum_radius_fraction` | Low | 0.0053 | 0.0034 | 33.3% | `0.16` (0.7788), `0.05` (0.7756), `0.1` (0.7754) | current run |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.7766), `0.55` (0.7766), `0.7` (0.7766) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `smoothing_window` × `maximum_radius_fraction` | 0.8276 | 0.1793 | 729 |
| `maximum_radius_fraction` × `ray_count` | 0.1744 | 0.0774 | 729 |
| `smoothing_window` × `ray_count` | 0.6890 | 0.0407 | 729 |
| `maximum_radius_fraction` × `bbox_padding_fraction` | 0.1305 | 0.0335 | 729 |
| `smoothing_window` × `bbox_padding_fraction` | 0.6799 | 0.0315 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9437 | 0.8260 | 0.9917 | 0.0502 | 100.0% |
| 5 | 0.5759 | 0.5286 | 0.6053 | 0.0208 | 100.0% |
| 6 | 0.5139 | 0.3465 | 0.8804 | 0.1373 | 100.0% |
| 9 | 0.9260 | 0.8888 | 0.9601 | 0.0244 | 100.0% |
| 10 | 0.9235 | 0.8454 | 0.9738 | 0.0386 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="connected-components-components"></a>
<details>
<summary><strong>Connected Components (`components`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 19683 |
| Parameter sets evaluated | 19683 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 14916 (75.8%) |
| Best Avg IoU | 0.7897 |
| Minimum Avg IoU | 0.6456 |
| Avg IoU StdDev | 0.0411 |
| Winner stabilized after | 249 parameter sets |
| Winner stabilized | 578 ms (1% of search) |
| Near-best coverage (basin; within 0.0010) | 162 (0.8%) |
| Equivalent-best configurations (within 0.0001) | 162 (0.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19683 | 100.0% | 6m 54s | 1.0× |
| Non-dormant | 2187 | 11.1% | 46s | 9.0× |
| Low+ | 2187 | 11.1% | 46s | 9.0× |
| Moderate+ | 243 | 1.2% | 5.1s | 81.0× |
| Important+ | 3 | 0.0% | 63 ms | 6561.0× |
| Critical | 3 | 0.0% | 63 ms | 6561.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `morphology_dilate_fraction` | Critical | 0.4776 | 0.0693 | 33.3% | `0.03` (0.7658), `0.015` (0.7266), `0.008` (0.6965) | current run |
| `merge_gap_fraction` | Moderate | 0.0940 | 0.0269 | 66.7% | `0.06` (0.7474), `0.035` (0.7209), `0.02` (0.7206) | current run |
| `minimum_selected_area_fraction` | Moderate | 0.0620 | 0.0217 | 100.0% | `0.02` (0.7369), `0.04` (0.7369), `0.07` (0.7152) | current run |
| `minimum_component_area_fraction` | Moderate | 0.0371 | 0.0179 | 33.3% | `0.00075` (0.7408), `0.0015` (0.7253), `0.003` (0.7229) | current run |
| `bbox_padding_fraction` | Moderate | 0.0362 | 0.0183 | 33.3% | `0` (0.7373), `0.005` (0.7328), `0.015` (0.7189) | current run |
| `merge_area_ratio` | Low | 0.0259 | 0.0161 | 33.3% | `0.01` (0.7372), `0.02` (0.7306), `0.05` (0.7211) | current run |
| `morphology_close_fraction` | Low | 0.0120 | 0.0096 | 100.0% | `0.016` (0.7360), `0.004` (0.7265), `0.008` (0.7265) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.7297), `0.12` (0.7296), `0.18` (0.7296) | current run |
| `minimum_component_area_px` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.7296), `25` (0.7296), `50` (0.7296) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `minimum_component_area_px`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `morphology_dilate_fraction` × `merge_gap_fraction` | 0.6172 | 0.1395 | 19683 |
| `morphology_dilate_fraction` × `minimum_selected_area_fraction` | 0.5739 | 0.0963 | 19683 |
| `merge_gap_fraction` × `minimum_selected_area_fraction` | 0.1561 | 0.0622 | 19683 |
| `morphology_dilate_fraction` × `minimum_component_area_fraction` | 0.5294 | 0.0517 | 19683 |
| `merge_gap_fraction` × `minimum_component_area_fraction` | 0.1353 | 0.0414 | 19683 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9491 | 0.9018 | 0.9734 | 0.0235 | 100.0% |
| 5 | 0.5487 | 0.4892 | 0.5929 | 0.0340 | 100.0% |
| 6 | 0.3305 | 0.0000 | 0.6404 | 0.2159 | 75.8% |
| 9 | 0.9012 | 0.8499 | 0.9429 | 0.0279 | 100.0% |
| 10 | 0.9187 | 0.8692 | 0.9543 | 0.0265 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="ransac-border-fit-ransac"></a>
<details>
<summary><strong>RANSAC Border Fit (`ransac`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 4 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 1380 of 1458 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 1458 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 78 (5.3%) |
| Best Avg IoU | 0.7541 |
| Minimum Avg IoU | 0.3643 |
| Avg IoU StdDev | 0.1249 |
| Winner stabilized after | 1243 parameter sets |
| Winner stabilized | 1m 16s (85% of search) |
| Near-best coverage (basin; within 0.0010) | 6 (0.4%) |
| Equivalent-best configurations (within 0.0001) | 6 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1458 | 100.0% | 25m 28s | 1.0× |
| Non-dormant | 27 | 1.9% | 28.3s | 54.0× |
| Low+ | 27 | 1.9% | 28.3s | 54.0× |
| Moderate+ | 9 | 0.6% | 9.4s | 162.0× |
| Important+ | 9 | 0.6% | 9.4s | 162.0× |
| Critical | 3 | 0.2% | 3.1s | 486.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_mean_inlier_ratio` | Critical | 0.7489 | 0.2487 | 33.3% | `0.25` (0.6889), `0.45` (0.6430), `0.65` (0.4402) | current run |
| `residual_threshold_fraction` | Important | 0.1372 | 0.1114 | 33.3% | `0.014` (0.6523), `0.008` (0.5789), `0.004` (0.5408) | current run |
| `bbox_padding_fraction` | Low | 0.0021 | 0.0129 | 33.3% | `0` (0.5956), `0.008` (0.5937), `0.016` (0.5827) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0002 | 0.0033 | 100.0% | `0.1` (0.5918), `0.18` (0.5918), `0.28` (0.5885) | current run |
| `scan_samples` | Dormant | 0.0001 | 0.0031 | 33.3% | `220` (0.5919), `320` (0.5914), `140` (0.5888) | current run |
| `minimum_scan_foreground_fraction` | Dormant | 0.0001 | 0.0028 | 33.3% | `0.02` (0.5917), `0.0125` (0.5915), `0.008` (0.5889) | current run |
| `max_trials` | Dormant | 0.0000 | 0.0001 | 100.0% | `200` (0.5907), `400` (0.5906) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `scan_samples`, `minimum_scan_foreground_fraction`, `max_trials`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_mean_inlier_ratio` × `residual_threshold_fraction` | 0.9913 | 0.2424 | 1458 |
| `minimum_mean_inlier_ratio` × `bbox_padding_fraction` | 0.7511 | 0.0022 | 1458 |
| `residual_threshold_fraction` × `bbox_padding_fraction` | 0.1394 | 0.0022 | 1458 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.7550 | 0.0000 | 0.9869 | 0.4036 | 77.8% |
| 5 | 0.3043 | 0.0000 | 0.5777 | 0.2724 | 55.6% |
| 6 | 0.0155 | 0.0000 | 0.3751 | 0.0659 | 5.3% |
| 9 | 0.9321 | 0.9029 | 0.9559 | 0.0205 | 100.0% |
| 10 | 0.9465 | 0.9188 | 0.9696 | 0.0182 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="line-segment-detector-lsd"></a>
<details>
<summary><strong>Line Segment Detector (`lsd`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 2187 of 2187 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 2187 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7378 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.1839 |
| Winner stabilized after | 406 parameter sets |
| Winner stabilized | 7.9s (19% of search) |
| Near-best coverage (basin; within 0.0010) | 27 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 9 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 13m 48s | 1.0× |
| Non-dormant | 243 | 11.1% | 1m 32s | 9.0× |
| Low+ | 243 | 11.1% | 1m 32s | 9.0× |
| Moderate+ | 81 | 3.7% | 30.7s | 27.0× |
| Important+ | 27 | 1.2% | 10.2s | 81.0× |
| Critical | 3 | 0.1% | 1.1s | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `refine_mode` | Critical | 0.2730 | 0.2038 | 33.3% | `none` (0.5940), `adv` (0.3902), `std` (0.3902) | current run |
| `minimum_length_fraction` | Important | 0.2059 | 0.1926 | 100.0% | `0.08` (0.5347), `0.14` (0.4975), `0.22` (0.3421) | current run |
| `outer_percentile` | Important | 0.1380 | 0.1568 | 33.3% | `5` (0.5197), `10` (0.4918), `20` (0.3629) | current run |
| `scale` | Moderate | 0.0428 | 0.0888 | 66.7% | `0.6` (0.4944), `0.8` (0.4743), `1` (0.4056) | current run |
| `bbox_padding_fraction` | Low | 0.0012 | 0.0138 | 33.3% | `0` (0.4628), `0.005` (0.4624), `0.015` (0.4490) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0004 | 100.0% | `0.08` (0.4584), `0.1` (0.4580), `0.15` (0.4580) | current run |
| `axis_angle_tolerance_degrees` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.4581), `18` (0.4581), `28` (0.4581) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `axis_angle_tolerance_degrees`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `refine_mode` × `minimum_length_fraction` | 0.6959 | 0.4229 | 2187 |
| `minimum_length_fraction` × `outer_percentile` | 0.3574 | 0.1515 | 2187 |
| `refine_mode` × `outer_percentile` | 0.4186 | 0.1457 | 2187 |
| `refine_mode` × `scale` | 0.3458 | 0.0728 | 2187 |
| `outer_percentile` × `scale` | 0.1962 | 0.0583 | 2187 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.5060 | 0.0000 | 0.9442 | 0.4240 | 61.7% |
| 5 | 0.2201 | 0.0000 | 0.9850 | 0.3124 | 35.3% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.7826 | 0.0000 | 0.8544 | 0.1894 | 96.7% |
| 10 | 0.7818 | 0.0000 | 0.9834 | 0.3409 | 85.2% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="convex-hull-detector-convexhull"></a>
<details>
<summary><strong>Convex Hull Detector (`convex_hull`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 4 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 2187 of 2187 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 2187 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7325 |
| Minimum Avg IoU | 0.5320 |
| Avg IoU StdDev | 0.0499 |
| Winner stabilized after | 168 parameter sets |
| Winner stabilized | 280 ms (8% of search) |
| Near-best coverage (basin; within 0.0010) | 144 (6.6%) |
| Equivalent-best configurations (within 0.0001) | 144 (6.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 6m 24s | 1.0× |
| Non-dormant | 27 | 1.2% | 4.7s | 81.0× |
| Low+ | 27 | 1.2% | 4.7s | 81.0× |
| Moderate+ | 9 | 0.4% | 1.6s | 243.0× |
| Important+ | 3 | 0.1% | 527 ms | 729.0× |
| Critical | 3 | 0.1% | 527 ms | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_solidity` | Critical | 0.3159 | 0.0595 | 66.7% | `0.35` (0.6854), `0.55` (0.6854), `0.75` (0.6260) | current run |
| `minimum_fragment_area_fraction` | Moderate | 0.0301 | 0.0211 | 33.3% | `0.0015` (0.6769), `0.0002` (0.6641), `0.0005` (0.6558) | current run |
| `bbox_padding_fraction` | Low | 0.0213 | 0.0174 | 33.3% | `0` (0.6732), `0.008` (0.6679), `0.016` (0.6558) | current run |
| `close_iterations` | Dormant | 0.0000 | 0.0003 | 100.0% | `0` (0.6657), `1` (0.6657), `2` (0.6654) | current run |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0003 | 100.0% | `0` (0.6657), `0.008` (0.6657), `0.016` (0.6654) | current run |
| `minimum_hull_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.6656), `0.16` (0.6656), `0.24` (0.6656) | current run |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.012` (0.6656), `0.025` (0.6656), `0.05` (0.6656) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_iterations`, `close_kernel_fraction`, `minimum_hull_area_fraction`, `polygon_epsilon_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_solidity` × `minimum_fragment_area_fraction` | 0.9779 | 0.6620 | 2187 |
| `minimum_fragment_area_fraction` × `bbox_padding_fraction` | 0.0520 | 0.0219 | 2187 |
| `minimum_solidity` × `bbox_padding_fraction` | 0.3373 | 0.0213 | 2187 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8924 | 0.8461 | 0.9734 | 0.0504 | 100.0% |
| 5 | 0.5672 | 0.0000 | 0.9030 | 0.2441 | 88.9% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9281 | 0.8982 | 0.9585 | 0.0246 | 100.0% |
| 10 | 0.9403 | 0.9157 | 0.9593 | 0.0178 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="border-energy-validator-borderenergy"></a>
<details>
<summary><strong>Border Energy Validator (`border_energy`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 6 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 6562 of 6562 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7250 |
| Minimum Avg IoU | 0.1724 |
| Avg IoU StdDev | 0.1328 |
| Winner stabilized after | 57 parameter sets |
| Winner stabilized | 2.5s (1% of search) |
| Near-best coverage (basin; within 0.0010) | 1296 (19.8%) |
| Equivalent-best configurations (within 0.0001) | 1296 (19.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 59m 42s | 1.0× |
| Non-dormant | 81 | 1.2% | 44.2s | 81.0× |
| Low+ | 81 | 1.2% | 44.2s | 81.0× |
| Moderate+ | 9 | 0.1% | 4.9s | 729.1× |
| Important+ | 9 | 0.1% | 4.9s | 729.1× |
| Critical | 3 | 0.0% | 1.6s | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_side_consistency` | Critical | 0.5951 | 0.2495 | 33.3% | `0.3` (0.6554), `0.45` (0.5542), `0.6` (0.4059) | current run |
| `band_fraction` | Important | 0.1173 | 0.1102 | 100.0% | `0.015` (0.5985), `0.008` (0.5287), `0.004` (0.4883) | current run |
| `gaussian_sigma` | Low | 0.0252 | 0.0459 | 100.0% | `1.8` (0.5683), `0.8` (0.5248), `1.2` (0.5224) | current run |
| `minimum_border_energy` | Low | 0.0020 | 0.0127 | 100.0% | `0.1` (0.5427), `0.05` (0.5427), `0.18` (0.5301) | current run |
| `consistency_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.15` (0.5542) | current run |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.45` (0.5542) | current run |
| `energy_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.5385), `0.3` (0.5385), `0.5` (0.5385) | current run |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.5385), `0.03` (0.5385), `0.06` (0.5385) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.5385), `0.08` (0.5385), `0.2` (0.5385) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.5385), `0.45` (0.5385), `0.7` (0.5385) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consistency_weight`, `contour_weight`, `energy_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_side_consistency` × `band_fraction` | 0.8355 | 0.2404 | 6562 |
| `minimum_side_consistency` × `gaussian_sigma` | 0.6678 | 0.0727 | 6562 |
| `band_fraction` × `gaussian_sigma` | 0.1776 | 0.0602 | 6562 |
| `band_fraction` × `minimum_border_energy` | 0.1234 | 0.0061 | 6562 |
| `minimum_side_consistency` × `minimum_border_energy` | 0.6012 | 0.0061 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.1687 | 0.0000 | 0.8542 | 0.3401 | 19.8% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8567 | 0.0000 | 0.9638 | 0.3029 | 88.9% |
| 10 | 0.8054 | 0.0000 | 0.9454 | 0.3358 | 85.2% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="distance-transform-rectangle-proposal-distancetransformrect"></a>
<details>
<summary><strong>Distance-Transform Rectangle Proposal (`distance_transform_rect`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 657 of 729 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 72 (9.9%) |
| Best Avg IoU | 0.7243 |
| Minimum Avg IoU | 0.5022 |
| Avg IoU StdDev | 0.0415 |
| Winner stabilized after | 597 parameter sets |
| Winner stabilized | 836 ms (82% of search) |
| Near-best coverage (basin; within 0.0010) | 6 (0.8%) |
| Equivalent-best configurations (within 0.0001) | 6 (0.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 4m 59s | 1.0× |
| Non-dormant | 243 | 33.3% | 1m 40s | 3.0× |
| Low+ | 243 | 33.3% | 1m 40s | 3.0× |
| Moderate+ | 9 | 1.2% | 3.7s | 81.0× |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `proposal_expansion_fraction` | Moderate | 0.0415 | 0.0184 | 33.3% | `0.06` (0.6160), `0.12` (0.6149), `0.22` (0.5975) | current run |
| `minimum_mask_coverage` | Moderate | 0.0411 | 0.0199 | 33.3% | `0.06` (0.6210), `0.12` (0.6064), `0.22` (0.6011) | current run |
| `minimum_core_area_fraction` | Low | 0.0204 | 0.0126 | 66.7% | `0.002` (0.6137), `0.006` (0.6137), `0.015` (0.6011) | current run |
| `distance_threshold_fraction` | Low | 0.0192 | 0.0140 | 33.3% | `0.18` (0.6168), `0.3` (0.6090), `0.1` (0.6027) | current run |
| `bbox_padding_fraction` | Low | 0.0018 | 0.0042 | 33.3% | `0.016` (0.6114), `0.008` (0.6099), `0` (0.6072) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.6095), `0.14` (0.6095), `0.22` (0.6095) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `proposal_expansion_fraction` × `distance_threshold_fraction` | 0.6474 | 0.6058 | 729 |
| `minimum_mask_coverage` × `distance_threshold_fraction` | 0.1424 | 0.1013 | 729 |
| `minimum_core_area_fraction` × `distance_threshold_fraction` | 0.0804 | 0.0600 | 729 |
| `proposal_expansion_fraction` × `minimum_mask_coverage` | 0.0943 | 0.0527 | 729 |
| `minimum_mask_coverage` × `minimum_core_area_fraction` | 0.0820 | 0.0409 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8507 | 0.7782 | 0.9672 | 0.0699 | 100.0% |
| 5 | 0.5053 | 0.3489 | 0.6490 | 0.0763 | 100.0% |
| 6 | 0.0419 | 0.0000 | 0.5727 | 0.1291 | 9.9% |
| 9 | 0.8127 | 0.6903 | 0.9353 | 0.0795 | 100.0% |
| 10 | 0.8368 | 0.6685 | 0.9433 | 0.0704 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="hough-line-borders-hough"></a>
<details>
<summary><strong>Hough Line Borders (`hough`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 8 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 2188 of 2188 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2188 |
| Parameter sets evaluated | 2188 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.6050 |
| Minimum Avg IoU | 0.1510 |
| Avg IoU StdDev | 0.1096 |
| Winner stabilized after | 1735 parameter sets |
| Winner stabilized | 2m 28s (79% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2188 | 100.0% | 49m 29s | 1.0× |
| Non-dormant | 729 | 33.3% | 16m 29s | 3.0× |
| Low+ | 729 | 33.3% | 16m 29s | 3.0× |
| Moderate+ | 27 | 1.2% | 36.6s | 81.0× |
| Important+ | 3 | 0.1% | 4.1s | 729.3× |
| Critical | 3 | 0.1% | 4.1s | 729.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `outer_percentile` | Critical | 0.7748 | 0.2317 | 33.3% | `5` (0.5231), `10` (0.4474), `20` (0.2914) | current run |
| `minimum_length_fraction` | Moderate | 0.0386 | 0.0495 | 33.3% | `0.12` (0.4402), `0.2` (0.4311), `0.3` (0.3907) | current run |
| `maximum_gap_fraction` | Moderate | 0.0311 | 0.0437 | 33.3% | `0.09` (0.4373), `0.055` (0.4312), `0.025` (0.3935) | current run |
| `canny_low_threshold` | Low | 0.0273 | 0.0443 | 33.3% | `40` (0.4423), `25` (0.4217), `65` (0.3980) | current run |
| `hough_threshold_fraction` | Low | 0.0063 | 0.0211 | 33.3% | `0.035` (0.4320), `0.055` (0.4190), `0.08` (0.4109) | current run |
| `bbox_padding_fraction` | Low | 0.0047 | 0.0182 | 33.3% | `0.015` (0.4305), `0.005` (0.4191), `0` (0.4124) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.1` (0.4784) | current run |
| `axis_angle_tolerance_degrees` | Dormant | 0.0000 | 0.0009 | 33.3% | `12` (0.4210), `22` (0.4209), `32` (0.4201) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `axis_angle_tolerance_degrees`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_gap_fraction` × `canny_low_threshold` | 0.0808 | 0.0497 | 2188 |
| `minimum_length_fraction` × `maximum_gap_fraction` | 0.0836 | 0.0450 | 2188 |
| `outer_percentile` × `minimum_length_fraction` | 0.8147 | 0.0400 | 2188 |
| `minimum_length_fraction` × `canny_low_threshold` | 0.0727 | 0.0341 | 2188 |
| `outer_percentile` × `maximum_gap_fraction` | 0.8078 | 0.0330 | 2188 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.5626 | 0.0000 | 0.8999 | 0.2287 | 97.1% |
| 5 | 0.1486 | 0.0000 | 0.5446 | 0.1764 | 45.7% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.6832 | 0.0000 | 0.8271 | 0.1454 | 99.6% |
| 10 | 0.7089 | 0.2854 | 0.8552 | 0.1156 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="projective-gradient-vote-projectivegradientvote"></a>
<details>
<summary><strong>Projective Gradient Vote (`projective_gradient_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 12 of 14 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 730 of 730 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 730 |
| Parameter sets evaluated | 730 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5541 |
| Minimum Avg IoU | 0.1683 |
| Avg IoU StdDev | 0.1555 |
| Winner stabilized after | 547 parameter sets |
| Winner stabilized | 5.2s (75% of search) |
| Near-best coverage (basin; within 0.0010) | 81 (11.1%) |
| Equivalent-best configurations (within 0.0001) | 27 (3.7%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 730 | 100.0% | 24m 43s | 1.0× |
| Non-dormant | 9 | 1.2% | 18.3s | 81.1× |
| Low+ | 9 | 1.2% | 18.3s | 81.1× |
| Moderate+ | 9 | 1.2% | 18.3s | 81.1× |
| Important+ | 9 | 1.2% | 18.3s | 81.1× |
| Critical | 3 | 0.4% | 6.1s | 243.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_segment_fraction` | Critical | 0.5142 | 0.2517 | 33.3% | `0.1` (0.5487), `0.16` (0.5147), `0.24` (0.2969) | current run |
| `gaussian_sigma` | Important | 0.2053 | 0.1628 | 33.3% | `1.8` (0.5515), `0.8` (0.4205), `1.2` (0.3888) | current run |
| `angle_bin_degrees` | Dormant | 0.0000 | 0.0000 | 0.0% | `4` (0.4474) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.15` (0.4474) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0` (0.4474) | current run |
| `geometry_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.3` (0.4474) | current run |
| `maximum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.4474) | current run |
| `maximum_corner_overshoot_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.08` (0.4474) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.18` (0.4474) | current run |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.55` (0.4474) | current run |
| `gradient_percentile` | Dormant | 0.0000 | 0.0003 | 100.0% | `74` (0.4536), `82` (0.4536), `90` (0.4533) | current run |
| `family_tolerance_degrees` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.4535), `24` (0.4535), `16` (0.4535) | current run |
| `minimum_side_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.4535), `0.3` (0.4535), `0.18` (0.4535) | current run |
| `orthogonality_tolerance_degrees` | Dormant | 0.0000 | 0.0000 | 100.0% | `12` (0.4535), `32` (0.4535), `22` (0.4535) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_bin_degrees`, `area_weight`, `bbox_padding_fraction`, `geometry_weight`, `maximum_area_fraction`, `maximum_corner_overshoot_fraction`, `minimum_area_fraction`, `support_weight`, `gradient_percentile`, `family_tolerance_degrees`, `minimum_side_support`, `orthogonality_tolerance_degrees`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_segment_fraction` × `gaussian_sigma` | 1.0000 | 0.4858 | 730 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.7292 | 0.0000 | 0.9698 | 0.3898 | 77.8% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8419 | 0.8393 | 0.8465 | 0.0023 | 100.0% |
| 10 | 0.6965 | 0.0000 | 0.9701 | 0.3998 | 77.8% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="consensus-quadrilateral-consensusquad"></a>
<details>
<summary><strong>Consensus Quadrilateral (`consensus_quad`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 3 of 5 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 243 of 243 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 243 |
| Parameter sets evaluated | 243 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5528 |
| Minimum Avg IoU | 0.3649 |
| Avg IoU StdDev | 0.0921 |
| Winner stabilized after | 40 parameter sets |
| Winner stabilized | 4.9s (17% of search) |
| Near-best coverage (basin; within 0.0010) | 24 (9.9%) |
| Equivalent-best configurations (within 0.0001) | 12 (4.9%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 243 | 100.0% | 5m 48s | 1.0× |
| Non-dormant | 9 | 3.7% | 12.9s | 27.0× |
| Low+ | 9 | 3.7% | 12.9s | 27.0× |
| Moderate+ | 9 | 3.7% | 12.9s | 27.0× |
| Important+ | 9 | 3.7% | 12.9s | 27.0× |
| Critical | 9 | 3.7% | 12.9s | 27.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `maximum_mean_corner_distance_fraction` | Critical | 0.3999 | 0.1235 | 66.7% | `0.025` (0.4887), `0.04` (0.4887), `0.015` (0.3651) | current run |
| `minimum_polygon_iou` | Critical | 0.3999 | 0.1235 | 66.7% | `0.8` (0.4887), `0.9` (0.4887), `0.95` (0.3651) | current run |
| `edge_contour_weight` | Dormant | 0.0000 | 0.0014 | 33.3% | `0.25` (0.4483), `0.5` (0.4474), `0.75` (0.4468) | current run |
| `contour_quad_weight` | Dormant | 0.0000 | 0.0013 | 66.7% | `0.75` (0.4480), `0.5` (0.4478), `0.25` (0.4467) | current run |
| `minimum_consensus_confidence` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.4475), `0.2` (0.4475), `0.35` (0.4475) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`edge_contour_weight`, `contour_quad_weight`, `minimum_consensus_confidence`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_mean_corner_distance_fraction` × `minimum_polygon_iou` | 0.9998 | 0.5999 | 243 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.8617 | 0.8616 | 0.8624 | 0.0003 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9640 | 0.9627 | 0.9647 | 0.0007 | 100.0% |
| 10 | 0.4118 | 0.0000 | 0.9386 | 0.4604 | 44.4% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="radon-boundary-projection-radonboundary"></a>
<details>
<summary><strong>Radon Boundary Projection (`radon_boundary`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 423 (58.0%) |
| Best Avg IoU | 0.4983 |
| Minimum Avg IoU | 0.0849 |
| Avg IoU StdDev | 0.1216 |
| Winner stabilized after | 47 parameter sets |
| Winner stabilized | 2.9s (6% of search) |
| Near-best coverage (basin; within 0.0010) | 9 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 9 (1.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 28m 52s | 1.0× |
| Non-dormant | 243 | 33.3% | 9m 37s | 3.0× |
| Low+ | 243 | 33.3% | 9m 37s | 3.0× |
| Moderate+ | 9 | 1.2% | 21.4s | 81.0× |
| Important+ | 9 | 1.2% | 21.4s | 81.0× |
| Critical | 9 | 1.2% | 21.4s | 81.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `projection_smooth_fraction` | Critical | 0.5794 | 0.2089 | 33.3% | `0.006` (0.4154), `0.012` (0.3870), `0.024` (0.2065) | current run |
| `minimum_peak_prominence` | Critical | 0.3666 | 0.1633 | 66.7% | `1.05` (0.3959), `1.25` (0.3804), `1.6` (0.2326) | current run |
| `edge_percentile` | Low | 0.0056 | 0.0205 | 33.3% | `90` (0.3491), `75` (0.3312), `82` (0.3286) | current run |
| `angle_limit_degrees` | Low | 0.0040 | 0.0185 | 100.0% | `12` (0.3447), `8` (0.3380), `4` (0.3262) | current run |
| `bbox_padding_fraction` | Low | 0.0036 | 0.0178 | 33.3% | `0.016` (0.3444), `0.008` (0.3378), `0` (0.3267) | current run |
| `angle_step_degrees` | Dormant | 0.0001 | 0.0036 | 66.7% | `0.5` (0.3382), `2` (0.3361), `1` (0.3346) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_step_degrees`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `projection_smooth_fraction` × `minimum_peak_prominence` | 0.9500 | 0.3706 | 729 |
| `minimum_peak_prominence` × `angle_limit_degrees` | 0.3782 | 0.0116 | 729 |
| `projection_smooth_fraction` × `edge_percentile` | 0.5882 | 0.0088 | 729 |
| `minimum_peak_prominence` × `edge_percentile` | 0.3742 | 0.0076 | 729 |
| `projection_smooth_fraction` × `angle_limit_degrees` | 0.5864 | 0.0070 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.1272 | 0.0000 | 0.3315 | 0.1152 | 60.5% |
| 5 | 0.4725 | 0.4141 | 0.5425 | 0.0433 | 100.0% |
| 6 | 0.6639 | 0.0000 | 0.9909 | 0.4413 | 88.9% |
| 9 | 0.1787 | 0.0000 | 0.4144 | 0.1348 | 70.4% |
| 10 | 0.2392 | 0.0000 | 0.4831 | 0.1909 | 61.7% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="joint-rectangle-voting-jointrectanglevote"></a>
<details>
<summary><strong>Joint Rectangle Voting (`joint_rectangle_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 3 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 2187 of 2187 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 2187 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.1980 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0659 |
| Winner stabilized after | 2143 parameter sets |
| Winner stabilized | 21.1s (98% of search) |
| Near-best coverage (basin; within 0.0010) | 27 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 27 (1.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 1h 28m 19s | 1.0× |
| Non-dormant | 81 | 3.7% | 3m 16s | 27.0× |
| Low+ | 81 | 3.7% | 3m 16s | 27.0× |
| Moderate+ | 9 | 0.4% | 21.8s | 243.0× |
| Important+ | 9 | 0.4% | 21.8s | 243.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `canny_high` | Important | 0.1758 | 0.0643 | 33.3% | `220` (0.0643), `100` (0.0140), `150` (0.0000) | current run |
| `hough_threshold` | Important | 0.1758 | 0.0643 | 33.3% | `120` (0.0643), `80` (0.0140), `50` (0.0000) | current run |
| `canny_low` | Low | 0.0100 | 0.0140 | 100.0% | `30` (0.0354), `50` (0.0214), `80` (0.0214) | current run |
| `axis_tolerance_degrees` | Low | 0.0024 | 0.0069 | 33.3% | `12` (0.0284), `18` (0.0284), `6` (0.0215) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0009 | 33.3% | `0` (0.0265), `0.008` (0.0262), `0.016` (0.0256) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0261), `0.16` (0.0261), `0.24` (0.0261) | current run |
| `minimum_side_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0261), `0.18` (0.0261), `0.3` (0.0261) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`bbox_padding_fraction`, `minimum_area_fraction`, `minimum_side_support`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `canny_high` × `hough_threshold` | 0.8417 | 0.6659 | 2187 |
| `canny_high` × `canny_low` | 0.2059 | 0.0301 | 2187 |
| `hough_threshold` × `canny_low` | 0.2059 | 0.0301 | 2187 |
| `canny_high` × `axis_tolerance_degrees` | 0.1834 | 0.0075 | 2187 |
| `hough_threshold` × `axis_tolerance_degrees` | 0.1834 | 0.0075 | 2187 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.1306 | 0.0000 | 0.9899 | 0.3294 | 13.6% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="text-flow-envelope-textflow"></a>
<details>
<summary><strong>Text Flow Envelope (`text_flow`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 729 of 729 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.1634 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0609 |
| Winner stabilized after | 149 parameter sets |
| Winner stabilized | 2.4s (20% of search) |
| Near-best coverage (basin; within 0.0010) | 34 (4.7%) |
| Equivalent-best configurations (within 0.0001) | 34 (4.7%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 4m 38s | 1.0× |
| Non-dormant | 243 | 33.3% | 1m 33s | 3.0× |
| Low+ | 243 | 33.3% | 1m 33s | 3.0× |
| Moderate+ | 81 | 11.1% | 30.9s | 9.0× |
| Important+ | 9 | 1.2% | 3.4s | 81.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_line_count` | Important | 0.2257 | 0.0613 | 100.0% | `2` (0.1082), `3` (0.1082), `5` (0.0469) | current run |
| `maximum_component_area_fraction` | Important | 0.1129 | 0.0434 | 100.0% | `0.02` (0.1167), `0.005` (0.0733), `0.01` (0.0733) | current run |
| `minimum_text_coverage_fraction` | Moderate | 0.0879 | 0.0383 | 100.0% | `0.04` (0.1005), `0.08` (0.1005), `0.14` (0.0623) | current run |
| `line_join_fraction` | Moderate | 0.0610 | 0.0367 | 33.3% | `0.05` (0.1051), `0.03` (0.0897), `0.018` (0.0685) | current run |
| `bbox_padding_fraction` | Low | 0.0027 | 0.0077 | 33.3% | `0.04` (0.0919), `0.02` (0.0873), `0.01` (0.0842) | current run |
| `minimum_component_area_fraction` | Dormant | 0.0007 | 0.0035 | 66.7% | `1e-05` (0.0889), `2e-05` (0.0889), `5e-05` (0.0854) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_component_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_line_count` × `line_join_fraction` | 0.4041 | 0.1784 | 729 |
| `maximum_component_area_fraction` × `minimum_text_coverage_fraction` | 0.2448 | 0.1319 | 729 |
| `minimum_line_count` × `minimum_text_coverage_fraction` | 0.3576 | 0.1319 | 729 |
| `maximum_component_area_fraction` × `line_join_fraction` | 0.2364 | 0.1235 | 729 |
| `minimum_line_count` × `maximum_component_area_fraction` | 0.3404 | 0.1147 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.4389 | 0.0000 | 0.8170 | 0.3043 | 70.4% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="whitespace-frame-whitespaceframe"></a>
<details>
<summary><strong>Whitespace Frame (`whitespace_frame`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- Every measured parameter was dormant for this Golden Set and grid.
- Detector failed on at least one Golden Set page for 730 of 730 parameter configurations.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 730 |
| Parameter sets evaluated | 730 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.0000 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 730 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 730 (100.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 730 | 100.0% | 5.1s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `background_threshold` | Dormant | 0.0000 | 0.0000 | 100.0% | `235` (0.0000), `245` (0.0000), `250` (0.0000) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.0000), `0.008` (0.0000), `0.016` (0.0000) | current run |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.004` (0.0000), `0.01` (0.0000), `0.02` (0.0000) | current run |
| `maximum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.9` (0.0000), `0.96` (0.0000), `0.98` (0.0000) | current run |
| `minimum_border_background_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.0000), `0.55` (0.0000), `0.7` (0.0000) | current run |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0000), `0.18` (0.0000), `0.28` (0.0000) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`background_threshold`, `bbox_padding_fraction`, `close_kernel_fraction`, `maximum_page_area_fraction`, `minimum_border_background_fraction`, `minimum_page_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>

</details>

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="detector-regression-reports"></a>
<details open>
<summary><h2>Detector Regression Reports</h2></summary>

[↑ Back to Navigation](#table-of-contents)

<a id="regression-completion-summary"></a>
### Regression Completion Summary

| Measure | Value | Notes |
|---|---:|---|
| Detector runs completed | 41 of 41 | Successful detector regressions completed out of those scheduled. |
| Parameter sets evaluated | 4370244 | Total detector parameter configurations evaluated across all runs. |
| Golden Set page evaluations | 21851220 | Parameter sets multiplied by evaluated Golden Set pages. |
| Aggregate detector runtime | 1d 20h 49m 49s | Sum of detector wall-clock runtimes; this is not the elapsed time experienced by the user. |
| Regression wall-clock span | 9d 8h 3m 52s | Earliest detector start through latest detector finish. |
| Effective detector concurrency | 0.20× | Aggregate detector runtime divided by regression wall-clock span. |
| Detector pipelines | 4 | Maximum concurrent detector regressions used by this build. |
| Loading strategy | LPT (Longest Processing Time first) | Strategy used to order the shared detector queue. |
| Pipeline stagger | 0m | Delay between initial pipeline starts; replacement loads begin immediately. |
| Source-document images | 929 | Total images recorded for the source document. |

[↑ Back to Navigation](#table-of-contents)

<a id="regression-execution-and-detector-queueing"></a>
### Regression Execution and Detector Queueing

| Setting | Value |
|---|---|
| Detector pipelines | 4 |
| Detector loading strategy | LPT (Longest Processing Time first) |
| Threads per detector regression | 2 |
| Execution recommendation basis | runtime-index coherent build 32327690407 (41/41 detectors) |
| Pipeline start stagger | 0m |
| Runtime intelligence | `runtime-index.json` |
| Parallelism intelligence | `parallelism-index.json` |
| Calibration intelligence | `calibration-index.json` |

Detector pipelines pull continuously from one shared queue. Once a detector finishes, that pipeline immediately loads the next queued detector until the queue is empty.

| Queue | Detector | Pipeline | Estimated Runtime | Scheduling Basis |
|---:|---|---|---:|---|
| 1 | GrabCut + Contour (`grabcut_contour`) | 1 | 10m 46s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 2 | GrabCut Segmentation (`grabcut`) | 2 | 9m 3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 3 | Kraken Page Mask (`kraken_page_mask`) | 3 | 8m 41s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 4 | Contour + GrabCut (`contour_grabcut`) | 4 | 3m 43s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 5 | Learned Page-Mask Detector (`learned_page_mask`) | 4 | 1m 39s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 6 | Fusion Gen1 — MSRE + BFQ + SPBV + Page Background (`msre_bfq_spbv_pbg`) | 4 | 1m 11s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 7 | Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background (`amsre_bfq_spbv_pbg`) | 4 | 1m 5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 8 | Hough Line Borders (`hough`) | 4 | 39.9s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 9 | dhSegment Page-Mask Detector (`dhsegment_page_mask`) | 4 | 35.8s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 10 | Adaptive Multi-Scale Radial Edge Search (`adaptive_multi_scale_radial_edge`) | 3 | 32.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 11 | Doc-UFCN Page-Mask Detector (`doc_ufcn_page_mask`) | 4 | 29.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 12 | Segment-Supported Polar Voting (`segment_supported_polar_vote`) | 2 | 20.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 13 | Consensus Quadrilateral (`consensus_quad`) | 3 | 17s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 14 | Adaptive Radial Edge Search (`adaptive_radial_edge`) | 4 | 12.8s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 15 | Contour + Projection (`contour_projection`) | 2 | 12.5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 16 | Contour Quadrilateral (`contour_quad`) | 3 | 11.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 17 | Border Fusion Quad (`border_fusion_quad`) | 4 | 10.9s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 18 | Border Energy Validator (`border_energy`) | 2 | 10.5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 19 | Multi-Scale Radial Edge Search (`multi_scale_radial_edge`) | 3 | 9.6s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 20 | Joint Rectangle Voting (`joint_rectangle_vote`) | 4 | 8.5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 21 | Projective Gradient Vote (`projective_gradient_vote`) | 2 | 7.8s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 22 | Page Background (`page_background`) | 3 | 6.5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 23 | Cross-Edge Contour (`cross_edge_contour`) | 2 | 6.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 24 | Radon Boundary Projection (`radon_boundary`) | 4 | 6.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 25 | Edge-Supported Contour (`edge_contour`) | 3 | 5.9s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 26 | Distance Transform Detector (`distance_transform`) | 2 | 5.3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 27 | Line Segment Detector (`lsd`) | 4 | 4.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 28 | Orli Page Mask (`orli_page_mask`) | 3 | 4.6s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 29 | Signed Polar Boundary Voting (`signed_polar_boundary_vote`) | 4 | 3.4s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 30 | Contour + Components (`contour_components`) | 2 | 3.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 31 | Radial Edge Search (`radial_edge`) | 3 | 2.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 32 | Star-Convex Boundary Optimization (`star_convex`) | 2 | 1.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 33 | RANSAC Border Fit (`ransac`) | 4 | 1.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 34 | Polar Boundary Voting (`polar_boundary_vote`) | 3 | 1.3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 35 | Connected Components (`components`) | 2 | 1.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 36 | Distance-Transform Rectangle Proposal (`distance_transform_rect`) | 4 | 903 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 37 | Convex Hull Detector (`convex_hull`) | 4 | 890 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 38 | Text Flow Envelope (`text_flow`) | 2 | 662 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 39 | Contour Envelope (`contour`) | 3 | 658 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 40 | Gradient Boundary Voting (`gradient_vote`) | 2 | 568 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 41 | Whitespace Frame (`whitespace_frame`) | 3 | 487 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |

#### Execution Optimization — Next Run Claim Strategy

| Setting | Preferred next run |
|---|---|
| Claim strategy | 10s LPT claim batches |
| Batch target | 10.0s estimated work |
| Scheduling estimate floor | 0.1s |
| Initial-wave claims | parent pre-batched |
| Refill strategy | one serialized claim per >=10s LPT batch |
| Claim-wait objective | amortized per batch |
| Optimization basis | current LPT runtime intelligence + persisted short-run occupation |

| Pipeline | Initial LPT claim batch | Estimated Work | Threads |
|---:|---|---|---:|---:|
| 1 | GrabCut + Contour (`grabcut_contour`) | 10m 46s | 2 |
| 2 | GrabCut Segmentation (`grabcut`) | 9m 3s | 2 |
| 3 | Kraken Page Mask (`kraken_page_mask`) | 8m 41s | 2 |
| 4 | Contour + GrabCut (`contour_grabcut`) | 3m 43s | 2 |

Each short-run claim atomically removes consecutive work from the LPT queue until the batch contains at least 10 seconds of estimated work, using a 0.1-second scheduling floor. The parent constructs the initial batches before workers start; refill batches use one serialized queue transaction each. The final claimant drains whatever work remains—there is no special tail-mode reversion.

Queue order reflects the selected loading strategy. LPT (Longest Processing Time first) schedules the longest estimated detector work first, FIFO preserves configured detector order, and Ranked uses historical detector quality.

[↑ Back to Navigation](#table-of-contents)

<a id="regression-recommendations-summary"></a>
### Regression Recommendations Summary

#### Execution Configuration

| Setting | Recommended | Basis |
|---|---|---|
| Detector pipelines | 4 | Current HTH default for multi-detector regressions. |
| Detector loading | LPT (Longest Processing Time first) | Reduces the slow-detector tail by loading historically longest regressions first. |
| Threads per detector regression | 2 | Preserve the current measured setting until runtime history supports a different thread recommendation. |
| Startup stagger | 0m | Avoids idle startup time unless runner contention requires a stagger. |

#### Estimated Runtime

| All-Detector Regression Scope | Estimated Wall Time* |
|---|---:|
| Exhaustive | 25d 17h 14m 12s |
| Non-dormant | 4d 14h 35m 39s |
| Critical only | 2d 8h 38m 3s |

\* Estimates scale each detector's measured runtime to the selected effect-size domain, apply the normal bounded shard plan, and simulate shard-level LPT placement across the recommended detector pipelines. Effect-group fallback remains active when a detector has no parameter sets in the requested group.

The reports below preserve the complete manifest, winner, baseline, calibration statistics, page analysis, and output inventory for each detector run.

[↑ Back to Navigation](#table-of-contents)

<a id="per-detector-regression-reports"></a>
<details open>
<summary><h3>Per-Detector Regression Reports</h3></summary>


[↑ Back to Navigation](#table-of-contents)

<a id="adaptive-multi-scale-radial-edge-search-adaptivemultiscaleradialedge-2"></a>
<details>
<summary><strong>Adaptive Multi-Scale Radial Edge Search (`adaptive_multi_scale_radial_edge`)</strong></summary>

**Status:** complete

## Run Information — adaptive_multi_scale_radial_edge

### Build Provenance

- Run ID: `run-20260815-155156`
- Detector: `adaptive_multi_scale_radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `699cbc8ea1e7`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-15T15:18:36.974784+00:00`
- Finished: `2026-08-15T15:51:49.791037+00:00`
- Wall-clock elapsed: `33m 13s`
- Est. serial runtime: `7d 13h 14m 18s`
- Effective acceleration: `327.40×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50001`
- Parameter sets evaluated: `50001`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — adaptive_multi_scale_radial_edge

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `fbe222668f99` | `unknown` | `21ea516c3c5a` | `21ea516c3c5a` | 0.9781 | 0.9564 | 0.0182 | 0.9781 | 0 | 13.5s |
| Baseline | `HTH-0001` | `fbe222668f99` | `unknown` | `e8e8dc34f8fb` | `baseline` | 0.9767 | 0.9566 | 0.0177 | 0.9767 | 0 | 740 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`699cbc8ea1e7`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `21ea516c3c5a` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `coarse_angle_step_degrees` | `2.0454545454545454` |
| `maximum_refined_sides` | `3` |
| `refined_angle_step_degrees` | `0.35` |
| `side_assignment_tolerance_fraction` | `0.0075` |
| `weak_side_support_fraction` | `0.65` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Fixed calibrated MSRE scale-space | Primary | Uses the best-known MSRE multiscale gradient evidence without changing its scale schedule or radial bounds. |
| Coarse angular pass | Generator | Samples the full page boundary at a configurable coarse angular step. |
| Per-side support | Validation | Measures each fitted side against only the coarse rays geometrically eligible to support that side. |
| Weak-side angular refinement | Robustness | Allocates a denser second angular pass only to weak sides, preserving MSRE evidence while testing ARE-style adaptive sampling. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 25 | 15 | 375 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `e8e8dc34f8fb` | `baseline` | 0.9767 | 0.9566 | 0.0177 | -0.0013 | 0.9767 | 0 | reference | reference |
| 1 | unknown | `unknown` | `21ea516c3c5a` | `21ea516c3c5a` | 0.9781 | 0.9564 | 0.0182 | +0.0000 | 0.9781 | 0 | 16m 31s | 52.95% |
| 2 | unknown | `unknown` | `280a60430236` | `280a60430236` | 0.9779 | 0.9556 | 0.0184 | -0.0002 | 0.9779 | 0 | 16m 39s | 53.39% |
| 3 | unknown | `unknown` | `32f1940975eb` | `32f1940975eb` | 0.9779 | 0.9556 | 0.0184 | -0.0002 | 0.9779 | 0 | 16m 38s | 53.34% |
| 4 | unknown | `unknown` | `a0c558c619bd` | `a0c558c619bd` | 0.9774 | 0.9564 | 0.0176 | -0.0006 | 0.9774 | 0 | 19m 41s | 63.88% |
| 5 | unknown | `unknown` | `98ac77058f43` | `98ac77058f43` | 0.9771 | 0.9556 | 0.0177 | -0.0010 | 0.9771 | 0 | 19m 44s | 64.00% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — adaptive_multi_scale_radial_edge

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `21ea516c3c5a` | 0.9767 | 0.9841 | +0.0074 | Improved |
| 5 | `unknown` | `21ea516c3c5a` | 0.9973 | 0.9973 | +0.0000 | Unchanged |
| 6 | `unknown` | `21ea516c3c5a` | 0.9959 | 0.9959 | +0.0000 | Unchanged |
| 9 | `unknown` | `21ea516c3c5a` | 0.9566 | 0.9566 | +0.0000 | Unchanged |
| 10 | `unknown` | `21ea516c3c5a` | 0.9573 | 0.9564 | -0.0009 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `unknown` | `21ea516c3c5a` | 16m 31s | 52.95% |

Total winner changes: **1**.
Search completed in **33m 13s** wall-clock time.

**Stabilization Interpretation:** Late convergence — the final winner emerged after 40–80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — adaptive_multi_scale_radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260815-155156`
- Calibration schema: `1.1`
- Detector: `adaptive_multi_scale_radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/adaptive_multi_scale_radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `699cbc8ea1e717c9116a9df9239f689426db2967`
- Source commit: `a7f676ca50341aaf7b3a00cb608a84832da25453`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `15`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `21ea516c3c5a`
- Recommended parameter short name: `21ea516c3c5a`
- Best observed Avg IoU: `0.9781`
- Avg IoU Success: `0.9781`
- Worst Golden Set page (Min IoU): `0.9564`
- Page-to-page StdDev: `0.0182`
- Calibration evidence: `Medium`
- Dormant parameters: `area_weight, base_sigma, bbox_padding_fraction, gradient_percentile, maximum_area_fraction, maximum_radius_fraction, minimum_area_fraction, minimum_radius_fraction, minimum_ray_support, scale_count, scale_ratio, strength_weight, support_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 13 of 18 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 50001 |
| Parameter sets evaluated | 50001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 50001 (100.0%) |
| Best Avg IoU | 0.9781 |
| Minimum Avg IoU | 0.9624 |
| Avg IoU StdDev | 0.0028 |
| Winner stabilized after | 26475 parameter sets |
| Winner stabilized | 16m 31s (53% of search) |
| Near-best coverage (basin; within 0.0010) | 6 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 50001 | 100.0% | 7d 19h 6m 38s | 1.0× |
| Non-dormant | 50000 | 100.0% | 7d 19h 6m 25s | 1.0× |
| Low+ | 50000 | 100.0% | 7d 19h 6m 25s | 1.0× |
| Moderate+ | 500 | 1.0% | 1h 52m 16s | 100.0× |
| Important+ | 50 | 0.1% | 11m 14s | 1000.0× |
| Critical | 10 | 0.0% | 2m 15s | 5000.1× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `coarse_angle_step_degrees` | Critical | 0.4927 | 0.0071 | 10.0% | `2.04545` (0.9754), `1.9` (0.9725), `2.025` (0.9713) | current run |
| `maximum_refined_sides` | Important | 0.1383 | 0.0029 | 40.0% | `4` (0.9719), `3` (0.9718), `2` (0.9708) | current run |
| `refined_angle_step_degrees` | Moderate | 0.0450 | 0.0022 | 10.0% | `0.5` (0.9715), `1` (0.9714), `0.8` (0.9712) | current run |
| `side_assignment_tolerance_fraction` | Low | 0.0071 | 0.0008 | 10.0% | `0.0075` (0.9712), `0.01` (0.9710), `0.0125` (0.9710) | current run |
| `weak_side_support_fraction` | Low | 0.0026 | 0.0004 | 30.0% | `0.55` (0.9709), `0.6` (0.9709), `0.5` (0.9709) | current run |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.2` (0.9767) | current run |
| `base_sigma` | Dormant | 0.0001 | 0.0000 | 0.0% | `1` (0.9767) | current run |
| `bbox_padding_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0` (0.9767) | current run |
| `gradient_percentile` | Dormant | 0.0001 | 0.0000 | 0.0% | `96.875` (0.9767) | current run |
| `maximum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.98` (0.9767) | current run |
| `maximum_radius_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.78` (0.9767) | current run |
| `minimum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.18` (0.9767) | current run |
| `minimum_radius_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.16` (0.9767) | current run |
| `minimum_ray_support` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.36` (0.9767) | current run |
| `scale_count` | Dormant | 0.0001 | 0.0000 | 0.0% | `4` (0.9767) | current run |
| `scale_ratio` | Dormant | 0.0001 | 0.0000 | 0.0% | `3.5` (0.9767) | current run |
| `strength_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.3` (0.9767) | current run |
| `support_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.5` (0.9767) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `base_sigma`, `bbox_padding_fraction`, `gradient_percentile`, `maximum_area_fraction`, `maximum_radius_fraction`, `minimum_area_fraction`, `minimum_radius_fraction`, `minimum_ray_support`, `scale_count`, `scale_ratio`, `strength_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `coarse_angle_step_degrees` × `maximum_refined_sides` | 0.8115 | 0.3186 | 25001 |
| `coarse_angle_step_degrees` × `side_assignment_tolerance_fraction` | 0.5748 | 0.0819 | 25001 |
| `maximum_refined_sides` × `refined_angle_step_degrees` | 0.2130 | 0.0747 | 25001 |
| `coarse_angle_step_degrees` × `refined_angle_step_degrees` | 0.5542 | 0.0613 | 25001 |
| `refined_angle_step_degrees` × `side_assignment_tolerance_fraction` | 0.1008 | 0.0494 | 25001 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9724 | 0.9464 | 0.9860 | 0.0080 | 100.0% |
| 5 | 0.9751 | 0.9617 | 0.9973 | 0.0088 | 100.0% |
| 6 | 0.9943 | 0.9856 | 0.9989 | 0.0030 | 100.0% |
| 9 | 0.9563 | 0.9544 | 0.9576 | 0.0010 | 100.0% |
| 10 | 0.9558 | 0.9541 | 0.9574 | 0.0009 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="adaptive-radial-edge-search-adaptiveradialedge-2"></a>
<details>
<summary><strong>Adaptive Radial Edge Search (`adaptive_radial_edge`)</strong></summary>

**Status:** complete

## Run Information — adaptive_radial_edge

### Build Provenance

- Run ID: `run-20260813-231555`
- Detector: `adaptive_radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `1000d4a6d7b9`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-13T22:05:20.834842+00:00`
- Finished: `2026-08-13T23:14:08.726990+00:00`
- Wall-clock elapsed: `1h 8m 48s`
- Est. serial runtime: `14d 19h 22m 52s`
- Effective acceleration: `309.93×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `750001`
- Parameter sets evaluated: `750001`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — adaptive_radial_edge

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `ee0f5dc816bf` | `unknown` | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9726 | 0.9557 | 0.0159 | 0.9726 | 0 | 1.8s |
| Baseline | `HTH-0001` | `ee0f5dc816bf` | `unknown` | `a132c2ac5e87` | `baseline` | 0.9329 | 0.8817 | 0.0344 | 0.9329 | 0 | 170 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`1000d4a6d7b9`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `bcd9a1d083cf` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `gaussian_sigma` | `2.2` |
| `gradient_percentile` | `74.0` |
| `maximum_radius_fraction` | `0.78` |
| `maximum_refined_sides` | `4` |
| `minimum_radius_fraction` | `0.26` |
| `refined_angle_step_degrees` | `0.35` |
| `side_assignment_tolerance_fraction` | `0.035` |
| `weak_side_support_fraction` | `0.35` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Coarse center-outward rays | Primary | Samples the full image at 3-degree spacing. |
| Weak-side support | Trigger | Identifies fitted document sides with comparatively sparse boundary confirmation. |
| One-degree angular refinement | Generator | Adds a second pass only through weak-side sectors. |
| Refined quadrilateral | Geometry | Refits the page boundary from combined coarse and refined evidence. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 29 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 60 | 6 | 360 | `rh8-al319` | 360 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `a132c2ac5e87` | `baseline` | 0.9329 | 0.8817 | 0.0344 | -0.0397 | 0.9329 | 0 | reference | reference |
| 1 | unknown | `unknown` | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9726 | 0.9557 | 0.0159 | +0.0000 | 0.9726 | 0 | 55m 27s | 91.55% |
| 2 | unknown | `unknown` | `1b92c2c685f9` | `1b92c2c685f9` | 0.9726 | 0.9557 | 0.0159 | +0.0000 | 0.9726 | 0 | 55m 28s | 91.58% |
| 3 | unknown | `unknown` | `139d5c2364e5` | `139d5c2364e5` | 0.9726 | 0.9557 | 0.0159 | +0.0000 | 0.9726 | 0 | 55m 29s | 91.61% |
| 4 | unknown | `unknown` | `e56e2cf13b6e` | `e56e2cf13b6e` | 0.9726 | 0.9557 | 0.0159 | +0.0000 | 0.9726 | 0 | 55m 31s | 91.64% |
| 5 | unknown | `unknown` | `82ecfe7cbae0` | `82ecfe7cbae0` | 0.9726 | 0.9557 | 0.0159 | +0.0000 | 0.9726 | 0 | 55m 31s | 91.66% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — adaptive_radial_edge

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `bcd9a1d083cf` | 0.8817 | 0.9814 | +0.0996 | Improved |
| 5 | `unknown` | `bcd9a1d083cf` | 0.9752 | 0.9716 | -0.0036 | Regressed |
| 6 | `unknown` | `bcd9a1d083cf` | 0.9046 | 0.9979 | +0.0933 | Improved |
| 9 | `unknown` | `bcd9a1d083cf` | 0.9480 | 0.9557 | +0.0076 | Improved |
| 10 | `unknown` | `bcd9a1d083cf` | 0.9548 | 0.9565 | +0.0017 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 25 | `unknown` | `56bd20bb315f` | 44m 19s | 75.18% |
| 26 | `unknown` | `8210c32d8a5c` | 44m 24s | 75.32% |
| 27 | `unknown` | `0c8435f96746` | 47m 22s | 79.77% |
| 28 | `unknown` | `c40dac441d85` | 49m 17s | 82.60% |
| 29 (final) | `unknown` | `bcd9a1d083cf` | 55m 27s | 91.55% |

Total winner changes: **29**.
Search completed in **1h 8m 48s** wall-clock time.

**Stabilization Interpretation:** No stable optimum — the final winner did not emerge until more than 80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 5 | `unknown` | `bcd9a1d083cf` | 0.9716 | Regressed |

## Calibration Intelligence — adaptive_radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260813-231555`
- Calibration schema: `1.1`
- Detector: `adaptive_radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/adaptive_radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1000d4a6d7b9b8f1bd73682a42f3c26d9ba73f62`
- Source commit: `c3ce5a61fca2d0595cbc4d75f8d1757fabee3c95`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `6`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `bcd9a1d083cf`
- Recommended parameter short name: `bcd9a1d083cf`
- Best observed Avg IoU: `0.9726`
- Avg IoU Success: `0.9726`
- Worst Golden Set page (Min IoU): `0.9557`
- Page-to-page StdDev: `0.0159`
- Calibration evidence: `Medium`
- Dormant parameters: `gradient_percentile, side_assignment_tolerance_fraction, weak_side_support_fraction, area_weight, coarse_angle_step_degrees, maximum_area_fraction, minimum_area_fraction, minimum_ray_support, ray_count, rectangularity_weight, support_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 11 of 16 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 750001 |
| Parameter sets evaluated | 750001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 750001 (100.0%) |
| Best Avg IoU | 0.9726 |
| Minimum Avg IoU | 0.7773 |
| Avg IoU StdDev | 0.0406 |
| Winner stabilized after | 686657 parameter sets |
| Winner stabilized | 55m 27s (92% of search) |
| Near-best coverage (basin; within 0.0010) | 149 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 29 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 750001 | 100.0% | 16d 50m 48s | 1.0× |
| Non-dormant | 3750 | 0.5% | 1h 55m 27s | 200.0× |
| Low+ | 3750 | 0.5% | 1h 55m 27s | 200.0× |
| Moderate+ | 250 | 0.0% | 7m 42s | 3000.0× |
| Important+ | 25 | 0.0% | 46.2s | 30000.0× |
| Critical | 5 | 0.0% | 9.2s | 150000.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `maximum_radius_fraction` | Critical | 0.6214 | 0.0893 | 40.0% | `0.72` (0.9266), `0.78` (0.9187), `0.84` (0.9120) | current run |
| `minimum_radius_fraction` | Important | 0.1201 | 0.0318 | 20.0% | `0.22` (0.9150), `0.26` (0.9143), `0.18` (0.8928) | current run |
| `gaussian_sigma` | Moderate | 0.0526 | 0.0363 | 20.0% | `2.4` (0.9121), `2` (0.9057), `2.2` (0.9051) | current run |
| `maximum_refined_sides` | Low | 0.0178 | 0.0132 | 33.3% | `4` (0.9049), `2` (0.8971), `1` (0.8917) | current run |
| `refined_angle_step_degrees` | Low | 0.0068 | 0.0099 | 20.0% | `0.35` (0.9033), `0.5` (0.8995), `0.75` (0.8973) | current run |
| `gradient_percentile` | Dormant | 0.0008 | 0.0038 | 100.0% | `74` (0.9008), `78` (0.8988), `80` (0.8986) | current run |
| `side_assignment_tolerance_fraction` | Dormant | 0.0003 | 0.0016 | 100.0% | `0.015` (0.8986), `0.025` (0.8984), `0.035` (0.8978) | current run |
| `weak_side_support_fraction` | Dormant | 0.0000 | 0.0003 | 100.0% | `0.55` (0.8980), `0.35` (0.8980), `0.45` (0.8979) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.35` (0.9329) | current run |
| `coarse_angle_step_degrees` | Dormant | 0.0000 | 0.0000 | 0.0% | `3` (0.9329) | current run |
| `maximum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.9329) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.18` (0.9329) | current run |
| `minimum_ray_support` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.45` (0.9329) | current run |
| `ray_count` | Dormant | 0.0000 | 0.0000 | 0.0% | `120` (0.9329) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.9329) | current run |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.45` (0.9329) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`gradient_percentile`, `side_assignment_tolerance_fraction`, `weak_side_support_fraction`, `area_weight`, `coarse_angle_step_degrees`, `maximum_area_fraction`, `minimum_area_fraction`, `minimum_ray_support`, `ray_count`, `rectangularity_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_radius_fraction` × `minimum_radius_fraction` | 0.7647 | 0.1445 | 46876 |
| `maximum_radius_fraction` × `gaussian_sigma` | 0.7178 | 0.0976 | 46876 |
| `minimum_radius_fraction` × `gaussian_sigma` | 0.1788 | 0.0580 | 46876 |
| `gaussian_sigma` × `maximum_refined_sides` | 0.0768 | 0.0241 | 46876 |
| `maximum_radius_fraction` × `maximum_refined_sides` | 0.6412 | 0.0211 | 46876 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9067 | 0.7146 | 0.9841 | 0.0511 | 100.0% |
| 5 | 0.9351 | 0.7520 | 0.9931 | 0.0456 | 100.0% |
| 6 | 0.8210 | 0.5665 | 0.9979 | 0.0923 | 100.0% |
| 9 | 0.8965 | 0.7134 | 0.9575 | 0.0687 | 100.0% |
| 10 | 0.9303 | 0.7929 | 0.9787 | 0.0430 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="fusion-gen2-amsre-bfq-spbv-page-background-amsrebfqspbvpbg-2"></a>
<details>
<summary><strong>Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background (`amsre_bfq_spbv_pbg`)</strong></summary>

**Status:** complete

## Run Information — amsre_bfq_spbv_pbg

### Build Provenance

- Run ID: `run-20260815-190041`
- Detector: `amsre_bfq_spbv_pbg`
- Strategy: `exhaustive`
- Pipeline commit: `fffeed69fec4`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-15T17:41:53.092281+00:00`
- Finished: `2026-08-15T19:00:34.535768+00:00`
- Wall-clock elapsed: `1h 18m 41s`
- Est. serial runtime: `20d 2h 57m 40s`
- Effective acceleration: `368.25×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50177`
- Parameter sets evaluated: `50177`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — amsre_bfq_spbv_pbg

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `749699bdcce5` | `unknown` | `156ff0241cc1` | `baseline` | 0.9743 | 0.9638 | 0.0103 | 0.9743 | 0 | 1.8s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`fffeed69fec4`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `156ff0241cc1` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `consensus_tolerance_fraction` | `0.012664` |
| `consensus_weight` | `0.6` |
| `gradient_percentile` | `76.0` |
| `gradient_weight` | `0.25` |
| `minimum_side_consensus` | `0.1` |
| `minimum_side_gradient_support` | `0.03` |
| `source_diversity_weight` | `0.15` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (AMSRE + BFQ + SPBV + Page Background)

| Evidence source | Function | Interpretation |
|---|---|---|
| Calibrated child quadrilaterals | Primary | Runs calibrated AMSRE, BFQ, SPBV, and Page Background as four deliberately distinct evidence families. |
| Side-level consensus | Generator | Recombines top/right/bottom/left boundaries and rewards sides independently supported by the other child quadrilaterals. |
| Gradient support | Validation | Checks each fused side against image-gradient evidence while giving the radial lineage one seat through AMSRE. |
| Source diversity | Robustness | Rewards fused quadrilaterals whose four sides draw from multiple hypothesis families. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 0 |
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 42 | 9 | 378 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `156ff0241cc1` | `baseline` | 0.9743 | 0.9638 | 0.0103 | +0.0000 | 0.9743 | 0 | reference | reference |
| 1 | unknown | `unknown` | `04e26e43dccf` | `04e26e43dccf` | 0.9743 | 0.9638 | 0.0103 | +0.0000 | 0.9743 | 0 | 45.5s | 0.71% |
| 2 | unknown | `unknown` | `e356abfa1acb` | `e356abfa1acb` | 0.9743 | 0.9638 | 0.0103 | +0.0000 | 0.9743 | 0 | 43.5s | 0.67% |
| 3 | unknown | `unknown` | `9ee30c2d1f2b` | `9ee30c2d1f2b` | 0.9743 | 0.9638 | 0.0103 | +0.0000 | 0.9743 | 0 | 39.7s | 0.46% |
| 4 | unknown | `unknown` | `06d18ff8f106` | `06d18ff8f106` | 0.9743 | 0.9638 | 0.0103 | +0.0000 | 0.9743 | 0 | 42.9s | 0.65% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — amsre_bfq_spbv_pbg

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `baseline` | 0.9751 | 0.9751 | +0.0000 | Unchanged |
| 5 | `unknown` | `baseline` | 0.9761 | 0.9761 | +0.0000 | Unchanged |
| 6 | `unknown` | `baseline` | 0.9920 | 0.9920 | +0.0000 | Unchanged |
| 9 | `unknown` | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `unknown` | `baseline` | 0.9643 | 0.9643 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **1h 18m 41s** wall-clock time.

**Stabilization Interpretation:** Unavailable because the completed-search fraction was not recorded.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — amsre_bfq_spbv_pbg

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260815-190041`
- Calibration schema: `1.1`
- Detector: `amsre_bfq_spbv_pbg`
- Detector configuration: `hth-pipeline/config/detectors/amsre_bfq_spbv_pbg.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `fffeed69fec4c7de6236b51c9d1bc562d28a4b1b`
- Source commit: `45ec2543963ce9ef27f60718827a34da455fb17a`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `9`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `156ff0241cc1`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.9743`
- Avg IoU Success: `0.9743`
- Worst Golden Set page (Min IoU): `0.9638`
- Page-to-page StdDev: `0.0103`
- Calibration evidence: `High`
- Dormant parameters: `consensus_weight, gradient_percentile, gradient_weight, minimum_side_gradient_support, source_diversity_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- 5 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 50177 |
| Parameter sets evaluated | 50177 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 49898 (99.4%) |
| Best Avg IoU | 0.9743 |
| Minimum Avg IoU | 0.5807 |
| Avg IoU StdDev | 0.0270 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 45274 (90.2%) |
| Equivalent-best configurations (within 0.0001) | 30913 (61.6%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 50177 | 100.0% | 1d 1h 29m 11s | 1.0× |
| Non-dormant | 50625 | 100.9% | 1d 1h 42m 50s | 1.0× |
| Low+ | 50625 | 100.9% | 1d 1h 42m 50s | 1.0× |
| Moderate+ | 50625 | 100.9% | 1d 1h 42m 50s | 1.0× |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `consensus_tolerance_fraction` | Moderate | 0.0837 | 0.0409 | 94.7% | `0.00896` (0.9743), `0.009094` (0.9743), `0.009229` (0.9743) | current run |
| `minimum_side_consensus` | Moderate | 0.0603 | 0.0343 | 100.0% | `0.1` (0.9743), `0.49843` (0.9740), `0.496188` (0.9740) | current run |
| `consensus_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.6` (0.9743) | current run |
| `gradient_percentile` | Dormant | 0.0000 | 0.0000 | 100.0% | `76` (0.9743) | current run |
| `gradient_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.9743) | current run |
| `minimum_side_gradient_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.9743) | current run |
| `source_diversity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.9743) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consensus_weight`, `gradient_percentile`, `gradient_weight`, `minimum_side_gradient_support`, `source_diversity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `consensus_tolerance_fraction` × `minimum_side_consensus` | 1.0000 | 0.9169 | 25089 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9707 | 0.0000 | 0.9751 | 0.0653 | 99.5% |
| 5 | 0.9707 | 0.0000 | 0.9913 | 0.0725 | 99.4% |
| 6 | 0.9917 | 0.9911 | 0.9920 | 0.0004 | 100.0% |
| 9 | 0.9633 | 0.9539 | 0.9638 | 0.0022 | 100.0% |
| 10 | 0.9636 | 0.9574 | 0.9643 | 0.0021 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="border-energy-validator-borderenergy-2"></a>
<details>
<summary><strong>Border Energy Validator (`border_energy`)</strong></summary>

**Status:** complete

## Run Information — border_energy

### Build Provenance

- Run ID: `run-20260810-192350`
- Detector: `border_energy`
- Strategy: `exhaustive`
- Pipeline commit: `650cc2492369`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:19:49.941606+00:00`
- Finished: `2026-08-10T19:23:49.071606+00:00`
- Wall-clock elapsed: `3m 59s`
- Est. serial runtime: `1h 3m`
- Effective acceleration: `15.81×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `6562`
- Parameter sets evaluated: `6562`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — border_energy

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | 0.9063 | 1 | 546 ms |
| Baseline | `HTH-0001` | `unknown` | `unknown` | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | 0.9237 | 2 | 257 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`650cc2492369`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `74e2112aac01` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `band_fraction` | `0.015` |
| `energy_weight` | `0.3` |
| `epsilon_max_fraction` | `0.03` |
| `gaussian_sigma` | `0.8` |
| `minimum_border_energy` | `0.05` |
| `minimum_contour_area_fraction` | `0.08` |
| `minimum_rectangularity` | `0.45` |
| `minimum_side_consistency` | `0.3` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Contour Quad + Border Energy)

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour quadrilateral | Generator | Produces candidate page geometry. |
| Sobel border energy | Validator | Measures gradient magnitude in a narrow band along each proposed border. |
| Side consistency | Validation | Requires all four sides to carry comparable boundary evidence. |
| Fusion score | Scoring | Combines contour quality, border energy, and side consistency. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 0 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 2 | 8 | 16 | `rh8-al325` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | -0.1708 | 0.9237 | 2 | reference | reference |
| 1 | unknown | `unknown` | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 2.5s | 0.87% |
| 2 | unknown | `unknown` | `e6a92aa03adc` | `e6a92aa03adc` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 2.5s | 0.94% |
| 3 | unknown | `unknown` | `10122ecc688c` | `10122ecc688c` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 3s | 1.11% |
| 4 | unknown | `unknown` | `495c895fab0e` | `495c895fab0e` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 4.3s | 1.69% |
| 5 | unknown | `unknown` | `20154950810f` | `20154950810f` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 4.1s | 1.60% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — border_energy

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `74e2112aac01` | 0.0000 | 0.8542 | +0.8542 | Recovered |
| 5 | `unknown` | `74e2112aac01` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `unknown` | `74e2112aac01` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `unknown` | `74e2112aac01` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `unknown` | `74e2112aac01` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **3m 59s** wall-clock time.

**Stabilization Interpretation:** Unavailable because the completed-search fraction was not recorded.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `1`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `unknown` | `74e2112aac01` | 0.0000 | No polygon found |

## Calibration Intelligence — border_energy

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-192350`
- Calibration schema: `1.1`
- Detector: `border_energy`
- Detector configuration: `hth-pipeline/config/detectors/border_energy.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `650cc24923691a3423eba18e11808024c21bddf3`
- Source commit: `2f6dab3da255cae9f8d5a7aa211218a8fed4a109`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `8`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `74e2112aac01`
- Recommended parameter short name: `74e2112aac01`
- Best observed Avg IoU: `0.7250`
- Avg IoU Success: `0.9063`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3651`
- Calibration evidence: `Medium`
- Dormant parameters: `consistency_weight, contour_weight, energy_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 6 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 6562 of 6562 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7250 |
| Minimum Avg IoU | 0.1724 |
| Avg IoU StdDev | 0.1328 |
| Winner stabilized after | 57 parameter sets |
| Winner stabilized | 2.5s (1% of search) |
| Near-best coverage (basin; within 0.0010) | 1296 (19.8%) |
| Equivalent-best configurations (within 0.0001) | 1296 (19.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 59m 42s | 1.0× |
| Non-dormant | 81 | 1.2% | 44.2s | 81.0× |
| Low+ | 81 | 1.2% | 44.2s | 81.0× |
| Moderate+ | 9 | 0.1% | 4.9s | 729.1× |
| Important+ | 9 | 0.1% | 4.9s | 729.1× |
| Critical | 3 | 0.0% | 1.6s | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_side_consistency` | Critical | 0.5951 | 0.2495 | 33.3% | `0.3` (0.6554), `0.45` (0.5542), `0.6` (0.4059) | current run |
| `band_fraction` | Important | 0.1173 | 0.1102 | 100.0% | `0.015` (0.5985), `0.008` (0.5287), `0.004` (0.4883) | current run |
| `gaussian_sigma` | Low | 0.0252 | 0.0459 | 100.0% | `1.8` (0.5683), `0.8` (0.5248), `1.2` (0.5224) | current run |
| `minimum_border_energy` | Low | 0.0020 | 0.0127 | 100.0% | `0.1` (0.5427), `0.05` (0.5427), `0.18` (0.5301) | current run |
| `consistency_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.15` (0.5542) | current run |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.45` (0.5542) | current run |
| `energy_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.5385), `0.3` (0.5385), `0.5` (0.5385) | current run |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.5385), `0.03` (0.5385), `0.06` (0.5385) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.5385), `0.08` (0.5385), `0.2` (0.5385) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.5385), `0.45` (0.5385), `0.7` (0.5385) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consistency_weight`, `contour_weight`, `energy_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_side_consistency` × `band_fraction` | 0.8355 | 0.2404 | 6562 |
| `minimum_side_consistency` × `gaussian_sigma` | 0.6678 | 0.0727 | 6562 |
| `band_fraction` × `gaussian_sigma` | 0.1776 | 0.0602 | 6562 |
| `band_fraction` × `minimum_border_energy` | 0.1234 | 0.0061 | 6562 |
| `minimum_side_consistency` × `minimum_border_energy` | 0.6012 | 0.0061 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.1687 | 0.0000 | 0.8542 | 0.3401 | 19.8% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8567 | 0.0000 | 0.9638 | 0.3029 | 88.9% |
| 10 | 0.8054 | 0.0000 | 0.9454 | 0.3358 | 85.2% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="border-fusion-quad-borderfusionquad-2"></a>
<details>
<summary><strong>Border Fusion Quad (`border_fusion_quad`)</strong></summary>

**Status:** complete

## Run Information — border_fusion_quad

### Build Provenance

- Run ID: `run-20260814-094205`
- Detector: `border_fusion_quad`
- Strategy: `exhaustive`
- Pipeline commit: `1000d4a6d7b9`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-13T22:12:07.713700+00:00`
- Finished: `2026-08-14T09:40:54.463675+00:00`
- Wall-clock elapsed: `11h 28m 47s`
- Est. serial runtime: `7d 12h 38m 49s`
- Effective acceleration: `15.74×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `539001`
- Parameter sets evaluated: `539001`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — border_fusion_quad

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `0025dba6a844` | `unknown` | `2370e6cea486` | `2370e6cea486` | 0.9707 | 0.9588 | 0.0112 | 0.9707 | 0 | 1.1s |
| Baseline | `HTH-0001` | `0025dba6a844` | `unknown` | `17b4a7b30cd9` | `baseline` | 0.8890 | 0.5825 | 0.1538 | 0.8890 | 0 | 237 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`1000d4a6d7b9`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `2370e6cea486` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `gradient_percentile` | `68` |
| `gradient_weight` | `0.15` |
| `minimum_area_fraction` | `0.08` |
| `minimum_side_gradient_support` | `0.06` |
| `source_confidence_weight` | `0.4` |
| `source_diversity_weight` | `0.0` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Radial + Polar + Gradient)

| Evidence source | Function | Interpretation |
|---|---|---|
| Radial/Polar/Gradient child quads | Primary | Supplies independent top/right/bottom/left boundary hypotheses from three detector families. |
| Side-level recombination | Generator | Allows each page side to come from the child detector that supports it best. |
| Gradient side support | Validation | Requires all four fused sides to coincide with image-gradient evidence. |
| Source diversity | Validation | Requires the selected quadrilateral to use evidence from multiple child detectors. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 8 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto-fallback-no-shape-history` | 4 | 4 | 16 | `rh8-al317` | 4 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `17b4a7b30cd9` | `baseline` | 0.8890 | 0.5825 | 0.1538 | -0.0817 | 0.8890 | 0 | reference | reference |
| 1 | unknown | `unknown` | `2370e6cea486` | `2370e6cea486` | 0.9707 | 0.9588 | 0.0112 | +0.0000 | 0.9707 | 0 | 9.6s | 0.02% |
| 2 | unknown | `unknown` | `b3f274ef2780` | `b3f274ef2780` | 0.9707 | 0.9588 | 0.0112 | +0.0000 | 0.9707 | 0 | 10.6s | 0.02% |
| 3 | unknown | `unknown` | `5ad0dc18eb89` | `5ad0dc18eb89` | 0.9707 | 0.9588 | 0.0112 | +0.0000 | 0.9707 | 0 | 11.8s | 0.03% |
| 4 | unknown | `unknown` | `66b8224f5bc3` | `66b8224f5bc3` | 0.9707 | 0.9588 | 0.0112 | +0.0000 | 0.9707 | 0 | 17.1s | 0.04% |
| 5 | unknown | `unknown` | `0f8997774e99` | `0f8997774e99` | 0.9707 | 0.9588 | 0.0112 | +0.0000 | 0.9707 | 0 | 17.9s | 0.04% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — border_fusion_quad

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `2370e6cea486` | 0.9520 | 0.9655 | +0.0135 | Improved |
| 5 | `unknown` | `2370e6cea486` | 0.5825 | 0.9734 | +0.3908 | Improved |
| 6 | `unknown` | `2370e6cea486` | 0.9911 | 0.9911 | +0.0000 | Unchanged |
| 9 | `unknown` | `2370e6cea486` | 0.9588 | 0.9588 | +0.0000 | Unchanged |
| 10 | `unknown` | `2370e6cea486` | 0.9607 | 0.9650 | +0.0043 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 4 | `unknown` | `0b2e65800857` | 1.4s | 0.00% |
| 5 | `unknown` | `c3ac8f265804` | 1.5s | 0.00% |
| 6 | `unknown` | `7902b66fe34a` | 9.5s | 0.02% |
| 7 | `unknown` | `00d13408c13c` | 9.5s | 0.02% |
| 8 (final) | `unknown` | `2370e6cea486` | 9.6s | 0.02% |

Total winner changes: **8**.
Search completed in **11h 28m 47s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — border_fusion_quad

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260814-094205`
- Calibration schema: `1.1`
- Detector: `border_fusion_quad`
- Detector configuration: `hth-pipeline/config/detectors/border_fusion_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1000d4a6d7b9b8f1bd73682a42f3c26d9ba73f62`
- Source commit: `911cc51ebe4f99e595f4968997059b961e7c987f`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `4`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `2370e6cea486`
- Recommended parameter short name: `2370e6cea486`
- Best observed Avg IoU: `0.9707`
- Avg IoU Success: `0.9707`
- Worst Golden Set page (Min IoU): `0.9588`
- Page-to-page StdDev: `0.0112`
- Calibration evidence: `High`
- Dormant parameters: `source_confidence_weight, source_diversity_weight, area_weight, bbox_padding_fraction, maximum_area_fraction, minimum_child_candidates, minimum_child_confidence, minimum_distinct_sources, minimum_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 9 of 12 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 539001 |
| Parameter sets evaluated | 539001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 534381 (99.1%) |
| Best Avg IoU | 0.9707 |
| Minimum Avg IoU | 0.6649 |
| Avg IoU StdDev | 0.0394 |
| Winner stabilized after | 115 parameter sets |
| Winner stabilized | 9.6s (0% of search) |
| Near-best coverage (basin; within 0.0010) | 28900 (5.4%) |
| Equivalent-best configurations (within 0.0001) | 4410 (0.8%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 539001 | 100.0% | 6d 20h 59m 57s | 1.0× |
| Non-dormant | 4004 | 0.7% | 1h 13m 33s | 134.6× |
| Low+ | 4004 | 0.7% | 1h 13m 33s | 134.6× |
| Moderate+ | 4004 | 0.7% | 1h 13m 33s | 134.6× |
| Important+ | 154 | 0.0% | 2m 50s | 3500.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_weight` | Important | 0.2369 | 0.0553 | 63.6% | `0.225` (0.9419), `0.2` (0.9403), `0.15` (0.9273) | current run |
| `minimum_side_gradient_support` | Important | 0.1783 | 0.0564 | 78.6% | `0.01` (0.9267), `0` (0.9262), `0.02` (0.9257) | current run |
| `gradient_percentile` | Moderate | 0.0459 | 0.0397 | 92.3% | `69` (0.9159), `68` (0.9158), `76` (0.9154) | current run |
| `source_confidence_weight` | Dormant | 0.0009 | 0.0034 | 100.0% | `0.45` (0.9126), `0.5` (0.9125), `0.55` (0.9125) | current run |
| `source_diversity_weight` | Dormant | 0.0001 | 0.0010 | 75.0% | `0.15` (0.9121), `0.05` (0.9114), `0` (0.9111) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.15` (0.8890) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0` (0.8890) | current run |
| `maximum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.8890) | current run |
| `minimum_child_candidates` | Dormant | 0.0000 | 0.0000 | 0.0% | `2` (0.8890) | current run |
| `minimum_child_confidence` | Dormant | 0.0000 | 0.0000 | 0.0% | `0` (0.8890) | current run |
| `minimum_distinct_sources` | Dormant | 0.0000 | 0.0000 | 0.0% | `2` (0.8890) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.9114), `0.12` (0.9114), `0.26` (0.9114) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`source_confidence_weight`, `source_diversity_weight`, `area_weight`, `bbox_padding_fraction`, `maximum_area_fraction`, `minimum_child_candidates`, `minimum_child_confidence`, `minimum_distinct_sources`, `minimum_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `gradient_weight` × `minimum_side_gradient_support` | 0.5152 | 0.2772 | 49001 |
| `minimum_side_gradient_support` × `gradient_percentile` | 0.4418 | 0.2621 | 49001 |
| `gradient_weight` × `gradient_percentile` | 0.3552 | 0.1172 | 49001 |
| `gradient_weight` × `source_confidence_weight` | 0.2518 | 0.0139 | 49001 |
| `gradient_percentile` × `source_confidence_weight` | 0.0521 | 0.0055 | 49001 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9565 | 0.8681 | 0.9686 | 0.0176 | 100.0% |
| 5 | 0.7249 | 0.5776 | 0.9734 | 0.1812 | 100.0% |
| 6 | 0.9804 | 0.0000 | 0.9911 | 0.0913 | 99.1% |
| 9 | 0.9374 | 0.8238 | 0.9588 | 0.0459 | 100.0% |
| 10 | 0.9579 | 0.8854 | 0.9660 | 0.0167 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="connected-components-components-2"></a>
<details>
<summary><strong>Connected Components (`components`)</strong></summary>

**Status:** complete

## Run Information — components

### Build Provenance

- Run ID: `run-20260810-192816`
- Detector: `components`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:27:32.864369+00:00`
- Finished: `2026-08-10T19:28:13.619664+00:00`
- Wall-clock elapsed: `40.8s`
- Est. serial runtime: `10m 4s`
- Effective acceleration: `14.81×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `19683`
- Parameter sets evaluated: `19683`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — components

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | 0.7897 | 0 | 21 ms |
| Baseline | `HTH-0001` | `unknown` | `unknown` | `4e09dc84fa8a` | `baseline` | 0.7185 | 0.2413 | 0.2967 | 0.7185 | 0 | 17 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `f1929c8e2655` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.0` |
| `merge_area_ratio` | `0.01` |
| `merge_gap_fraction` | `0.035` |
| `minimum_bbox_area_fraction` | `0.08` |
| `minimum_component_area_fraction` | `0.00075` |
| `minimum_component_area_px` | `10` |
| `minimum_selected_area_fraction` | `0.02` |
| `morphology_close_fraction` | `0.008` |
| `morphology_dilate_fraction` | `0.03` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Connected-component envelope | Primary | Generates a page-region hypothesis from grouped foreground components. |
| Morphological grouping | Supporting | Controls how fragmented marks are joined before envelope extraction. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 3 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 2 | 8 | 16 | `rh8-al320` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `4e09dc84fa8a` | `baseline` | 0.7185 | 0.2413 | 0.2967 | -0.0712 | 0.7185 | 0 | reference | reference |
| 1 | unknown | `unknown` | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 578 ms | 1.27% |
| 2 | unknown | `unknown` | `6a55e49277e7` | `6a55e49277e7` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 630 ms | 1.40% |
| 3 | unknown | `unknown` | `62e19d69cdf6` | `62e19d69cdf6` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 660 ms | 1.46% |
| 4 | unknown | `unknown` | `966b20b76507` | `966b20b76507` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 688 ms | 1.53% |
| 5 | unknown | `unknown` | `9230a0393357` | `9230a0393357` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 741 ms | 1.68% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — components

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `f1929c8e2655` | 0.9734 | 0.9533 | -0.0201 | Regressed |
| 5 | `unknown` | `f1929c8e2655` | 0.4973 | 0.5725 | +0.0752 | Improved |
| 6 | `unknown` | `f1929c8e2655` | 0.2413 | 0.6018 | +0.3605 | Improved |
| 9 | `unknown` | `f1929c8e2655` | 0.9314 | 0.9018 | -0.0296 | Regressed |
| 10 | `unknown` | `f1929c8e2655` | 0.9491 | 0.9192 | -0.0299 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `732d1fd40ae7` | 101 ms | 0.01% |
| 2 | `unknown` | `b6a644d99d2e` | 102 ms | 0.01% |
| 3 (final) | `unknown` | `2f8c682579f8` | 204 ms | 0.28% |

Total winner changes: **3**.
Search completed in **40.8s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `3`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `f1929c8e2655` | 0.9533 | Regressed |
| 9 | `unknown` | `f1929c8e2655` | 0.9018 | Regressed |
| 10 | `unknown` | `f1929c8e2655` | 0.9192 | Regressed |

## Calibration Intelligence — components

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-192816`
- Calibration schema: `1.1`
- Detector: `components`
- Detector configuration: `hth-pipeline/config/detectors/components.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `89419c198d82b23cc47c96f3b15ea3047bbb108f`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `8`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `f1929c8e2655`
- Recommended parameter short name: `f1929c8e2655`
- Best observed Avg IoU: `0.7897`
- Avg IoU Success: `0.7897`
- Worst Golden Set page (Min IoU): `0.5725`
- Page-to-page StdDev: `0.1665`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, minimum_component_area_px`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 19683 |
| Parameter sets evaluated | 19683 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 14916 (75.8%) |
| Best Avg IoU | 0.7897 |
| Minimum Avg IoU | 0.6456 |
| Avg IoU StdDev | 0.0411 |
| Winner stabilized after | 249 parameter sets |
| Winner stabilized | 578 ms (1% of search) |
| Near-best coverage (basin; within 0.0010) | 162 (0.8%) |
| Equivalent-best configurations (within 0.0001) | 162 (0.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19683 | 100.0% | 6m 54s | 1.0× |
| Non-dormant | 2187 | 11.1% | 46s | 9.0× |
| Low+ | 2187 | 11.1% | 46s | 9.0× |
| Moderate+ | 243 | 1.2% | 5.1s | 81.0× |
| Important+ | 3 | 0.0% | 63 ms | 6561.0× |
| Critical | 3 | 0.0% | 63 ms | 6561.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `morphology_dilate_fraction` | Critical | 0.4776 | 0.0693 | 33.3% | `0.03` (0.7658), `0.015` (0.7266), `0.008` (0.6965) | current run |
| `merge_gap_fraction` | Moderate | 0.0940 | 0.0269 | 66.7% | `0.06` (0.7474), `0.035` (0.7209), `0.02` (0.7206) | current run |
| `minimum_selected_area_fraction` | Moderate | 0.0620 | 0.0217 | 100.0% | `0.02` (0.7369), `0.04` (0.7369), `0.07` (0.7152) | current run |
| `minimum_component_area_fraction` | Moderate | 0.0371 | 0.0179 | 33.3% | `0.00075` (0.7408), `0.0015` (0.7253), `0.003` (0.7229) | current run |
| `bbox_padding_fraction` | Moderate | 0.0362 | 0.0183 | 33.3% | `0` (0.7373), `0.005` (0.7328), `0.015` (0.7189) | current run |
| `merge_area_ratio` | Low | 0.0259 | 0.0161 | 33.3% | `0.01` (0.7372), `0.02` (0.7306), `0.05` (0.7211) | current run |
| `morphology_close_fraction` | Low | 0.0120 | 0.0096 | 100.0% | `0.016` (0.7360), `0.004` (0.7265), `0.008` (0.7265) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.7297), `0.12` (0.7296), `0.18` (0.7296) | current run |
| `minimum_component_area_px` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.7296), `25` (0.7296), `50` (0.7296) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `minimum_component_area_px`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `morphology_dilate_fraction` × `merge_gap_fraction` | 0.6172 | 0.1395 | 19683 |
| `morphology_dilate_fraction` × `minimum_selected_area_fraction` | 0.5739 | 0.0963 | 19683 |
| `merge_gap_fraction` × `minimum_selected_area_fraction` | 0.1561 | 0.0622 | 19683 |
| `morphology_dilate_fraction` × `minimum_component_area_fraction` | 0.5294 | 0.0517 | 19683 |
| `merge_gap_fraction` × `minimum_component_area_fraction` | 0.1353 | 0.0414 | 19683 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9491 | 0.9018 | 0.9734 | 0.0235 | 100.0% |
| 5 | 0.5487 | 0.4892 | 0.5929 | 0.0340 | 100.0% |
| 6 | 0.3305 | 0.0000 | 0.6404 | 0.2159 | 75.8% |
| 9 | 0.9012 | 0.8499 | 0.9429 | 0.0279 | 100.0% |
| 10 | 0.9187 | 0.8692 | 0.9543 | 0.0265 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="consensus-quadrilateral-consensusquad-2"></a>
<details>
<summary><strong>Consensus Quadrilateral (`consensus_quad`)</strong></summary>

**Status:** complete

## Run Information — consensus_quad

### Build Provenance

- Run ID: `run-20260810-192735`
- Detector: `consensus_quad`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:27:35.848808+00:00`
- Finished: `2026-08-10T19:27:57.107898+00:00`
- Wall-clock elapsed: `21.3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `243`
- Parameter sets evaluated: `243`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — consensus_quad

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | 0.9213 | 2 | 1.4s |
| Baseline | `HTH-0001` | `unknown` | `unknown` | `dce471449373` | `baseline` | 0.5513 | 0.0000 | 0.4513 | 0.9188 | 2 | 571 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `f387da7ebb7e` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `contour_quad_weight` | `0.75` |
| `edge_contour_weight` | `0.25` |
| `maximum_mean_corner_distance_fraction` | `0.025` |
| `minimum_consensus_confidence` | `0.1` |
| `minimum_polygon_iou` | `0.8` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Contour Quad + Edge Contour)

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour Quad vote | Primary | Supplies one geometric quadrilateral hypothesis. |
| Edge Contour vote | Primary | Supplies an independently scored edge-supported hypothesis. |
| Polygon agreement | Decision | Requires sufficient IoU and corner agreement before fusion. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 2 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 3 |
| Total metric improvements | 5 |
| Parameter sets with improvements | 5 |
| Winner changes | 2 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 1 | 16 | 16 | `rh8-al323` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `dce471449373` | `baseline` | 0.5513 | 0.0000 | 0.4513 | -0.0015 | 0.9188 | 2 | reference | reference |
| 1 | unknown | `unknown` | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 4.9s | 16.53% |
| 2 | unknown | `unknown` | `d3afdfd96e35` | `d3afdfd96e35` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 4.9s | 15.70% |
| 3 | unknown | `unknown` | `a00dcf94f01e` | `a00dcf94f01e` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 4.9s | 17.36% |
| 4 | unknown | `unknown` | `855195437d31` | `855195437d31` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 7.7s | 32.23% |
| 5 | unknown | `unknown` | `99d0beb98285` | `99d0beb98285` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 7.7s | 33.88% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — consensus_quad

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `f387da7ebb7e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `unknown` | `f387da7ebb7e` | 0.8616 | 0.8616 | +0.0000 | Unchanged |
| 6 | `unknown` | `f387da7ebb7e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `unknown` | `f387da7ebb7e` | 0.9647 | 0.9636 | -0.0011 | Regressed |
| 10 | `unknown` | `f387da7ebb7e` | 0.9302 | 0.9386 | +0.0085 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `a0704ed94d82` | 4.5s | 15.29% |
| 2 (final) | `unknown` | `d3afdfd96e35` | 4.9s | 15.70% |

Total winner changes: **2**.
Search completed in **21.3s** wall-clock time.

**Stabilization Interpretation:** Moderate exploration — the final winner emerged after 10–40% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `2`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `f387da7ebb7e` | 0.0000 | No polygon found |
| 6 | `unknown` | `f387da7ebb7e` | 0.0000 | No polygon found |
| 9 | `unknown` | `f387da7ebb7e` | 0.9636 | Regressed |

## Calibration Intelligence — consensus_quad

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-192735`
- Calibration schema: `1.1`
- Detector: `consensus_quad`
- Detector configuration: `hth-pipeline/config/detectors/consensus_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `89419c198d82b23cc47c96f3b15ea3047bbb108f`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `16`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `f387da7ebb7e`
- Recommended parameter short name: `f387da7ebb7e`
- Best observed Avg IoU: `0.5528`
- Avg IoU Success: `0.9213`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4526`
- Calibration evidence: `Medium`
- Dormant parameters: `edge_contour_weight, contour_quad_weight, minimum_consensus_confidence`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 3 of 5 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 243 of 243 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 243 |
| Parameter sets evaluated | 243 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5528 |
| Minimum Avg IoU | 0.3649 |
| Avg IoU StdDev | 0.0921 |
| Winner stabilized after | 40 parameter sets |
| Winner stabilized | 4.9s (17% of search) |
| Near-best coverage (basin; within 0.0010) | 24 (9.9%) |
| Equivalent-best configurations (within 0.0001) | 12 (4.9%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 243 | 100.0% | 5m 48s | 1.0× |
| Non-dormant | 9 | 3.7% | 12.9s | 27.0× |
| Low+ | 9 | 3.7% | 12.9s | 27.0× |
| Moderate+ | 9 | 3.7% | 12.9s | 27.0× |
| Important+ | 9 | 3.7% | 12.9s | 27.0× |
| Critical | 9 | 3.7% | 12.9s | 27.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `maximum_mean_corner_distance_fraction` | Critical | 0.3999 | 0.1235 | 66.7% | `0.025` (0.4887), `0.04` (0.4887), `0.015` (0.3651) | current run |
| `minimum_polygon_iou` | Critical | 0.3999 | 0.1235 | 66.7% | `0.8` (0.4887), `0.9` (0.4887), `0.95` (0.3651) | current run |
| `edge_contour_weight` | Dormant | 0.0000 | 0.0014 | 33.3% | `0.25` (0.4483), `0.5` (0.4474), `0.75` (0.4468) | current run |
| `contour_quad_weight` | Dormant | 0.0000 | 0.0013 | 66.7% | `0.75` (0.4480), `0.5` (0.4478), `0.25` (0.4467) | current run |
| `minimum_consensus_confidence` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.4475), `0.2` (0.4475), `0.35` (0.4475) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`edge_contour_weight`, `contour_quad_weight`, `minimum_consensus_confidence`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_mean_corner_distance_fraction` × `minimum_polygon_iou` | 0.9998 | 0.5999 | 243 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.8617 | 0.8616 | 0.8624 | 0.0003 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9640 | 0.9627 | 0.9647 | 0.0007 | 100.0% |
| 10 | 0.4118 | 0.0000 | 0.9386 | 0.4604 | 44.4% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-envelope-contour-2"></a>
<details>
<summary><strong>Contour Envelope (`contour`)</strong></summary>

**Status:** complete

## Run Information — contour

### Build Provenance

- Run ID: `run-20260810-192734`
- Detector: `contour`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:27:34.524224+00:00`
- Finished: `2026-08-10T19:27:39.166609+00:00`
- Wall-clock elapsed: `4.6s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1458`
- Parameter sets evaluated: `1458`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | 34 ms |
| Baseline | `HTH-0001` | `unknown` | `unknown` | `6019a18e4c4e` | `baseline` | 0.6722 | 0.0000 | 0.3846 | 0.8403 | 1 | 9 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `7aed2fc501c5` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.005` |
| `close_iterations` | `2` |
| `close_kernel_fraction` | `0.018` |
| `merge_fragmented_contours` | `true` |
| `minimum_contour_area_fraction` | `0.06` |
| `polygon_epsilon_fraction` | `0.008` |
| `rectangularity_weight` | `0.1` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour geometry | Primary | Generates page-region hypotheses from thresholded contours. |
| Fragment merging | Supporting | Attempts to recover page boundaries split across multiple contours. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 4 |
| Minimum IoU improvements | 6 |
| StdDev improvements | 5 |
| Total metric improvements | 15 |
| Parameter sets with improvements | 6 |
| Winner changes | 4 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 1 | 16 | 16 | `rh8-al325` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `6019a18e4c4e` | `baseline` | 0.6722 | 0.0000 | 0.3846 | -0.1776 | 0.8403 | 1 | reference | reference |
| 1 | unknown | `unknown` | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 468 ms | 10.30% |
| 2 | unknown | `unknown` | `fe1e051ea449` | `fe1e051ea449` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 478 ms | 10.64% |
| 3 | unknown | `unknown` | `bf0386f44c6e` | `bf0386f44c6e` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 492 ms | 11.05% |
| 4 | unknown | `unknown` | `2cbcf16dd63a` | `2cbcf16dd63a` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 890 ms | 21.28% |
| 5 | unknown | `unknown` | `3fe11d0f3e41` | `3fe11d0f3e41` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 907 ms | 21.69% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `7aed2fc501c5` | 0.9648 | 0.9734 | +0.0086 | Improved |
| 5 | `unknown` | `7aed2fc501c5` | 0.4784 | 0.5457 | +0.0673 | Improved |
| 6 | `unknown` | `7aed2fc501c5` | 0.0000 | 0.8392 | +0.8392 | Recovered |
| 9 | `unknown` | `7aed2fc501c5` | 0.9585 | 0.9390 | -0.0195 | Regressed |
| 10 | `unknown` | `7aed2fc501c5` | 0.9593 | 0.9517 | -0.0076 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `a20447ccca1e` | 79 ms | 0.21% |
| 2 | `unknown` | `2f4c8ab8f1e0` | 85 ms | 0.48% |
| 3 | `unknown` | `a577ea13a69c` | 460 ms | 10.02% |
| 4 (final) | `unknown` | `7aed2fc501c5` | 468 ms | 10.30% |

Total winner changes: **4**.
Search completed in **4.6s** wall-clock time.

**Stabilization Interpretation:** Moderate exploration — the final winner emerged after 10–40% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 9 | `unknown` | `7aed2fc501c5` | 0.9390 | Regressed |
| 10 | `unknown` | `7aed2fc501c5` | 0.9517 | Regressed |

## Calibration Intelligence — contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-192734`
- Calibration schema: `1.1`
- Detector: `contour`
- Detector configuration: `hth-pipeline/config/detectors/contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `89419c198d82b23cc47c96f3b15ea3047bbb108f`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `16`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `7aed2fc501c5`
- Recommended parameter short name: `7aed2fc501c5`
- Best observed Avg IoU: `0.8498`
- Avg IoU Success: `0.8498`
- Worst Golden Set page (Min IoU): `0.5457`
- Page-to-page StdDev: `0.1589`
- Calibration evidence: `Medium`
- Dormant parameters: `close_iterations, close_kernel_fraction, minimum_contour_area_fraction, polygon_epsilon_fraction, rectangularity_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 5 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 1458 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 729 (50.0%) |
| Best Avg IoU | 0.8498 |
| Minimum Avg IoU | 0.6586 |
| Avg IoU StdDev | 0.0847 |
| Winner stabilized after | 150 parameter sets |
| Winner stabilized | 468 ms (10% of search) |
| Near-best coverage (basin; within 0.0010) | 27 (1.9%) |
| Equivalent-best configurations (within 0.0001) | 27 (1.9%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1458 | 100.0% | 50.1s | 1.0× |
| Non-dormant | 6 | 0.4% | 206 ms | 243.0× |
| Low+ | 6 | 0.4% | 206 ms | 243.0× |
| Moderate+ | 2 | 0.1% | 69 ms | 729.0× |
| Important+ | 2 | 0.1% | 69 ms | 729.0× |
| Critical | 2 | 0.1% | 69 ms | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `merge_fragmented_contours` | Critical | 0.9954 | 0.1691 | 50.0% | `true` (0.8377), `false` (0.6686) | current run |
| `bbox_padding_fraction` | Low | 0.0023 | 0.0091 | 33.3% | `0.005` (0.7565), `0` (0.7555), `0.015` (0.7474) | current run |
| `close_iterations` | Dormant | 0.0004 | 0.0035 | 33.3% | `2` (0.7555), `0` (0.7519), `1` (0.7519) | current run |
| `close_kernel_fraction` | Dormant | 0.0004 | 0.0035 | 33.3% | `0.018` (0.7555), `0` (0.7519), `0.008` (0.7519) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.06` (0.7531), `0.12` (0.7531), `0.2` (0.7531) | current run |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.7531), `0.018` (0.7531), `0.035` (0.7531) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.7531), `0.25` (0.7531), `0.4` (0.7531) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_iterations`, `close_kernel_fraction`, `minimum_contour_area_fraction`, `polygon_epsilon_fraction`, `rectangularity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `merge_fragmented_contours` × `bbox_padding_fraction` | 0.9984 | 0.0030 | 1458 |
| `close_iterations` × `close_kernel_fraction` | 0.0015 | 0.0012 | 1458 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9638 | 0.9533 | 0.9734 | 0.0082 | 100.0% |
| 5 | 0.5020 | 0.4784 | 0.5725 | 0.0236 | 100.0% |
| 6 | 0.4227 | 0.0000 | 0.8763 | 0.4231 | 50.0% |
| 9 | 0.9331 | 0.9018 | 0.9585 | 0.0235 | 100.0% |
| 10 | 0.9439 | 0.9192 | 0.9593 | 0.0171 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-components-contourcomponents-2"></a>
<details>
<summary><strong>Contour + Components (`contour_components`)</strong></summary>

**Status:** complete

## Run Information — contour_components

### Build Provenance

- Run ID: `run-20260810-193127`
- Detector: `contour_components`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:27:36.540249+00:00`
- Finished: `2026-08-10T19:31:24.755273+00:00`
- Wall-clock elapsed: `3m 48s`
- Est. serial runtime: `57m 32s`
- Effective acceleration: `15.13×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `19684`
- Parameter sets evaluated: `19684`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour_components

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | 60 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `14818b491952` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `angle_weight` | `0.15` |
| `area_weight` | `0.25` |
| `close_iterations` | `1` |
| `close_kernel_fraction` | `0.008` |
| `component_bbox_padding_fraction` | `0.0` |
| `component_close_fraction` | `0.008` |
| `component_dilate_fraction` | `0.015` |
| `component_merge_area_ratio` | `0.02` |
| `component_merge_gap_fraction` | `0.035` |
| `component_minimum_area_fraction` | `0.0015` |
| `component_minimum_area_px` | `25` |
| `component_minimum_bbox_area_fraction` | `0.12` |
| `component_minimum_selected_area_fraction` | `0.04` |
| `component_weight` | `0.4` |
| `epsilon_max_fraction` | `0.04` |
| `epsilon_min_fraction` | `0.008` |
| `epsilon_steps` | `9` |
| `merge_fragmented_contours` | `true` |
| `minimum_component_score` | `0.05` |
| `minimum_contour_area_fraction` | `0.12` |
| `minimum_rectangularity` | `0.55` |
| `rectangularity_weight` | `0.2` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Contour Quad + Components)

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour quadrilateral | Generator | Produces candidate page quadrilaterals. |
| Component containment | Validator | Measures how well selected components fall within each candidate. |
| Component envelope overlap | Validator | Compares each contour candidate with the independent component envelope. |
| Component spread and density | Validator | Checks whether foreground evidence is distributed plausibly across the candidate. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 0 |
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 2 | 8 | 16 | `rh8-al321` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | reference | reference |
| 1 | unknown | `unknown` | `6931e3aea38a` | `6931e3aea38a` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 255 ms | 0.01% |
| 2 | unknown | `unknown` | `4339c3f69581` | `4339c3f69581` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 258 ms | 0.02% |
| 3 | unknown | `unknown` | `91d7206d1476` | `91d7206d1476` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 287 ms | 0.05% |
| 4 | unknown | `unknown` | `81a0687b7bc1` | `81a0687b7bc1` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 264 ms | 0.02% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour_components

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `baseline` | 0.8540 | 0.8540 | +0.0000 | Unchanged |
| 5 | `unknown` | `baseline` | 0.8616 | 0.8616 | +0.0000 | Unchanged |
| 6 | `unknown` | `baseline` | 0.7572 | 0.7572 | +0.0000 | Unchanged |
| 9 | `unknown` | `baseline` | 0.9636 | 0.9636 | +0.0000 | Unchanged |
| 10 | `unknown` | `baseline` | 0.8719 | 0.8719 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **3m 48s** wall-clock time.

**Stabilization Interpretation:** Unavailable because the completed-search fraction was not recorded.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — contour_components

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-193127`
- Calibration schema: `1.1`
- Detector: `contour_components`
- Detector configuration: `hth-pipeline/config/detectors/contour_components.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `89419c198d82b23cc47c96f3b15ea3047bbb108f`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `8`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `14818b491952`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8617`
- Avg IoU Success: `0.8617`
- Worst Golden Set page (Min IoU): `0.7572`
- Page-to-page StdDev: `0.0655`
- Calibration evidence: `High`
- Dormant parameters: `component_close_fraction, component_dilate_fraction, component_merge_gap_fraction, component_minimum_area_fraction, component_weight, epsilon_max_fraction, minimum_component_score, minimum_contour_area_fraction, minimum_rectangularity, angle_weight, area_weight, close_iterations, close_kernel_fraction, component_bbox_padding_fraction, component_merge_area_ratio, component_minimum_area_px, component_minimum_bbox_area_fraction, component_minimum_selected_area_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- Every measured parameter was dormant for this Golden Set and grid.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 19684 |
| Parameter sets evaluated | 19684 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 19684 (100.0%) |
| Best Avg IoU | 0.8617 |
| Minimum Avg IoU | 0.8617 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 19684 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 19684 (100.0%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19684 | 100.0% | 19m 37s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `component_close_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.004` (0.8617), `0.012` (0.8617), `0.008` (0.8617) | current run |
| `component_dilate_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.008` (0.8617), `0.025` (0.8617), `0.015` (0.8617) | current run |
| `component_merge_gap_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.06` (0.8617), `0.035` (0.8617) | current run |
| `component_minimum_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.0008` (0.8617), `0.003` (0.8617), `0.0015` (0.8617) | current run |
| `component_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.25` (0.8617), `0.55` (0.8617), `0.4` (0.8617) | current run |
| `epsilon_max_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8617), `0.06` (0.8617), `0.04` (0.8617) | current run |
| `minimum_component_score` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.12` (0.8617), `0.05` (0.8617) | current run |
| `minimum_contour_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.08` (0.8617), `0.18` (0.8617), `0.12` (0.8617) | current run |
| `minimum_rectangularity` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.45` (0.8617), `0.7` (0.8617), `0.55` (0.8617) | current run |
| `angle_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.15` (0.8617) | current run |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.25` (0.8617) | current run |
| `close_iterations` | Dormant | 0.0001 | 0.0000 | 100.0% | `1` (0.8617) | current run |
| `close_kernel_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.008` (0.8617) | current run |
| `component_bbox_padding_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0` (0.8617) | current run |
| `component_merge_area_ratio` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.02` (0.8617) | current run |
| `component_minimum_area_px` | Dormant | 0.0001 | 0.0000 | 100.0% | `25` (0.8617) | current run |
| `component_minimum_bbox_area_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.12` (0.8617) | current run |
| `component_minimum_selected_area_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.04` (0.8617) | current run |
| `epsilon_min_fraction` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.008` (0.8617) | current run |
| `epsilon_steps` | Dormant | 0.0001 | 0.0000 | 100.0% | `9` (0.8617) | current run |
| `merge_fragmented_contours` | Dormant | 0.0001 | 0.0000 | 100.0% | `true` (0.8617) | current run |
| `rectangularity_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.2` (0.8617) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`component_close_fraction`, `component_dilate_fraction`, `component_merge_gap_fraction`, `component_minimum_area_fraction`, `component_weight`, `epsilon_max_fraction`, `minimum_component_score`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `component_bbox_padding_fraction`, `component_merge_area_ratio`, `component_minimum_area_px`, `component_minimum_bbox_area_fraction`, `component_minimum_selected_area_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8540 | 0.8540 | 0.8540 | 0.0000 | 100.0% |
| 5 | 0.8616 | 0.8616 | 0.8616 | 0.0000 | 100.0% |
| 6 | 0.7572 | 0.7572 | 0.7572 | 0.0000 | 100.0% |
| 9 | 0.9636 | 0.9636 | 0.9636 | 0.0000 | 100.0% |
| 10 | 0.8719 | 0.8719 | 0.8719 | 0.0000 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-grabcut-contourgrabcut-2"></a>
<details>
<summary><strong>Contour + GrabCut (`contour_grabcut`)</strong></summary>

**Status:** complete

## Run Information — contour_grabcut

### Build Provenance

- Run ID: `run-20260810-223743`
- Detector: `contour_grabcut`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:28:11.904369+00:00`
- Finished: `2026-08-10T22:37:42.297736+00:00`
- Wall-clock elapsed: `3h 9m 30s`
- Est. serial runtime: `1d 21h 8m 24s`
- Effective acceleration: `14.29×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `6562`
- Parameter sets evaluated: `6562`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour_grabcut

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 28.3s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `3eec8a03f1de` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `agreement_weight` | `0.3` |
| `contour_epsilon_max_fraction` | `0.04` |
| `contour_minimum_area_fraction` | `0.12` |
| `contour_minimum_rectangularity` | `0.55` |
| `contour_weight` | `0.45` |
| `grabcut_border_fraction` | `0.02` |
| `grabcut_erosion_kernel_fraction` | `0.015` |
| `grabcut_iterations` | `3` |
| `grabcut_weight` | `0.25` |
| `minimum_agreement_iou` | `0.3` |
| `require_grabcut` | `false` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Contour Quad + GrabCut)

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour quadrilateral | Generator | Produces the candidate page geometry. |
| GrabCut foreground segmentation | Validator | Provides independent pixel-level foreground evidence. |
| Polygon agreement | Validation | Requires sufficient overlap between contour and GrabCut hypotheses. |
| Fusion score | Scoring | Combines contour quality, GrabCut quality, and hypothesis agreement. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 0 |
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 4 | 4 | 16 | `rh8-al325` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | reference | reference |
| 1 | unknown | `unknown` | `42fc63229bb3` | `42fc63229bb3` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 38.7s | 0.08% |
| 2 | unknown | `unknown` | `72f0d747f696` | `72f0d747f696` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 53.5s | 0.20% |
| 3 | unknown | `unknown` | `d4633ac4cc93` | `d4633ac4cc93` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 38.2s | 0.02% |
| 4 | unknown | `unknown` | `e35f2d10bf3d` | `e35f2d10bf3d` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 56.9s | 0.26% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour_grabcut

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `unknown` | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `unknown` | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `unknown` | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `unknown` | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **3h 9m 30s** wall-clock time.

**Stabilization Interpretation:** Unavailable because the completed-search fraction was not recorded.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — contour_grabcut

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-223743`
- Calibration schema: `1.1`
- Detector: `contour_grabcut`
- Detector configuration: `hth-pipeline/config/detectors/contour_grabcut.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `446e07532b131b5e57355f291530b89f6670b8f4`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `4`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `3eec8a03f1de`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `High`
- Dormant parameters: `agreement_weight, contour_epsilon_max_fraction, contour_minimum_area_fraction, contour_minimum_rectangularity, contour_weight, grabcut_border_fraction, grabcut_erosion_kernel_fraction, grabcut_iterations, grabcut_weight, minimum_agreement_iou, require_grabcut`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- Every measured parameter was dormant for this Golden Set and grid.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 6562 (100.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.8768 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 6562 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 6562 (100.0%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 2d 3h 40m 13s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `agreement_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) | current run |
| `contour_epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768), `0.06` (0.8768) | current run |
| `contour_minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768), `0.18` (0.8768) | current run |
| `contour_minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768), `0.7` (0.8768) | current run |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768) | current run |
| `grabcut_border_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.01` (0.8768), `0.02` (0.8768), `0.03` (0.8768) | current run |
| `grabcut_erosion_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8768) | current run |
| `grabcut_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8768), `3` (0.8768), `5` (0.8768) | current run |
| `grabcut_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.25` (0.8768), `0.35` (0.8768) | current run |
| `minimum_agreement_iou` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.3` (0.8768), `0.5` (0.8768) | current run |
| `require_grabcut` | Dormant | 0.0000 | 0.0000 | 100.0% | `false` (0.8768) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`agreement_weight`, `contour_epsilon_max_fraction`, `contour_minimum_area_fraction`, `contour_minimum_rectangularity`, `contour_weight`, `grabcut_border_fraction`, `grabcut_erosion_kernel_fraction`, `grabcut_iterations`, `grabcut_weight`, `minimum_agreement_iou`, `require_grabcut`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8542 | 0.8542 | 0.8542 | 0.0000 | 100.0% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.7589 | 0.7589 | 0.7589 | 0.0000 | 100.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-projection-contourprojection-2"></a>
<details>
<summary><strong>Contour + Projection (`contour_projection`)</strong></summary>

**Status:** complete

## Run Information — contour_projection

### Build Provenance

- Run ID: `run-20260810-193552`
- Detector: `contour_projection`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:28:29.654223+00:00`
- Finished: `2026-08-10T19:35:51.223907+00:00`
- Wall-clock elapsed: `7m 22s`
- Est. serial runtime: `1h 43m 5s`
- Effective acceleration: `14.01×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `6562`
- Parameter sets evaluated: `6562`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour_projection

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 458 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `0cd13eb1a471` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `angle_weight` | `0.2` |
| `area_weight` | `0.25` |
| `close_iterations` | `1` |
| `close_kernel_fraction` | `0.008` |
| `epsilon_max_fraction` | `0.04` |
| `epsilon_min_fraction` | `0.008` |
| `epsilon_steps` | `9` |
| `merge_fragmented_contours` | `true` |
| `minimum_contour_area_fraction` | `0.12` |
| `minimum_projection_score` | `0.08` |
| `minimum_rectangularity` | `0.55` |
| `projection_margin_fraction` | `0.06` |
| `projection_threshold_block_fraction` | `0.08` |
| `projection_threshold_c` | `9.0` |
| `projection_weight` | `0.3` |
| `rectangularity_weight` | `0.25` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Contour Quad + Projection)

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour quadrilateral | Generator | Produces candidate page quadrilaterals. |
| Horizontal projection profile | Validator | Scores text-band structure after candidate normalization. |
| Vertical coverage | Validator | Checks whether foreground structure spans the candidate height. |
| Ink density | Validator | Rejects implausibly empty or saturated candidate interiors. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 0 |
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 4 | 4 | 16 | `rh8-al323` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | reference | reference |
| 1 | unknown | `unknown` | `172304831b2e` | `172304831b2e` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.6s | 0.18% |
| 2 | unknown | `unknown` | `b71b6267963a` | `b71b6267963a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.5s | 0.14% |
| 3 | unknown | `unknown` | `8c229faefd09` | `8c229faefd09` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.6s | 0.17% |
| 4 | unknown | `unknown` | `3315664f787d` | `3315664f787d` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.5s | 0.15% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour_projection

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `unknown` | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `unknown` | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `unknown` | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `unknown` | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **7m 22s** wall-clock time.

**Stabilization Interpretation:** Unavailable because the completed-search fraction was not recorded.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — contour_projection

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-193552`
- Calibration schema: `1.1`
- Detector: `contour_projection`
- Detector configuration: `hth-pipeline/config/detectors/contour_projection.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `52212219a8f07a001587020df0bfe6a6518ba7e2`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `4`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `0cd13eb1a471`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `High`
- Dormant parameters: `angle_weight, area_weight, close_iterations, close_kernel_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_projection_score, minimum_rectangularity`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- 12 of 16 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 6562 (100.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.7946 |
| Avg IoU StdDev | 0.0215 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 6076 (92.6%) |
| Equivalent-best configurations (within 0.0001) | 6076 (92.6%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 50m 5s | 1.0× |
| Non-dormant | 81 | 1.2% | 37.1s | 81.0× |
| Low+ | 81 | 1.2% | 37.1s | 81.0× |
| Moderate+ | 27 | 0.4% | 12.4s | 243.0× |
| Important+ | 3 | 0.0% | 1.4s | 2187.3× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `projection_threshold_block_fraction` | Important | 0.1600 | 0.0183 | 100.0% | `0.05` (0.8768), `0.08` (0.8768), `0.12` (0.8586) | current run |
| `projection_weight` | Moderate | 0.0933 | 0.0152 | 100.0% | `0.2` (0.8768), `0.3` (0.8738), `0.4` (0.8616) | current run |
| `projection_threshold_c` | Moderate | 0.0400 | 0.0091 | 100.0% | `13` (0.8738), `5` (0.8738), `9` (0.8646) | current run |
| `projection_margin_fraction` | Low | 0.0133 | 0.0061 | 100.0% | `0.06` (0.8738), `0.1` (0.8707), `0.03` (0.8677) | current run |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) | current run |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8768) | current run |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) | current run |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) | current run |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 100.0% | `9` (0.8768) | current run |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 100.0% | `true` (0.8768) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) | current run |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8707), `0.03` (0.8707), `0.06` (0.8707) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.8707), `0.08` (0.8707), `0.18` (0.8707) | current run |
| `minimum_projection_score` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8707), `0.05` (0.8707), `0.15` (0.8707) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.8707), `0.45` (0.8707), `0.7` (0.8707) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_projection_score`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `projection_threshold_block_fraction` × `projection_weight` | 0.4400 | 0.2800 | 6562 |
| `projection_threshold_block_fraction` × `projection_threshold_c` | 0.2800 | 0.1200 | 6562 |
| `projection_weight` × `projection_threshold_c` | 0.1600 | 0.0666 | 6562 |
| `projection_threshold_c` × `projection_margin_fraction` | 0.0800 | 0.0400 | 6562 |
| `projection_threshold_block_fraction` × `projection_margin_fraction` | 0.2000 | 0.0400 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8542 | 0.8542 | 0.8542 | 0.0000 | 100.0% |
| 5 | 0.8313 | 0.4508 | 0.8618 | 0.1076 | 100.0% |
| 6 | 0.7589 | 0.7589 | 0.7589 | 0.0000 | 100.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-quadrilateral-contourquad-2"></a>
<details>
<summary><strong>Contour Quadrilateral (`contour_quad`)</strong></summary>

**Status:** complete

## Run Information — contour_quad

### Build Provenance

- Run ID: `run-20260811-061212`
- Detector: `contour_quad`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:29:16.698306+00:00`
- Finished: `2026-08-11T06:09:50.446698+00:00`
- Wall-clock elapsed: `10h 40m 34s`
- Est. serial runtime: `6d 9h 8m 7s`
- Effective acceleration: `14.34×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1062882`
- Parameter sets evaluated: `1062882`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour_quad

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | 0.8874 | 0 | 399 ms |
| Baseline | `HTH-0001` | `unknown` | `unknown` | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 206 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `49095b866d0d` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `angle_weight` | `0.2` |
| `area_weight` | `0.25` |
| `close_iterations` | `0` |
| `close_kernel_fraction` | `0.018` |
| `edge_support_dilation_fraction` | `0.008` |
| `edge_support_weight` | `0.15` |
| `epsilon_max_fraction` | `0.04` |
| `epsilon_min_fraction` | `0.004` |
| `epsilon_steps` | `5` |
| `merge_fragmented_contours` | `true` |
| `minimum_contour_area_fraction` | `0.12` |
| `minimum_rectangularity` | `0.55` |
| `rectangularity_weight` | `0.3` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour quadrilaterals | Primary | Generates multiple polygonal page hypotheses. |
| Area | Scoring | Rewards candidates occupying a plausible image fraction. |
| Rectangularity | Scoring | Rewards quadrilateral-like contour geometry. |
| Corner angles | Scoring | Rewards near-right-angle page geometry. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 4 | 4 | 16 | `rh8-al320` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | -0.0105 | 0.8768 | 0 | reference | reference |
| 1 | unknown | `unknown` | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 57.3s | 0.16% |
| 2 | unknown | `unknown` | `fe0372f03bb1` | `fe0372f03bb1` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 58.5s | 0.16% |
| 3 | unknown | `unknown` | `b75e8d4f5261` | `b75e8d4f5261` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 58.7s | 0.16% |
| 4 | unknown | `unknown` | `1d74604d7956` | `1d74604d7956` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 59.2s | 0.16% |
| 5 | unknown | `unknown` | `c542268fe001` | `c542268fe001` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 59.4s | 0.16% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour_quad

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `49095b866d0d` | 0.8542 | 0.9069 | +0.0527 | Improved |
| 5 | `unknown` | `49095b866d0d` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `unknown` | `49095b866d0d` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `unknown` | `49095b866d0d` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `unknown` | `49095b866d0d` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `unknown` | `fe6f0b79695c` | 320 ms | 0.00% |

Total winner changes: **1**.
Search completed in **10h 40m 34s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — contour_quad

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260811-061212`
- Calibration schema: `1.1`
- Detector: `contour_quad`
- Detector configuration: `hth-pipeline/config/detectors/contour_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `1e1f3f5cd036172b1c29eb4a9a5295612bf46618`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `4`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `49095b866d0d`
- Recommended parameter short name: `49095b866d0d`
- Best observed Avg IoU: `0.8874`
- Avg IoU Success: `0.8874`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0731`
- Calibration evidence: `Medium`
- Dormant parameters: `close_kernel_fraction, close_iterations, edge_support_weight, edge_support_dilation_fraction, area_weight, angle_weight, epsilon_min_fraction, epsilon_steps, minimum_contour_area_fraction, minimum_rectangularity, rectangularity_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 11 of 13 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 708588 of 1062882 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 1062882 |
| Parameter sets evaluated | 1062882 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 354294 (33.3%) |
| Best Avg IoU | 0.8874 |
| Minimum Avg IoU | 0.5629 |
| Avg IoU StdDev | 0.1192 |
| Winner stabilized after | 1708 parameter sets |
| Winner stabilized | 57.3s (0% of search) |
| Near-best coverage (basin; within 0.0010) | 164754 (15.5%) |
| Equivalent-best configurations (within 0.0001) | 55890 (5.3%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1062882 | 100.0% | 4d 21h 52m 55s | 1.0× |
| Non-dormant | 6 | 0.0% | 2.4s | 177147.0× |
| Low+ | 6 | 0.0% | 2.4s | 177147.0× |
| Moderate+ | 6 | 0.0% | 2.4s | 177147.0× |
| Important+ | 6 | 0.0% | 2.4s | 177147.0× |
| Critical | 6 | 0.0% | 2.4s | 177147.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `merge_fragmented_contours` | Critical | 0.7000 | 0.1995 | 50.0% | `true` (0.8241), `false` (0.6246) | current run |
| `epsilon_max_fraction` | Critical | 0.2737 | 0.1323 | 66.7% | `0.04` (0.7685), `0.06` (0.7685), `0.025` (0.6362) | current run |
| `close_kernel_fraction` | Dormant | 0.0001 | 0.0027 | 100.0% | `0.018` (0.7260), `0.008` (0.7237), `0` (0.7233) | current run |
| `close_iterations` | Dormant | 0.0001 | 0.0025 | 100.0% | `2` (0.7259), `1` (0.7238), `0` (0.7233) | current run |
| `edge_support_weight` | Dormant | 0.0001 | 0.0024 | 100.0% | `0.25` (0.7256), `0.15` (0.7242), `0.1` (0.7233) | current run |
| `edge_support_dilation_fraction` | Dormant | 0.0001 | 0.0022 | 100.0% | `0.008` (0.7256), `0.004` (0.7240), `0.002` (0.7234) | current run |
| `area_weight` | Dormant | 0.0001 | 0.0021 | 100.0% | `0.25` (0.7255), `0.35` (0.7242), `0.45` (0.7234) | current run |
| `angle_weight` | Dormant | 0.0000 | 0.0012 | 100.0% | `0.3` (0.7249), `0.2` (0.7244), `0.1` (0.7237) | current run |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.004` (0.7244), `0.008` (0.7244), `0.012` (0.7244) | current run |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 100.0% | `13` (0.7244), `5` (0.7244), `9` (0.7244) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.06` (0.7244), `0.12` (0.7244), `0.2` (0.7244) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.7244), `0.55` (0.7244), `0.7` (0.7244) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.7244), `0.3` (0.7244), `0.4` (0.7244) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_kernel_fraction`, `close_iterations`, `edge_support_weight`, `edge_support_dilation_fraction`, `area_weight`, `angle_weight`, `epsilon_min_fraction`, `epsilon_steps`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `rectangularity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `merge_fragmented_contours` × `epsilon_max_fraction` | 0.9988 | 0.2987 | 48313 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8921 | 0.8383 | 0.9069 | 0.0233 | 100.0% |
| 5 | 0.4410 | 0.0000 | 0.8618 | 0.3522 | 66.7% |
| 6 | 0.3795 | 0.0000 | 0.7589 | 0.3795 | 50.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="convex-hull-detector-convexhull-2"></a>
<details>
<summary><strong>Convex Hull Detector (`convex_hull`)</strong></summary>

**Status:** complete

## Run Information — convex_hull

### Build Provenance

- Run ID: `run-20260812-142040`
- Detector: `convex_hull`
- Strategy: `exhaustive`
- Pipeline commit: `10db0a4103e3`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T14:20:37.648868+00:00`
- Finished: `2026-08-12T14:20:39.680538+00:00`
- Wall-clock elapsed: `2s`
- Est. serial runtime: `7m 54s`
- Effective acceleration: `233.16×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `2187`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — convex_hull

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `35e2e87f251b` | `unknown` | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | 0.9156 | 1 | 176 ms |
| Baseline | `HTH-0001` | `35e2e87f251b` | `unknown` | `74f5cad7945a` | `baseline` | 0.6633 | 0.0000 | 0.3670 | 0.8291 | 1 | 12 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`10db0a4103e3`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `04fd0a6e4bc2` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.0` |
| `close_iterations` | `0` |
| `close_kernel_fraction` | `0.0` |
| `minimum_fragment_area_fraction` | `0.0002` |
| `minimum_hull_area_fraction` | `0.1` |
| `minimum_solidity` | `0.35` |
| `polygon_epsilon_fraction` | `0.012` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Foreground fragments | Primary | Collects substantial foreground regions from the document mask. |
| Convex hull | Geometry | Wraps fragmented foreground evidence in the smallest convex envelope. |
| Solidity | Validation | Rejects hulls whose enclosed area is poorly supported by foreground evidence. |
| Quadrilateral fit | Geometry | Returns a polygonal or minimum-area rectangular page envelope. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile` | 8 | 48 | 384 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `74f5cad7945a` | `baseline` | 0.6633 | 0.0000 | 0.3670 | -0.0692 | 0.8291 | 1 | reference | reference |
| 1 | unknown | `unknown` | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 280 ms | 7.69% |
| 2 | unknown | `unknown` | `7fe4e99339c2` | `7fe4e99339c2` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 320 ms | 10.93% |
| 3 | unknown | `unknown` | `58b1b96bcfa4` | `58b1b96bcfa4` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 340 ms | 12.26% |
| 4 | unknown | `unknown` | `f9049ebaa534` | `f9049ebaa534` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 327 ms | 11.21% |
| 5 | unknown | `unknown` | `ae8e0d8d384d` | `ae8e0d8d384d` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 337 ms | 11.85% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — convex_hull

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `04fd0a6e4bc2` | 0.8668 | 0.8668 | +0.0000 | Unchanged |
| 5 | `unknown` | `04fd0a6e4bc2` | 0.5316 | 0.8776 | +0.3460 | Improved |
| 6 | `unknown` | `04fd0a6e4bc2` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `unknown` | `04fd0a6e4bc2` | 0.9585 | 0.9585 | +0.0000 | Unchanged |
| 10 | `unknown` | `04fd0a6e4bc2` | 0.9593 | 0.9593 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `unknown` | `c9b4a5f645ab` | 151 ms | 0.05% |

Total winner changes: **1**.
Search completed in **2s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `1`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `unknown` | `04fd0a6e4bc2` | 0.0000 | No polygon found |

## Calibration Intelligence — convex_hull

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-142040`
- Calibration schema: `1.1`
- Detector: `convex_hull`
- Detector configuration: `hth-pipeline/config/detectors/convex_hull.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `10db0a4103e36908be1adfbd4a4a1daa74c6240d`
- Source commit: `f92b0a144edd9ba0ca546457661374653964c681`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `48`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `04fd0a6e4bc2`
- Recommended parameter short name: `04fd0a6e4bc2`
- Best observed Avg IoU: `0.7325`
- Avg IoU Success: `0.9156`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3683`
- Calibration evidence: `Medium`
- Dormant parameters: `close_iterations, close_kernel_fraction, minimum_hull_area_fraction, polygon_epsilon_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 4 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 2187 of 2187 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 2187 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7325 |
| Minimum Avg IoU | 0.5320 |
| Avg IoU StdDev | 0.0499 |
| Winner stabilized after | 168 parameter sets |
| Winner stabilized | 280 ms (8% of search) |
| Near-best coverage (basin; within 0.0010) | 144 (6.6%) |
| Equivalent-best configurations (within 0.0001) | 144 (6.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 6m 24s | 1.0× |
| Non-dormant | 27 | 1.2% | 4.7s | 81.0× |
| Low+ | 27 | 1.2% | 4.7s | 81.0× |
| Moderate+ | 9 | 0.4% | 1.6s | 243.0× |
| Important+ | 3 | 0.1% | 527 ms | 729.0× |
| Critical | 3 | 0.1% | 527 ms | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_solidity` | Critical | 0.3159 | 0.0595 | 66.7% | `0.35` (0.6854), `0.55` (0.6854), `0.75` (0.6260) | current run |
| `minimum_fragment_area_fraction` | Moderate | 0.0301 | 0.0211 | 33.3% | `0.0015` (0.6769), `0.0002` (0.6641), `0.0005` (0.6558) | current run |
| `bbox_padding_fraction` | Low | 0.0213 | 0.0174 | 33.3% | `0` (0.6732), `0.008` (0.6679), `0.016` (0.6558) | current run |
| `close_iterations` | Dormant | 0.0000 | 0.0003 | 100.0% | `0` (0.6657), `1` (0.6657), `2` (0.6654) | current run |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0003 | 100.0% | `0` (0.6657), `0.008` (0.6657), `0.016` (0.6654) | current run |
| `minimum_hull_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.6656), `0.16` (0.6656), `0.24` (0.6656) | current run |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.012` (0.6656), `0.025` (0.6656), `0.05` (0.6656) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_iterations`, `close_kernel_fraction`, `minimum_hull_area_fraction`, `polygon_epsilon_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_solidity` × `minimum_fragment_area_fraction` | 0.9779 | 0.6620 | 2187 |
| `minimum_fragment_area_fraction` × `bbox_padding_fraction` | 0.0520 | 0.0219 | 2187 |
| `minimum_solidity` × `bbox_padding_fraction` | 0.3373 | 0.0213 | 2187 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8924 | 0.8461 | 0.9734 | 0.0504 | 100.0% |
| 5 | 0.5672 | 0.0000 | 0.9030 | 0.2441 | 88.9% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9281 | 0.8982 | 0.9585 | 0.0246 | 100.0% |
| 10 | 0.9403 | 0.9157 | 0.9593 | 0.0178 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="cross-edge-contour-crossedgecontour-2"></a>
<details>
<summary><strong>Cross-Edge Contour (`cross_edge_contour`)</strong></summary>

**Status:** complete

## Run Information — cross_edge_contour

### Build Provenance

- Run ID: `run-20260810-193535`
- Detector: `cross_edge_contour`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:32:06.089087+00:00`
- Finished: `2026-08-10T19:35:34.583833+00:00`
- Wall-clock elapsed: `3m 28s`
- Est. serial runtime: `55m 4s`
- Effective acceleration: `15.85×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `6562`
- Parameter sets evaluated: `6562`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — cross_edge_contour

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 214 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `a5450e58ec9e` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `contour_weight` | `0.45` |
| `contrast_weight` | `0.4` |
| `epsilon_max_fraction` | `0.04` |
| `minimum_contour_area_fraction` | `0.12` |
| `minimum_cross_edge_contrast` | `0.045` |
| `minimum_polarity_consistency` | `0.55` |
| `minimum_rectangularity` | `0.55` |
| `polarity_weight` | `0.15` |
| `sample_offset_fraction` | `0.008` |
| `samples_per_edge` | `48` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Contour Quad + Cross-Edge Validation)

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour quadrilateral | Generator | Produces candidate page geometry. |
| Inside/outside intensity samples | Validator | Measures the image transition across each proposed boundary. |
| Cross-edge contrast | Validation | Rejects geometrically plausible boundaries lacking a real photometric transition. |
| Polarity consistency | Validation | Checks that inside-versus-outside transition direction is coherent around the page. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 2 |
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 2 | 8 | 16 | `rh8-al321` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | reference | reference |
| 1 | unknown | `unknown` | `0bd97323ddd6` | `0bd97323ddd6` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 679 ms | 0.08% |
| 2 | unknown | `unknown` | `491385b9c30f` | `491385b9c30f` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 722 ms | 0.14% |
| 3 | unknown | `unknown` | `3f36d70252ce` | `3f36d70252ce` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 661 ms | 0.05% |
| 4 | unknown | `unknown` | `ebfb7feac827` | `ebfb7feac827` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.2s | 0.40% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — cross_edge_contour

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `unknown` | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `unknown` | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `unknown` | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `unknown` | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `9739acebc0a5` | 641 ms | 0.02% |
| 2 (final) | `unknown` | `0474de95ff10` | 659 ms | 0.03% |

Total winner changes: **2**.
Search completed in **3m 28s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — cross_edge_contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-193535`
- Calibration schema: `1.1`
- Detector: `cross_edge_contour`
- Detector configuration: `hth-pipeline/config/detectors/cross_edge_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `b0fd9da59edbe250f2d0634b3290535616ce15b8`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `8`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `a5450e58ec9e`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Medium`
- Dormant parameters: `contour_weight, polarity_weight, contrast_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity, samples_per_edge`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 7 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 4617 of 6562 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 1945 (29.6%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.3818 |
| Avg IoU StdDev | 0.2038 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1945 (29.6%) |
| Equivalent-best configurations (within 0.0001) | 1945 (29.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 23m 21s | 1.0× |
| Non-dormant | 36 | 0.5% | 7.7s | 182.3× |
| Low+ | 36 | 0.5% | 7.7s | 182.3× |
| Moderate+ | 4 | 0.1% | 854 ms | 1640.5× |
| Important+ | 4 | 0.1% | 854 ms | 1640.5× |
| Critical | 4 | 0.1% | 854 ms | 1640.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_polarity_consistency` | Critical | 0.9288 | 0.4950 | 50.0% | `0.55` (0.8768), `0.5` (0.8600), `0.65` (0.6676) | current run |
| `sample_offset_fraction` | Low | 0.0296 | 0.0744 | 100.0% | `0.008` (0.6613), `0.014` (0.6612), `0.004` (0.5869) | current run |
| `minimum_cross_edge_contrast` | Low | 0.0015 | 0.0170 | 100.0% | `0.045` (0.6422), `0.02` (0.6421), `0.08` (0.6252) | current run |
| `contour_weight` | Dormant | 0.0002 | 0.0000 | 100.0% | `0.45` (0.8768) | current run |
| `polarity_weight` | Dormant | 0.0002 | 0.0000 | 100.0% | `0.15` (0.8768) | current run |
| `contrast_weight` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.4` (0.6366), `0.3` (0.6365), `0.5` (0.6365) | current run |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.04` (0.6366), `0.03` (0.6365), `0.06` (0.6365) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.12` (0.6366), `0.08` (0.6365), `0.18` (0.6365) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.55` (0.6366), `0.45` (0.6365), `0.7` (0.6365) | current run |
| `samples_per_edge` | Dormant | 0.0000 | 0.0001 | 100.0% | `48` (0.6366), `24` (0.6365), `72` (0.6365) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_weight`, `polarity_weight`, `contrast_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `samples_per_edge`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_polarity_consistency` × `sample_offset_fraction` | 0.9863 | 0.0575 | 6562 |
| `sample_offset_fraction` × `minimum_cross_edge_contrast` | 0.0341 | 0.0046 | 6562 |
| `minimum_polarity_consistency` × `minimum_cross_edge_contrast` | 0.9334 | 0.0046 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.5695 | 0.0000 | 0.8542 | 0.4027 | 66.7% |
| 5 | 0.4788 | 0.0000 | 0.8618 | 0.4282 | 55.6% |
| 6 | 0.2249 | 0.0000 | 0.7589 | 0.3466 | 29.6% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="dhsegment-page-mask-detector-dhsegmentpagemask-2"></a>
<details>
<summary><strong>dhSegment Page-Mask Detector (`dhsegment_page_mask`)</strong></summary>

**Status:** complete

## Run Information — dhsegment_page_mask

### Build Provenance

- Run ID: `run-20260816-222324`
- Detector: `dhsegment_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `15b8530db9c2`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-16T22:09:44.550911+00:00`
- Finished: `2026-08-16T22:23:21.320469+00:00`
- Wall-clock elapsed: `13m 37s`
- Est. serial runtime: `3d 10h 12m 20s`
- Effective acceleration: `362.33×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `10000`
- Parameter sets evaluated: `10000`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — dhsegment_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `9cb0b223675c` | `unknown` | `15434712cddf` | `15434712cddf` | 0.9735 | 0.9634 | 0.0100 | 0.9735 | 0 | 17.2s |
| Baseline | `HTH-0001` | `9cb0b223675c` | `unknown` | `013084b6c0e9` | `baseline` | 0.9670 | 0.9424 | 0.0148 | 0.9670 | 0 | 11.3s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`15b8530db9c2`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `15434712cddf` |
| Absolute parameter SHA-256 | `841ec32f19eff2147663f902e8102b233de1e5623c43b017ac56933750266e6a` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `09e95ccbad8b282cca50d6ba800bdd49440c3d31ad399deba82b8cf85902bacb` |
| Grid ordinal | `3078` |
| Reproducibility | **Fully reproducible** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `close_kernel_fraction` | `0.0025` |
| `contour_offset_fraction` | `0.008` |
| `fill_holes` | `0` |
| `minimum_page_area_fraction` | `0.1` |
| `open_kernel_fraction` | `0.006` |
| `probability_threshold` | `0.35` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| dhSegment page segmentation | Primary | Uses the released dhSegment page-extraction CNN to predict per-pixel page membership. |
| Probability threshold | Generator | Converts the network probability surface into a page mask using either Otsu or a calibrated fixed threshold. |
| Mask cleanup | Robustness | Calibrates morphology, hole filling, and small boundary offsets before geometry fitting. |
| Minimum-area rectangle | Geometry | Fits an oriented page quadrilateral to the dominant learned page region. |
| Model identity | Provenance | Records the upstream release source and downloaded archive SHA-256. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 192 | 2 | 384 | `rh8-al307` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `unknown` | `013084b6c0e9` | `baseline` | 0.9670 | 0.9424 | 0.0148 | -0.0065 | 0.9670 | 0 | reference | reference |
| Best** | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `unknown` | `15434712cddf` | `15434712cddf` | 0.9735 | 0.9634 | 0.0100 | +0.0000 | 0.9735 | 0 | reference | reference |
| 1 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `unknown` | `d111a018eb16` | `d111a018eb16` | 0.9735 | 0.9634 | 0.0100 | +0.0000 | 0.9735 | 0 | 4m 45s | 33.03% |
| 2 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `unknown` | `2ac98c16bd62` | `2ac98c16bd62` | 0.9735 | 0.9634 | 0.0100 | +0.0000 | 0.9735 | 0 | 4m 35s | 31.19% |
| 3 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `unknown` | `9b960d695eea` | `9b960d695eea` | 0.9735 | 0.9634 | 0.0100 | +0.0000 | 0.9735 | 0 | 4m 45s | 32.92% |
| 4 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `unknown` | `d64258f10461` | `d64258f10461` | 0.9735 | 0.9634 | 0.0100 | +0.0000 | 0.9735 | 0 | 5m 12s | 36.30% |
| 5 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `unknown` | `7486e3797400` | `7486e3797400` | 0.9735 | 0.9634 | 0.0100 | +0.0000 | 0.9735 | 0 | 5m 17s | 37.20% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — dhsegment_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `15434712cddf` | 0.9694 | 0.9757 | +0.0064 | Improved |
| 5 | `unknown` | `15434712cddf` | 0.9424 | 0.9634 | +0.0210 | Improved |
| 6 | `unknown` | `15434712cddf` | 0.9891 | 0.9919 | +0.0029 | Improved |
| 9 | `unknown` | `15434712cddf` | 0.9665 | 0.9671 | +0.0006 | Unchanged |
| 10 | `unknown` | `15434712cddf` | 0.9676 | 0.9695 | +0.0019 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `unknown` | `15434712cddf` | 28.4s | 0.01% |

Total winner changes: **1**.
Search completed in **13m 37s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — dhsegment_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260816-222324`
- Calibration schema: `1.1`
- Detector: `dhsegment_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/dhsegment_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `15b8530db9c26a6967776f4ef9797f35718d5422`
- Source commit: `62bb83b3054ae869862c683d6174fcf6d772536a`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `15434712cddf`
- Recommended parameter short name: `15434712cddf`
- Best observed Avg IoU: `0.9735`
- Avg IoU Success: `0.9735`
- Worst Golden Set page (Min IoU): `0.9634`
- Page-to-page StdDev: `0.0100`
- Calibration evidence: `High`
- Dormant parameters: `open_kernel_fraction, fill_holes, minimum_page_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 3 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 10000 |
| Parameter sets evaluated | 10000 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 10000 (100.0%) |
| Best Avg IoU | 0.9735 |
| Minimum Avg IoU | 0.9581 |
| Avg IoU StdDev | 0.0034 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 28.4s (0% of search) |
| Near-best coverage (basin; within 0.0010) | 770 (7.7%) |
| Equivalent-best configurations (within 0.0001) | 130 (1.3%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 10000 | 100.0% | 1d 23h 44m 42s | 1.0× |
| Non-dormant | 200 | 2.0% | 57m 18s | 50.0× |
| Low+ | 200 | 2.0% | 57m 18s | 50.0× |
| Moderate+ | 40 | 0.4% | 11m 28s | 250.0× |
| Important+ | 40 | 0.4% | 11m 28s | 250.0× |
| Critical | 4 | 0.0% | 1m 9s | 2500.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `contour_offset_fraction` | Critical | 0.6663 | 0.0075 | 25.0% | `0.008` (0.9707), `0.004` (0.9683), `0` (0.9659) | current run |
| `probability_threshold` | Important | 0.2246 | 0.0052 | 50.0% | `0.35` (0.9689), `0.4` (0.9684), `-1` (0.9683) | current run |
| `close_kernel_fraction` | Low | 0.0022 | 0.0004 | 100.0% | `0` (0.9673), `0.0025` (0.9672), `0.005` (0.9670) | current run |
| `open_kernel_fraction` | Dormant | 0.0003 | 0.0002 | 100.0% | `0.0045` (0.9671), `0.006` (0.9671), `0.0015` (0.9670) | current run |
| `fill_holes` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.9670), `0` (0.9670) | current run |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.9670), `0.15` (0.9670), `0.2` (0.9670) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`open_kernel_fraction`, `fill_holes`, `minimum_page_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `contour_offset_fraction` × `probability_threshold` | 0.9660 | 0.2997 | 10000 |
| `probability_threshold` × `close_kernel_fraction` | 0.2462 | 0.0216 | 10000 |
| `probability_threshold` × `open_kernel_fraction` | 0.2285 | 0.0039 | 10000 |
| `contour_offset_fraction` × `close_kernel_fraction` | 0.6686 | 0.0023 | 10000 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9696 | 0.9534 | 0.9795 | 0.0053 | 100.0% |
| 5 | 0.9449 | 0.9192 | 0.9793 | 0.0124 | 100.0% |
| 6 | 0.9898 | 0.9811 | 0.9951 | 0.0036 | 100.0% |
| 9 | 0.9643 | 0.9532 | 0.9719 | 0.0052 | 100.0% |
| 10 | 0.9667 | 0.9600 | 0.9726 | 0.0022 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="distance-transform-detector-distancetransform-2"></a>
<details>
<summary><strong>Distance Transform Detector (`distance_transform`)</strong></summary>

**Status:** complete

## Run Information — distance_transform

### Build Provenance

- Run ID: `run-20260812-142114`
- Detector: `distance_transform`
- Strategy: `exhaustive`
- Pipeline commit: `10db0a4103e3`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T14:21:14.932142+00:00`
- Finished: `2026-08-12T14:21:43.514313+00:00`
- Wall-clock elapsed: `28.6s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `2187`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — distance_transform

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `0779968e9f1d` | `unknown` | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | 0.8388 | 0 | 2.5s |
| Baseline | `HTH-0001` | `0779968e9f1d` | `unknown` | `8b59bc493e1f` | `baseline` | 0.7593 | 0.4357 | 0.2472 | 0.7593 | 0 | 283 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`10db0a4103e3`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `e66a7546e1a7` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.008` |
| `close_kernel_fraction` | `0.0` |
| `distance_threshold_fraction` | `0.1` |
| `minimum_bbox_area_fraction` | `0.1` |
| `minimum_component_core_overlap` | `0.03` |
| `minimum_core_area_fraction` | `0.004` |
| `minimum_rectangularity` | `0.35` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Distance transform | Primary | Measures interior distance from foreground pixels to the nearest background boundary. |
| Interior core | Generator | Selects robust page-interior support away from noisy edges. |
| Core-supported components | Filtering | Retains connected foreground regions supported by the interior core. |
| Supported hull | Geometry | Fits a page quadrilateral around the selected foreground support. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 2 |
| Minimum IoU improvements | 3 |
| StdDev improvements | 4 |
| Total metric improvements | 9 |
| Parameter sets with improvements | 4 |
| Winner changes | 2 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile` | 1 | 384 | 384 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `8b59bc493e1f` | `baseline` | 0.7593 | 0.4357 | 0.2472 | -0.0795 | 0.7593 | 0 | reference | reference |
| 1 | unknown | `unknown` | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 2.15% |
| 2 | unknown | `unknown` | `8e57ff70b94c` | `8e57ff70b94c` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 4.39% |
| 3 | unknown | `unknown` | `d0c1acdb2940` | `d0c1acdb2940` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 2.70% |
| 4 | unknown | `unknown` | `9e2cea4f0e56` | `9e2cea4f0e56` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 4.85% |
| 5 | unknown | `unknown` | `ae46f8953bd6` | `ae46f8953bd6` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 3.71% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — distance_transform

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `e66a7546e1a7` | 0.9648 | 0.9734 | +0.0086 | Improved |
| 5 | `unknown` | `e66a7546e1a7` | 0.4784 | 0.5001 | +0.0217 | Improved |
| 6 | `unknown` | `e66a7546e1a7` | 0.4357 | 0.8475 | +0.4118 | Improved |
| 9 | `unknown` | `e66a7546e1a7` | 0.9585 | 0.9276 | -0.0309 | Regressed |
| 10 | `unknown` | `e66a7546e1a7` | 0.9593 | 0.9454 | -0.0139 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `823d0ace1a0f` | 3.1s | 0.09% |
| 2 (final) | `unknown` | `677a2d78be31` | 4.4s | 0.46% |

Total winner changes: **2**.
Search completed in **28.6s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 9 | `unknown` | `e66a7546e1a7` | 0.9276 | Regressed |
| 10 | `unknown` | `e66a7546e1a7` | 0.9454 | Regressed |

## Calibration Intelligence — distance_transform

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-142114`
- Calibration schema: `1.1`
- Detector: `distance_transform`
- Detector configuration: `hth-pipeline/config/detectors/distance_transform.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `10db0a4103e36908be1adfbd4a4a1daa74c6240d`
- Source commit: `0e581bc5ffa0778301a981eecdbaa483e4d5172f`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `384`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `e66a7546e1a7`
- Recommended parameter short name: `e66a7546e1a7`
- Best observed Avg IoU: `0.8388`
- Avg IoU Success: `0.8388`
- Worst Golden Set page (Min IoU): `0.5001`
- Page-to-page StdDev: `0.1745`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 2187 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 1119 (51.2%) |
| Best Avg IoU | 0.8388 |
| Minimum Avg IoU | 0.6568 |
| Avg IoU StdDev | 0.0728 |
| Winner stabilized after | 47 parameter sets |
| Winner stabilized | 5.1s (2% of search) |
| Near-best coverage (basin; within 0.0010) | 144 (6.6%) |
| Equivalent-best configurations (within 0.0001) | 144 (6.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 1h 29m 58s | 1.0× |
| Non-dormant | 729 | 33.3% | 29m 59s | 3.0× |
| Low+ | 729 | 33.3% | 29m 59s | 3.0× |
| Moderate+ | 81 | 3.7% | 3m 20s | 27.0× |
| Important+ | 9 | 0.4% | 22.2s | 243.0× |
| Critical | 3 | 0.1% | 7.4s | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `distance_threshold_fraction` | Critical | 0.5293 | 0.1276 | 33.3% | `0.1` (0.8039), `0.18` (0.7195), `0.3` (0.6763) | current run |
| `minimum_core_area_fraction` | Important | 0.1010 | 0.0534 | 100.0% | `0.004` (0.7545), `0.01` (0.7442), `0.025` (0.7011) | current run |
| `minimum_rectangularity` | Moderate | 0.0335 | 0.0283 | 100.0% | `0.35` (0.7427), `0.5` (0.7427), `0.7` (0.7144) | current run |
| `minimum_component_core_overlap` | Moderate | 0.0319 | 0.0289 | 66.7% | `0.03` (0.7438), `0.08` (0.7410), `0.16` (0.7149) | current run |
| `close_kernel_fraction` | Low | 0.0160 | 0.0215 | 100.0% | `0.016` (0.7421), `0.008` (0.7371), `0` (0.7205) | current run |
| `bbox_padding_fraction` | Low | 0.0042 | 0.0102 | 33.3% | `0` (0.7367), `0.008` (0.7364), `0.016` (0.7266) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0004 | 100.0% | `0.1` (0.7335), `0.16` (0.7331), `0.24` (0.7331) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `distance_threshold_fraction` × `minimum_core_area_fraction` | 0.6662 | 0.1368 | 2187 |
| `distance_threshold_fraction` × `close_kernel_fraction` | 0.5805 | 0.0512 | 2187 |
| `minimum_core_area_fraction` × `minimum_rectangularity` | 0.1466 | 0.0456 | 2187 |
| `minimum_rectangularity` × `minimum_component_core_overlap` | 0.0763 | 0.0428 | 2187 |
| `minimum_core_area_fraction` × `minimum_component_core_overlap` | 0.1420 | 0.0411 | 2187 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9626 | 0.9496 | 0.9734 | 0.0098 | 100.0% |
| 5 | 0.4994 | 0.4784 | 0.5197 | 0.0169 | 100.0% |
| 6 | 0.3357 | 0.0000 | 0.8772 | 0.3635 | 51.2% |
| 9 | 0.9281 | 0.8982 | 0.9585 | 0.0246 | 100.0% |
| 10 | 0.9404 | 0.9165 | 0.9593 | 0.0178 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="distance-transform-rectangle-proposal-distancetransformrect-2"></a>
<details>
<summary><strong>Distance-Transform Rectangle Proposal (`distance_transform_rect`)</strong></summary>

**Status:** complete

## Run Information — distance_transform_rect

### Build Provenance

- Run ID: `run-20260812-155322`
- Detector: `distance_transform_rect`
- Strategy: `exhaustive`
- Pipeline commit: `4f49196091a4`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T15:53:21.237383+00:00`
- Finished: `2026-08-12T15:53:22.463952+00:00`
- Wall-clock elapsed: `1.2s`
- Est. serial runtime: `3m 48s`
- Effective acceleration: `185.84×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `729`
- Parameter sets evaluated: `729`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — distance_transform_rect

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `0c0fe423db71` | `unknown` | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | 0.7243 | 0 | 410 ms |
| Baseline | `HTH-0001` | `0c0fe423db71` | `unknown` | `e04459bcb474` | `baseline` | 0.6347 | 0.0000 | 0.3534 | 0.7933 | 1 | 32 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`4f49196091a4`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `0a8482550c35` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.016` |
| `distance_threshold_fraction` | `0.3` |
| `minimum_bbox_area_fraction` | `0.22` |
| `minimum_core_area_fraction` | `0.002` |
| `minimum_mask_coverage` | `0.06` |
| `proposal_expansion_fraction` | `0.12` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Distance transform | Primary | Measures robust interior support away from foreground boundaries. |
| Interior core | Generator | Thresholds the distance field to obtain a stable document core. |
| Rectangle expansion | Proposal | Expands the core envelope into a candidate page rectangle. |
| Mask coverage | Validation | Rejects proposals with insufficient foreground support or implausible area. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 7 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile` | 5 | 76 | 380 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `e04459bcb474` | `baseline` | 0.6347 | 0.0000 | 0.3534 | -0.0896 | 0.7933 | 1 | reference | reference |
| 1 | unknown | `unknown` | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 836 ms | 82.01% |
| 2 | unknown | `unknown` | `43eedb6484a7` | `43eedb6484a7` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 881 ms | 98.21% |
| 3 | unknown | `unknown` | `b42ab476afc9` | `b42ab476afc9` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 844 ms | 84.75% |
| 4 | unknown | `unknown` | `1ce89ec0c98a` | `1ce89ec0c98a` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 810 ms | 74.45% |
| 5 | unknown | `unknown` | `7e13cb642dbe` | `7e13cb642dbe` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 791 ms | 70.47% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — distance_transform_rect

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `0a8482550c35` | 0.8697 | 0.9520 | +0.0823 | Improved |
| 5 | `unknown` | `0a8482550c35` | 0.4937 | 0.4499 | -0.0438 | Regressed |
| 6 | `unknown` | `0a8482550c35` | 0.0000 | 0.4523 | +0.4523 | Recovered |
| 9 | `unknown` | `0a8482550c35` | 0.8916 | 0.8884 | -0.0032 | Regressed |
| 10 | `unknown` | `0a8482550c35` | 0.9183 | 0.8788 | -0.0395 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 3 | `unknown` | `5638d44f7565` | 544 ms | 14.42% |
| 4 | `unknown` | `e74ab4635629` | 685 ms | 30.49% |
| 5 | `unknown` | `42564449a7c9` | 759 ms | 62.77% |
| 6 | `unknown` | `cacd39184a6d` | 778 ms | 67.31% |
| 7 (final) | `unknown` | `7e13cb642dbe` | 791 ms | 70.47% |

Total winner changes: **7**.
Search completed in **1.2s** wall-clock time.

**Stabilization Interpretation:** Late convergence — the final winner emerged after 40–80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `2`
- Regressed pages (Δ IoU < -0.0010): `3`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 5 | `unknown` | `0a8482550c35` | 0.4499 | Poor match; Regressed |
| 6 | `unknown` | `0a8482550c35` | 0.4523 | Poor match |
| 9 | `unknown` | `0a8482550c35` | 0.8884 | Regressed |
| 10 | `unknown` | `0a8482550c35` | 0.8788 | Regressed |

## Calibration Intelligence — distance_transform_rect

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-155322`
- Calibration schema: `1.1`
- Detector: `distance_transform_rect`
- Detector configuration: `hth-pipeline/config/detectors/distance_transform_rect.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `4f49196091a44d5ca7cfe2269ab7c5a207f6336f`
- Source commit: `927d9bb3457cf7af9276ccf5a629fe648cbf7660`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `76`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `0a8482550c35`
- Recommended parameter short name: `0a8482550c35`
- Best observed Avg IoU: `0.7243`
- Avg IoU Success: `0.7243`
- Worst Golden Set page (Min IoU): `0.4499`
- Page-to-page StdDev: `0.2245`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 657 of 729 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 72 (9.9%) |
| Best Avg IoU | 0.7243 |
| Minimum Avg IoU | 0.5022 |
| Avg IoU StdDev | 0.0415 |
| Winner stabilized after | 597 parameter sets |
| Winner stabilized | 836 ms (82% of search) |
| Near-best coverage (basin; within 0.0010) | 6 (0.8%) |
| Equivalent-best configurations (within 0.0001) | 6 (0.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 4m 59s | 1.0× |
| Non-dormant | 243 | 33.3% | 1m 40s | 3.0× |
| Low+ | 243 | 33.3% | 1m 40s | 3.0× |
| Moderate+ | 9 | 1.2% | 3.7s | 81.0× |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `proposal_expansion_fraction` | Moderate | 0.0415 | 0.0184 | 33.3% | `0.06` (0.6160), `0.12` (0.6149), `0.22` (0.5975) | current run |
| `minimum_mask_coverage` | Moderate | 0.0411 | 0.0199 | 33.3% | `0.06` (0.6210), `0.12` (0.6064), `0.22` (0.6011) | current run |
| `minimum_core_area_fraction` | Low | 0.0204 | 0.0126 | 66.7% | `0.002` (0.6137), `0.006` (0.6137), `0.015` (0.6011) | current run |
| `distance_threshold_fraction` | Low | 0.0192 | 0.0140 | 33.3% | `0.18` (0.6168), `0.3` (0.6090), `0.1` (0.6027) | current run |
| `bbox_padding_fraction` | Low | 0.0018 | 0.0042 | 33.3% | `0.016` (0.6114), `0.008` (0.6099), `0` (0.6072) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.6095), `0.14` (0.6095), `0.22` (0.6095) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `proposal_expansion_fraction` × `distance_threshold_fraction` | 0.6474 | 0.6058 | 729 |
| `minimum_mask_coverage` × `distance_threshold_fraction` | 0.1424 | 0.1013 | 729 |
| `minimum_core_area_fraction` × `distance_threshold_fraction` | 0.0804 | 0.0600 | 729 |
| `proposal_expansion_fraction` × `minimum_mask_coverage` | 0.0943 | 0.0527 | 729 |
| `minimum_mask_coverage` × `minimum_core_area_fraction` | 0.0820 | 0.0409 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8507 | 0.7782 | 0.9672 | 0.0699 | 100.0% |
| 5 | 0.5053 | 0.3489 | 0.6490 | 0.0763 | 100.0% |
| 6 | 0.0419 | 0.0000 | 0.5727 | 0.1291 | 9.9% |
| 9 | 0.8127 | 0.6903 | 0.9353 | 0.0795 | 100.0% |
| 10 | 0.8368 | 0.6685 | 0.9433 | 0.0704 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="doc-ufcn-page-mask-detector-docufcnpagemask-2"></a>
<details>
<summary><strong>Doc-UFCN Page-Mask Detector (`doc_ufcn_page_mask`)</strong></summary>

**Status:** complete

## Run Information — doc_ufcn_page_mask

### Build Provenance

- Run ID: `run-20260820-031930`
- Detector: `doc_ufcn_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `1ee8d0935ff6`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:19:25.410393+00:00`
- Finished: `2026-08-20T03:19:29.889853+00:00`
- Wall-clock elapsed: `4.5s`
- Est. serial runtime: `20m 49s`
- Effective acceleration: `278.78×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2000`
- Parameter sets evaluated: `2000`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — doc_ufcn_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `bfd166146734` | `595002645fcc` | `595002645fcc` | `595002645fcc` | 0.9371 | 0.7663 | 0.0856 | 0.9371 | 0 | 151 ms |
| Baseline | `HTH-0001` | `bfd166146734` | `329dcc7161e9` | `329dcc7161e9` | `baseline` | 0.8655 | 0.8209 | 0.0368 | 0.8655 | 0 | 37 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`1ee8d0935ff6`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `595002645fcc` |
| Parameter Set ID (legacy alias) | `595002645fcc` |
| Absolute parameter SHA-256 | `c33f132009cd80271da55c26a096d05dcee4d8794353e5e514c637c35f419b32` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `85fa16f9a9085f2d9f1abcf26ea66ce563a0fe1e6fa70cbb849de75d9be25105` |
| Grid ordinal | `881` |
| Reproducibility | **Fully reproducible** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `minimum_component_area_fraction` | `0.0005` |
| `minimum_confidence` | `0.5` |
| `minimum_page_area_fraction` | `0.2` |
| `page_padding_fraction` | `0.01` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | 2026-08-20 | `595002645fcc` | `595002645fcc` | authoritative |
| [#581](https://github.com/dlstupka/hth/actions/runs/32326851416) | 2026-08-20 | `595002645fcc` | `595002645fcc` | authoritative |
| [#578](https://github.com/dlstupka/hth/actions/runs/32314480081) | 2026-08-19 | `595002645fcc` | `595002645fcc` | authoritative |
| [#574](https://github.com/dlstupka/hth/actions/runs/32308270196) | 2026-08-19 | `595002645fcc` | `595002645fcc` | authoritative |
| [#568](https://github.com/dlstupka/hth/actions/runs/32306309263) | 2026-08-19 | `595002645fcc` | `595002645fcc` | authoritative |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Doc-UFCN page segmentation | Primary | Uses Teklia's generic historical page model to predict learned physical-page polygons. |
| Confidence and component filtering | Generator | Calibrates deterministic rejection of weak or tiny learned page components without retraining the model. |
| Minimum-area page quadrilateral | Geometry | Fits an oriented quadrilateral around the strongest surviving learned page polygon. |
| Page-envelope padding | Geometry | Calibrates conservative expansion of the learned page quadrilateral before source-image clipping. |
| Model identity | Provenance | Records the Doc-UFCN package version plus model and parameter-file SHA-256 identities. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 5 | 76 | 380 | `rh8-al317` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | `329dcc7161e9` | `329dcc7161e9` | `baseline` | 0.8655 | 0.8209 | 0.0368 | -0.0716 | 0.8655 | 0 | reference | reference |
| Best** | [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | `595002645fcc` | `595002645fcc` | `595002645fcc` | 0.9371 | 0.7663 | 0.0856 | +0.0000 | 0.9371 | 0 | reference | reference |
| 1 | [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | `7d392433a7bb` | `7d392433a7bb` | `7d392433a7bb` | 0.9371 | 0.7663 | 0.0856 | +0.0000 | 0.9371 | 0 | 2.7s | 66.18% |
| 2 | [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | `a5b5f0a03acf` | `a5b5f0a03acf` | `a5b5f0a03acf` | 0.9371 | 0.7663 | 0.0856 | +0.0000 | 0.9371 | 0 | 1.1s | 17.41% |
| 3 | [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | `6d7d608afa3a` | `6d7d608afa3a` | `6d7d608afa3a` | 0.9371 | 0.7663 | 0.0856 | +0.0000 | 0.9371 | 0 | 1.1s | 17.66% |
| 4 | [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | `25c211109d95` | `25c211109d95` | `25c211109d95` | 0.9371 | 0.7663 | 0.0856 | +0.0000 | 0.9371 | 0 | 1.1s | 18.01% |
| 5 | [#585](https://github.com/dlstupka/hth/actions/runs/32327760620) | `5120e4b79f78` | `5120e4b79f78` | `5120e4b79f78` | 0.9371 | 0.7663 | 0.0856 | +0.0000 | 0.9371 | 0 | 1s | 17.06% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — doc_ufcn_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `595002645fcc` | `595002645fcc` | 0.8565 | 0.9770 | +0.1205 | Improved |
| 5 | `595002645fcc` | `595002645fcc` | 0.8209 | 0.7663 | -0.0546 | Regressed |
| 6 | `595002645fcc` | `595002645fcc` | 0.9327 | 0.9708 | +0.0381 | Improved |
| 9 | `595002645fcc` | `595002645fcc` | 0.8515 | 0.9900 | +0.1385 | Improved |
| 10 | `595002645fcc` | `595002645fcc` | 0.8657 | 0.9814 | +0.1157 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `595002645fcc` | `595002645fcc` | 246 ms | 0.05% |

Total winner changes: **1**.
Search completed in **4.5s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 5 | `595002645fcc` | `595002645fcc` | 0.7663 | Regressed |

## Calibration Intelligence — doc_ufcn_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-031930`
- Calibration schema: `1.1`
- Detector: `doc_ufcn_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/doc_ufcn_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ee8d0935ff6892e9e6b60c7e5f15417d4073949`
- Source commit: `cba7f32e6885ec7268c77d35ecc12f79cc6c2bc7`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `76`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `595002645fcc`
- Recommended parameter short name: `595002645fcc`
- Best observed Avg IoU: `0.9371`
- Avg IoU Success: `0.9371`
- Worst Golden Set page (Min IoU): `0.7663`
- Page-to-page StdDev: `0.0856`
- Calibration evidence: `High`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2000 |
| Parameter sets evaluated | 2000 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 2000 (100.0%) |
| Best Avg IoU | 0.9371 |
| Minimum Avg IoU | 0.8198 |
| Avg IoU StdDev | 0.0403 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 246 ms (0% of search) |
| Near-best coverage (basin; within 0.0010) | 200 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 200 (10.0%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2000 | 100.0% | 5m 2s | 1.0× |
| Exhaustive | 2000 | 100.0% | 5m 2s | 1.0× |
| Non-dormant | 10 | 0.5% | 1.5s | 200.0× |
| Low+ | 10 | 0.5% | 1.5s | 200.0× |
| Moderate+ | 10 | 0.5% | 1.5s | 200.0× |
| Important+ | 10 | 0.5% | 1.5s | 200.0× |
| Critical | 10 | 0.5% | 1.5s | 200.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `page_padding_fraction` | Critical | 1.0000 | 0.1173 | 10.0% | `0.01` (0.9371), `0` (0.9294), `0.02` (0.9127) | current run |
| `minimum_component_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.8747), `0.0001` (0.8747), `0.0005` (0.8747) | current run |
| `minimum_page_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8747), `0.12` (0.8747), `0.16` (0.8747) | current run |
| `minimum_confidence` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.8747), `0.25` (0.8747), `0.4` (0.8747) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8734 | 0.7782 | 0.9770 | 0.0721 | 100.0% |
| 5 | 0.8038 | 0.7370 | 0.8370 | 0.0325 | 100.0% |
| 6 | 0.9432 | 0.9327 | 0.9899 | 0.0193 | 100.0% |
| 9 | 0.8699 | 0.7569 | 0.9900 | 0.0807 | 100.0% |
| 10 | 0.8832 | 0.7940 | 0.9814 | 0.0653 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="edge-supported-contour-edgecontour-2"></a>
<details>
<summary><strong>Edge-Supported Contour (`edge_contour`)</strong></summary>

**Status:** complete

## Run Information — edge_contour

### Build Provenance

- Run ID: `run-20260810-221217`
- Detector: `edge_contour`
- Strategy: `exhaustive`
- Pipeline commit: `9d1ea15025c1`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T22:11:08.149584+00:00`
- Finished: `2026-08-10T22:12:16.069858+00:00`
- Wall-clock elapsed: `1m 8s`
- Est. serial runtime: `6h 49m 42s`
- Effective acceleration: `361.93×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `13123`
- Parameter sets evaluated: `13123`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — edge_contour

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `2bf3c6b9248e` | `unknown` | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 1s |
| Baseline | `HTH-0001` | `2bf3c6b9248e` | `unknown` | `cc91b22426bb` | `baseline` | 0.5392 | 0.0000 | 0.4417 | 0.8986 | 2 | 392 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`9d1ea15025c1`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `4e5bc37a649a` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `edge_support_dilation_fraction` | `0.003` |
| `edge_support_weight` | `0.2` |
| `epsilon_max_fraction` | `0.03` |
| `lsd_refine_mode` | `"none"` |
| `lsd_scale` | `0.6` |
| `minimum_contour_area_fraction` | `0.08` |
| `minimum_edge_support` | `0.05` |
| `minimum_rectangularity` | `0.45` |
| `minimum_segment_length_fraction` | `0.03` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Contour Quad + LSD)

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour quadrilateral | Generator | Produces candidate page quadrilaterals. |
| LSD line segments | Validator | Independently detects line support near proposed borders. |
| Edge support | Validator | Measures border coverage after configurable dilation. |
| Geometry score | Scoring | Combines area, rectangularity, and angle quality. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 2 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile-legacy-workload` | 20 | 19 | 380 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `cc91b22426bb` | `baseline` | 0.5392 | 0.0000 | 0.4417 | -0.3377 | 0.8986 | 2 | reference | reference |
| 1 | unknown | `unknown` | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.5s | 0.21% |
| 2 | unknown | `unknown` | `723797320a20` | `723797320a20` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.5s | 0.15% |
| 3 | unknown | `unknown` | `45f853e88afb` | `45f853e88afb` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 2s | 1.14% |
| 4 | unknown | `unknown` | `d3cfbe72a64d` | `d3cfbe72a64d` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 7s | 8.53% |
| 5 | unknown | `unknown` | `79f1c310cb10` | `79f1c310cb10` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 8s | 10.11% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — edge_contour

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `4e5bc37a649a` | 0.0000 | 0.8542 | +0.8542 | Recovered |
| 5 | `unknown` | `4e5bc37a649a` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `unknown` | `4e5bc37a649a` | 0.0000 | 0.7589 | +0.7589 | Recovered |
| 9 | `unknown` | `4e5bc37a649a` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `unknown` | `4e5bc37a649a` | 0.8703 | 0.9454 | +0.0751 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `335dc91690c9` | 1.1s | 0.01% |
| 2 (final) | `unknown` | `ff097da4d65f` | 1.3s | 0.02% |

Total winner changes: **2**.
Search completed in **1m 8s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — edge_contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-221217`
- Calibration schema: `1.1`
- Detector: `edge_contour`
- Detector configuration: `hth-pipeline/config/detectors/edge_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `9d1ea15025c12e64648a2b8d479acfc9c7a71ea5`
- Source commit: `fdbb3706e75ce5acb619f397d99a7a262816b7a8`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `19`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `4e5bc37a649a`
- Recommended parameter short name: `4e5bc37a649a`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Medium`
- Dormant parameters: `angle_weight, area_weight, close_iterations, close_kernel_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight, edge_support_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 12 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 11503 of 13123 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 13123 |
| Parameter sets evaluated | 13123 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 1620 (12.3%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.2495 |
| Winner stabilized after | 27 parameter sets |
| Winner stabilized | 1.5s (0% of search) |
| Near-best coverage (basin; within 0.0010) | 1134 (8.6%) |
| Equivalent-best configurations (within 0.0001) | 1134 (8.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13123 | 100.0% | 3h 46m 46s | 1.0× |
| Non-dormant | 162 | 1.2% | 2m 48s | 81.0× |
| Low+ | 162 | 1.2% | 2m 48s | 81.0× |
| Moderate+ | 162 | 1.2% | 2m 48s | 81.0× |
| Important+ | 81 | 0.6% | 1m 24s | 162.0× |
| Critical | 3 | 0.0% | 3.1s | 4374.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_edge_support` | Critical | 0.3207 | 0.3412 | 66.7% | `0.05` (0.6504), `0.12` (0.4293), `0.2` (0.3092) | current run |
| `edge_support_dilation_fraction` | Important | 0.1807 | 0.2557 | 100.0% | `0.01` (0.5775), `0.006` (0.4895), `0.003` (0.3218) | current run |
| `minimum_segment_length_fraction` | Important | 0.1417 | 0.2229 | 33.3% | `0.03` (0.5908), `0.06` (0.4301), `0.1` (0.3679) | current run |
| `lsd_scale` | Important | 0.1119 | 0.1922 | 66.7% | `0.6` (0.5390), `0.8` (0.5031), `1` (0.3468) | current run |
| `lsd_refine_mode` | Moderate | 0.0518 | 0.1136 | 100.0% | `none` (0.5197), `std` (0.4062) | current run |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.5392) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.5392) | current run |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.5392) | current run |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.5392) | current run |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.5392) | current run |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 0.0% | `9` (0.5392) | current run |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 0.0% | `true` (0.5392) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.5392) | current run |
| `edge_support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.3` (0.4630), `0.2` (0.4629), `0.4` (0.4629) | current run |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.4630), `0.03` (0.4629), `0.06` (0.4629) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.4630), `0.08` (0.4629), `0.18` (0.4629) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.4630), `0.45` (0.4629), `0.7` (0.4629) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`, `edge_support_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_edge_support` × `edge_support_dilation_fraction` | 0.5279 | 0.2072 | 13123 |
| `minimum_edge_support` × `minimum_segment_length_fraction` | 0.4739 | 0.1532 | 13123 |
| `edge_support_dilation_fraction` × `minimum_segment_length_fraction` | 0.3245 | 0.1438 | 13123 |
| `edge_support_dilation_fraction` × `lsd_scale` | 0.2965 | 0.1158 | 13123 |
| `minimum_segment_length_fraction` × `lsd_scale` | 0.2562 | 0.1145 | 13123 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.2478 | 0.0000 | 0.8542 | 0.3877 | 29.0% |
| 5 | 0.4735 | 0.0000 | 0.8618 | 0.4288 | 54.9% |
| 6 | 0.0937 | 0.0000 | 0.7589 | 0.2496 | 12.3% |
| 9 | 0.9281 | 0.0000 | 0.9638 | 0.1820 | 96.3% |
| 10 | 0.5717 | 0.0000 | 0.9454 | 0.4278 | 64.2% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-segmentation-grabcut-2"></a>
<details>
<summary><strong>GrabCut Segmentation (`grabcut`)</strong></summary>

**Status:** complete

## Run Information — grabcut

### Build Provenance

- Run ID: `run-20260816-161000`
- Detector: `grabcut`
- Strategy: `exhaustive`
- Pipeline commit: `7067fdc5b522`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-16T15:23:49.376404+00:00`
- Finished: `2026-08-16T16:09:57.615252+00:00`
- Wall-clock elapsed: `46m 8s`
- Est. serial runtime: `11d 20h 30m 32s`
- Effective acceleration: `369.99×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `13122`
- Parameter sets evaluated: `13122`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — grabcut

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `3250a8986204` | `unknown` | `110867d137a9` | `110867d137a9` | 0.9137 | 0.7378 | 0.0886 | 0.9137 | 0 | 1m 42s |
| Baseline | `HTH-0001` | `3250a8986204` | `unknown` | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 27.7s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`7067fdc5b522`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `110867d137a9` |
| Absolute parameter SHA-256 | `0457f33a3ddc4db1b62c2ea856666a8575ec33a160f1a29e3e7fef585df5219a` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `92d52112a9eed7ca91666e56bc46767b4ed8ed7afdc8c26d9b8f77f16f061327` |
| Grid ordinal | `1315` |
| Reproducibility | **Fully reproducible** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `border_fraction` | `0.01` |
| `close_iterations` | `1` |
| `close_kernel_fraction` | `0.01` |
| `erosion_iterations` | `2` |
| `erosion_kernel_fraction` | `0.0075` |
| `grabcut_iterations` | `5` |
| `minimum_bbox_area_fraction` | `0.15` |
| `minimum_contour_area_fraction` | `0.02` |
| `polygon_epsilon_fraction` | `0.018` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| GrabCut foreground mask | Primary | Segments foreground pixels from a border-seeded background model. |
| Morphological cleanup | Supporting | Closes and erodes the segmentation before region extraction. |
| Foreground contour | Geometry | Converts the segmented region into a page polygon or bounding quadrilateral. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 9 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 2 | 192 | 384 | `rh8-al308` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `unknown` | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | -0.1006 | 0.8130 | 0 | reference | reference |
| 1 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `unknown` | `110867d137a9` | `110867d137a9` | 0.9137 | 0.7378 | 0.0886 | +0.0000 | 0.9137 | 0 | 6m 3s | 10.33% |
| 2 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `unknown` | `1262b0b433bf` | `1262b0b433bf` | 0.9084 | 0.7378 | 0.0859 | -0.0052 | 0.9084 | 0 | 6m 12s | 11.01% |
| 3 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `unknown` | `3784a76b67a0` | `3784a76b67a0` | 0.9071 | 0.7249 | 0.0912 | -0.0066 | 0.9071 | 0 | 21m 2s | 41.19% |
| 4 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `unknown` | `7de1564ea01e` | `7de1564ea01e` | 0.9071 | 0.7249 | 0.0912 | -0.0066 | 0.9071 | 0 | 21m 5s | 41.40% |
| 5 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `unknown` | `114948776d31` | `114948776d31` | 0.9071 | 0.7249 | 0.0912 | -0.0066 | 0.9071 | 0 | 21m 7s | 41.48% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — grabcut

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `110867d137a9` | 0.9568 | 0.9578 | +0.0010 | Improved |
| 5 | `unknown` | `110867d137a9` | 0.5532 | 0.9755 | +0.4223 | Improved |
| 6 | `unknown` | `110867d137a9` | 0.6683 | 0.7378 | +0.0695 | Improved |
| 9 | `unknown` | `110867d137a9` | 0.9422 | 0.9433 | +0.0010 | Improved |
| 10 | `unknown` | `110867d137a9` | 0.9447 | 0.9540 | +0.0093 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 5 | `unknown` | `573c302bd551` | 2m 40s | 2.92% |
| 6 | `unknown` | `e08577fea107` | 3m 24s | 4.17% |
| 7 | `unknown` | `1aa5ff7fa09b` | 3m 30s | 4.20% |
| 8 | `unknown` | `06713f658536` | 5m 50s | 10.01% |
| 9 (final) | `unknown` | `110867d137a9` | 6m 3s | 10.33% |

Total winner changes: **9**.
Search completed in **46m 8s** wall-clock time.

**Stabilization Interpretation:** Moderate exploration — the final winner emerged after 10–40% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — grabcut

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260816-161000`
- Calibration schema: `1.1`
- Detector: `grabcut`
- Detector configuration: `hth-pipeline/config/detectors/grabcut.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `7067fdc5b522fbe4bb195f18bccf5f1123d8a87f`
- Source commit: `22e63f5eb5e6514e09228c827fcfc44d13e14e82`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `192`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `110867d137a9`
- Recommended parameter short name: `110867d137a9`
- Best observed Avg IoU: `0.9137`
- Avg IoU Success: `0.9137`
- Worst Golden Set page (Min IoU): `0.7378`
- Page-to-page StdDev: `0.0886`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, polygon_epsilon_fraction, minimum_contour_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 3 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 13122 |
| Parameter sets evaluated | 13122 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 12515 (95.4%) |
| Best Avg IoU | 0.9137 |
| Minimum Avg IoU | 0.4353 |
| Avg IoU StdDev | 0.0712 |
| Winner stabilized after | 1355 parameter sets |
| Winner stabilized | 6m 3s (10% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13122 | 100.0% | 15d 12h 43m 31s | 1.0× |
| Non-dormant | 486 | 3.7% | 13h 48m 17s | 27.0× |
| Low+ | 486 | 3.7% | 13h 48m 17s | 27.0× |
| Moderate+ | 81 | 0.6% | 2h 18m 3s | 162.0× |
| Important+ | 27 | 0.2% | 46m 1s | 486.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `erosion_iterations` | Important | 0.2068 | 0.0763 | 33.3% | `1` (0.7946), `2` (0.7753), `0` (0.7183) | current run |
| `border_fraction` | Important | 0.1542 | 0.0611 | 33.3% | `0.01` (0.8022), `0.03` (0.7449), `0.02` (0.7411) | current run |
| `grabcut_iterations` | Important | 0.1207 | 0.0547 | 33.3% | `5` (0.7825), `3` (0.7778), `1` (0.7279) | current run |
| `erosion_kernel_fraction` | Moderate | 0.0329 | 0.0316 | 33.3% | `0.0075` (0.7789), `0.015` (0.7620), `0.025` (0.7473) | current run |
| `close_kernel_fraction` | Low | 0.0162 | 0.0209 | 33.3% | `0.01` (0.7711), `0.02` (0.7670), `0.035` (0.7501) | current run |
| `close_iterations` | Low | 0.0107 | 0.0147 | 50.0% | `1` (0.7701), `2` (0.7554) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0009 | 33.3% | `0.15` (0.7633), `0.07` (0.7626), `0.1` (0.7624) | current run |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0006 | 33.3% | `0.03` (0.7630), `0.018` (0.7627), `0.01` (0.7624) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0002 | 33.3% | `0.02` (0.7629), `0.04` (0.7627), `0.07` (0.7626) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `polygon_epsilon_fraction`, `minimum_contour_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `erosion_iterations` × `border_fraction` | 0.4096 | 0.2028 | 13122 |
| `erosion_iterations` × `grabcut_iterations` | 0.3374 | 0.1306 | 13122 |
| `border_fraction` × `grabcut_iterations` | 0.2832 | 0.1291 | 13122 |
| `erosion_iterations` × `erosion_kernel_fraction` | 0.3027 | 0.0959 | 13122 |
| `border_fraction` × `erosion_kernel_fraction` | 0.1964 | 0.0422 | 13122 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8946 | 0.0000 | 0.9904 | 0.2046 | 95.9% |
| 5 | 0.5491 | 0.2980 | 0.9755 | 0.1047 | 100.0% |
| 6 | 0.5056 | 0.0000 | 0.8217 | 0.1758 | 99.2% |
| 9 | 0.9307 | 0.8522 | 0.9433 | 0.0288 | 100.0% |
| 10 | 0.9336 | 0.8355 | 0.9661 | 0.0228 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-contour-grabcutcontour-2"></a>
<details>
<summary><strong>GrabCut + Contour (`grabcut_contour`)</strong></summary>

**Status:** complete

## Run Information — grabcut_contour

### Build Provenance

- Run ID: `run-20260818-051255`
- Detector: `grabcut_contour`
- Strategy: `exhaustive`
- Pipeline commit: `3879c560eeb6`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-18T01:49:52.624779+00:00`
- Finished: `2026-08-18T05:12:47.198591+00:00`
- Wall-clock elapsed: `3h 22m 55s`
- Est. serial runtime: `32d 13m 16s`
- Effective acceleration: `227.16×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `46657`
- Parameter sets evaluated: `46657`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — grabcut_contour

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `29f3ef9c9b1a` | `unknown` | `3a1623be3b6e` | `3a1623be3b6e` | 0.8781 | 0.7198 | 0.0900 | 0.8781 | 0 | 1m 14s |
| Baseline | `HTH-0001` | `29f3ef9c9b1a` | `unknown` | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 28.2s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`3879c560eeb6`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `3a1623be3b6e` |
| Absolute parameter SHA-256 | `42cae522722e69f1890161081132a16e7507cb6b18baef2b2192d11c921333d1` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `22f4aa58310d079c7f92395261d8891ef8cd13346470c080af1540870ee9ca46` |
| Grid ordinal | `8759` |
| Reproducibility | **Fully reproducible** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `agreement_weight` | `0.35` |
| `contour_minimum_area_fraction` | `0.08` |
| `contour_minimum_rectangularity` | `0.45` |
| `grabcut_border_fraction` | `0.02` |
| `grabcut_close_kernel_fraction` | `0.03` |
| `grabcut_erosion_kernel_fraction` | `0.015` |
| `grabcut_iterations` | `5` |
| `grabcut_minimum_contour_area_fraction` | `0.04` |
| `grabcut_polygon_epsilon_fraction` | `0.01` |
| `grabcut_weight` | `0.55` |
| `minimum_agreement_iou` | `0.05` |
| `require_contour` | `true` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (GrabCut + Contour Quad)

| Evidence source | Function | Interpretation |
|---|---|---|
| GrabCut foreground segmentation | Generator | Generates the primary page polygon from pixel-level foreground segmentation. |
| Foreground contour geometry | Geometry | Converts the GrabCut mask into the returned page quadrilateral. |
| Contour quadrilateral | Validator | Provides an independent geometric hypothesis for validation. |
| Polygon agreement | Validation | Requires sufficient overlap between GrabCut-derived and contour-derived hypotheses. |
| Fusion score | Scoring | Combines GrabCut quality, contour quality, and hypothesis agreement while retaining GrabCut geometry. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 3 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `manual` | 2 | 192 | 384 | `rh8-al317` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `unknown` | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | -0.0651 | 0.8130 | 0 | reference | reference |
| Best** | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `unknown` | `45a2660cc96b` | `45a2660cc96b` | 0.8164 | 0.5574 | 0.1661 | -0.0617 | 0.8164 | 0 | reference | reference |
| 1 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `unknown` | `3a1623be3b6e` | `3a1623be3b6e` | 0.8781 | 0.7198 | 0.0900 | +0.0000 | 0.8781 | 0 | 2m 18s | 0.63% |
| 2 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `unknown` | `94bd6199c3b4` | `94bd6199c3b4` | 0.8781 | 0.7198 | 0.0900 | +0.0000 | 0.8781 | 0 | 2m 19s | 0.67% |
| 3 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `unknown` | `db82dda712d3` | `db82dda712d3` | 0.8781 | 0.7198 | 0.0900 | +0.0000 | 0.8781 | 0 | 2m 19s | 0.66% |
| 4 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `unknown` | `0a1aa69fb04e` | `0a1aa69fb04e` | 0.8781 | 0.7198 | 0.0900 | +0.0000 | 0.8781 | 0 | 2m 20s | 0.68% |
| 5 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `unknown` | `092fad84e4fa` | `092fad84e4fa` | 0.8781 | 0.7198 | 0.0900 | +0.0000 | 0.8781 | 0 | 2m 19s | 0.66% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — grabcut_contour

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `3a1623be3b6e` | 0.9568 | 0.9489 | -0.0078 | Regressed |
| 5 | `unknown` | `3a1623be3b6e` | 0.5532 | 0.8348 | +0.2816 | Improved |
| 6 | `unknown` | `3a1623be3b6e` | 0.6683 | 0.7198 | +0.0515 | Improved |
| 9 | `unknown` | `3a1623be3b6e` | 0.9422 | 0.9422 | +0.0000 | Unchanged |
| 10 | `unknown` | `3a1623be3b6e` | 0.9447 | 0.9447 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `45a2660cc96b` | 1m 4s | 0.11% |
| 2 | `unknown` | `cb2dc0cb4d7f` | 1m 23s | 0.30% |
| 3 (final) | `unknown` | `ac6e790ba105` | 1m 24s | 0.31% |

Total winner changes: **3**.
Search completed in **3h 22m 55s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `3a1623be3b6e` | 0.9489 | Regressed |

## Calibration Intelligence — grabcut_contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260818-051255`
- Calibration schema: `1.1`
- Detector: `grabcut_contour`
- Detector configuration: `hth-pipeline/config/detectors/grabcut_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `3879c560eeb670529cd9063feae4543aa86e9f45`
- Source commit: `49af4e905d761e10cefda11af62a6ef840a64a15`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `192`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `3a1623be3b6e`
- Recommended parameter short name: `3a1623be3b6e`
- Best observed Avg IoU: `0.8781`
- Avg IoU Success: `0.8781`
- Worst Golden Set page (Min IoU): `0.7198`
- Page-to-page StdDev: `0.0900`
- Calibration evidence: `High`
- Dormant parameters: `contour_epsilon_max_fraction, contour_weight, grabcut_close_iterations, grabcut_erosion_iterations, grabcut_minimum_bbox_area_fraction, grabcut_close_kernel_fraction, agreement_weight, grabcut_weight, contour_minimum_area_fraction, contour_minimum_rectangularity, grabcut_polygon_epsilon_fraction, minimum_agreement_iou, grabcut_minimum_contour_area_fraction, require_contour`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 14 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 46657 |
| Parameter sets evaluated | 46657 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 46657 (100.0%) |
| Best Avg IoU | 0.8781 |
| Minimum Avg IoU | 0.7426 |
| Avg IoU StdDev | 0.0452 |
| Winner stabilized after | 294 parameter sets |
| Winner stabilized | 2m 18s (1% of search) |
| Near-best coverage (basin; within 0.0010) | 2916 (6.2%) |
| Equivalent-best configurations (within 0.0001) | 2916 (6.2%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 46657 | 100.0% | 39d 23h 10m 57s | 1.0× |
| Non-dormant | 8 | 0.0% | 9m 52s | 5832.1× |
| Low+ | 8 | 0.0% | 9m 52s | 5832.1× |
| Moderate+ | 8 | 0.0% | 9m 52s | 5832.1× |
| Important+ | 2 | 0.0% | 2m 28s | 23328.5× |
| Critical | 2 | 0.0% | 2m 28s | 23328.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `grabcut_erosion_kernel_fraction` | Critical | 0.8010 | 0.0808 | 50.0% | `0.015` (0.8286), `0.025` (0.7478) | current run |
| `grabcut_border_fraction` | Moderate | 0.0441 | 0.0190 | 50.0% | `0.02` (0.7977), `0.03` (0.7787) | current run |
| `grabcut_iterations` | Moderate | 0.0393 | 0.0179 | 50.0% | `5` (0.7972), `3` (0.7793) | current run |
| `contour_epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.04` (0.8130) | current run |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.8130) | current run |
| `grabcut_close_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.8130) | current run |
| `grabcut_erosion_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.8130) | current run |
| `grabcut_minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.1` (0.8130) | current run |
| `grabcut_close_kernel_fraction` | Dormant | 0.0000 | 0.0002 | 50.0% | `0.03` (0.7883), `0.02` (0.7881) | current run |
| `agreement_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.7882), `0.15` (0.7882), `0.35` (0.7882) | current run |
| `grabcut_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.7882), `0.45` (0.7882), `0.65` (0.7882) | current run |
| `contour_minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.7882), `0.08` (0.7882), `0.18` (0.7882) | current run |
| `contour_minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.7882), `0.45` (0.7882), `0.7` (0.7882) | current run |
| `grabcut_polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.018` (0.7882), `0.01` (0.7882), `0.03` (0.7882) | current run |
| `minimum_agreement_iou` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.7882), `0.05` (0.7882), `0.3` (0.7882) | current run |
| `grabcut_minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.7882), `0.08` (0.7882) | current run |
| `require_contour` | Dormant | 0.0000 | 0.0000 | 100.0% | `false` (0.7882), `true` (0.7882) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_epsilon_max_fraction`, `contour_weight`, `grabcut_close_iterations`, `grabcut_erosion_iterations`, `grabcut_minimum_bbox_area_fraction`, `grabcut_close_kernel_fraction`, `agreement_weight`, `grabcut_weight`, `contour_minimum_area_fraction`, `contour_minimum_rectangularity`, `grabcut_polygon_epsilon_fraction`, `minimum_agreement_iou`, `grabcut_minimum_contour_area_fraction`, `require_contour`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `grabcut_erosion_kernel_fraction` × `grabcut_iterations` | 0.8810 | 0.0800 | 46657 |
| `grabcut_border_fraction` × `grabcut_iterations` | 0.1176 | 0.0735 | 46657 |
| `grabcut_erosion_kernel_fraction` × `grabcut_border_fraction` | 0.8696 | 0.0686 | 46657 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9517 | 0.9467 | 0.9568 | 0.0041 | 100.0% |
| 5 | 0.5973 | 0.5532 | 0.8348 | 0.0889 | 100.0% |
| 6 | 0.5077 | 0.3232 | 0.7198 | 0.1781 | 100.0% |
| 9 | 0.9425 | 0.9422 | 0.9433 | 0.0005 | 100.0% |
| 10 | 0.9418 | 0.9389 | 0.9447 | 0.0029 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="gradient-boundary-voting-gradientvote-2"></a>
<details>
<summary><strong>Gradient Boundary Voting (`gradient_vote`)</strong></summary>

**Status:** complete

## Run Information — gradient_vote

### Build Provenance

- Run ID: `run-20260815-150143`
- Detector: `gradient_vote`
- Strategy: `exhaustive`
- Pipeline commit: `e20fbfa08988`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-15T15:01:42.407693+00:00`
- Finished: `2026-08-15T15:01:43.216597+00:00`
- Wall-clock elapsed: `809 ms`
- Est. serial runtime: `132 ms`
- Effective acceleration: `0.16×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `22`
- Parameter sets evaluated: `22`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — gradient_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `6f3152478904` | `unknown` | `cf581d27715b` | `cf581d27715b` | 0.9622 | 0.9384 | 0.0160 | 0.9622 | 0 | 10 ms |
| Baseline | `HTH-0001` | `6f3152478904` | `unknown` | `1029318d5974` | `baseline` | 0.9467 | 0.8611 | 0.0442 | 0.9467 | 0 | 10 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`e20fbfa08988`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `cf581d27715b` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `border_search_fraction` | `0.14` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Sobel gradient field | Primary | Measures distributed horizontal and vertical intensity transitions. |
| Boundary vote profiles | Generator | Accumulates local gradients into opposing page-boundary votes. |
| Peak prominence | Validation | Requires selected boundaries to stand out from competing transitions. |
| Boundary span | Geometry | Forms a page quadrilateral from the winning left, right, top, and bottom votes. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 9 | 42 | 378 | `rh8-al307` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `1029318d5974` | `baseline` | 0.9467 | 0.8611 | 0.0442 | -0.0155 | 0.9467 | 0 | reference | reference |
| 1 | unknown | `unknown` | `cf581d27715b` | `cf581d27715b` | 0.9622 | 0.9384 | 0.0160 | +0.0000 | 0.9622 | 0 | 118 ms | 66.67% |
| 2 | unknown | `unknown` | `a445f6a76753` | `a445f6a76753` | 0.9622 | 0.9384 | 0.0160 | +0.0000 | 0.9622 | 0 | 43 ms | 28.57% |
| 3 | unknown | `unknown` | `a69dfc686c7c` | `a69dfc686c7c` | 0.9622 | 0.9384 | 0.0160 | +0.0000 | 0.9622 | 0 | 144 ms | 100.00% |
| 4 | unknown | `unknown` | `ea16ebcdc2f7` | `ea16ebcdc2f7` | 0.9620 | 0.9384 | 0.0161 | -0.0002 | 0.9620 | 0 | 99 ms | 52.38% |
| 5 | unknown | `unknown` | `a8558e4ecf4c` | `a8558e4ecf4c` | 0.9469 | 0.8618 | 0.0439 | -0.0153 | 0.9469 | 0 | 87 ms | 42.86% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — gradient_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `cf581d27715b` | 0.9613 | 0.9613 | +0.0000 | Unchanged |
| 5 | `unknown` | `cf581d27715b` | 0.8611 | 0.9384 | +0.0773 | Improved |
| 6 | `unknown` | `cf581d27715b` | 0.9889 | 0.9889 | +0.0000 | Unchanged |
| 9 | `unknown` | `cf581d27715b` | 0.9612 | 0.9612 | +0.0000 | Unchanged |
| 10 | `unknown` | `cf581d27715b` | 0.9611 | 0.9611 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `unknown` | `a445f6a76753` | 43 ms | 28.57% |

Total winner changes: **1**.
Search completed in **809 ms** wall-clock time.

**Stabilization Interpretation:** Moderate exploration — the final winner emerged after 10–40% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — gradient_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260815-150143`
- Calibration schema: `1.1`
- Detector: `gradient_vote`
- Detector configuration: `hth-pipeline/config/detectors/gradient_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `e20fbfa089881d9188888dcfd94bf906289ff1ec`
- Source commit: `5cd5db580a43946dc4c98cc0ebfb040686800080`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `42`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `cf581d27715b`
- Recommended parameter short name: `cf581d27715b`
- Best observed Avg IoU: `0.9622`
- Avg IoU Success: `0.9622`
- Worst Golden Set page (Min IoU): `0.9384`
- Page-to-page StdDev: `0.0160`
- Calibration evidence: `Medium`
- Dormant parameters: `area_weight, central_band_fraction, gaussian_sigma, gradient_percentile, minimum_area_fraction, minimum_span_fraction, minimum_vote_support, rectangularity_weight, support_weight, vote_smooth_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 10 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 22 |
| Parameter sets evaluated | 22 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 12 (54.5%) |
| Best Avg IoU | 0.9622 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.4725 |
| Winner stabilized after | 14 parameter sets |
| Winner stabilized | 118 ms (67% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (18.2%) |
| Equivalent-best configurations (within 0.0001) | 3 (13.6%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 22 | 100.0% | 219 ms | 1.0× |
| Non-dormant | 21 | 95.5% | 209 ms | 1.0× |
| Low+ | 21 | 95.5% | 209 ms | 1.0× |
| Moderate+ | 21 | 95.5% | 209 ms | 1.0× |
| Important+ | 21 | 95.5% | 209 ms | 1.0× |
| Critical | 21 | 95.5% | 209 ms | 1.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `border_search_fraction` | Critical | 1.0000 | 0.9622 | 19.0% | `0.13` (0.9622), `0.135` (0.9622), `0.14` (0.9622) | current run |
| `area_weight` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.25` (0.9467) | current run |
| `central_band_fraction` | Dormant | 0.0375 | 0.0000 | 0.0% | `1` (0.9467) | current run |
| `gaussian_sigma` | Dormant | 0.0375 | 0.0000 | 0.0% | `1.2` (0.9467) | current run |
| `gradient_percentile` | Dormant | 0.0375 | 0.0000 | 0.0% | `70` (0.9467) | current run |
| `minimum_area_fraction` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.2` (0.9467) | current run |
| `minimum_span_fraction` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.15` (0.9467) | current run |
| `minimum_vote_support` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.08` (0.9467) | current run |
| `rectangularity_weight` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.2` (0.9467) | current run |
| `support_weight` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.45` (0.9467) | current run |
| `vote_smooth_fraction` | Dormant | 0.0375 | 0.0000 | 0.0% | `0.012` (0.9467) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `central_band_fraction`, `gaussian_sigma`, `gradient_percentile`, `minimum_area_fraction`, `minimum_span_fraction`, `minimum_vote_support`, `rectangularity_weight`, `support_weight`, `vote_smooth_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.5243 | 0.0000 | 0.9613 | 0.4787 | 54.5% |
| 5 | 0.5012 | 0.0000 | 0.9384 | 0.4582 | 54.5% |
| 6 | 0.5394 | 0.0000 | 0.9889 | 0.4924 | 54.5% |
| 9 | 0.4986 | 0.0000 | 0.9612 | 0.4570 | 54.5% |
| 10 | 0.5242 | 0.0000 | 0.9611 | 0.4785 | 54.5% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="hough-line-borders-hough-2"></a>
<details>
<summary><strong>Hough Line Borders (`hough`)</strong></summary>

**Status:** complete

## Run Information — hough

### Build Provenance

- Run ID: `run-20260810-195940`
- Detector: `hough`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:56:35.726210+00:00`
- Finished: `2026-08-10T19:59:40.046210+00:00`
- Wall-clock elapsed: `3m 4s`
- Est. serial runtime: `48m 20s`
- Effective acceleration: `15.73×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2188`
- Parameter sets evaluated: `2188`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — hough

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | 0.7563 | 1 | 1.4s |
| Baseline | `HTH-0001` | `unknown` | `unknown` | `7078053f309d` | `baseline` | 0.4784 | 0.0000 | 0.2851 | 0.5981 | 1 | 1.4s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `c2c117479e3f` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `axis_angle_tolerance_degrees` | `12.0` |
| `bbox_padding_fraction` | `0.015` |
| `canny_low_threshold` | `65` |
| `hough_threshold_fraction` | `0.055` |
| `maximum_gap_fraction` | `0.055` |
| `minimum_length_fraction` | `0.12` |
| `outer_percentile` | `5.0` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Hough lines | Primary | Generates axis-aligned border hypotheses from detected lines. |
| Outer-line percentile | Scoring | Selects outer line groups used to form a page box. |
| Axis-angle tolerance | Filtering | Restricts candidate lines to near-horizontal or near-vertical orientations. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 5 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 2 | 8 | 16 | `rh8-al319` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `7078053f309d` | `baseline` | 0.4784 | 0.0000 | 0.2851 | -0.1266 | 0.5981 | 1 | reference | reference |
| 1 | unknown | `unknown` | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | +0.0000 | 0.7563 | 1 | 2m 28s | 79.33% |
| 2 | unknown | `unknown` | `d2207b5c0b61` | `d2207b5c0b61` | 0.6040 | 0.0000 | 0.3210 | -0.0010 | 0.7550 | 1 | 2m 12s | 67.95% |
| 3 | unknown | `unknown` | `16967597e3b6` | `16967597e3b6` | 0.6039 | 0.0000 | 0.3215 | -0.0011 | 0.7549 | 1 | 2m 28s | 79.38% |
| 4 | unknown | `unknown` | `bf183b1707fd` | `bf183b1707fd` | 0.6038 | 0.0000 | 0.3209 | -0.0012 | 0.7547 | 1 | 2m 13s | 68.54% |
| 5 | unknown | `unknown` | `7a75b3e87104` | `7a75b3e87104` | 0.6022 | 0.0000 | 0.3206 | -0.0028 | 0.7528 | 1 | 2m 13s | 68.72% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — hough

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `c2c117479e3f` | 0.6261 | 0.8347 | +0.2086 | Improved |
| 5 | `unknown` | `c2c117479e3f` | 0.3071 | 0.5446 | +0.2375 | Improved |
| 6 | `unknown` | `c2c117479e3f` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `unknown` | `c2c117479e3f` | 0.7370 | 0.8188 | +0.0819 | Improved |
| 10 | `unknown` | `c2c117479e3f` | 0.7221 | 0.8270 | +0.1049 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `ed3e6fe9ea40` | 2.7s | 0.05% |
| 2 | `unknown` | `d2ef0aec6694` | 2.8s | 0.64% |
| 3 | `unknown` | `0dd1e07cee62` | 4.4s | 1.28% |
| 4 | `unknown` | `a28d5dc71704` | 4.5s | 1.33% |
| 5 (final) | `unknown` | `07a0b3ac190f` | 7.5s | 2.61% |

Total winner changes: **5**.
Search completed in **3m 4s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `1`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `unknown` | `c2c117479e3f` | 0.0000 | No polygon found |

## Calibration Intelligence — hough

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-195940`
- Calibration schema: `1.1`
- Detector: `hough`
- Detector configuration: `hth-pipeline/config/detectors/hough.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `ddc6357a34db71a97494193712b7db85995ffee4`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `8`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `c2c117479e3f`
- Recommended parameter short name: `c2c117479e3f`
- Best observed Avg IoU: `0.6050`
- Avg IoU Success: `0.7563`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3217`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, axis_angle_tolerance_degrees`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 8 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 2188 of 2188 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2188 |
| Parameter sets evaluated | 2188 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.6050 |
| Minimum Avg IoU | 0.1510 |
| Avg IoU StdDev | 0.1096 |
| Winner stabilized after | 1735 parameter sets |
| Winner stabilized | 2m 28s (79% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2188 | 100.0% | 49m 29s | 1.0× |
| Non-dormant | 729 | 33.3% | 16m 29s | 3.0× |
| Low+ | 729 | 33.3% | 16m 29s | 3.0× |
| Moderate+ | 27 | 1.2% | 36.6s | 81.0× |
| Important+ | 3 | 0.1% | 4.1s | 729.3× |
| Critical | 3 | 0.1% | 4.1s | 729.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `outer_percentile` | Critical | 0.7748 | 0.2317 | 33.3% | `5` (0.5231), `10` (0.4474), `20` (0.2914) | current run |
| `minimum_length_fraction` | Moderate | 0.0386 | 0.0495 | 33.3% | `0.12` (0.4402), `0.2` (0.4311), `0.3` (0.3907) | current run |
| `maximum_gap_fraction` | Moderate | 0.0311 | 0.0437 | 33.3% | `0.09` (0.4373), `0.055` (0.4312), `0.025` (0.3935) | current run |
| `canny_low_threshold` | Low | 0.0273 | 0.0443 | 33.3% | `40` (0.4423), `25` (0.4217), `65` (0.3980) | current run |
| `hough_threshold_fraction` | Low | 0.0063 | 0.0211 | 33.3% | `0.035` (0.4320), `0.055` (0.4190), `0.08` (0.4109) | current run |
| `bbox_padding_fraction` | Low | 0.0047 | 0.0182 | 33.3% | `0.015` (0.4305), `0.005` (0.4191), `0` (0.4124) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.1` (0.4784) | current run |
| `axis_angle_tolerance_degrees` | Dormant | 0.0000 | 0.0009 | 33.3% | `12` (0.4210), `22` (0.4209), `32` (0.4201) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `axis_angle_tolerance_degrees`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_gap_fraction` × `canny_low_threshold` | 0.0808 | 0.0497 | 2188 |
| `minimum_length_fraction` × `maximum_gap_fraction` | 0.0836 | 0.0450 | 2188 |
| `outer_percentile` × `minimum_length_fraction` | 0.8147 | 0.0400 | 2188 |
| `minimum_length_fraction` × `canny_low_threshold` | 0.0727 | 0.0341 | 2188 |
| `outer_percentile` × `maximum_gap_fraction` | 0.8078 | 0.0330 | 2188 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.5626 | 0.0000 | 0.8999 | 0.2287 | 97.1% |
| 5 | 0.1486 | 0.0000 | 0.5446 | 0.1764 | 45.7% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.6832 | 0.0000 | 0.8271 | 0.1454 | 99.6% |
| 10 | 0.7089 | 0.2854 | 0.8552 | 0.1156 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="joint-rectangle-voting-jointrectanglevote-2"></a>
<details>
<summary><strong>Joint Rectangle Voting (`joint_rectangle_vote`)</strong></summary>

**Status:** complete

## Run Information — joint_rectangle_vote

### Build Provenance

- Run ID: `run-20260812-200221`
- Detector: `joint_rectangle_vote`
- Strategy: `exhaustive`
- Pipeline commit: `eea9070116fb`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T20:01:58.215008+00:00`
- Finished: `2026-08-12T20:02:20.470207+00:00`
- Wall-clock elapsed: `22.3s`
- Est. serial runtime: `2h 2m`
- Effective acceleration: `328.91×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `2187`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — joint_rectangle_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `0b94f9621f29` | `unknown` | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | 0.9899 | 4 | 2.4s |
| Baseline | `HTH-0001` | `0b94f9621f29` | `unknown` | `697c22dd549f` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 352 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`eea9070116fb`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `5c9509e05f14` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `axis_tolerance_degrees` | `6.0` |
| `bbox_padding_fraction` | `0.0` |
| `canny_high` | `220.0` |
| `canny_low` | `80.0` |
| `hough_threshold` | `120` |
| `minimum_area_fraction` | `0.16` |
| `minimum_side_support` | `0.18` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Hough line families | Primary | Detects near-horizontal and near-vertical line evidence. |
| Opposing side pairs | Generator | Selects outer opposing lines as a single four-side rectangle hypothesis. |
| Side support | Validation | Requires edge support along all four proposed page boundaries. |
| Rectangle area | Validation | Rejects geometrically implausible page extents. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 4 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-exact-runner` | 23 | 16 | 368 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `697c22dd549f` | `baseline` | 0.0000 | 0.0000 | 0.0000 | -0.1980 | 0.0000 | 5 | reference | reference |
| 1 | unknown | `unknown` | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 21.1s | 98.03% |
| 2 | unknown | `unknown` | `3d84cd0a9026` | `3d84cd0a9026` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 7.7s | 26.67% |
| 3 | unknown | `unknown` | `d2dea9b84b6e` | `d2dea9b84b6e` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 15.6s | 65.69% |
| 4 | unknown | `unknown` | `1e66b0603099` | `1e66b0603099` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 7.3s | 23.47% |
| 5 | unknown | `unknown` | `951741938aa2` | `951741938aa2` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 20.8s | 92.91% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — joint_rectangle_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `unknown` | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `unknown` | `5c9509e05f14` | 0.0000 | 0.9899 | +0.9899 | Recovered |
| 9 | `unknown` | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `unknown` | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `e4eb7eb9fbf0` | 3.2s | 0.41% |
| 2 | `unknown` | `862c5f52fdd9` | 6.9s | 19.72% |
| 3 | `unknown` | `94fb75d7472b` | 7.1s | 21.04% |
| 4 (final) | `unknown` | `1e66b0603099` | 7.3s | 23.47% |

Total winner changes: **4**.
Search completed in **22.3s** wall-clock time.

**Stabilization Interpretation:** Moderate exploration — the final winner emerged after 10–40% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `4`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `5c9509e05f14` | 0.0000 | No polygon found |
| 5 | `unknown` | `5c9509e05f14` | 0.0000 | No polygon found |
| 9 | `unknown` | `5c9509e05f14` | 0.0000 | No polygon found |
| 10 | `unknown` | `5c9509e05f14` | 0.0000 | No polygon found |

## Calibration Intelligence — joint_rectangle_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-200221`
- Calibration schema: `1.1`
- Detector: `joint_rectangle_vote`
- Detector configuration: `hth-pipeline/config/detectors/joint_rectangle_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `eea9070116fb1cce18838ae0b338cc7b2b4ba8ab`
- Source commit: `72b6034c39a81775067d1a56f0ffde59193a9b0c`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `16`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `5c9509e05f14`
- Recommended parameter short name: `5c9509e05f14`
- Best observed Avg IoU: `0.1980`
- Avg IoU Success: `0.9899`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3960`
- Calibration evidence: `Medium`
- Dormant parameters: `bbox_padding_fraction, minimum_area_fraction, minimum_side_support`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 3 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 2187 of 2187 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 2187 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.1980 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0659 |
| Winner stabilized after | 2143 parameter sets |
| Winner stabilized | 21.1s (98% of search) |
| Near-best coverage (basin; within 0.0010) | 27 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 27 (1.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 1h 28m 19s | 1.0× |
| Non-dormant | 81 | 3.7% | 3m 16s | 27.0× |
| Low+ | 81 | 3.7% | 3m 16s | 27.0× |
| Moderate+ | 9 | 0.4% | 21.8s | 243.0× |
| Important+ | 9 | 0.4% | 21.8s | 243.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `canny_high` | Important | 0.1758 | 0.0643 | 33.3% | `220` (0.0643), `100` (0.0140), `150` (0.0000) | current run |
| `hough_threshold` | Important | 0.1758 | 0.0643 | 33.3% | `120` (0.0643), `80` (0.0140), `50` (0.0000) | current run |
| `canny_low` | Low | 0.0100 | 0.0140 | 100.0% | `30` (0.0354), `50` (0.0214), `80` (0.0214) | current run |
| `axis_tolerance_degrees` | Low | 0.0024 | 0.0069 | 33.3% | `12` (0.0284), `18` (0.0284), `6` (0.0215) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0009 | 33.3% | `0` (0.0265), `0.008` (0.0262), `0.016` (0.0256) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0261), `0.16` (0.0261), `0.24` (0.0261) | current run |
| `minimum_side_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0261), `0.18` (0.0261), `0.3` (0.0261) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`bbox_padding_fraction`, `minimum_area_fraction`, `minimum_side_support`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `canny_high` × `hough_threshold` | 0.8417 | 0.6659 | 2187 |
| `canny_high` × `canny_low` | 0.2059 | 0.0301 | 2187 |
| `hough_threshold` × `canny_low` | 0.2059 | 0.0301 | 2187 |
| `canny_high` × `axis_tolerance_degrees` | 0.1834 | 0.0075 | 2187 |
| `hough_threshold` × `axis_tolerance_degrees` | 0.1834 | 0.0075 | 2187 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.1306 | 0.0000 | 0.9899 | 0.3294 | 13.6% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="kraken-page-mask-krakenpagemask-2"></a>
<details>
<summary><strong>Kraken Page Mask (`kraken_page_mask`)</strong></summary>

**Status:** complete

## Run Information — kraken_page_mask

### Build Provenance

- Run ID: `run-20260817-203851`
- Detector: `kraken_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `da7ad14b3019`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-17T20:38:40.886091+00:00`
- Finished: `2026-08-17T20:38:50.279482+00:00`
- Wall-clock elapsed: `9.4s`
- Est. serial runtime: `48m 26s`
- Effective acceleration: `309.40×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `10000`
- Parameter sets evaluated: `10000`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — kraken_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `9f629f3caee1` | `unknown` | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8396 | 0.5596 | 0.1531 | 0.8396 | 0 | 54 ms |
| Baseline | `HTH-0001` | `9f629f3caee1` | `unknown` | `d75b76f301e6` | `baseline` | 0.8068 | 0.6201 | 0.0947 | 0.8068 | 0 | 42 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`da7ad14b3019`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `c4845fd6c6b6` |
| Absolute parameter SHA-256 | `0ad5a02f402f04e10fa227a6b5051aa34eb36175f63c5869e7bddce505f90ef6` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `1c25ef2a0d8ab414b36636e41d1f7eb955c1610e5540d4ac49f3ef61c294a4d6` |
| Grid ordinal | `3009` |
| Reproducibility | **Fully reproducible** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `close_kernel_fraction` | `0.0` |
| `dilation_fraction` | `0.02` |
| `fill_holes` | `1` |
| `include_lines` | `0` |
| `minimum_page_area_fraction` | `0.25` |
| `page_padding_fraction` | `0.0` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Kraken BLLA segmentation | Primary | Uses Kraken's historical-document segmentation model to recover page-region and text-line evidence. |
| Region and line evidence | Generator | Rasterizes learned regions, line polygons, and baselines into a common page-support mask. |
| Sparse multi-region envelope | Robustness | Combines substantial disconnected learned regions when they jointly describe a larger document extent instead of accepting only the dominant component. |
| Page quadrilateral | Geometry | Fits and pads a minimum-area quadrilateral around the selected learned-evidence envelope. |
| Model identity | Provenance | Records the Kraken model provenance and model SHA-256 used to generate the immutable Golden Set evidence. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 3 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 17 | 22 | 374 | `rh8-al307` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `unknown` | `d75b76f301e6` | `baseline` | 0.8068 | 0.6201 | 0.0947 | -0.0328 | 0.8068 | 0 | reference | reference |
| Best** | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `unknown` | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8396 | 0.5596 | 0.1531 | +0.0000 | 0.8396 | 0 | reference | reference |
| 1 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `unknown` | `de686528c884` | `de686528c884` | 0.8396 | 0.5596 | 0.1531 | +0.0000 | 0.8396 | 0 | 2.1s | 32.69% |
| 2 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `unknown` | `788f3aff6db1` | `788f3aff6db1` | 0.8396 | 0.5596 | 0.1531 | +0.0000 | 0.8396 | 0 | 2.1s | 32.90% |
| 3 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `unknown` | `ff40d7e92e50` | `ff40d7e92e50` | 0.8396 | 0.5596 | 0.1531 | +0.0000 | 0.8396 | 0 | 2.1s | 32.40% |
| 4 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `unknown` | `d56ec4c56d71` | `d56ec4c56d71` | 0.8396 | 0.5596 | 0.1531 | +0.0000 | 0.8396 | 0 | 2.1s | 32.47% |
| 5 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `unknown` | `61134fb443b4` | `61134fb443b4` | 0.8396 | 0.5596 | 0.1531 | +0.0000 | 0.8396 | 0 | 1.8s | 27.02% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — kraken_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `c4845fd6c6b6` | 0.8769 | 0.9694 | +0.0925 | Improved |
| 5 | `unknown` | `c4845fd6c6b6` | 0.6201 | 0.5596 | -0.0606 | Regressed |
| 6 | `unknown` | `c4845fd6c6b6` | 0.8310 | 0.7918 | -0.0392 | Regressed |
| 9 | `unknown` | `c4845fd6c6b6` | 0.8437 | 0.9356 | +0.0919 | Improved |
| 10 | `unknown` | `c4845fd6c6b6` | 0.8625 | 0.9416 | +0.0791 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `68cfb88d9f60` | 63 ms | 0.01% |
| 2 | `unknown` | `dbf49629f1d9` | 132 ms | 0.10% |
| 3 (final) | `unknown` | `c4845fd6c6b6` | 474 ms | 2.52% |

Total winner changes: **3**.
Search completed in **9.4s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 5 | `unknown` | `c4845fd6c6b6` | 0.5596 | Regressed |
| 6 | `unknown` | `c4845fd6c6b6` | 0.7918 | Regressed |

## Calibration Intelligence — kraken_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260817-203851`
- Calibration schema: `1.1`
- Detector: `kraken_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/kraken_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `da7ad14b3019ee394e9e6bab389f05c65c4b582d`
- Source commit: `61cdb8397fe047e6648ddee45170dd4a72d9f0c3`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `22`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `c4845fd6c6b6`
- Recommended parameter short name: `c4845fd6c6b6`
- Best observed Avg IoU: `0.8396`
- Avg IoU Success: `0.8396`
- Worst Golden Set page (Min IoU): `0.5596`
- Page-to-page StdDev: `0.1531`
- Calibration evidence: `High`
- Dormant parameters: `close_kernel_fraction, fill_holes, minimum_page_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 3 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 10000 |
| Parameter sets evaluated | 10000 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 10000 (100.0%) |
| Best Avg IoU | 0.8396 |
| Minimum Avg IoU | 0.7728 |
| Avg IoU StdDev | 0.0205 |
| Winner stabilized after | 252 parameter sets |
| Winner stabilized | 474 ms (3% of search) |
| Near-best coverage (basin; within 0.0010) | 100 (1.0%) |
| Equivalent-best configurations (within 0.0001) | 40 (0.4%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 10000 | 100.0% | 8m 56s | 1.0× |
| Non-dormant | 200 | 2.0% | 10.7s | 50.0× |
| Low+ | 200 | 2.0% | 10.7s | 50.0× |
| Moderate+ | 100 | 1.0% | 5.4s | 100.0× |
| Important+ | 10 | 0.1% | 536 ms | 1000.0× |
| Critical | 10 | 0.1% | 536 ms | 1000.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `page_padding_fraction` | Critical | 0.8934 | 0.0588 | 10.0% | `0` (0.8336), `0.01` (0.8303), `0.02` (0.8232) | current run |
| `dilation_fraction` | Moderate | 0.0771 | 0.0183 | 20.0% | `0` (0.8108), `0.0025` (0.8103), `0.005` (0.8100) | current run |
| `include_lines` | Low | 0.0036 | 0.0025 | 50.0% | `1` (0.8067), `0` (0.8042) | current run |
| `close_kernel_fraction` | Dormant | 0.0002 | 0.0008 | 100.0% | `0.012` (0.8058), `0.006` (0.8056), `0.003` (0.8055) | current run |
| `fill_holes` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.8055), `1` (0.8055) | current run |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8055), `0.12` (0.8055), `0.16` (0.8055) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_kernel_fraction`, `fill_holes`, `minimum_page_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `page_padding_fraction` × `dilation_fraction` | 0.9908 | 0.0974 | 10000 |
| `page_padding_fraction` × `include_lines` | 0.8981 | 0.0047 | 10000 |
| `dilation_fraction` × `include_lines` | 0.0808 | 0.0037 | 10000 |
| `dilation_fraction` × `close_kernel_fraction` | 0.0791 | 0.0020 | 10000 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8743 | 0.7782 | 0.9788 | 0.0598 | 100.0% |
| 5 | 0.6190 | 0.5226 | 0.6752 | 0.0432 | 100.0% |
| 6 | 0.8293 | 0.7560 | 0.8855 | 0.0306 | 100.0% |
| 9 | 0.8410 | 0.7399 | 0.9622 | 0.0647 | 100.0% |
| 10 | 0.8637 | 0.7940 | 0.9599 | 0.0505 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="learned-page-mask-detector-learnedpagemask-2"></a>
<details>
<summary><strong>Learned Page-Mask Detector (`learned_page_mask`)</strong></summary>

**Status:** complete

## Run Information — learned_page_mask

### Build Provenance

- Run ID: `run-20260813-160754`
- Detector: `learned_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `9e60b2c88b51`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-13T14:48:25.122499+00:00`
- Finished: `2026-08-13T16:07:46.691779+00:00`
- Wall-clock elapsed: `1h 19m 22s`
- Est. serial runtime: `20d 23h 27m 40s`
- Effective acceleration: `380.64×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50000`
- Parameter sets evaluated: `50000`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — learned_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `ea90f1d0eee5` | `unknown` | `275078578cee` | `275078578cee` | 0.8868 | 0.8122 | 0.0470 | 0.8868 | 0 | 36.8s |
| Baseline | `HTH-0001` | `ea90f1d0eee5` | `unknown` | `04e0ef2b5787` | `baseline` | 0.8374 | 0.7029 | 0.0740 | 0.8374 | 0 | 701 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`9e60b2c88b51`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `275078578cee` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.029` |
| `close_kernel_fraction` | `0.0` |
| `mask_threshold` | `0.226` |
| `minimum_mask_area_fraction` | `0.04` |
| `polygon_epsilon_fraction` | `0.0185` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| PageNet segmentation | Primary | Uses a pretrained historical-document CNN to predict per-pixel page membership. |
| Probability threshold | Generator | Converts learned probabilities into a page mask. |
| Dominant learned region | Geometry | Fits a quadrilateral to the dominant predicted region. |
| Model identity | Provenance | Records released-model source, license, and SHA-256. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 10 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 4 | 96 | 384 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `04e0ef2b5787` | `baseline` | 0.8374 | 0.7029 | 0.0740 | -0.0494 | 0.8374 | 0 | reference | reference |
| 1 | unknown | `unknown` | `275078578cee` | `275078578cee` | 0.8868 | 0.8122 | 0.0470 | +0.0000 | 0.8868 | 0 | 35m 56s | 44.78% |
| 2 | unknown | `unknown` | `3d8095986d9a` | `3d8095986d9a` | 0.8868 | 0.8122 | 0.0470 | +0.0000 | 0.8868 | 0 | 36m 6s | 44.97% |
| 3 | unknown | `unknown` | `d5e117ddf813` | `d5e117ddf813` | 0.8868 | 0.8122 | 0.0470 | +0.0000 | 0.8868 | 0 | 36m 55s | 46.03% |
| 4 | unknown | `unknown` | `11e7cbc6f848` | `11e7cbc6f848` | 0.8868 | 0.8122 | 0.0470 | +0.0000 | 0.8868 | 0 | 37m 30s | 46.77% |
| 5 | unknown | `unknown` | `7a323edb562e` | `7a323edb562e` | 0.8868 | 0.8122 | 0.0470 | +0.0000 | 0.8868 | 0 | 37m 42s | 47.02% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — learned_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `275078578cee` | 0.8884 | 0.9135 | +0.0251 | Improved |
| 5 | `unknown` | `275078578cee` | 0.9183 | 0.9195 | +0.0011 | Improved |
| 6 | `unknown` | `275078578cee` | 0.7029 | 0.8122 | +0.1092 | Improved |
| 9 | `unknown` | `275078578cee` | 0.8479 | 0.8521 | +0.0042 | Improved |
| 10 | `unknown` | `275078578cee` | 0.8297 | 0.9369 | +0.1072 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 6 | `unknown` | `c605830c818e` | 10m 9s | 12.23% |
| 7 | `unknown` | `01fbb2042031` | 10m 21s | 12.43% |
| 8 | `unknown` | `1a548b3a69ea` | 10m 25s | 12.48% |
| 9 | `unknown` | `b829f3e60adc` | 13m 5s | 15.86% |
| 10 (final) | `unknown` | `90ba33886d5f` | 35m 3s | 43.64% |

Total winner changes: **10**.
Search completed in **1h 19m 22s** wall-clock time.

**Stabilization Interpretation:** Late convergence — the final winner emerged after 40–80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — learned_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260813-160754`
- Calibration schema: `1.1`
- Detector: `learned_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/learned_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `9e60b2c88b51a0c0e3ae2f79b0494cbf2ffad117`
- Source commit: `e7b1675473ca1c7647fa4a5590cf798b8b543b43`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `275078578cee`
- Recommended parameter short name: `275078578cee`
- Best observed Avg IoU: `0.8868`
- Avg IoU Success: `0.8868`
- Worst Golden Set page (Min IoU): `0.8122`
- Page-to-page StdDev: `0.0470`
- Calibration evidence: `High`
- Dormant parameters: `minimum_mask_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 5 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 50000 |
| Parameter sets evaluated | 50000 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 50000 (100.0%) |
| Best Avg IoU | 0.8868 |
| Minimum Avg IoU | 0.8158 |
| Avg IoU StdDev | 0.0066 |
| Winner stabilized after | 22390 parameter sets |
| Winner stabilized | 35m 56s (45% of search) |
| Near-best coverage (basin; within 0.0010) | 510 (1.0%) |
| Equivalent-best configurations (within 0.0001) | 56 (0.1%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 50000 | 100.0% | 21d 6h 42m 26s | 1.0× |
| Non-dormant | 25000 | 50.0% | 10d 15h 21m 13s | 2.0× |
| Low+ | 25000 | 50.0% | 10d 15h 21m 13s | 2.0× |
| Moderate+ | 12500 | 25.0% | 5d 7h 40m 36s | 4.0× |
| Important+ | 12500 | 25.0% | 5d 7h 40m 36s | 4.0× |
| Critical | 625 | 1.2% | 6h 23m 2s | 80.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `bbox_padding_fraction` | Critical | 0.2994 | 0.0184 | 52.0% | `0.027` (0.8788), `0.028` (0.8788), `0.029` (0.8788) | current run |
| `mask_threshold` | Critical | 0.2921 | 0.0175 | 28.0% | `0.214` (0.8789), `0.21` (0.8789), `0.212` (0.8788) | current run |
| `polygon_epsilon_fraction` | Important | 0.1620 | 0.0076 | 55.0% | `0.0195` (0.8805), `0.019` (0.8803), `0.02` (0.8802) | current run |
| `close_kernel_fraction` | Low | 0.0041 | 0.0009 | 100.0% | `0` (0.8768), `0.006` (0.8759) | current run |
| `minimum_mask_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8763), `0.15` (0.8763) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_mask_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `bbox_padding_fraction` × `mask_threshold` | 0.6362 | 0.3368 | 50000 |
| `mask_threshold` × `polygon_epsilon_fraction` | 0.5219 | 0.2298 | 50000 |
| `bbox_padding_fraction` × `polygon_epsilon_fraction` | 0.5259 | 0.2265 | 50000 |
| `polygon_epsilon_fraction` × `close_kernel_fraction` | 0.1866 | 0.0246 | 50000 |
| `mask_threshold` × `close_kernel_fraction` | 0.3115 | 0.0194 | 50000 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8951 | 0.8593 | 0.9528 | 0.0228 | 100.0% |
| 5 | 0.9143 | 0.9021 | 0.9242 | 0.0065 | 100.0% |
| 6 | 0.8066 | 0.7029 | 0.8221 | 0.0191 | 100.0% |
| 9 | 0.8410 | 0.7701 | 0.8587 | 0.0146 | 100.0% |
| 10 | 0.9247 | 0.8240 | 0.9511 | 0.0193 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="line-segment-detector-lsd-2"></a>
<details>
<summary><strong>Line Segment Detector (`lsd`)</strong></summary>

**Status:** complete

## Run Information — lsd

### Build Provenance

- Run ID: `run-20260810-195852`
- Detector: `lsd`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:58:52.506857+00:00`
- Finished: `2026-08-10T19:59:51.466427+00:00`
- Wall-clock elapsed: `59s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `2187`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — lsd

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | 0.9222 | 1 | 379 ms |
| Baseline | `HTH-0001` | `unknown` | `unknown` | `b2df04f4e947` | `baseline` | 0.5414 | 0.0000 | 0.4436 | 0.9023 | 2 | 332 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `7546c5067527` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `axis_angle_tolerance_degrees` | `10.0` |
| `bbox_padding_fraction` | `0.005` |
| `minimum_bbox_area_fraction` | `0.08` |
| `minimum_length_fraction` | `0.22` |
| `outer_percentile` | `5.0` |
| `refine_mode` | `"none"` |
| `scale` | `0.8` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| LSD segments | Primary | Generates border hypotheses directly from line segments. |
| Outer-line percentile | Scoring | Selects outer segment groups for page-boundary construction. |
| Axis-angle tolerance | Filtering | Limits segments to plausible page-border orientations. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 3 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 7 |
| Total metric improvements | 10 |
| Parameter sets with improvements | 9 |
| Winner changes | 3 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 1 | 16 | 16 | `rh8-al318` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `b2df04f4e947` | `baseline` | 0.5414 | 0.0000 | 0.4436 | -0.1964 | 0.9023 | 2 | reference | reference |
| 1 | unknown | `unknown` | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 7.9s | 18.57% |
| 2 | unknown | `unknown` | `05a653fabdd0` | `05a653fabdd0` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 8.1s | 18.76% |
| 3 | unknown | `unknown` | `497528ffc236` | `497528ffc236` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 8.2s | 18.89% |
| 4 | unknown | `unknown` | `24a5a18c61f3` | `24a5a18c61f3` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 8.7s | 19.76% |
| 5 | unknown | `unknown` | `97f5383e66cd` | `97f5383e66cd` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 8.7s | 19.99% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — lsd

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `7546c5067527` | 0.8955 | 0.9102 | +0.0147 | Improved |
| 5 | `unknown` | `7546c5067527` | 0.0000 | 0.9850 | +0.9850 | Recovered |
| 6 | `unknown` | `7546c5067527` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `unknown` | `7546c5067527` | 0.8475 | 0.8400 | -0.0075 | Regressed |
| 10 | `unknown` | `7546c5067527` | 0.9641 | 0.9537 | -0.0103 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `0bd9251e7f32` | 570 ms | 0.05% |
| 2 | `unknown` | `1b2cebd68deb` | 622 ms | 0.32% |
| 3 (final) | `unknown` | `7546c5067527` | 7.9s | 18.57% |

Total winner changes: **3**.
Search completed in **59s** wall-clock time.

**Stabilization Interpretation:** Moderate exploration — the final winner emerged after 10–40% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `1`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `unknown` | `7546c5067527` | 0.0000 | No polygon found |
| 9 | `unknown` | `7546c5067527` | 0.8400 | Regressed |
| 10 | `unknown` | `7546c5067527` | 0.9537 | Regressed |

## Calibration Intelligence — lsd

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-195852`
- Calibration schema: `1.1`
- Detector: `lsd`
- Detector configuration: `hth-pipeline/config/detectors/lsd.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `ddc6357a34db71a97494193712b7db85995ffee4`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `16`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `7546c5067527`
- Recommended parameter short name: `7546c5067527`
- Best observed Avg IoU: `0.7378`
- Avg IoU Success: `0.9222`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3721`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, axis_angle_tolerance_degrees`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 2187 of 2187 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 2187 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7378 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.1839 |
| Winner stabilized after | 406 parameter sets |
| Winner stabilized | 7.9s (19% of search) |
| Near-best coverage (basin; within 0.0010) | 27 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 9 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 13m 48s | 1.0× |
| Non-dormant | 243 | 11.1% | 1m 32s | 9.0× |
| Low+ | 243 | 11.1% | 1m 32s | 9.0× |
| Moderate+ | 81 | 3.7% | 30.7s | 27.0× |
| Important+ | 27 | 1.2% | 10.2s | 81.0× |
| Critical | 3 | 0.1% | 1.1s | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `refine_mode` | Critical | 0.2730 | 0.2038 | 33.3% | `none` (0.5940), `adv` (0.3902), `std` (0.3902) | current run |
| `minimum_length_fraction` | Important | 0.2059 | 0.1926 | 100.0% | `0.08` (0.5347), `0.14` (0.4975), `0.22` (0.3421) | current run |
| `outer_percentile` | Important | 0.1380 | 0.1568 | 33.3% | `5` (0.5197), `10` (0.4918), `20` (0.3629) | current run |
| `scale` | Moderate | 0.0428 | 0.0888 | 66.7% | `0.6` (0.4944), `0.8` (0.4743), `1` (0.4056) | current run |
| `bbox_padding_fraction` | Low | 0.0012 | 0.0138 | 33.3% | `0` (0.4628), `0.005` (0.4624), `0.015` (0.4490) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0004 | 100.0% | `0.08` (0.4584), `0.1` (0.4580), `0.15` (0.4580) | current run |
| `axis_angle_tolerance_degrees` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.4581), `18` (0.4581), `28` (0.4581) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `axis_angle_tolerance_degrees`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `refine_mode` × `minimum_length_fraction` | 0.6959 | 0.4229 | 2187 |
| `minimum_length_fraction` × `outer_percentile` | 0.3574 | 0.1515 | 2187 |
| `refine_mode` × `outer_percentile` | 0.4186 | 0.1457 | 2187 |
| `refine_mode` × `scale` | 0.3458 | 0.0728 | 2187 |
| `outer_percentile` × `scale` | 0.1962 | 0.0583 | 2187 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.5060 | 0.0000 | 0.9442 | 0.4240 | 61.7% |
| 5 | 0.2201 | 0.0000 | 0.9850 | 0.3124 | 35.3% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.7826 | 0.0000 | 0.8544 | 0.1894 | 96.7% |
| 10 | 0.7818 | 0.0000 | 0.9834 | 0.3409 | 85.2% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="fusion-gen1-msre-bfq-spbv-page-background-msrebfqspbvpbg-2"></a>
<details>
<summary><strong>Fusion Gen1 — MSRE + BFQ + SPBV + Page Background (`msre_bfq_spbv_pbg`)</strong></summary>

**Status:** complete

## Run Information — msre_bfq_spbv_pbg

### Build Provenance

- Run ID: `run-20260814-184153`
- Detector: `msre_bfq_spbv_pbg`
- Strategy: `exhaustive`
- Pipeline commit: `25dcfe9e8b50`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-14T17:32:59.628457+00:00`
- Finished: `2026-08-14T18:41:46.282549+00:00`
- Wall-clock elapsed: `1h 8m 47s`
- Est. serial runtime: `16d 11h 57m 22s`
- Effective acceleration: `345.42×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50176`
- Parameter sets evaluated: `50176`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — msre_bfq_spbv_pbg

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `f8c6ce9843d5` | `unknown` | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9747 | 0.9638 | 0.0101 | 0.9747 | 0 | 18.7s |
| Baseline | `HTH-0001` | `f8c6ce9843d5` | `unknown` | `54d4e56ee0fc` | `baseline` | 0.9738 | 0.9638 | 0.0103 | 0.9738 | 0 | 1.6s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`25dcfe9e8b50`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `7b7dbac43ea6` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `consensus_tolerance_fraction` | `0.031641` |
| `consensus_weight` | `0.6` |
| `gradient_percentile` | `76.0` |
| `gradient_weight` | `0.25` |
| `minimum_side_consensus` | `0.867713` |
| `minimum_side_gradient_support` | `0.03` |
| `source_diversity_weight` | `0.15` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (MSRE + BFQ + SPBV + Page Background)

| Evidence source | Function | Interpretation |
|---|---|---|
| Calibrated child quadrilaterals | Primary | Runs the best-known calibrated MSRE, BFQ, SPBV, and Page Background hypotheses as four deliberately distinct evidence families. |
| Side-level consensus | Generator | Recombines top/right/bottom/left boundaries and rewards sides independently supported by the other child quadrilaterals. |
| Gradient support | Validation | Checks each fused side against image-gradient evidence without granting extra votes to the RE/ARE radial lineage. |
| Source diversity | Robustness | Rewards fused quadrilaterals whose four sides draw from multiple hypothesis families. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 2 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 36 | 10 | 360 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `54d4e56ee0fc` | `baseline` | 0.9738 | 0.9638 | 0.0103 | -0.0009 | 0.9738 | 0 | reference | reference |
| 1 | unknown | `unknown` | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9747 | 0.9638 | 0.0101 | +0.0000 | 0.9747 | 0 | 1h 7m 13s | 99.20% |
| 2 | unknown | `unknown` | `a4620024015d` | `a4620024015d` | 0.9747 | 0.9638 | 0.0101 | +0.0000 | 0.9747 | 0 | 1h 6m 58s | 98.86% |
| 3 | unknown | `unknown` | `092c820ce756` | `092c820ce756` | 0.9747 | 0.9638 | 0.0101 | +0.0000 | 0.9747 | 0 | 1h 5m 19s | 96.73% |
| 4 | unknown | `unknown` | `8ca9228b4d29` | `8ca9228b4d29` | 0.9747 | 0.9638 | 0.0101 | +0.0000 | 0.9747 | 0 | 1h 4m 16s | 95.39% |
| 5 | unknown | `unknown` | `b22a7446bcc1` | `b22a7446bcc1` | 0.9743 | 0.9638 | 0.0103 | -0.0004 | 0.9743 | 0 | 1h 1m 45s | 91.57% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — msre_bfq_spbv_pbg

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `7b7dbac43ea6` | 0.9729 | 0.9785 | +0.0056 | Improved |
| 5 | `unknown` | `7b7dbac43ea6` | 0.9761 | 0.9761 | +0.0000 | Unchanged |
| 6 | `unknown` | `7b7dbac43ea6` | 0.9920 | 0.9911 | -0.0009 | Unchanged |
| 9 | `unknown` | `7b7dbac43ea6` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `unknown` | `7b7dbac43ea6` | 0.9643 | 0.9643 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `b22a7446bcc1` | 1h 1m 45s | 91.57% |
| 2 (final) | `unknown` | `8ca9228b4d29` | 1h 4m 16s | 95.39% |

Total winner changes: **2**.
Search completed in **1h 8m 47s** wall-clock time.

**Stabilization Interpretation:** No stable optimum — the final winner did not emerge until more than 80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — msre_bfq_spbv_pbg

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260814-184153`
- Calibration schema: `1.1`
- Detector: `msre_bfq_spbv_pbg`
- Detector configuration: `hth-pipeline/config/detectors/msre_bfq_spbv_pbg.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `25dcfe9e8b5047a62937255e9afd50d1ef2e3de9`
- Source commit: `b63242213c549c52482d4197bca72db133a098fd`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `10`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `7b7dbac43ea6`
- Recommended parameter short name: `7b7dbac43ea6`
- Best observed Avg IoU: `0.9747`
- Avg IoU Success: `0.9747`
- Worst Golden Set page (Min IoU): `0.9638`
- Page-to-page StdDev: `0.0101`
- Calibration evidence: `Medium`
- Dormant parameters: `consensus_weight, gradient_percentile, gradient_weight, minimum_side_gradient_support, source_diversity_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 5 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 50176 |
| Parameter sets evaluated | 50176 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 42395 (84.5%) |
| Best Avg IoU | 0.9747 |
| Minimum Avg IoU | 0.1984 |
| Avg IoU StdDev | 0.1319 |
| Winner stabilized after | 49773 parameter sets |
| Winner stabilized | 1h 7m 13s (99% of search) |
| Near-best coverage (basin; within 0.0010) | 15544 (31.0%) |
| Equivalent-best configurations (within 0.0001) | 4 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Non-dormant | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Low+ | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Moderate+ | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Important+ | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |
| Critical | 50176 | 100.0% | 10d 20h 18m 31s | 1.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_side_consensus` | Critical | 0.2704 | 0.2601 | 93.8% | `0.487444` (0.9736), `0.483857` (0.9735), `0.480269` (0.9735) | current run |
| `consensus_tolerance_fraction` | Critical | 0.2696 | 0.2502 | 42.9% | `0.037623` (0.9736), `0.03783` (0.9736), `0.038036` (0.9736) | current run |
| `consensus_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.6` (0.9201) | current run |
| `gradient_percentile` | Dormant | 0.0000 | 0.0000 | 100.0% | `76` (0.9201) | current run |
| `gradient_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.9201) | current run |
| `minimum_side_gradient_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.9201) | current run |
| `source_diversity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.9201) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consensus_weight`, `gradient_percentile`, `gradient_weight`, `minimum_side_gradient_support`, `source_diversity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_side_consensus` × `consensus_tolerance_fraction` | 1.0000 | 0.7256 | 25088 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8227 | 0.0000 | 0.9785 | 0.3515 | 84.6% |
| 5 | 0.8664 | 0.0000 | 0.9913 | 0.3083 | 88.8% |
| 6 | 0.9915 | 0.9911 | 0.9931 | 0.0005 | 100.0% |
| 9 | 0.9597 | 0.0000 | 0.9638 | 0.0565 | 99.7% |
| 10 | 0.9603 | 0.0000 | 0.9643 | 0.0567 | 99.7% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="multi-scale-radial-edge-search-multiscaleradialedge-2"></a>
<details>
<summary><strong>Multi-Scale Radial Edge Search (`multi_scale_radial_edge`)</strong></summary>

**Status:** complete

## Run Information — multi_scale_radial_edge

### Build Provenance

- Run ID: `run-20260814-015713`
- Detector: `multi_scale_radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `1000d4a6d7b9`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-13T22:06:01.473140+00:00`
- Finished: `2026-08-14T01:56:19.583951+00:00`
- Wall-clock elapsed: `3h 50m 18s`
- Est. serial runtime: `2d 11h 42m 29s`
- Effective acceleration: `15.56×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `384077`
- Parameter sets evaluated: `384077`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — multi_scale_radial_edge

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `93856df8cd67` | `unknown` | `ddb7623ebb92` | `ddb7623ebb92` | 0.9765 | 0.9566 | 0.0175 | 0.9765 | 0 | 959 ms |
| Baseline | `HTH-0001` | `93856df8cd67` | `unknown` | `e732fc5165fb` | `baseline` | 0.6520 | 0.3544 | 0.1762 | 0.6520 | 0 | 184 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`1000d4a6d7b9`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `ddb7623ebb92` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `base_sigma` | `1.0` |
| `gradient_percentile` | `96.875` |
| `ray_count` | `176` |
| `scale_count` | `4` |
| `scale_ratio` | `3.5` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Scale-space gradient field | Primary | Measures page-boundary transitions across several independently normalized blur scales. |
| Center-outward rays | Generator | Samples the fused scale-space evidence along radial paths from the document center. |
| Cross-scale persistence | Robustness | Allows a physical boundary to remain strong when fine texture or coarse illumination weakens another scale. |
| Minimum-area rectangle | Geometry | Fits a page quadrilateral to angularly distributed multi-scale edge points. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 19 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto-fallback-no-shape-history` | 4 | 4 | 16 | `rh8-al318` | 4 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `e732fc5165fb` | `baseline` | 0.6520 | 0.3544 | 0.1762 | -0.3245 | 0.6520 | 0 | reference | reference |
| 1 | unknown | `unknown` | `ddb7623ebb92` | `ddb7623ebb92` | 0.9765 | 0.9566 | 0.0175 | +0.0000 | 0.9765 | 0 | 3h 34m 22s | 94.50% |
| 2 | unknown | `unknown` | `271c2530e085` | `271c2530e085` | 0.9764 | 0.9562 | 0.0164 | -0.0002 | 0.9764 | 0 | 1h 33m 40s | 41.49% |
| 3 | unknown | `unknown` | `af4c8beeb0eb` | `af4c8beeb0eb` | 0.9764 | 0.9562 | 0.0164 | -0.0002 | 0.9764 | 0 | 1h 33m 59s | 41.63% |
| 4 | unknown | `unknown` | `7afcc292a6ad` | `7afcc292a6ad` | 0.9764 | 0.9562 | 0.0164 | -0.0002 | 0.9764 | 0 | 2h 51m 51s | 75.88% |
| 5 | unknown | `unknown` | `f68d6528fbdf` | `f68d6528fbdf` | 0.9764 | 0.9562 | 0.0164 | -0.0002 | 0.9764 | 0 | 2h 51m 50s | 75.87% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — multi_scale_radial_edge

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `ddb7623ebb92` | 0.7081 | 0.9767 | +0.2686 | Improved |
| 5 | `unknown` | `ddb7623ebb92` | 0.6844 | 0.9962 | +0.3119 | Improved |
| 6 | `unknown` | `ddb7623ebb92` | 0.3544 | 0.9959 | +0.6414 | Improved |
| 9 | `unknown` | `ddb7623ebb92` | 0.6140 | 0.9566 | +0.3426 | Improved |
| 10 | `unknown` | `ddb7623ebb92` | 0.8991 | 0.9573 | +0.0581 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 15 | `unknown` | `01bdeb81d1eb` | 2m 54s | 1.59% |
| 16 | `unknown` | `2e5b8c48f2ab` | 2m 57s | 1.61% |
| 17 | `unknown` | `9d2e6a349946` | 3m 1s | 1.64% |
| 18 | `unknown` | `271c2530e085` | 1h 33m 40s | 41.49% |
| 19 (final) | `unknown` | `ddb7623ebb92` | 3h 34m 22s | 94.50% |

Total winner changes: **19**.
Search completed in **3h 50m 18s** wall-clock time.

**Stabilization Interpretation:** No stable optimum — the final winner did not emerge until more than 80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — multi_scale_radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260814-015713`
- Calibration schema: `1.1`
- Detector: `multi_scale_radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/multi_scale_radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1000d4a6d7b9b8f1bd73682a42f3c26d9ba73f62`
- Source commit: `c3ce5a61fca2d0595cbc4d75f8d1757fabee3c95`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `4`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `ddb7623ebb92`
- Recommended parameter short name: `ddb7623ebb92`
- Best observed Avg IoU: `0.9765`
- Avg IoU Success: `0.9765`
- Worst Golden Set page (Min IoU): `0.9566`
- Page-to-page StdDev: `0.0175`
- Calibration evidence: `Medium`
- Dormant parameters: `area_weight, bbox_padding_fraction, maximum_area_fraction, maximum_radius_fraction, minimum_area_fraction, minimum_radius_fraction, minimum_ray_support, strength_weight, support_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 9 of 14 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 384077 |
| Parameter sets evaluated | 384077 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 383901 (100.0%) |
| Best Avg IoU | 0.9765 |
| Minimum Avg IoU | 0.4493 |
| Avg IoU StdDev | 0.0480 |
| Winner stabilized after | 362950 parameter sets |
| Winner stabilized | 3h 34m 22s (94% of search) |
| Near-best coverage (basin; within 0.0010) | 75 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 384077 | 100.0% | 4d 6h 16m 47s | 1.0× |
| Non-dormant | 384076 | 100.0% | 4d 6h 16m 46s | 1.0× |
| Low+ | 384076 | 100.0% | 4d 6h 16m 46s | 1.0× |
| Moderate+ | 43 | 0.0% | 41.2s | 8932.0× |
| Important+ | 43 | 0.0% | 41.2s | 8932.0× |
| Critical | 43 | 0.0% | 41.2s | 8932.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_percentile` | Critical | 0.8335 | 0.2814 | 39.5% | `95.5` (0.9614), `95.625` (0.9613), `95.375` (0.9611) | current run |
| `base_sigma` | Low | 0.0281 | 0.0241 | 27.6% | `1.3` (0.9540), `1.475` (0.9538), `1.35` (0.9535) | current run |
| `ray_count` | Low | 0.0135 | 0.0166 | 28.6% | `240` (0.9536), `192` (0.9521), `96` (0.9517) | current run |
| `scale_ratio` | Low | 0.0079 | 0.0142 | 54.5% | `2.875` (0.9512), `3` (0.9508), `2.75` (0.9504) | current run |
| `scale_count` | Low | 0.0017 | 0.0039 | 100.0% | `4` (0.9483), `3` (0.9444) | current run |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.2` (0.6520) | current run |
| `bbox_padding_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0` (0.6520) | current run |
| `maximum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.98` (0.6520) | current run |
| `maximum_radius_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.78` (0.6520) | current run |
| `minimum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.18` (0.6520) | current run |
| `minimum_radius_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.16` (0.6520) | current run |
| `minimum_ray_support` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.36` (0.6520) | current run |
| `strength_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.3` (0.6520) | current run |
| `support_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.5` (0.6520) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `bbox_padding_fraction`, `maximum_area_fraction`, `maximum_radius_fraction`, `minimum_area_fraction`, `minimum_radius_fraction`, `minimum_ray_support`, `strength_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `gradient_percentile` × `base_sigma` | 0.8977 | 0.0639 | 48010 |
| `base_sigma` × `scale_ratio` | 0.0539 | 0.0257 | 48010 |
| `base_sigma` × `ray_count` | 0.0529 | 0.0246 | 48010 |
| `gradient_percentile` × `ray_count` | 0.8555 | 0.0216 | 48010 |
| `ray_count` × `scale_ratio` | 0.0251 | 0.0120 | 48010 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9542 | 0.2997 | 0.9963 | 0.0525 | 100.0% |
| 5 | 0.9544 | 0.5614 | 0.9971 | 0.0468 | 100.0% |
| 6 | 0.9220 | 0.2904 | 1.0000 | 0.1288 | 100.0% |
| 9 | 0.9496 | 0.0000 | 0.9616 | 0.0383 | 100.0% |
| 10 | 0.9516 | 0.7940 | 0.9820 | 0.0134 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="orli-page-mask-orlipagemask-2"></a>
<details>
<summary><strong>Orli Page Mask (`orli_page_mask`)</strong></summary>

**Status:** complete

## Run Information — orli_page_mask

### Build Provenance

- Run ID: `run-20260820-032343`
- Detector: `orli_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `1ee8d0935ff6`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:23:28.743822+00:00`
- Finished: `2026-08-20T03:23:42.415320+00:00`
- Wall-clock elapsed: `13.7s`
- Est. serial runtime: `1h 14m 20s`
- Effective acceleration: `326.26×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1680`
- Parameter sets evaluated: `1680`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — orli_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `e94fed281c30` | `d58e03537115` | `bd0c02b4f4fe` | `bd0c02b4f4fe` | 0.9185 | 0.8557 | 0.0411 | 0.9185 | 0 | 228 ms |
| Baseline | `HTH-0001` | `e94fed281c30` | `479a861bb552` | `d75b76f301e6` | `baseline` | 0.8063 | 0.6913 | 0.0867 | 0.8063 | 0 | 228 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`1ee8d0935ff6`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `d58e03537115` |
| Parameter Set ID (legacy alias) | `bd0c02b4f4fe` |
| Absolute parameter SHA-256 | `c1778ac8b8c4fa6110b19ddf798fa6e5094a0fa23a52087794db2f452ada69e5` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `b57207a2661208171dc0551e8f8024ab795228ddaf2c7b523d01d97c84153790` |
| Grid ordinal | `917` |
| Reproducibility | **Fully reproducible** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `close_kernel_fraction` | `0.006` |
| `dilation_fraction` | `0.0` |
| `fill_holes` | `1` |
| `include_lines` | `1` |
| `minimum_page_area_fraction` | `0.04` |
| `page_padding_fraction` | `0.16` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Orli historical baseline model | Primary | Uses Orli's historical-document base model to recover page-region and text-line evidence. |
| Region and line evidence | Generator | Rasterizes learned regions, line polygons, and baselines into a common page-support mask. |
| Sparse multi-region envelope | Robustness | Combines substantial disconnected learned regions when they jointly describe a larger document extent instead of accepting only the dominant component. |
| Page quadrilateral | Geometry | Fits and pads a minimum-area quadrilateral around the selected learned-evidence envelope. |
| Model identity | Provenance | Records the Orli model provenance and model SHA-256 used to generate the immutable Golden Set evidence. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 14 | 27 | 378 | `rh8-al308` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `479a861bb552` | `d75b76f301e6` | `baseline` | 0.8063 | 0.6913 | 0.0867 | -0.1122 | 0.8063 | 0 | reference | reference |
| Best** | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `d58e03537115` | `bd0c02b4f4fe` | `bd0c02b4f4fe` | 0.9185 | 0.8557 | 0.0411 | +0.0000 | 0.9185 | 0 | reference | reference |
| 1 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `51cca5b09690` | `00ef6c43ace4` | `00ef6c43ace4` | 0.9185 | 0.8557 | 0.0411 | +0.0000 | 0.9185 | 0 | 8.6s | 55.27% |
| 2 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `c1a9bf418d6f` | `e0cc09712f81` | `e0cc09712f81` | 0.9185 | 0.8557 | 0.0411 | +0.0000 | 0.9185 | 0 | 8.3s | 50.45% |
| 3 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `5b9fa4e280fb` | `cbd779241f30` | `cbd779241f30` | 0.9185 | 0.8557 | 0.0411 | +0.0000 | 0.9185 | 0 | 8.1s | 50.15% |
| 4 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `1337b1410b71` | `53424c05cacd` | `53424c05cacd` | 0.9185 | 0.8557 | 0.0411 | +0.0000 | 0.9185 | 0 | 8.8s | 59.68% |
| 5 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `b9bc5cc3c029` | `4c01efb18cc0` | `4c01efb18cc0` | 0.9185 | 0.8557 | 0.0411 | +0.0000 | 0.9185 | 0 | 8.7s | 57.65% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — orli_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `d58e03537115` | `bd0c02b4f4fe` | 0.7785 | 0.9357 | +0.1572 | Improved |
| 5 | `d58e03537115` | `bd0c02b4f4fe` | 0.9125 | 0.9263 | +0.0138 | Improved |
| 6 | `d58e03537115` | `bd0c02b4f4fe` | 0.6913 | 0.8557 | +0.1644 | Improved |
| 9 | `d58e03537115` | `bd0c02b4f4fe` | 0.7483 | 0.8959 | +0.1476 | Improved |
| 10 | `d58e03537115` | `bd0c02b4f4fe` | 0.9010 | 0.9788 | +0.0779 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `d58e03537115` | `bd0c02b4f4fe` | 602 ms | 0.06% |

Total winner changes: **1**.
Search completed in **13.7s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — orli_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-032343`
- Calibration schema: `1.1`
- Detector: `orli_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/orli_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ee8d0935ff6892e9e6b60c7e5f15417d4073949`
- Source commit: `cba7f32e6885ec7268c77d35ecc12f79cc6c2bc7`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `27`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `bd0c02b4f4fe`
- Recommended parameter short name: `bd0c02b4f4fe`
- Best observed Avg IoU: `0.9185`
- Avg IoU Success: `0.9185`
- Worst Golden Set page (Min IoU): `0.8557`
- Page-to-page StdDev: `0.0411`
- Calibration evidence: `Medium`
- Dormant parameters: `dilation_fraction`
- Configured zombie parameters: `close_kernel_fraction, fill_holes`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 1680 |
| Parameter sets evaluated | 1680 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 840 (50.0%) |
| Best Avg IoU | 0.9185 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.4106 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 602 ms (0% of search) |
| Near-best coverage (basin; within 0.0010) | 14 (0.8%) |
| Equivalent-best configurations (within 0.0001) | 7 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 16800 | 100.0% | 1h 3m 58s | 1.0× |
| Exhaustive | 1680 | 10.0% | 6m 24s | 10.0× |
| Non-dormant | 24 | 0.1% | 5.5s | 700.0× |
| Low+ | 24 | 0.1% | 5.5s | 700.0× |
| Moderate+ | 2 | 0.0% | 457 ms | 8400.0× |
| Important+ | 2 | 0.0% | 457 ms | 8400.0× |
| Critical | 2 | 0.0% | 457 ms | 8400.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `include_lines` | Critical | 0.9856 | 0.8153 | 50.0% | `1` (0.8153), `0` (0.0000) | current run |
| `page_padding_fraction` | Low | 0.0070 | 0.1039 | 8.3% | `0.16` (0.4569), `0.14` (0.4540), `0.12` (0.4462) | current run |
| `dilation_fraction` | Dormant | 0.0001 | 0.0108 | 20.0% | `0.06` (0.4146), `0.04` (0.4110), `0.03` (0.4100) | current run |
| `minimum_page_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.4077), `0.06` (0.4077), `0.08` (0.4077) | current run |
| `close_kernel_fraction` | Zombie | 0.0000 | 0.0001 | 100.0% | unknown | retained HTH-0001 10,000-set exhaustive-with-zombies calibration (2026-08-18) |
| `fill_holes` | Zombie | 0.0000 | 0.0000 | 100.0% | unknown | retained HTH-0001 10,000-set exhaustive-with-zombies calibration (2026-08-18) |

*Dormant and Zombie are canonical measured effect-size classifications, not synonyms. Retained rows were not varied in this run: their last compatible audited measurements are shown for visibility only and do not contribute to this run's search-space counts, influence calculations, interactions, or winner selection.*

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`dilation_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `include_lines` × `page_padding_fraction` | 0.9997 | 0.0141 | 1680 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.4034 | 0.0000 | 0.9357 | 0.4074 | 50.0% |
| 5 | 0.4445 | 0.0000 | 0.9580 | 0.4468 | 50.0% |
| 6 | 0.3477 | 0.0000 | 0.8557 | 0.3531 | 50.0% |
| 9 | 0.3848 | 0.0000 | 0.8959 | 0.3901 | 50.0% |
| 10 | 0.4578 | 0.0000 | 0.9834 | 0.4591 | 50.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="page-background-pagebackground-2"></a>
<details>
<summary><strong>Page Background (`page_background`)</strong></summary>

**Status:** complete

## Run Information — page_background

### Build Provenance

- Run ID: `run-20260814-140234`
- Detector: `page_background`
- Strategy: `exhaustive`
- Pipeline commit: `f46553b29db4`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-14T13:45:48.927609+00:00`
- Finished: `2026-08-14T14:02:05.861424+00:00`
- Wall-clock elapsed: `16m 17s`
- Est. serial runtime: `4d 3h 13m 52s`
- Effective acceleration: `365.67×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `200001`
- Parameter sets evaluated: `200001`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — page_background

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `b8d9daa2315e` | `unknown` | `afbe81a796a1` | `afbe81a796a1` | 0.9692 | 0.9498 | 0.0171 | 0.9692 | 0 | 2.5s |
| Baseline | `HTH-0001` | `b8d9daa2315e` | `unknown` | `c81fb1ff4213` | `baseline` | 0.7618 | 0.0000 | 0.3812 | 0.9523 | 1 | 196 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`f46553b29db4`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `afbe81a796a1` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `blur_sigma` | `0.0` |
| `border_band_fraction` | `0.015` |
| `close_kernel_fraction` | `0.0` |
| `color_distance_threshold` | `11.5` |
| `minimum_border_background_fraction` | `0.15` |
| `minimum_page_area_fraction` | `0.15` |
| `open_kernel_fraction` | `0.0035` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Outer-border background samples | Primary | Learns robust capture-background color statistics from the image perimeter rather than assuming a white surround. |
| Lab background distance | Generator | Classifies pixels by robust normalized distance from the learned border-background model. |
| Negative-space page region | Geometry | Extracts the dominant plausible non-background region and fits an oriented quadrilateral. |
| Border coherence | Validation | Requires the image perimeter to agree sufficiently with the learned background model before accepting a page proposal. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 11 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 5 | 76 | 380 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `c81fb1ff4213` | `baseline` | 0.7618 | 0.0000 | 0.3812 | -0.2074 | 0.9523 | 1 | reference | reference |
| 1 | unknown | `unknown` | `afbe81a796a1` | `afbe81a796a1` | 0.9692 | 0.9498 | 0.0171 | +0.0000 | 0.9692 | 0 | 18.6s | 2.01% |
| 2 | unknown | `unknown` | `e4fff2a19df5` | `e4fff2a19df5` | 0.9692 | 0.9498 | 0.0171 | +0.0000 | 0.9692 | 0 | 18.8s | 2.03% |
| 3 | unknown | `unknown` | `c083c4c84edd` | `c083c4c84edd` | 0.9692 | 0.9498 | 0.0171 | +0.0000 | 0.9692 | 0 | 19.1s | 2.08% |
| 4 | unknown | `unknown` | `b4cfb123b850` | `b4cfb123b850` | 0.9692 | 0.9498 | 0.0171 | +0.0000 | 0.9692 | 0 | 1m 2s | 7.44% |
| 5 | unknown | `unknown` | `4be5e4c505c3` | `4be5e4c505c3` | 0.9692 | 0.9498 | 0.0171 | +0.0000 | 0.9692 | 0 | 1m 2s | 7.46% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — page_background

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `afbe81a796a1` | 0.9402 | 0.9644 | +0.0242 | Improved |
| 5 | `unknown` | `afbe81a796a1` | 0.9794 | 0.9810 | +0.0016 | Improved |
| 6 | `unknown` | `afbe81a796a1` | 0.0000 | 0.9961 | +0.9961 | Recovered |
| 9 | `unknown` | `afbe81a796a1` | 0.9441 | 0.9498 | +0.0057 | Improved |
| 10 | `unknown` | `afbe81a796a1` | 0.9456 | 0.9550 | +0.0094 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 7 | `unknown` | `6e3e9933273a` | 3.6s | 0.20% |
| 8 | `unknown` | `e804ea5d2a73` | 6s | 0.46% |
| 9 | `unknown` | `bb880d4e0574` | 6.1s | 0.47% |
| 10 | `unknown` | `4198a4f7e82a` | 9.5s | 0.90% |
| 11 (final) | `unknown` | `d0e236bbd3f9` | 17.5s | 1.88% |

Total winner changes: **11**.
Search completed in **16m 17s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — page_background

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260814-140234`
- Calibration schema: `1.1`
- Detector: `page_background`
- Detector configuration: `hth-pipeline/config/detectors/page_background.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `f46553b29db4074bed211c2615059de7a29861ae`
- Source commit: `c521d572cc7561aab42b757527f19ca8c5e5bd2c`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `76`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `afbe81a796a1`
- Recommended parameter short name: `afbe81a796a1`
- Best observed Avg IoU: `0.9692`
- Avg IoU Success: `0.9692`
- Worst Golden Set page (Min IoU): `0.9498`
- Page-to-page StdDev: `0.0171`
- Calibration evidence: `Medium`
- Dormant parameters: `open_kernel_fraction, minimum_border_background_fraction, minimum_page_area_fraction, maximum_page_area_fraction, minimum_rectangularity`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 5 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 107968 of 200001 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 200001 |
| Parameter sets evaluated | 200001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 92033 (46.0%) |
| Best Avg IoU | 0.9692 |
| Minimum Avg IoU | 0.6924 |
| Avg IoU StdDev | 0.1014 |
| Winner stabilized after | 4026 parameter sets |
| Winner stabilized | 18.6s (2% of search) |
| Near-best coverage (basin; within 0.0010) | 1185 (0.6%) |
| Equivalent-best configurations (within 0.0001) | 110 (0.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 200001 | 100.0% | 5d 18h 13m 52s | 1.0× |
| Non-dormant | 25000 | 12.5% | 17h 16m 44s | 8.0× |
| Low+ | 25000 | 12.5% | 17h 16m 44s | 8.0× |
| Moderate+ | 500 | 0.2% | 20m 44s | 400.0× |
| Important+ | 20 | 0.0% | 49.8s | 10000.0× |
| Critical | 20 | 0.0% | 49.8s | 10000.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `border_band_fraction` | Critical | 0.8776 | 0.1988 | 50.0% | `0.015` (0.9534), `0.02` (0.9534), `0.0225` (0.9534) | current run |
| `color_distance_threshold` | Moderate | 0.0411 | 0.0725 | 48.0% | `9.5` (0.8609), `9` (0.8606), `6` (0.8605) | current run |
| `blur_sigma` | Low | 0.0044 | 0.0223 | 90.0% | `0` (0.8543), `0.2` (0.8543), `0.4` (0.8525) | current run |
| `close_kernel_fraction` | Low | 0.0011 | 0.0108 | 100.0% | `0.008` (0.8517), `0.0005` (0.8461), `0.001` (0.8461) | current run |
| `open_kernel_fraction` | Dormant | 0.0003 | 0.0053 | 100.0% | `0` (0.8477), `0.0015` (0.8470), `0.002` (0.8470) | current run |
| `minimum_border_background_fraction` | Dormant | 0.0000 | 0.0843 | 50.0% | `0.15` (0.8462), `0.5` (0.7618) | current run |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0843 | 50.0% | `0.15` (0.8462), `0.25` (0.7618) | current run |
| `maximum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.7618) | current run |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.6` (0.7618) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`open_kernel_fraction`, `minimum_border_background_fraction`, `minimum_page_area_fraction`, `maximum_page_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `border_band_fraction` × `blur_sigma` | 0.9280 | 0.0501 | 40001 |
| `border_band_fraction` × `color_distance_threshold` | 0.9247 | 0.0467 | 40001 |
| `color_distance_threshold` × `blur_sigma` | 0.0485 | 0.0073 | 40001 |
| `color_distance_threshold` × `close_kernel_fraction` | 0.0460 | 0.0049 | 40001 |
| `color_distance_threshold` × `open_kernel_fraction` | 0.0436 | 0.0024 | 40001 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9569 | 0.9243 | 0.9952 | 0.0093 | 100.0% |
| 5 | 0.9146 | 0.5678 | 0.9920 | 0.1126 | 100.0% |
| 6 | 0.4565 | 0.0000 | 0.9991 | 0.4945 | 46.0% |
| 9 | 0.9506 | 0.9317 | 0.9736 | 0.0031 | 100.0% |
| 10 | 0.9523 | 0.9280 | 0.9792 | 0.0049 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="polar-boundary-voting-polarboundaryvote-2"></a>
<details>
<summary><strong>Polar Boundary Voting (`polar_boundary_vote`)</strong></summary>

**Status:** complete

## Run Information — polar_boundary_vote

### Build Provenance

- Run ID: `run-20260815-145118`
- Detector: `polar_boundary_vote`
- Strategy: `exhaustive`
- Pipeline commit: `77e4c24dea27`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-15T14:51:18.322341+00:00`
- Finished: `2026-08-15T15:18:07.442154+00:00`
- Wall-clock elapsed: `26m 49s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `19636`
- Parameter sets evaluated: `19636`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — polar_boundary_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `5fc41309f029` | `unknown` | `935369155754` | `935369155754` | 0.9691 | 0.9524 | 0.0154 | 0.9691 | 0 | 20.7s |
| Baseline | `HTH-0001` | `5fc41309f029` | `unknown` | `cd967f93437d` | `baseline` | 0.9678 | 0.9425 | 0.0182 | 0.9678 | 0 | 49 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`77e4c24dea27`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `935369155754` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.0` |
| `gradient_percentile` | `94.0` |
| `outer_radius_fraction` | `0.6` |
| `ray_count` | `90` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Polar gradient field | Primary | Samples image-gradient evidence along center-outward polar rays. |
| Boundary votes | Generator | Selects strong outer transitions on each ray as page-boundary votes. |
| Ray support | Validation | Requires sufficient angular support before fitting geometry. |
| Minimum-area rectangle | Geometry | Fits the page proposal around the accepted polar votes. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 4 |
| StdDev improvements | 3 |
| Total metric improvements | 8 |
| Parameter sets with improvements | 7 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto-fallback-no-shape-history` | 1 | 384 | 384 | `rh8-al317` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `cd967f93437d` | `baseline` | 0.9678 | 0.9425 | 0.0182 | -0.0013 | 0.9678 | 0 | reference | reference |
| 1 | unknown | `unknown` | `935369155754` | `935369155754` | 0.9691 | 0.9524 | 0.0154 | +0.0000 | 0.9691 | 0 | 3m 21s | 19.79% |
| 2 | unknown | `unknown` | `dd690ba558fc` | `dd690ba558fc` | 0.9690 | 0.9487 | 0.0154 | -0.0001 | 0.9690 | 0 | 26m 37s | 98.87% |
| 3 | unknown | `unknown` | `7cabafc75bc3` | `7cabafc75bc3` | 0.9681 | 0.9483 | 0.0166 | -0.0010 | 0.9681 | 0 | 26m 37s | 98.89% |
| 4 | unknown | `unknown` | `eb72c986992d` | `eb72c986992d` | 0.9676 | 0.9455 | 0.0168 | -0.0015 | 0.9676 | 0 | 18m 56s | 79.59% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — polar_boundary_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `935369155754` | 0.9819 | 0.9684 | -0.0135 | Regressed |
| 5 | `unknown` | `935369155754` | 0.9925 | 0.9942 | +0.0017 | Improved |
| 6 | `unknown` | `935369155754` | 0.9688 | 0.9765 | +0.0077 | Improved |
| 9 | `unknown` | `935369155754` | 0.9425 | 0.9524 | +0.0099 | Improved |
| 10 | `unknown` | `935369155754` | 0.9533 | 0.9541 | +0.0007 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `unknown` | `935369155754` | 3m 21s | 19.79% |

Total winner changes: **1**.
Search completed in **26m 49s** wall-clock time.

**Stabilization Interpretation:** Moderate exploration — the final winner emerged after 10–40% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `935369155754` | 0.9684 | Regressed |

## Calibration Intelligence — polar_boundary_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260815-145118`
- Calibration schema: `1.1`
- Detector: `polar_boundary_vote`
- Detector configuration: `hth-pipeline/config/detectors/polar_boundary_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `77e4c24dea27f3097d7f6f7aafa75b3c3fb6bb7d`
- Source commit: `5bf7e5b7891c636518dde9fbb8379c93a7b3dfdd`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `384`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `935369155754`
- Recommended parameter short name: `935369155754`
- Best observed Avg IoU: `0.9691`
- Avg IoU Success: `0.9691`
- Worst Golden Set page (Min IoU): `0.9524`
- Page-to-page StdDev: `0.0154`
- Calibration evidence: `Medium`
- Dormant parameters: `inner_radius_fraction, minimum_support_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 19636 |
| Parameter sets evaluated | 19636 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 19636 (100.0%) |
| Best Avg IoU | 0.9691 |
| Minimum Avg IoU | 0.6602 |
| Avg IoU StdDev | 0.0410 |
| Winner stabilized after | 3885 parameter sets |
| Winner stabilized | 3m 21s (20% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19636 | 100.0% | 4d 17h 9m 3s | 1.0× |
| Non-dormant | 19635 | 100.0% | 4d 17h 8m 42s | 1.0× |
| Low+ | 19635 | 100.0% | 4d 17h 8m 42s | 1.0× |
| Moderate+ | 357 | 1.8% | 2h 3m 26s | 55.0× |
| Important+ | 357 | 1.8% | 2h 3m 26s | 55.0× |
| Critical | 21 | 0.1% | 7m 16s | 935.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `outer_radius_fraction` | Critical | 0.6383 | 0.0975 | 9.5% | `0.58` (0.9389), `0.59` (0.9389), `0.6` (0.9372) | current run |
| `gradient_percentile` | Important | 0.1934 | 0.0782 | 11.8% | `94` (0.9034), `93` (0.9026), `92` (0.9004) | current run |
| `ray_count` | Low | 0.0034 | 0.0064 | 40.0% | `240` (0.8958), `180` (0.8955), `90` (0.8938) | current run |
| `bbox_padding_fraction` | Low | 0.0012 | 0.0043 | 9.1% | `0.001` (0.8946), `0.002` (0.8946), `0` (0.8946) | current run |
| `inner_radius_fraction` | Dormant | 0.0002 | 0.0000 | 0.0% | `0.06` (0.9678) | current run |
| `minimum_support_fraction` | Dormant | 0.0002 | 0.0000 | 0.0% | `0.25` (0.9678) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`inner_radius_fraction`, `minimum_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_radius_fraction` × `gradient_percentile` | 0.8647 | 0.2264 | 19636 |
| `outer_radius_fraction` × `ray_count` | 0.6650 | 0.0267 | 19636 |
| `outer_radius_fraction` × `bbox_padding_fraction` | 0.6545 | 0.0162 | 19636 |
| `gradient_percentile` × `ray_count` | 0.2083 | 0.0149 | 19636 |
| `gradient_percentile` × `bbox_padding_fraction` | 0.1972 | 0.0037 | 19636 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8575 | 0.4953 | 0.9819 | 0.0664 | 100.0% |
| 5 | 0.9126 | 0.5381 | 0.9952 | 0.0628 | 100.0% |
| 6 | 0.9149 | 0.5503 | 0.9874 | 0.0653 | 100.0% |
| 9 | 0.8754 | 0.5444 | 0.9893 | 0.0523 | 100.0% |
| 10 | 0.9062 | 0.5745 | 0.9918 | 0.0494 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="projective-gradient-vote-projectivegradientvote-2"></a>
<details>
<summary><strong>Projective Gradient Vote (`projective_gradient_vote`)</strong></summary>

**Status:** complete

## Run Information — projective_gradient_vote

### Build Provenance

- Run ID: `run-20260813-152907`
- Detector: `projective_gradient_vote`
- Strategy: `exhaustive`
- Pipeline commit: `a3f40c56b9e1`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-13T15:29:00.733077+00:00`
- Finished: `2026-08-13T15:29:06.789124+00:00`
- Wall-clock elapsed: `6.1s`
- Est. serial runtime: `28m 15s`
- Effective acceleration: `279.83×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `730`
- Parameter sets evaluated: `730`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — projective_gradient_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `196f35b35d3c` | `unknown` | `e536a07cca54` | `e536a07cca54` | 0.5541 | 0.0000 | 0.4546 | 0.9235 | 2 | 2s |
| Baseline | `HTH-0001` | `196f35b35d3c` | `unknown` | `c6d5d9271464` | `baseline` | 0.4474 | 0.0000 | 0.3917 | 0.7457 | 2 | 353 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`a3f40c56b9e1`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `e536a07cca54` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `family_tolerance_degrees` | `10.0` |
| `gaussian_sigma` | `1.8` |
| `gradient_percentile` | `82.0` |
| `minimum_segment_fraction` | `0.24` |
| `minimum_side_support` | `0.08` |
| `orthogonality_tolerance_degrees` | `22.0` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Long line segments | Primary | Finds extended boundary candidates without assuming horizontal or vertical page sides. |
| Sobel gradient support | Scoring | Weights each segment by the image transition carried along it. |
| Orientation families | Geometry | Selects two near-orthogonal side families while allowing opposite sides to converge under perspective. |
| Line intersections | Generator | Builds a projective quadrilateral from opposing members of both families. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 4 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 6 | 64 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `c6d5d9271464` | `baseline` | 0.4474 | 0.0000 | 0.3917 | -0.1067 | 0.7457 | 2 | reference | reference |
| 1 | unknown | `unknown` | `e536a07cca54` | `e536a07cca54` | 0.5541 | 0.0000 | 0.4546 | +0.0000 | 0.9235 | 2 | 5.2s | 75.03% |
| 2 | unknown | `unknown` | `ae1b6cb6726e` | `ae1b6cb6726e` | 0.5541 | 0.0000 | 0.4546 | +0.0000 | 0.9235 | 2 | 5.3s | 78.05% |
| 3 | unknown | `unknown` | `6bc5449b490b` | `6bc5449b490b` | 0.5541 | 0.0000 | 0.4546 | +0.0000 | 0.9235 | 2 | 5.3s | 76.82% |
| 4 | unknown | `unknown` | `336356f67c6a` | `336356f67c6a` | 0.5541 | 0.0000 | 0.4546 | +0.0000 | 0.9235 | 2 | 5.4s | 84.22% |
| 5 | unknown | `unknown` | `608d1c2f6dcd` | `608d1c2f6dcd` | 0.5541 | 0.0000 | 0.4546 | +0.0000 | 0.9235 | 2 | 5.6s | 96.30% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — projective_gradient_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `e536a07cca54` | 0.9069 | 0.9698 | +0.0629 | Improved |
| 5 | `unknown` | `e536a07cca54` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `unknown` | `e536a07cca54` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `unknown` | `e536a07cca54` | 0.8393 | 0.8437 | +0.0045 | Improved |
| 10 | `unknown` | `e536a07cca54` | 0.4910 | 0.9570 | +0.4660 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `0e38b938903c` | 2.2s | 1.23% |
| 2 | `unknown` | `f248b5757196` | 3.3s | 32.37% |
| 3 | `unknown` | `a7b54450371b` | 4.7s | 58.57% |
| 4 (final) | `unknown` | `e388ca75f56f` | 4.9s | 61.73% |

Total winner changes: **4**.
Search completed in **6.1s** wall-clock time.

**Stabilization Interpretation:** Late convergence — the final winner emerged after 40–80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `2`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 5 | `unknown` | `e536a07cca54` | 0.0000 | No polygon found |
| 6 | `unknown` | `e536a07cca54` | 0.0000 | No polygon found |

## Calibration Intelligence — projective_gradient_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260813-152907`
- Calibration schema: `1.1`
- Detector: `projective_gradient_vote`
- Detector configuration: `hth-pipeline/config/detectors/projective_gradient_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `a3f40c56b9e1cae9667c249d3729a8a34075a306`
- Source commit: `12a629cce69ca29d927ee5b8ab72d4e2e8727789`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `64`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `e536a07cca54`
- Recommended parameter short name: `e536a07cca54`
- Best observed Avg IoU: `0.5541`
- Avg IoU Success: `0.9235`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4546`
- Calibration evidence: `Medium`
- Dormant parameters: `angle_bin_degrees, area_weight, bbox_padding_fraction, geometry_weight, maximum_area_fraction, maximum_corner_overshoot_fraction, minimum_area_fraction, support_weight, gradient_percentile, family_tolerance_degrees, minimum_side_support, orthogonality_tolerance_degrees`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 12 of 14 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 730 of 730 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 730 |
| Parameter sets evaluated | 730 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5541 |
| Minimum Avg IoU | 0.1683 |
| Avg IoU StdDev | 0.1555 |
| Winner stabilized after | 547 parameter sets |
| Winner stabilized | 5.2s (75% of search) |
| Near-best coverage (basin; within 0.0010) | 81 (11.1%) |
| Equivalent-best configurations (within 0.0001) | 27 (3.7%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 730 | 100.0% | 24m 43s | 1.0× |
| Non-dormant | 9 | 1.2% | 18.3s | 81.1× |
| Low+ | 9 | 1.2% | 18.3s | 81.1× |
| Moderate+ | 9 | 1.2% | 18.3s | 81.1× |
| Important+ | 9 | 1.2% | 18.3s | 81.1× |
| Critical | 3 | 0.4% | 6.1s | 243.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_segment_fraction` | Critical | 0.5142 | 0.2517 | 33.3% | `0.1` (0.5487), `0.16` (0.5147), `0.24` (0.2969) | current run |
| `gaussian_sigma` | Important | 0.2053 | 0.1628 | 33.3% | `1.8` (0.5515), `0.8` (0.4205), `1.2` (0.3888) | current run |
| `angle_bin_degrees` | Dormant | 0.0000 | 0.0000 | 0.0% | `4` (0.4474) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.15` (0.4474) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0` (0.4474) | current run |
| `geometry_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.3` (0.4474) | current run |
| `maximum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.4474) | current run |
| `maximum_corner_overshoot_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.08` (0.4474) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.18` (0.4474) | current run |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.55` (0.4474) | current run |
| `gradient_percentile` | Dormant | 0.0000 | 0.0003 | 100.0% | `74` (0.4536), `82` (0.4536), `90` (0.4533) | current run |
| `family_tolerance_degrees` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.4535), `24` (0.4535), `16` (0.4535) | current run |
| `minimum_side_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.4535), `0.3` (0.4535), `0.18` (0.4535) | current run |
| `orthogonality_tolerance_degrees` | Dormant | 0.0000 | 0.0000 | 100.0% | `12` (0.4535), `32` (0.4535), `22` (0.4535) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_bin_degrees`, `area_weight`, `bbox_padding_fraction`, `geometry_weight`, `maximum_area_fraction`, `maximum_corner_overshoot_fraction`, `minimum_area_fraction`, `support_weight`, `gradient_percentile`, `family_tolerance_degrees`, `minimum_side_support`, `orthogonality_tolerance_degrees`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_segment_fraction` × `gaussian_sigma` | 1.0000 | 0.4858 | 730 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.7292 | 0.0000 | 0.9698 | 0.3898 | 77.8% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8419 | 0.8393 | 0.8465 | 0.0023 | 100.0% |
| 10 | 0.6965 | 0.0000 | 0.9701 | 0.3998 | 77.8% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="radial-edge-search-radialedge-2"></a>
<details>
<summary><strong>Radial Edge Search (`radial_edge`)</strong></summary>

**Status:** complete

## Run Information — radial_edge

### Build Provenance

- Run ID: `run-20260813-221915`
- Detector: `radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `1000d4a6d7b9`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-13T22:04:48.225122+00:00`
- Finished: `2026-08-13T22:18:15.794430+00:00`
- Wall-clock elapsed: `13m 28s`
- Est. serial runtime: `3d 5h 23m 15s`
- Effective acceleration: `344.98×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `400001`
- Parameter sets evaluated: `400001`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — radial_edge

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `6bd38e1e69c4` | `unknown` | `837321a04ccf` | `837321a04ccf` | 0.9571 | 0.9261 | 0.0183 | 0.9571 | 0 | 773 ms |
| Baseline | `HTH-0001` | `6bd38e1e69c4` | `unknown` | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | 0.9503 | 0 | 56 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`1000d4a6d7b9`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `837321a04ccf` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `gaussian_sigma` | `2.4` |
| `gradient_percentile` | `78.0` |
| `maximum_radius_fraction` | `0.78` |
| `minimum_radius_fraction` | `0.22` |
| `minimum_ray_support` | `0.25` |
| `ray_count` | `144` |
| `rectangularity_weight` | `0.2` |
| `support_weight` | `0.45` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Center-outward rays | Primary | Samples image gradients along radial paths from the document center. |
| Strongest radial transitions | Generator | Selects likely page-boundary points independently on each ray. |
| Minimum-area rectangle | Geometry | Fits a quadrilateral to the supported radial edge points. |
| Ray support | Validation | Rejects candidates when too few directions provide credible boundary evidence. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 7 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 26 | 14 | 364 | `rh8-al316` | 364 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | -0.0068 | 0.9503 | 0 | reference | reference |
| 1 | unknown | `unknown` | `837321a04ccf` | `837321a04ccf` | 0.9571 | 0.9261 | 0.0183 | +0.0000 | 0.9571 | 0 | 12m 42s | 98.78% |
| 2 | unknown | `unknown` | `b619ceda35ed` | `b619ceda35ed` | 0.9571 | 0.9261 | 0.0183 | +0.0000 | 0.9571 | 0 | 12m 42s | 98.78% |
| 3 | unknown | `unknown` | `6db979d1e8c1` | `6db979d1e8c1` | 0.9571 | 0.9261 | 0.0183 | +0.0000 | 0.9571 | 0 | 12m 42s | 98.78% |
| 4 | unknown | `unknown` | `4e2961cac062` | `4e2961cac062` | 0.9571 | 0.9261 | 0.0183 | +0.0000 | 0.9571 | 0 | 12m 42s | 98.78% |
| 5 | unknown | `unknown` | `90610600ab17` | `90610600ab17` | 0.9571 | 0.9261 | 0.0183 | +0.0000 | 0.9571 | 0 | 12m 42s | 98.78% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — radial_edge

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `837321a04ccf` | 0.9466 | 0.9751 | +0.0285 | Improved |
| 5 | `unknown` | `837321a04ccf` | 0.9742 | 0.9764 | +0.0022 | Improved |
| 6 | `unknown` | `837321a04ccf` | 0.9384 | 0.9261 | -0.0123 | Regressed |
| 9 | `unknown` | `837321a04ccf` | 0.9340 | 0.9533 | +0.0194 | Improved |
| 10 | `unknown` | `837321a04ccf` | 0.9582 | 0.9547 | -0.0036 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 3 | `unknown` | `c918f1a9de1b` | 4m 8s | 36.09% |
| 4 | `unknown` | `ed9024291f54` | 4m 28s | 38.49% |
| 5 | `unknown` | `6d70daddda25` | 5m 43s | 49.15% |
| 6 | `unknown` | `84832daf2c97` | 11m 18s | 90.19% |
| 7 (final) | `unknown` | `6fcb3105e05c` | 11m 49s | 93.56% |

Total winner changes: **7**.
Search completed in **13m 28s** wall-clock time.

**Stabilization Interpretation:** No stable optimum — the final winner did not emerge until more than 80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `unknown` | `837321a04ccf` | 0.9261 | Regressed |
| 10 | `unknown` | `837321a04ccf` | 0.9547 | Regressed |

## Calibration Intelligence — radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260813-221915`
- Calibration schema: `1.1`
- Detector: `radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1000d4a6d7b9b8f1bd73682a42f3c26d9ba73f62`
- Source commit: `c3ce5a61fca2d0595cbc4d75f8d1757fabee3c95`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `14`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `837321a04ccf`
- Recommended parameter short name: `837321a04ccf`
- Best observed Avg IoU: `0.9571`
- Avg IoU Success: `0.9571`
- Worst Golden Set page (Min IoU): `0.9261`
- Page-to-page StdDev: `0.0183`
- Calibration evidence: `Medium`
- Dormant parameters: `gradient_percentile, area_weight, maximum_area_fraction, minimum_area_fraction, minimum_ray_support, rectangularity_weight, support_weight`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 7 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 400001 |
| Parameter sets evaluated | 400001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 400001 (100.0%) |
| Best Avg IoU | 0.9571 |
| Minimum Avg IoU | 0.7182 |
| Avg IoU StdDev | 0.0469 |
| Winner stabilized after | 395128 parameter sets |
| Winner stabilized | 12m 42s (99% of search) |
| Near-best coverage (basin; within 0.0010) | 400 (0.1%) |
| Equivalent-best configurations (within 0.0001) | 200 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 400001 | 100.0% | 3d 13h 51m 54s | 1.0× |
| Non-dormant | 2000 | 0.5% | 25m 46s | 200.0× |
| Low+ | 2000 | 0.5% | 25m 46s | 200.0× |
| Moderate+ | 2000 | 0.5% | 25m 46s | 200.0× |
| Important+ | 25 | 0.0% | 19.3s | 16000.0× |
| Critical | 5 | 0.0% | 3.9s | 80000.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `maximum_radius_fraction` | Critical | 0.5481 | 0.0935 | 40.0% | `0.72` (0.9121), `0.78` (0.9065), `0.84` (0.8979) | current run |
| `minimum_radius_fraction` | Important | 0.1192 | 0.0403 | 40.0% | `0.26` (0.9005), `0.22` (0.8981), `0.18` (0.8732) | current run |
| `ray_count` | Moderate | 0.0770 | 0.0368 | 25.0% | `96` (0.8962), `224` (0.8901), `144` (0.8898) | current run |
| `gaussian_sigma` | Moderate | 0.0614 | 0.0398 | 10.0% | `1.6` (0.8921), `2.4` (0.8903), `2` (0.8865) | current run |
| `gradient_percentile` | Dormant | 0.0001 | 0.0018 | 100.0% | `74` (0.8814), `78` (0.8808), `80` (0.8804) | current run |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.35` (0.9503) | current run |
| `maximum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.98` (0.9503) | current run |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.18` (0.9503) | current run |
| `minimum_ray_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8802), `0.35` (0.8802), `0.25` (0.8802) | current run |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8802), `0.3` (0.8802) | current run |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8802), `0.35` (0.8802) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`gradient_percentile`, `area_weight`, `maximum_area_fraction`, `minimum_area_fraction`, `minimum_ray_support`, `rectangularity_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_radius_fraction` × `minimum_radius_fraction` | 0.6895 | 0.1416 | 44445 |
| `maximum_radius_fraction` × `gaussian_sigma` | 0.6532 | 0.1053 | 44445 |
| `maximum_radius_fraction` × `ray_count` | 0.6418 | 0.0939 | 44445 |
| `minimum_radius_fraction` × `ray_count` | 0.2079 | 0.0880 | 44445 |
| `ray_count` × `gaussian_sigma` | 0.1539 | 0.0769 | 44445 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8758 | 0.6585 | 0.9786 | 0.0675 | 100.0% |
| 5 | 0.9265 | 0.7115 | 0.9861 | 0.0580 | 100.0% |
| 6 | 0.7966 | 0.4658 | 0.9542 | 0.1005 | 100.0% |
| 9 | 0.8861 | 0.6453 | 0.9849 | 0.0747 | 100.0% |
| 10 | 0.9158 | 0.7679 | 0.9763 | 0.0534 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="radon-boundary-projection-radonboundary-2"></a>
<details>
<summary><strong>Radon Boundary Projection (`radon_boundary`)</strong></summary>

**Status:** complete

## Run Information — radon_boundary

### Build Provenance

- Run ID: `run-20260812-193240`
- Detector: `radon_boundary`
- Strategy: `exhaustive`
- Pipeline commit: `eea9070116fb`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T19:32:29.835051+00:00`
- Finished: `2026-08-12T19:32:40.233482+00:00`
- Wall-clock elapsed: `10.4s`
- Est. serial runtime: `43m 15s`
- Effective acceleration: `249.58×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `729`
- Parameter sets evaluated: `729`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — radon_boundary

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `72a4caf2b968` | `unknown` | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | 0.4983 | 0 | 2.4s |
| Baseline | `HTH-0001` | `72a4caf2b968` | `unknown` | `f26bbb16c7b6` | `baseline` | 0.4227 | 0.2130 | 0.2863 | 0.4227 | 0 | 181 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`eea9070116fb`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `dd6b2601d568` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `angle_limit_degrees` | `4.0` |
| `angle_step_degrees` | `1.0` |
| `bbox_padding_fraction` | `0.016` |
| `edge_percentile` | `90.0` |
| `minimum_peak_prominence` | `1.25` |
| `projection_smooth_fraction` | `0.006` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Projection-angle integration | Primary | Integrates gradient evidence along candidate orientations and offsets. |
| Opposing projection peaks | Generator | Selects left/right and top/bottom boundary pairs jointly in projection space. |
| Orientation search | Geometry | Searches a bounded skew range before mapping the winning rectangle back to image coordinates. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 5 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-exact-runner` | 7 | 54 | 378 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `f26bbb16c7b6` | `baseline` | 0.4227 | 0.2130 | 0.2863 | -0.0756 | 0.4227 | 0 | reference | reference |
| 1 | unknown | `unknown` | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 2.9s | 6.46% |
| 2 | unknown | `unknown` | `2576db79d995` | `2576db79d995` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 7.4s | 64.84% |
| 3 | unknown | `unknown` | `7e45c62ce0a0` | `7e45c62ce0a0` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 5.7s | 49.04% |
| 4 | unknown | `unknown` | `75b9c212c0c0` | `75b9c212c0c0` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 8.7s | 83.10% |
| 5 | unknown | `unknown` | `bd0668adeb01` | `bd0668adeb01` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 4.5s | 30.22% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — radon_boundary

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `dd6b2601d568` | 0.2480 | 0.2028 | -0.0452 | Regressed |
| 5 | `unknown` | `dd6b2601d568` | 0.4147 | 0.5425 | +0.1278 | Improved |
| 6 | `unknown` | `dd6b2601d568` | 0.9782 | 0.9507 | -0.0275 | Regressed |
| 9 | `unknown` | `dd6b2601d568` | 0.2130 | 0.4144 | +0.2014 | Improved |
| 10 | `unknown` | `dd6b2601d568` | 0.2595 | 0.3809 | +0.1214 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 | `unknown` | `4586c6c3690c` | 2.4s | 0.27% |
| 2 | `unknown` | `c8902d013cc7` | 2.5s | 0.82% |
| 3 | `unknown` | `6635a2bca65b` | 2.6s | 1.79% |
| 4 | `unknown` | `d7abaf98543e` | 2.8s | 5.49% |
| 5 (final) | `unknown` | `dd6b2601d568` | 2.9s | 6.46% |

Total winner changes: **5**.
Search completed in **10.4s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `3`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `dd6b2601d568` | 0.2028 | Poor match; Regressed |
| 6 | `unknown` | `dd6b2601d568` | 0.9507 | Regressed |
| 9 | `unknown` | `dd6b2601d568` | 0.4144 | Poor match |
| 10 | `unknown` | `dd6b2601d568` | 0.3809 | Poor match |

## Calibration Intelligence — radon_boundary

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-193240`
- Calibration schema: `1.1`
- Detector: `radon_boundary`
- Detector configuration: `hth-pipeline/config/detectors/radon_boundary.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `eea9070116fb1cce18838ae0b338cc7b2b4ba8ab`
- Source commit: `bdc14cd41a69c463e090ed4cdbe835c2bc6e1ef6`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `54`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `dd6b2601d568`
- Recommended parameter short name: `dd6b2601d568`
- Best observed Avg IoU: `0.4983`
- Avg IoU Success: `0.4983`
- Worst Golden Set page (Min IoU): `0.2028`
- Page-to-page StdDev: `0.2509`
- Calibration evidence: `Medium`
- Dormant parameters: `angle_step_degrees`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 423 (58.0%) |
| Best Avg IoU | 0.4983 |
| Minimum Avg IoU | 0.0849 |
| Avg IoU StdDev | 0.1216 |
| Winner stabilized after | 47 parameter sets |
| Winner stabilized | 2.9s (6% of search) |
| Near-best coverage (basin; within 0.0010) | 9 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 9 (1.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 28m 52s | 1.0× |
| Non-dormant | 243 | 33.3% | 9m 37s | 3.0× |
| Low+ | 243 | 33.3% | 9m 37s | 3.0× |
| Moderate+ | 9 | 1.2% | 21.4s | 81.0× |
| Important+ | 9 | 1.2% | 21.4s | 81.0× |
| Critical | 9 | 1.2% | 21.4s | 81.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `projection_smooth_fraction` | Critical | 0.5794 | 0.2089 | 33.3% | `0.006` (0.4154), `0.012` (0.3870), `0.024` (0.2065) | current run |
| `minimum_peak_prominence` | Critical | 0.3666 | 0.1633 | 66.7% | `1.05` (0.3959), `1.25` (0.3804), `1.6` (0.2326) | current run |
| `edge_percentile` | Low | 0.0056 | 0.0205 | 33.3% | `90` (0.3491), `75` (0.3312), `82` (0.3286) | current run |
| `angle_limit_degrees` | Low | 0.0040 | 0.0185 | 100.0% | `12` (0.3447), `8` (0.3380), `4` (0.3262) | current run |
| `bbox_padding_fraction` | Low | 0.0036 | 0.0178 | 33.3% | `0.016` (0.3444), `0.008` (0.3378), `0` (0.3267) | current run |
| `angle_step_degrees` | Dormant | 0.0001 | 0.0036 | 66.7% | `0.5` (0.3382), `2` (0.3361), `1` (0.3346) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_step_degrees`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `projection_smooth_fraction` × `minimum_peak_prominence` | 0.9500 | 0.3706 | 729 |
| `minimum_peak_prominence` × `angle_limit_degrees` | 0.3782 | 0.0116 | 729 |
| `projection_smooth_fraction` × `edge_percentile` | 0.5882 | 0.0088 | 729 |
| `minimum_peak_prominence` × `edge_percentile` | 0.3742 | 0.0076 | 729 |
| `projection_smooth_fraction` × `angle_limit_degrees` | 0.5864 | 0.0070 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.1272 | 0.0000 | 0.3315 | 0.1152 | 60.5% |
| 5 | 0.4725 | 0.4141 | 0.5425 | 0.0433 | 100.0% |
| 6 | 0.6639 | 0.0000 | 0.9909 | 0.4413 | 88.9% |
| 9 | 0.1787 | 0.0000 | 0.4144 | 0.1348 | 70.4% |
| 10 | 0.2392 | 0.0000 | 0.4831 | 0.1909 | 61.7% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="ransac-border-fit-ransac-2"></a>
<details>
<summary><strong>RANSAC Border Fit (`ransac`)</strong></summary>

**Status:** complete

## Run Information — ransac

### Build Provenance

- Run ID: `run-20260810-200018`
- Detector: `ransac`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T20:00:18.868655+00:00`
- Finished: `2026-08-10T20:01:49.481171+00:00`
- Wall-clock elapsed: `1m 31s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1458`
- Parameter sets evaluated: `1458`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — ransac

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `unknown` | `unknown` | `9647b030702e` | `9647b030702e` | 0.7541 | 0.3558 | 0.2541 | 0.7541 | 0 | 1s |
| Baseline | `HTH-0001` | `unknown` | `unknown` | `7e367fe3bfd5` | `baseline` | 0.6831 | 0.0000 | 0.3806 | 0.8539 | 1 | 42 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`0ccc635b9a94`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `9647b030702e` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.008` |
| `max_trials` | `200` |
| `minimum_bbox_area_fraction` | `0.1` |
| `minimum_mean_inlier_ratio` | `0.25` |
| `minimum_scan_foreground_fraction` | `0.0125` |
| `residual_threshold_fraction` | `0.014` |
| `scan_samples` | `320` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Scan foreground samples | Primary | Samples likely border evidence along image scans. |
| RANSAC line fitting | Primary | Fits robust page-border models while rejecting outliers. |
| Inlier ratio | Validation | Requires sufficient support for accepted line models. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 10 |
| Minimum IoU improvements | 6 |
| StdDev improvements | 9 |
| Total metric improvements | 25 |
| Parameter sets with improvements | 16 |
| Winner changes | 10 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 1 | 16 | 16 | `rh8-al318` | unknown |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `7e367fe3bfd5` | `baseline` | 0.6831 | 0.0000 | 0.3806 | -0.0710 | 0.8539 | 1 | reference | reference |
| 1 | unknown | `unknown` | `9647b030702e` | `9647b030702e` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 16s | 85.31% |
| 2 | unknown | `unknown` | `d212abf22eb8` | `d212abf22eb8` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 16s | 85.52% |
| 3 | unknown | `unknown` | `90823a3ef18b` | `90823a3ef18b` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 16s | 85.72% |
| 4 | unknown | `unknown` | `4375bb0ee3a5` | `4375bb0ee3a5` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 17s | 86.82% |
| 5 | unknown | `unknown` | `7352e2e44471` | `7352e2e44471` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 17s | 87.30% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — ransac

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `9647b030702e` | 0.9665 | 0.9738 | +0.0072 | Improved |
| 5 | `unknown` | `9647b030702e` | 0.5289 | 0.5490 | +0.0202 | Improved |
| 6 | `unknown` | `9647b030702e` | 0.0000 | 0.3558 | +0.3558 | Recovered |
| 9 | `unknown` | `9647b030702e` | 0.9550 | 0.9373 | -0.0177 | Regressed |
| 10 | `unknown` | `9647b030702e` | 0.9652 | 0.9546 | -0.0106 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 6 | `unknown` | `e5a2730e1b8e` | 34.5s | 40.97% |
| 7 | `unknown` | `f70957e5e192` | 43.8s | 52.02% |
| 8 | `unknown` | `f256461b1f0e` | 52.9s | 63.01% |
| 9 | `unknown` | `6f60c05601a6` | 1m 16s | 84.83% |
| 10 (final) | `unknown` | `9647b030702e` | 1m 16s | 85.31% |

Total winner changes: **10**.
Search completed in **1m 31s** wall-clock time.

**Stabilization Interpretation:** No stable optimum — the final winner did not emerge until more than 80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `1`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `unknown` | `9647b030702e` | 0.3558 | Poor match |
| 9 | `unknown` | `9647b030702e` | 0.9373 | Regressed |
| 10 | `unknown` | `9647b030702e` | 0.9546 | Regressed |

## Calibration Intelligence — ransac

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-200018`
- Calibration schema: `1.1`
- Detector: `ransac`
- Detector configuration: `hth-pipeline/config/detectors/ransac.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `71e4c7704e77fb55d220b547c2443c186fb4b8f1`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `16`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `9647b030702e`
- Recommended parameter short name: `9647b030702e`
- Best observed Avg IoU: `0.7541`
- Avg IoU Success: `0.7541`
- Worst Golden Set page (Min IoU): `0.3558`
- Page-to-page StdDev: `0.2541`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, scan_samples, minimum_scan_foreground_fraction, max_trials`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 4 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 1380 of 1458 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 1458 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 78 (5.3%) |
| Best Avg IoU | 0.7541 |
| Minimum Avg IoU | 0.3643 |
| Avg IoU StdDev | 0.1249 |
| Winner stabilized after | 1243 parameter sets |
| Winner stabilized | 1m 16s (85% of search) |
| Near-best coverage (basin; within 0.0010) | 6 (0.4%) |
| Equivalent-best configurations (within 0.0001) | 6 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1458 | 100.0% | 25m 28s | 1.0× |
| Non-dormant | 27 | 1.9% | 28.3s | 54.0× |
| Low+ | 27 | 1.9% | 28.3s | 54.0× |
| Moderate+ | 9 | 0.6% | 9.4s | 162.0× |
| Important+ | 9 | 0.6% | 9.4s | 162.0× |
| Critical | 3 | 0.2% | 3.1s | 486.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_mean_inlier_ratio` | Critical | 0.7489 | 0.2487 | 33.3% | `0.25` (0.6889), `0.45` (0.6430), `0.65` (0.4402) | current run |
| `residual_threshold_fraction` | Important | 0.1372 | 0.1114 | 33.3% | `0.014` (0.6523), `0.008` (0.5789), `0.004` (0.5408) | current run |
| `bbox_padding_fraction` | Low | 0.0021 | 0.0129 | 33.3% | `0` (0.5956), `0.008` (0.5937), `0.016` (0.5827) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0002 | 0.0033 | 100.0% | `0.1` (0.5918), `0.18` (0.5918), `0.28` (0.5885) | current run |
| `scan_samples` | Dormant | 0.0001 | 0.0031 | 33.3% | `220` (0.5919), `320` (0.5914), `140` (0.5888) | current run |
| `minimum_scan_foreground_fraction` | Dormant | 0.0001 | 0.0028 | 33.3% | `0.02` (0.5917), `0.0125` (0.5915), `0.008` (0.5889) | current run |
| `max_trials` | Dormant | 0.0000 | 0.0001 | 100.0% | `200` (0.5907), `400` (0.5906) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `scan_samples`, `minimum_scan_foreground_fraction`, `max_trials`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_mean_inlier_ratio` × `residual_threshold_fraction` | 0.9913 | 0.2424 | 1458 |
| `minimum_mean_inlier_ratio` × `bbox_padding_fraction` | 0.7511 | 0.0022 | 1458 |
| `residual_threshold_fraction` × `bbox_padding_fraction` | 0.1394 | 0.0022 | 1458 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.7550 | 0.0000 | 0.9869 | 0.4036 | 77.8% |
| 5 | 0.3043 | 0.0000 | 0.5777 | 0.2724 | 55.6% |
| 6 | 0.0155 | 0.0000 | 0.3751 | 0.0659 | 5.3% |
| 9 | 0.9321 | 0.9029 | 0.9559 | 0.0205 | 100.0% |
| 10 | 0.9465 | 0.9188 | 0.9696 | 0.0182 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="segment-supported-polar-voting-segmentsupportedpolarvote-2"></a>
<details>
<summary><strong>Segment-Supported Polar Voting (`segment_supported_polar_vote`)</strong></summary>

**Status:** complete

## Run Information — segment_supported_polar_vote

### Build Provenance

- Run ID: `run-20260814-140845`
- Detector: `segment_supported_polar_vote`
- Strategy: `exhaustive`
- Pipeline commit: `f46553b29db4`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-14T13:45:25.172961+00:00`
- Finished: `2026-08-14T14:08:19.664283+00:00`
- Wall-clock elapsed: `22m 54s`
- Est. serial runtime: `5d 16h 50m 7s`
- Effective acceleration: `358.39×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `180001`
- Parameter sets evaluated: `180001`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — segment_supported_polar_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `04911507316d` | `unknown` | `4546643c94a4` | `4546643c94a4` | 0.9470 | 0.8447 | 0.0536 | 0.9470 | 0 | 2.2s |
| Baseline | `HTH-0001` | `04911507316d` | `unknown` | `92e0158634c3` | `baseline` | 0.6974 | 0.0000 | 0.3602 | 0.8717 | 1 | 501 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`f46553b29db4`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `4546643c94a4` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.0` |
| `gradient_percentile` | `92.0` |
| `inner_radius_fraction` | `0.1` |
| `minimum_segment_length_fraction` | `0.03` |
| `minimum_segment_support_fraction` | `0.1` |
| `minimum_support_fraction` | `0.2` |
| `outer_radius_fraction` | `0.68` |
| `ray_count` | `48` |
| `segment_distance_fraction` | `0.0025` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Hybrid (Polar + LSD)

| Evidence source | Function | Interpretation |
|---|---|---|
| Polar boundary votes | Primary | Generates radial page-boundary hypotheses. |
| Long line segments | Validator | Detects independent straight boundary evidence with OpenCV LSD. |
| Vote-to-segment proximity | Validation | Retains polar votes that lie close to sufficiently long line segments. |
| Minimum-area rectangle | Geometry | Fits the page proposal to segment-supported polar votes. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 7 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-dispatch-optimizer` | 62 | 6 | 372 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `92e0158634c3` | `baseline` | 0.6974 | 0.0000 | 0.3602 | -0.2496 | 0.8717 | 1 | reference | reference |
| 1 | unknown | `unknown` | `4546643c94a4` | `4546643c94a4` | 0.9470 | 0.8447 | 0.0536 | +0.0000 | 0.9470 | 0 | 22.6s | 1.95% |
| 2 | unknown | `unknown` | `25ac83637ef3` | `25ac83637ef3` | 0.9470 | 0.8447 | 0.0536 | +0.0000 | 0.9470 | 0 | 22.5s | 1.94% |
| 3 | unknown | `unknown` | `b2dafb5231b7` | `b2dafb5231b7` | 0.9470 | 0.8447 | 0.0536 | +0.0000 | 0.9470 | 0 | 21.1s | 1.80% |
| 4 | unknown | `unknown` | `0806c90bfc1d` | `0806c90bfc1d` | 0.9467 | 0.8421 | 0.0548 | -0.0003 | 0.9467 | 0 | 12m 26s | 66.96% |
| 5 | unknown | `unknown` | `7bf6dee90187` | `7bf6dee90187` | 0.9467 | 0.8421 | 0.0548 | -0.0003 | 0.9467 | 0 | 12m 28s | 67.16% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — segment_supported_polar_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `4546643c94a4` | 0.7294 | 0.9630 | +0.2336 | Improved |
| 5 | `unknown` | `4546643c94a4` | 0.0000 | 0.9750 | +0.9750 | Recovered |
| 6 | `unknown` | `4546643c94a4` | 0.9767 | 1.0000 | +0.0233 | Improved |
| 9 | `unknown` | `4546643c94a4` | 0.8241 | 0.8447 | +0.0206 | Improved |
| 10 | `unknown` | `4546643c94a4` | 0.9567 | 0.9525 | -0.0042 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 3 | `unknown` | `7731c11510d0` | 2.2s | 0.03% |
| 4 | `unknown` | `1c7e199ebfc3` | 2.2s | 0.04% |
| 5 | `unknown` | `60b61ea9ed02` | 3s | 0.10% |
| 6 | `unknown` | `adda15e6507d` | 4.5s | 0.24% |
| 7 (final) | `unknown` | `b2dafb5231b7` | 21.1s | 1.80% |

Total winner changes: **7**.
Search completed in **22m 54s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 10 | `unknown` | `4546643c94a4` | 0.9525 | Regressed |

## Calibration Intelligence — segment_supported_polar_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260814-140845`
- Calibration schema: `1.1`
- Detector: `segment_supported_polar_vote`
- Detector configuration: `hth-pipeline/config/detectors/segment_supported_polar_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `f46553b29db4074bed211c2615059de7a29861ae`
- Source commit: `c521d572cc7561aab42b757527f19ca8c5e5bd2c`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `6`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `4546643c94a4`
- Recommended parameter short name: `4546643c94a4`
- Best observed Avg IoU: `0.9470`
- Avg IoU Success: `0.9470`
- Worst Golden Set page (Min IoU): `0.8447`
- Page-to-page StdDev: `0.0536`
- Calibration evidence: `Medium`
- Dormant parameters: `segment_distance_fraction, inner_radius_fraction, minimum_segment_support_fraction, minimum_support_fraction, bbox_padding_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 5 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 180001 |
| Parameter sets evaluated | 180001 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 144000 (80.0%) |
| Best Avg IoU | 0.9470 |
| Minimum Avg IoU | 0.5149 |
| Avg IoU StdDev | 0.0991 |
| Winner stabilized after | 3511 parameter sets |
| Winner stabilized | 22.6s (2% of search) |
| Near-best coverage (basin; within 0.0010) | 38 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 180001 | 100.0% | 4d 13h 22m 46s | 1.0× |
| Non-dormant | 5000 | 2.8% | 3h 2m 18s | 36.0× |
| Low+ | 5000 | 2.8% | 3h 2m 18s | 36.0× |
| Moderate+ | 5 | 0.0% | 10.9s | 36000.2× |
| Important+ | 5 | 0.0% | 10.9s | 36000.2× |
| Critical | 5 | 0.0% | 10.9s | 36000.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_segment_length_fraction` | Critical | 0.9390 | 0.2496 | 20.0% | `0.03` (0.9093), `0.0225` (0.9076), `0.015` (0.9040) | current run |
| `outer_radius_fraction` | Low | 0.0153 | 0.0323 | 20.0% | `0.72` (0.8539), `0.74` (0.8531), `0.76` (0.8520) | current run |
| `gradient_percentile` | Low | 0.0021 | 0.0144 | 20.0% | `92` (0.8491), `90` (0.8480), `88` (0.8453) | current run |
| `ray_count` | Low | 0.0010 | 0.0113 | 50.0% | `72` (0.8483), `54` (0.8445), `60` (0.8436) | current run |
| `segment_distance_fraction` | Dormant | 0.0003 | 0.0053 | 66.7% | `0.0035` (0.8434), `0.005` (0.8428), `0.0065` (0.8426) | current run |
| `inner_radius_fraction` | Dormant | 0.0000 | 0.0014 | 100.0% | `0.1` (0.8421), `0.08` (0.8419), `0.12` (0.8416) | current run |
| `minimum_segment_support_fraction` | Dormant | 0.0000 | 0.1441 | 50.0% | `0.1` (0.8415), `0.3` (0.6974) | current run |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.1441 | 50.0% | `0.2` (0.8415), `0.35` (0.6974) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.8415) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`segment_distance_fraction`, `inner_radius_fraction`, `minimum_segment_support_fraction`, `minimum_support_fraction`, `bbox_padding_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_segment_length_fraction` × `outer_radius_fraction` | 0.9727 | 0.0338 | 45001 |
| `minimum_segment_length_fraction` × `gradient_percentile` | 0.9443 | 0.0054 | 45001 |
| `outer_radius_fraction` × `ray_count` | 0.0194 | 0.0049 | 45001 |
| `minimum_segment_length_fraction` × `ray_count` | 0.9434 | 0.0046 | 45001 |
| `outer_radius_fraction` × `gradient_percentile` | 0.0182 | 0.0037 | 45001 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8629 | 0.0014 | 0.9676 | 0.1319 | 100.0% |
| 5 | 0.6598 | 0.0000 | 0.9808 | 0.3706 | 80.0% |
| 6 | 0.9789 | 0.8244 | 1.0000 | 0.0244 | 100.0% |
| 9 | 0.8090 | 0.7134 | 0.8463 | 0.0353 | 100.0% |
| 10 | 0.8968 | 0.7113 | 0.9654 | 0.0388 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="signed-polar-boundary-voting-signedpolarboundaryvote-2"></a>
<details>
<summary><strong>Signed Polar Boundary Voting (`signed_polar_boundary_vote`)</strong></summary>

**Status:** complete

## Run Information — signed_polar_boundary_vote

### Build Provenance

- Run ID: `run-20260814-021729`
- Detector: `signed_polar_boundary_vote`
- Strategy: `exhaustive`
- Pipeline commit: `1000d4a6d7b9`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-13T22:14:57.795133+00:00`
- Finished: `2026-08-14T02:16:22.511762+00:00`
- Wall-clock elapsed: `4h 1m 25s`
- Est. serial runtime: `2d 14h 59m 15s`
- Effective acceleration: `15.65×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `453600`
- Parameter sets evaluated: `453600`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — signed_polar_boundary_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `b85eaa7b71f0` | `unknown` | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.9717 | 0.9506 | 0.0193 | 0.9717 | 0 | 180 ms |
| Baseline | `HTH-0001` | `b85eaa7b71f0` | `unknown` | `839015ab653d` | `baseline` | 0.8483 | 0.7473 | 0.0746 | 0.8483 | 0 | 63 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`1000d4a6d7b9`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `8ddbe5f468cd` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.0` |
| `gradient_percentile` | `95.0` |
| `inner_radius_fraction` | `0.2` |
| `minimum_support_fraction` | `0.35` |
| `outer_radius_fraction` | `0.6` |
| `polarity` | `"absolute"` |
| `ray_count` | `72` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Signed radial gradient | Primary | Measures transition direction as well as magnitude along center-outward rays. |
| Polarity gate | Filtering | Prefers bright-page-to-dark-background, dark-page-to-bright-background, or absolute transitions. |
| Boundary votes | Generator | Selects strong outer polarity-consistent transitions on each ray. |
| Minimum-area rectangle | Geometry | Fits the page proposal around accepted signed polar votes. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 20 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto-fallback-no-shape-history` | 4 | 4 | 16 | `rh8-al307` | 4 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `839015ab653d` | `baseline` | 0.8483 | 0.7473 | 0.0746 | -0.1235 | 0.8483 | 0 | reference | reference |
| 1 | unknown | `unknown` | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.9717 | 0.9506 | 0.0193 | +0.0000 | 0.9717 | 0 | 6m 28s | 3.02% |
| 2 | unknown | `unknown` | `15bd2a879a92` | `15bd2a879a92` | 0.9717 | 0.9506 | 0.0193 | +0.0000 | 0.9717 | 0 | 30m 17s | 13.26% |
| 3 | unknown | `unknown` | `4a506ba2e980` | `4a506ba2e980` | 0.9717 | 0.9506 | 0.0193 | +0.0000 | 0.9717 | 0 | 54m 12s | 23.24% |
| 4 | unknown | `unknown` | `8f86c9091425` | `8f86c9091425` | 0.9717 | 0.9506 | 0.0193 | +0.0000 | 0.9717 | 0 | 2h 58m 38s | 75.06% |
| 5 | unknown | `unknown` | `3523918cd50d` | `3523918cd50d` | 0.9717 | 0.9506 | 0.0193 | +0.0000 | 0.9717 | 0 | 3h 22m 35s | 85.07% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — signed_polar_boundary_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `8ddbe5f468cd` | 0.7957 | 0.9684 | +0.1727 | Improved |
| 5 | `unknown` | `8ddbe5f468cd` | 0.8951 | 0.9930 | +0.0979 | Improved |
| 6 | `unknown` | `8ddbe5f468cd` | 0.9607 | 0.9952 | +0.0344 | Improved |
| 9 | `unknown` | `8ddbe5f468cd` | 0.7473 | 0.9516 | +0.2042 | Improved |
| 10 | `unknown` | `8ddbe5f468cd` | 0.8426 | 0.9506 | +0.1080 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 16 | `unknown` | `dd61f7e45f55` | 1.4s | 0.02% |
| 17 | `unknown` | `95af06a4d558` | 4.1s | 0.07% |
| 18 | `unknown` | `92d3227025bf` | 11.9s | 0.21% |
| 19 | `unknown` | `fdd9de7b6642` | 2m 18s | 1.53% |
| 20 (final) | `unknown` | `8ddbe5f468cd` | 6m 28s | 3.02% |

Total winner changes: **20**.
Search completed in **4h 1m 25s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence — signed_polar_boundary_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260814-021729`
- Calibration schema: `1.1`
- Detector: `signed_polar_boundary_vote`
- Detector configuration: `hth-pipeline/config/detectors/signed_polar_boundary_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1000d4a6d7b9b8f1bd73682a42f3c26d9ba73f62`
- Source commit: `911cc51ebe4f99e595f4968997059b961e7c987f`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `4`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `8ddbe5f468cd`
- Recommended parameter short name: `8ddbe5f468cd`
- Best observed Avg IoU: `0.9717`
- Avg IoU Success: `0.9717`
- Worst Golden Set page (Min IoU): `0.9506`
- Page-to-page StdDev: `0.0193`
- Calibration evidence: `Medium`
- Dormant parameters: `inner_radius_fraction, minimum_support_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 453600 |
| Parameter sets evaluated | 453600 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 453600 (100.0%) |
| Best Avg IoU | 0.9717 |
| Minimum Avg IoU | 0.7926 |
| Avg IoU StdDev | 0.0394 |
| Winner stabilized after | 13680 parameter sets |
| Winner stabilized | 6m 28s (3% of search) |
| Near-best coverage (basin; within 0.0010) | 18 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 6 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 453600 | 100.0% | 22h 37m 14s | 1.0× |
| Non-dormant | 10800 | 2.4% | 32m 19s | 42.0× |
| Low+ | 10800 | 2.4% | 32m 19s | 42.0× |
| Moderate+ | 450 | 0.1% | 1m 21s | 1008.0× |
| Important+ | 9 | 0.0% | 1.6s | 50400.0× |
| Critical | 9 | 0.0% | 1.6s | 50400.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `outer_radius_fraction` | Critical | 0.7674 | 0.1051 | 11.1% | `0.575` (0.9381), `0.6` (0.9355), `0.55` (0.9302) | current run |
| `bbox_padding_fraction` | Moderate | 0.0436 | 0.0230 | 20.0% | `0` (0.9068), `0.002` (0.9041), `0.004` (0.9010) | current run |
| `gradient_percentile` | Moderate | 0.0330 | 0.0245 | 10.0% | `95` (0.9079), `94` (0.9058), `93` (0.9034) | current run |
| `polarity` | Low | 0.0169 | 0.0125 | 33.3% | `absolute` (0.9046), `bright_inside` (0.8973), `dark_inside` (0.8921) | current run |
| `ray_count` | Low | 0.0095 | 0.0099 | 12.5% | `72` (0.9019), `144` (0.9014), `120` (0.9012) | current run |
| `inner_radius_fraction` | Dormant | 0.0000 | 0.0009 | 42.9% | `0.18` (0.8984), `0.1` (0.8983), `0.14` (0.8981) | current run |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8980), `0.25` (0.8980), `0.3` (0.8980) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`inner_radius_fraction`, `minimum_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_radius_fraction` × `bbox_padding_fraction` | 0.8309 | 0.0635 | 45360 |
| `outer_radius_fraction` × `gradient_percentile` | 0.8165 | 0.0491 | 45360 |
| `outer_radius_fraction` × `polarity` | 0.8077 | 0.0402 | 45360 |
| `bbox_padding_fraction` × `gradient_percentile` | 0.0766 | 0.0322 | 45360 |
| `outer_radius_fraction` × `ray_count` | 0.7907 | 0.0233 | 45360 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8902 | 0.7175 | 0.9840 | 0.0537 | 100.0% |
| 5 | 0.9214 | 0.6838 | 0.9962 | 0.0568 | 100.0% |
| 6 | 0.9471 | 0.7115 | 0.9981 | 0.0160 | 100.0% |
| 9 | 0.8391 | 0.7134 | 0.9582 | 0.0738 | 100.0% |
| 10 | 0.8924 | 0.7523 | 0.9714 | 0.0477 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="star-convex-boundary-optimization-starconvex-2"></a>
<details>
<summary><strong>Star-Convex Boundary Optimization (`star_convex`)</strong></summary>

**Status:** complete

## Run Information — star_convex

### Build Provenance

- Run ID: `run-20260812-155453`
- Detector: `star_convex`
- Strategy: `exhaustive`
- Pipeline commit: `4f49196091a4`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T15:54:45.430152+00:00`
- Finished: `2026-08-12T15:54:52.583237+00:00`
- Wall-clock elapsed: `7.2s`
- Est. serial runtime: `32m 46s`
- Effective acceleration: `274.84×`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `729`
- Parameter sets evaluated: `729`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — star_convex

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `360d0d12e0ab` | `unknown` | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | 0.8179 | 0 | 3.8s |
| Baseline | `HTH-0001` | `360d0d12e0ab` | `unknown` | `f914375ada78` | `baseline` | 0.7756 | 0.3969 | 0.2448 | 0.7756 | 0 | 46 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`4f49196091a4`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `024732f5e631` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.0` |
| `maximum_radius_fraction` | `0.6` |
| `minimum_radius_fraction` | `0.16` |
| `minimum_support_fraction` | `0.7` |
| `ray_count` | `360` |
| `smoothing_window` | `1` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Foreground center | Anchor | Estimates an interior anchor from the document mask. |
| Star rays | Primary | Finds the outer supported foreground extent independently along radial directions. |
| Angular smoothing | Optimization | Suppresses isolated radial excursions while preserving star-convex boundary support. |
| Boundary envelope | Geometry | Fits a page quadrilateral around the optimized radial boundary. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 11 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-exact-runner` | 10 | 38 | 380 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `f914375ada78` | `baseline` | 0.7756 | 0.3969 | 0.2448 | -0.0422 | 0.7756 | 0 | reference | reference |
| 1 | unknown | `unknown` | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | +0.0000 | 0.8179 | 0 | 6.8s | 98.76% |
| 2 | unknown | `unknown` | `d1a67626e1a7` | `d1a67626e1a7` | 0.8179 | 0.5367 | 0.1827 | +0.0000 | 0.8179 | 0 | 5.7s | 74.31% |
| 3 | unknown | `unknown` | `fa97b23311b2` | `fa97b23311b2` | 0.8179 | 0.5367 | 0.1827 | +0.0000 | 0.8179 | 0 | 6.6s | 95.88% |
| 4 | unknown | `unknown` | `9e7c1f9b7e79` | `9e7c1f9b7e79` | 0.8166 | 0.5344 | 0.1825 | -0.0013 | 0.8166 | 0 | 6.2s | 82.97% |
| 5 | unknown | `unknown` | `ef8cc5554d87` | `ef8cc5554d87` | 0.8166 | 0.5344 | 0.1825 | -0.0013 | 0.8166 | 0 | 6.4s | 86.81% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — star_convex

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `024732f5e631` | 0.9881 | 0.9761 | -0.0120 | Regressed |
| 5 | `unknown` | `024732f5e631` | 0.5706 | 0.5367 | -0.0339 | Regressed |
| 6 | `unknown` | `024732f5e631` | 0.3969 | 0.6626 | +0.2657 | Improved |
| 9 | `unknown` | `024732f5e631` | 0.9542 | 0.9523 | -0.0020 | Regressed |
| 10 | `unknown` | `024732f5e631` | 0.9683 | 0.9617 | -0.0066 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 7 | `unknown` | `05bb5aa0b671` | 5.3s | 67.72% |
| 8 | `unknown` | `8b82548b32eb` | 5.3s | 68.54% |
| 9 | `unknown` | `e7bf7814121d` | 5.4s | 68.96% |
| 10 | `unknown` | `7ecd223a15dc` | 5.5s | 70.60% |
| 11 (final) | `unknown` | `d1a67626e1a7` | 5.7s | 74.31% |

Total winner changes: **11**.
Search completed in **7.2s** wall-clock time.

**Stabilization Interpretation:** Late convergence — the final winner emerged after 40–80% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `4`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `024732f5e631` | 0.9761 | Regressed |
| 5 | `unknown` | `024732f5e631` | 0.5367 | Regressed |
| 9 | `unknown` | `024732f5e631` | 0.9523 | Regressed |
| 10 | `unknown` | `024732f5e631` | 0.9617 | Regressed |

## Calibration Intelligence — star_convex

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-155453`
- Calibration schema: `1.1`
- Detector: `star_convex`
- Detector configuration: `hth-pipeline/config/detectors/star_convex.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `4f49196091a44d5ca7cfe2269ab7c5a207f6336f`
- Source commit: `1baeee3568bc00f0ccf273e8e318da8ded66e8e0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `38`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `024732f5e631`
- Recommended parameter short name: `024732f5e631`
- Best observed Avg IoU: `0.8179`
- Avg IoU Success: `0.8179`
- Worst Golden Set page (Min IoU): `0.5367`
- Page-to-page StdDev: `0.1827`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_support_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 729 (100.0%) |
| Best Avg IoU | 0.8179 |
| Minimum Avg IoU | 0.7309 |
| Avg IoU StdDev | 0.0213 |
| Winner stabilized after | 719 parameter sets |
| Winner stabilized | 6.8s (99% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (0.4%) |
| Equivalent-best configurations (within 0.0001) | 3 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 46m 14s | 1.0× |
| Non-dormant | 243 | 33.3% | 15m 25s | 3.0× |
| Low+ | 243 | 33.3% | 15m 25s | 3.0× |
| Moderate+ | 27 | 3.7% | 1m 43s | 27.0× |
| Important+ | 3 | 0.4% | 11.4s | 243.0× |
| Critical | 3 | 0.4% | 11.4s | 243.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `smoothing_window` | Critical | 0.6484 | 0.0365 | 33.3% | `1` (0.8009), `9` (0.7645), `5` (0.7644) | current run |
| `maximum_radius_fraction` | Moderate | 0.0970 | 0.0150 | 33.3% | `0.6` (0.7822), `0.72` (0.7803), `0.84` (0.7673) | current run |
| `bbox_padding_fraction` | Moderate | 0.0312 | 0.0084 | 33.3% | `0` (0.7797), `0.008` (0.7788), `0.016` (0.7713) | current run |
| `ray_count` | Low | 0.0171 | 0.0065 | 33.3% | `360` (0.7804), `180` (0.7755), `90` (0.7739) | current run |
| `minimum_radius_fraction` | Low | 0.0053 | 0.0034 | 33.3% | `0.16` (0.7788), `0.05` (0.7756), `0.1` (0.7754) | current run |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.7766), `0.55` (0.7766), `0.7` (0.7766) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `smoothing_window` × `maximum_radius_fraction` | 0.8276 | 0.1793 | 729 |
| `maximum_radius_fraction` × `ray_count` | 0.1744 | 0.0774 | 729 |
| `smoothing_window` × `ray_count` | 0.6890 | 0.0407 | 729 |
| `maximum_radius_fraction` × `bbox_padding_fraction` | 0.1305 | 0.0335 | 729 |
| `smoothing_window` × `bbox_padding_fraction` | 0.6799 | 0.0315 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9437 | 0.8260 | 0.9917 | 0.0502 | 100.0% |
| 5 | 0.5759 | 0.5286 | 0.6053 | 0.0208 | 100.0% |
| 6 | 0.5139 | 0.3465 | 0.8804 | 0.1373 | 100.0% |
| 9 | 0.9260 | 0.8888 | 0.9601 | 0.0244 | 100.0% |
| 10 | 0.9235 | 0.8454 | 0.9738 | 0.0386 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="text-flow-envelope-textflow-2"></a>
<details>
<summary><strong>Text Flow Envelope (`text_flow`)</strong></summary>

**Status:** complete

## Run Information — text_flow

### Build Provenance

- Run ID: `run-20260812-200122`
- Detector: `text_flow`
- Strategy: `exhaustive`
- Pipeline commit: `eea9070116fb`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T20:01:22.669973+00:00`
- Finished: `2026-08-12T20:01:26.124540+00:00`
- Wall-clock elapsed: `3.5s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `729`
- Parameter sets evaluated: `729`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — text_flow

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `161f74b6ff2e` | `unknown` | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | 0.8170 | 4 | 382 ms |
| Baseline | `HTH-0001` | `161f74b6ff2e` | `unknown` | `cd4fbe8ec7d8` | `baseline` | 0.1596 | 0.0000 | 0.3191 | 0.7978 | 4 | 19 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`eea9070116fb`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `a2bbfc162f9e` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.04` |
| `line_join_fraction` | `0.03` |
| `maximum_component_area_fraction` | `0.005` |
| `minimum_component_area_fraction` | `1e-05` |
| `minimum_line_count` | `2` |
| `minimum_text_coverage_fraction` | `0.04` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Ink components | Primary | Extracts writing-sized connected components from the document mask. |
| Text-line grouping | Generator | Joins nearby components into horizontal writing bands. |
| Text envelope | Geometry | Fits an oriented document envelope around the recovered text flow. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 1 |
| Total metric improvements | 2 |
| Parameter sets with improvements | 2 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-exact-runner` | 1 | 384 | 384 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `cd4fbe8ec7d8` | `baseline` | 0.1596 | 0.0000 | 0.3191 | -0.0038 | 0.7978 | 4 | reference | reference |
| 1 | unknown | `unknown` | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.4s | 20.47% |
| 2 | unknown | `unknown` | `919f35cbc4af` | `919f35cbc4af` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.4s | 17.86% |
| 3 | unknown | `unknown` | `e127c712c18d` | `e127c712c18d` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.4s | 14.84% |
| 4 | unknown | `unknown` | `a83d7e03757b` | `a83d7e03757b` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.4s | 1.37% |
| 5 | unknown | `unknown` | `5caa04c23d75` | `5caa04c23d75` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.4s | 44.37% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — text_flow

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `unknown` | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `unknown` | `a2bbfc162f9e` | 0.7978 | 0.8170 | +0.0192 | Improved |
| 9 | `unknown` | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `unknown` | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `unknown` | `b9cf797aedf9` | 2.1s | 0.69% |

Total winner changes: **1**.
Search completed in **3.5s** wall-clock time.

**Stabilization Interpretation:** Early convergence — the final winner emerged within the first 10% of the evaluated search.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `4`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 5 | `unknown` | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 9 | `unknown` | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 10 | `unknown` | `a2bbfc162f9e` | 0.0000 | No polygon found |

## Calibration Intelligence — text_flow

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-200122`
- Calibration schema: `1.1`
- Detector: `text_flow`
- Detector configuration: `hth-pipeline/config/detectors/text_flow.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `eea9070116fb1cce18838ae0b338cc7b2b4ba8ab`
- Source commit: `05558f4a01ba3142555502b7ac352df66660a75f`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `384`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `a2bbfc162f9e`
- Recommended parameter short name: `a2bbfc162f9e`
- Best observed Avg IoU: `0.1634`
- Avg IoU Success: `0.8170`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3268`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_component_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 729 of 729 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.1634 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0609 |
| Winner stabilized after | 149 parameter sets |
| Winner stabilized | 2.4s (20% of search) |
| Near-best coverage (basin; within 0.0010) | 34 (4.7%) |
| Equivalent-best configurations (within 0.0001) | 34 (4.7%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 4m 38s | 1.0× |
| Non-dormant | 243 | 33.3% | 1m 33s | 3.0× |
| Low+ | 243 | 33.3% | 1m 33s | 3.0× |
| Moderate+ | 81 | 11.1% | 30.9s | 9.0× |
| Important+ | 9 | 1.2% | 3.4s | 81.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_line_count` | Important | 0.2257 | 0.0613 | 100.0% | `2` (0.1082), `3` (0.1082), `5` (0.0469) | current run |
| `maximum_component_area_fraction` | Important | 0.1129 | 0.0434 | 100.0% | `0.02` (0.1167), `0.005` (0.0733), `0.01` (0.0733) | current run |
| `minimum_text_coverage_fraction` | Moderate | 0.0879 | 0.0383 | 100.0% | `0.04` (0.1005), `0.08` (0.1005), `0.14` (0.0623) | current run |
| `line_join_fraction` | Moderate | 0.0610 | 0.0367 | 33.3% | `0.05` (0.1051), `0.03` (0.0897), `0.018` (0.0685) | current run |
| `bbox_padding_fraction` | Low | 0.0027 | 0.0077 | 33.3% | `0.04` (0.0919), `0.02` (0.0873), `0.01` (0.0842) | current run |
| `minimum_component_area_fraction` | Dormant | 0.0007 | 0.0035 | 66.7% | `1e-05` (0.0889), `2e-05` (0.0889), `5e-05` (0.0854) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_component_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_line_count` × `line_join_fraction` | 0.4041 | 0.1784 | 729 |
| `maximum_component_area_fraction` × `minimum_text_coverage_fraction` | 0.2448 | 0.1319 | 729 |
| `minimum_line_count` × `minimum_text_coverage_fraction` | 0.3576 | 0.1319 | 729 |
| `maximum_component_area_fraction` × `line_join_fraction` | 0.2364 | 0.1235 | 729 |
| `minimum_line_count` × `maximum_component_area_fraction` | 0.3404 | 0.1147 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.4389 | 0.0000 | 0.8170 | 0.3043 | 70.4% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="whitespace-frame-whitespaceframe-2"></a>
<details>
<summary><strong>Whitespace Frame (`whitespace_frame`)</strong></summary>

**Status:** complete

## Run Information — whitespace_frame

### Build Provenance

- Run ID: `run-20260812-193428`
- Detector: `whitespace_frame`
- Strategy: `exhaustive`
- Pipeline commit: `eea9070116fb`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T19:34:28.978584+00:00`
- Finished: `2026-08-12T19:34:30.305717+00:00`
- Wall-clock elapsed: `1.3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `730`
- Parameter sets evaluated: `730`
- Evaluated sets (% of all possible parameter sets): `100.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — whitespace_frame

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `f39c62493a19` | `unknown` | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 7 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`eea9070116fb`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `unknown` |
| Parameter Set ID (legacy alias) | `9ef715dda063` |
| Absolute parameter SHA-256 | `unavailable (legacy record)` |
| Identity schema | `unknown` |
| Parameter schema | `unknown` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Legacy identity only / exact configuration unavailable** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `background_threshold` | `245` |
| `bbox_padding_fraction` | `0.0` |
| `close_kernel_fraction` | `0.01` |
| `maximum_page_area_fraction` | `0.98` |
| `minimum_border_background_fraction` | `0.55` |
| `minimum_page_area_fraction` | `0.18` |

#### Known Builds Using Equivalent Parameter Sets

Builds known at the time this report was generated; matching is by Parameter Set Equivalence Family ID. Exact Parameter Set IDs are shown to preserve the distinct executable configurations represented within the family.

| Build | Date | Family ID | Parameter Set ID | Evidence |
|---|---|---|---|---|
| current/unknown | unknown | `unknown` | `unknown` | No build provenance was available. |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Border whitespace | Primary | Measures whether the image perimeter is dominated by background. |
| Negative-space segmentation | Generator | Inverts the surrounding whitespace to isolate the enclosed page region. |
| Page envelope | Geometry | Fits an oriented rectangle to the dominant non-background region. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 0 |
| Parameter sets with improvements | 0 |
| Winner changes | 0 |
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile` | 1 | 384 | 384 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | unknown | `unknown` | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | reference | reference |
| 1 | unknown | `unknown` | `f7e0d706deeb` | `f7e0d706deeb` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 826 ms | 64.75% |
| 2 | unknown | `unknown` | `93f2d7e9ecfa` | `93f2d7e9ecfa` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 826 ms | 68.45% |
| 3 | unknown | `unknown` | `f2b82f6c9e72` | `f2b82f6c9e72` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 826 ms | 72.02% |
| 4 | unknown | `unknown` | `051f77f76305` | `051f77f76305` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 823 ms | 62.14% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — whitespace_frame

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `unknown` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `unknown` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `unknown` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `unknown` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `unknown` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **1.3s** wall-clock time.

**Stabilization Interpretation:** Unavailable because the completed-search fraction was not recorded.

### Status Definitions

- **Recovered:** baseline IoU was zero and the winner found a matching polygon.
- **Improved:** Δ IoU is greater than `0.0010`.
- **Unchanged:** Δ IoU is between `-0.0010` and `+0.0010`.
- **Regressed:** Δ IoU is less than `-0.0010`.
- **Poor match:** Winner IoU is greater than zero but below `0.5000`.
- **Zero overlap:** a polygon was returned, but its IoU is zero.
- **No polygon found:** the detector completed without returning a polygon.
- **Unprocessed:** evaluation raised an error.

### Golden Set Page Issues

- Unprocessed pages: `0`
- No polygon found: `5`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `unknown` | `baseline` | 0.0000 | No polygon found |
| 5 | `unknown` | `baseline` | 0.0000 | No polygon found |
| 6 | `unknown` | `baseline` | 0.0000 | No polygon found |
| 9 | `unknown` | `baseline` | 0.0000 | No polygon found |
| 10 | `unknown` | `baseline` | 0.0000 | No polygon found |

## Calibration Intelligence — whitespace_frame

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-193428`
- Calibration schema: `1.1`
- Detector: `whitespace_frame`
- Detector configuration: `hth-pipeline/config/detectors/whitespace_frame.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `eea9070116fb1cce18838ae0b338cc7b2b4ba8ab`
- Source commit: `cdbc61b86a709b08a9f9e97f00b2202a3e8f89ed`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `384`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `9ef715dda063`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.0000`
- Avg IoU Success: `0.0000`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.0000`
- Calibration evidence: `Medium`
- Dormant parameters: `background_threshold, bbox_padding_fraction, close_kernel_fraction, maximum_page_area_fraction, minimum_border_background_fraction, minimum_page_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- Every measured parameter was dormant for this Golden Set and grid.
- Detector failed on at least one Golden Set page for 730 of 730 parameter configurations.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 730 |
| Parameter sets evaluated | 730 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.0000 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 730 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 730 (100.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 730 | 100.0% | 5.1s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `background_threshold` | Dormant | 0.0000 | 0.0000 | 100.0% | `235` (0.0000), `245` (0.0000), `250` (0.0000) | current run |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.0000), `0.008` (0.0000), `0.016` (0.0000) | current run |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.004` (0.0000), `0.01` (0.0000), `0.02` (0.0000) | current run |
| `maximum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.9` (0.0000), `0.96` (0.0000), `0.98` (0.0000) | current run |
| `minimum_border_background_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.0000), `0.55` (0.0000), `0.7` (0.0000) | current run |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0000), `0.18` (0.0000), `0.28` (0.0000) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`background_threshold`, `bbox_padding_fraction`, `close_kernel_fraction`, `maximum_page_area_fraction`, `minimum_border_background_fraction`, `minimum_page_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>

</details>

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="engineering-continuous-improvement"></a>
## Engineering Continuous Improvement

Every completed regression contributes reusable quality and runtime evidence so future document analysis and regression execution can begin from measured history rather than rediscovering prior results.

[↑ Back to Navigation](#table-of-contents)

<a id="calibration-intelligence-persistence"></a>
### Calibration Intelligence Persistence

- `calibration-index.json` retains detector quality, winner, parameter influence, domain-space, page-sensitivity, and calibration-evidence metadata.
- Compatible authoritative calibrations remain preferred over provisional smoke observations.
- Results commit: [64f5f3fa38718b5808b2c6a2471e9904d8634477](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/commit/64f5f3fa38718b5808b2c6a2471e9904d8634477).
- Workflow run: [Open workflow run](https://github.com/dlstupka/hth/actions/runs/32329021133).
- Pipeline repository: [dlstupka/hth](https://github.com/dlstupka/hth).
- Results repository: [dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results).
- Calibration index: [calibration-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/64f5f3fa38718b5808b2c6a2471e9904d8634477/calibration-index.json).
- Runtime index: [runtime-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/64f5f3fa38718b5808b2c6a2471e9904d8634477/runtime-index.json).
- Smoke records are provisional; complete exhaustive full regressions are authoritative.

[↑ Back to Navigation](#table-of-contents)

<a id="runtime-intelligence-persistence"></a>
### Runtime Intelligence Persistence

- `runtime-index.json` retains detector wall-clock time, workload size, threads, pipeline placement, loading strategy, runner characteristics, and scheduler estimates.
- `parallelism-index.json` retains measured shard, pipeline, and thread execution shapes so equivalent workloads can be compared by wall-clock time and effective acceleration.
- Runtime history supports LPT queueing, regression-duration estimates, and future evidence-based thread recommendations.

[↑ Back to Navigation](#table-of-contents)

<a id="engineering-notes"></a>
### Engineering Notes

- Runtime estimates are derived from historical detector measurements and improve as additional compatible regressions are collected.
- Multi-detector execution defaults to Longest Processing Time (LPT) scheduling to reduce the all-detector makespan.
- Detector and parameter-thread recommendations must remain grounded in measured runtime history rather than runner CPU count alone.
- Calibration recommendations evolve from accumulated quality evidence; runtime recommendations evolve independently from accumulated execution evidence.
- Estimates and recommendations are specific to the Golden Set, detector configuration, parameter grid, strategy, thread count, and runner characteristics represented by the stored observations.


[↑ Back to Navigation](#table-of-contents)