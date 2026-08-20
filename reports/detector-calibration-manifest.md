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
    - [Doc-UFCN Page-Mask Detector (`doc_ufcn_page_mask`)](#doc-ufcn-page-mask-detector-docufcnpagemask)
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
    - [Orli Page Mask (`orli_page_mask`)](#orli-page-mask-orlipagemask)
    - [Contour Quadrilateral (`contour_quad`)](#contour-quadrilateral-contourquad)
    - [Learned Page-Mask Detector (`learned_page_mask`)](#learned-page-mask-detector-learnedpagemask)
    - [GrabCut + Contour (`grabcut_contour`)](#grabcut-contour-grabcutcontour)
    - [Edge-Supported Contour (`edge_contour`)](#edge-supported-contour-edgecontour)
    - [Cross-Edge Contour (`cross_edge_contour`)](#cross-edge-contour-crossedgecontour)
    - [Contour + Projection (`contour_projection`)](#contour-projection-contourprojection)
    - [Contour + GrabCut (`contour_grabcut`)](#contour-grabcut-contourgrabcut)
    - [Contour + Components (`contour_components`)](#contour-components-contourcomponents)
    - [Contour Envelope (`contour`)](#contour-envelope-contour)
    - [Kraken Page Mask (`kraken_page_mask`)](#kraken-page-mask-krakenpagemask)
    - [GrabCut Segmentation (`grabcut`)](#grabcut-segmentation-grabcut)
    - [Distance Transform Detector (`distance_transform`)](#distance-transform-detector-distancetransform)
    - [Star-Convex Boundary Optimization (`star_convex`)](#star-convex-boundary-optimization-starconvex)
    - [Connected Components (`components`)](#connected-components-components)
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
    - [RANSAC Border Fit (`ransac`)](#ransac-border-fit-ransac)
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

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

This recommendation is specific to the evaluated Golden Set and parameter grid and should be revisited when the Golden Set, parameter grid, or source document changes.

[↑ Back to Navigation](#table-of-contents)

<a id="ranked-detector-smoke-test-results"></a>
## Ranked Detector Smoke Test Results

| Rank | Detector | Detector ID | Role | Golden Set ID | Status | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Parameter Sets | Eval Rate | Doc Time | Run Elapsed |
|---:|---|---|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | Adaptive Multi-Scale Radial Edge Search | `adaptive_multi_scale_radial_edge` | Generator | `HTH-0001` | complete | `21ea516c3c5a` | `21ea516c3c5a` | `21ea516c3c5a` | 0.9781 | 0.9564 | 0.0182 | 0.9781 | 0 | 11 | 6.594 pg/s | 2m 21s | 6.4s |
| 2 | Multi-Scale Radial Edge Search | `multi_scale_radial_edge` | Generator | `HTH-0001` | complete | `ddb7623ebb92` | `ddb7623ebb92` | `ddb7623ebb92` | 0.9765 | 0.9566 | 0.0175 | 0.9765 | 0 | 11 | 1.615 pg/s | 9m 35s | 10.3s |
| 3 | Fusion Gen1 — MSRE + BFQ + SPBV + Page Background | `msre_bfq_spbv_pbg` | Hybrid (MSRE + BFQ + SPBV + Page Background) | `HTH-0001` | complete | `7b7dbac43ea6` | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9747 | 0.9638 | 0.0101 | 0.9747 | 0 | 11 | 1.008 pg/s | 15m 22s | 53.7s |
| 4 | Doc-UFCN Page-Mask Detector | `doc_ufcn_page_mask` | Generator | `HTH-0001` | complete | `595002645fcc` | `595002645fcc` | `595002645fcc` | 0.9747 | 0.9545 | 0.0119 | 0.9747 | 0 | 11 | 33.22 pg/s | 28s | 23.2s |
| 5 | Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background | `amsre_bfq_spbv_pbg` | Hybrid (AMSRE + BFQ + SPBV + Page Background) | `HTH-0001` | complete | `156ff0241cc1` | `156ff0241cc1` | `baseline` | 0.9743 | 0.9638 | 0.0103 | 0.9743 | 0 | 10 | 0.6844 pg/s | 22m 37s | 1m 7s |
| 6 | dhSegment Page-Mask Detector | `dhsegment_page_mask` | Generator | `HTH-0001` | complete | `15434712cddf` | `15434712cddf` | `15434712cddf` | 0.9735 | 0.9634 | 0.0100 | 0.9735 | 0 | 11 | 26.73 pg/s | 34.8s | 34s |
| 7 | Adaptive Radial Edge Search | `adaptive_radial_edge` | Generator | `HTH-0001` | complete | `bcd9a1d083cf` | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9726 | 0.9557 | 0.0159 | 0.9726 | 0 | 11 | 4.995 pg/s | 3m 6s | 19s |
| 8 | Signed Polar Boundary Voting | `signed_polar_boundary_vote` | Generator | `HTH-0001` | complete | `8ddbe5f468cd` | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.9717 | 0.9506 | 0.0193 | 0.9717 | 0 | 11 | 38.66 pg/s | 24s | 4.2s |
| 9 | Border Fusion Quad | `border_fusion_quad` | Hybrid (Radial + Polar + Gradient) | `HTH-0001` | complete | `2370e6cea486` | `2370e6cea486` | `2370e6cea486` | 0.9707 | 0.9588 | 0.0112 | 0.9707 | 0 | 11 | 5.147 pg/s | 3m | 11.5s |
| 10 | Page Background | `page_background` | Generator | `HTH-0001` | complete | `afbe81a796a1` | `afbe81a796a1` | `afbe81a796a1` | 0.9692 | 0.9498 | 0.0171 | 0.9692 | 0 | 11 | 11.95 pg/s | 1m 18s | 8.3s |
| 11 | Polar Boundary Voting | `polar_boundary_vote` | Generator | `HTH-0001` | complete | `935369155754` | `935369155754` | `935369155754` | 0.9691 | 0.9524 | 0.0154 | 0.9691 | 0 | 11 | 41.34 pg/s | 22.5s | 2.4s |
| 12 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | complete | `cf581d27715b` | `cf581d27715b` | `cf581d27715b` | 0.9622 | 0.9384 | 0.0160 | 0.9622 | 0 | 11 | 46.60 pg/s | 19.9s | 1.2s |
| 13 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | complete | `837321a04ccf` | `837321a04ccf` | `837321a04ccf` | 0.9571 | 0.9261 | 0.0183 | 0.9571 | 0 | 11 | 34.80 pg/s | 26.7s | 4s |
| 14 | Segment-Supported Polar Voting | `segment_supported_polar_vote` | Hybrid (Polar + LSD) | `HTH-0001` | complete | `4546643c94a4` | `4546643c94a4` | `4546643c94a4` | 0.9470 | 0.8447 | 0.0536 | 0.9470 | 0 | 11 | 7.351 pg/s | 2m 6s | 7.4s |
| 15 | Orli Page Mask | `orli_page_mask` | Generator | `HTH-0001` | complete | `d58e03537115` | `bd0c02b4f4fe` | `bd0c02b4f4fe` | 0.9185 | 0.8557 | 0.0411 | 0.9185 | 0 | 11 | 10.32 pg/s | 1m 30s | 7.5s |
| 16 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | complete | `49095b866d0d` | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | 0.8874 | 0 | 11 | 11.46 pg/s | 1m 21s | 3.5s |
| 17 | Learned Page-Mask Detector | `learned_page_mask` | Generator | `HTH-0001` | complete | `275078578cee` | `275078578cee` | `275078578cee` | 0.8868 | 0.8122 | 0.0470 | 0.8868 | 0 | 11 | 0.5560 pg/s | 27m 51s | 1m 21s |
| 18 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | complete | `3a1623be3b6e` | `3a1623be3b6e` | `3a1623be3b6e` | 0.8772 | 0.7198 | 0.0893 | 0.8772 | 0 | 11 | 0.1159 pg/s | 2h 13m 33s | 1m 47s |
| 19 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | complete | `4e5bc37a649a` | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 11 | 7.205 pg/s | 2m 9s | 8.1s |
| 20 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | complete | `a5450e58ec9e` | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 10 | 5.164 pg/s | 3m | 8.1s |
| 21 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | complete | `0cd13eb1a471` | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 10 | 2.832 pg/s | 5m 28s | 15.7s |
| 22 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | complete | `3eec8a03f1de` | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 10 | 0.1710 pg/s | 1h 30m 34s | 41.6s |
| 23 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | complete | `14818b491952` | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | 10 | 16.33 pg/s | 56.9s | 5.1s |
| 24 | Contour Envelope | `contour` | Generator | `HTH-0001` | complete | `7aed2fc501c5` | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | 11 | 131.36 pg/s | 7.1s | 959 ms |
| 25 | Kraken Page Mask | `kraken_page_mask` | Generator | `HTH-0001` | complete | `c4845fd6c6b6` | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8396 | 0.5596 | 0.1531 | 0.8396 | 0 | 11 | 112.09 pg/s | 8.3s | 3m 15s |
| 26 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | complete | `110867d137a9` | `110867d137a9` | `110867d137a9` | 0.8394 | 0.6041 | 0.1440 | 0.8394 | 0 | 11 | 0.1467 pg/s | 1h 45m 34s | 1m 28s |
| 27 | Distance Transform Detector | `distance_transform` | Generator | `HTH-0001` | complete | `e66a7546e1a7` | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | 0.8388 | 0 | 11 | 5.720 pg/s | 2m 42s | 7.9s |
| 28 | Star-Convex Boundary Optimization | `star_convex` | Generator | `HTH-0001` | complete | `024732f5e631` | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | 0.8179 | 0 | 11 | 59.27 pg/s | 15.7s | 775 ms |
| 29 | Connected Components | `components` | Generator | `HTH-0001` | complete | `f1929c8e2655` | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | 0.7897 | 0 | 11 | 211.51 pg/s | 4.4s | 1.1s |
| 30 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | complete | `7546c5067527` | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | 0.9222 | 1 | 11 | 3.070 pg/s | 5m 3s | 7.4s |
| 31 | Convex Hull Detector | `convex_hull` | Generator | `HTH-0001` | complete | `04fd0a6e4bc2` | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | 0.9156 | 1 | 11 | 384.64 pg/s | 2.4s | 998 ms |
| 32 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | complete | `74e2112aac01` | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | 0.9063 | 1 | 11 | 4.094 pg/s | 3m 47s | 11.1s |
| 33 | Distance-Transform Rectangle Proposal | `distance_transform_rect` | Generator | `HTH-0001` | complete | `0a8482550c35` | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | 0.7243 | 0 | 11 | 36.12 pg/s | 25.7s | 2s |
| 34 | Hough Line Borders | `hough` | Generator | `HTH-0001` | complete | `c2c117479e3f` | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | 0.7563 | 1 | 11 | 3.391 pg/s | 4m 34s | 5.3s |
| 35 | Projective Gradient Vote | `projective_gradient_vote` | Generator | `HTH-0001` | complete | `e536a07cca54` | `e536a07cca54` | `e536a07cca54` | 0.5541 | 0.0000 | 0.4546 | 0.9235 | 2 | 11 | 5.909 pg/s | 2m 37s | 6.2s |
| 36 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | complete | `f387da7ebb7e` | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | 0.9213 | 2 | 11 | 8.683 pg/s | 1m 47s | 3s |
| 37 | Radon Boundary Projection | `radon_boundary` | Generator | `HTH-0001` | complete | `dd6b2601d568` | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | 0.4983 | 0 | 11 | 8.092 pg/s | 1m 55s | 8.6s |
| 38 | Joint Rectangle Voting | `joint_rectangle_vote` | Generator | `HTH-0001` | complete | `5c9509e05f14` | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | 0.9899 | 4 | 11 | 11.27 pg/s | 1m 22s | 8.7s |
| 39 | Text Flow Envelope | `text_flow` | Generator | `HTH-0001` | complete | `a2bbfc162f9e` | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | 0.8170 | 4 | 11 | 114.51 pg/s | 8.1s | 969 ms |
| 40 | Whitespace Frame | `whitespace_frame` | Generator | `HTH-0001` | complete | `9ef715dda063` | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 10 | 192.40 pg/s | 4.8s | 752 ms |
| 41 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | complete | `7e367fe3bfd5` | `7e367fe3bfd5` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 11 | 28.01 pg/s | 33.2s | 3s |

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
| 4 | Doc-UFCN Page-Mask Detector | `doc_ufcn_page_mask` | Generator | `HTH-0001` | 2026-08-20 | [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | 8.8s | `595002645fcc` | `595002645fcc` | 2000 | exhaustive | 100.0% | 0.9747 | 0.9545 | 0.0119 | 0.9747 | 0 | +0.0841 | 10.0% | 10.0% | High | Approved |
| 5 | Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background | `amsre_bfq_spbv_pbg` | Hybrid (AMSRE + BFQ + SPBV + Page Background) | `HTH-0001` | 2026-08-15 | [#428](https://github.com/dlstupka/hth/actions/runs/31899010020) | 1h 18m 41s | `unknown` | `156ff0241cc1` | 50177 | exhaustive | 99.4% | 0.9743 | 0.9638 | 0.0103 | 0.9743 | 0 | +0.0000 | 90.2% | 61.6% | High | Approved |
| 6 | dhSegment Page-Mask Detector | `dhsegment_page_mask` | Generator | `HTH-0001` | 2026-08-16 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | 13m 37s | `unknown` | `15434712cddf` | 10000 | exhaustive | 100.0% | 0.9735 | 0.9634 | 0.0100 | 0.9735 | 0 | +0.0065 | 7.7% | 1.3% | High | Approved |
| 7 | Adaptive Radial Edge Search | `adaptive_radial_edge` | Generator | `HTH-0001` | 2026-08-13 | [#370](https://github.com/dlstupka/hth/actions/runs/31748441601) | 1h 8m 48s | `unknown` | `bcd9a1d083cf` | 750001 | exhaustive | 100.0% | 0.9726 | 0.9557 | 0.0159 | 0.9726 | 0 | +0.0397 | 0.0% | 0.0% | Medium | Recommended |
| 8 | Signed Polar Boundary Voting | `signed_polar_boundary_vote` | Generator | `HTH-0001` | 2026-08-13 | [#374](https://github.com/dlstupka/hth/actions/runs/31748657986) | 4h 1m 25s | `unknown` | `8ddbe5f468cd` | 453600 | exhaustive | 100.0% | 0.9717 | 0.9506 | 0.0193 | 0.9717 | 0 | +0.1235 | 0.0% | 0.0% | Medium | Recommended |
| 9 | Border Fusion Quad | `border_fusion_quad` | Hybrid (Radial + Polar + Gradient) | `HTH-0001` | 2026-08-13 | [#372](https://github.com/dlstupka/hth/actions/runs/31748550347) | 11h 28m 47s | `unknown` | `2370e6cea486` | 539001 | exhaustive | 99.1% | 0.9707 | 0.9588 | 0.0112 | 0.9707 | 0 | +0.0817 | 5.4% | 0.8% | High | Approved |
| 10 | Page Background | `page_background` | Generator | `HTH-0001` | 2026-08-14 | [#383](https://github.com/dlstupka/hth/actions/runs/31806184641) | 16m 17s | `unknown` | `afbe81a796a1` | 200001 | exhaustive | 46.0% | 0.9692 | 0.9498 | 0.0171 | 0.9692 | 0 | +0.2074 | 0.6% | 0.1% | Medium | Recommended |
| 11 | Polar Boundary Voting | `polar_boundary_vote` | Generator | `HTH-0001` | 2026-08-15 | [#416](https://github.com/dlstupka/hth/actions/runs/31891034843) | 26m 49s | `unknown` | `935369155754` | 19636 | exhaustive | 100.0% | 0.9691 | 0.9524 | 0.0154 | 0.9691 | 0 | +0.0013 | 0.0% | 0.0% | Medium | Recommended |
| 12 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | 2026-08-15 | [#421](https://github.com/dlstupka/hth/actions/runs/31891526961) | 809 ms | `unknown` | `cf581d27715b` | 22 | exhaustive | 54.5% | 0.9622 | 0.9384 | 0.0160 | 0.9622 | 0 | +0.0155 | 18.2% | 13.6% | Medium | Recommended |
| 13 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | 2026-08-13 | [#369](https://github.com/dlstupka/hth/actions/runs/31748401024) | 13m 28s | `unknown` | `837321a04ccf` | 400001 | exhaustive | 100.0% | 0.9571 | 0.9261 | 0.0183 | 0.9571 | 0 | +0.0068 | 0.1% | 0.0% | Medium | Recommended |
| 14 | Segment-Supported Polar Voting | `segment_supported_polar_vote` | Hybrid (Polar + LSD) | `HTH-0001` | 2026-08-14 | [#382](https://github.com/dlstupka/hth/actions/runs/31806152306) | 22m 54s | `unknown` | `4546643c94a4` | 180001 | exhaustive | 80.0% | 0.9470 | 0.8447 | 0.0536 | 0.9470 | 0 | +0.2496 | 0.0% | 0.0% | Medium | Recommended |
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
- **Build*:** `#run` links open GitHub Actions logs and artifacts and expire according to repository retention; the calibration data persists in [calibration-intelligence.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/7e7b3e8c70ab792907b2748db67088db033f9203/source-documents/baptisms-san-antonio-baptism-records-1788-1824-1858-1898/golden-sets/hth-0001/135c0ff57687/calibrations/adaptive_multi_scale_radial_edge/run-20260815-155156/calibration-intelligence.json).
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

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50001 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 10h 31m 45s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9781 |
| Minimum Avg IoU | 0.9701 |
| Avg IoU StdDev | 0.0026 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.5s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50000 | 100.0% | 10h 31m 52s | 1.0× |
| Exhaustive | 50000 | 100.0% | 10h 31m 52s | 1.0× |
| Non-dormant | 180 | 0.4% | 2m 16s | 277.8× |
| Low+ | 180 | 0.4% | 2m 16s | 277.8× |
| Moderate+ | 180 | 0.4% | 2m 16s | 277.8× |
| Important+ | 180 | 0.4% | 2m 16s | 277.8× |
| Critical | 180 | 0.4% | 2m 16s | 277.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `weak_side_support_fraction` | Critical | 0.8819 | 0.0070 | 33.3% | `0.65` (0.9781), `0.45` (0.9767), `0.3` (0.9711) | current run |
| `coarse_angle_step_degrees` | Critical | 0.8706 | 0.0063 | 50.0% | `2.04545` (0.9774), `1.85` (0.9711) | current run |
| `refined_angle_step_degrees` | Critical | 0.8706 | 0.0063 | 50.0% | `0.35` (0.9774), `0.25` (0.9711) | current run |
| `maximum_refined_sides` | Critical | 0.5469 | 0.0044 | 20.0% | `4` (0.9745), `3` (0.9741), `2` (0.9713) | current run |
| `side_assignment_tolerance_fraction` | Critical | 0.3994 | 0.0060 | 33.3% | `0.015` (0.9767), `0.0075` (0.9725), `0.01` (0.9707) | current run |
| `area_weight` | Critical | 0.2718 | 0.0000 | 0.0% | `0.2` (0.9767) | current run |
| `base_sigma` | Critical | 0.2718 | 0.0000 | 0.0% | `1` (0.9767) | current run |
| `bbox_padding_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0` (0.9767) | current run |
| `gradient_percentile` | Critical | 0.2718 | 0.0000 | 0.0% | `96.875` (0.9767) | current run |
| `maximum_area_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0.98` (0.9767) | current run |
| `maximum_radius_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0.78` (0.9767) | current run |
| `minimum_area_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0.18` (0.9767) | current run |
| `minimum_radius_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0.16` (0.9767) | current run |
| `minimum_ray_support` | Critical | 0.2718 | 0.0000 | 0.0% | `0.36` (0.9767) | current run |
| `scale_count` | Critical | 0.2718 | 0.0000 | 0.0% | `4` (0.9767) | current run |
| `scale_ratio` | Critical | 0.2718 | 0.0000 | 0.0% | `3.5` (0.9767) | current run |
| `strength_weight` | Critical | 0.2718 | 0.0000 | 0.0% | `0.3` (0.9767) | current run |
| `support_weight` | Critical | 0.2718 | 0.0000 | 0.0% | `0.5` (0.9767) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_refined_sides` × `side_assignment_tolerance_fraction` | 0.7790 | 0.2321 | 11 |
| `coarse_angle_step_degrees` × `maximum_refined_sides` | 0.9846 | 0.1141 | 11 |
| `refined_angle_step_degrees` × `maximum_refined_sides` | 0.9846 | 0.1141 | 11 |
| `weak_side_support_fraction` × `maximum_refined_sides` | 0.9846 | 0.1027 | 11 |
| `coarse_angle_step_degrees` × `side_assignment_tolerance_fraction` | 0.8948 | 0.0242 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9771 | 0.9751 | 0.9841 | 0.0023 | 100.0% |
| 5 | 0.9774 | 0.9685 | 0.9973 | 0.0100 | 100.0% |
| 6 | 0.9948 | 0.9932 | 0.9960 | 0.0010 | 100.0% |
| 9 | 0.9559 | 0.9557 | 0.9566 | 0.0003 | 100.0% |
| 10 | 0.9560 | 0.9558 | 0.9573 | 0.0004 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="multi-scale-radial-edge-search-multiscaleradialedge"></a>
<details>
<summary><strong>Multi-Scale Radial Edge Search (`multi_scale_radial_edge`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 48335 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 1d 17h 34m 9s |
| Fully successful parameter sets | 9 (90.0%) |
| Best Avg IoU | 0.9020 |
| Minimum Avg IoU | 0.4733 |
| Avg IoU StdDev | 0.1379 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 3.9s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (20.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 48334 | 100.0% | 1d 17h 34m 37s | 1.0× |
| Exhaustive | 48334 | 100.0% | 1d 17h 34m 37s | 1.0× |
| Non-dormant | 18 | 0.0% | 55.7s | 2685.2× |
| Low+ | 18 | 0.0% | 55.7s | 2685.2× |
| Moderate+ | 18 | 0.0% | 55.7s | 2685.2× |
| Important+ | 18 | 0.0% | 55.7s | 2685.2× |
| Critical | 18 | 0.0% | 55.7s | 2685.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_percentile` | Critical | 0.9159 | 0.3393 | 22.2% | `94.375` (0.9020), `94` (0.9018), `95.25` (0.9003) | current run |
| `ray_count` | Critical | 0.1597 | 0.1837 | 50.0% | `64` (0.8357), `144` (0.6520) | current run |
| `area_weight` | Critical | 0.1437 | 0.0000 | 0.0% | `0.2` (0.6520) | current run |
| `bbox_padding_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0` (0.6520) | current run |
| `maximum_area_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0.98` (0.6520) | current run |
| `maximum_radius_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0.78` (0.6520) | current run |
| `minimum_area_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0.18` (0.6520) | current run |
| `minimum_radius_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0.16` (0.6520) | current run |
| `minimum_ray_support` | Critical | 0.1437 | 0.0000 | 0.0% | `0.36` (0.6520) | current run |
| `strength_weight` | Critical | 0.1437 | 0.0000 | 0.0% | `0.3` (0.6520) | current run |
| `support_weight` | Critical | 0.1437 | 0.0000 | 0.0% | `0.5` (0.6520) | current run |
| `base_sigma` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.8` (0.8173) | current run |
| `scale_count` | Zombie | 0.0000 | 0.0000 | 100.0% | `3` (0.8173) | current run |
| `scale_ratio` | Zombie | 0.0000 | 0.0000 | 100.0% | `2` (0.8173) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `gradient_percentile` × `ray_count` | 1.0000 | 0.0841 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8200 | 0.3625 | 0.8950 | 0.1620 | 100.0% |
| 5 | 0.8821 | 0.6844 | 0.9741 | 0.1010 | 100.0% |
| 6 | 0.6182 | 0.3345 | 0.7318 | 0.1738 | 100.0% |
| 9 | 0.8274 | 0.0000 | 0.9585 | 0.2942 | 90.0% |
| 10 | 0.9389 | 0.8546 | 0.9567 | 0.0326 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="fusion-gen1-msre-bfq-spbv-page-background-msrebfqspbvpbg"></a>
<details>
<summary><strong>Fusion Gen1 — MSRE + BFQ + SPBV + Page Background (`msre_bfq_spbv_pbg`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50176 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 2d 21h 7m 37s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9747 |
| Minimum Avg IoU | 0.9703 |
| Avg IoU StdDev | 0.0016 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 10.3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (18.2%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50176 | 100.0% | 2d 21h 8m 32s | 1.0× |
| Exhaustive | 50176 | 100.0% | 2d 21h 8m 32s | 1.0× |
| Non-dormant | 33 | 0.1% | 2m 44s | 1520.5× |
| Low+ | 33 | 0.1% | 2m 44s | 1520.5× |
| Moderate+ | 33 | 0.1% | 2m 44s | 1520.5× |
| Important+ | 33 | 0.1% | 2m 44s | 1520.5× |
| Critical | 33 | 0.1% | 2m 44s | 1520.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `consensus_tolerance_fraction` | Critical | 1.0000 | 0.0045 | 18.2% | `0.031641` (0.9747), `0.012` (0.9738), `0.004` (0.9703) | current run |
| `minimum_side_consensus` | Critical | 1.0000 | 0.0045 | 66.7% | `0.867713` (0.9747), `0.5` (0.9738), `0.1` (0.9703) | current run |
| `consensus_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.6` (0.9710) | current run |
| `gradient_percentile` | Zombie | 0.0000 | 0.0000 | 100.0% | `76` (0.9710) | current run |
| `gradient_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.9710) | current run |
| `minimum_side_gradient_support` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.03` (0.9710) | current run |
| `source_diversity_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.15` (0.9710) | current run |

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
| 1 | 0.9734 | 0.9729 | 0.9785 | 0.0016 | 100.0% |
| 5 | 0.9754 | 0.9752 | 0.9761 | 0.0003 | 100.0% |
| 6 | 0.9919 | 0.9911 | 0.9920 | 0.0003 | 100.0% |
| 9 | 0.9557 | 0.9539 | 0.9638 | 0.0038 | 100.0% |
| 10 | 0.9587 | 0.9574 | 0.9643 | 0.0027 | 100.0% |

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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2000 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 4m 59s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9747 |
| Minimum Avg IoU | 0.8324 |
| Avg IoU StdDev | 0.0477 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 227 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (18.2%) |
| Equivalent-best configurations (within 0.0001) | 2 (18.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2000 | 100.0% | 5m 1s | 1.0× |
| Exhaustive | 2000 | 100.0% | 5m 1s | 1.0× |
| Non-dormant | 108 | 5.4% | 16.3s | 18.5× |
| Low+ | 108 | 5.4% | 16.3s | 18.5× |
| Moderate+ | 108 | 5.4% | 16.3s | 18.5× |
| Important+ | 27 | 1.4% | 4.1s | 74.1× |
| Critical | 27 | 1.4% | 4.1s | 74.1× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `page_padding_fraction` | Critical | 1.0000 | 0.1423 | 11.1% | `0.01` (0.9747), `0` (0.9656), `0.02` (0.9485) | current run |
| `minimum_page_area_fraction` | Critical | 0.1837 | 0.0841 | 66.7% | `0.2` (0.9747), `0.08` (0.9072), `0.12` (0.8906) | current run |
| `minimum_component_area_fraction` | Moderate | 0.0425 | 0.0255 | 100.0% | `0.0005` (0.9327), `0` (0.9072) | current run |
| `minimum_confidence` | Moderate | 0.0425 | 0.0255 | 100.0% | `0.5` (0.9327), `0` (0.9072) | current run |

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
| 1 | 0.8899 | 0.7810 | 0.9770 | 0.0681 | 100.0% |
| 5 | 0.9354 | 0.8752 | 0.9595 | 0.0262 | 100.0% |
| 6 | 0.9457 | 0.9327 | 0.9899 | 0.0200 | 100.0% |
| 9 | 0.8894 | 0.7696 | 0.9900 | 0.0756 | 100.0% |
| 10 | 0.8986 | 0.8035 | 0.9814 | 0.0618 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="fusion-gen2-amsre-bfq-spbv-page-background-amsrebfqspbvpbg"></a>
<details>
<summary><strong>Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background (`amsre_bfq_spbv_pbg`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50177 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 4d 5h 48m 36s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9743 |
| Minimum Avg IoU | 0.9707 |
| Avg IoU StdDev | 0.0010 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50176 | 100.0% | 4d 5h 49m 42s | 1.0× |
| Exhaustive | 50176 | 100.0% | 4d 5h 49m 42s | 1.0× |
| Non-dormant | 20 | 0.0% | 2m 26s | 2508.8× |
| Low+ | 20 | 0.0% | 2m 26s | 2508.8× |
| Moderate+ | 20 | 0.0% | 2m 26s | 2508.8× |
| Important+ | 20 | 0.0% | 2m 26s | 2508.8× |
| Critical | 20 | 0.0% | 2m 26s | 2508.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `consensus_tolerance_fraction` | Critical | 1.0000 | 0.0035 | 10.0% | `0.012664` (0.9743), `0.006673` (0.9709), `0.006807` (0.9709) | current run |
| `minimum_side_consensus` | Critical | 0.9941 | 0.0035 | 50.0% | `0.1` (0.9743), `0.05` (0.9708) | current run |
| `consensus_weight` | Critical | 0.8947 | 0.0000 | 100.0% | `0.6` (0.9743) | current run |
| `gradient_percentile` | Critical | 0.8947 | 0.0000 | 100.0% | `76` (0.9743) | current run |
| `gradient_weight` | Critical | 0.8947 | 0.0000 | 100.0% | `0.25` (0.9743) | current run |
| `minimum_side_gradient_support` | Critical | 0.8947 | 0.0000 | 100.0% | `0.03` (0.9743) | current run |
| `source_diversity_weight` | Critical | 0.8947 | 0.0000 | 100.0% | `0.15` (0.9743) | current run |

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
| 1 | 0.9751 | 0.9751 | 0.9751 | 0.0000 | 100.0% |
| 5 | 0.9756 | 0.9752 | 0.9761 | 0.0004 | 100.0% |
| 6 | 0.9920 | 0.9920 | 0.9920 | 0.0000 | 100.0% |
| 9 | 0.9549 | 0.9539 | 0.9638 | 0.0030 | 100.0% |
| 10 | 0.9581 | 0.9574 | 0.9643 | 0.0021 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="dhsegment-page-mask-detector-dhsegmentpagemask"></a>
<details>
<summary><strong>dhSegment Page-Mask Detector (`dhsegment_page_mask`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 10000 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 31m 8s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9735 |
| Minimum Avg IoU | 0.9636 |
| Avg IoU StdDev | 0.0036 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 279 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (27.3%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 10000 | 100.0% | 31m 10s | 1.0× |
| Exhaustive | 10000 | 100.0% | 31m 10s | 1.0× |
| Non-dormant | 144 | 1.4% | 26.9s | 69.4× |
| Low+ | 144 | 1.4% | 26.9s | 69.4× |
| Moderate+ | 72 | 0.7% | 13.5s | 138.9× |
| Important+ | 72 | 0.7% | 13.5s | 138.9× |
| Critical | 72 | 0.7% | 13.5s | 138.9× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `contour_offset_fraction` | Critical | 0.9980 | 0.0095 | 25.0% | `0.008` (0.9731), `0.004` (0.9691), `0` (0.9670) | current run |
| `open_kernel_fraction` | Critical | 0.3534 | 0.0100 | 66.7% | `0.006` (0.9735), `0` (0.9680), `0.0015` (0.9636) | current run |
| `close_kernel_fraction` | Critical | 0.2294 | 0.0065 | 66.7% | `0.0025` (0.9735), `0` (0.9676), `0.005` (0.9670) | current run |
| `probability_threshold` | Critical | 0.2265 | 0.0059 | 100.0% | `0.35` (0.9735), `-1` (0.9676) | current run |
| `minimum_page_area_fraction` | Low | 0.0101 | 0.0013 | 50.0% | `0.1` (0.9682), `0.2` (0.9670) | current run |
| `fill_holes` | Dormant | 0.0021 | 0.0003 | 100.0% | `0` (0.9683), `1` (0.9679) | current run |

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

`fill_holes`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `close_kernel_fraction` × `fill_holes` | 0.2437 | 0.0144 | 11 |
| `probability_threshold` × `fill_holes` | 0.2356 | 0.0091 | 11 |
| `open_kernel_fraction` × `close_kernel_fraction` | 0.3621 | 0.0088 | 11 |
| `open_kernel_fraction` × `minimum_page_area_fraction` | 0.3621 | 0.0088 | 11 |
| `probability_threshold` × `minimum_page_area_fraction` | 0.2294 | 0.0029 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9708 | 0.9653 | 0.9780 | 0.0045 | 100.0% |
| 5 | 0.9463 | 0.9361 | 0.9634 | 0.0089 | 100.0% |
| 6 | 0.9890 | 0.9840 | 0.9928 | 0.0033 | 100.0% |
| 9 | 0.9667 | 0.9652 | 0.9679 | 0.0011 | 100.0% |
| 10 | 0.9678 | 0.9672 | 0.9695 | 0.0008 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="adaptive-radial-edge-search-adaptiveradialedge"></a>
<details>
<summary><strong>Adaptive Radial Edge Search (`adaptive_radial_edge`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 49153 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 13h 39m 54s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9329 |
| Minimum Avg IoU | 0.8603 |
| Avg IoU StdDev | 0.0202 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.7s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 49152 | 100.0% | 13h 40m 3s | 1.0× |
| Exhaustive | 49152 | 100.0% | 13h 40m 3s | 1.0× |
| Non-dormant | 576 | 1.2% | 9m 37s | 85.3× |
| Low+ | 576 | 1.2% | 9m 37s | 85.3× |
| Moderate+ | 576 | 1.2% | 9m 37s | 85.3× |
| Important+ | 576 | 1.2% | 9m 37s | 85.3× |
| Critical | 576 | 1.2% | 9m 37s | 85.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gaussian_sigma` | Critical | 0.8925 | 0.0635 | 50.0% | `1.2` (0.9329), `0.6` (0.8694) | current run |
| `gradient_percentile` | Critical | 0.8925 | 0.0635 | 50.0% | `82` (0.9329), `74` (0.8694) | current run |
| `maximum_radius_fraction` | Critical | 0.8925 | 0.0635 | 50.0% | `0.72` (0.9329), `0.6` (0.8694) | current run |
| `minimum_radius_fraction` | Critical | 0.8925 | 0.0635 | 50.0% | `0.18` (0.9329), `0.1` (0.8694) | current run |
| `refined_angle_step_degrees` | Critical | 0.8925 | 0.0635 | 50.0% | `1` (0.9329), `0.35` (0.8694) | current run |
| `weak_side_support_fraction` | Critical | 0.8925 | 0.0635 | 50.0% | `0.55` (0.9329), `0.35` (0.8694) | current run |
| `area_weight` | Critical | 0.8033 | 0.0000 | 100.0% | `0.35` (0.9329) | current run |
| `coarse_angle_step_degrees` | Critical | 0.8033 | 0.0000 | 100.0% | `3` (0.9329) | current run |
| `maximum_area_fraction` | Critical | 0.8033 | 0.0000 | 100.0% | `0.98` (0.9329) | current run |
| `minimum_area_fraction` | Critical | 0.8033 | 0.0000 | 100.0% | `0.18` (0.9329) | current run |
| `minimum_ray_support` | Critical | 0.8033 | 0.0000 | 100.0% | `0.45` (0.9329) | current run |
| `ray_count` | Critical | 0.8033 | 0.0000 | 100.0% | `120` (0.9329) | current run |
| `rectangularity_weight` | Critical | 0.8033 | 0.0000 | 100.0% | `0.2` (0.9329) | current run |
| `support_weight` | Critical | 0.8033 | 0.0000 | 100.0% | `0.45` (0.9329) | current run |
| `side_assignment_tolerance_fraction` | Critical | 0.3187 | 0.0247 | 33.3% | `0.025` (0.8896), `0.015` (0.8682), `0.035` (0.8649) | current run |
| `maximum_refined_sides` | Critical | 0.3134 | 0.0240 | 33.3% | `2` (0.8895), `4` (0.8676), `1` (0.8656) | current run |

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
| 1 | 0.8791 | 0.8278 | 0.9085 | 0.0317 | 100.0% |
| 5 | 0.8967 | 0.8772 | 0.9752 | 0.0281 | 100.0% |
| 6 | 0.8905 | 0.8316 | 0.9090 | 0.0271 | 100.0% |
| 9 | 0.8345 | 0.8125 | 0.9480 | 0.0404 | 100.0% |
| 10 | 0.8780 | 0.8016 | 0.9548 | 0.0530 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="signed-polar-boundary-voting-signedpolarboundaryvote"></a>
<details>
<summary><strong>Signed Polar Boundary Voting (`signed_polar_boundary_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 5 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 46875 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 1h 41m 2s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8668 |
| Minimum Avg IoU | 0.8229 |
| Avg IoU StdDev | 0.0166 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 388 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (20.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 46875 | 100.0% | 1h 41m 3s | 1.0× |
| Exhaustive | 46875 | 100.0% | 1h 41m 3s | 1.0× |
| Non-dormant | 3 | 0.0% | 388 ms | 15625.0× |
| Low+ | 3 | 0.0% | 388 ms | 15625.0× |
| Moderate+ | 3 | 0.0% | 388 ms | 15625.0× |
| Important+ | 3 | 0.0% | 388 ms | 15625.0× |
| Critical | 3 | 0.0% | 388 ms | 15625.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `polarity` | Critical | 0.8340 | 0.0364 | 33.3% | `absolute` (0.8663), `dark_inside` (0.8431), `bright_inside` (0.8299) | current run |
| `inner_radius_fraction` | Dormant | 0.0050 | 0.0039 | 50.0% | `0.12` (0.8483), `0.1` (0.8444) | current run |
| `minimum_support_fraction` | Dormant | 0.0050 | 0.0039 | 50.0% | `0.35` (0.8483), `0.2` (0.8444) | current run |
| `outer_radius_fraction` | Dormant | 0.0050 | 0.0039 | 50.0% | `0.7` (0.8483), `0.45` (0.8444) | current run |
| `ray_count` | Dormant | 0.0050 | 0.0039 | 50.0% | `180` (0.8483), `72` (0.8444) | current run |
| `bbox_padding_fraction` | Dormant | 0.0003 | 0.0007 | 66.7% | `0` (0.8451), `0.004` (0.8447), `0.002` (0.8444) | current run |
| `gradient_percentile` | Zombie | 0.0000 | 0.0000 | 100.0% | `82` (0.8448) | current run |

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

`inner_radius_fraction`, `minimum_support_fraction`, `outer_radius_fraction`, `ray_count`, `bbox_padding_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `polarity` × `inner_radius_fraction` | 0.9990 | 0.1650 | 10 |
| `polarity` × `minimum_support_fraction` | 0.9990 | 0.1650 | 10 |
| `polarity` × `outer_radius_fraction` | 0.9990 | 0.1650 | 10 |
| `polarity` × `ray_count` | 0.9990 | 0.1650 | 10 |
| `polarity` × `bbox_padding_fraction` | 0.8827 | 0.0487 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8526 | 0.7957 | 0.9006 | 0.0342 | 100.0% |
| 5 | 0.7589 | 0.7313 | 0.8951 | 0.0459 | 100.0% |
| 6 | 0.9381 | 0.9327 | 0.9607 | 0.0086 | 100.0% |
| 9 | 0.8084 | 0.7473 | 0.8681 | 0.0448 | 100.0% |
| 10 | 0.8658 | 0.8232 | 0.9262 | 0.0398 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="border-fusion-quad-borderfusionquad"></a>
<details>
<summary><strong>Border Fusion Quad (`border_fusion_quad`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 48021 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 12h 57m 18s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9367 |
| Minimum Avg IoU | 0.8890 |
| Avg IoU StdDev | 0.0144 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.7s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 48020 | 100.0% | 12h 57m 27s | 1.0× |
| Exhaustive | 48020 | 100.0% | 12h 57m 27s | 1.0× |
| Non-dormant | 192 | 0.4% | 3m 7s | 250.1× |
| Low+ | 192 | 0.4% | 3m 7s | 250.1× |
| Moderate+ | 192 | 0.4% | 3m 7s | 250.1× |
| Important+ | 192 | 0.4% | 3m 7s | 250.1× |
| Critical | 64 | 0.1% | 1m 2s | 750.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_percentile` | Critical | 0.5502 | 0.0355 | 50.0% | `68` (0.9246), `82` (0.8890) | current run |
| `gradient_weight` | Critical | 0.5502 | 0.0355 | 50.0% | `0.1` (0.9246), `0.45` (0.8890) | current run |
| `minimum_area_fraction` | Critical | 0.5502 | 0.0355 | 50.0% | `0.08` (0.9246), `0.18` (0.8890) | current run |
| `minimum_side_gradient_support` | Critical | 0.5502 | 0.0355 | 50.0% | `0` (0.9246), `0.16` (0.8890) | current run |
| `area_weight` | Critical | 0.4952 | 0.0000 | 0.0% | `0.15` (0.8890) | current run |
| `bbox_padding_fraction` | Critical | 0.4952 | 0.0000 | 0.0% | `0` (0.8890) | current run |
| `maximum_area_fraction` | Critical | 0.4952 | 0.0000 | 0.0% | `0.98` (0.8890) | current run |
| `minimum_child_candidates` | Critical | 0.4952 | 0.0000 | 0.0% | `2` (0.8890) | current run |
| `minimum_child_confidence` | Critical | 0.4952 | 0.0000 | 0.0% | `0` (0.8890) | current run |
| `minimum_distinct_sources` | Critical | 0.4952 | 0.0000 | 0.0% | `2` (0.8890) | current run |
| `source_diversity_weight` | Critical | 0.2357 | 0.0168 | 25.0% | `0` (0.9273), `0.025` (0.9244), `0.05` (0.9237) | current run |
| `source_confidence_weight` | Important | 0.1172 | 0.0104 | 33.3% | `0.25` (0.9257), `0.35` (0.9204), `0.3` (0.9153) | current run |

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
| 1 | 0.9322 | 0.8847 | 0.9655 | 0.0308 | 100.0% |
| 5 | 0.8855 | 0.5825 | 0.9240 | 0.1011 | 100.0% |
| 6 | 0.9887 | 0.9791 | 0.9911 | 0.0048 | 100.0% |
| 9 | 0.8500 | 0.8379 | 0.9588 | 0.0363 | 100.0% |
| 10 | 0.9486 | 0.9106 | 0.9660 | 0.0249 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="page-background-pagebackground"></a>
<details>
<summary><strong>Page Background (`page_background`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 48401 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 5h 37m 28s |
| Fully successful parameter sets | 9 (90.0%) |
| Best Avg IoU | 0.9664 |
| Minimum Avg IoU | 0.7618 |
| Avg IoU StdDev | 0.0603 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (20.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 48400 | 100.0% | 5h 37m 32s | 1.0× |
| Exhaustive | 48400 | 100.0% | 5h 37m 32s | 1.0× |
| Non-dormant | 384 | 0.8% | 2m 41s | 126.0× |
| Low+ | 384 | 0.8% | 2m 41s | 126.0× |
| Moderate+ | 384 | 0.8% | 2m 41s | 126.0× |
| Important+ | 384 | 0.8% | 2m 41s | 126.0× |
| Critical | 384 | 0.8% | 2m 41s | 126.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `close_kernel_fraction` | Critical | 0.9992 | 0.2020 | 33.3% | `0` (0.9639), `0.0005` (0.9516), `0.008` (0.7618) | current run |
| `blur_sigma` | Critical | 0.9955 | 0.2007 | 50.0% | `0` (0.9625), `1.2` (0.7618) | current run |
| `border_band_fraction` | Critical | 0.9955 | 0.2007 | 50.0% | `0.015` (0.9625), `0.06` (0.7618) | current run |
| `minimum_border_background_fraction` | Critical | 0.9955 | 0.2007 | 50.0% | `0.15` (0.9625), `0.5` (0.7618) | current run |
| `minimum_page_area_fraction` | Critical | 0.9955 | 0.2007 | 50.0% | `0.15` (0.9625), `0.25` (0.7618) | current run |
| `maximum_page_area_fraction` | Critical | 0.8960 | 0.0000 | 0.0% | `0.98` (0.7618) | current run |
| `minimum_rectangularity` | Critical | 0.8960 | 0.0000 | 0.0% | `0.6` (0.7618) | current run |
| `open_kernel_fraction` | Critical | 0.4392 | 0.1036 | 25.0% | `0.006` (0.9664), `0.0045` (0.9662), `0.0015` (0.9638) | current run |
| `color_distance_threshold` | Zombie | 0.0000 | 0.0000 | 100.0% | `3` (0.9425) | current run |

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
| 1 | 0.9459 | 0.9402 | 0.9489 | 0.0026 | 100.0% |
| 5 | 0.9876 | 0.9772 | 0.9920 | 0.0054 | 100.0% |
| 6 | 0.8903 | 0.0000 | 0.9961 | 0.2968 | 90.0% |
| 9 | 0.9446 | 0.9328 | 0.9476 | 0.0045 | 100.0% |
| 10 | 0.9439 | 0.9291 | 0.9512 | 0.0056 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="polar-boundary-voting-polarboundaryvote"></a>
<details>
<summary><strong>Polar Boundary Voting (`polar_boundary_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 19636 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 39m 34s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9691 |
| Minimum Avg IoU | 0.8908 |
| Avg IoU StdDev | 0.0285 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 355 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 19635 | 100.0% | 39m 35s | 1.0× |
| Exhaustive | 19635 | 100.0% | 39m 35s | 1.0× |
| Non-dormant | 108 | 0.6% | 13.1s | 181.8× |
| Low+ | 108 | 0.6% | 13.1s | 181.8× |
| Moderate+ | 108 | 0.6% | 13.1s | 181.8× |
| Important+ | 108 | 0.6% | 13.1s | 181.8× |
| Critical | 108 | 0.6% | 13.1s | 181.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_percentile` | Critical | 0.9930 | 0.0743 | 33.3% | `94` (0.9691), `90` (0.9678), `84` (0.8948) | current run |
| `outer_radius_fraction` | Critical | 0.9929 | 0.0737 | 50.0% | `0.6` (0.9684), `0.4` (0.8948) | current run |
| `bbox_padding_fraction` | Critical | 0.5505 | 0.0508 | 11.1% | `0` (0.9426), `0.01` (0.8991), `0.008` (0.8979) | current run |
| `ray_count` | Critical | 0.4372 | 0.0656 | 50.0% | `180` (0.9678), `90` (0.9022) | current run |
| `inner_radius_fraction` | Critical | 0.3974 | 0.0000 | 0.0% | `0.06` (0.9678) | current run |
| `minimum_support_fraction` | Critical | 0.3974 | 0.0000 | 0.0% | `0.25` (0.9678) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `bbox_padding_fraction` × `ray_count` | 0.6573 | 0.1067 | 11 |
| `gradient_percentile` × `bbox_padding_fraction` | 1.0000 | 0.0070 | 11 |
| `outer_radius_fraction` × `bbox_padding_fraction` | 0.9999 | 0.0070 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8878 | 0.8620 | 0.9819 | 0.0415 | 100.0% |
| 5 | 0.9444 | 0.9263 | 0.9942 | 0.0235 | 100.0% |
| 6 | 0.9434 | 0.9305 | 0.9765 | 0.0143 | 100.0% |
| 9 | 0.8435 | 0.8204 | 0.9524 | 0.0491 | 100.0% |
| 10 | 0.9217 | 0.9145 | 0.9541 | 0.0151 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="gradient-boundary-voting-gradientvote"></a>
<details>
<summary><strong>Gradient Boundary Voting (`gradient_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 9 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 22 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 50.0% |
| Est. serial runtime for full parameter set evaluation* | 1.2s |
| Fully successful parameter sets | 2 (18.2%) |
| Best Avg IoU | 0.9622 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.3681 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 235 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 21 | 100.0% | 2.3s | 1.0× |
| Exhaustive | 21 | 100.0% | 2.3s | 1.0× |
| Non-dormant | 11 | 52.4% | 1.2s | 1.9× |
| Low+ | 11 | 52.4% | 1.2s | 1.9× |
| Moderate+ | 11 | 52.4% | 1.2s | 1.9× |
| Important+ | 11 | 52.4% | 1.2s | 1.9× |
| Critical | 11 | 52.4% | 1.2s | 1.9× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `border_search_fraction` | Critical | 1.0000 | 0.9622 | 9.1% | `0.14` (0.9622), `0.15` (0.9467), `0.05` (0.0000) | current run |
| `area_weight` | Critical | 0.4010 | 0.0000 | 0.0% | `0.25` (0.9467) | current run |
| `central_band_fraction` | Critical | 0.4010 | 0.0000 | 0.0% | `1` (0.9467) | current run |
| `gaussian_sigma` | Critical | 0.4010 | 0.0000 | 0.0% | `1.2` (0.9467) | current run |
| `gradient_percentile` | Critical | 0.4010 | 0.0000 | 0.0% | `70` (0.9467) | current run |
| `minimum_area_fraction` | Critical | 0.4010 | 0.0000 | 0.0% | `0.2` (0.9467) | current run |
| `minimum_span_fraction` | Critical | 0.4010 | 0.0000 | 0.0% | `0.15` (0.9467) | current run |
| `minimum_vote_support` | Critical | 0.4010 | 0.0000 | 0.0% | `0.08` (0.9467) | current run |
| `rectangularity_weight` | Critical | 0.4010 | 0.0000 | 0.0% | `0.2` (0.9467) | current run |
| `support_weight` | Critical | 0.4010 | 0.0000 | 0.0% | `0.45` (0.9467) | current run |
| `vote_smooth_fraction` | Critical | 0.4010 | 0.0000 | 0.0% | `0.012` (0.9467) | current run |

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
| 1 | 0.1748 | 0.0000 | 0.9613 | 0.3708 | 18.2% |
| 5 | 0.1636 | 0.0000 | 0.9384 | 0.3474 | 18.2% |
| 6 | 0.1798 | 0.0000 | 0.9889 | 0.3814 | 18.2% |
| 9 | 0.1748 | 0.0000 | 0.9612 | 0.3707 | 18.2% |
| 10 | 0.1747 | 0.0000 | 0.9611 | 0.3707 | 18.2% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="radial-edge-search-radialedge"></a>
<details>
<summary><strong>Radial Edge Search (`radial_edge`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50001 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 1h 59m 43s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9503 |
| Minimum Avg IoU | 0.7861 |
| Avg IoU StdDev | 0.0493 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 283 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50000 | 100.0% | 1h 59m 44s | 1.0× |
| Exhaustive | 50000 | 100.0% | 1h 59m 44s | 1.0× |
| Non-dormant | 384 | 0.8% | 55.2s | 130.2× |
| Low+ | 384 | 0.8% | 55.2s | 130.2× |
| Moderate+ | 384 | 0.8% | 55.2s | 130.2× |
| Important+ | 384 | 0.8% | 55.2s | 130.2× |
| Critical | 96 | 0.2% | 13.8s | 520.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gaussian_sigma` | Critical | 1.0000 | 0.1642 | 50.0% | `1.2` (0.9503), `0.6` (0.7861) | current run |
| `gradient_percentile` | Critical | 1.0000 | 0.1642 | 50.0% | `82` (0.9503), `74` (0.7861) | current run |
| `maximum_radius_fraction` | Critical | 1.0000 | 0.1642 | 50.0% | `0.72` (0.9503), `0.6` (0.7861) | current run |
| `minimum_radius_fraction` | Critical | 1.0000 | 0.1642 | 50.0% | `0.18` (0.9503), `0.1` (0.7861) | current run |
| `ray_count` | Critical | 1.0000 | 0.1642 | 50.0% | `96` (0.9503), `64` (0.7861) | current run |
| `area_weight` | Critical | 0.9000 | 0.0000 | 100.0% | `0.35` (0.9503) | current run |
| `maximum_area_fraction` | Critical | 0.9000 | 0.0000 | 100.0% | `0.98` (0.9503) | current run |
| `minimum_area_fraction` | Critical | 0.9000 | 0.0000 | 100.0% | `0.18` (0.9503) | current run |
| `minimum_ray_support` | Critical | 0.4444 | 0.0821 | 33.3% | `0.45` (0.8682), `0.25` (0.7861), `0.35` (0.7861) | current run |
| `support_weight` | Important | 0.1111 | 0.0328 | 50.0% | `0.45` (0.8189), `0.35` (0.7861) | current run |
| `rectangularity_weight` | Important | 0.0741 | 0.0274 | 50.0% | `0.2` (0.8135), `0.3` (0.7861) | current run |

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
| 1 | 0.7171 | 0.6916 | 0.9466 | 0.0765 | 100.0% |
| 5 | 0.9356 | 0.9313 | 0.9742 | 0.0129 | 100.0% |
| 6 | 0.7162 | 0.6915 | 0.9384 | 0.0741 | 100.0% |
| 9 | 0.7833 | 0.7665 | 0.9340 | 0.0502 | 100.0% |
| 10 | 0.8604 | 0.8495 | 0.9582 | 0.0326 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="segment-supported-polar-voting-segmentsupportedpolarvote"></a>
<details>
<summary><strong>Segment-Supported Polar Voting (`segment_supported_polar_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 45361 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 8h 34m 7s |
| Fully successful parameter sets | 8 (80.0%) |
| Best Avg IoU | 0.9236 |
| Minimum Avg IoU | 0.6177 |
| Avg IoU StdDev | 0.1066 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.4s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (20.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 45360 | 100.0% | 8h 34m 13s | 1.0× |
| Exhaustive | 45360 | 100.0% | 8h 34m 13s | 1.0× |
| Non-dormant | 960 | 2.1% | 10m 53s | 47.2× |
| Low+ | 960 | 2.1% | 10m 53s | 47.2× |
| Moderate+ | 960 | 2.1% | 10m 53s | 47.2× |
| Important+ | 960 | 2.1% | 10m 53s | 47.2× |
| Critical | 960 | 2.1% | 10m 53s | 47.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_segment_length_fraction` | Critical | 0.9720 | 0.2658 | 20.0% | `0.03` (0.9234), `0.015` (0.9192), `0.0225` (0.9176) | current run |
| `segment_distance_fraction` | Critical | 0.2596 | 0.1899 | 66.7% | `0.0035` (0.8872), `0.0025` (0.8331), `0.018` (0.6974) | current run |
| `gradient_percentile` | Critical | 0.2022 | 0.1598 | 50.0% | `78` (0.8571), `82` (0.6974) | current run |
| `inner_radius_fraction` | Critical | 0.2022 | 0.1598 | 50.0% | `0.08` (0.8571), `0.12` (0.6974) | current run |
| `minimum_segment_support_fraction` | Critical | 0.2022 | 0.1598 | 50.0% | `0.1` (0.8571), `0.3` (0.6974) | current run |
| `minimum_support_fraction` | Critical | 0.2022 | 0.1598 | 50.0% | `0.2` (0.8571), `0.35` (0.6974) | current run |
| `outer_radius_fraction` | Critical | 0.2022 | 0.1598 | 50.0% | `0.66` (0.8571), `0.7` (0.6974) | current run |
| `ray_count` | Critical | 0.2022 | 0.1598 | 50.0% | `48` (0.8571), `180` (0.6974) | current run |
| `bbox_padding_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.8412) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_segment_length_fraction` × `segment_distance_fraction` | 1.0000 | 0.0280 | 10 |
| `minimum_segment_length_fraction` × `gradient_percentile` | 1.0000 | 0.0279 | 10 |
| `minimum_segment_length_fraction` × `inner_radius_fraction` | 1.0000 | 0.0279 | 10 |
| `minimum_segment_length_fraction` × `minimum_segment_support_fraction` | 1.0000 | 0.0279 | 10 |
| `minimum_segment_length_fraction` × `minimum_support_fraction` | 1.0000 | 0.0279 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8595 | 0.5828 | 0.9606 | 0.1268 | 100.0% |
| 5 | 0.6483 | 0.0000 | 0.9512 | 0.3800 | 80.0% |
| 6 | 0.9756 | 0.8314 | 0.9951 | 0.0484 | 100.0% |
| 9 | 0.8194 | 0.7975 | 0.8360 | 0.0182 | 100.0% |
| 10 | 0.9029 | 0.8383 | 0.9567 | 0.0266 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="orli-page-mask-orlipagemask"></a>
<details>
<summary><strong>Orli Page Mask (`orli_page_mask`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 9 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1680 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.7% |
| Est. serial runtime for full parameter set evaluation* | 13m 29s |
| Fully successful parameter sets | 2 (18.2%) |
| Best Avg IoU | 0.9185 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.3335 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.9s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 16800 | 100.0% | 2h 15m 38s | 1.0× |
| Exhaustive | 1680 | 10.0% | 13m 34s | 10.0× |
| Non-dormant | 112 | 0.7% | 54.3s | 150.0× |
| Low+ | 112 | 0.7% | 54.3s | 150.0× |
| Moderate+ | 112 | 0.7% | 54.3s | 150.0× |
| Important+ | 112 | 0.7% | 54.3s | 150.0× |
| Critical | 112 | 0.7% | 54.3s | 150.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `page_padding_fraction` | Critical | 1.0000 | 0.9185 | 25.0% | `0.16` (0.9185), `0.05` (0.8063), `0` (0.0000) | current run |
| `include_lines` | Critical | 0.9949 | 0.8624 | 50.0% | `1` (0.8624), `0` (0.0000) | current run |
| `dilation_fraction` | Critical | 0.3794 | 0.7145 | 50.0% | `0.01` (0.8063), `0` (0.0918) | current run |
| `minimum_page_area_fraction` | Critical | 0.2745 | 0.4032 | 14.3% | `0.12` (0.4032), `0.04` (0.3062), `0.06` (0.0000) | current run |
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

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `dilation_fraction` × `minimum_page_area_fraction` | 0.5403 | 0.1609 | 11 |
| `include_lines` × `dilation_fraction` | 1.0000 | 0.0051 | 11 |
| `include_lines` × `minimum_page_area_fraction` | 1.0000 | 0.0051 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.1558 | 0.0000 | 0.9357 | 0.3323 | 18.2% |
| 5 | 0.1672 | 0.0000 | 0.9263 | 0.3546 | 18.2% |
| 6 | 0.1406 | 0.0000 | 0.8557 | 0.3004 | 18.2% |
| 9 | 0.1495 | 0.0000 | 0.8959 | 0.3186 | 18.2% |
| 10 | 0.1709 | 0.0000 | 0.9788 | 0.3629 | 18.2% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="contour-quadrilateral-contourquad"></a>
<details>
<summary><strong>Contour Quadrilateral (`contour_quad`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 41472 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 5h 1m 29s |
| Fully successful parameter sets | 5 (50.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.6531 |
| Avg IoU StdDev | 0.1119 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 5 (50.0%) |
| Equivalent-best configurations (within 0.0001) | 5 (50.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 41472 | 100.0% | 5h 1m 33s | 1.0× |
| Exhaustive | 41472 | 100.0% | 5h 1m 33s | 1.0× |
| Non-dormant | 8 | 0.0% | 3.5s | 5184.0× |
| Low+ | 8 | 0.0% | 3.5s | 5184.0× |
| Moderate+ | 8 | 0.0% | 3.5s | 5184.0× |
| Important+ | 8 | 0.0% | 3.5s | 5184.0× |
| Critical | 2 | 0.0% | 873 ms | 20736.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `merge_fragmented_contours` | Critical | 1.0000 | 0.2237 | 50.0% | `true` (0.8768), `false` (0.6531) | current run |
| `angle_weight` | Important | 0.1111 | 0.1243 | 100.0% | `0.2` (0.8768), `0.1` (0.7525) | current run |
| `rectangularity_weight` | Important | 0.1111 | 0.1243 | 100.0% | `0.3` (0.8768), `0.2` (0.7525) | current run |
| `edge_support_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.1` (0.7650), `0.15` (0.7650) | current run |
| `area_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.35` (0.7650) | current run |
| `close_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.7650) | current run |
| `close_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.7650) | current run |
| `edge_support_dilation_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.002` (0.7650), `0.004` (0.7650), `0.008` (0.7650) | current run |
| `epsilon_max_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.7650) | current run |
| `epsilon_min_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.7650) | current run |
| `epsilon_steps` | Zombie | 0.0000 | 0.0000 | 100.0% | `9` (0.7650) | current run |
| `minimum_contour_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.12` (0.7650) | current run |
| `minimum_rectangularity` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.55` (0.7650) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `angle_weight` × `edge_support_weight` | 0.1333 | 0.0222 | 10 |
| `rectangularity_weight` × `edge_support_weight` | 0.1333 | 0.0222 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8799 | 0.8542 | 0.9055 | 0.0256 | 100.0% |
| 5 | 0.6563 | 0.4508 | 0.8618 | 0.2055 | 100.0% |
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

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50000 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 5d 4h 51m 44s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8868 |
| Minimum Avg IoU | 0.8374 |
| Avg IoU StdDev | 0.0123 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 17.4s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50000 | 100.0% | 5d 4h 53m 23s | 1.0× |
| Exhaustive | 50000 | 100.0% | 5d 4h 53m 23s | 1.0× |
| Non-dormant | 240 | 0.5% | 35m 58s | 208.3× |
| Low+ | 240 | 0.5% | 35m 58s | 208.3× |
| Moderate+ | 240 | 0.5% | 35m 58s | 208.3× |
| Important+ | 240 | 0.5% | 35m 58s | 208.3× |
| Critical | 120 | 0.2% | 17m 59s | 416.7× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `mask_threshold` | Critical | 0.9701 | 0.0494 | 33.3% | `0.226` (0.8868), `0.204` (0.8778), `0.5` (0.8374) | current run |
| `close_kernel_fraction` | Critical | 0.9259 | 0.0412 | 50.0% | `0` (0.8787), `0.006` (0.8374) | current run |
| `minimum_mask_area_fraction` | Critical | 0.9259 | 0.0412 | 50.0% | `0.04` (0.8787), `0.15` (0.8374) | current run |
| `bbox_padding_fraction` | Critical | 0.6568 | 0.0324 | 10.0% | `0.029` (0.8868), `0.02` (0.8792), `0.021` (0.8792) | current run |
| `polygon_epsilon_fraction` | Important | 0.0933 | 0.0131 | 50.0% | `0.0185` (0.8868), `0.012` (0.8737) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `close_kernel_fraction` × `bbox_padding_fraction` | 1.0000 | 0.0741 | 11 |
| `minimum_mask_area_fraction` × `bbox_padding_fraction` | 1.0000 | 0.0741 | 11 |
| `close_kernel_fraction` × `polygon_epsilon_fraction` | 0.9701 | 0.0442 | 11 |
| `minimum_mask_area_fraction` × `polygon_epsilon_fraction` | 0.9701 | 0.0442 | 11 |
| `mask_threshold` × `bbox_padding_fraction` | 1.0000 | 0.0299 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8985 | 0.8835 | 0.9471 | 0.0173 | 100.0% |
| 5 | 0.9199 | 0.9151 | 0.9235 | 0.0026 | 100.0% |
| 6 | 0.7857 | 0.7029 | 0.8122 | 0.0347 | 100.0% |
| 9 | 0.8508 | 0.8475 | 0.8521 | 0.0015 | 100.0% |
| 10 | 0.9197 | 0.8297 | 0.9369 | 0.0289 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-contour-grabcutcontour"></a>
<details>
<summary><strong>GrabCut + Contour (`grabcut_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 46657 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 23d 6h 48m 45s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8772 |
| Minimum Avg IoU | 0.8130 |
| Avg IoU StdDev | 0.0185 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1m 13s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 46656 | 100.0% | 23d 6h 55m 56s | 1.0× |
| Exhaustive | 46656 | 100.0% | 23d 6h 55m 56s | 1.0× |
| Non-dormant | 768 | 1.6% | 9h 12m 2s | 60.8× |
| Low+ | 768 | 1.6% | 9h 12m 2s | 60.8× |
| Moderate+ | 48 | 0.1% | 34m 30s | 972.0× |
| Important+ | 48 | 0.1% | 34m 30s | 972.0× |
| Critical | 12 | 0.0% | 8m 38s | 3888.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `grabcut_close_kernel_fraction` | Critical | 1.0000 | 0.0642 | 50.0% | `0.03` (0.8772), `0.02` (0.8130) | current run |
| `grabcut_iterations` | Critical | 1.0000 | 0.0642 | 50.0% | `5` (0.8772), `3` (0.8130) | current run |
| `agreement_weight` | Critical | 0.2667 | 0.0214 | 33.3% | `0.35` (0.8344), `0.15` (0.8130), `0.25` (0.8130) | current run |
| `grabcut_weight` | Important | 0.1200 | 0.0128 | 50.0% | `0.55` (0.8259), `0.45` (0.8130) | current run |
| `require_contour` | Important | 0.1200 | 0.0128 | 50.0% | `true` (0.8259), `false` (0.8130) | current run |
| `contour_minimum_area_fraction` | Low | 0.0100 | 0.0064 | 50.0% | `0.08` (0.8194), `0.12` (0.8130) | current run |
| `contour_minimum_rectangularity` | Low | 0.0100 | 0.0064 | 50.0% | `0.45` (0.8194), `0.55` (0.8130) | current run |
| `grabcut_polygon_epsilon_fraction` | Low | 0.0100 | 0.0064 | 50.0% | `0.01` (0.8194), `0.018` (0.8130) | current run |
| `minimum_agreement_iou` | Low | 0.0100 | 0.0064 | 50.0% | `0.05` (0.8194), `0.15` (0.8130) | current run |
| `contour_epsilon_max_fraction` | Low | 0.0091 | 0.0000 | 0.0% | `0.04` (0.8130) | current run |
| `contour_weight` | Low | 0.0091 | 0.0000 | 0.0% | `0.2` (0.8130) | current run |
| `grabcut_close_iterations` | Low | 0.0091 | 0.0000 | 0.0% | `1` (0.8130) | current run |
| `grabcut_erosion_iterations` | Low | 0.0091 | 0.0000 | 0.0% | `1` (0.8130) | current run |
| `grabcut_minimum_bbox_area_fraction` | Low | 0.0091 | 0.0000 | 0.0% | `0.1` (0.8130) | current run |
| `grabcut_border_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.02` (0.8189) | current run |
| `grabcut_erosion_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8189) | current run |
| `grabcut_minimum_contour_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8189) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `agreement_weight` × `grabcut_weight` | 1.0000 | 0.7333 | 11 |
| `grabcut_weight` × `require_contour` | 0.4500 | 0.3300 | 11 |
| `agreement_weight` × `require_contour` | 0.4500 | 0.1833 | 11 |
| `grabcut_weight` × `contour_minimum_area_fraction` | 0.1750 | 0.0550 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9556 | 0.9436 | 0.9568 | 0.0038 | 100.0% |
| 5 | 0.5788 | 0.5532 | 0.8348 | 0.0810 | 100.0% |
| 6 | 0.6730 | 0.6683 | 0.7198 | 0.0148 | 100.0% |
| 9 | 0.9423 | 0.9422 | 0.9433 | 0.0003 | 100.0% |
| 10 | 0.9447 | 0.9447 | 0.9447 | 0.0000 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="edge-supported-contour-edgecontour"></a>
<details>
<summary><strong>Edge-Supported Contour (`edge_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 6 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 7 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 13123 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 2h 31m 39s |
| Fully successful parameter sets | 4 (36.4%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.1928 |
| Avg IoU StdDev | 0.2865 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.9s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (36.4%) |
| Equivalent-best configurations (within 0.0001) | 4 (36.4%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 13122 | 100.0% | 2h 31m 46s | 1.0× |
| Exhaustive | 13122 | 100.0% | 2h 31m 46s | 1.0× |
| Non-dormant | 18 | 0.1% | 12.5s | 729.0× |
| Low+ | 18 | 0.1% | 12.5s | 729.0× |
| Moderate+ | 18 | 0.1% | 12.5s | 729.0× |
| Important+ | 6 | 0.0% | 4.2s | 2187.0× |
| Critical | 3 | 0.0% | 2.1s | 4374.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_edge_support` | Critical | 0.9748 | 0.6841 | 33.3% | `0.05` (0.8768), `0.12` (0.4086), `0.2` (0.1928) | current run |
| `edge_support_dilation_fraction` | Important | 0.0957 | 0.2298 | 100.0% | `0.006` (0.7080), `0.003` (0.4782) | current run |
| `edge_support_weight` | Moderate | 0.0238 | 0.0996 | 100.0% | `0.2` (0.5779), `0.3` (0.4935), `0.4` (0.4782) | current run |
| `epsilon_max_fraction` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.04` (0.5392), `0.03` (0.5181) | current run |
| `lsd_refine_mode` | Dormant | 0.0004 | 0.0211 | 50.0% | `std` (0.5392), `none` (0.5181) | current run |
| `lsd_scale` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.8` (0.5392), `0.6` (0.5181) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.12` (0.5392), `0.08` (0.5181) | current run |
| `minimum_rectangularity` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.55` (0.5392), `0.45` (0.5181) | current run |
| `minimum_segment_length_fraction` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.06` (0.5392), `0.03` (0.5181) | current run |
| `angle_weight` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.2` (0.5392) | current run |
| `area_weight` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.25` (0.5392) | current run |
| `close_iterations` | Zombie | 0.0004 | 0.0000 | 0.0% | `1` (0.5392) | current run |
| `close_kernel_fraction` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.008` (0.5392) | current run |
| `epsilon_min_fraction` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.008` (0.5392) | current run |
| `epsilon_steps` | Zombie | 0.0004 | 0.0000 | 0.0% | `9` (0.5392) | current run |
| `merge_fragmented_contours` | Zombie | 0.0004 | 0.0000 | 0.0% | `true` (0.5392) | current run |
| `rectangularity_weight` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.25` (0.5392) | current run |

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

`epsilon_max_fraction`, `lsd_refine_mode`, `lsd_scale`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `minimum_segment_length_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `edge_support_dilation_fraction` × `edge_support_weight` | 0.1588 | 0.0631 | 11 |
| `edge_support_dilation_fraction` × `epsilon_max_fraction` | 0.1588 | 0.0631 | 11 |
| `edge_support_dilation_fraction` × `lsd_refine_mode` | 0.1588 | 0.0631 | 11 |
| `edge_support_dilation_fraction` × `lsd_scale` | 0.1588 | 0.0631 | 11 |
| `minimum_edge_support` × `edge_support_dilation_fraction` | 1.0000 | 0.0252 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.3106 | 0.0000 | 0.8542 | 0.4109 | 36.4% |
| 5 | 0.6267 | 0.0000 | 0.8618 | 0.3838 | 72.7% |
| 6 | 0.2760 | 0.0000 | 0.7589 | 0.3651 | 36.4% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.4229 | 0.0000 | 0.9454 | 0.4637 | 45.5% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="cross-edge-contour-crossedgecontour"></a>
<details>
<summary><strong>Cross-Edge Contour (`cross_edge_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 6 of 10 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 1h 45m 44s |
| Fully successful parameter sets | 4 (40.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.3818 |
| Avg IoU StdDev | 0.2113 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 4 (40.0%) |
| Equivalent-best configurations (within 0.0001) | 4 (40.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 6561 | 100.0% | 1h 45m 52s | 1.0× |
| Exhaustive | 6561 | 100.0% | 1h 45m 52s | 1.0× |
| Non-dormant | 768 | 11.7% | 12m 24s | 8.5× |
| Low+ | 768 | 11.7% | 12m 24s | 8.5× |
| Moderate+ | 768 | 11.7% | 12m 24s | 8.5× |
| Important+ | 256 | 3.9% | 4m 8s | 25.6× |
| Critical | 256 | 3.9% | 4m 8s | 25.6× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_polarity_consistency` | Critical | 1.0000 | 0.4950 | 50.0% | `0.5` (0.8768), `0.55` (0.8768), `0.65` (0.5527) | current run |
| `epsilon_max_fraction` | Critical | 0.1503 | 0.2730 | 100.0% | `0.04` (0.8768), `0.03` (0.6038) | current run |
| `minimum_contour_area_fraction` | Critical | 0.1503 | 0.2730 | 100.0% | `0.12` (0.8768), `0.08` (0.6038) | current run |
| `minimum_cross_edge_contrast` | Critical | 0.1503 | 0.2730 | 100.0% | `0.045` (0.8768), `0.02` (0.6038) | current run |
| `minimum_rectangularity` | Critical | 0.1503 | 0.2730 | 100.0% | `0.55` (0.8768), `0.45` (0.6038) | current run |
| `sample_offset_fraction` | Critical | 0.1503 | 0.2730 | 100.0% | `0.008` (0.8768), `0.004` (0.6038) | current run |
| `samples_per_edge` | Critical | 0.1503 | 0.2730 | 100.0% | `48` (0.8768), `24` (0.6038) | current run |
| `contour_weight` | Important | 0.1353 | 0.0000 | 100.0% | `0.45` (0.8768) | current run |
| `polarity_weight` | Important | 0.1353 | 0.0000 | 100.0% | `0.15` (0.8768) | current run |
| `contrast_weight` | Moderate | 0.0251 | 0.0683 | 100.0% | `0.4` (0.6720), `0.3` (0.6038), `0.5` (0.6038) | current run |

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
| 1 | 0.5980 | 0.0000 | 0.8542 | 0.3915 | 70.0% |
| 5 | 0.3447 | 0.0000 | 0.8618 | 0.4222 | 40.0% |
| 6 | 0.3036 | 0.0000 | 0.7589 | 0.3718 | 40.0% |
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
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 3h 12m 46s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.8768 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 10 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 10 (100.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 6561 | 100.0% | 3h 13m 2s | 1.0× |
| Exhaustive | 6561 | 100.0% | 3h 13m 2s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `epsilon_max_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768) | current run |
| `minimum_contour_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768) | current run |
| `minimum_rectangularity` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768) | current run |
| `projection_margin_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.06` (0.8768) | current run |
| `projection_threshold_block_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.05` (0.8768), `0.08` (0.8768) | current run |
| `projection_threshold_c` | Zombie | 0.0000 | 0.0000 | 100.0% | `5` (0.8768), `9` (0.8768) | current run |
| `angle_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768) | current run |
| `area_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) | current run |
| `close_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.8768) | current run |
| `close_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) | current run |
| `epsilon_min_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) | current run |
| `epsilon_steps` | Zombie | 0.0000 | 0.0000 | 100.0% | `9` (0.8768) | current run |
| `merge_fragmented_contours` | Zombie | 0.0000 | 0.0000 | 100.0% | `true` (0.8768) | current run |
| `minimum_projection_score` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.05` (0.8768), `0.08` (0.8768), `0.15` (0.8768) | current run |
| `projection_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) | current run |
| `rectangularity_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) | current run |

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
| 1 | 0.8542 | 0.8542 | 0.8542 | 0.0000 | 100.0% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.7589 | 0.7589 | 0.7589 | 0.0000 | 100.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="contour-grabcut-contourgrabcut"></a>
<details>
<summary><strong>Contour + GrabCut (`contour_grabcut`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 2d 5h 13m 26s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.8768 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 10 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 10 (100.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 6561 | 100.0% | 2d 5h 17m 49s | 1.0× |
| Exhaustive | 6561 | 100.0% | 2d 5h 17m 49s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `contour_epsilon_max_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768) | current run |
| `contour_minimum_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768) | current run |
| `contour_minimum_rectangularity` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768) | current run |
| `grabcut_border_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.01` (0.8768), `0.02` (0.8768) | current run |
| `grabcut_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.8768), `3` (0.8768) | current run |
| `minimum_agreement_iou` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.3` (0.8768) | current run |
| `agreement_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) | current run |
| `contour_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768) | current run |
| `grabcut_erosion_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8768) | current run |
| `grabcut_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.25` (0.8768), `0.35` (0.8768) | current run |
| `require_grabcut` | Zombie | 0.0000 | 0.0000 | 100.0% | `false` (0.8768) | current run |

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
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 19684 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 1h 40m 24s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8617 |
| Minimum Avg IoU | 0.8617 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 10 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 10 (100.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 19683 | 100.0% | 1h 40m 27s | 1.0× |
| Exhaustive | 19683 | 100.0% | 1h 40m 27s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `component_close_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617), `0.004` (0.8617) | current run |
| `component_dilate_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8617), `0.008` (0.8617) | current run |
| `component_merge_gap_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.035` (0.8617), `0.02` (0.8617) | current run |
| `component_minimum_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.0015` (0.8617), `0.0008` (0.8617) | current run |
| `epsilon_max_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8617), `0.03` (0.8617) | current run |
| `minimum_contour_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.12` (0.8617), `0.08` (0.8617) | current run |
| `minimum_rectangularity` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.55` (0.8617), `0.45` (0.8617) | current run |
| `angle_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8617) | current run |
| `area_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8617) | current run |
| `close_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.8617) | current run |
| `close_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617) | current run |
| `component_bbox_padding_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.8617) | current run |
| `component_merge_area_ratio` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.02` (0.8617) | current run |
| `component_minimum_area_px` | Zombie | 0.0000 | 0.0000 | 100.0% | `25` (0.8617) | current run |
| `component_minimum_bbox_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.12` (0.8617) | current run |
| `component_minimum_selected_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8617) | current run |
| `component_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8617), `0.4` (0.8617), `0.55` (0.8617) | current run |
| `epsilon_min_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617) | current run |
| `epsilon_steps` | Zombie | 0.0000 | 0.0000 | 100.0% | `9` (0.8617) | current run |
| `merge_fragmented_contours` | Zombie | 0.0000 | 0.0000 | 100.0% | `true` (0.8617) | current run |
| `minimum_component_score` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.05` (0.8617), `0.12` (0.8617) | current run |
| `rectangularity_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8617) | current run |

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

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 6 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.8% |
| Est. serial runtime for full parameter set evaluation* | 55.1s |
| Fully successful parameter sets | 5 (45.5%) |
| Best Avg IoU | 0.8498 |
| Minimum Avg IoU | 0.6586 |
| Avg IoU StdDev | 0.0846 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 94 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 1458 | 100.0% | 55.5s | 1.0× |
| Exhaustive | 1458 | 100.0% | 55.5s | 1.0× |
| Non-dormant | 192 | 13.2% | 7.3s | 7.6× |
| Low+ | 192 | 13.2% | 7.3s | 7.6× |
| Moderate+ | 64 | 4.4% | 2.4s | 22.8× |
| Important+ | 64 | 4.4% | 2.4s | 22.8× |
| Critical | 8 | 0.5% | 304 ms | 182.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `merge_fragmented_contours` | Critical | 0.9961 | 0.1695 | 50.0% | `true` (0.8391), `false` (0.6697) | current run |
| `close_iterations` | Critical | 0.1487 | 0.1134 | 50.0% | `2` (0.8498), `0` (0.7364) | current run |
| `close_kernel_fraction` | Critical | 0.1487 | 0.1134 | 50.0% | `0.018` (0.8498), `0` (0.7364) | current run |
| `rectangularity_weight` | Important | 0.0905 | 0.0529 | 50.0% | `0.1` (0.7659), `0.25` (0.7130) | current run |
| `minimum_contour_area_fraction` | Important | 0.0776 | 0.0819 | 50.0% | `0.06` (0.7541), `0.12` (0.6722) | current run |
| `polygon_epsilon_fraction` | Important | 0.0776 | 0.0819 | 50.0% | `0.008` (0.7541), `0.018` (0.6722) | current run |
| `bbox_padding_fraction` | Low | 0.0114 | 0.0201 | 33.3% | `0.005` (0.7579), `0.015` (0.7462), `0` (0.7379) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `close_iterations` × `minimum_contour_area_fraction` | 0.2069 | 0.0582 | 11 |
| `close_iterations` × `polygon_epsilon_fraction` | 0.2069 | 0.0582 | 11 |
| `close_kernel_fraction` × `minimum_contour_area_fraction` | 0.2069 | 0.0582 | 11 |
| `close_kernel_fraction` × `polygon_epsilon_fraction` | 0.2069 | 0.0582 | 11 |
| `close_iterations` × `rectangularity_weight` | 0.1949 | 0.0462 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9658 | 0.9533 | 0.9734 | 0.0071 | 100.0% |
| 5 | 0.4953 | 0.4784 | 0.5457 | 0.0214 | 100.0% |
| 6 | 0.3815 | 0.0000 | 0.8763 | 0.4181 | 45.5% |
| 9 | 0.9411 | 0.9018 | 0.9585 | 0.0205 | 100.0% |
| 10 | 0.9497 | 0.9200 | 0.9593 | 0.0143 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="kraken-page-mask-krakenpagemask"></a>
<details>
<summary><strong>Kraken Page Mask (`kraken_page_mask`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 10000 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 7m 26s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8396 |
| Minimum Avg IoU | 0.8068 |
| Avg IoU StdDev | 0.0081 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 92 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 10000 | 100.0% | 7m 26s | 1.0× |
| Exhaustive | 10000 | 100.0% | 7m 26s | 1.0× |
| Non-dormant | 240 | 2.4% | 10.7s | 41.7× |
| Low+ | 240 | 2.4% | 10.7s | 41.7× |
| Moderate+ | 240 | 2.4% | 10.7s | 41.7× |
| Important+ | 120 | 1.2% | 5.4s | 83.3× |
| Critical | 120 | 1.2% | 5.4s | 83.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `dilation_fraction` | Critical | 1.0000 | 0.0328 | 33.3% | `0.02` (0.8396), `0` (0.8336), `0.01` (0.8068) | current run |
| `close_kernel_fraction` | Critical | 0.9552 | 0.0274 | 50.0% | `0` (0.8342), `0.006` (0.8068) | current run |
| `include_lines` | Critical | 0.9552 | 0.0274 | 50.0% | `0` (0.8342), `1` (0.8068) | current run |
| `page_padding_fraction` | Critical | 0.9552 | 0.0274 | 50.0% | `0` (0.8342), `0.05` (0.8068) | current run |
| `minimum_page_area_fraction` | Critical | 0.3048 | 0.0119 | 20.0% | `0.25` (0.8366), `0.08` (0.8336), `0.16` (0.8336) | current run |
| `fill_holes` | Moderate | 0.0461 | 0.0035 | 50.0% | `0` (0.8336), `1` (0.8302) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_page_area_fraction` × `fill_holes` | 0.4972 | 0.1925 | 11 |
| `close_kernel_fraction` × `minimum_page_area_fraction` | 0.9751 | 0.0199 | 11 |
| `include_lines` × `minimum_page_area_fraction` | 0.9751 | 0.0199 | 11 |
| `page_padding_fraction` × `minimum_page_area_fraction` | 0.9751 | 0.0199 | 11 |
| `close_kernel_fraction` × `fill_holes` | 0.9602 | 0.0050 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9674 | 0.8769 | 0.9772 | 0.0287 | 100.0% |
| 5 | 0.5348 | 0.5226 | 0.6201 | 0.0290 | 100.0% |
| 6 | 0.7661 | 0.7560 | 0.8310 | 0.0229 | 100.0% |
| 9 | 0.9411 | 0.8437 | 0.9525 | 0.0312 | 100.0% |
| 10 | 0.9494 | 0.8625 | 0.9599 | 0.0280 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-segmentation-grabcut"></a>
<details>
<summary><strong>GrabCut Segmentation (`grabcut`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 13122 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 5d 4h 9m 21s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8394 |
| Minimum Avg IoU | 0.7400 |
| Avg IoU StdDev | 0.0337 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1m 3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 13122 | 100.0% | 5d 4h 15m 36s | 1.0× |
| Exhaustive | 13122 | 100.0% | 5d 4h 15m 36s | 1.0× |
| Non-dormant | 1944 | 14.8% | 18h 24m 32s | 6.8× |
| Low+ | 1944 | 14.8% | 18h 24m 32s | 6.8× |
| Moderate+ | 1944 | 14.8% | 18h 24m 32s | 6.8× |
| Important+ | 1944 | 14.8% | 18h 24m 32s | 6.8× |
| Critical | 648 | 4.9% | 6h 8m 11s | 20.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `erosion_iterations` | Critical | 1.0000 | 0.0994 | 33.3% | `2` (0.8394), `1` (0.8130), `0` (0.7400) | current run |
| `grabcut_iterations` | Critical | 1.0000 | 0.0994 | 33.3% | `5` (0.8394), `3` (0.8130), `1` (0.7400) | current run |
| `minimum_bbox_area_fraction` | Critical | 1.0000 | 0.0994 | 33.3% | `0.15` (0.8394), `0.1` (0.8130), `0.07` (0.7400) | current run |
| `border_fraction` | Critical | 0.2893 | 0.0631 | 50.0% | `0.02` (0.8130), `0.01` (0.7499) | current run |
| `close_kernel_fraction` | Critical | 0.2893 | 0.0631 | 50.0% | `0.02` (0.8130), `0.01` (0.7499) | current run |
| `erosion_kernel_fraction` | Critical | 0.2893 | 0.0631 | 50.0% | `0.015` (0.8130), `0.0075` (0.7499) | current run |
| `polygon_epsilon_fraction` | Critical | 0.2593 | 0.0345 | 33.3% | `0.018` (0.7745), `0.01` (0.7400), `0.03` (0.7400) | current run |
| `minimum_contour_area_fraction` | Important | 0.0880 | 0.0248 | 33.3% | `0.02` (0.7648), `0.04` (0.7583), `0.07` (0.7400) | current run |
| `close_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.7557) | current run |

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
| 1 | 0.9609 | 0.9568 | 0.9617 | 0.0017 | 100.0% |
| 5 | 0.3929 | 0.3516 | 0.6041 | 0.0883 | 100.0% |
| 6 | 0.5283 | 0.4895 | 0.7378 | 0.0837 | 100.0% |
| 9 | 0.9432 | 0.9422 | 0.9433 | 0.0003 | 100.0% |
| 10 | 0.9531 | 0.9447 | 0.9540 | 0.0027 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="distance-transform-detector-distancetransform"></a>
<details>
<summary><strong>Distance Transform Detector (`distance_transform`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 31m 42s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8388 |
| Minimum Avg IoU | 0.7593 |
| Avg IoU StdDev | 0.0221 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.8s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (27.3%) |
| Equivalent-best configurations (within 0.0001) | 3 (27.3%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 31m 52s | 1.0× |
| Exhaustive | 2187 | 100.0% | 31m 52s | 1.0× |
| Non-dormant | 288 | 13.2% | 4m 12s | 7.6× |
| Low+ | 288 | 13.2% | 4m 12s | 7.6× |
| Moderate+ | 288 | 13.2% | 4m 12s | 7.6× |
| Important+ | 288 | 13.2% | 4m 12s | 7.6× |
| Critical | 96 | 4.4% | 1m 24s | 22.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `close_kernel_fraction` | Critical | 0.9880 | 0.0763 | 50.0% | `0` (0.8357), `0.008` (0.7593) | current run |
| `distance_threshold_fraction` | Critical | 0.9880 | 0.0763 | 50.0% | `0.1` (0.8357), `0.18` (0.7593) | current run |
| `minimum_component_core_overlap` | Critical | 0.9880 | 0.0763 | 50.0% | `0.03` (0.8357), `0.08` (0.7593) | current run |
| `minimum_core_area_fraction` | Critical | 0.9880 | 0.0763 | 50.0% | `0.004` (0.8357), `0.01` (0.7593) | current run |
| `minimum_bbox_area_fraction` | Critical | 0.4418 | 0.0380 | 50.0% | `0.1` (0.8356), `0.16` (0.7976) | current run |
| `minimum_rectangularity` | Critical | 0.1734 | 0.0191 | 100.0% | `0.35` (0.8357), `0.7` (0.8356), `0.5` (0.8166) | current run |
| `bbox_padding_fraction` | Important | 0.1261 | 0.0182 | 33.3% | `0.008` (0.8388), `0.016` (0.8323), `0` (0.8205) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_bbox_area_fraction` × `minimum_rectangularity` | 0.9880 | 0.5462 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9630 | 0.9496 | 0.9734 | 0.0089 | 100.0% |
| 5 | 0.4956 | 0.4784 | 0.5197 | 0.0173 | 100.0% |
| 6 | 0.8075 | 0.4357 | 0.8772 | 0.1199 | 100.0% |
| 9 | 0.9336 | 0.8982 | 0.9585 | 0.0252 | 100.0% |
| 10 | 0.9438 | 0.9165 | 0.9593 | 0.0177 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="star-convex-boundary-optimization-starconvex"></a>
<details>
<summary><strong>Star-Convex Boundary Optimization (`star_convex`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 1m 1s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8179 |
| Minimum Avg IoU | 0.7597 |
| Avg IoU StdDev | 0.0191 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 151 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 1m 2s | 1.0× |
| Exhaustive | 729 | 100.0% | 1m 2s | 1.0× |
| Non-dormant | 243 | 33.3% | 20.5s | 3.0× |
| Low+ | 243 | 33.3% | 20.5s | 3.0× |
| Moderate+ | 243 | 33.3% | 20.5s | 3.0× |
| Important+ | 243 | 33.3% | 20.5s | 3.0× |
| Critical | 81 | 11.1% | 6.8s | 9.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `smoothing_window` | Critical | 0.8478 | 0.0376 | 33.3% | `1` (0.8007), `5` (0.7651), `9` (0.7631) | current run |
| `minimum_radius_fraction` | Critical | 0.4494 | 0.0447 | 33.3% | `0.16` (0.8179), `0.1` (0.7756), `0.05` (0.7732) | current run |
| `minimum_support_fraction` | Critical | 0.4494 | 0.0447 | 33.3% | `0.7` (0.8179), `0.55` (0.7756), `0.4` (0.7732) | current run |
| `ray_count` | Critical | 0.4494 | 0.0447 | 33.3% | `360` (0.8179), `180` (0.7756), `90` (0.7732) | current run |
| `bbox_padding_fraction` | Important | 0.0634 | 0.0115 | 33.3% | `0` (0.7822), `0.008` (0.7764), `0.016` (0.7707) | current run |
| `maximum_radius_fraction` | Dormant | 0.0010 | 0.0021 | 50.0% | `0.6` (0.7777), `0.72` (0.7756) | current run |

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

`maximum_radius_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `smoothing_window` × `minimum_radius_fraction` | 0.9832 | 0.1354 | 11 |
| `smoothing_window` × `minimum_support_fraction` | 0.9832 | 0.1354 | 11 |
| `smoothing_window` × `ray_count` | 0.9832 | 0.1354 | 11 |
| `smoothing_window` × `bbox_padding_fraction` | 0.9131 | 0.0653 | 11 |
| `smoothing_window` × `maximum_radius_fraction` | 0.8850 | 0.0373 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9730 | 0.9414 | 0.9881 | 0.0134 | 100.0% |
| 5 | 0.5707 | 0.5353 | 0.6026 | 0.0210 | 100.0% |
| 6 | 0.4581 | 0.3702 | 0.6626 | 0.0928 | 100.0% |
| 9 | 0.9323 | 0.8941 | 0.9591 | 0.0240 | 100.0% |
| 10 | 0.9534 | 0.9260 | 0.9726 | 0.0174 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="connected-components-components"></a>
<details>
<summary><strong>Connected Components (`components`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 19683 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 7m 45s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.7897 |
| Minimum Avg IoU | 0.7185 |
| Avg IoU StdDev | 0.0253 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 53 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 19683 | 100.0% | 7m 45s | 1.0× |
| Exhaustive | 19683 | 100.0% | 7m 45s | 1.0× |
| Non-dormant | 192 | 1.0% | 4.5s | 102.5× |
| Low+ | 192 | 1.0% | 4.5s | 102.5× |
| Moderate+ | 96 | 0.5% | 2.3s | 205.0× |
| Important+ | 96 | 0.5% | 2.3s | 205.0× |
| Critical | 96 | 0.5% | 2.3s | 205.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `morphology_dilate_fraction` | Critical | 0.6669 | 0.0522 | 33.3% | `0.03` (0.7820), `0.015` (0.7597), `0.008` (0.7298) | current run |
| `merge_area_ratio` | Critical | 0.2651 | 0.0452 | 50.0% | `0.01` (0.7637), `0.02` (0.7185) | current run |
| `minimum_bbox_area_fraction` | Critical | 0.2651 | 0.0452 | 50.0% | `0.08` (0.7637), `0.12` (0.7185) | current run |
| `minimum_component_area_fraction` | Critical | 0.2651 | 0.0452 | 50.0% | `0.00075` (0.7637), `0.0015` (0.7185) | current run |
| `minimum_component_area_px` | Critical | 0.2651 | 0.0452 | 50.0% | `10` (0.7637), `25` (0.7185) | current run |
| `minimum_selected_area_fraction` | Critical | 0.2651 | 0.0452 | 50.0% | `0.02` (0.7637), `0.04` (0.7185) | current run |
| `merge_gap_fraction` | Low | 0.0106 | 0.0067 | 50.0% | `0.02` (0.7609), `0.035` (0.7541) | current run |
| `morphology_close_fraction` | Dormant | 0.0028 | 0.0027 | 33.3% | `0.016` (0.7609), `0.004` (0.7609), `0.008` (0.7582) | current run |
| `bbox_padding_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.7596) | current run |

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

`morphology_close_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `morphology_dilate_fraction` × `merge_area_ratio` | 0.9887 | 0.3218 | 11 |
| `morphology_dilate_fraction` × `minimum_bbox_area_fraction` | 0.9887 | 0.3218 | 11 |
| `morphology_dilate_fraction` × `minimum_component_area_fraction` | 0.9887 | 0.3218 | 11 |
| `morphology_dilate_fraction` × `minimum_component_area_px` | 0.9887 | 0.3218 | 11 |
| `morphology_dilate_fraction` × `minimum_selected_area_fraction` | 0.9887 | 0.3218 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9661 | 0.9533 | 0.9734 | 0.0097 | 100.0% |
| 5 | 0.5518 | 0.4973 | 0.5725 | 0.0211 | 100.0% |
| 6 | 0.4169 | 0.2352 | 0.6018 | 0.1425 | 100.0% |
| 9 | 0.9238 | 0.9018 | 0.9429 | 0.0172 | 100.0% |
| 10 | 0.9397 | 0.9192 | 0.9543 | 0.0156 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="line-segment-detector-lsd"></a>
<details>
<summary><strong>Line Segment Detector (`lsd`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 59m 4s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7378 |
| Minimum Avg IoU | 0.5414 |
| Avg IoU StdDev | 0.0549 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (36.4%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 59m 22s | 1.0× |
| Exhaustive | 2187 | 100.0% | 59m 22s | 1.0× |
| Non-dormant | 432 | 19.8% | 11m 44s | 5.1× |
| Low+ | 432 | 19.8% | 11m 44s | 5.1× |
| Moderate+ | 432 | 19.8% | 11m 44s | 5.1× |
| Important+ | 432 | 19.8% | 11m 44s | 5.1× |
| Critical | 432 | 19.8% | 11m 44s | 5.1× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_length_fraction` | Critical | 0.9801 | 0.1964 | 66.7% | `0.22` (0.7378), `0.08` (0.7294), `0.14` (0.5414) | current run |
| `axis_angle_tolerance_degrees` | Critical | 0.9782 | 0.1888 | 50.0% | `10` (0.7302), `18` (0.5414) | current run |
| `outer_percentile` | Critical | 0.9782 | 0.1888 | 50.0% | `5` (0.7302), `10` (0.5414) | current run |
| `refine_mode` | Critical | 0.9782 | 0.1888 | 50.0% | `none` (0.7302), `std` (0.5414) | current run |
| `scale` | Critical | 0.3984 | 0.0898 | 100.0% | `0.6` (0.7294), `0.8` (0.6396) | current run |
| `minimum_bbox_area_fraction` | Critical | 0.1786 | 0.0491 | 100.0% | `0.08` (0.7315), `0.15` (0.7294), `0.1` (0.6824) | current run |
| `bbox_padding_fraction` | Critical | 0.1606 | 0.0512 | 33.3% | `0.005` (0.7371), `0.015` (0.7174), `0` (0.6858) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `scale` × `minimum_bbox_area_fraction` | 0.9801 | 0.5817 | 11 |
| `axis_angle_tolerance_degrees` × `scale` | 0.9801 | 0.0019 | 11 |
| `outer_percentile` × `scale` | 0.9801 | 0.0019 | 11 |
| `refine_mode` × `scale` | 0.9801 | 0.0019 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8984 | 0.8828 | 0.9102 | 0.0107 | 100.0% |
| 5 | 0.8847 | 0.0000 | 0.9850 | 0.2798 | 90.9% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8344 | 0.8091 | 0.8475 | 0.0157 | 100.0% |
| 10 | 0.9479 | 0.9209 | 0.9641 | 0.0168 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="convex-hull-detector-convexhull"></a>
<details>
<summary><strong>Convex Hull Detector (`convex_hull`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 28.3s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7325 |
| Minimum Avg IoU | 0.6633 |
| Avg IoU StdDev | 0.0193 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 46 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (36.4%) |
| Equivalent-best configurations (within 0.0001) | 4 (36.4%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 28.4s | 1.0× |
| Exhaustive | 2187 | 100.0% | 28.4s | 1.0× |
| Non-dormant | 288 | 13.2% | 3.7s | 7.6× |
| Low+ | 288 | 13.2% | 3.7s | 7.6× |
| Moderate+ | 288 | 13.2% | 3.7s | 7.6× |
| Important+ | 288 | 13.2% | 3.7s | 7.6× |
| Critical | 96 | 4.4% | 1.2s | 22.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `close_iterations` | Critical | 0.8357 | 0.0614 | 50.0% | `0` (0.7246), `1` (0.6633) | current run |
| `close_kernel_fraction` | Critical | 0.8357 | 0.0614 | 50.0% | `0` (0.7246), `0.008` (0.6633) | current run |
| `minimum_fragment_area_fraction` | Critical | 0.8357 | 0.0614 | 50.0% | `0.0002` (0.7246), `0.0005` (0.6633) | current run |
| `minimum_hull_area_fraction` | Critical | 0.8357 | 0.0614 | 50.0% | `0.1` (0.7246), `0.16` (0.6633) | current run |
| `minimum_solidity` | Critical | 0.2680 | 0.0259 | 100.0% | `0.35` (0.7238), `0.55` (0.6979) | current run |
| `polygon_epsilon_fraction` | Critical | 0.1684 | 0.0173 | 100.0% | `0.012` (0.7259), `0.05` (0.7238), `0.025` (0.7086) | current run |
| `bbox_padding_fraction` | Important | 0.0650 | 0.0133 | 33.3% | `0.008` (0.7261), `0` (0.7186), `0.016` (0.7128) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_solidity` × `polygon_epsilon_fraction` | 0.8523 | 0.5843 | 11 |
| `close_iterations` × `minimum_solidity` | 0.8523 | 0.0166 | 11 |
| `close_kernel_fraction` × `minimum_solidity` | 0.8523 | 0.0166 | 11 |
| `minimum_fragment_area_fraction` × `minimum_solidity` | 0.8523 | 0.0166 | 11 |
| `minimum_hull_area_fraction` × `minimum_solidity` | 0.8523 | 0.0166 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8597 | 0.8461 | 0.8668 | 0.0086 | 100.0% |
| 5 | 0.8581 | 0.5316 | 0.9030 | 0.1038 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9336 | 0.8982 | 0.9585 | 0.0252 | 100.0% |
| 10 | 0.9438 | 0.9165 | 0.9593 | 0.0177 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="border-energy-validator-borderenergy"></a>
<details>
<summary><strong>Border Energy Validator (`border_energy`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 2h 13m 21s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7250 |
| Minimum Avg IoU | 0.3651 |
| Avg IoU StdDev | 0.1054 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 2.4s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 6561 | 100.0% | 2h 13m 33s | 1.0× |
| Exhaustive | 6561 | 100.0% | 2h 13m 33s | 1.0× |
| Non-dormant | 864 | 13.2% | 17m 35s | 7.6× |
| Low+ | 864 | 13.2% | 17m 35s | 7.6× |
| Moderate+ | 27 | 0.4% | 33s | 243.0× |
| Important+ | 9 | 0.1% | 11s | 729.0× |
| Critical | 9 | 0.1% | 11s | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_side_consistency` | Critical | 0.8208 | 0.2318 | 33.3% | `0.3` (0.5969), `0.45` (0.5542), `0.6` (0.3651) | current run |
| `band_fraction` | Critical | 0.4147 | 0.2339 | 33.3% | `0.015` (0.7250), `0.008` (0.5542), `0.004` (0.4912) | current run |
| `energy_weight` | Moderate | 0.0545 | 0.0585 | 33.3% | `0.3` (0.5496), `0.4` (0.5069), `0.5` (0.4912) | current run |
| `epsilon_max_fraction` | Low | 0.0117 | 0.0396 | 50.0% | `0.04` (0.5542), `0.03` (0.5146) | current run |
| `gaussian_sigma` | Low | 0.0117 | 0.0396 | 50.0% | `1.2` (0.5542), `0.8` (0.5146) | current run |
| `minimum_border_energy` | Low | 0.0117 | 0.0396 | 50.0% | `0.1` (0.5542), `0.05` (0.5146) | current run |
| `minimum_contour_area_fraction` | Low | 0.0117 | 0.0396 | 50.0% | `0.12` (0.5542), `0.08` (0.5146) | current run |
| `minimum_rectangularity` | Low | 0.0117 | 0.0396 | 50.0% | `0.55` (0.5542), `0.45` (0.5146) | current run |
| `consistency_weight` | Low | 0.0106 | 0.0000 | 0.0% | `0.15` (0.5542) | current run |
| `contour_weight` | Low | 0.0106 | 0.0000 | 0.0% | `0.45` (0.5542) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_side_consistency` × `band_fraction` | 1.0000 | 0.1792 | 11 |
| `minimum_side_consistency` × `energy_weight` | 0.8805 | 0.0597 | 11 |
| `energy_weight` × `epsilon_max_fraction` | 0.0789 | 0.0244 | 11 |
| `energy_weight` × `gaussian_sigma` | 0.0789 | 0.0244 | 11 |
| `energy_weight` × `minimum_border_energy` | 0.0789 | 0.0244 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0777 | 0.0000 | 0.8542 | 0.2456 | 9.1% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.6876 | 0.0000 | 0.9454 | 0.4210 | 72.7% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="distance-transform-rectangle-proposal-distancetransformrect"></a>
<details>
<summary><strong>Distance-Transform Rectangle Proposal (`distance_transform_rect`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 10 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 1m 39s |
| Fully successful parameter sets | 1 (9.1%) |
| Best Avg IoU | 0.7243 |
| Minimum Avg IoU | 0.6310 |
| Avg IoU StdDev | 0.0254 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 262 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 1m 41s | 1.0× |
| Exhaustive | 729 | 100.0% | 1m 41s | 1.0× |
| Non-dormant | 216 | 29.6% | 29.9s | 3.4× |
| Low+ | 216 | 29.6% | 29.9s | 3.4× |
| Moderate+ | 216 | 29.6% | 29.9s | 3.4× |
| Important+ | 18 | 2.5% | 2.5s | 40.5× |
| Critical | 18 | 2.5% | 2.5s | 40.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `distance_threshold_fraction` | Critical | 0.8642 | 0.0896 | 33.3% | `0.3` (0.7243), `0.1` (0.6435), `0.18` (0.6347) | current run |
| `proposal_expansion_fraction` | Critical | 0.2979 | 0.0359 | 50.0% | `0.12` (0.6795), `0.06` (0.6435) | current run |
| `minimum_bbox_area_fraction` | Critical | 0.1664 | 0.0224 | 33.3% | `0.22` (0.6637), `0.08` (0.6435), `0.14` (0.6413) | current run |
| `minimum_core_area_fraction` | Moderate | 0.0368 | 0.0170 | 50.0% | `0.002` (0.6516), `0.006` (0.6347) | current run |
| `minimum_mask_coverage` | Moderate | 0.0368 | 0.0170 | 50.0% | `0.06` (0.6516), `0.12` (0.6347) | current run |
| `bbox_padding_fraction` | Moderate | 0.0303 | 0.0111 | 33.3% | `0.016` (0.6543), `0` (0.6509), `0.008` (0.6433) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `proposal_expansion_fraction` × `bbox_padding_fraction` | 1.0000 | 0.7021 | 11 |
| `proposal_expansion_fraction` × `minimum_bbox_area_fraction` | 0.8642 | 0.5663 | 11 |
| `proposal_expansion_fraction` × `minimum_core_area_fraction` | 0.8642 | 0.5663 | 11 |
| `proposal_expansion_fraction` × `minimum_mask_coverage` | 0.8642 | 0.5663 | 11 |
| `minimum_bbox_area_fraction` × `bbox_padding_fraction` | 0.3535 | 0.1871 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9043 | 0.8697 | 0.9520 | 0.0245 | 100.0% |
| 5 | 0.4946 | 0.4499 | 0.5131 | 0.0174 | 100.0% |
| 6 | 0.0411 | 0.0000 | 0.4523 | 0.1300 | 9.1% |
| 9 | 0.8955 | 0.8682 | 0.9256 | 0.0213 | 100.0% |
| 10 | 0.9150 | 0.8788 | 0.9433 | 0.0220 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="hough-line-borders-hough"></a>
<details>
<summary><strong>Hough Line Borders (`hough`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 3 of 8 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2188 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 53m 30s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.6050 |
| Minimum Avg IoU | 0.3084 |
| Avg IoU StdDev | 0.1011 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 53m 44s | 1.0× |
| Exhaustive | 2187 | 100.0% | 53m 44s | 1.0× |
| Non-dormant | 108 | 4.9% | 2m 39s | 20.2× |
| Low+ | 108 | 4.9% | 2m 39s | 20.2× |
| Moderate+ | 108 | 4.9% | 2m 39s | 20.2× |
| Important+ | 36 | 1.6% | 53.1s | 60.8× |
| Critical | 9 | 0.4% | 13.3s | 243.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `outer_percentile` | Critical | 0.9781 | 0.2513 | 33.3% | `5` (0.5691), `10` (0.4874), `20` (0.3177) | current run |
| `canny_low_threshold` | Critical | 0.1805 | 0.1500 | 33.3% | `65` (0.6050), `40` (0.4784), `25` (0.4551) | current run |
| `hough_threshold_fraction` | Important | 0.1093 | 0.0867 | 50.0% | `0.055` (0.5417), `0.035` (0.4551) | current run |
| `maximum_gap_fraction` | Important | 0.1093 | 0.0867 | 50.0% | `0.055` (0.5417), `0.025` (0.4551) | current run |
| `bbox_padding_fraction` | Moderate | 0.0502 | 0.0476 | 33.3% | `0.015` (0.5008), `0` (0.4541), `0.005` (0.4532) | current run |
| `axis_angle_tolerance_degrees` | Dormant | 0.0006 | 0.0084 | 50.0% | `22` (0.4784), `12` (0.4701) | current run |
| `minimum_length_fraction` | Dormant | 0.0006 | 0.0084 | 50.0% | `0.2` (0.4784), `0.12` (0.4701) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0005 | 0.0000 | 0.0% | `0.1` (0.4784) | current run |

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

`axis_angle_tolerance_degrees`, `minimum_length_fraction`, `minimum_bbox_area_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `hough_threshold_fraction` × `bbox_padding_fraction` | 0.1860 | 0.0767 | 11 |
| `maximum_gap_fraction` × `bbox_padding_fraction` | 0.1860 | 0.0767 | 11 |
| `hough_threshold_fraction` × `axis_angle_tolerance_degrees` | 0.1805 | 0.0712 | 11 |
| `maximum_gap_fraction` × `axis_angle_tolerance_degrees` | 0.1805 | 0.0712 | 11 |
| `outer_percentile` × `canny_low_threshold` | 0.9944 | 0.0163 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.6759 | 0.4658 | 0.8453 | 0.1390 | 100.0% |
| 5 | 0.2418 | 0.0000 | 0.5446 | 0.1642 | 72.7% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.7038 | 0.4958 | 0.8188 | 0.1219 | 100.0% |
| 10 | 0.7326 | 0.5805 | 0.8305 | 0.0927 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="projective-gradient-vote-projectivegradientvote"></a>
<details>
<summary><strong>Projective Gradient Vote (`projective_gradient_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 730 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 10m 8s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5541 |
| Minimum Avg IoU | 0.4474 |
| Avg IoU StdDev | 0.0287 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.7s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 10m 17s | 1.0× |
| Exhaustive | 729 | 100.0% | 10m 17s | 1.0× |
| Non-dormant | 324 | 44.4% | 4m 34s | 2.2× |
| Low+ | 324 | 44.4% | 4m 34s | 2.2× |
| Moderate+ | 324 | 44.4% | 4m 34s | 2.2× |
| Important+ | 324 | 44.4% | 4m 34s | 2.2× |
| Critical | 108 | 14.8% | 1m 31s | 6.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gaussian_sigma` | Critical | 1.0000 | 0.1067 | 33.3% | `1.8` (0.5541), `0.8` (0.5463), `1.2` (0.4474) | current run |
| `minimum_segment_fraction` | Critical | 1.0000 | 0.1067 | 33.3% | `0.24` (0.5541), `0.1` (0.5463), `0.16` (0.4474) | current run |
| `family_tolerance_degrees` | Critical | 0.9940 | 0.0996 | 50.0% | `10` (0.5471), `16` (0.4474) | current run |
| `angle_bin_degrees` | Critical | 0.9036 | 0.0000 | 0.0% | `4` (0.4474) | current run |
| `area_weight` | Critical | 0.9036 | 0.0000 | 0.0% | `0.15` (0.4474) | current run |
| `bbox_padding_fraction` | Critical | 0.9036 | 0.0000 | 0.0% | `0` (0.4474) | current run |
| `geometry_weight` | Critical | 0.9036 | 0.0000 | 0.0% | `0.3` (0.4474) | current run |
| `maximum_area_fraction` | Critical | 0.9036 | 0.0000 | 0.0% | `0.98` (0.4474) | current run |
| `maximum_corner_overshoot_fraction` | Critical | 0.9036 | 0.0000 | 0.0% | `0.08` (0.4474) | current run |
| `minimum_area_fraction` | Critical | 0.9036 | 0.0000 | 0.0% | `0.18` (0.4474) | current run |
| `support_weight` | Critical | 0.9036 | 0.0000 | 0.0% | `0.55` (0.4474) | current run |
| `gradient_percentile` | Critical | 0.3735 | 0.0455 | 50.0% | `74` (0.5463), `82` (0.5008) | current run |
| `minimum_side_support` | Critical | 0.1877 | 0.0267 | 33.3% | `0.08` (0.5483), `0.3` (0.5463), `0.18` (0.5216) | current run |
| `orthogonality_tolerance_degrees` | Important | 0.0996 | 0.0182 | 33.3% | `12` (0.5463), `32` (0.5463), `22` (0.5281) | current run |

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
| 1 | 0.9201 | 0.9069 | 0.9698 | 0.0159 | 100.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8456 | 0.8393 | 0.8465 | 0.0022 | 100.0% |
| 10 | 0.9245 | 0.4910 | 0.9690 | 0.1371 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="consensus-quadrilateral-consensusquad"></a>
<details>
<summary><strong>Consensus Quadrilateral (`consensus_quad`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 243 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 4.5% |
| Est. serial runtime for full parameter set evaluation* | 2m 14s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5528 |
| Minimum Avg IoU | 0.3651 |
| Avg IoU StdDev | 0.0720 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.2s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 243 | 100.0% | 2m 20s | 1.0× |
| Exhaustive | 243 | 100.0% | 2m 20s | 1.0× |
| Non-dormant | 108 | 44.4% | 1m 2s | 2.2× |
| Low+ | 108 | 44.4% | 1m 2s | 2.2× |
| Moderate+ | 108 | 44.4% | 1m 2s | 2.2× |
| Important+ | 108 | 44.4% | 1m 2s | 2.2× |
| Critical | 12 | 4.9% | 6.9s | 20.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `contour_quad_weight` | Critical | 1.0000 | 0.1875 | 33.3% | `0.75` (0.5528), `0.5` (0.5513), `0.25` (0.3653) | current run |
| `maximum_mean_corner_distance_fraction` | Critical | 1.0000 | 0.1868 | 50.0% | `0.025` (0.5520), `0.015` (0.3653) | current run |
| `minimum_polygon_iou` | Critical | 0.4456 | 0.1673 | 50.0% | `0.9` (0.5513), `0.8` (0.3840) | current run |
| `minimum_consensus_confidence` | Important | 0.0833 | 0.0469 | 33.3% | `0.1` (0.4121), `0.2` (0.4118), `0.35` (0.3653) | current run |
| `edge_contour_weight` | Important | 0.0825 | 0.0467 | 33.3% | `0.25` (0.4121), `0.5` (0.4116), `0.75` (0.3654) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_consensus_confidence` × `edge_contour_weight` | 0.3883 | 0.3050 | 11 |
| `minimum_polygon_iou` × `edge_contour_weight` | 0.5380 | 0.0924 | 11 |
| `minimum_polygon_iou` × `minimum_consensus_confidence` | 0.5380 | 0.0924 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.8619 | 0.8616 | 0.8624 | 0.0004 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9643 | 0.9636 | 0.9647 | 0.0005 | 100.0% |
| 10 | 0.1699 | 0.0000 | 0.9386 | 0.3604 | 18.2% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="radon-boundary-projection-radonboundary"></a>
<details>
<summary><strong>Radon Boundary Projection (`radon_boundary`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 2 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 7m 24s |
| Fully successful parameter sets | 8 (72.7%) |
| Best Avg IoU | 0.4983 |
| Minimum Avg IoU | 0.2986 |
| Avg IoU StdDev | 0.0738 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.5s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 7m 30s | 1.0× |
| Exhaustive | 729 | 100.0% | 7m 30s | 1.0× |
| Non-dormant | 54 | 7.4% | 33.4s | 13.5× |
| Low+ | 54 | 7.4% | 33.4s | 13.5× |
| Moderate+ | 54 | 7.4% | 33.4s | 13.5× |
| Important+ | 18 | 2.5% | 11.1s | 40.5× |
| Critical | 3 | 0.4% | 1.9s | 243.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_peak_prominence` | Critical | 0.9422 | 0.1718 | 33.3% | `1.05` (0.4716), `1.25` (0.4526), `1.6` (0.2998) | current run |
| `edge_percentile` | Important | 0.1278 | 0.0920 | 33.3% | `90` (0.4983), `82` (0.4227), `75` (0.4063) | current run |
| `angle_step_degrees` | Important | 0.0802 | 0.0542 | 50.0% | `1` (0.4605), `0.5` (0.4063) | current run |
| `bbox_padding_fraction` | Moderate | 0.0317 | 0.0286 | 33.3% | `0.016` (0.4334), `0.008` (0.4081), `0` (0.4048) | current run |
| `angle_limit_degrees` | Dormant | 0.0008 | 0.0072 | 50.0% | `8` (0.4227), `4` (0.4155) | current run |
| `projection_smooth_fraction` | Dormant | 0.0008 | 0.0072 | 50.0% | `0.012` (0.4227), `0.006` (0.4155) | current run |

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

`angle_limit_degrees`, `projection_smooth_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `angle_step_degrees` × `bbox_padding_fraction` | 0.1323 | 0.0521 | 11 |
| `minimum_peak_prominence` × `edge_percentile` | 0.9933 | 0.0511 | 11 |
| `angle_step_degrees` × `angle_limit_degrees` | 0.1278 | 0.0477 | 11 |
| `angle_step_degrees` × `projection_smooth_fraction` | 0.1278 | 0.0477 | 11 |
| `minimum_peak_prominence` × `bbox_padding_fraction` | 0.9831 | 0.0409 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.1475 | 0.0000 | 0.2732 | 0.1023 | 72.7% |
| 5 | 0.5174 | 0.4147 | 0.5425 | 0.0352 | 100.0% |
| 6 | 0.9714 | 0.9507 | 0.9871 | 0.0159 | 100.0% |
| 9 | 0.1535 | 0.0000 | 0.4144 | 0.1154 | 72.7% |
| 10 | 0.2907 | 0.0000 | 0.4473 | 0.1845 | 72.7% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="joint-rectangle-voting-jointrectanglevote"></a>
<details>
<summary><strong>Joint Rectangle Voting (`joint_rectangle_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 16m 6s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.1980 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0569 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.1s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 16m 10s | 1.0× |
| Exhaustive | 2187 | 100.0% | 16m 10s | 1.0× |
| Non-dormant | 972 | 44.4% | 7m 11s | 2.2× |
| Low+ | 972 | 44.4% | 7m 11s | 2.2× |
| Moderate+ | 486 | 22.2% | 3m 36s | 4.5× |
| Important+ | 486 | 22.2% | 3m 36s | 4.5× |
| Critical | 54 | 2.5% | 24s | 40.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `canny_high` | Critical | 1.0000 | 0.1980 | 33.3% | `220` (0.1980), `100` (0.0000), `150` (0.0000) | current run |
| `canny_low` | Critical | 1.0000 | 0.1980 | 33.3% | `80` (0.1980), `30` (0.0000), `50` (0.0000) | current run |
| `hough_threshold` | Critical | 1.0000 | 0.1980 | 33.3% | `120` (0.1980), `50` (0.0000), `80` (0.0000) | current run |
| `minimum_side_support` | Critical | 0.4500 | 0.0990 | 50.0% | `0.18` (0.0990), `0.1` (0.0000) | current run |
| `bbox_padding_fraction` | Important | 0.1200 | 0.0396 | 33.3% | `0` (0.0396), `0.008` (0.0000), `0.016` (0.0000) | current run |
| `minimum_area_fraction` | Important | 0.1200 | 0.0396 | 33.3% | `0.16` (0.0396), `0.1` (0.0000), `0.24` (0.0000) | current run |
| `axis_tolerance_degrees` | Low | 0.0100 | 0.0198 | 50.0% | `6` (0.0198), `12` (0.0000) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `bbox_padding_fraction` × `minimum_area_fraction` | 0.2667 | 0.1467 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0900 | 0.0000 | 0.9899 | 0.2846 | 9.1% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="text-flow-envelope-textflow"></a>
<details>
<summary><strong>Text Flow Envelope (`text_flow`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 31.4s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.1634 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0582 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 95 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 31.8s | 1.0× |
| Exhaustive | 729 | 100.0% | 31.8s | 1.0× |
| Non-dormant | 144 | 19.8% | 6.3s | 5.1× |
| Low+ | 144 | 19.8% | 6.3s | 5.1× |
| Moderate+ | 144 | 19.8% | 6.3s | 5.1× |
| Important+ | 48 | 6.6% | 2.1s | 15.2× |
| Critical | 48 | 6.6% | 2.1s | 15.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_text_coverage_fraction` | Critical | 0.8962 | 0.1243 | 33.3% | `0.04` (0.1243), `0.08` (0.1233), `0.14` (0.0000) | current run |
| `line_join_fraction` | Critical | 0.3343 | 0.0873 | 50.0% | `0.03` (0.1615), `0.018` (0.0742) | current run |
| `maximum_component_area_fraction` | Critical | 0.1425 | 0.0765 | 50.0% | `0.01` (0.1596), `0.005` (0.0831) | current run |
| `minimum_component_area_fraction` | Critical | 0.1425 | 0.0765 | 50.0% | `2e-05` (0.1596), `1e-05` (0.0831) | current run |
| `minimum_line_count` | Critical | 0.1425 | 0.0765 | 50.0% | `3` (0.1596), `2` (0.0831) | current run |
| `bbox_padding_fraction` | Moderate | 0.0399 | 0.0276 | 33.3% | `0.04` (0.0988), `0.02` (0.0955), `0.01` (0.0712) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_text_coverage_fraction` × `line_join_fraction` | 0.9978 | 0.1016 | 11 |
| `minimum_text_coverage_fraction` × `maximum_component_area_fraction` | 0.9431 | 0.0469 | 11 |
| `minimum_text_coverage_fraction` × `minimum_component_area_fraction` | 0.9431 | 0.0469 | 11 |
| `minimum_text_coverage_fraction` × `minimum_line_count` | 0.9431 | 0.0469 | 11 |
| `maximum_component_area_fraction` × `bbox_padding_fraction` | 0.1867 | 0.0442 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.4502 | 0.0000 | 0.8170 | 0.2912 | 72.7% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="whitespace-frame-whitespaceframe"></a>
<details>
<summary><strong>Whitespace Frame (`whitespace_frame`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- Calibration did not produce a valid measurement: no evaluated page returned a usable detector candidate.
- The zero Avg IoU values are failure placeholders, not evidence of a flat calibration landscape or dormant parameters.
- Observed detector failure reasons: border_not_background (50).

#### Evidence of ROI

Do not expand or reduce the parameter search yet. Inspect detector inference/debug evidence and restore a valid overlap signal before drawing tuning-ROI conclusions.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 730 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 1.4% |
| Est. serial runtime for full parameter set evaluation* | 18.7s |
| Fully successful parameter sets | 0 (0.0%) |
| Calibration signal | no_valid_measurements |
| Best Avg IoU | 0.0000 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 10 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 10 (100.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

Withheld: effect-size reduction is not meaningful until calibration produces valid positive-overlap measurements.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="ransac-border-fit-ransac"></a>
<details>
<summary><strong>RANSAC Border Fit (`ransac`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- Calibration did not produce a valid measurement: no evaluated page returned a usable detector candidate.
- The zero Avg IoU values are failure placeholders, not evidence of a flat calibration landscape or dormant parameters.
- Observed detector failure reasons: AttributeError (55).

#### Evidence of ROI

Do not expand or reduce the parameter search yet. Inspect detector inference/debug evidence and restore a valid overlap signal before drawing tuning-ROI conclusions.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.8% |
| Est. serial runtime for full parameter set evaluation* | 4m 18s |
| Fully successful parameter sets | 0 (0.0%) |
| Calibration signal | no_valid_measurements |
| Best Avg IoU | 0.0000 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 11 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 11 (100.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

Withheld: effect-size reduction is not meaningful until calibration produces valid positive-overlap measurements.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

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
| Parameter sets evaluated | 445 | Total detector parameter configurations evaluated across all runs. |
| Golden Set page evaluations | 2225 | Parameter sets multiplied by evaluated Golden Set pages. |
| Aggregate detector runtime | 14m 42s | Sum of detector wall-clock runtimes; this is not the elapsed time experienced by the user. |
| Regression wall-clock span | 5m 5s | Earliest detector start through latest detector finish. |
| Effective detector concurrency | 2.89× | Aggregate detector runtime divided by regression wall-clock span. |
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
| Execution recommendation basis | runtime-index coherent build 32328295726 (41/41 detectors) |
| Pipeline start stagger | 0m |
| Runtime intelligence | `runtime-index.json` |
| Parallelism intelligence | `parallelism-index.json` |
| Calibration intelligence | `calibration-index.json` |

Detector pipelines pull continuously from one shared queue. Once a detector finishes, that pipeline immediately loads the next queued detector until the queue is empty.

| Queue | Detector | Pipeline | Estimated Runtime | Scheduling Basis |
|---:|---|---|---:|---|
| 1 | GrabCut + Contour (`grabcut_contour`) | 1 | 10m 50s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 2 | GrabCut Segmentation (`grabcut`) | 2 | 9m 11s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 3 | Kraken Page Mask (`kraken_page_mask`) | 3 | 8m 13s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 4 | Contour + GrabCut (`contour_grabcut`) | 4 | 3m 45s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 5 | Learned Page-Mask Detector (`learned_page_mask`) | 4 | 1m 21s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 6 | Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background (`amsre_bfq_spbv_pbg`) | 4 | 1m 7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 7 | Fusion Gen1 — MSRE + BFQ + SPBV + Page Background (`msre_bfq_spbv_pbg`) | 4 | 53.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 8 | Hough Line Borders (`hough`) | 4 | 51.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 9 | Adaptive Multi-Scale Radial Edge Search (`adaptive_multi_scale_radial_edge`) | 4 | 36.4s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 10 | dhSegment Page-Mask Detector (`dhsegment_page_mask`) | 3 | 34s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 11 | Doc-UFCN Page-Mask Detector (`doc_ufcn_page_mask`) | 4 | 28.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 12 | Consensus Quadrilateral (`consensus_quad`) | 3 | 22.6s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 13 | Adaptive Radial Edge Search (`adaptive_radial_edge`) | 4 | 19s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 14 | Segment-Supported Polar Voting (`segment_supported_polar_vote`) | 3 | 18s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 15 | Contour + Projection (`contour_projection`) | 2 | 15.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 16 | Contour Quadrilateral (`contour_quad`) | 4 | 11.9s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 17 | Border Fusion Quad (`border_fusion_quad`) | 2 | 11.5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 18 | Border Energy Validator (`border_energy`) | 3 | 11.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 19 | Multi-Scale Radial Edge Search (`multi_scale_radial_edge`) | 4 | 10.3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 20 | Joint Rectangle Voting (`joint_rectangle_vote`) | 2 | 8.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 21 | Radon Boundary Projection (`radon_boundary`) | 3 | 8.6s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 22 | Page Background (`page_background`) | 4 | 8.3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 23 | Cross-Edge Contour (`cross_edge_contour`) | 2 | 8.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 24 | Edge-Supported Contour (`edge_contour`) | 3 | 8.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 25 | Distance Transform Detector (`distance_transform`) | 4 | 7.9s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 26 | Orli Page Mask (`orli_page_mask`) | 2 | 7.5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 27 | Line Segment Detector (`lsd`) | 3 | 7.4s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 28 | Projective Gradient Vote (`projective_gradient_vote`) | 4 | 6.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 29 | Contour + Components (`contour_components`) | 2 | 5.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 30 | Signed Polar Boundary Voting (`signed_polar_boundary_vote`) | 3 | 4.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 31 | Radial Edge Search (`radial_edge`) | 4 | 4s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 32 | RANSAC Border Fit (`ransac`) | 3 | 3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 33 | Polar Boundary Voting (`polar_boundary_vote`) | 2 | 2.4s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 34 | Distance-Transform Rectangle Proposal (`distance_transform_rect`) | 4 | 2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 35 | Gradient Boundary Voting (`gradient_vote`) | 2 | 1.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 36 | Connected Components (`components`) | 3 | 1.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 37 | Convex Hull Detector (`convex_hull`) | 2 | 998 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 38 | Text Flow Envelope (`text_flow`) | 3 | 969 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 39 | Contour Envelope (`contour`) | 4 | 959 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 40 | Star-Convex Boundary Optimization (`star_convex`) | 2 | 775 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 41 | Whitespace Frame (`whitespace_frame`) | 3 | 752 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |

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
| 1 | GrabCut + Contour (`grabcut_contour`) | 10m 50s | 2 |
| 2 | GrabCut Segmentation (`grabcut`) | 9m 11s | 2 |
| 3 | Kraken Page Mask (`kraken_page_mask`) | 8m 13s | 2 |
| 4 | Contour + GrabCut (`contour_grabcut`) | 3m 45s | 2 |

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
| Exhaustive | unknown |
| Non-dormant | unknown |
| Critical only | unknown |

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

- Run ID: `run-20260820-035359`
- Detector: `adaptive_multi_scale_radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:53:59.144246+00:00`
- Finished: `2026-08-20T03:54:05.585334+00:00`
- Wall-clock elapsed: `6.4s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50001`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — adaptive_multi_scale_radial_edge

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `d271fcd63b1f` | `21ea516c3c5a` | `21ea516c3c5a` | `21ea516c3c5a` | 0.9781 | 0.9564 | 0.0182 | 0.9781 | 0 | 759 ms |
| Baseline | `HTH-0001` | `d271fcd63b1f` | `e8e8dc34f8fb` | `e8e8dc34f8fb` | `baseline` | 0.9767 | 0.9566 | 0.0177 | 0.9767 | 0 | 759 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `21ea516c3c5a` |
| Parameter Set ID (legacy alias) | `21ea516c3c5a` |
| Absolute parameter SHA-256 | `863c5b26d1a5857621a36ca640f40ad1ac54ba886e13c855269f819b932e804a` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `68e48d10ee23b4711e714ff04ed23d0143995259ff1cbe36fe6094c87b0e8e50` |
| Grid ordinal | `26353` |
| Reproducibility | **Fully reproducible** |

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
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `e8e8dc34f8fb` | `e8e8dc34f8fb` | `baseline` | 0.9767 | 0.9566 | 0.0177 | -0.0013 | 0.9767 | 0 | reference | reference |
| Best** | — | `21ea516c3c5a` | `21ea516c3c5a` | `21ea516c3c5a` | 0.9781 | 0.9564 | 0.0182 | +0.0000 | 0.9781 | 0 | reference | reference |
| 1 | — | `06a6f380f2b1` | `06a6f380f2b1` | `06a6f380f2b1` | 0.9723 | 0.9557 | 0.0152 | -0.0058 | 0.9723 | 0 | 5.1s | 81.82% |
| 2 | — | `4b0617f73ec2` | `4b0617f73ec2` | `4b0617f73ec2` | 0.9723 | 0.9557 | 0.0152 | -0.0058 | 0.9723 | 0 | 5.3s | 100.00% |
| 3 | — | `e634d8ca1523` | `e634d8ca1523` | `e634d8ca1523` | 0.9721 | 0.9557 | 0.0149 | -0.0060 | 0.9721 | 0 | 5.3s | 90.91% |
| 4 | — | `b45c5ee0f5fa` | `b45c5ee0f5fa` | `b45c5ee0f5fa` | 0.9720 | 0.9557 | 0.0148 | -0.0060 | 0.9720 | 0 | 4.5s | 45.45% |
| 5 | — | `f6301375e3a7` | `f6301375e3a7` | `f6301375e3a7` | 0.9705 | 0.9557 | 0.0146 | -0.0075 | 0.9705 | 0 | 4.9s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — adaptive_multi_scale_radial_edge

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `21ea516c3c5a` | `21ea516c3c5a` | 0.9767 | 0.9841 | +0.0074 | Improved |
| 5 | `21ea516c3c5a` | `21ea516c3c5a` | 0.9973 | 0.9973 | +0.0000 | Unchanged |
| 6 | `21ea516c3c5a` | `21ea516c3c5a` | 0.9959 | 0.9959 | +0.0000 | Unchanged |
| 9 | `21ea516c3c5a` | `21ea516c3c5a` | 0.9566 | 0.9566 | +0.0000 | Unchanged |
| 10 | `21ea516c3c5a` | `21ea516c3c5a` | 0.9573 | 0.9564 | -0.0009 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `21ea516c3c5a` | `21ea516c3c5a` | 1.5s | 18.18% |

Total winner changes: **1**.
Search completed in **6.4s** wall-clock time.

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

## Calibration Intelligence — adaptive_multi_scale_radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035359`
- Calibration schema: `1.1`
- Detector: `adaptive_multi_scale_radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/adaptive_multi_scale_radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `21ea516c3c5a`
- Recommended parameter short name: `21ea516c3c5a`
- Best observed Avg IoU: `0.9781`
- Avg IoU Success: `0.9781`
- Worst Golden Set page (Min IoU): `0.9564`
- Page-to-page StdDev: `0.0182`
- Calibration evidence: `Medium`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50001 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 10h 31m 45s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9781 |
| Minimum Avg IoU | 0.9701 |
| Avg IoU StdDev | 0.0026 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.5s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50000 | 100.0% | 10h 31m 52s | 1.0× |
| Exhaustive | 50000 | 100.0% | 10h 31m 52s | 1.0× |
| Non-dormant | 180 | 0.4% | 2m 16s | 277.8× |
| Low+ | 180 | 0.4% | 2m 16s | 277.8× |
| Moderate+ | 180 | 0.4% | 2m 16s | 277.8× |
| Important+ | 180 | 0.4% | 2m 16s | 277.8× |
| Critical | 180 | 0.4% | 2m 16s | 277.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `weak_side_support_fraction` | Critical | 0.8819 | 0.0070 | 33.3% | `0.65` (0.9781), `0.45` (0.9767), `0.3` (0.9711) | current run |
| `coarse_angle_step_degrees` | Critical | 0.8706 | 0.0063 | 50.0% | `2.04545` (0.9774), `1.85` (0.9711) | current run |
| `refined_angle_step_degrees` | Critical | 0.8706 | 0.0063 | 50.0% | `0.35` (0.9774), `0.25` (0.9711) | current run |
| `maximum_refined_sides` | Critical | 0.5469 | 0.0044 | 20.0% | `4` (0.9745), `3` (0.9741), `2` (0.9713) | current run |
| `side_assignment_tolerance_fraction` | Critical | 0.3994 | 0.0060 | 33.3% | `0.015` (0.9767), `0.0075` (0.9725), `0.01` (0.9707) | current run |
| `area_weight` | Critical | 0.2718 | 0.0000 | 0.0% | `0.2` (0.9767) | current run |
| `base_sigma` | Critical | 0.2718 | 0.0000 | 0.0% | `1` (0.9767) | current run |
| `bbox_padding_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0` (0.9767) | current run |
| `gradient_percentile` | Critical | 0.2718 | 0.0000 | 0.0% | `96.875` (0.9767) | current run |
| `maximum_area_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0.98` (0.9767) | current run |
| `maximum_radius_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0.78` (0.9767) | current run |
| `minimum_area_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0.18` (0.9767) | current run |
| `minimum_radius_fraction` | Critical | 0.2718 | 0.0000 | 0.0% | `0.16` (0.9767) | current run |
| `minimum_ray_support` | Critical | 0.2718 | 0.0000 | 0.0% | `0.36` (0.9767) | current run |
| `scale_count` | Critical | 0.2718 | 0.0000 | 0.0% | `4` (0.9767) | current run |
| `scale_ratio` | Critical | 0.2718 | 0.0000 | 0.0% | `3.5` (0.9767) | current run |
| `strength_weight` | Critical | 0.2718 | 0.0000 | 0.0% | `0.3` (0.9767) | current run |
| `support_weight` | Critical | 0.2718 | 0.0000 | 0.0% | `0.5` (0.9767) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_refined_sides` × `side_assignment_tolerance_fraction` | 0.7790 | 0.2321 | 11 |
| `coarse_angle_step_degrees` × `maximum_refined_sides` | 0.9846 | 0.1141 | 11 |
| `refined_angle_step_degrees` × `maximum_refined_sides` | 0.9846 | 0.1141 | 11 |
| `weak_side_support_fraction` × `maximum_refined_sides` | 0.9846 | 0.1027 | 11 |
| `coarse_angle_step_degrees` × `side_assignment_tolerance_fraction` | 0.8948 | 0.0242 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9771 | 0.9751 | 0.9841 | 0.0023 | 100.0% |
| 5 | 0.9774 | 0.9685 | 0.9973 | 0.0100 | 100.0% |
| 6 | 0.9948 | 0.9932 | 0.9960 | 0.0010 | 100.0% |
| 9 | 0.9559 | 0.9557 | 0.9566 | 0.0003 | 100.0% |
| 10 | 0.9560 | 0.9558 | 0.9573 | 0.0004 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="adaptive-radial-edge-search-adaptiveradialedge-2"></a>
<details>
<summary><strong>Adaptive Radial Edge Search (`adaptive_radial_edge`)</strong></summary>

**Status:** complete

## Run Information — adaptive_radial_edge

### Build Provenance

- Run ID: `run-20260820-035605`
- Detector: `adaptive_radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:05.170037+00:00`
- Finished: `2026-08-20T03:56:24.139625+00:00`
- Wall-clock elapsed: `19s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `49153`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — adaptive_radial_edge

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `3f151454bc4e` | `bcd9a1d083cf` | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9726 | 0.9557 | 0.0159 | 0.9726 | 0 | 1s |
| Baseline | `HTH-0001` | `3f151454bc4e` | `a132c2ac5e87` | `a132c2ac5e87` | `baseline` | 0.9329 | 0.8817 | 0.0344 | 0.9329 | 0 | 654 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `bcd9a1d083cf` |
| Parameter Set ID (legacy alias) | `bcd9a1d083cf` |
| Absolute parameter SHA-256 | `37f7949a8d5ffbce089237b0585497cb90abbe08c480413099ca0fedd66d14b9` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `a132c2ac5e87` | `a132c2ac5e87` | `baseline` | 0.9329 | 0.8817 | 0.0344 | -0.0397 | 0.9329 | 0 | reference | reference |
| Best** | — | `bcd9a1d083cf` | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9726 | 0.9557 | 0.0159 | +0.0000 | 0.9726 | 0 | reference | reference |
| 1 | — | `31e6d8b608a6` | `31e6d8b608a6` | `31e6d8b608a6` | 0.8826 | 0.8125 | 0.0362 | -0.0900 | 0.8826 | 0 | 8.7s | 63.64% |
| 2 | — | `18306ca501cd` | `18306ca501cd` | `18306ca501cd` | 0.8766 | 0.8125 | 0.0346 | -0.0960 | 0.8766 | 0 | 4.1s | 36.36% |
| 3 | — | `b1bad09b25cc` | `b1bad09b25cc` | `b1bad09b25cc` | 0.8754 | 0.8583 | 0.0204 | -0.0973 | 0.8754 | 0 | 6.4s | 45.45% |
| 4 | — | `5ebb46d5cf37` | `5ebb46d5cf37` | `5ebb46d5cf37` | 0.8676 | 0.8016 | 0.0477 | -0.1051 | 0.8676 | 0 | 7.2s | 54.55% |
| 5 | — | `2981cdfaca34` | `2981cdfaca34` | `2981cdfaca34` | 0.8676 | 0.8016 | 0.0477 | -0.1051 | 0.8676 | 0 | 10s | 72.73% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — adaptive_radial_edge

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.8817 | 0.9814 | +0.0996 | Improved |
| 5 | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9752 | 0.9716 | -0.0036 | Regressed |
| 6 | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9046 | 0.9979 | +0.0933 | Improved |
| 9 | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9480 | 0.9557 | +0.0076 | Improved |
| 10 | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9548 | 0.9565 | +0.0017 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `bcd9a1d083cf` | `bcd9a1d083cf` | 1.7s | 18.18% |

Total winner changes: **1**.
Search completed in **19s** wall-clock time.

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
| 5 | `bcd9a1d083cf` | `bcd9a1d083cf` | 0.9716 | Regressed |

## Calibration Intelligence — adaptive_radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035605`
- Calibration schema: `1.1`
- Detector: `adaptive_radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/adaptive_radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `bcd9a1d083cf`
- Recommended parameter short name: `bcd9a1d083cf`
- Best observed Avg IoU: `0.9726`
- Avg IoU Success: `0.9726`
- Worst Golden Set page (Min IoU): `0.9557`
- Page-to-page StdDev: `0.0159`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 49153 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 13h 39m 54s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9329 |
| Minimum Avg IoU | 0.8603 |
| Avg IoU StdDev | 0.0202 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.7s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 49152 | 100.0% | 13h 40m 3s | 1.0× |
| Exhaustive | 49152 | 100.0% | 13h 40m 3s | 1.0× |
| Non-dormant | 576 | 1.2% | 9m 37s | 85.3× |
| Low+ | 576 | 1.2% | 9m 37s | 85.3× |
| Moderate+ | 576 | 1.2% | 9m 37s | 85.3× |
| Important+ | 576 | 1.2% | 9m 37s | 85.3× |
| Critical | 576 | 1.2% | 9m 37s | 85.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gaussian_sigma` | Critical | 0.8925 | 0.0635 | 50.0% | `1.2` (0.9329), `0.6` (0.8694) | current run |
| `gradient_percentile` | Critical | 0.8925 | 0.0635 | 50.0% | `82` (0.9329), `74` (0.8694) | current run |
| `maximum_radius_fraction` | Critical | 0.8925 | 0.0635 | 50.0% | `0.72` (0.9329), `0.6` (0.8694) | current run |
| `minimum_radius_fraction` | Critical | 0.8925 | 0.0635 | 50.0% | `0.18` (0.9329), `0.1` (0.8694) | current run |
| `refined_angle_step_degrees` | Critical | 0.8925 | 0.0635 | 50.0% | `1` (0.9329), `0.35` (0.8694) | current run |
| `weak_side_support_fraction` | Critical | 0.8925 | 0.0635 | 50.0% | `0.55` (0.9329), `0.35` (0.8694) | current run |
| `area_weight` | Critical | 0.8033 | 0.0000 | 100.0% | `0.35` (0.9329) | current run |
| `coarse_angle_step_degrees` | Critical | 0.8033 | 0.0000 | 100.0% | `3` (0.9329) | current run |
| `maximum_area_fraction` | Critical | 0.8033 | 0.0000 | 100.0% | `0.98` (0.9329) | current run |
| `minimum_area_fraction` | Critical | 0.8033 | 0.0000 | 100.0% | `0.18` (0.9329) | current run |
| `minimum_ray_support` | Critical | 0.8033 | 0.0000 | 100.0% | `0.45` (0.9329) | current run |
| `ray_count` | Critical | 0.8033 | 0.0000 | 100.0% | `120` (0.9329) | current run |
| `rectangularity_weight` | Critical | 0.8033 | 0.0000 | 100.0% | `0.2` (0.9329) | current run |
| `support_weight` | Critical | 0.8033 | 0.0000 | 100.0% | `0.45` (0.9329) | current run |
| `side_assignment_tolerance_fraction` | Critical | 0.3187 | 0.0247 | 33.3% | `0.025` (0.8896), `0.015` (0.8682), `0.035` (0.8649) | current run |
| `maximum_refined_sides` | Critical | 0.3134 | 0.0240 | 33.3% | `2` (0.8895), `4` (0.8676), `1` (0.8656) | current run |

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
| 1 | 0.8791 | 0.8278 | 0.9085 | 0.0317 | 100.0% |
| 5 | 0.8967 | 0.8772 | 0.9752 | 0.0281 | 100.0% |
| 6 | 0.8905 | 0.8316 | 0.9090 | 0.0271 | 100.0% |
| 9 | 0.8345 | 0.8125 | 0.9480 | 0.0404 | 100.0% |
| 10 | 0.8780 | 0.8016 | 0.9548 | 0.0530 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="fusion-gen2-amsre-bfq-spbv-page-background-amsrebfqspbvpbg-2"></a>
<details>
<summary><strong>Fusion Gen2 — AMSRE + BFQ + SPBV + Page Background (`amsre_bfq_spbv_pbg`)</strong></summary>

**Status:** complete

## Run Information — amsre_bfq_spbv_pbg

### Build Provenance

- Run ID: `run-20260820-035326`
- Detector: `amsre_bfq_spbv_pbg`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:53:26.648329+00:00`
- Finished: `2026-08-20T03:54:33.290697+00:00`
- Wall-clock elapsed: `1m 7s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50177`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — amsre_bfq_spbv_pbg

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `f7c408e15389` | `156ff0241cc1` | `156ff0241cc1` | `baseline` | 0.9743 | 0.9638 | 0.0103 | 0.9743 | 0 | 7.3s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `156ff0241cc1` |
| Parameter Set ID (legacy alias) | `156ff0241cc1` |
| Absolute parameter SHA-256 | `38b21a2c6946890600ec97767ca82efb037b400c558f9b33ac608db8fd013b43` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `156ff0241cc1` | `156ff0241cc1` | `baseline` | 0.9743 | 0.9638 | 0.0103 | +0.0000 | 0.9743 | 0 | reference | reference |
| 1 | — | `2aa41939b8f9` | `2aa41939b8f9` | `2aa41939b8f9` | 0.9709 | 0.9539 | 0.0139 | -0.0034 | 0.9709 | 0 | 43.2s | 70.00% |
| 2 | — | `e940d0a6d2b3` | `e940d0a6d2b3` | `e940d0a6d2b3` | 0.9709 | 0.9539 | 0.0139 | -0.0034 | 0.9709 | 0 | 55.7s | 80.00% |
| 3 | — | `15d3526249ed` | `15d3526249ed` | `15d3526249ed` | 0.9709 | 0.9539 | 0.0139 | -0.0034 | 0.9709 | 0 | 56s | 90.00% |
| 4 | — | `88a403377e09` | `88a403377e09` | `88a403377e09` | 0.9709 | 0.9539 | 0.0139 | -0.0034 | 0.9709 | 0 | 1m 4s | 100.00% |
| 5 | — | `8243d036b8d9` | `8243d036b8d9` | `8243d036b8d9` | 0.9707 | 0.9539 | 0.0138 | -0.0035 | 0.9707 | 0 | 17.3s | 20.00% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — amsre_bfq_spbv_pbg

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `156ff0241cc1` | `baseline` | 0.9751 | 0.9751 | +0.0000 | Unchanged |
| 5 | `156ff0241cc1` | `baseline` | 0.9761 | 0.9761 | +0.0000 | Unchanged |
| 6 | `156ff0241cc1` | `baseline` | 0.9920 | 0.9920 | +0.0000 | Unchanged |
| 9 | `156ff0241cc1` | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `156ff0241cc1` | `baseline` | 0.9643 | 0.9643 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **1m 7s** wall-clock time.

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

- Calibration run ID: `run-20260820-035326`
- Calibration schema: `1.1`
- Detector: `amsre_bfq_spbv_pbg`
- Detector configuration: `hth-pipeline/config/detectors/amsre_bfq_spbv_pbg.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `156ff0241cc1`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.9743`
- Avg IoU Success: `0.9743`
- Worst Golden Set page (Min IoU): `0.9638`
- Page-to-page StdDev: `0.0103`
- Calibration evidence: `Medium`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50177 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 4d 5h 48m 36s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9743 |
| Minimum Avg IoU | 0.9707 |
| Avg IoU StdDev | 0.0010 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50176 | 100.0% | 4d 5h 49m 42s | 1.0× |
| Exhaustive | 50176 | 100.0% | 4d 5h 49m 42s | 1.0× |
| Non-dormant | 20 | 0.0% | 2m 26s | 2508.8× |
| Low+ | 20 | 0.0% | 2m 26s | 2508.8× |
| Moderate+ | 20 | 0.0% | 2m 26s | 2508.8× |
| Important+ | 20 | 0.0% | 2m 26s | 2508.8× |
| Critical | 20 | 0.0% | 2m 26s | 2508.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `consensus_tolerance_fraction` | Critical | 1.0000 | 0.0035 | 10.0% | `0.012664` (0.9743), `0.006673` (0.9709), `0.006807` (0.9709) | current run |
| `minimum_side_consensus` | Critical | 0.9941 | 0.0035 | 50.0% | `0.1` (0.9743), `0.05` (0.9708) | current run |
| `consensus_weight` | Critical | 0.8947 | 0.0000 | 100.0% | `0.6` (0.9743) | current run |
| `gradient_percentile` | Critical | 0.8947 | 0.0000 | 100.0% | `76` (0.9743) | current run |
| `gradient_weight` | Critical | 0.8947 | 0.0000 | 100.0% | `0.25` (0.9743) | current run |
| `minimum_side_gradient_support` | Critical | 0.8947 | 0.0000 | 100.0% | `0.03` (0.9743) | current run |
| `source_diversity_weight` | Critical | 0.8947 | 0.0000 | 100.0% | `0.15` (0.9743) | current run |

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
| 1 | 0.9751 | 0.9751 | 0.9751 | 0.0000 | 100.0% |
| 5 | 0.9756 | 0.9752 | 0.9761 | 0.0004 | 100.0% |
| 6 | 0.9920 | 0.9920 | 0.9920 | 0.0000 | 100.0% |
| 9 | 0.9549 | 0.9539 | 0.9638 | 0.0030 | 100.0% |
| 10 | 0.9581 | 0.9574 | 0.9643 | 0.0021 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="border-energy-validator-borderenergy-2"></a>
<details>
<summary><strong>Border Energy Validator (`border_energy`)</strong></summary>

**Status:** complete

## Run Information — border_energy

### Build Provenance

- Run ID: `run-20260820-035528`
- Detector: `border_energy`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:55:28.343718+00:00`
- Finished: `2026-08-20T03:55:39.424201+00:00`
- Wall-clock elapsed: `11.1s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `6562`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.17%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — border_energy

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `30216017d691` | `74e2112aac01` | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | 0.9063 | 1 | 1.2s |
| Baseline | `HTH-0001` | `30216017d691` | `e38a975d1436` | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | 0.9237 | 2 | 1.1s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `74e2112aac01` |
| Parameter Set ID (legacy alias) | `74e2112aac01` |
| Absolute parameter SHA-256 | `b95b091530ccec81ec3436966ecb54c2141674bb5df49a2f01e4f2738262472e` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `797c456dbd7dd781f46faafccb9d6bd73218053ac4b40b4bd76da5350c296dd9` |
| Grid ordinal | `54` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 1 |
| Total metric improvements | 2 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `e38a975d1436` | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | -0.1708 | 0.9237 | 2 | reference | reference |
| Best** | — | `74e2112aac01` | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | reference | reference |
| 1 | — | `ee832909df97` | `ee832909df97` | `ee832909df97` | 0.5542 | 0.0000 | 0.4538 | -0.1708 | 0.9237 | 2 | 3.7s | 27.27% |
| 2 | — | `24d1f88af992` | `24d1f88af992` | `24d1f88af992` | 0.5542 | 0.0000 | 0.4538 | -0.1708 | 0.9237 | 2 | 4s | 36.36% |
| 3 | — | `66d5d1766542` | `66d5d1766542` | `66d5d1766542` | 0.5542 | 0.0000 | 0.4538 | -0.1708 | 0.9237 | 2 | 5.4s | 45.45% |
| 4 | — | `d051925a3a6c` | `d051925a3a6c` | `d051925a3a6c` | 0.5542 | 0.0000 | 0.4538 | -0.1708 | 0.9237 | 2 | 5.5s | 54.55% |
| 5 | — | `d4b93ff23f99` | `d4b93ff23f99` | `d4b93ff23f99` | 0.5542 | 0.0000 | 0.4538 | -0.1708 | 0.9237 | 2 | 6.9s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — border_energy

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `74e2112aac01` | `74e2112aac01` | 0.0000 | 0.8542 | +0.8542 | Recovered |
| 5 | `74e2112aac01` | `74e2112aac01` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `74e2112aac01` | `74e2112aac01` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `74e2112aac01` | `74e2112aac01` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `74e2112aac01` | `74e2112aac01` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `74e2112aac01` | `74e2112aac01` | 2.4s | 18.18% |

Total winner changes: **1**.
Search completed in **11.1s** wall-clock time.

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
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `74e2112aac01` | `74e2112aac01` | 0.0000 | No polygon found |

## Calibration Intelligence — border_energy

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035528`
- Calibration schema: `1.1`
- Detector: `border_energy`
- Detector configuration: `hth-pipeline/config/detectors/border_energy.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `74e2112aac01`
- Recommended parameter short name: `74e2112aac01`
- Best observed Avg IoU: `0.7250`
- Avg IoU Success: `0.9063`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3651`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 2h 13m 21s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7250 |
| Minimum Avg IoU | 0.3651 |
| Avg IoU StdDev | 0.1054 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 2.4s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 6561 | 100.0% | 2h 13m 33s | 1.0× |
| Exhaustive | 6561 | 100.0% | 2h 13m 33s | 1.0× |
| Non-dormant | 864 | 13.2% | 17m 35s | 7.6× |
| Low+ | 864 | 13.2% | 17m 35s | 7.6× |
| Moderate+ | 27 | 0.4% | 33s | 243.0× |
| Important+ | 9 | 0.1% | 11s | 729.0× |
| Critical | 9 | 0.1% | 11s | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_side_consistency` | Critical | 0.8208 | 0.2318 | 33.3% | `0.3` (0.5969), `0.45` (0.5542), `0.6` (0.3651) | current run |
| `band_fraction` | Critical | 0.4147 | 0.2339 | 33.3% | `0.015` (0.7250), `0.008` (0.5542), `0.004` (0.4912) | current run |
| `energy_weight` | Moderate | 0.0545 | 0.0585 | 33.3% | `0.3` (0.5496), `0.4` (0.5069), `0.5` (0.4912) | current run |
| `epsilon_max_fraction` | Low | 0.0117 | 0.0396 | 50.0% | `0.04` (0.5542), `0.03` (0.5146) | current run |
| `gaussian_sigma` | Low | 0.0117 | 0.0396 | 50.0% | `1.2` (0.5542), `0.8` (0.5146) | current run |
| `minimum_border_energy` | Low | 0.0117 | 0.0396 | 50.0% | `0.1` (0.5542), `0.05` (0.5146) | current run |
| `minimum_contour_area_fraction` | Low | 0.0117 | 0.0396 | 50.0% | `0.12` (0.5542), `0.08` (0.5146) | current run |
| `minimum_rectangularity` | Low | 0.0117 | 0.0396 | 50.0% | `0.55` (0.5542), `0.45` (0.5146) | current run |
| `consistency_weight` | Low | 0.0106 | 0.0000 | 0.0% | `0.15` (0.5542) | current run |
| `contour_weight` | Low | 0.0106 | 0.0000 | 0.0% | `0.45` (0.5542) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_side_consistency` × `band_fraction` | 1.0000 | 0.1792 | 11 |
| `minimum_side_consistency` × `energy_weight` | 0.8805 | 0.0597 | 11 |
| `energy_weight` × `epsilon_max_fraction` | 0.0789 | 0.0244 | 11 |
| `energy_weight` × `gaussian_sigma` | 0.0789 | 0.0244 | 11 |
| `energy_weight` × `minimum_border_energy` | 0.0789 | 0.0244 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0777 | 0.0000 | 0.8542 | 0.2456 | 9.1% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.6876 | 0.0000 | 0.9454 | 0.4210 | 72.7% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="border-fusion-quad-borderfusionquad-2"></a>
<details>
<summary><strong>Border Fusion Quad (`border_fusion_quad`)</strong></summary>

**Status:** complete

## Run Information — border_fusion_quad

### Build Provenance

- Run ID: `run-20260820-035528`
- Detector: `border_fusion_quad`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:55:28.266850+00:00`
- Finished: `2026-08-20T03:55:39.761363+00:00`
- Wall-clock elapsed: `11.5s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `48021`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — border_fusion_quad

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `92f32c3b8792` | `2370e6cea486` | `2370e6cea486` | `2370e6cea486` | 0.9707 | 0.9588 | 0.0112 | 0.9707 | 0 | 972 ms |
| Baseline | `HTH-0001` | `92f32c3b8792` | `17b4a7b30cd9` | `17b4a7b30cd9` | `baseline` | 0.8890 | 0.5825 | 0.1538 | 0.8890 | 0 | 716 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `2370e6cea486` |
| Parameter Set ID (legacy alias) | `2370e6cea486` |
| Absolute parameter SHA-256 | `102be21f00195df448c8cc79ffedf5a05442baa0890b6f2688bc012473337e9c` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `17b4a7b30cd9` | `17b4a7b30cd9` | `baseline` | 0.8890 | 0.5825 | 0.1538 | -0.0817 | 0.8890 | 0 | reference | reference |
| Best** | — | `2370e6cea486` | `2370e6cea486` | `2370e6cea486` | 0.9707 | 0.9588 | 0.0112 | +0.0000 | 0.9707 | 0 | reference | reference |
| 1 | — | `90182e3a350a` | `90182e3a350a` | `90182e3a350a` | 0.9367 | 0.8379 | 0.0539 | -0.0340 | 0.9367 | 0 | 3.7s | 36.36% |
| 2 | — | `736ea0f654f7` | `736ea0f654f7` | `736ea0f654f7` | 0.9351 | 0.8379 | 0.0543 | -0.0357 | 0.9351 | 0 | 3.4s | 27.27% |
| 3 | — | `4bc129a45c0c` | `4bc129a45c0c` | `4bc129a45c0c` | 0.9351 | 0.8379 | 0.0543 | -0.0357 | 0.9351 | 0 | 5.4s | 45.45% |
| 4 | — | `63a3ee8a870f` | `63a3ee8a870f` | `63a3ee8a870f` | 0.9327 | 0.8379 | 0.0520 | -0.0381 | 0.9327 | 0 | 5.6s | 54.55% |
| 5 | — | `2c69d245c77d` | `2c69d245c77d` | `2c69d245c77d` | 0.9250 | 0.8379 | 0.0526 | -0.0458 | 0.9250 | 0 | 6.7s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — border_fusion_quad

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `2370e6cea486` | `2370e6cea486` | 0.9520 | 0.9655 | +0.0135 | Improved |
| 5 | `2370e6cea486` | `2370e6cea486` | 0.5825 | 0.9734 | +0.3908 | Improved |
| 6 | `2370e6cea486` | `2370e6cea486` | 0.9911 | 0.9911 | +0.0000 | Unchanged |
| 9 | `2370e6cea486` | `2370e6cea486` | 0.9588 | 0.9588 | +0.0000 | Unchanged |
| 10 | `2370e6cea486` | `2370e6cea486` | 0.9607 | 0.9650 | +0.0043 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `2370e6cea486` | `2370e6cea486` | 1.7s | 18.18% |

Total winner changes: **1**.
Search completed in **11.5s** wall-clock time.

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

## Calibration Intelligence — border_fusion_quad

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035528`
- Calibration schema: `1.1`
- Detector: `border_fusion_quad`
- Detector configuration: `hth-pipeline/config/detectors/border_fusion_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `2370e6cea486`
- Recommended parameter short name: `2370e6cea486`
- Best observed Avg IoU: `0.9707`
- Avg IoU Success: `0.9707`
- Worst Golden Set page (Min IoU): `0.9588`
- Page-to-page StdDev: `0.0112`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 48021 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 12h 57m 18s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9367 |
| Minimum Avg IoU | 0.8890 |
| Avg IoU StdDev | 0.0144 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.7s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 48020 | 100.0% | 12h 57m 27s | 1.0× |
| Exhaustive | 48020 | 100.0% | 12h 57m 27s | 1.0× |
| Non-dormant | 192 | 0.4% | 3m 7s | 250.1× |
| Low+ | 192 | 0.4% | 3m 7s | 250.1× |
| Moderate+ | 192 | 0.4% | 3m 7s | 250.1× |
| Important+ | 192 | 0.4% | 3m 7s | 250.1× |
| Critical | 64 | 0.1% | 1m 2s | 750.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_percentile` | Critical | 0.5502 | 0.0355 | 50.0% | `68` (0.9246), `82` (0.8890) | current run |
| `gradient_weight` | Critical | 0.5502 | 0.0355 | 50.0% | `0.1` (0.9246), `0.45` (0.8890) | current run |
| `minimum_area_fraction` | Critical | 0.5502 | 0.0355 | 50.0% | `0.08` (0.9246), `0.18` (0.8890) | current run |
| `minimum_side_gradient_support` | Critical | 0.5502 | 0.0355 | 50.0% | `0` (0.9246), `0.16` (0.8890) | current run |
| `area_weight` | Critical | 0.4952 | 0.0000 | 0.0% | `0.15` (0.8890) | current run |
| `bbox_padding_fraction` | Critical | 0.4952 | 0.0000 | 0.0% | `0` (0.8890) | current run |
| `maximum_area_fraction` | Critical | 0.4952 | 0.0000 | 0.0% | `0.98` (0.8890) | current run |
| `minimum_child_candidates` | Critical | 0.4952 | 0.0000 | 0.0% | `2` (0.8890) | current run |
| `minimum_child_confidence` | Critical | 0.4952 | 0.0000 | 0.0% | `0` (0.8890) | current run |
| `minimum_distinct_sources` | Critical | 0.4952 | 0.0000 | 0.0% | `2` (0.8890) | current run |
| `source_diversity_weight` | Critical | 0.2357 | 0.0168 | 25.0% | `0` (0.9273), `0.025` (0.9244), `0.05` (0.9237) | current run |
| `source_confidence_weight` | Important | 0.1172 | 0.0104 | 33.3% | `0.25` (0.9257), `0.35` (0.9204), `0.3` (0.9153) | current run |

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
| 1 | 0.9322 | 0.8847 | 0.9655 | 0.0308 | 100.0% |
| 5 | 0.8855 | 0.5825 | 0.9240 | 0.1011 | 100.0% |
| 6 | 0.9887 | 0.9791 | 0.9911 | 0.0048 | 100.0% |
| 9 | 0.8500 | 0.8379 | 0.9588 | 0.0363 | 100.0% |
| 10 | 0.9486 | 0.9106 | 0.9660 | 0.0249 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="connected-components-components-2"></a>
<details>
<summary><strong>Connected Components (`components`)</strong></summary>

**Status:** complete

## Run Information — components

### Build Provenance

- Run ID: `run-20260820-035709`
- Detector: `components`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:57:09.823803+00:00`
- Finished: `2026-08-20T03:57:10.906683+00:00`
- Wall-clock elapsed: `1.1s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `19683`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.06%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — components

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `e15dea95a56f` | `f1929c8e2655` | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | 0.7897 | 0 | 24 ms |
| Baseline | `HTH-0001` | `e15dea95a56f` | `4e09dc84fa8a` | `4e09dc84fa8a` | `baseline` | 0.7185 | 0.2413 | 0.2967 | 0.7185 | 0 | 27 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `f1929c8e2655` |
| Parameter Set ID (legacy alias) | `f1929c8e2655` |
| Absolute parameter SHA-256 | `bb68733f9ab2bdd03f4a403c6ad5935e02312e8d5fd6d640dba05250ea116913` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `590321d84ef7dd961d1ca2905240dad6bbfc6172e4a7ea5093cb0451ebb84bce` |
| Grid ordinal | `248` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `4e09dc84fa8a` | `4e09dc84fa8a` | `baseline` | 0.7185 | 0.2413 | 0.2967 | -0.0712 | 0.7185 | 0 | reference | reference |
| Best** | — | `f1929c8e2655` | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | reference | reference |
| 1 | — | `7eb87978bb9a` | `7eb87978bb9a` | `7eb87978bb9a` | 0.7794 | 0.5504 | 0.1789 | -0.0103 | 0.7794 | 0 | 126 ms | 54.55% |
| 2 | — | `2a180d02de36` | `2a180d02de36` | `2a180d02de36` | 0.7794 | 0.5504 | 0.1789 | -0.0103 | 0.7794 | 0 | 158 ms | 72.73% |
| 3 | — | `b6a644d99d2e` | `b6a644d99d2e` | `b6a644d99d2e` | 0.7794 | 0.5504 | 0.1789 | -0.0103 | 0.7794 | 0 | 213 ms | 100.00% |
| 4 | — | `04ff9a0c7a86` | `04ff9a0c7a86` | `04ff9a0c7a86` | 0.7734 | 0.4617 | 0.2201 | -0.0163 | 0.7734 | 0 | 89 ms | 27.27% |
| 5 | — | `732d1fd40ae7` | `732d1fd40ae7` | `732d1fd40ae7` | 0.7734 | 0.4617 | 0.2201 | -0.0163 | 0.7734 | 0 | 154 ms | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — components

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `f1929c8e2655` | `f1929c8e2655` | 0.9734 | 0.9533 | -0.0201 | Regressed |
| 5 | `f1929c8e2655` | `f1929c8e2655` | 0.4973 | 0.5725 | +0.0752 | Improved |
| 6 | `f1929c8e2655` | `f1929c8e2655` | 0.2413 | 0.6018 | +0.3605 | Improved |
| 9 | `f1929c8e2655` | `f1929c8e2655` | 0.9314 | 0.9018 | -0.0296 | Regressed |
| 10 | `f1929c8e2655` | `f1929c8e2655` | 0.9491 | 0.9192 | -0.0299 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `f1929c8e2655` | `f1929c8e2655` | 53 ms | 18.18% |

Total winner changes: **1**.
Search completed in **1.1s** wall-clock time.

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
- Regressed pages (Δ IoU < -0.0010): `3`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `f1929c8e2655` | `f1929c8e2655` | 0.9533 | Regressed |
| 9 | `f1929c8e2655` | `f1929c8e2655` | 0.9018 | Regressed |
| 10 | `f1929c8e2655` | `f1929c8e2655` | 0.9192 | Regressed |

## Calibration Intelligence — components

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035709`
- Calibration schema: `1.1`
- Detector: `components`
- Detector configuration: `hth-pipeline/config/detectors/components.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `f1929c8e2655`
- Recommended parameter short name: `f1929c8e2655`
- Best observed Avg IoU: `0.7897`
- Avg IoU Success: `0.7897`
- Worst Golden Set page (Min IoU): `0.5725`
- Page-to-page StdDev: `0.1665`
- Calibration evidence: `Medium`
- Dormant parameters: `morphology_close_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 9 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 19683 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 7m 45s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.7897 |
| Minimum Avg IoU | 0.7185 |
| Avg IoU StdDev | 0.0253 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 53 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 19683 | 100.0% | 7m 45s | 1.0× |
| Exhaustive | 19683 | 100.0% | 7m 45s | 1.0× |
| Non-dormant | 192 | 1.0% | 4.5s | 102.5× |
| Low+ | 192 | 1.0% | 4.5s | 102.5× |
| Moderate+ | 96 | 0.5% | 2.3s | 205.0× |
| Important+ | 96 | 0.5% | 2.3s | 205.0× |
| Critical | 96 | 0.5% | 2.3s | 205.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `morphology_dilate_fraction` | Critical | 0.6669 | 0.0522 | 33.3% | `0.03` (0.7820), `0.015` (0.7597), `0.008` (0.7298) | current run |
| `merge_area_ratio` | Critical | 0.2651 | 0.0452 | 50.0% | `0.01` (0.7637), `0.02` (0.7185) | current run |
| `minimum_bbox_area_fraction` | Critical | 0.2651 | 0.0452 | 50.0% | `0.08` (0.7637), `0.12` (0.7185) | current run |
| `minimum_component_area_fraction` | Critical | 0.2651 | 0.0452 | 50.0% | `0.00075` (0.7637), `0.0015` (0.7185) | current run |
| `minimum_component_area_px` | Critical | 0.2651 | 0.0452 | 50.0% | `10` (0.7637), `25` (0.7185) | current run |
| `minimum_selected_area_fraction` | Critical | 0.2651 | 0.0452 | 50.0% | `0.02` (0.7637), `0.04` (0.7185) | current run |
| `merge_gap_fraction` | Low | 0.0106 | 0.0067 | 50.0% | `0.02` (0.7609), `0.035` (0.7541) | current run |
| `morphology_close_fraction` | Dormant | 0.0028 | 0.0027 | 33.3% | `0.016` (0.7609), `0.004` (0.7609), `0.008` (0.7582) | current run |
| `bbox_padding_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.7596) | current run |

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

`morphology_close_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `morphology_dilate_fraction` × `merge_area_ratio` | 0.9887 | 0.3218 | 11 |
| `morphology_dilate_fraction` × `minimum_bbox_area_fraction` | 0.9887 | 0.3218 | 11 |
| `morphology_dilate_fraction` × `minimum_component_area_fraction` | 0.9887 | 0.3218 | 11 |
| `morphology_dilate_fraction` × `minimum_component_area_px` | 0.9887 | 0.3218 | 11 |
| `morphology_dilate_fraction` × `minimum_selected_area_fraction` | 0.9887 | 0.3218 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9661 | 0.9533 | 0.9734 | 0.0097 | 100.0% |
| 5 | 0.5518 | 0.4973 | 0.5725 | 0.0211 | 100.0% |
| 6 | 0.4169 | 0.2352 | 0.6018 | 0.1425 | 100.0% |
| 9 | 0.9238 | 0.9018 | 0.9429 | 0.0172 | 100.0% |
| 10 | 0.9397 | 0.9192 | 0.9543 | 0.0156 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="consensus-quadrilateral-consensusquad-2"></a>
<details>
<summary><strong>Consensus Quadrilateral (`consensus_quad`)</strong></summary>

**Status:** complete

## Run Information — consensus_quad

### Build Provenance

- Run ID: `run-20260820-035401`
- Detector: `consensus_quad`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:54:01.046135+00:00`
- Finished: `2026-08-20T03:54:04.062410+00:00`
- Wall-clock elapsed: `3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `243`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `4.53%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
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
| Winner | `HTH-0001` | `964f55411f64` | `f387da7ebb7e` | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | 0.9213 | 2 | 576 ms |
| Baseline | `HTH-0001` | `964f55411f64` | `dce471449373` | `dce471449373` | `baseline` | 0.5513 | 0.0000 | 0.4513 | 0.9188 | 2 | 623 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `f387da7ebb7e` |
| Parameter Set ID (legacy alias) | `f387da7ebb7e` |
| Absolute parameter SHA-256 | `6a0be21d0e4aac7edd7f83fb965fd79a382f176333222365abf9d35725c1021f` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `81788627a94a597617d4c1d68c25b039bf43d33e16345a520f4e42219f352a5e` |
| Grid ordinal | `45` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 2 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 3 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `dce471449373` | `dce471449373` | `baseline` | 0.5513 | 0.0000 | 0.4513 | -0.0015 | 0.9188 | 2 | reference | reference |
| Best** | — | `f387da7ebb7e` | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | reference | reference |
| 1 | — | `48c503656d02` | `48c503656d02` | `48c503656d02` | 0.3654 | 0.0000 | 0.4487 | -0.1873 | 0.9136 | 3 | 2.5s | 27.27% |
| 2 | — | `957153998277` | `957153998277` | `957153998277` | 0.3654 | 0.0000 | 0.4487 | -0.1873 | 0.9136 | 3 | 2.7s | 81.82% |
| 3 | — | `1752e509b03b` | `1752e509b03b` | `1752e509b03b` | 0.3654 | 0.0000 | 0.4487 | -0.1873 | 0.9136 | 3 | 2.6s | 36.36% |
| 4 | — | `0c4cd99b53b0` | `0c4cd99b53b0` | `0c4cd99b53b0` | 0.3653 | 0.0000 | 0.4485 | -0.1875 | 0.9131 | 3 | 2.6s | 63.64% |
| 5 | — | `c11482b7189e` | `c11482b7189e` | `c11482b7189e` | 0.3653 | 0.0000 | 0.4485 | -0.1875 | 0.9131 | 3 | 2.7s | 72.73% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — consensus_quad

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `f387da7ebb7e` | `f387da7ebb7e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `f387da7ebb7e` | `f387da7ebb7e` | 0.8616 | 0.8616 | +0.0000 | Unchanged |
| 6 | `f387da7ebb7e` | `f387da7ebb7e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `f387da7ebb7e` | `f387da7ebb7e` | 0.9647 | 0.9636 | -0.0011 | Regressed |
| 10 | `f387da7ebb7e` | `f387da7ebb7e` | 0.9302 | 0.9386 | +0.0085 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `f387da7ebb7e` | `f387da7ebb7e` | 1.2s | 18.18% |

Total winner changes: **1**.
Search completed in **3s** wall-clock time.

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
| 1 | `f387da7ebb7e` | `f387da7ebb7e` | 0.0000 | No polygon found |
| 6 | `f387da7ebb7e` | `f387da7ebb7e` | 0.0000 | No polygon found |
| 9 | `f387da7ebb7e` | `f387da7ebb7e` | 0.9636 | Regressed |

## Calibration Intelligence — consensus_quad

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035401`
- Calibration schema: `1.1`
- Detector: `consensus_quad`
- Detector configuration: `hth-pipeline/config/detectors/consensus_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `f387da7ebb7e`
- Recommended parameter short name: `f387da7ebb7e`
- Best observed Avg IoU: `0.5528`
- Avg IoU Success: `0.9213`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4526`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 243 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 4.5% |
| Est. serial runtime for full parameter set evaluation* | 2m 14s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5528 |
| Minimum Avg IoU | 0.3651 |
| Avg IoU StdDev | 0.0720 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.2s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 243 | 100.0% | 2m 20s | 1.0× |
| Exhaustive | 243 | 100.0% | 2m 20s | 1.0× |
| Non-dormant | 108 | 44.4% | 1m 2s | 2.2× |
| Low+ | 108 | 44.4% | 1m 2s | 2.2× |
| Moderate+ | 108 | 44.4% | 1m 2s | 2.2× |
| Important+ | 108 | 44.4% | 1m 2s | 2.2× |
| Critical | 12 | 4.9% | 6.9s | 20.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `contour_quad_weight` | Critical | 1.0000 | 0.1875 | 33.3% | `0.75` (0.5528), `0.5` (0.5513), `0.25` (0.3653) | current run |
| `maximum_mean_corner_distance_fraction` | Critical | 1.0000 | 0.1868 | 50.0% | `0.025` (0.5520), `0.015` (0.3653) | current run |
| `minimum_polygon_iou` | Critical | 0.4456 | 0.1673 | 50.0% | `0.9` (0.5513), `0.8` (0.3840) | current run |
| `minimum_consensus_confidence` | Important | 0.0833 | 0.0469 | 33.3% | `0.1` (0.4121), `0.2` (0.4118), `0.35` (0.3653) | current run |
| `edge_contour_weight` | Important | 0.0825 | 0.0467 | 33.3% | `0.25` (0.4121), `0.5` (0.4116), `0.75` (0.3654) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_consensus_confidence` × `edge_contour_weight` | 0.3883 | 0.3050 | 11 |
| `minimum_polygon_iou` × `edge_contour_weight` | 0.5380 | 0.0924 | 11 |
| `minimum_polygon_iou` × `minimum_consensus_confidence` | 0.5380 | 0.0924 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.8619 | 0.8616 | 0.8624 | 0.0004 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9643 | 0.9636 | 0.9647 | 0.0005 | 100.0% |
| 10 | 0.1699 | 0.0000 | 0.9386 | 0.3604 | 18.2% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-envelope-contour-2"></a>
<details>
<summary><strong>Contour Envelope (`contour`)</strong></summary>

**Status:** complete

## Run Information — contour

### Build Provenance

- Run ID: `run-20260820-035704`
- Detector: `contour`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:57:04.034933+00:00`
- Finished: `2026-08-20T03:57:04.994115+00:00`
- Wall-clock elapsed: `959 ms`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1458`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.75%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
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
| Winner | `HTH-0001` | `50c7162c44c1` | `7aed2fc501c5` | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | 39 ms |
| Baseline | `HTH-0001` | `50c7162c44c1` | `6019a18e4c4e` | `6019a18e4c4e` | `baseline` | 0.6722 | 0.0000 | 0.3846 | 0.8403 | 1 | 49 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `7aed2fc501c5` |
| Parameter Set ID (legacy alias) | `7aed2fc501c5` |
| Absolute parameter SHA-256 | `f3be94c2efb6ee89d9366a3f0ef6f033d4f728be45ccfc8498e19d57b63a1e2f` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `82ae8377914bcb10d48ff95337120000a514277e384779cc6be6e865dd3197da` |
| Grid ordinal | `147` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `6019a18e4c4e` | `6019a18e4c4e` | `baseline` | 0.6722 | 0.0000 | 0.3846 | -0.1776 | 0.8403 | 1 | reference | reference |
| Best** | — | `7aed2fc501c5` | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | reference | reference |
| 1 | — | `0bf3c1624426` | `0bf3c1624426` | `0bf3c1624426` | 0.8392 | 0.4919 | 0.1797 | -0.0106 | 0.8392 | 0 | 232 ms | 63.64% |
| 2 | — | `a20447ccca1e` | `a20447ccca1e` | `a20447ccca1e` | 0.8364 | 0.4784 | 0.1870 | -0.0134 | 0.8364 | 0 | 160 ms | 45.45% |
| 3 | — | `160333f7751d` | `160333f7751d` | `160333f7751d` | 0.8364 | 0.4784 | 0.1870 | -0.0134 | 0.8364 | 0 | 314 ms | 90.91% |
| 4 | — | `e0ad87b12d87` | `e0ad87b12d87` | `e0ad87b12d87` | 0.8338 | 0.5178 | 0.1600 | -0.0160 | 0.8338 | 0 | 277 ms | 72.73% |
| 5 | — | `7e0ae458ce6c` | `7e0ae458ce6c` | `7e0ae458ce6c` | 0.6722 | 0.0000 | 0.3846 | -0.1776 | 0.8403 | 1 | 121 ms | 27.27% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `7aed2fc501c5` | `7aed2fc501c5` | 0.9648 | 0.9734 | +0.0086 | Improved |
| 5 | `7aed2fc501c5` | `7aed2fc501c5` | 0.4784 | 0.5457 | +0.0673 | Improved |
| 6 | `7aed2fc501c5` | `7aed2fc501c5` | 0.0000 | 0.8392 | +0.8392 | Recovered |
| 9 | `7aed2fc501c5` | `7aed2fc501c5` | 0.9585 | 0.9390 | -0.0195 | Regressed |
| 10 | `7aed2fc501c5` | `7aed2fc501c5` | 0.9593 | 0.9517 | -0.0076 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `7aed2fc501c5` | `7aed2fc501c5` | 94 ms | 18.18% |

Total winner changes: **1**.
Search completed in **959 ms** wall-clock time.

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
| 9 | `7aed2fc501c5` | `7aed2fc501c5` | 0.9390 | Regressed |
| 10 | `7aed2fc501c5` | `7aed2fc501c5` | 0.9517 | Regressed |

## Calibration Intelligence — contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035704`
- Calibration schema: `1.1`
- Detector: `contour`
- Detector configuration: `hth-pipeline/config/detectors/contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `7aed2fc501c5`
- Recommended parameter short name: `7aed2fc501c5`
- Best observed Avg IoU: `0.8498`
- Avg IoU Success: `0.8498`
- Worst Golden Set page (Min IoU): `0.5457`
- Page-to-page StdDev: `0.1589`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 6 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.8% |
| Est. serial runtime for full parameter set evaluation* | 55.1s |
| Fully successful parameter sets | 5 (45.5%) |
| Best Avg IoU | 0.8498 |
| Minimum Avg IoU | 0.6586 |
| Avg IoU StdDev | 0.0846 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 94 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 1458 | 100.0% | 55.5s | 1.0× |
| Exhaustive | 1458 | 100.0% | 55.5s | 1.0× |
| Non-dormant | 192 | 13.2% | 7.3s | 7.6× |
| Low+ | 192 | 13.2% | 7.3s | 7.6× |
| Moderate+ | 64 | 4.4% | 2.4s | 22.8× |
| Important+ | 64 | 4.4% | 2.4s | 22.8× |
| Critical | 8 | 0.5% | 304 ms | 182.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `merge_fragmented_contours` | Critical | 0.9961 | 0.1695 | 50.0% | `true` (0.8391), `false` (0.6697) | current run |
| `close_iterations` | Critical | 0.1487 | 0.1134 | 50.0% | `2` (0.8498), `0` (0.7364) | current run |
| `close_kernel_fraction` | Critical | 0.1487 | 0.1134 | 50.0% | `0.018` (0.8498), `0` (0.7364) | current run |
| `rectangularity_weight` | Important | 0.0905 | 0.0529 | 50.0% | `0.1` (0.7659), `0.25` (0.7130) | current run |
| `minimum_contour_area_fraction` | Important | 0.0776 | 0.0819 | 50.0% | `0.06` (0.7541), `0.12` (0.6722) | current run |
| `polygon_epsilon_fraction` | Important | 0.0776 | 0.0819 | 50.0% | `0.008` (0.7541), `0.018` (0.6722) | current run |
| `bbox_padding_fraction` | Low | 0.0114 | 0.0201 | 33.3% | `0.005` (0.7579), `0.015` (0.7462), `0` (0.7379) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `close_iterations` × `minimum_contour_area_fraction` | 0.2069 | 0.0582 | 11 |
| `close_iterations` × `polygon_epsilon_fraction` | 0.2069 | 0.0582 | 11 |
| `close_kernel_fraction` × `minimum_contour_area_fraction` | 0.2069 | 0.0582 | 11 |
| `close_kernel_fraction` × `polygon_epsilon_fraction` | 0.2069 | 0.0582 | 11 |
| `close_iterations` × `rectangularity_weight` | 0.1949 | 0.0462 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9658 | 0.9533 | 0.9734 | 0.0071 | 100.0% |
| 5 | 0.4953 | 0.4784 | 0.5457 | 0.0214 | 100.0% |
| 6 | 0.3815 | 0.0000 | 0.8763 | 0.4181 | 45.5% |
| 9 | 0.9411 | 0.9018 | 0.9585 | 0.0205 | 100.0% |
| 10 | 0.9497 | 0.9200 | 0.9593 | 0.0143 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-components-contourcomponents-2"></a>
<details>
<summary><strong>Contour + Components (`contour_components`)</strong></summary>

**Status:** complete

## Run Information — contour_components

### Build Provenance

- Run ID: `run-20260820-035640`
- Detector: `contour_components`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:40.142567+00:00`
- Finished: `2026-08-20T03:56:45.202632+00:00`
- Wall-clock elapsed: `5.1s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `19684`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.05%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour_components

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `45b36bf94550` | `14818b491952` | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | 307 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `14818b491952` |
| Parameter Set ID (legacy alias) | `14818b491952` |
| Absolute parameter SHA-256 | `0ed41441d776274eaef913d67fdc923d5dabe25e56117dac7b3b28a6969597e4` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `14818b491952` | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | reference | reference |
| 1 | — | `6931e3aea38a` | `6931e3aea38a` | `6931e3aea38a` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 673 ms | 20.00% |
| 2 | — | `d6a2096d57a6` | `d6a2096d57a6` | `d6a2096d57a6` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 776 ms | 30.00% |
| 3 | — | `4339c3f69581` | `4339c3f69581` | `4339c3f69581` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 1.1s | 40.00% |
| 4 | — | `2cd41c1cfd70` | `2cd41c1cfd70` | `2cd41c1cfd70` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 1.2s | 50.00% |
| 5 | — | `91d7206d1476` | `91d7206d1476` | `91d7206d1476` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 1.5s | 60.00% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour_components

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `14818b491952` | `baseline` | 0.8540 | 0.8540 | +0.0000 | Unchanged |
| 5 | `14818b491952` | `baseline` | 0.8616 | 0.8616 | +0.0000 | Unchanged |
| 6 | `14818b491952` | `baseline` | 0.7572 | 0.7572 | +0.0000 | Unchanged |
| 9 | `14818b491952` | `baseline` | 0.9636 | 0.9636 | +0.0000 | Unchanged |
| 10 | `14818b491952` | `baseline` | 0.8719 | 0.8719 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **5.1s** wall-clock time.

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

- Calibration run ID: `run-20260820-035640`
- Calibration schema: `1.1`
- Detector: `contour_components`
- Detector configuration: `hth-pipeline/config/detectors/contour_components.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `14818b491952`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8617`
- Avg IoU Success: `0.8617`
- Worst Golden Set page (Min IoU): `0.7572`
- Page-to-page StdDev: `0.0655`
- Calibration evidence: `Medium`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, exhaustive_with_zombies`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 19684 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 1h 40m 24s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8617 |
| Minimum Avg IoU | 0.8617 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 10 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 10 (100.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 19683 | 100.0% | 1h 40m 27s | 1.0× |
| Exhaustive | 19683 | 100.0% | 1h 40m 27s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `component_close_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617), `0.004` (0.8617) | current run |
| `component_dilate_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8617), `0.008` (0.8617) | current run |
| `component_merge_gap_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.035` (0.8617), `0.02` (0.8617) | current run |
| `component_minimum_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.0015` (0.8617), `0.0008` (0.8617) | current run |
| `epsilon_max_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8617), `0.03` (0.8617) | current run |
| `minimum_contour_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.12` (0.8617), `0.08` (0.8617) | current run |
| `minimum_rectangularity` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.55` (0.8617), `0.45` (0.8617) | current run |
| `angle_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8617) | current run |
| `area_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8617) | current run |
| `close_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.8617) | current run |
| `close_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617) | current run |
| `component_bbox_padding_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.8617) | current run |
| `component_merge_area_ratio` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.02` (0.8617) | current run |
| `component_minimum_area_px` | Zombie | 0.0000 | 0.0000 | 100.0% | `25` (0.8617) | current run |
| `component_minimum_bbox_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.12` (0.8617) | current run |
| `component_minimum_selected_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8617) | current run |
| `component_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8617), `0.4` (0.8617), `0.55` (0.8617) | current run |
| `epsilon_min_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617) | current run |
| `epsilon_steps` | Zombie | 0.0000 | 0.0000 | 100.0% | `9` (0.8617) | current run |
| `merge_fragmented_contours` | Zombie | 0.0000 | 0.0000 | 100.0% | `true` (0.8617) | current run |
| `minimum_component_score` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.05` (0.8617), `0.12` (0.8617) | current run |
| `rectangularity_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8617) | current run |

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

- Run ID: `run-20260820-035207`
- Detector: `contour_grabcut`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:52:07.157432+00:00`
- Finished: `2026-08-20T03:52:48.733145+00:00`
- Wall-clock elapsed: `41.6s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `6562`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.15%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour_grabcut

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `4e0a69665997` | `3eec8a03f1de` | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 29.2s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `3eec8a03f1de` |
| Parameter Set ID (legacy alias) | `3eec8a03f1de` |
| Absolute parameter SHA-256 | `c409c128cf7a1ce1b8299a1ac42eddfa3e916b43dd748a8c10345420038a72e8` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `3eec8a03f1de` | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | reference | reference |
| 1 | — | `42fc63229bb3` | `42fc63229bb3` | `42fc63229bb3` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 40.9s | 70.00% |
| 2 | — | `cb5795c42bd3` | `cb5795c42bd3` | `cb5795c42bd3` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 40.9s | 40.00% |
| 3 | — | `a3d42053b548` | `a3d42053b548` | `a3d42053b548` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 40.9s | 60.00% |
| 4 | — | `0fb98d4d4330` | `0fb98d4d4330` | `0fb98d4d4330` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 41.2s | 100.00% |
| 5 | — | `56ae8fdbf618` | `56ae8fdbf618` | `56ae8fdbf618` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 40.8s | 30.00% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour_grabcut

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `3eec8a03f1de` | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `3eec8a03f1de` | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `3eec8a03f1de` | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `3eec8a03f1de` | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `3eec8a03f1de` | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **41.6s** wall-clock time.

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

- Calibration run ID: `run-20260820-035207`
- Calibration schema: `1.1`
- Detector: `contour_grabcut`
- Detector configuration: `hth-pipeline/config/detectors/contour_grabcut.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `3eec8a03f1de`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Medium`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, exhaustive_with_zombies`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 2d 5h 13m 26s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.8768 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 10 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 10 (100.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 6561 | 100.0% | 2d 5h 17m 49s | 1.0× |
| Exhaustive | 6561 | 100.0% | 2d 5h 17m 49s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `contour_epsilon_max_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768) | current run |
| `contour_minimum_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768) | current run |
| `contour_minimum_rectangularity` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768) | current run |
| `grabcut_border_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.01` (0.8768), `0.02` (0.8768) | current run |
| `grabcut_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.8768), `3` (0.8768) | current run |
| `minimum_agreement_iou` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.3` (0.8768) | current run |
| `agreement_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) | current run |
| `contour_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768) | current run |
| `grabcut_erosion_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8768) | current run |
| `grabcut_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.25` (0.8768), `0.35` (0.8768) | current run |
| `require_grabcut` | Zombie | 0.0000 | 0.0000 | 100.0% | `false` (0.8768) | current run |

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

- Run ID: `run-20260820-035434`
- Detector: `contour_projection`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:54:34.841165+00:00`
- Finished: `2026-08-20T03:54:50.558069+00:00`
- Wall-clock elapsed: `15.7s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `6562`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.15%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour_projection

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `cbe149a9e40c` | `0cd13eb1a471` | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 1.8s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `0cd13eb1a471` |
| Parameter Set ID (legacy alias) | `0cd13eb1a471` |
| Absolute parameter SHA-256 | `36d705551505b46c54b4407c7708373a5529e88a69afa087f3365f8699ce3a9b` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `0cd13eb1a471` | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | reference | reference |
| 1 | — | `172304831b2e` | `172304831b2e` | `172304831b2e` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 4.3s | 30.00% |
| 2 | — | `06593bf5afce` | `06593bf5afce` | `06593bf5afce` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 4s | 20.00% |
| 3 | — | `07cc1ff1c71c` | `07cc1ff1c71c` | `07cc1ff1c71c` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 6.8s | 40.00% |
| 4 | — | `8d75cf39600c` | `8d75cf39600c` | `8d75cf39600c` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 6.9s | 50.00% |
| 5 | — | `b71b6267963a` | `b71b6267963a` | `b71b6267963a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 9.5s | 60.00% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour_projection

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `0cd13eb1a471` | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `0cd13eb1a471` | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `0cd13eb1a471` | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `0cd13eb1a471` | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `0cd13eb1a471` | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **15.7s** wall-clock time.

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

- Calibration run ID: `run-20260820-035434`
- Calibration schema: `1.1`
- Detector: `contour_projection`
- Detector configuration: `hth-pipeline/config/detectors/contour_projection.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `0cd13eb1a471`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Medium`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `exhaustive, exhaustive_with_zombies`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 3h 12m 46s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.8768 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 10 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 10 (100.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 6561 | 100.0% | 3h 13m 2s | 1.0× |
| Exhaustive | 6561 | 100.0% | 3h 13m 2s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `epsilon_max_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768) | current run |
| `minimum_contour_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768) | current run |
| `minimum_rectangularity` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768) | current run |
| `projection_margin_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.06` (0.8768) | current run |
| `projection_threshold_block_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.05` (0.8768), `0.08` (0.8768) | current run |
| `projection_threshold_c` | Zombie | 0.0000 | 0.0000 | 100.0% | `5` (0.8768), `9` (0.8768) | current run |
| `angle_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768) | current run |
| `area_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) | current run |
| `close_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.8768) | current run |
| `close_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) | current run |
| `epsilon_min_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) | current run |
| `epsilon_steps` | Zombie | 0.0000 | 0.0000 | 100.0% | `9` (0.8768) | current run |
| `merge_fragmented_contours` | Zombie | 0.0000 | 0.0000 | 100.0% | `true` (0.8768) | current run |
| `minimum_projection_score` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.05` (0.8768), `0.08` (0.8768), `0.15` (0.8768) | current run |
| `projection_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) | current run |
| `rectangularity_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) | current run |

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
| 1 | 0.8542 | 0.8542 | 0.8542 | 0.0000 | 100.0% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
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

- Run ID: `run-20260820-035414`
- Detector: `contour_quad`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:54:14.148459+00:00`
- Finished: `2026-08-20T03:54:17.668311+00:00`
- Wall-clock elapsed: `3.5s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `41472`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.03%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — contour_quad

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `dfc24bbe7f30` | `49095b866d0d` | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | 0.8874 | 0 | 437 ms |
| Baseline | `HTH-0001` | `dfc24bbe7f30` | `bea942a4969a` | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 885 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `49095b866d0d` |
| Parameter Set ID (legacy alias) | `49095b866d0d` |
| Absolute parameter SHA-256 | `70d7a855c27c6bc821055d21c6d2ecfc7924e9546be1777c6a2c55fc5d15098c` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 1 |
| Total metric improvements | 2 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `bea942a4969a` | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | -0.0105 | 0.8768 | 0 | reference | reference |
| Best** | — | `49095b866d0d` | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | reference | reference |
| 1 | — | `f1832589441b` | `f1832589441b` | `f1832589441b` | 0.8768 | 0.7589 | 0.0734 | -0.0105 | 0.8768 | 0 | 2.1s | 100.00% |
| 2 | — | `d830fab26f05` | `d830fab26f05` | `d830fab26f05` | 0.8768 | 0.7589 | 0.0734 | -0.0105 | 0.8768 | 0 | 2.1s | 72.73% |
| 3 | — | `5a213f7d7eeb` | `5a213f7d7eeb` | `5a213f7d7eeb` | 0.8768 | 0.7589 | 0.0734 | -0.0105 | 0.8768 | 0 | 2.1s | 90.91% |
| 4 | — | `5ee8b6f684ab` | `5ee8b6f684ab` | `5ee8b6f684ab` | 0.8768 | 0.7589 | 0.0734 | -0.0105 | 0.8768 | 0 | 2.1s | 81.82% |
| 5 | — | `67a3c5ff528e` | `67a3c5ff528e` | `67a3c5ff528e` | 0.6531 | 0.0000 | 0.3777 | -0.2343 | 0.8164 | 1 | 1.7s | 27.27% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — contour_quad

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `49095b866d0d` | `49095b866d0d` | 0.8542 | 0.9069 | +0.0527 | Improved |
| 5 | `49095b866d0d` | `49095b866d0d` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `49095b866d0d` | `49095b866d0d` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `49095b866d0d` | `49095b866d0d` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `49095b866d0d` | `49095b866d0d` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `49095b866d0d` | `49095b866d0d` | 1.3s | 18.18% |

Total winner changes: **1**.
Search completed in **3.5s** wall-clock time.

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

## Calibration Intelligence — contour_quad

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035414`
- Calibration schema: `1.1`
- Detector: `contour_quad`
- Detector configuration: `hth-pipeline/config/detectors/contour_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `49095b866d0d`
- Recommended parameter short name: `49095b866d0d`
- Best observed Avg IoU: `0.8874`
- Avg IoU Success: `0.8874`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0731`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 41472 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 5h 1m 29s |
| Fully successful parameter sets | 5 (50.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.6531 |
| Avg IoU StdDev | 0.1119 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 5 (50.0%) |
| Equivalent-best configurations (within 0.0001) | 5 (50.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 41472 | 100.0% | 5h 1m 33s | 1.0× |
| Exhaustive | 41472 | 100.0% | 5h 1m 33s | 1.0× |
| Non-dormant | 8 | 0.0% | 3.5s | 5184.0× |
| Low+ | 8 | 0.0% | 3.5s | 5184.0× |
| Moderate+ | 8 | 0.0% | 3.5s | 5184.0× |
| Important+ | 8 | 0.0% | 3.5s | 5184.0× |
| Critical | 2 | 0.0% | 873 ms | 20736.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `merge_fragmented_contours` | Critical | 1.0000 | 0.2237 | 50.0% | `true` (0.8768), `false` (0.6531) | current run |
| `angle_weight` | Important | 0.1111 | 0.1243 | 100.0% | `0.2` (0.8768), `0.1` (0.7525) | current run |
| `rectangularity_weight` | Important | 0.1111 | 0.1243 | 100.0% | `0.3` (0.8768), `0.2` (0.7525) | current run |
| `edge_support_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.1` (0.7650), `0.15` (0.7650) | current run |
| `area_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.35` (0.7650) | current run |
| `close_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.7650) | current run |
| `close_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.7650) | current run |
| `edge_support_dilation_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.002` (0.7650), `0.004` (0.7650), `0.008` (0.7650) | current run |
| `epsilon_max_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.7650) | current run |
| `epsilon_min_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.008` (0.7650) | current run |
| `epsilon_steps` | Zombie | 0.0000 | 0.0000 | 100.0% | `9` (0.7650) | current run |
| `minimum_contour_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.12` (0.7650) | current run |
| `minimum_rectangularity` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.55` (0.7650) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `angle_weight` × `edge_support_weight` | 0.1333 | 0.0222 | 10 |
| `rectangularity_weight` × `edge_support_weight` | 0.1333 | 0.0222 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8799 | 0.8542 | 0.9055 | 0.0256 | 100.0% |
| 5 | 0.6563 | 0.4508 | 0.8618 | 0.2055 | 100.0% |
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

- Run ID: `run-20260820-035702`
- Detector: `convex_hull`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:57:02.070078+00:00`
- Finished: `2026-08-20T03:57:03.068491+00:00`
- Wall-clock elapsed: `998 ms`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.50%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — convex_hull

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `07aa4fec0974` | `04fd0a6e4bc2` | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | 0.9156 | 1 | 13 ms |
| Baseline | `HTH-0001` | `07aa4fec0974` | `74f5cad7945a` | `74f5cad7945a` | `baseline` | 0.6633 | 0.0000 | 0.3670 | 0.8291 | 1 | 31 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `04fd0a6e4bc2` |
| Parameter Set ID (legacy alias) | `04fd0a6e4bc2` |
| Absolute parameter SHA-256 | `860510d4626e5cf3b20de4ab3af6f4e9038b22773cb006175ab5d6c2cf51cab2` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `7e63509aa30d47a3dc13493d26242ba3716352258cf69db2e6e4fdf8fb95ff8e` |
| Grid ordinal | `0` |
| Reproducibility | **Fully reproducible** |

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
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `74f5cad7945a` | `74f5cad7945a` | `baseline` | 0.6633 | 0.0000 | 0.3670 | -0.0692 | 0.8291 | 1 | reference | reference |
| Best** | — | `04fd0a6e4bc2` | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | reference | reference |
| 1 | — | `f1f8a19fc636` | `f1f8a19fc636` | `f1f8a19fc636` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 86 ms | 45.45% |
| 2 | — | `b9dc838c7691` | `b9dc838c7691` | `b9dc838c7691` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 106 ms | 72.73% |
| 3 | — | `7199c38f19b9` | `7199c38f19b9` | `7199c38f19b9` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 134 ms | 100.00% |
| 4 | — | `c0dae043b64c` | `c0dae043b64c` | `c0dae043b64c` | 0.7261 | 0.0000 | 0.3642 | -0.0064 | 0.9076 | 1 | 71 ms | 36.36% |
| 5 | — | `b15680d0d573` | `b15680d0d573` | `b15680d0d573` | 0.7261 | 0.0000 | 0.3642 | -0.0064 | 0.9076 | 1 | 86 ms | 54.55% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — convex_hull

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.8668 | 0.8668 | +0.0000 | Unchanged |
| 5 | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.5316 | 0.8776 | +0.3460 | Improved |
| 6 | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.9585 | 0.9585 | +0.0000 | Unchanged |
| 10 | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.9593 | 0.9593 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 46 ms | 18.18% |

Total winner changes: **1**.
Search completed in **998 ms** wall-clock time.

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
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.0000 | No polygon found |

## Calibration Intelligence — convex_hull

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035702`
- Calibration schema: `1.1`
- Detector: `convex_hull`
- Detector configuration: `hth-pipeline/config/detectors/convex_hull.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `04fd0a6e4bc2`
- Recommended parameter short name: `04fd0a6e4bc2`
- Best observed Avg IoU: `0.7325`
- Avg IoU Success: `0.9156`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3683`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 28.3s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7325 |
| Minimum Avg IoU | 0.6633 |
| Avg IoU StdDev | 0.0193 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 46 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (36.4%) |
| Equivalent-best configurations (within 0.0001) | 4 (36.4%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 28.4s | 1.0× |
| Exhaustive | 2187 | 100.0% | 28.4s | 1.0× |
| Non-dormant | 288 | 13.2% | 3.7s | 7.6× |
| Low+ | 288 | 13.2% | 3.7s | 7.6× |
| Moderate+ | 288 | 13.2% | 3.7s | 7.6× |
| Important+ | 288 | 13.2% | 3.7s | 7.6× |
| Critical | 96 | 4.4% | 1.2s | 22.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `close_iterations` | Critical | 0.8357 | 0.0614 | 50.0% | `0` (0.7246), `1` (0.6633) | current run |
| `close_kernel_fraction` | Critical | 0.8357 | 0.0614 | 50.0% | `0` (0.7246), `0.008` (0.6633) | current run |
| `minimum_fragment_area_fraction` | Critical | 0.8357 | 0.0614 | 50.0% | `0.0002` (0.7246), `0.0005` (0.6633) | current run |
| `minimum_hull_area_fraction` | Critical | 0.8357 | 0.0614 | 50.0% | `0.1` (0.7246), `0.16` (0.6633) | current run |
| `minimum_solidity` | Critical | 0.2680 | 0.0259 | 100.0% | `0.35` (0.7238), `0.55` (0.6979) | current run |
| `polygon_epsilon_fraction` | Critical | 0.1684 | 0.0173 | 100.0% | `0.012` (0.7259), `0.05` (0.7238), `0.025` (0.7086) | current run |
| `bbox_padding_fraction` | Important | 0.0650 | 0.0133 | 33.3% | `0.008` (0.7261), `0` (0.7186), `0.016` (0.7128) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_solidity` × `polygon_epsilon_fraction` | 0.8523 | 0.5843 | 11 |
| `close_iterations` × `minimum_solidity` | 0.8523 | 0.0166 | 11 |
| `close_kernel_fraction` × `minimum_solidity` | 0.8523 | 0.0166 | 11 |
| `minimum_fragment_area_fraction` × `minimum_solidity` | 0.8523 | 0.0166 | 11 |
| `minimum_hull_area_fraction` × `minimum_solidity` | 0.8523 | 0.0166 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8597 | 0.8461 | 0.8668 | 0.0086 | 100.0% |
| 5 | 0.8581 | 0.5316 | 0.9030 | 0.1038 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9336 | 0.8982 | 0.9585 | 0.0252 | 100.0% |
| 10 | 0.9438 | 0.9165 | 0.9593 | 0.0177 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="cross-edge-contour-crossedgecontour-2"></a>
<details>
<summary><strong>Cross-Edge Contour (`cross_edge_contour`)</strong></summary>

**Status:** complete

## Run Information — cross_edge_contour

### Build Provenance

- Run ID: `run-20260820-035550`
- Detector: `cross_edge_contour`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:55:50.985101+00:00`
- Finished: `2026-08-20T03:55:59.088789+00:00`
- Wall-clock elapsed: `8.1s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `6562`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.15%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — cross_edge_contour

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `97a9ba3c5090` | `a5450e58ec9e` | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 969 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `a5450e58ec9e` |
| Parameter Set ID (legacy alias) | `a5450e58ec9e` |
| Absolute parameter SHA-256 | `3d82d36167e53106763fd0a6b3a2041b59b933e70d9b33ce55118a6eeb73b452` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| Winner changes | 0 |
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `a5450e58ec9e` | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | reference | reference |
| 1 | — | `0bd97323ddd6` | `0bd97323ddd6` | `0bd97323ddd6` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 2.5s | 30.00% |
| 2 | — | `5417f7a84576` | `5417f7a84576` | `5417f7a84576` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 2.3s | 20.00% |
| 3 | — | `491385b9c30f` | `491385b9c30f` | `491385b9c30f` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 3.7s | 40.00% |
| 4 | — | `5e7bbad85e3f` | `5e7bbad85e3f` | `5e7bbad85e3f` | 0.5527 | 0.0000 | 0.4528 | -0.3241 | 0.9211 | 2 | 3.9s | 50.00% |
| 5 | — | `9739acebc0a5` | `9739acebc0a5` | `9739acebc0a5` | 0.5527 | 0.0000 | 0.4528 | -0.3241 | 0.9211 | 2 | 4.9s | 60.00% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — cross_edge_contour

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `a5450e58ec9e` | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `a5450e58ec9e` | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `a5450e58ec9e` | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `a5450e58ec9e` | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `a5450e58ec9e` | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **8.1s** wall-clock time.

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

## Calibration Intelligence — cross_edge_contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035550`
- Calibration schema: `1.1`
- Detector: `cross_edge_contour`
- Detector configuration: `hth-pipeline/config/detectors/cross_edge_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `a5450e58ec9e`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 6 of 10 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 1h 45m 44s |
| Fully successful parameter sets | 4 (40.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.3818 |
| Avg IoU StdDev | 0.2113 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 4 (40.0%) |
| Equivalent-best configurations (within 0.0001) | 4 (40.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 6561 | 100.0% | 1h 45m 52s | 1.0× |
| Exhaustive | 6561 | 100.0% | 1h 45m 52s | 1.0× |
| Non-dormant | 768 | 11.7% | 12m 24s | 8.5× |
| Low+ | 768 | 11.7% | 12m 24s | 8.5× |
| Moderate+ | 768 | 11.7% | 12m 24s | 8.5× |
| Important+ | 256 | 3.9% | 4m 8s | 25.6× |
| Critical | 256 | 3.9% | 4m 8s | 25.6× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_polarity_consistency` | Critical | 1.0000 | 0.4950 | 50.0% | `0.5` (0.8768), `0.55` (0.8768), `0.65` (0.5527) | current run |
| `epsilon_max_fraction` | Critical | 0.1503 | 0.2730 | 100.0% | `0.04` (0.8768), `0.03` (0.6038) | current run |
| `minimum_contour_area_fraction` | Critical | 0.1503 | 0.2730 | 100.0% | `0.12` (0.8768), `0.08` (0.6038) | current run |
| `minimum_cross_edge_contrast` | Critical | 0.1503 | 0.2730 | 100.0% | `0.045` (0.8768), `0.02` (0.6038) | current run |
| `minimum_rectangularity` | Critical | 0.1503 | 0.2730 | 100.0% | `0.55` (0.8768), `0.45` (0.6038) | current run |
| `sample_offset_fraction` | Critical | 0.1503 | 0.2730 | 100.0% | `0.008` (0.8768), `0.004` (0.6038) | current run |
| `samples_per_edge` | Critical | 0.1503 | 0.2730 | 100.0% | `48` (0.8768), `24` (0.6038) | current run |
| `contour_weight` | Important | 0.1353 | 0.0000 | 100.0% | `0.45` (0.8768) | current run |
| `polarity_weight` | Important | 0.1353 | 0.0000 | 100.0% | `0.15` (0.8768) | current run |
| `contrast_weight` | Moderate | 0.0251 | 0.0683 | 100.0% | `0.4` (0.6720), `0.3` (0.6038), `0.5` (0.6038) | current run |

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
| 1 | 0.5980 | 0.0000 | 0.8542 | 0.3915 | 70.0% |
| 5 | 0.3447 | 0.0000 | 0.8618 | 0.4222 | 40.0% |
| 6 | 0.3036 | 0.0000 | 0.7589 | 0.3718 | 40.0% |
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

- Run ID: `run-20260820-035452`
- Detector: `dhsegment_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:54:52.139410+00:00`
- Finished: `2026-08-20T03:55:26.188481+00:00`
- Wall-clock elapsed: `34s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `10000`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.11%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — dhsegment_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `16aa45a0d95c` | `15434712cddf` | `15434712cddf` | `15434712cddf` | 0.9735 | 0.9634 | 0.0100 | 0.9735 | 0 | 188 ms |
| Baseline | `HTH-0001` | `16aa45a0d95c` | `013084b6c0e9` | `013084b6c0e9` | `baseline` | 0.9670 | 0.9424 | 0.0148 | 0.9670 | 0 | 86 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `15434712cddf` |
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
| [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | 2026-08-16 | `15434712cddf` | `15434712cddf` | authoritative |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `013084b6c0e9` | `013084b6c0e9` | `baseline` | 0.9670 | 0.9424 | 0.0148 | -0.0065 | 0.9670 | 0 | reference | reference |
| Best** | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `15434712cddf` | `15434712cddf` | `15434712cddf` | 0.9735 | 0.9634 | 0.0100 | +0.0000 | 0.9735 | 0 | reference | reference |
| 1 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `28199c1dee3e` | `28199c1dee3e` | `28199c1dee3e` | 0.9729 | 0.9571 | 0.0120 | -0.0006 | 0.9729 | 0 | 916 ms | 81.82% |
| 2 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `eaa0fe25898d` | `eaa0fe25898d` | `eaa0fe25898d` | 0.9729 | 0.9571 | 0.0120 | -0.0006 | 0.9729 | 0 | 990 ms | 90.91% |
| 3 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `171496d5337d` | `171496d5337d` | `171496d5337d` | 0.9691 | 0.9479 | 0.0137 | -0.0044 | 0.9691 | 0 | 825 ms | 72.73% |
| 4 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `3ac283e1a83c` | `3ac283e1a83c` | `3ac283e1a83c` | 0.9691 | 0.9479 | 0.0137 | -0.0044 | 0.9691 | 0 | 825 ms | 63.64% |
| 5 | [#455](https://github.com/dlstupka/hth/actions/runs/31975517634) | `bebf5b6a6773` | `bebf5b6a6773` | `bebf5b6a6773` | 0.9670 | 0.9424 | 0.0148 | -0.0065 | 0.9670 | 0 | 702 ms | 45.45% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — dhsegment_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `15434712cddf` | `15434712cddf` | 0.9694 | 0.9757 | +0.0064 | Improved |
| 5 | `15434712cddf` | `15434712cddf` | 0.9424 | 0.9634 | +0.0210 | Improved |
| 6 | `15434712cddf` | `15434712cddf` | 0.9891 | 0.9919 | +0.0029 | Improved |
| 9 | `15434712cddf` | `15434712cddf` | 0.9665 | 0.9671 | +0.0006 | Unchanged |
| 10 | `15434712cddf` | `15434712cddf` | 0.9676 | 0.9695 | +0.0019 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `15434712cddf` | `15434712cddf` | 279 ms | 18.18% |

Total winner changes: **1**.
Search completed in **34s** wall-clock time.

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

## Calibration Intelligence — dhsegment_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035452`
- Calibration schema: `1.1`
- Detector: `dhsegment_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/dhsegment_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
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
- Calibration evidence: `Medium`
- Dormant parameters: `fill_holes`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 10000 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 31m 8s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9735 |
| Minimum Avg IoU | 0.9636 |
| Avg IoU StdDev | 0.0036 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 279 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (27.3%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 10000 | 100.0% | 31m 10s | 1.0× |
| Exhaustive | 10000 | 100.0% | 31m 10s | 1.0× |
| Non-dormant | 144 | 1.4% | 26.9s | 69.4× |
| Low+ | 144 | 1.4% | 26.9s | 69.4× |
| Moderate+ | 72 | 0.7% | 13.5s | 138.9× |
| Important+ | 72 | 0.7% | 13.5s | 138.9× |
| Critical | 72 | 0.7% | 13.5s | 138.9× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `contour_offset_fraction` | Critical | 0.9980 | 0.0095 | 25.0% | `0.008` (0.9731), `0.004` (0.9691), `0` (0.9670) | current run |
| `open_kernel_fraction` | Critical | 0.3534 | 0.0100 | 66.7% | `0.006` (0.9735), `0` (0.9680), `0.0015` (0.9636) | current run |
| `close_kernel_fraction` | Critical | 0.2294 | 0.0065 | 66.7% | `0.0025` (0.9735), `0` (0.9676), `0.005` (0.9670) | current run |
| `probability_threshold` | Critical | 0.2265 | 0.0059 | 100.0% | `0.35` (0.9735), `-1` (0.9676) | current run |
| `minimum_page_area_fraction` | Low | 0.0101 | 0.0013 | 50.0% | `0.1` (0.9682), `0.2` (0.9670) | current run |
| `fill_holes` | Dormant | 0.0021 | 0.0003 | 100.0% | `0` (0.9683), `1` (0.9679) | current run |

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

`fill_holes`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `close_kernel_fraction` × `fill_holes` | 0.2437 | 0.0144 | 11 |
| `probability_threshold` × `fill_holes` | 0.2356 | 0.0091 | 11 |
| `open_kernel_fraction` × `close_kernel_fraction` | 0.3621 | 0.0088 | 11 |
| `open_kernel_fraction` × `minimum_page_area_fraction` | 0.3621 | 0.0088 | 11 |
| `probability_threshold` × `minimum_page_area_fraction` | 0.2294 | 0.0029 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9708 | 0.9653 | 0.9780 | 0.0045 | 100.0% |
| 5 | 0.9463 | 0.9361 | 0.9634 | 0.0089 | 100.0% |
| 6 | 0.9890 | 0.9840 | 0.9928 | 0.0033 | 100.0% |
| 9 | 0.9667 | 0.9652 | 0.9679 | 0.0011 | 100.0% |
| 10 | 0.9678 | 0.9672 | 0.9695 | 0.0008 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="distance-transform-detector-distancetransform-2"></a>
<details>
<summary><strong>Distance Transform Detector (`distance_transform`)</strong></summary>

**Status:** complete

## Run Information — distance_transform

### Build Provenance

- Run ID: `run-20260820-035630`
- Detector: `distance_transform`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:30.875755+00:00`
- Finished: `2026-08-20T03:56:38.809056+00:00`
- Wall-clock elapsed: `7.9s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.50%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
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
| Winner | `HTH-0001` | `bcaf51048d46` | `e66a7546e1a7` | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | 0.8388 | 0 | 875 ms |
| Baseline | `HTH-0001` | `bcaf51048d46` | `8b59bc493e1f` | `8b59bc493e1f` | `baseline` | 0.7593 | 0.4357 | 0.2472 | 0.7593 | 0 | 935 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `e66a7546e1a7` |
| Parameter Set ID (legacy alias) | `e66a7546e1a7` |
| Absolute parameter SHA-256 | `653a65978067647a0c76375d58880a511a5e97322c0a2da5746740ec2044b547` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `eb26756f83e39af392d5371674497c8b57953520411287a79867e81bf2b547a2` |
| Grid ordinal | `1` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 2 |
| StdDev improvements | 2 |
| Total metric improvements | 5 |
| Parameter sets with improvements | 2 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `8b59bc493e1f` | `8b59bc493e1f` | `baseline` | 0.7593 | 0.4357 | 0.2472 | -0.0795 | 0.7593 | 0 | reference | reference |
| Best** | — | `e66a7546e1a7` | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | reference | reference |
| 1 | — | `8e57ff70b94c` | `8e57ff70b94c` | `8e57ff70b94c` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 3.8s | 54.55% |
| 2 | — | `d0c1acdb2940` | `d0c1acdb2940` | `d0c1acdb2940` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5s | 81.82% |
| 3 | — | `98c86be0e2ce` | `98c86be0e2ce` | `98c86be0e2ce` | 0.8358 | 0.4784 | 0.1871 | -0.0029 | 0.8358 | 0 | 3.2s | 36.36% |
| 4 | — | `823d0ace1a0f` | `823d0ace1a0f` | `823d0ace1a0f` | 0.8358 | 0.4784 | 0.1871 | -0.0029 | 0.8358 | 0 | 3.6s | 45.45% |
| 5 | — | `26026b725659` | `26026b725659` | `26026b725659` | 0.8358 | 0.4784 | 0.1871 | -0.0029 | 0.8358 | 0 | 4.4s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — distance_transform

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `e66a7546e1a7` | `e66a7546e1a7` | 0.9648 | 0.9734 | +0.0086 | Improved |
| 5 | `e66a7546e1a7` | `e66a7546e1a7` | 0.4784 | 0.5001 | +0.0217 | Improved |
| 6 | `e66a7546e1a7` | `e66a7546e1a7` | 0.4357 | 0.8475 | +0.4118 | Improved |
| 9 | `e66a7546e1a7` | `e66a7546e1a7` | 0.9585 | 0.9276 | -0.0309 | Regressed |
| 10 | `e66a7546e1a7` | `e66a7546e1a7` | 0.9593 | 0.9454 | -0.0139 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `e66a7546e1a7` | `e66a7546e1a7` | 1.8s | 18.18% |

Total winner changes: **1**.
Search completed in **7.9s** wall-clock time.

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
| 9 | `e66a7546e1a7` | `e66a7546e1a7` | 0.9276 | Regressed |
| 10 | `e66a7546e1a7` | `e66a7546e1a7` | 0.9454 | Regressed |

## Calibration Intelligence — distance_transform

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035630`
- Calibration schema: `1.1`
- Detector: `distance_transform`
- Detector configuration: `hth-pipeline/config/detectors/distance_transform.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `e66a7546e1a7`
- Recommended parameter short name: `e66a7546e1a7`
- Best observed Avg IoU: `0.8388`
- Avg IoU Success: `0.8388`
- Worst Golden Set page (Min IoU): `0.5001`
- Page-to-page StdDev: `0.1745`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 31m 42s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8388 |
| Minimum Avg IoU | 0.7593 |
| Avg IoU StdDev | 0.0221 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.8s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (27.3%) |
| Equivalent-best configurations (within 0.0001) | 3 (27.3%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 31m 52s | 1.0× |
| Exhaustive | 2187 | 100.0% | 31m 52s | 1.0× |
| Non-dormant | 288 | 13.2% | 4m 12s | 7.6× |
| Low+ | 288 | 13.2% | 4m 12s | 7.6× |
| Moderate+ | 288 | 13.2% | 4m 12s | 7.6× |
| Important+ | 288 | 13.2% | 4m 12s | 7.6× |
| Critical | 96 | 4.4% | 1m 24s | 22.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `close_kernel_fraction` | Critical | 0.9880 | 0.0763 | 50.0% | `0` (0.8357), `0.008` (0.7593) | current run |
| `distance_threshold_fraction` | Critical | 0.9880 | 0.0763 | 50.0% | `0.1` (0.8357), `0.18` (0.7593) | current run |
| `minimum_component_core_overlap` | Critical | 0.9880 | 0.0763 | 50.0% | `0.03` (0.8357), `0.08` (0.7593) | current run |
| `minimum_core_area_fraction` | Critical | 0.9880 | 0.0763 | 50.0% | `0.004` (0.8357), `0.01` (0.7593) | current run |
| `minimum_bbox_area_fraction` | Critical | 0.4418 | 0.0380 | 50.0% | `0.1` (0.8356), `0.16` (0.7976) | current run |
| `minimum_rectangularity` | Critical | 0.1734 | 0.0191 | 100.0% | `0.35` (0.8357), `0.7` (0.8356), `0.5` (0.8166) | current run |
| `bbox_padding_fraction` | Important | 0.1261 | 0.0182 | 33.3% | `0.008` (0.8388), `0.016` (0.8323), `0` (0.8205) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_bbox_area_fraction` × `minimum_rectangularity` | 0.9880 | 0.5462 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9630 | 0.9496 | 0.9734 | 0.0089 | 100.0% |
| 5 | 0.4956 | 0.4784 | 0.5197 | 0.0173 | 100.0% |
| 6 | 0.8075 | 0.4357 | 0.8772 | 0.1199 | 100.0% |
| 9 | 0.9336 | 0.8982 | 0.9585 | 0.0252 | 100.0% |
| 10 | 0.9438 | 0.9165 | 0.9593 | 0.0177 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="distance-transform-rectangle-proposal-distancetransformrect-2"></a>
<details>
<summary><strong>Distance-Transform Rectangle Proposal (`distance_transform_rect`)</strong></summary>

**Status:** complete

## Run Information — distance_transform_rect

### Build Provenance

- Run ID: `run-20260820-035658`
- Detector: `distance_transform_rect`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:58.719061+00:00`
- Finished: `2026-08-20T03:57:00.738741+00:00`
- Wall-clock elapsed: `2s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `729`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `1.51%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — distance_transform_rect

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `79a1d1aa4447` | `0a8482550c35` | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | 0.7243 | 0 | 139 ms |
| Baseline | `HTH-0001` | `79a1d1aa4447` | `e04459bcb474` | `e04459bcb474` | `baseline` | 0.6347 | 0.0000 | 0.3534 | 0.7933 | 1 | 118 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `0a8482550c35` |
| Parameter Set ID (legacy alias) | `0a8482550c35` |
| Absolute parameter SHA-256 | `51d7fef425396728362fbd5fe84634f94fdae09fee8e66f6b0f2425e2543d011` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `f83255e0995c0336ff5ad84a779600f049aeb629cbd697e2082c9c47ec12745b` |
| Grid ordinal | `521` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `e04459bcb474` | `e04459bcb474` | `baseline` | 0.6347 | 0.0000 | 0.3534 | -0.0896 | 0.7933 | 1 | reference | reference |
| Best** | — | `0a8482550c35` | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | reference | reference |
| 1 | — | `4be72657e9a7` | `4be72657e9a7` | `4be72657e9a7` | 0.6563 | 0.0000 | 0.3709 | -0.0679 | 0.8204 | 1 | 492 ms | 36.36% |
| 2 | — | `fb963211fbe9` | `fb963211fbe9` | `fb963211fbe9` | 0.6563 | 0.0000 | 0.3709 | -0.0679 | 0.8204 | 1 | 658 ms | 54.55% |
| 3 | — | `86b444be6e6e` | `86b444be6e6e` | `86b444be6e6e` | 0.6563 | 0.0000 | 0.3709 | -0.0679 | 0.8204 | 1 | 997 ms | 81.82% |
| 4 | — | `29e38f999fc0` | `29e38f999fc0` | `29e38f999fc0` | 0.6433 | 0.0000 | 0.3581 | -0.0810 | 0.8041 | 1 | 435 ms | 27.27% |
| 5 | — | `30ddd9d571be` | `30ddd9d571be` | `30ddd9d571be` | 0.6433 | 0.0000 | 0.3581 | -0.0810 | 0.8041 | 1 | 783 ms | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — distance_transform_rect

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `0a8482550c35` | `0a8482550c35` | 0.8697 | 0.9520 | +0.0823 | Improved |
| 5 | `0a8482550c35` | `0a8482550c35` | 0.4937 | 0.4499 | -0.0438 | Regressed |
| 6 | `0a8482550c35` | `0a8482550c35` | 0.0000 | 0.4523 | +0.4523 | Recovered |
| 9 | `0a8482550c35` | `0a8482550c35` | 0.8916 | 0.8884 | -0.0032 | Regressed |
| 10 | `0a8482550c35` | `0a8482550c35` | 0.9183 | 0.8788 | -0.0395 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `0a8482550c35` | `0a8482550c35` | 262 ms | 18.18% |

Total winner changes: **1**.
Search completed in **2s** wall-clock time.

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
- Poor matches (Winner IoU < 0.5000): `2`
- Regressed pages (Δ IoU < -0.0010): `3`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 5 | `0a8482550c35` | `0a8482550c35` | 0.4499 | Poor match; Regressed |
| 6 | `0a8482550c35` | `0a8482550c35` | 0.4523 | Poor match |
| 9 | `0a8482550c35` | `0a8482550c35` | 0.8884 | Regressed |
| 10 | `0a8482550c35` | `0a8482550c35` | 0.8788 | Regressed |

## Calibration Intelligence — distance_transform_rect

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035658`
- Calibration schema: `1.1`
- Detector: `distance_transform_rect`
- Detector configuration: `hth-pipeline/config/detectors/distance_transform_rect.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `0a8482550c35`
- Recommended parameter short name: `0a8482550c35`
- Best observed Avg IoU: `0.7243`
- Avg IoU Success: `0.7243`
- Worst Golden Set page (Min IoU): `0.4499`
- Page-to-page StdDev: `0.2245`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 10 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 1m 39s |
| Fully successful parameter sets | 1 (9.1%) |
| Best Avg IoU | 0.7243 |
| Minimum Avg IoU | 0.6310 |
| Avg IoU StdDev | 0.0254 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 262 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 1m 41s | 1.0× |
| Exhaustive | 729 | 100.0% | 1m 41s | 1.0× |
| Non-dormant | 216 | 29.6% | 29.9s | 3.4× |
| Low+ | 216 | 29.6% | 29.9s | 3.4× |
| Moderate+ | 216 | 29.6% | 29.9s | 3.4× |
| Important+ | 18 | 2.5% | 2.5s | 40.5× |
| Critical | 18 | 2.5% | 2.5s | 40.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `distance_threshold_fraction` | Critical | 0.8642 | 0.0896 | 33.3% | `0.3` (0.7243), `0.1` (0.6435), `0.18` (0.6347) | current run |
| `proposal_expansion_fraction` | Critical | 0.2979 | 0.0359 | 50.0% | `0.12` (0.6795), `0.06` (0.6435) | current run |
| `minimum_bbox_area_fraction` | Critical | 0.1664 | 0.0224 | 33.3% | `0.22` (0.6637), `0.08` (0.6435), `0.14` (0.6413) | current run |
| `minimum_core_area_fraction` | Moderate | 0.0368 | 0.0170 | 50.0% | `0.002` (0.6516), `0.006` (0.6347) | current run |
| `minimum_mask_coverage` | Moderate | 0.0368 | 0.0170 | 50.0% | `0.06` (0.6516), `0.12` (0.6347) | current run |
| `bbox_padding_fraction` | Moderate | 0.0303 | 0.0111 | 33.3% | `0.016` (0.6543), `0` (0.6509), `0.008` (0.6433) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `proposal_expansion_fraction` × `bbox_padding_fraction` | 1.0000 | 0.7021 | 11 |
| `proposal_expansion_fraction` × `minimum_bbox_area_fraction` | 0.8642 | 0.5663 | 11 |
| `proposal_expansion_fraction` × `minimum_core_area_fraction` | 0.8642 | 0.5663 | 11 |
| `proposal_expansion_fraction` × `minimum_mask_coverage` | 0.8642 | 0.5663 | 11 |
| `minimum_bbox_area_fraction` × `bbox_padding_fraction` | 0.3535 | 0.1871 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9043 | 0.8697 | 0.9520 | 0.0245 | 100.0% |
| 5 | 0.4946 | 0.4499 | 0.5131 | 0.0174 | 100.0% |
| 6 | 0.0411 | 0.0000 | 0.4523 | 0.1300 | 9.1% |
| 9 | 0.8955 | 0.8682 | 0.9256 | 0.0213 | 100.0% |
| 10 | 0.9150 | 0.8788 | 0.9433 | 0.0220 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="doc-ufcn-page-mask-detector-docufcnpagemask-2"></a>
<details>
<summary><strong>Doc-UFCN Page-Mask Detector (`doc_ufcn_page_mask`)</strong></summary>

**Status:** complete

## Run Information — doc_ufcn_page_mask

### Build Provenance

- Run ID: `run-20260820-035249`
- Detector: `doc_ufcn_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:52:49.218796+00:00`
- Finished: `2026-08-20T03:53:12.390218+00:00`
- Wall-clock elapsed: `23.2s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2000`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.55%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — doc_ufcn_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `bfd166146734` | `595002645fcc` | `595002645fcc` | `595002645fcc` | 0.9747 | 0.9545 | 0.0119 | 0.9747 | 0 | 151 ms |
| Baseline | `HTH-0001` | `bfd166146734` | `329dcc7161e9` | `329dcc7161e9` | `baseline` | 0.8906 | 0.8515 | 0.0406 | 0.8906 | 0 | 58 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

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
| [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | 2026-08-20 | `595002645fcc` | `595002645fcc` | authoritative |
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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 2 |
| Total metric improvements | 4 |
| Parameter sets with improvements | 2 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | `329dcc7161e9` | `329dcc7161e9` | `baseline` | 0.8906 | 0.8515 | 0.0406 | -0.0841 | 0.8906 | 0 | reference | reference |
| Best** | [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | `595002645fcc` | `595002645fcc` | `595002645fcc` | 0.9747 | 0.9545 | 0.0119 | +0.0000 | 0.9747 | 0 | reference | reference |
| 1 | [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | `a5b5f0a03acf` | `a5b5f0a03acf` | `a5b5f0a03acf` | 0.9747 | 0.9545 | 0.0119 | +0.0000 | 0.9747 | 0 | 713 ms | 100.00% |
| 2 | [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | `45a72b95bd15` | `45a72b95bd15` | `45a72b95bd15` | 0.9656 | 0.9181 | 0.0249 | -0.0091 | 0.9656 | 0 | 688 ms | 90.91% |
| 3 | [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | `cb7b5ba5905b` | `cb7b5ba5905b` | `cb7b5ba5905b` | 0.9485 | 0.9423 | 0.0064 | -0.0262 | 0.9485 | 0 | 681 ms | 81.82% |
| 4 | [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | `2c66b3ee474f` | `2c66b3ee474f` | `2c66b3ee474f` | 0.9241 | 0.9082 | 0.0168 | -0.0506 | 0.9241 | 0 | 657 ms | 63.64% |
| 5 | [#590](https://github.com/dlstupka/hth/actions/runs/32329218231) | `2cd594505fcb` | `2cd594505fcb` | `2cd594505fcb` | 0.9066 | 0.8811 | 0.0304 | -0.0681 | 0.9066 | 0 | 659 ms | 72.73% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — doc_ufcn_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `595002645fcc` | `595002645fcc` | 0.8565 | 0.9770 | +0.1205 | Improved |
| 5 | `595002645fcc` | `595002645fcc` | 0.9468 | 0.9545 | +0.0076 | Improved |
| 6 | `595002645fcc` | `595002645fcc` | 0.9327 | 0.9708 | +0.0381 | Improved |
| 9 | `595002645fcc` | `595002645fcc` | 0.8515 | 0.9900 | +0.1385 | Improved |
| 10 | `595002645fcc` | `595002645fcc` | 0.8657 | 0.9814 | +0.1157 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `595002645fcc` | `595002645fcc` | 227 ms | 18.18% |

Total winner changes: **1**.
Search completed in **23.2s** wall-clock time.

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

## Calibration Intelligence — doc_ufcn_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035249`
- Calibration schema: `1.1`
- Detector: `doc_ufcn_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/doc_ufcn_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `595002645fcc`
- Recommended parameter short name: `595002645fcc`
- Best observed Avg IoU: `0.9747`
- Avg IoU Success: `0.9747`
- Worst Golden Set page (Min IoU): `0.9545`
- Page-to-page StdDev: `0.0119`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2000 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 4m 59s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9747 |
| Minimum Avg IoU | 0.8324 |
| Avg IoU StdDev | 0.0477 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 227 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (18.2%) |
| Equivalent-best configurations (within 0.0001) | 2 (18.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2000 | 100.0% | 5m 1s | 1.0× |
| Exhaustive | 2000 | 100.0% | 5m 1s | 1.0× |
| Non-dormant | 108 | 5.4% | 16.3s | 18.5× |
| Low+ | 108 | 5.4% | 16.3s | 18.5× |
| Moderate+ | 108 | 5.4% | 16.3s | 18.5× |
| Important+ | 27 | 1.4% | 4.1s | 74.1× |
| Critical | 27 | 1.4% | 4.1s | 74.1× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `page_padding_fraction` | Critical | 1.0000 | 0.1423 | 11.1% | `0.01` (0.9747), `0` (0.9656), `0.02` (0.9485) | current run |
| `minimum_page_area_fraction` | Critical | 0.1837 | 0.0841 | 66.7% | `0.2` (0.9747), `0.08` (0.9072), `0.12` (0.8906) | current run |
| `minimum_component_area_fraction` | Moderate | 0.0425 | 0.0255 | 100.0% | `0.0005` (0.9327), `0` (0.9072) | current run |
| `minimum_confidence` | Moderate | 0.0425 | 0.0255 | 100.0% | `0.5` (0.9327), `0` (0.9072) | current run |

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
| 1 | 0.8899 | 0.7810 | 0.9770 | 0.0681 | 100.0% |
| 5 | 0.9354 | 0.8752 | 0.9595 | 0.0262 | 100.0% |
| 6 | 0.9457 | 0.9327 | 0.9899 | 0.0200 | 100.0% |
| 9 | 0.8894 | 0.7696 | 0.9900 | 0.0756 | 100.0% |
| 10 | 0.8986 | 0.8035 | 0.9814 | 0.0618 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="edge-supported-contour-edgecontour-2"></a>
<details>
<summary><strong>Edge-Supported Contour (`edge_contour`)</strong></summary>

**Status:** complete

## Run Information — edge_contour

### Build Provenance

- Run ID: `run-20260820-035610`
- Detector: `edge_contour`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:10.446810+00:00`
- Finished: `2026-08-20T03:56:18.522504+00:00`
- Wall-clock elapsed: `8.1s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `13123`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.08%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — edge_contour

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `3b09a8916348` | `4e5bc37a649a` | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 695 ms |
| Baseline | `HTH-0001` | `3b09a8916348` | `cc91b22426bb` | `cc91b22426bb` | `baseline` | 0.5392 | 0.0000 | 0.4417 | 0.8986 | 2 | 1.2s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `4e5bc37a649a` |
| Parameter Set ID (legacy alias) | `4e5bc37a649a` |
| Absolute parameter SHA-256 | `e90be8501b7f84d03b43a0cc9f6ea6ba11832e6e42413165d06070479176eefa` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `958a995e6b36cf6431e45752f2997f42d4312be8c9546b66cef8c00397b51ca9` |
| Grid ordinal | `0` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `cc91b22426bb` | `cc91b22426bb` | `baseline` | 0.5392 | 0.0000 | 0.4417 | -0.3377 | 0.8986 | 2 | reference | reference |
| Best** | — | `4e5bc37a649a` | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | reference | reference |
| 1 | — | `3f9b315b2a2d` | `3f9b315b2a2d` | `3f9b315b2a2d` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 3s | 36.36% |
| 2 | — | `06aecf5b236a` | `06aecf5b236a` | `06aecf5b236a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 2.7s | 27.27% |
| 3 | — | `3fc2f6f9c2c2` | `3fc2f6f9c2c2` | `3fc2f6f9c2c2` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 6.2s | 90.91% |
| 4 | — | `466c3d5add05` | `466c3d5add05` | `466c3d5add05` | 0.3651 | 0.0000 | 0.4483 | -0.5117 | 0.9128 | 3 | 3.3s | 45.45% |
| 5 | — | `908717e8cc63` | `908717e8cc63` | `908717e8cc63` | 0.3651 | 0.0000 | 0.4483 | -0.5117 | 0.9128 | 3 | 3.9s | 54.55% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — edge_contour

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `4e5bc37a649a` | `4e5bc37a649a` | 0.0000 | 0.8542 | +0.8542 | Recovered |
| 5 | `4e5bc37a649a` | `4e5bc37a649a` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `4e5bc37a649a` | `4e5bc37a649a` | 0.0000 | 0.7589 | +0.7589 | Recovered |
| 9 | `4e5bc37a649a` | `4e5bc37a649a` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `4e5bc37a649a` | `4e5bc37a649a` | 0.8703 | 0.9454 | +0.0751 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `4e5bc37a649a` | `4e5bc37a649a` | 1.9s | 18.18% |

Total winner changes: **1**.
Search completed in **8.1s** wall-clock time.

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

## Calibration Intelligence — edge_contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035610`
- Calibration schema: `1.1`
- Detector: `edge_contour`
- Detector configuration: `hth-pipeline/config/detectors/edge_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `4e5bc37a649a`
- Recommended parameter short name: `4e5bc37a649a`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Low`
- Dormant parameters: `epsilon_max_fraction, lsd_refine_mode, lsd_scale, minimum_contour_area_fraction, minimum_rectangularity, minimum_segment_length_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 6 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 7 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 13123 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 2h 31m 39s |
| Fully successful parameter sets | 4 (36.4%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.1928 |
| Avg IoU StdDev | 0.2865 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.9s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (36.4%) |
| Equivalent-best configurations (within 0.0001) | 4 (36.4%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 13122 | 100.0% | 2h 31m 46s | 1.0× |
| Exhaustive | 13122 | 100.0% | 2h 31m 46s | 1.0× |
| Non-dormant | 18 | 0.1% | 12.5s | 729.0× |
| Low+ | 18 | 0.1% | 12.5s | 729.0× |
| Moderate+ | 18 | 0.1% | 12.5s | 729.0× |
| Important+ | 6 | 0.0% | 4.2s | 2187.0× |
| Critical | 3 | 0.0% | 2.1s | 4374.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_edge_support` | Critical | 0.9748 | 0.6841 | 33.3% | `0.05` (0.8768), `0.12` (0.4086), `0.2` (0.1928) | current run |
| `edge_support_dilation_fraction` | Important | 0.0957 | 0.2298 | 100.0% | `0.006` (0.7080), `0.003` (0.4782) | current run |
| `edge_support_weight` | Moderate | 0.0238 | 0.0996 | 100.0% | `0.2` (0.5779), `0.3` (0.4935), `0.4` (0.4782) | current run |
| `epsilon_max_fraction` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.04` (0.5392), `0.03` (0.5181) | current run |
| `lsd_refine_mode` | Dormant | 0.0004 | 0.0211 | 50.0% | `std` (0.5392), `none` (0.5181) | current run |
| `lsd_scale` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.8` (0.5392), `0.6` (0.5181) | current run |
| `minimum_contour_area_fraction` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.12` (0.5392), `0.08` (0.5181) | current run |
| `minimum_rectangularity` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.55` (0.5392), `0.45` (0.5181) | current run |
| `minimum_segment_length_fraction` | Dormant | 0.0004 | 0.0211 | 50.0% | `0.06` (0.5392), `0.03` (0.5181) | current run |
| `angle_weight` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.2` (0.5392) | current run |
| `area_weight` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.25` (0.5392) | current run |
| `close_iterations` | Zombie | 0.0004 | 0.0000 | 0.0% | `1` (0.5392) | current run |
| `close_kernel_fraction` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.008` (0.5392) | current run |
| `epsilon_min_fraction` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.008` (0.5392) | current run |
| `epsilon_steps` | Zombie | 0.0004 | 0.0000 | 0.0% | `9` (0.5392) | current run |
| `merge_fragmented_contours` | Zombie | 0.0004 | 0.0000 | 0.0% | `true` (0.5392) | current run |
| `rectangularity_weight` | Zombie | 0.0004 | 0.0000 | 0.0% | `0.25` (0.5392) | current run |

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

`epsilon_max_fraction`, `lsd_refine_mode`, `lsd_scale`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `minimum_segment_length_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `edge_support_dilation_fraction` × `edge_support_weight` | 0.1588 | 0.0631 | 11 |
| `edge_support_dilation_fraction` × `epsilon_max_fraction` | 0.1588 | 0.0631 | 11 |
| `edge_support_dilation_fraction` × `lsd_refine_mode` | 0.1588 | 0.0631 | 11 |
| `edge_support_dilation_fraction` × `lsd_scale` | 0.1588 | 0.0631 | 11 |
| `minimum_edge_support` × `edge_support_dilation_fraction` | 1.0000 | 0.0252 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.3106 | 0.0000 | 0.8542 | 0.4109 | 36.4% |
| 5 | 0.6267 | 0.0000 | 0.8618 | 0.3838 | 72.7% |
| 6 | 0.2760 | 0.0000 | 0.7589 | 0.3651 | 36.4% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.4229 | 0.0000 | 0.9454 | 0.4637 | 45.5% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-segmentation-grabcut-2"></a>
<details>
<summary><strong>GrabCut Segmentation (`grabcut`)</strong></summary>

**Status:** complete

## Run Information — grabcut

### Build Provenance

- Run ID: `run-20260820-035207`
- Detector: `grabcut`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:52:07.163888+00:00`
- Finished: `2026-08-20T03:53:35.638961+00:00`
- Wall-clock elapsed: `1m 28s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `13122`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.08%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — grabcut

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `bd476134059a` | `110867d137a9` | `110867d137a9` | `110867d137a9` | 0.8394 | 0.6041 | 0.1440 | 0.8394 | 0 | 34.1s |
| Baseline | `HTH-0001` | `bd476134059a` | `018d128420cb` | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 28.6s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `110867d137a9` |
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
| [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | 2026-08-16 | `110867d137a9` | `110867d137a9` | authoritative |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `018d128420cb` | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | -0.0263 | 0.8130 | 0 | reference | reference |
| Best** | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `110867d137a9` | `110867d137a9` | `110867d137a9` | 0.8394 | 0.6041 | 0.1440 | +0.0000 | 0.8394 | 0 | reference | reference |
| 1 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `0e1da08a0efd` | `0e1da08a0efd` | `0e1da08a0efd` | 0.7400 | 0.3516 | 0.2645 | -0.0994 | 0.7400 | 0 | 1m 27s | 27.27% |
| 2 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `3a127ecba148` | `3a127ecba148` | `3a127ecba148` | 0.7400 | 0.3516 | 0.2645 | -0.0994 | 0.7400 | 0 | 1m 27s | 54.55% |
| 3 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `c441348e0a37` | `c441348e0a37` | `c441348e0a37` | 0.7400 | 0.3516 | 0.2645 | -0.0994 | 0.7400 | 0 | 1m 28s | 72.73% |
| 4 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `cfd87bfbcb9d` | `cfd87bfbcb9d` | `cfd87bfbcb9d` | 0.7400 | 0.3516 | 0.2645 | -0.0994 | 0.7400 | 0 | 1m 28s | 81.82% |
| 5 | [#447](https://github.com/dlstupka/hth/actions/runs/31955479629) | `71c8fb00da00` | `71c8fb00da00` | `71c8fb00da00` | 0.7400 | 0.3516 | 0.2645 | -0.0994 | 0.7400 | 0 | 1m 28s | 90.91% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — grabcut

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `110867d137a9` | `110867d137a9` | 0.9568 | 0.9578 | +0.0010 | Improved |
| 5 | `110867d137a9` | `110867d137a9` | 0.5532 | 0.6041 | +0.0509 | Improved |
| 6 | `110867d137a9` | `110867d137a9` | 0.6683 | 0.7378 | +0.0695 | Improved |
| 9 | `110867d137a9` | `110867d137a9` | 0.9422 | 0.9433 | +0.0010 | Improved |
| 10 | `110867d137a9` | `110867d137a9` | 0.9447 | 0.9540 | +0.0093 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `110867d137a9` | `110867d137a9` | 1m 3s | 18.18% |

Total winner changes: **1**.
Search completed in **1m 28s** wall-clock time.

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

- Calibration run ID: `run-20260820-035207`
- Calibration schema: `1.1`
- Detector: `grabcut`
- Detector configuration: `hth-pipeline/config/detectors/grabcut.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `110867d137a9`
- Recommended parameter short name: `110867d137a9`
- Best observed Avg IoU: `0.8394`
- Avg IoU Success: `0.8394`
- Worst Golden Set page (Min IoU): `0.6041`
- Page-to-page StdDev: `0.1440`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 13122 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 5d 4h 9m 21s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8394 |
| Minimum Avg IoU | 0.7400 |
| Avg IoU StdDev | 0.0337 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1m 3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 13122 | 100.0% | 5d 4h 15m 36s | 1.0× |
| Exhaustive | 13122 | 100.0% | 5d 4h 15m 36s | 1.0× |
| Non-dormant | 1944 | 14.8% | 18h 24m 32s | 6.8× |
| Low+ | 1944 | 14.8% | 18h 24m 32s | 6.8× |
| Moderate+ | 1944 | 14.8% | 18h 24m 32s | 6.8× |
| Important+ | 1944 | 14.8% | 18h 24m 32s | 6.8× |
| Critical | 648 | 4.9% | 6h 8m 11s | 20.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `erosion_iterations` | Critical | 1.0000 | 0.0994 | 33.3% | `2` (0.8394), `1` (0.8130), `0` (0.7400) | current run |
| `grabcut_iterations` | Critical | 1.0000 | 0.0994 | 33.3% | `5` (0.8394), `3` (0.8130), `1` (0.7400) | current run |
| `minimum_bbox_area_fraction` | Critical | 1.0000 | 0.0994 | 33.3% | `0.15` (0.8394), `0.1` (0.8130), `0.07` (0.7400) | current run |
| `border_fraction` | Critical | 0.2893 | 0.0631 | 50.0% | `0.02` (0.8130), `0.01` (0.7499) | current run |
| `close_kernel_fraction` | Critical | 0.2893 | 0.0631 | 50.0% | `0.02` (0.8130), `0.01` (0.7499) | current run |
| `erosion_kernel_fraction` | Critical | 0.2893 | 0.0631 | 50.0% | `0.015` (0.8130), `0.0075` (0.7499) | current run |
| `polygon_epsilon_fraction` | Critical | 0.2593 | 0.0345 | 33.3% | `0.018` (0.7745), `0.01` (0.7400), `0.03` (0.7400) | current run |
| `minimum_contour_area_fraction` | Important | 0.0880 | 0.0248 | 33.3% | `0.02` (0.7648), `0.04` (0.7583), `0.07` (0.7400) | current run |
| `close_iterations` | Zombie | 0.0000 | 0.0000 | 100.0% | `1` (0.7557) | current run |

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
| 1 | 0.9609 | 0.9568 | 0.9617 | 0.0017 | 100.0% |
| 5 | 0.3929 | 0.3516 | 0.6041 | 0.0883 | 100.0% |
| 6 | 0.5283 | 0.4895 | 0.7378 | 0.0837 | 100.0% |
| 9 | 0.9432 | 0.9422 | 0.9433 | 0.0003 | 100.0% |
| 10 | 0.9531 | 0.9447 | 0.9540 | 0.0027 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-contour-grabcutcontour-2"></a>
<details>
<summary><strong>GrabCut + Contour (`grabcut_contour`)</strong></summary>

**Status:** complete

## Run Information — grabcut_contour

### Build Provenance

- Run ID: `run-20260820-035207`
- Detector: `grabcut_contour`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:52:07.311786+00:00`
- Finished: `2026-08-20T03:53:53.928365+00:00`
- Wall-clock elapsed: `1m 47s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `46657`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — grabcut_contour

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `29f3ef9c9b1a` | `3a1623be3b6e` | `3a1623be3b6e` | `3a1623be3b6e` | 0.8772 | 0.7198 | 0.0893 | 0.8772 | 0 | 43.1s |
| Baseline | `HTH-0001` | `29f3ef9c9b1a` | `3817f226228a` | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 29.7s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `3a1623be3b6e` |
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
| [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | 2026-08-18 | `3a1623be3b6e` | `3a1623be3b6e` | authoritative |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `3817f226228a` | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | -0.0642 | 0.8130 | 0 | reference | reference |
| Best** | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `3a1623be3b6e` | `3a1623be3b6e` | `3a1623be3b6e` | 0.8772 | 0.7198 | 0.0893 | +0.0000 | 0.8772 | 0 | reference | reference |
| 1 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `483f54de1394` | `483f54de1394` | `483f54de1394` | 0.8130 | 0.5532 | 0.1692 | -0.0642 | 0.8130 | 0 | 1m 45s | 100.00% |
| 2 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `3262ece7a3a9` | `3262ece7a3a9` | `3262ece7a3a9` | 0.8130 | 0.5532 | 0.1692 | -0.0642 | 0.8130 | 0 | 1m 45s | 72.73% |
| 3 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `5129f68f30d3` | `5129f68f30d3` | `5129f68f30d3` | 0.8130 | 0.5532 | 0.1692 | -0.0642 | 0.8130 | 0 | 1m 45s | 90.91% |
| 4 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `5809567183b8` | `5809567183b8` | `5809567183b8` | 0.8130 | 0.5532 | 0.1692 | -0.0642 | 0.8130 | 0 | 1m 45s | 27.27% |
| 5 | [#512](https://github.com/dlstupka/hth/actions/runs/32089562359) | `a8c2142a0236` | `a8c2142a0236` | `a8c2142a0236` | 0.8130 | 0.5532 | 0.1692 | -0.0642 | 0.8130 | 0 | 1m 45s | 81.82% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — grabcut_contour

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `3a1623be3b6e` | `3a1623be3b6e` | 0.9568 | 0.9436 | -0.0132 | Regressed |
| 5 | `3a1623be3b6e` | `3a1623be3b6e` | 0.5532 | 0.8348 | +0.2816 | Improved |
| 6 | `3a1623be3b6e` | `3a1623be3b6e` | 0.6683 | 0.7198 | +0.0515 | Improved |
| 9 | `3a1623be3b6e` | `3a1623be3b6e` | 0.9422 | 0.9433 | +0.0010 | Improved |
| 10 | `3a1623be3b6e` | `3a1623be3b6e` | 0.9447 | 0.9447 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `3a1623be3b6e` | `3a1623be3b6e` | 1m 13s | 18.18% |

Total winner changes: **1**.
Search completed in **1m 47s** wall-clock time.

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
| 1 | `3a1623be3b6e` | `3a1623be3b6e` | 0.9436 | Regressed |

## Calibration Intelligence — grabcut_contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035207`
- Calibration schema: `1.1`
- Detector: `grabcut_contour`
- Detector configuration: `hth-pipeline/config/detectors/grabcut_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `3a1623be3b6e`
- Recommended parameter short name: `3a1623be3b6e`
- Best observed Avg IoU: `0.8772`
- Avg IoU Success: `0.8772`
- Worst Golden Set page (Min IoU): `0.7198`
- Page-to-page StdDev: `0.0893`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 46657 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 23d 6h 48m 45s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8772 |
| Minimum Avg IoU | 0.8130 |
| Avg IoU StdDev | 0.0185 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1m 13s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 46656 | 100.0% | 23d 6h 55m 56s | 1.0× |
| Exhaustive | 46656 | 100.0% | 23d 6h 55m 56s | 1.0× |
| Non-dormant | 768 | 1.6% | 9h 12m 2s | 60.8× |
| Low+ | 768 | 1.6% | 9h 12m 2s | 60.8× |
| Moderate+ | 48 | 0.1% | 34m 30s | 972.0× |
| Important+ | 48 | 0.1% | 34m 30s | 972.0× |
| Critical | 12 | 0.0% | 8m 38s | 3888.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `grabcut_close_kernel_fraction` | Critical | 1.0000 | 0.0642 | 50.0% | `0.03` (0.8772), `0.02` (0.8130) | current run |
| `grabcut_iterations` | Critical | 1.0000 | 0.0642 | 50.0% | `5` (0.8772), `3` (0.8130) | current run |
| `agreement_weight` | Critical | 0.2667 | 0.0214 | 33.3% | `0.35` (0.8344), `0.15` (0.8130), `0.25` (0.8130) | current run |
| `grabcut_weight` | Important | 0.1200 | 0.0128 | 50.0% | `0.55` (0.8259), `0.45` (0.8130) | current run |
| `require_contour` | Important | 0.1200 | 0.0128 | 50.0% | `true` (0.8259), `false` (0.8130) | current run |
| `contour_minimum_area_fraction` | Low | 0.0100 | 0.0064 | 50.0% | `0.08` (0.8194), `0.12` (0.8130) | current run |
| `contour_minimum_rectangularity` | Low | 0.0100 | 0.0064 | 50.0% | `0.45` (0.8194), `0.55` (0.8130) | current run |
| `grabcut_polygon_epsilon_fraction` | Low | 0.0100 | 0.0064 | 50.0% | `0.01` (0.8194), `0.018` (0.8130) | current run |
| `minimum_agreement_iou` | Low | 0.0100 | 0.0064 | 50.0% | `0.05` (0.8194), `0.15` (0.8130) | current run |
| `contour_epsilon_max_fraction` | Low | 0.0091 | 0.0000 | 0.0% | `0.04` (0.8130) | current run |
| `contour_weight` | Low | 0.0091 | 0.0000 | 0.0% | `0.2` (0.8130) | current run |
| `grabcut_close_iterations` | Low | 0.0091 | 0.0000 | 0.0% | `1` (0.8130) | current run |
| `grabcut_erosion_iterations` | Low | 0.0091 | 0.0000 | 0.0% | `1` (0.8130) | current run |
| `grabcut_minimum_bbox_area_fraction` | Low | 0.0091 | 0.0000 | 0.0% | `0.1` (0.8130) | current run |
| `grabcut_border_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.02` (0.8189) | current run |
| `grabcut_erosion_kernel_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8189) | current run |
| `grabcut_minimum_contour_area_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8189) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `agreement_weight` × `grabcut_weight` | 1.0000 | 0.7333 | 11 |
| `grabcut_weight` × `require_contour` | 0.4500 | 0.3300 | 11 |
| `agreement_weight` × `require_contour` | 0.4500 | 0.1833 | 11 |
| `grabcut_weight` × `contour_minimum_area_fraction` | 0.1750 | 0.0550 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9556 | 0.9436 | 0.9568 | 0.0038 | 100.0% |
| 5 | 0.5788 | 0.5532 | 0.8348 | 0.0810 | 100.0% |
| 6 | 0.6730 | 0.6683 | 0.7198 | 0.0148 | 100.0% |
| 9 | 0.9423 | 0.9422 | 0.9433 | 0.0003 | 100.0% |
| 10 | 0.9447 | 0.9447 | 0.9447 | 0.0000 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="gradient-boundary-voting-gradientvote-2"></a>
<details>
<summary><strong>Gradient Boundary Voting (`gradient_vote`)</strong></summary>

**Status:** complete

## Run Information — gradient_vote

### Build Provenance

- Run ID: `run-20260820-035655`
- Detector: `gradient_vote`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:55.944529+00:00`
- Finished: `2026-08-20T03:56:57.107199+00:00`
- Wall-clock elapsed: `1.2s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `22`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `50.00%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — gradient_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `e7c5bdbd0324` | `cf581d27715b` | `cf581d27715b` | `cf581d27715b` | 0.9622 | 0.9384 | 0.0160 | 0.9622 | 0 | 108 ms |
| Baseline | `HTH-0001` | `e7c5bdbd0324` | `1029318d5974` | `1029318d5974` | `baseline` | 0.9467 | 0.8611 | 0.0442 | 0.9467 | 0 | 114 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `cf581d27715b` |
| Parameter Set ID (legacy alias) | `cf581d27715b` |
| Absolute parameter SHA-256 | `3ba8789e5680c6aa07e7a378865223f606a00dd4323b7851c205748410b6f422` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `ccc52c4807b420ee814b0f627641df6fa92e721b9408bb146749a413ca4c5f29` |
| Grid ordinal | `18` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 2 |
| Total metric improvements | 4 |
| Parameter sets with improvements | 2 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `1029318d5974` | `1029318d5974` | `baseline` | 0.9467 | 0.8611 | 0.0442 | -0.0155 | 0.9467 | 0 | reference | reference |
| Best** | — | `cf581d27715b` | `cf581d27715b` | `cf581d27715b` | 0.9622 | 0.9384 | 0.0160 | +0.0000 | 0.9622 | 0 | reference | reference |
| 1 | — | `30474c8453fd` | `30474c8453fd` | `30474c8453fd` | 0.0000 | 0.0000 | 0.0000 | -0.9622 | 0.0000 | 5 | 241 ms | 45.45% |
| 2 | — | `899d902a4617` | `899d902a4617` | `899d902a4617` | 0.0000 | 0.0000 | 0.0000 | -0.9622 | 0.0000 | 5 | 241 ms | 36.36% |
| 3 | — | `77872953d74c` | `77872953d74c` | `77872953d74c` | 0.0000 | 0.0000 | 0.0000 | -0.9622 | 0.0000 | 5 | 241 ms | 27.27% |
| 4 | — | `4969d77896b6` | `4969d77896b6` | `4969d77896b6` | 0.0000 | 0.0000 | 0.0000 | -0.9622 | 0.0000 | 5 | 245 ms | 54.55% |
| 5 | — | `578ed95f660c` | `578ed95f660c` | `578ed95f660c` | 0.0000 | 0.0000 | 0.0000 | -0.9622 | 0.0000 | 5 | 245 ms | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — gradient_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `cf581d27715b` | `cf581d27715b` | 0.9613 | 0.9613 | +0.0000 | Unchanged |
| 5 | `cf581d27715b` | `cf581d27715b` | 0.8611 | 0.9384 | +0.0773 | Improved |
| 6 | `cf581d27715b` | `cf581d27715b` | 0.9889 | 0.9889 | +0.0000 | Unchanged |
| 9 | `cf581d27715b` | `cf581d27715b` | 0.9612 | 0.9612 | +0.0000 | Unchanged |
| 10 | `cf581d27715b` | `cf581d27715b` | 0.9611 | 0.9611 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `cf581d27715b` | `cf581d27715b` | 235 ms | 18.18% |

Total winner changes: **1**.
Search completed in **1.2s** wall-clock time.

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

- Calibration run ID: `run-20260820-035655`
- Calibration schema: `1.1`
- Detector: `gradient_vote`
- Detector configuration: `hth-pipeline/config/detectors/gradient_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `cf581d27715b`
- Recommended parameter short name: `cf581d27715b`
- Best observed Avg IoU: `0.9622`
- Avg IoU Success: `0.9622`
- Worst Golden Set page (Min IoU): `0.9384`
- Page-to-page StdDev: `0.0160`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 9 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 22 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 50.0% |
| Est. serial runtime for full parameter set evaluation* | 1.2s |
| Fully successful parameter sets | 2 (18.2%) |
| Best Avg IoU | 0.9622 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.3681 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 235 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 21 | 100.0% | 2.3s | 1.0× |
| Exhaustive | 21 | 100.0% | 2.3s | 1.0× |
| Non-dormant | 11 | 52.4% | 1.2s | 1.9× |
| Low+ | 11 | 52.4% | 1.2s | 1.9× |
| Moderate+ | 11 | 52.4% | 1.2s | 1.9× |
| Important+ | 11 | 52.4% | 1.2s | 1.9× |
| Critical | 11 | 52.4% | 1.2s | 1.9× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `border_search_fraction` | Critical | 1.0000 | 0.9622 | 9.1% | `0.14` (0.9622), `0.15` (0.9467), `0.05` (0.0000) | current run |
| `area_weight` | Critical | 0.4010 | 0.0000 | 0.0% | `0.25` (0.9467) | current run |
| `central_band_fraction` | Critical | 0.4010 | 0.0000 | 0.0% | `1` (0.9467) | current run |
| `gaussian_sigma` | Critical | 0.4010 | 0.0000 | 0.0% | `1.2` (0.9467) | current run |
| `gradient_percentile` | Critical | 0.4010 | 0.0000 | 0.0% | `70` (0.9467) | current run |
| `minimum_area_fraction` | Critical | 0.4010 | 0.0000 | 0.0% | `0.2` (0.9467) | current run |
| `minimum_span_fraction` | Critical | 0.4010 | 0.0000 | 0.0% | `0.15` (0.9467) | current run |
| `minimum_vote_support` | Critical | 0.4010 | 0.0000 | 0.0% | `0.08` (0.9467) | current run |
| `rectangularity_weight` | Critical | 0.4010 | 0.0000 | 0.0% | `0.2` (0.9467) | current run |
| `support_weight` | Critical | 0.4010 | 0.0000 | 0.0% | `0.45` (0.9467) | current run |
| `vote_smooth_fraction` | Critical | 0.4010 | 0.0000 | 0.0% | `0.012` (0.9467) | current run |

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
| 1 | 0.1748 | 0.0000 | 0.9613 | 0.3708 | 18.2% |
| 5 | 0.1636 | 0.0000 | 0.9384 | 0.3474 | 18.2% |
| 6 | 0.1798 | 0.0000 | 0.9889 | 0.3814 | 18.2% |
| 9 | 0.1748 | 0.0000 | 0.9612 | 0.3707 | 18.2% |
| 10 | 0.1747 | 0.0000 | 0.9611 | 0.3707 | 18.2% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="hough-line-borders-hough-2"></a>
<details>
<summary><strong>Hough Line Borders (`hough`)</strong></summary>

**Status:** complete

## Run Information — hough

### Build Provenance

- Run ID: `run-20260820-035404`
- Detector: `hough`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:54:04.668900+00:00`
- Finished: `2026-08-20T03:54:09.979521+00:00`
- Wall-clock elapsed: `5.3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2188`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.50%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — hough

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `8a2ee1ed3a5c` | `c2c117479e3f` | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | 0.7563 | 1 | 1.5s |
| Baseline | `HTH-0001` | `8a2ee1ed3a5c` | `7078053f309d` | `7078053f309d` | `baseline` | 0.4784 | 0.0000 | 0.2851 | 0.5981 | 1 | 1.5s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `c2c117479e3f` |
| Parameter Set ID (legacy alias) | `c2c117479e3f` |
| Absolute parameter SHA-256 | `f86c289191351ba1fcc9fc65c7e060df7dc6af0ba88cd84df5973bae725511d7` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `22cf3b17e40a484392adc3900ceb342c32e6d40fb4797151344f5e15138148d9` |
| Grid ordinal | `1730` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 2 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 3 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `7078053f309d` | `7078053f309d` | `baseline` | 0.4784 | 0.0000 | 0.2851 | -0.1266 | 0.5981 | 1 | reference | reference |
| Best** | — | `c2c117479e3f` | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | +0.0000 | 0.7563 | 1 | reference | reference |
| 1 | — | `d2ef0aec6694` | `d2ef0aec6694` | `d2ef0aec6694` | 0.5661 | 0.0000 | 0.3407 | -0.0389 | 0.7076 | 1 | 4.7s | 81.82% |
| 2 | — | `217ec1728985` | `217ec1728985` | `217ec1728985` | 0.5556 | 0.0000 | 0.3391 | -0.0494 | 0.6946 | 1 | 4.5s | 27.27% |
| 3 | — | `90e4276c2a1d` | `90e4276c2a1d` | `90e4276c2a1d` | 0.5495 | 0.0000 | 0.3375 | -0.0555 | 0.6869 | 1 | 4.7s | 100.00% |
| 4 | — | `cd10502d9095` | `cd10502d9095` | `cd10502d9095` | 0.5030 | 0.0000 | 0.3046 | -0.1020 | 0.6288 | 1 | 4.6s | 72.73% |
| 5 | — | `96052fb049b9` | `96052fb049b9` | `96052fb049b9` | 0.4882 | 0.0000 | 0.3000 | -0.1169 | 0.6102 | 1 | 4.5s | 45.45% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — hough

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `c2c117479e3f` | `c2c117479e3f` | 0.6261 | 0.8347 | +0.2086 | Improved |
| 5 | `c2c117479e3f` | `c2c117479e3f` | 0.3071 | 0.5446 | +0.2375 | Improved |
| 6 | `c2c117479e3f` | `c2c117479e3f` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `c2c117479e3f` | `c2c117479e3f` | 0.7370 | 0.8188 | +0.0819 | Improved |
| 10 | `c2c117479e3f` | `c2c117479e3f` | 0.7221 | 0.8270 | +0.1049 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `c2c117479e3f` | `c2c117479e3f` | 3s | 18.18% |

Total winner changes: **1**.
Search completed in **5.3s** wall-clock time.

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
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 6 | `c2c117479e3f` | `c2c117479e3f` | 0.0000 | No polygon found |

## Calibration Intelligence — hough

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035404`
- Calibration schema: `1.1`
- Detector: `hough`
- Detector configuration: `hth-pipeline/config/detectors/hough.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `c2c117479e3f`
- Recommended parameter short name: `c2c117479e3f`
- Best observed Avg IoU: `0.6050`
- Avg IoU Success: `0.7563`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3217`
- Calibration evidence: `Low`
- Dormant parameters: `axis_angle_tolerance_degrees, minimum_length_fraction, minimum_bbox_area_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 3 of 8 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2188 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 53m 30s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.6050 |
| Minimum Avg IoU | 0.3084 |
| Avg IoU StdDev | 0.1011 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 53m 44s | 1.0× |
| Exhaustive | 2187 | 100.0% | 53m 44s | 1.0× |
| Non-dormant | 108 | 4.9% | 2m 39s | 20.2× |
| Low+ | 108 | 4.9% | 2m 39s | 20.2× |
| Moderate+ | 108 | 4.9% | 2m 39s | 20.2× |
| Important+ | 36 | 1.6% | 53.1s | 60.8× |
| Critical | 9 | 0.4% | 13.3s | 243.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `outer_percentile` | Critical | 0.9781 | 0.2513 | 33.3% | `5` (0.5691), `10` (0.4874), `20` (0.3177) | current run |
| `canny_low_threshold` | Critical | 0.1805 | 0.1500 | 33.3% | `65` (0.6050), `40` (0.4784), `25` (0.4551) | current run |
| `hough_threshold_fraction` | Important | 0.1093 | 0.0867 | 50.0% | `0.055` (0.5417), `0.035` (0.4551) | current run |
| `maximum_gap_fraction` | Important | 0.1093 | 0.0867 | 50.0% | `0.055` (0.5417), `0.025` (0.4551) | current run |
| `bbox_padding_fraction` | Moderate | 0.0502 | 0.0476 | 33.3% | `0.015` (0.5008), `0` (0.4541), `0.005` (0.4532) | current run |
| `axis_angle_tolerance_degrees` | Dormant | 0.0006 | 0.0084 | 50.0% | `22` (0.4784), `12` (0.4701) | current run |
| `minimum_length_fraction` | Dormant | 0.0006 | 0.0084 | 50.0% | `0.2` (0.4784), `0.12` (0.4701) | current run |
| `minimum_bbox_area_fraction` | Dormant | 0.0005 | 0.0000 | 0.0% | `0.1` (0.4784) | current run |

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

`axis_angle_tolerance_degrees`, `minimum_length_fraction`, `minimum_bbox_area_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `hough_threshold_fraction` × `bbox_padding_fraction` | 0.1860 | 0.0767 | 11 |
| `maximum_gap_fraction` × `bbox_padding_fraction` | 0.1860 | 0.0767 | 11 |
| `hough_threshold_fraction` × `axis_angle_tolerance_degrees` | 0.1805 | 0.0712 | 11 |
| `maximum_gap_fraction` × `axis_angle_tolerance_degrees` | 0.1805 | 0.0712 | 11 |
| `outer_percentile` × `canny_low_threshold` | 0.9944 | 0.0163 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.6759 | 0.4658 | 0.8453 | 0.1390 | 100.0% |
| 5 | 0.2418 | 0.0000 | 0.5446 | 0.1642 | 72.7% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.7038 | 0.4958 | 0.8188 | 0.1219 | 100.0% |
| 10 | 0.7326 | 0.5805 | 0.8305 | 0.0927 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="joint-rectangle-voting-jointrectanglevote-2"></a>
<details>
<summary><strong>Joint Rectangle Voting (`joint_rectangle_vote`)</strong></summary>

**Status:** complete

## Run Information — joint_rectangle_vote

### Build Provenance

- Run ID: `run-20260820-035540`
- Detector: `joint_rectangle_vote`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:55:40.914069+00:00`
- Finished: `2026-08-20T03:55:49.618934+00:00`
- Wall-clock elapsed: `8.7s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.50%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — joint_rectangle_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `7f2c9afba612` | `5c9509e05f14` | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | 0.9899 | 4 | 444 ms |
| Baseline | `HTH-0001` | `7f2c9afba612` | `697c22dd549f` | `697c22dd549f` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 653 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `5c9509e05f14` |
| Parameter Set ID (legacy alias) | `5c9509e05f14` |
| Absolute parameter SHA-256 | `c37b1b650f9c5544f4e560d30d4eb4a70b1afc907786010dd7a9a3d0a001123f` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `fa4da63ad8842e4c2753300cf49f64f852d1783ea39dcd6c941b844251d294ce` |
| Grid ordinal | `2118` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 1 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `697c22dd549f` | `697c22dd549f` | `baseline` | 0.0000 | 0.0000 | 0.0000 | -0.1980 | 0.0000 | 5 | reference | reference |
| Best** | — | `5c9509e05f14` | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | reference | reference |
| 1 | — | `b699602175ff` | `b699602175ff` | `b699602175ff` | 0.0000 | 0.0000 | 0.0000 | -0.1980 | 0.0000 | 5 | 2.4s | 27.27% |
| 2 | — | `832829bf5599` | `832829bf5599` | `832829bf5599` | 0.0000 | 0.0000 | 0.0000 | -0.1980 | 0.0000 | 5 | 2.5s | 36.36% |
| 3 | — | `ae65e4295acc` | `ae65e4295acc` | `ae65e4295acc` | 0.0000 | 0.0000 | 0.0000 | -0.1980 | 0.0000 | 5 | 3.8s | 45.45% |
| 4 | — | `bd9ecd87d248` | `bd9ecd87d248` | `bd9ecd87d248` | 0.0000 | 0.0000 | 0.0000 | -0.1980 | 0.0000 | 5 | 4s | 54.55% |
| 5 | — | `f926b52af6a2` | `f926b52af6a2` | `f926b52af6a2` | 0.0000 | 0.0000 | 0.0000 | -0.1980 | 0.0000 | 5 | 5.4s | 72.73% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — joint_rectangle_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | 0.9899 | +0.9899 | Recovered |
| 9 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `5c9509e05f14` | `5c9509e05f14` | 1.1s | 18.18% |

Total winner changes: **1**.
Search completed in **8.7s** wall-clock time.

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
| 1 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | No polygon found |
| 5 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | No polygon found |
| 9 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | No polygon found |
| 10 | `5c9509e05f14` | `5c9509e05f14` | 0.0000 | No polygon found |

## Calibration Intelligence — joint_rectangle_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035540`
- Calibration schema: `1.1`
- Detector: `joint_rectangle_vote`
- Detector configuration: `hth-pipeline/config/detectors/joint_rectangle_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `5c9509e05f14`
- Recommended parameter short name: `5c9509e05f14`
- Best observed Avg IoU: `0.1980`
- Avg IoU Success: `0.9899`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3960`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 16m 6s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.1980 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0569 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.1s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 16m 10s | 1.0× |
| Exhaustive | 2187 | 100.0% | 16m 10s | 1.0× |
| Non-dormant | 972 | 44.4% | 7m 11s | 2.2× |
| Low+ | 972 | 44.4% | 7m 11s | 2.2× |
| Moderate+ | 486 | 22.2% | 3m 36s | 4.5× |
| Important+ | 486 | 22.2% | 3m 36s | 4.5× |
| Critical | 54 | 2.5% | 24s | 40.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `canny_high` | Critical | 1.0000 | 0.1980 | 33.3% | `220` (0.1980), `100` (0.0000), `150` (0.0000) | current run |
| `canny_low` | Critical | 1.0000 | 0.1980 | 33.3% | `80` (0.1980), `30` (0.0000), `50` (0.0000) | current run |
| `hough_threshold` | Critical | 1.0000 | 0.1980 | 33.3% | `120` (0.1980), `50` (0.0000), `80` (0.0000) | current run |
| `minimum_side_support` | Critical | 0.4500 | 0.0990 | 50.0% | `0.18` (0.0990), `0.1` (0.0000) | current run |
| `bbox_padding_fraction` | Important | 0.1200 | 0.0396 | 33.3% | `0` (0.0396), `0.008` (0.0000), `0.016` (0.0000) | current run |
| `minimum_area_fraction` | Important | 0.1200 | 0.0396 | 33.3% | `0.16` (0.0396), `0.1` (0.0000), `0.24` (0.0000) | current run |
| `axis_tolerance_degrees` | Low | 0.0100 | 0.0198 | 50.0% | `6` (0.0198), `12` (0.0000) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `bbox_padding_fraction` × `minimum_area_fraction` | 0.2667 | 0.1467 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0900 | 0.0000 | 0.9899 | 0.2846 | 9.1% |
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

- Run ID: `run-20260820-035207`
- Detector: `kraken_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:52:07.217459+00:00`
- Finished: `2026-08-20T03:55:22.352914+00:00`
- Wall-clock elapsed: `3m 15s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `10000`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.11%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — kraken_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `9f629f3caee1` | `c4845fd6c6b6` | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8396 | 0.5596 | 0.1531 | 0.8396 | 0 | 45 ms |
| Baseline | `HTH-0001` | `9f629f3caee1` | `d75b76f301e6` | `d75b76f301e6` | `baseline` | 0.8068 | 0.6201 | 0.0947 | 0.8068 | 0 | 45 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `c4845fd6c6b6` |
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
| [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | 2026-08-17 | `c4845fd6c6b6` | `c4845fd6c6b6` | authoritative |
| [#499](https://github.com/dlstupka/hth/actions/runs/32062830685) | 2026-08-17 | `c4845fd6c6b6` | `c4845fd6c6b6` | authoritative |
| [#494](https://github.com/dlstupka/hth/actions/runs/32061781495) | 2026-08-17 | `c4845fd6c6b6` | `c4845fd6c6b6` | authoritative |
| [#492](https://github.com/dlstupka/hth/actions/runs/32060600276) | 2026-08-17 | `c4845fd6c6b6` | `c4845fd6c6b6` | authoritative |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 1 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `d75b76f301e6` | `d75b76f301e6` | `baseline` | 0.8068 | 0.6201 | 0.0947 | -0.0328 | 0.8068 | 0 | reference | reference |
| Best** | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `c4845fd6c6b6` | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8396 | 0.5596 | 0.1531 | +0.0000 | 0.8396 | 0 | reference | reference |
| 1 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `8e7329ed85d1` | `8e7329ed85d1` | `8e7329ed85d1` | 0.8336 | 0.5226 | 0.1752 | -0.0060 | 0.8336 | 0 | 126 ms | 27.27% |
| 2 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `172a631f5c19` | `172a631f5c19` | `172a631f5c19` | 0.8336 | 0.5226 | 0.1752 | -0.0060 | 0.8336 | 0 | 131 ms | 72.73% |
| 3 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `8161375b5ba2` | `8161375b5ba2` | `8161375b5ba2` | 0.8336 | 0.5226 | 0.1752 | -0.0060 | 0.8336 | 0 | 127 ms | 36.36% |
| 4 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `bd78177097cd` | `bd78177097cd` | `bd78177097cd` | 0.8336 | 0.5226 | 0.1752 | -0.0060 | 0.8336 | 0 | 132 ms | 81.82% |
| 5 | [#503](https://github.com/dlstupka/hth/actions/runs/32066651136) | `4c073e72c58a` | `4c073e72c58a` | `4c073e72c58a` | 0.8336 | 0.5226 | 0.1752 | -0.0060 | 0.8336 | 0 | 128 ms | 45.45% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — kraken_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8769 | 0.9694 | +0.0925 | Improved |
| 5 | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.6201 | 0.5596 | -0.0606 | Regressed |
| 6 | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8310 | 0.7918 | -0.0392 | Regressed |
| 9 | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8437 | 0.9356 | +0.0919 | Improved |
| 10 | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.8625 | 0.9416 | +0.0791 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `c4845fd6c6b6` | `c4845fd6c6b6` | 92 ms | 18.18% |

Total winner changes: **1**.
Search completed in **3m 15s** wall-clock time.

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
| 5 | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.5596 | Regressed |
| 6 | `c4845fd6c6b6` | `c4845fd6c6b6` | 0.7918 | Regressed |

## Calibration Intelligence — kraken_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035207`
- Calibration schema: `1.1`
- Detector: `kraken_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/kraken_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `c4845fd6c6b6`
- Recommended parameter short name: `c4845fd6c6b6`
- Best observed Avg IoU: `0.8396`
- Avg IoU Success: `0.8396`
- Worst Golden Set page (Min IoU): `0.5596`
- Page-to-page StdDev: `0.1531`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 10000 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 7m 26s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8396 |
| Minimum Avg IoU | 0.8068 |
| Avg IoU StdDev | 0.0081 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 92 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 10000 | 100.0% | 7m 26s | 1.0× |
| Exhaustive | 10000 | 100.0% | 7m 26s | 1.0× |
| Non-dormant | 240 | 2.4% | 10.7s | 41.7× |
| Low+ | 240 | 2.4% | 10.7s | 41.7× |
| Moderate+ | 240 | 2.4% | 10.7s | 41.7× |
| Important+ | 120 | 1.2% | 5.4s | 83.3× |
| Critical | 120 | 1.2% | 5.4s | 83.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `dilation_fraction` | Critical | 1.0000 | 0.0328 | 33.3% | `0.02` (0.8396), `0` (0.8336), `0.01` (0.8068) | current run |
| `close_kernel_fraction` | Critical | 0.9552 | 0.0274 | 50.0% | `0` (0.8342), `0.006` (0.8068) | current run |
| `include_lines` | Critical | 0.9552 | 0.0274 | 50.0% | `0` (0.8342), `1` (0.8068) | current run |
| `page_padding_fraction` | Critical | 0.9552 | 0.0274 | 50.0% | `0` (0.8342), `0.05` (0.8068) | current run |
| `minimum_page_area_fraction` | Critical | 0.3048 | 0.0119 | 20.0% | `0.25` (0.8366), `0.08` (0.8336), `0.16` (0.8336) | current run |
| `fill_holes` | Moderate | 0.0461 | 0.0035 | 50.0% | `0` (0.8336), `1` (0.8302) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_page_area_fraction` × `fill_holes` | 0.4972 | 0.1925 | 11 |
| `close_kernel_fraction` × `minimum_page_area_fraction` | 0.9751 | 0.0199 | 11 |
| `include_lines` × `minimum_page_area_fraction` | 0.9751 | 0.0199 | 11 |
| `page_padding_fraction` × `minimum_page_area_fraction` | 0.9751 | 0.0199 | 11 |
| `close_kernel_fraction` × `fill_holes` | 0.9602 | 0.0050 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9674 | 0.8769 | 0.9772 | 0.0287 | 100.0% |
| 5 | 0.5348 | 0.5226 | 0.6201 | 0.0290 | 100.0% |
| 6 | 0.7661 | 0.7560 | 0.8310 | 0.0229 | 100.0% |
| 9 | 0.9411 | 0.8437 | 0.9525 | 0.0312 | 100.0% |
| 10 | 0.9494 | 0.8625 | 0.9599 | 0.0280 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="learned-page-mask-detector-learnedpagemask-2"></a>
<details>
<summary><strong>Learned Page-Mask Detector (`learned_page_mask`)</strong></summary>

**Status:** complete

## Run Information — learned_page_mask

### Build Provenance

- Run ID: `run-20260820-035541`
- Detector: `learned_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:55:41.556113+00:00`
- Finished: `2026-08-20T03:57:02.762359+00:00`
- Wall-clock elapsed: `1m 21s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50000`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — learned_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `11caf9fec70e` | `275078578cee` | `275078578cee` | `275078578cee` | 0.8868 | 0.8122 | 0.0470 | 0.8868 | 0 | 9s |
| Baseline | `HTH-0001` | `11caf9fec70e` | `04e0ef2b5787` | `04e0ef2b5787` | `baseline` | 0.8374 | 0.7029 | 0.0740 | 0.8374 | 0 | 8.4s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `275078578cee` |
| Parameter Set ID (legacy alias) | `275078578cee` |
| Absolute parameter SHA-256 | `e85c6e16e9fdae0f94de3b4fe20088770a90a63f4b0a635a96152cb6c9d6d031` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `1e64e5c18a2760deef433e0a47eedae63e8cc4067de6714b5fabfa655941872e` |
| Grid ordinal | `22260` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 3 |
| Total metric improvements | 5 |
| Parameter sets with improvements | 3 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `04e0ef2b5787` | `04e0ef2b5787` | `baseline` | 0.8374 | 0.7029 | 0.0740 | -0.0494 | 0.8374 | 0 | reference | reference |
| Best** | — | `275078578cee` | `275078578cee` | `275078578cee` | 0.8868 | 0.8122 | 0.0470 | +0.0000 | 0.8868 | 0 | reference | reference |
| 1 | — | `5224fd6d0bf0` | `5224fd6d0bf0` | `5224fd6d0bf0` | 0.8792 | 0.7929 | 0.0511 | -0.0076 | 0.8792 | 0 | 26.8s | 27.27% |
| 2 | — | `df8cf13093da` | `df8cf13093da` | `df8cf13093da` | 0.8792 | 0.7951 | 0.0502 | -0.0077 | 0.8792 | 0 | 36.9s | 36.36% |
| 3 | — | `7ced6c1838d8` | `7ced6c1838d8` | `7ced6c1838d8` | 0.8791 | 0.7972 | 0.0493 | -0.0077 | 0.8791 | 0 | 48.4s | 54.55% |
| 4 | — | `ca8b4fb456e1` | `ca8b4fb456e1` | `ca8b4fb456e1` | 0.8788 | 0.7993 | 0.0482 | -0.0080 | 0.8788 | 0 | 58.3s | 63.64% |
| 5 | — | `75d99c2f888e` | `75d99c2f888e` | `75d99c2f888e` | 0.8785 | 0.8015 | 0.0471 | -0.0083 | 0.8785 | 0 | 59.9s | 72.73% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — learned_page_mask

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `275078578cee` | `275078578cee` | 0.8884 | 0.9135 | +0.0251 | Improved |
| 5 | `275078578cee` | `275078578cee` | 0.9183 | 0.9195 | +0.0011 | Improved |
| 6 | `275078578cee` | `275078578cee` | 0.7029 | 0.8122 | +0.1092 | Improved |
| 9 | `275078578cee` | `275078578cee` | 0.8479 | 0.8521 | +0.0042 | Improved |
| 10 | `275078578cee` | `275078578cee` | 0.8297 | 0.9369 | +0.1072 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `275078578cee` | `275078578cee` | 17.4s | 18.18% |

Total winner changes: **1**.
Search completed in **1m 21s** wall-clock time.

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

## Calibration Intelligence — learned_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035541`
- Calibration schema: `1.1`
- Detector: `learned_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/learned_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `275078578cee`
- Recommended parameter short name: `275078578cee`
- Best observed Avg IoU: `0.8868`
- Avg IoU Success: `0.8868`
- Worst Golden Set page (Min IoU): `0.8122`
- Page-to-page StdDev: `0.0470`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50000 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 5d 4h 51m 44s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8868 |
| Minimum Avg IoU | 0.8374 |
| Avg IoU StdDev | 0.0123 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 17.4s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50000 | 100.0% | 5d 4h 53m 23s | 1.0× |
| Exhaustive | 50000 | 100.0% | 5d 4h 53m 23s | 1.0× |
| Non-dormant | 240 | 0.5% | 35m 58s | 208.3× |
| Low+ | 240 | 0.5% | 35m 58s | 208.3× |
| Moderate+ | 240 | 0.5% | 35m 58s | 208.3× |
| Important+ | 240 | 0.5% | 35m 58s | 208.3× |
| Critical | 120 | 0.2% | 17m 59s | 416.7× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `mask_threshold` | Critical | 0.9701 | 0.0494 | 33.3% | `0.226` (0.8868), `0.204` (0.8778), `0.5` (0.8374) | current run |
| `close_kernel_fraction` | Critical | 0.9259 | 0.0412 | 50.0% | `0` (0.8787), `0.006` (0.8374) | current run |
| `minimum_mask_area_fraction` | Critical | 0.9259 | 0.0412 | 50.0% | `0.04` (0.8787), `0.15` (0.8374) | current run |
| `bbox_padding_fraction` | Critical | 0.6568 | 0.0324 | 10.0% | `0.029` (0.8868), `0.02` (0.8792), `0.021` (0.8792) | current run |
| `polygon_epsilon_fraction` | Important | 0.0933 | 0.0131 | 50.0% | `0.0185` (0.8868), `0.012` (0.8737) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `close_kernel_fraction` × `bbox_padding_fraction` | 1.0000 | 0.0741 | 11 |
| `minimum_mask_area_fraction` × `bbox_padding_fraction` | 1.0000 | 0.0741 | 11 |
| `close_kernel_fraction` × `polygon_epsilon_fraction` | 0.9701 | 0.0442 | 11 |
| `minimum_mask_area_fraction` × `polygon_epsilon_fraction` | 0.9701 | 0.0442 | 11 |
| `mask_threshold` × `bbox_padding_fraction` | 1.0000 | 0.0299 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8985 | 0.8835 | 0.9471 | 0.0173 | 100.0% |
| 5 | 0.9199 | 0.9151 | 0.9235 | 0.0026 | 100.0% |
| 6 | 0.7857 | 0.7029 | 0.8122 | 0.0347 | 100.0% |
| 9 | 0.8508 | 0.8475 | 0.8521 | 0.0015 | 100.0% |
| 10 | 0.9197 | 0.8297 | 0.9369 | 0.0289 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="line-segment-detector-lsd-2"></a>
<details>
<summary><strong>Line Segment Detector (`lsd`)</strong></summary>

**Status:** complete

## Run Information — lsd

### Build Provenance

- Run ID: `run-20260820-035626`
- Detector: `lsd`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:26.508047+00:00`
- Finished: `2026-08-20T03:56:33.945037+00:00`
- Wall-clock elapsed: `7.4s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.50%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
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
| Winner | `HTH-0001` | `1c8144751349` | `7546c5067527` | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | 0.9222 | 1 | 1.6s |
| Baseline | `HTH-0001` | `1c8144751349` | `b2df04f4e947` | `b2df04f4e947` | `baseline` | 0.5414 | 0.0000 | 0.4436 | 0.9023 | 2 | 1.3s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `7546c5067527` |
| Parameter Set ID (legacy alias) | `7546c5067527` |
| Absolute parameter SHA-256 | `8009375e49ea788fff5764f7537d03ed94e4d5e054b5ac363c804eaf4d7c802c` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `6e2c51ae3089ad7b2e3cbc67591e7965e2c3125df856be25b3ad306412915b46` |
| Grid ordinal | `406` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 4 |
| Total metric improvements | 5 |
| Parameter sets with improvements | 4 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `b2df04f4e947` | `b2df04f4e947` | `baseline` | 0.5414 | 0.0000 | 0.4436 | -0.1964 | 0.9023 | 2 | reference | reference |
| Best** | — | `7546c5067527` | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | reference | reference |
| 1 | — | `7b8b1aaee481` | `7b8b1aaee481` | `7b8b1aaee481` | 0.7368 | 0.0000 | 0.3714 | -0.0010 | 0.9210 | 1 | 3.6s | 27.27% |
| 2 | — | `19a4857c76d8` | `19a4857c76d8` | `19a4857c76d8` | 0.7368 | 0.0000 | 0.3714 | -0.0010 | 0.9210 | 1 | 4.5s | 54.55% |
| 3 | — | `1b2cebd68deb` | `1b2cebd68deb` | `1b2cebd68deb` | 0.7368 | 0.0000 | 0.3714 | -0.0010 | 0.9210 | 1 | 5.9s | 90.91% |
| 4 | — | `0bd9251e7f32` | `0bd9251e7f32` | `0bd9251e7f32` | 0.7340 | 0.0000 | 0.3695 | -0.0038 | 0.9175 | 1 | 3.7s | 36.36% |
| 5 | — | `2cf82997c714` | `2cf82997c714` | `2cf82997c714` | 0.7340 | 0.0000 | 0.3695 | -0.0038 | 0.9175 | 1 | 4.1s | 45.45% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — lsd

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `7546c5067527` | `7546c5067527` | 0.8955 | 0.9102 | +0.0147 | Improved |
| 5 | `7546c5067527` | `7546c5067527` | 0.0000 | 0.9850 | +0.9850 | Recovered |
| 6 | `7546c5067527` | `7546c5067527` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `7546c5067527` | `7546c5067527` | 0.8475 | 0.8400 | -0.0075 | Regressed |
| 10 | `7546c5067527` | `7546c5067527` | 0.9641 | 0.9537 | -0.0103 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `7546c5067527` | `7546c5067527` | 3s | 18.18% |

Total winner changes: **1**.
Search completed in **7.4s** wall-clock time.

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
| 6 | `7546c5067527` | `7546c5067527` | 0.0000 | No polygon found |
| 9 | `7546c5067527` | `7546c5067527` | 0.8400 | Regressed |
| 10 | `7546c5067527` | `7546c5067527` | 0.9537 | Regressed |

## Calibration Intelligence — lsd

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035626`
- Calibration schema: `1.1`
- Detector: `lsd`
- Detector configuration: `hth-pipeline/config/detectors/lsd.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `7546c5067527`
- Recommended parameter short name: `7546c5067527`
- Best observed Avg IoU: `0.7378`
- Avg IoU Success: `0.9222`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3721`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 59m 4s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7378 |
| Minimum Avg IoU | 0.5414 |
| Avg IoU StdDev | 0.0549 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (36.4%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 2187 | 100.0% | 59m 22s | 1.0× |
| Exhaustive | 2187 | 100.0% | 59m 22s | 1.0× |
| Non-dormant | 432 | 19.8% | 11m 44s | 5.1× |
| Low+ | 432 | 19.8% | 11m 44s | 5.1× |
| Moderate+ | 432 | 19.8% | 11m 44s | 5.1× |
| Important+ | 432 | 19.8% | 11m 44s | 5.1× |
| Critical | 432 | 19.8% | 11m 44s | 5.1× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_length_fraction` | Critical | 0.9801 | 0.1964 | 66.7% | `0.22` (0.7378), `0.08` (0.7294), `0.14` (0.5414) | current run |
| `axis_angle_tolerance_degrees` | Critical | 0.9782 | 0.1888 | 50.0% | `10` (0.7302), `18` (0.5414) | current run |
| `outer_percentile` | Critical | 0.9782 | 0.1888 | 50.0% | `5` (0.7302), `10` (0.5414) | current run |
| `refine_mode` | Critical | 0.9782 | 0.1888 | 50.0% | `none` (0.7302), `std` (0.5414) | current run |
| `scale` | Critical | 0.3984 | 0.0898 | 100.0% | `0.6` (0.7294), `0.8` (0.6396) | current run |
| `minimum_bbox_area_fraction` | Critical | 0.1786 | 0.0491 | 100.0% | `0.08` (0.7315), `0.15` (0.7294), `0.1` (0.6824) | current run |
| `bbox_padding_fraction` | Critical | 0.1606 | 0.0512 | 33.3% | `0.005` (0.7371), `0.015` (0.7174), `0` (0.6858) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `scale` × `minimum_bbox_area_fraction` | 0.9801 | 0.5817 | 11 |
| `axis_angle_tolerance_degrees` × `scale` | 0.9801 | 0.0019 | 11 |
| `outer_percentile` × `scale` | 0.9801 | 0.0019 | 11 |
| `refine_mode` × `scale` | 0.9801 | 0.0019 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8984 | 0.8828 | 0.9102 | 0.0107 | 100.0% |
| 5 | 0.8847 | 0.0000 | 0.9850 | 0.2798 | 90.9% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8344 | 0.8091 | 0.8475 | 0.0157 | 100.0% |
| 10 | 0.9479 | 0.9209 | 0.9641 | 0.0168 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="fusion-gen1-msre-bfq-spbv-page-background-msrebfqspbvpbg-2"></a>
<details>
<summary><strong>Fusion Gen1 — MSRE + BFQ + SPBV + Page Background (`msre_bfq_spbv_pbg`)</strong></summary>

**Status:** complete

## Run Information — msre_bfq_spbv_pbg

### Build Provenance

- Run ID: `run-20260820-035433`
- Detector: `msre_bfq_spbv_pbg`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:54:33.244111+00:00`
- Finished: `2026-08-20T03:55:26.918163+00:00`
- Wall-clock elapsed: `53.7s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50176`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — msre_bfq_spbv_pbg

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `c89a30906bb8` | `7b7dbac43ea6` | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9747 | 0.9638 | 0.0101 | 0.9747 | 0 | 5s |
| Baseline | `HTH-0001` | `c89a30906bb8` | `54d4e56ee0fc` | `54d4e56ee0fc` | `baseline` | 0.9738 | 0.9638 | 0.0103 | 0.9738 | 0 | 5.3s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `7b7dbac43ea6` |
| Parameter Set ID (legacy alias) | `7b7dbac43ea6` |
| Absolute parameter SHA-256 | `750f2f573416135035c2f130f3597cc4ce00c3d8340f7808ba917ab2bd0f5546` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `7a959f88cd10fd3f5119712d24841950c3e9864844e4fb4f77fd497e59c042c0` |
| Grid ordinal | `48070` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 1 |
| Total metric improvements | 2 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `54d4e56ee0fc` | `54d4e56ee0fc` | `baseline` | 0.9738 | 0.9638 | 0.0103 | -0.0009 | 0.9738 | 0 | reference | reference |
| Best** | — | `7b7dbac43ea6` | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9747 | 0.9638 | 0.0101 | +0.0000 | 0.9747 | 0 | reference | reference |
| 1 | — | `3f64fab7e641` | `3f64fab7e641` | `3f64fab7e641` | 0.9703 | 0.9539 | 0.0137 | -0.0045 | 0.9703 | 0 | 18.2s | 27.27% |
| 2 | — | `693f5e845232` | `693f5e845232` | `693f5e845232` | 0.9703 | 0.9539 | 0.0137 | -0.0045 | 0.9703 | 0 | 19.2s | 36.36% |
| 3 | — | `d0e428c5372c` | `d0e428c5372c` | `d0e428c5372c` | 0.9703 | 0.9539 | 0.0137 | -0.0045 | 0.9703 | 0 | 26.5s | 45.45% |
| 4 | — | `342fb75c5f5a` | `342fb75c5f5a` | `342fb75c5f5a` | 0.9703 | 0.9539 | 0.0137 | -0.0045 | 0.9703 | 0 | 27.5s | 54.55% |
| 5 | — | `9e6c4d554438` | `9e6c4d554438` | `9e6c4d554438` | 0.9703 | 0.9539 | 0.0137 | -0.0045 | 0.9703 | 0 | 35.1s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — msre_bfq_spbv_pbg

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9729 | 0.9785 | +0.0056 | Improved |
| 5 | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9761 | 0.9761 | +0.0000 | Unchanged |
| 6 | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9920 | 0.9911 | -0.0009 | Unchanged |
| 9 | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `7b7dbac43ea6` | `7b7dbac43ea6` | 0.9643 | 0.9643 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `7b7dbac43ea6` | `7b7dbac43ea6` | 10.3s | 18.18% |

Total winner changes: **1**.
Search completed in **53.7s** wall-clock time.

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

## Calibration Intelligence — msre_bfq_spbv_pbg

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035433`
- Calibration schema: `1.1`
- Detector: `msre_bfq_spbv_pbg`
- Detector configuration: `hth-pipeline/config/detectors/msre_bfq_spbv_pbg.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `7b7dbac43ea6`
- Recommended parameter short name: `7b7dbac43ea6`
- Best observed Avg IoU: `0.9747`
- Avg IoU Success: `0.9747`
- Worst Golden Set page (Min IoU): `0.9638`
- Page-to-page StdDev: `0.0101`
- Calibration evidence: `Medium`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50176 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 2d 21h 7m 37s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9747 |
| Minimum Avg IoU | 0.9703 |
| Avg IoU StdDev | 0.0016 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 10.3s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (18.2%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50176 | 100.0% | 2d 21h 8m 32s | 1.0× |
| Exhaustive | 50176 | 100.0% | 2d 21h 8m 32s | 1.0× |
| Non-dormant | 33 | 0.1% | 2m 44s | 1520.5× |
| Low+ | 33 | 0.1% | 2m 44s | 1520.5× |
| Moderate+ | 33 | 0.1% | 2m 44s | 1520.5× |
| Important+ | 33 | 0.1% | 2m 44s | 1520.5× |
| Critical | 33 | 0.1% | 2m 44s | 1520.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `consensus_tolerance_fraction` | Critical | 1.0000 | 0.0045 | 18.2% | `0.031641` (0.9747), `0.012` (0.9738), `0.004` (0.9703) | current run |
| `minimum_side_consensus` | Critical | 1.0000 | 0.0045 | 66.7% | `0.867713` (0.9747), `0.5` (0.9738), `0.1` (0.9703) | current run |
| `consensus_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.6` (0.9710) | current run |
| `gradient_percentile` | Zombie | 0.0000 | 0.0000 | 100.0% | `76` (0.9710) | current run |
| `gradient_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.25` (0.9710) | current run |
| `minimum_side_gradient_support` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.03` (0.9710) | current run |
| `source_diversity_weight` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.15` (0.9710) | current run |

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
| 1 | 0.9734 | 0.9729 | 0.9785 | 0.0016 | 100.0% |
| 5 | 0.9754 | 0.9752 | 0.9761 | 0.0003 | 100.0% |
| 6 | 0.9919 | 0.9911 | 0.9920 | 0.0003 | 100.0% |
| 9 | 0.9557 | 0.9539 | 0.9638 | 0.0038 | 100.0% |
| 10 | 0.9587 | 0.9574 | 0.9643 | 0.0027 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="multi-scale-radial-edge-search-multiscaleradialedge-2"></a>
<details>
<summary><strong>Multi-Scale Radial Edge Search (`multi_scale_radial_edge`)</strong></summary>

**Status:** complete

## Run Information — multi_scale_radial_edge

### Build Provenance

- Run ID: `run-20260820-035531`
- Detector: `multi_scale_radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:55:31.797384+00:00`
- Finished: `2026-08-20T03:55:42.081662+00:00`
- Wall-clock elapsed: `10.3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `48335`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — multi_scale_radial_edge

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `235cd315ed3e` | `ddb7623ebb92` | `ddb7623ebb92` | `ddb7623ebb92` | 0.9765 | 0.9566 | 0.0175 | 0.9765 | 0 | 3.1s |
| Baseline | `HTH-0001` | `235cd315ed3e` | `e732fc5165fb` | `e732fc5165fb` | `baseline` | 0.6520 | 0.3544 | 0.1762 | 0.6520 | 0 | 827 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `ddb7623ebb92` |
| Parameter Set ID (legacy alias) | `ddb7623ebb92` |
| Absolute parameter SHA-256 | `906ef3a96536cebaca808023a8f9150951165020cbdc874a3d4d113ef5e1a94b` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| [#464](https://github.com/dlstupka/hth/actions/runs/31995147935) | 2026-08-17 | `ddb7623ebb92` | `ddb7623ebb92` | partial |
| [#460](https://github.com/dlstupka/hth/actions/runs/31994623927) | 2026-08-17 | `ddb7623ebb92` | `ddb7623ebb92` | partial |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#464](https://github.com/dlstupka/hth/actions/runs/31995147935) | `e732fc5165fb` | `e732fc5165fb` | `baseline` | 0.6520 | 0.3544 | 0.1762 | -0.3245 | 0.6520 | 0 | reference | reference |
| Best** | [#464](https://github.com/dlstupka/hth/actions/runs/31995147935) | `ddb7623ebb92` | `ddb7623ebb92` | `ddb7623ebb92` | 0.9765 | 0.9566 | 0.0175 | +0.0000 | 0.9765 | 0 | reference | reference |
| 1 | [#464](https://github.com/dlstupka/hth/actions/runs/31995147935) | `82346a58b9d3` | `82346a58b9d3` | `82346a58b9d3` | 0.9020 | 0.7318 | 0.0897 | -0.0746 | 0.9020 | 0 | 6.3s | 81.82% |
| 2 | [#464](https://github.com/dlstupka/hth/actions/runs/31995147935) | `3794c3a143a9` | `3794c3a143a9` | `3794c3a143a9` | 0.9018 | 0.7318 | 0.0896 | -0.0747 | 0.9018 | 0 | 6s | 72.73% |
| 3 | [#464](https://github.com/dlstupka/hth/actions/runs/31995147935) | `1ec9b961447c` | `1ec9b961447c` | `1ec9b961447c` | 0.9003 | 0.7318 | 0.0884 | -0.0763 | 0.9003 | 0 | 7s | 100.00% |
| 4 | [#464](https://github.com/dlstupka/hth/actions/runs/31995147935) | `17b9ede58a3c` | `17b9ede58a3c` | `17b9ede58a3c` | 0.8999 | 0.7318 | 0.0882 | -0.0766 | 0.8999 | 0 | 6.8s | 90.91% |
| 5 | [#464](https://github.com/dlstupka/hth/actions/runs/31995147935) | `7655f2d438cb` | `7655f2d438cb` | `7655f2d438cb` | 0.8955 | 0.7318 | 0.0853 | -0.0811 | 0.8955 | 0 | 5.1s | 45.45% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — multi_scale_radial_edge

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `ddb7623ebb92` | `ddb7623ebb92` | 0.7081 | 0.9767 | +0.2686 | Improved |
| 5 | `ddb7623ebb92` | `ddb7623ebb92` | 0.6844 | 0.9962 | +0.3119 | Improved |
| 6 | `ddb7623ebb92` | `ddb7623ebb92` | 0.3544 | 0.9959 | +0.6414 | Improved |
| 9 | `ddb7623ebb92` | `ddb7623ebb92` | 0.6140 | 0.9566 | +0.3426 | Improved |
| 10 | `ddb7623ebb92` | `ddb7623ebb92` | 0.8991 | 0.9573 | +0.0581 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `ddb7623ebb92` | `ddb7623ebb92` | 3.9s | 18.18% |

Total winner changes: **1**.
Search completed in **10.3s** wall-clock time.

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

## Calibration Intelligence — multi_scale_radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035531`
- Calibration schema: `1.1`
- Detector: `multi_scale_radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/multi_scale_radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `ddb7623ebb92`
- Recommended parameter short name: `ddb7623ebb92`
- Best observed Avg IoU: `0.9765`
- Avg IoU Success: `0.9765`
- Worst Golden Set page (Min IoU): `0.9566`
- Page-to-page StdDev: `0.0175`
- Calibration evidence: `Medium`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 48335 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 1d 17h 34m 9s |
| Fully successful parameter sets | 9 (90.0%) |
| Best Avg IoU | 0.9020 |
| Minimum Avg IoU | 0.4733 |
| Avg IoU StdDev | 0.1379 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 3.9s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (20.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 48334 | 100.0% | 1d 17h 34m 37s | 1.0× |
| Exhaustive | 48334 | 100.0% | 1d 17h 34m 37s | 1.0× |
| Non-dormant | 18 | 0.0% | 55.7s | 2685.2× |
| Low+ | 18 | 0.0% | 55.7s | 2685.2× |
| Moderate+ | 18 | 0.0% | 55.7s | 2685.2× |
| Important+ | 18 | 0.0% | 55.7s | 2685.2× |
| Critical | 18 | 0.0% | 55.7s | 2685.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_percentile` | Critical | 0.9159 | 0.3393 | 22.2% | `94.375` (0.9020), `94` (0.9018), `95.25` (0.9003) | current run |
| `ray_count` | Critical | 0.1597 | 0.1837 | 50.0% | `64` (0.8357), `144` (0.6520) | current run |
| `area_weight` | Critical | 0.1437 | 0.0000 | 0.0% | `0.2` (0.6520) | current run |
| `bbox_padding_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0` (0.6520) | current run |
| `maximum_area_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0.98` (0.6520) | current run |
| `maximum_radius_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0.78` (0.6520) | current run |
| `minimum_area_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0.18` (0.6520) | current run |
| `minimum_radius_fraction` | Critical | 0.1437 | 0.0000 | 0.0% | `0.16` (0.6520) | current run |
| `minimum_ray_support` | Critical | 0.1437 | 0.0000 | 0.0% | `0.36` (0.6520) | current run |
| `strength_weight` | Critical | 0.1437 | 0.0000 | 0.0% | `0.3` (0.6520) | current run |
| `support_weight` | Critical | 0.1437 | 0.0000 | 0.0% | `0.5` (0.6520) | current run |
| `base_sigma` | Zombie | 0.0000 | 0.0000 | 100.0% | `0.8` (0.8173) | current run |
| `scale_count` | Zombie | 0.0000 | 0.0000 | 100.0% | `3` (0.8173) | current run |
| `scale_ratio` | Zombie | 0.0000 | 0.0000 | 100.0% | `2` (0.8173) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `gradient_percentile` × `ray_count` | 1.0000 | 0.0841 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8200 | 0.3625 | 0.8950 | 0.1620 | 100.0% |
| 5 | 0.8821 | 0.6844 | 0.9741 | 0.1010 | 100.0% |
| 6 | 0.6182 | 0.3345 | 0.7318 | 0.1738 | 100.0% |
| 9 | 0.8274 | 0.0000 | 0.9585 | 0.2942 | 90.0% |
| 10 | 0.9389 | 0.8546 | 0.9567 | 0.0326 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="orli-page-mask-orlipagemask-2"></a>
<details>
<summary><strong>Orli Page Mask (`orli_page_mask`)</strong></summary>

**Status:** complete

## Run Information — orli_page_mask

### Build Provenance

- Run ID: `run-20260820-035635`
- Detector: `orli_page_mask`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:35.347268+00:00`
- Finished: `2026-08-20T03:56:42.823694+00:00`
- Wall-clock elapsed: `7.5s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1680`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.65%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — orli_page_mask

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `e94fed281c30` | `d58e03537115` | `bd0c02b4f4fe` | `bd0c02b4f4fe` | 0.9185 | 0.8557 | 0.0411 | 0.9185 | 0 | 486 ms |
| Baseline | `HTH-0001` | `e94fed281c30` | `479a861bb552` | `d75b76f301e6` | `baseline` | 0.8063 | 0.6913 | 0.0867 | 0.8063 | 0 | 1.4s |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 2 |
| Total metric improvements | 4 |
| Parameter sets with improvements | 2 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `479a861bb552` | `d75b76f301e6` | `baseline` | 0.8063 | 0.6913 | 0.0867 | -0.1122 | 0.8063 | 0 | reference | reference |
| Best** | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `d58e03537115` | `bd0c02b4f4fe` | `bd0c02b4f4fe` | 0.9185 | 0.8557 | 0.0411 | +0.0000 | 0.9185 | 0 | reference | reference |
| 1 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `0d91a06fe178` | `df47a71b2101` | `df47a71b2101` | 0.0000 | 0.0000 | 0.0000 | -0.9185 | 0.0000 | 5 | 2.9s | 36.36% |
| 2 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `c6ab179988ea` | `b5bffe569ef0` | `b5bffe569ef0` | 0.0000 | 0.0000 | 0.0000 | -0.9185 | 0.0000 | 5 | 2.7s | 27.27% |
| 3 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `80b8be1482c2` | `1f96a73219f3` | `1f96a73219f3` | 0.0000 | 0.0000 | 0.0000 | -0.9185 | 0.0000 | 5 | 3.6s | 45.45% |
| 4 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `4189b7899756` | `e7f7b003d576` | `e7f7b003d576` | 0.0000 | 0.0000 | 0.0000 | -0.9185 | 0.0000 | 5 | 3.8s | 54.55% |
| 5 | [#584](https://github.com/dlstupka/hth/actions/runs/32327736880) | `dda61b64c8ee` | `63b7e71e9389` | `63b7e71e9389` | 0.0000 | 0.0000 | 0.0000 | -0.9185 | 0.0000 | 5 | 4.5s | 63.64% |

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
| 1 (final) | `d58e03537115` | `bd0c02b4f4fe` | 1.9s | 18.18% |

Total winner changes: **1**.
Search completed in **7.5s** wall-clock time.

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

## Calibration Intelligence — orli_page_mask

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035635`
- Calibration schema: `1.1`
- Detector: `orli_page_mask`
- Detector configuration: `hth-pipeline/config/detectors/orli_page_mask.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `bd0c02b4f4fe`
- Recommended parameter short name: `bd0c02b4f4fe`
- Best observed Avg IoU: `0.9185`
- Avg IoU Success: `0.9185`
- Worst Golden Set page (Min IoU): `0.8557`
- Page-to-page StdDev: `0.0411`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `close_kernel_fraction, fill_holes`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 9 of 11 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1680 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.7% |
| Est. serial runtime for full parameter set evaluation* | 13m 29s |
| Fully successful parameter sets | 2 (18.2%) |
| Best Avg IoU | 0.9185 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.3335 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.9s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 16800 | 100.0% | 2h 15m 38s | 1.0× |
| Exhaustive | 1680 | 10.0% | 13m 34s | 10.0× |
| Non-dormant | 112 | 0.7% | 54.3s | 150.0× |
| Low+ | 112 | 0.7% | 54.3s | 150.0× |
| Moderate+ | 112 | 0.7% | 54.3s | 150.0× |
| Important+ | 112 | 0.7% | 54.3s | 150.0× |
| Critical | 112 | 0.7% | 54.3s | 150.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `page_padding_fraction` | Critical | 1.0000 | 0.9185 | 25.0% | `0.16` (0.9185), `0.05` (0.8063), `0` (0.0000) | current run |
| `include_lines` | Critical | 0.9949 | 0.8624 | 50.0% | `1` (0.8624), `0` (0.0000) | current run |
| `dilation_fraction` | Critical | 0.3794 | 0.7145 | 50.0% | `0.01` (0.8063), `0` (0.0918) | current run |
| `minimum_page_area_fraction` | Critical | 0.2745 | 0.4032 | 14.3% | `0.12` (0.4032), `0.04` (0.3062), `0.06` (0.0000) | current run |
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

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `dilation_fraction` × `minimum_page_area_fraction` | 0.5403 | 0.1609 | 11 |
| `include_lines` × `dilation_fraction` | 1.0000 | 0.0051 | 11 |
| `include_lines` × `minimum_page_area_fraction` | 1.0000 | 0.0051 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.1558 | 0.0000 | 0.9357 | 0.3323 | 18.2% |
| 5 | 0.1672 | 0.0000 | 0.9263 | 0.3546 | 18.2% |
| 6 | 0.1406 | 0.0000 | 0.8557 | 0.3004 | 18.2% |
| 9 | 0.1495 | 0.0000 | 0.8959 | 0.3186 | 18.2% |
| 10 | 0.1709 | 0.0000 | 0.9788 | 0.3629 | 18.2% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="page-background-pagebackground-2"></a>
<details>
<summary><strong>Page Background (`page_background`)</strong></summary>

**Status:** complete

## Run Information — page_background

### Build Provenance

- Run ID: `run-20260820-035600`
- Detector: `page_background`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:00.485818+00:00`
- Finished: `2026-08-20T03:56:08.782197+00:00`
- Wall-clock elapsed: `8.3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `48401`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — page_background

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `ef29eca47b5c` | `afbe81a796a1` | `afbe81a796a1` | `afbe81a796a1` | 0.9692 | 0.9498 | 0.0171 | 0.9692 | 0 | 419 ms |
| Baseline | `HTH-0001` | `ef29eca47b5c` | `c81fb1ff4213` | `c81fb1ff4213` | `baseline` | 0.7618 | 0.0000 | 0.3812 | 0.9523 | 1 | 588 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `afbe81a796a1` |
| Parameter Set ID (legacy alias) | `afbe81a796a1` |
| Absolute parameter SHA-256 | `a74ff2d88f4f8366c3d49ca37a44e540b158d4bba96daca56bcddb1c82bc8ef8` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `c81fb1ff4213` | `c81fb1ff4213` | `baseline` | 0.7618 | 0.0000 | 0.3812 | -0.2074 | 0.9523 | 1 | reference | reference |
| Best** | — | `afbe81a796a1` | `afbe81a796a1` | `afbe81a796a1` | 0.9692 | 0.9498 | 0.0171 | +0.0000 | 0.9692 | 0 | reference | reference |
| 1 | — | `5ba735a3e4a4` | `5ba735a3e4a4` | `5ba735a3e4a4` | 0.9664 | 0.9476 | 0.0212 | -0.0028 | 0.9664 | 0 | 4.5s | 90.91% |
| 2 | — | `39a3c9b2d5e8` | `39a3c9b2d5e8` | `39a3c9b2d5e8` | 0.9662 | 0.9476 | 0.0214 | -0.0030 | 0.9662 | 0 | 3.9s | 81.82% |
| 3 | — | `156e30d9452e` | `156e30d9452e` | `156e30d9452e` | 0.9638 | 0.9437 | 0.0222 | -0.0055 | 0.9638 | 0 | 2.1s | 36.36% |
| 4 | — | `7364bda565d2` | `7364bda565d2` | `7364bda565d2` | 0.9638 | 0.9437 | 0.0222 | -0.0055 | 0.9638 | 0 | 2.2s | 45.45% |
| 5 | — | `35244cae67e0` | `35244cae67e0` | `35244cae67e0` | 0.9638 | 0.9437 | 0.0222 | -0.0055 | 0.9638 | 0 | 3s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — page_background

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `afbe81a796a1` | `afbe81a796a1` | 0.9402 | 0.9644 | +0.0242 | Improved |
| 5 | `afbe81a796a1` | `afbe81a796a1` | 0.9794 | 0.9810 | +0.0016 | Improved |
| 6 | `afbe81a796a1` | `afbe81a796a1` | 0.0000 | 0.9961 | +0.9961 | Recovered |
| 9 | `afbe81a796a1` | `afbe81a796a1` | 0.9441 | 0.9498 | +0.0057 | Improved |
| 10 | `afbe81a796a1` | `afbe81a796a1` | 0.9456 | 0.9550 | +0.0094 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `afbe81a796a1` | `afbe81a796a1` | 1s | 18.18% |

Total winner changes: **1**.
Search completed in **8.3s** wall-clock time.

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

## Calibration Intelligence — page_background

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035600`
- Calibration schema: `1.1`
- Detector: `page_background`
- Detector configuration: `hth-pipeline/config/detectors/page_background.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `afbe81a796a1`
- Recommended parameter short name: `afbe81a796a1`
- Best observed Avg IoU: `0.9692`
- Avg IoU Success: `0.9692`
- Worst Golden Set page (Min IoU): `0.9498`
- Page-to-page StdDev: `0.0171`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 48401 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 5h 37m 28s |
| Fully successful parameter sets | 9 (90.0%) |
| Best Avg IoU | 0.9664 |
| Minimum Avg IoU | 0.7618 |
| Avg IoU StdDev | 0.0603 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (20.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 48400 | 100.0% | 5h 37m 32s | 1.0× |
| Exhaustive | 48400 | 100.0% | 5h 37m 32s | 1.0× |
| Non-dormant | 384 | 0.8% | 2m 41s | 126.0× |
| Low+ | 384 | 0.8% | 2m 41s | 126.0× |
| Moderate+ | 384 | 0.8% | 2m 41s | 126.0× |
| Important+ | 384 | 0.8% | 2m 41s | 126.0× |
| Critical | 384 | 0.8% | 2m 41s | 126.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `close_kernel_fraction` | Critical | 0.9992 | 0.2020 | 33.3% | `0` (0.9639), `0.0005` (0.9516), `0.008` (0.7618) | current run |
| `blur_sigma` | Critical | 0.9955 | 0.2007 | 50.0% | `0` (0.9625), `1.2` (0.7618) | current run |
| `border_band_fraction` | Critical | 0.9955 | 0.2007 | 50.0% | `0.015` (0.9625), `0.06` (0.7618) | current run |
| `minimum_border_background_fraction` | Critical | 0.9955 | 0.2007 | 50.0% | `0.15` (0.9625), `0.5` (0.7618) | current run |
| `minimum_page_area_fraction` | Critical | 0.9955 | 0.2007 | 50.0% | `0.15` (0.9625), `0.25` (0.7618) | current run |
| `maximum_page_area_fraction` | Critical | 0.8960 | 0.0000 | 0.0% | `0.98` (0.7618) | current run |
| `minimum_rectangularity` | Critical | 0.8960 | 0.0000 | 0.0% | `0.6` (0.7618) | current run |
| `open_kernel_fraction` | Critical | 0.4392 | 0.1036 | 25.0% | `0.006` (0.9664), `0.0045` (0.9662), `0.0015` (0.9638) | current run |
| `color_distance_threshold` | Zombie | 0.0000 | 0.0000 | 100.0% | `3` (0.9425) | current run |

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
| 1 | 0.9459 | 0.9402 | 0.9489 | 0.0026 | 100.0% |
| 5 | 0.9876 | 0.9772 | 0.9920 | 0.0054 | 100.0% |
| 6 | 0.8903 | 0.0000 | 0.9961 | 0.2968 | 90.0% |
| 9 | 0.9446 | 0.9328 | 0.9476 | 0.0045 | 100.0% |
| 10 | 0.9439 | 0.9291 | 0.9512 | 0.0056 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="polar-boundary-voting-polarboundaryvote-2"></a>
<details>
<summary><strong>Polar Boundary Voting (`polar_boundary_vote`)</strong></summary>

**Status:** complete

## Run Information — polar_boundary_vote

### Build Provenance

- Run ID: `run-20260820-035652`
- Detector: `polar_boundary_vote`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:52.184245+00:00`
- Finished: `2026-08-20T03:56:54.629071+00:00`
- Wall-clock elapsed: `2.4s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `19636`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.06%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
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
| Winner | `HTH-0001` | `ae1c492f8b89` | `935369155754` | `935369155754` | `935369155754` | 0.9691 | 0.9524 | 0.0154 | 0.9691 | 0 | 121 ms |
| Baseline | `HTH-0001` | `ae1c492f8b89` | `cd967f93437d` | `cd967f93437d` | `baseline` | 0.9678 | 0.9425 | 0.0182 | 0.9678 | 0 | 230 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `935369155754` |
| Parameter Set ID (legacy alias) | `935369155754` |
| Absolute parameter SHA-256 | `7b4f35df887d2a7fad20e3d7023e6067637fa43897fe7e27b8922e81a54fab2f` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `33ebf4c17649a430f2bb362be7e2b13c30508a7d61b7abb2b3146de89e4c3fc9` |
| Grid ordinal | `3850` |
| Reproducibility | **Fully reproducible** |

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
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `cd967f93437d` | `cd967f93437d` | `baseline` | 0.9678 | 0.9425 | 0.0182 | -0.0013 | 0.9678 | 0 | reference | reference |
| Best** | — | `935369155754` | `935369155754` | `935369155754` | 0.9691 | 0.9524 | 0.0154 | +0.0000 | 0.9691 | 0 | reference | reference |
| 1 | — | `8e42d73c350b` | `8e42d73c350b` | `8e42d73c350b` | 0.8991 | 0.8205 | 0.0460 | -0.0700 | 0.8991 | 0 | 999 ms | 100.00% |
| 2 | — | `e2eac70d041d` | `e2eac70d041d` | `e2eac70d041d` | 0.8979 | 0.8204 | 0.0457 | -0.0712 | 0.8979 | 0 | 944 ms | 90.91% |
| 3 | — | `e671a728c6d4` | `e671a728c6d4` | `e671a728c6d4` | 0.8966 | 0.8204 | 0.0454 | -0.0725 | 0.8966 | 0 | 922 ms | 81.82% |
| 4 | — | `e5ad7959f684` | `e5ad7959f684` | `e5ad7959f684` | 0.8956 | 0.8204 | 0.0450 | -0.0735 | 0.8956 | 0 | 806 ms | 72.73% |
| 5 | — | `f2305c0a35d0` | `f2305c0a35d0` | `f2305c0a35d0` | 0.8947 | 0.8204 | 0.0445 | -0.0744 | 0.8947 | 0 | 781 ms | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — polar_boundary_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `935369155754` | `935369155754` | 0.9819 | 0.9684 | -0.0135 | Regressed |
| 5 | `935369155754` | `935369155754` | 0.9925 | 0.9942 | +0.0017 | Improved |
| 6 | `935369155754` | `935369155754` | 0.9688 | 0.9765 | +0.0077 | Improved |
| 9 | `935369155754` | `935369155754` | 0.9425 | 0.9524 | +0.0099 | Improved |
| 10 | `935369155754` | `935369155754` | 0.9533 | 0.9541 | +0.0007 | Unchanged |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `935369155754` | `935369155754` | 355 ms | 18.18% |

Total winner changes: **1**.
Search completed in **2.4s** wall-clock time.

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
| 1 | `935369155754` | `935369155754` | 0.9684 | Regressed |

## Calibration Intelligence — polar_boundary_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035652`
- Calibration schema: `1.1`
- Detector: `polar_boundary_vote`
- Detector configuration: `hth-pipeline/config/detectors/polar_boundary_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `935369155754`
- Recommended parameter short name: `935369155754`
- Best observed Avg IoU: `0.9691`
- Avg IoU Success: `0.9691`
- Worst Golden Set page (Min IoU): `0.9524`
- Page-to-page StdDev: `0.0154`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 19636 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 39m 34s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.9691 |
| Minimum Avg IoU | 0.8908 |
| Avg IoU StdDev | 0.0285 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 355 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 19635 | 100.0% | 39m 35s | 1.0× |
| Exhaustive | 19635 | 100.0% | 39m 35s | 1.0× |
| Non-dormant | 108 | 0.6% | 13.1s | 181.8× |
| Low+ | 108 | 0.6% | 13.1s | 181.8× |
| Moderate+ | 108 | 0.6% | 13.1s | 181.8× |
| Important+ | 108 | 0.6% | 13.1s | 181.8× |
| Critical | 108 | 0.6% | 13.1s | 181.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gradient_percentile` | Critical | 0.9930 | 0.0743 | 33.3% | `94` (0.9691), `90` (0.9678), `84` (0.8948) | current run |
| `outer_radius_fraction` | Critical | 0.9929 | 0.0737 | 50.0% | `0.6` (0.9684), `0.4` (0.8948) | current run |
| `bbox_padding_fraction` | Critical | 0.5505 | 0.0508 | 11.1% | `0` (0.9426), `0.01` (0.8991), `0.008` (0.8979) | current run |
| `ray_count` | Critical | 0.4372 | 0.0656 | 50.0% | `180` (0.9678), `90` (0.9022) | current run |
| `inner_radius_fraction` | Critical | 0.3974 | 0.0000 | 0.0% | `0.06` (0.9678) | current run |
| `minimum_support_fraction` | Critical | 0.3974 | 0.0000 | 0.0% | `0.25` (0.9678) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `bbox_padding_fraction` × `ray_count` | 0.6573 | 0.1067 | 11 |
| `gradient_percentile` × `bbox_padding_fraction` | 1.0000 | 0.0070 | 11 |
| `outer_radius_fraction` × `bbox_padding_fraction` | 0.9999 | 0.0070 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8878 | 0.8620 | 0.9819 | 0.0415 | 100.0% |
| 5 | 0.9444 | 0.9263 | 0.9942 | 0.0235 | 100.0% |
| 6 | 0.9434 | 0.9305 | 0.9765 | 0.0143 | 100.0% |
| 9 | 0.8435 | 0.8204 | 0.9524 | 0.0491 | 100.0% |
| 10 | 0.9217 | 0.9145 | 0.9541 | 0.0151 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="projective-gradient-vote-projectivegradientvote-2"></a>
<details>
<summary><strong>Projective Gradient Vote (`projective_gradient_vote`)</strong></summary>

**Status:** complete

## Run Information — projective_gradient_vote

### Build Provenance

- Run ID: `run-20260820-035703`
- Detector: `projective_gradient_vote`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:57:03.689241+00:00`
- Finished: `2026-08-20T03:57:09.892965+00:00`
- Wall-clock elapsed: `6.2s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `730`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `1.51%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — projective_gradient_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `10c49cfcf0a8` | `e536a07cca54` | `e536a07cca54` | `e536a07cca54` | 0.5541 | 0.0000 | 0.4546 | 0.9235 | 2 | 847 ms |
| Baseline | `HTH-0001` | `10c49cfcf0a8` | `c6d5d9271464` | `c6d5d9271464` | `baseline` | 0.4474 | 0.0000 | 0.3917 | 0.7457 | 2 | 875 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `e536a07cca54` |
| Parameter Set ID (legacy alias) | `e536a07cca54` |
| Absolute parameter SHA-256 | `c929b8c419967ff8c374fcde1498a6bbfb38e4d0c0512b99781ae5412dfd7420` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `4af0d7b29b360e5cc1db2842d6c10c4e41494d99496461a32334ccc3d6d77b3a` |
| Grid ordinal | `624` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 1 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `c6d5d9271464` | `c6d5d9271464` | `baseline` | 0.4474 | 0.0000 | 0.3917 | -0.1067 | 0.7457 | 2 | reference | reference |
| Best** | — | `e536a07cca54` | `e536a07cca54` | `e536a07cca54` | 0.5541 | 0.0000 | 0.4546 | +0.0000 | 0.9235 | 2 | reference | reference |
| 1 | — | `ea6049908ba9` | `ea6049908ba9` | `ea6049908ba9` | 0.5463 | 0.0000 | 0.4477 | -0.0078 | 0.9105 | 2 | 2.6s | 27.27% |
| 2 | — | `058b6c85f605` | `058b6c85f605` | `058b6c85f605` | 0.5463 | 0.0000 | 0.4477 | -0.0078 | 0.9105 | 2 | 2.6s | 36.36% |
| 3 | — | `218afc35ed78` | `218afc35ed78` | `218afc35ed78` | 0.5463 | 0.0000 | 0.4477 | -0.0078 | 0.9105 | 2 | 3.5s | 54.55% |
| 4 | — | `09234c13ffc4` | `09234c13ffc4` | `09234c13ffc4` | 0.5463 | 0.0000 | 0.4477 | -0.0078 | 0.9105 | 2 | 3.4s | 45.45% |
| 5 | — | `928d5fcecfd4` | `928d5fcecfd4` | `928d5fcecfd4` | 0.5463 | 0.0000 | 0.4477 | -0.0078 | 0.9105 | 2 | 4.2s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — projective_gradient_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `e536a07cca54` | `e536a07cca54` | 0.9069 | 0.9698 | +0.0629 | Improved |
| 5 | `e536a07cca54` | `e536a07cca54` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `e536a07cca54` | `e536a07cca54` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `e536a07cca54` | `e536a07cca54` | 0.8393 | 0.8437 | +0.0045 | Improved |
| 10 | `e536a07cca54` | `e536a07cca54` | 0.4910 | 0.9570 | +0.4660 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `e536a07cca54` | `e536a07cca54` | 1.7s | 18.18% |

Total winner changes: **1**.
Search completed in **6.2s** wall-clock time.

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
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 5 | `e536a07cca54` | `e536a07cca54` | 0.0000 | No polygon found |
| 6 | `e536a07cca54` | `e536a07cca54` | 0.0000 | No polygon found |

## Calibration Intelligence — projective_gradient_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035703`
- Calibration schema: `1.1`
- Detector: `projective_gradient_vote`
- Detector configuration: `hth-pipeline/config/detectors/projective_gradient_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `e536a07cca54`
- Recommended parameter short name: `e536a07cca54`
- Best observed Avg IoU: `0.5541`
- Avg IoU Success: `0.9235`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4546`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 730 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 10m 8s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5541 |
| Minimum Avg IoU | 0.4474 |
| Avg IoU StdDev | 0.0287 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.7s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 10m 17s | 1.0× |
| Exhaustive | 729 | 100.0% | 10m 17s | 1.0× |
| Non-dormant | 324 | 44.4% | 4m 34s | 2.2× |
| Low+ | 324 | 44.4% | 4m 34s | 2.2× |
| Moderate+ | 324 | 44.4% | 4m 34s | 2.2× |
| Important+ | 324 | 44.4% | 4m 34s | 2.2× |
| Critical | 108 | 14.8% | 1m 31s | 6.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gaussian_sigma` | Critical | 1.0000 | 0.1067 | 33.3% | `1.8` (0.5541), `0.8` (0.5463), `1.2` (0.4474) | current run |
| `minimum_segment_fraction` | Critical | 1.0000 | 0.1067 | 33.3% | `0.24` (0.5541), `0.1` (0.5463), `0.16` (0.4474) | current run |
| `family_tolerance_degrees` | Critical | 0.9940 | 0.0996 | 50.0% | `10` (0.5471), `16` (0.4474) | current run |
| `angle_bin_degrees` | Critical | 0.9036 | 0.0000 | 0.0% | `4` (0.4474) | current run |
| `area_weight` | Critical | 0.9036 | 0.0000 | 0.0% | `0.15` (0.4474) | current run |
| `bbox_padding_fraction` | Critical | 0.9036 | 0.0000 | 0.0% | `0` (0.4474) | current run |
| `geometry_weight` | Critical | 0.9036 | 0.0000 | 0.0% | `0.3` (0.4474) | current run |
| `maximum_area_fraction` | Critical | 0.9036 | 0.0000 | 0.0% | `0.98` (0.4474) | current run |
| `maximum_corner_overshoot_fraction` | Critical | 0.9036 | 0.0000 | 0.0% | `0.08` (0.4474) | current run |
| `minimum_area_fraction` | Critical | 0.9036 | 0.0000 | 0.0% | `0.18` (0.4474) | current run |
| `support_weight` | Critical | 0.9036 | 0.0000 | 0.0% | `0.55` (0.4474) | current run |
| `gradient_percentile` | Critical | 0.3735 | 0.0455 | 50.0% | `74` (0.5463), `82` (0.5008) | current run |
| `minimum_side_support` | Critical | 0.1877 | 0.0267 | 33.3% | `0.08` (0.5483), `0.3` (0.5463), `0.18` (0.5216) | current run |
| `orthogonality_tolerance_degrees` | Important | 0.0996 | 0.0182 | 33.3% | `12` (0.5463), `32` (0.5463), `22` (0.5281) | current run |

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
| 1 | 0.9201 | 0.9069 | 0.9698 | 0.0159 | 100.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8456 | 0.8393 | 0.8465 | 0.0022 | 100.0% |
| 10 | 0.9245 | 0.4910 | 0.9690 | 0.1371 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="radial-edge-search-radialedge-2"></a>
<details>
<summary><strong>Radial Edge Search (`radial_edge`)</strong></summary>

**Status:** complete

## Run Information — radial_edge

### Build Provenance

- Run ID: `run-20260820-035705`
- Detector: `radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:57:05.057584+00:00`
- Finished: `2026-08-20T03:57:09.093461+00:00`
- Wall-clock elapsed: `4s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `50001`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — radial_edge

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `48fd60fb2fda` | `837321a04ccf` | `837321a04ccf` | `837321a04ccf` | 0.9571 | 0.9261 | 0.0183 | 0.9571 | 0 | 144 ms |
| Baseline | `HTH-0001` | `48fd60fb2fda` | `d593fad7aeea` | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | 0.9503 | 0 | 137 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `837321a04ccf` |
| Parameter Set ID (legacy alias) | `837321a04ccf` |
| Absolute parameter SHA-256 | `9d6acb57090207933e95d74ebbe3b0d7412474b367ae91793a11e0fe035e4297` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 0 |
| Total metric improvements | 1 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `d593fad7aeea` | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | -0.0068 | 0.9503 | 0 | reference | reference |
| Best** | — | `837321a04ccf` | `837321a04ccf` | `837321a04ccf` | 0.9571 | 0.9261 | 0.0183 | +0.0000 | 0.9571 | 0 | reference | reference |
| 1 | — | `0c476a6d2841` | `0c476a6d2841` | `0c476a6d2841` | 0.7861 | 0.6915 | 0.0931 | -0.1710 | 0.7861 | 0 | 526 ms | 27.27% |
| 2 | — | `d1b85a845bdf` | `d1b85a845bdf` | `d1b85a845bdf` | 0.7861 | 0.6915 | 0.0931 | -0.1710 | 0.7861 | 0 | 534 ms | 36.36% |
| 3 | — | `ad5a7b3bfe96` | `ad5a7b3bfe96` | `ad5a7b3bfe96` | 0.7861 | 0.6915 | 0.0931 | -0.1710 | 0.7861 | 0 | 743 ms | 45.45% |
| 4 | — | `5ac13f6272da` | `5ac13f6272da` | `5ac13f6272da` | 0.7861 | 0.6915 | 0.0931 | -0.1710 | 0.7861 | 0 | 749 ms | 54.55% |
| 5 | — | `8e677524b6d5` | `8e677524b6d5` | `8e677524b6d5` | 0.7861 | 0.6915 | 0.0931 | -0.1710 | 0.7861 | 0 | 881 ms | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — radial_edge

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `837321a04ccf` | `837321a04ccf` | 0.9466 | 0.9751 | +0.0285 | Improved |
| 5 | `837321a04ccf` | `837321a04ccf` | 0.9742 | 0.9764 | +0.0022 | Improved |
| 6 | `837321a04ccf` | `837321a04ccf` | 0.9384 | 0.9261 | -0.0123 | Regressed |
| 9 | `837321a04ccf` | `837321a04ccf` | 0.9340 | 0.9533 | +0.0194 | Improved |
| 10 | `837321a04ccf` | `837321a04ccf` | 0.9582 | 0.9547 | -0.0036 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `837321a04ccf` | `837321a04ccf` | 283 ms | 18.18% |

Total winner changes: **1**.
Search completed in **4s** wall-clock time.

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
| 6 | `837321a04ccf` | `837321a04ccf` | 0.9261 | Regressed |
| 10 | `837321a04ccf` | `837321a04ccf` | 0.9547 | Regressed |

## Calibration Intelligence — radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035705`
- Calibration schema: `1.1`
- Detector: `radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `837321a04ccf`
- Recommended parameter short name: `837321a04ccf`
- Best observed Avg IoU: `0.9571`
- Avg IoU Success: `0.9571`
- Worst Golden Set page (Min IoU): `0.9261`
- Page-to-page StdDev: `0.0183`
- Calibration evidence: `Medium`
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

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 50001 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 1h 59m 43s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9503 |
| Minimum Avg IoU | 0.7861 |
| Avg IoU StdDev | 0.0493 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 283 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 50000 | 100.0% | 1h 59m 44s | 1.0× |
| Exhaustive | 50000 | 100.0% | 1h 59m 44s | 1.0× |
| Non-dormant | 384 | 0.8% | 55.2s | 130.2× |
| Low+ | 384 | 0.8% | 55.2s | 130.2× |
| Moderate+ | 384 | 0.8% | 55.2s | 130.2× |
| Important+ | 384 | 0.8% | 55.2s | 130.2× |
| Critical | 96 | 0.2% | 13.8s | 520.8× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `gaussian_sigma` | Critical | 1.0000 | 0.1642 | 50.0% | `1.2` (0.9503), `0.6` (0.7861) | current run |
| `gradient_percentile` | Critical | 1.0000 | 0.1642 | 50.0% | `82` (0.9503), `74` (0.7861) | current run |
| `maximum_radius_fraction` | Critical | 1.0000 | 0.1642 | 50.0% | `0.72` (0.9503), `0.6` (0.7861) | current run |
| `minimum_radius_fraction` | Critical | 1.0000 | 0.1642 | 50.0% | `0.18` (0.9503), `0.1` (0.7861) | current run |
| `ray_count` | Critical | 1.0000 | 0.1642 | 50.0% | `96` (0.9503), `64` (0.7861) | current run |
| `area_weight` | Critical | 0.9000 | 0.0000 | 100.0% | `0.35` (0.9503) | current run |
| `maximum_area_fraction` | Critical | 0.9000 | 0.0000 | 100.0% | `0.98` (0.9503) | current run |
| `minimum_area_fraction` | Critical | 0.9000 | 0.0000 | 100.0% | `0.18` (0.9503) | current run |
| `minimum_ray_support` | Critical | 0.4444 | 0.0821 | 33.3% | `0.45` (0.8682), `0.25` (0.7861), `0.35` (0.7861) | current run |
| `support_weight` | Important | 0.1111 | 0.0328 | 50.0% | `0.45` (0.8189), `0.35` (0.7861) | current run |
| `rectangularity_weight` | Important | 0.0741 | 0.0274 | 50.0% | `0.2` (0.8135), `0.3` (0.7861) | current run |

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
| 1 | 0.7171 | 0.6916 | 0.9466 | 0.0765 | 100.0% |
| 5 | 0.9356 | 0.9313 | 0.9742 | 0.0129 | 100.0% |
| 6 | 0.7162 | 0.6915 | 0.9384 | 0.0741 | 100.0% |
| 9 | 0.7833 | 0.7665 | 0.9340 | 0.0502 | 100.0% |
| 10 | 0.8604 | 0.8495 | 0.9582 | 0.0326 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="radon-boundary-projection-radonboundary-2"></a>
<details>
<summary><strong>Radon Boundary Projection (`radon_boundary`)</strong></summary>

**Status:** complete

## Run Information — radon_boundary

### Build Provenance

- Run ID: `run-20260820-035620`
- Detector: `radon_boundary`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:20.367722+00:00`
- Finished: `2026-08-20T03:56:28.984623+00:00`
- Wall-clock elapsed: `8.6s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `729`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `1.51%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — radon_boundary

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `b74bb00ea731` | `dd6b2601d568` | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | 0.4983 | 0 | 621 ms |
| Baseline | `HTH-0001` | `b74bb00ea731` | `f26bbb16c7b6` | `f26bbb16c7b6` | `baseline` | 0.4227 | 0.2130 | 0.2863 | 0.4227 | 0 | 875 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `dd6b2601d568` |
| Parameter Set ID (legacy alias) | `dd6b2601d568` |
| Absolute parameter SHA-256 | `43e8ccf3f21d2e2b42176dc5e58e120188f236d99da38a4e8011553dfbbd5e01` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `ecff96c32abd5f50e2fbbb8fd4ac1d0fc0890e57db208c6bf2dad3c47c281c8f` |
| Grid ordinal | `140` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 1 |
| Total metric improvements | 2 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `f26bbb16c7b6` | `f26bbb16c7b6` | `baseline` | 0.4227 | 0.2130 | 0.2863 | -0.0756 | 0.4227 | 0 | reference | reference |
| Best** | — | `dd6b2601d568` | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | reference | reference |
| 1 | — | `7310593db919` | `7310593db919` | `7310593db919` | 0.4811 | 0.1918 | 0.2655 | -0.0172 | 0.4811 | 0 | 4.1s | 45.45% |
| 2 | — | `991ec364dc7e` | `991ec364dc7e` | `991ec364dc7e` | 0.4735 | 0.1767 | 0.2822 | -0.0248 | 0.4735 | 0 | 3.2s | 36.36% |
| 3 | — | `d16cee8d5acd` | `d16cee8d5acd` | `d16cee8d5acd` | 0.4604 | 0.1623 | 0.2900 | -0.0378 | 0.4604 | 0 | 2.9s | 27.27% |
| 4 | — | `227420ed6c9e` | `227420ed6c9e` | `227420ed6c9e` | 0.4557 | 0.1462 | 0.2892 | -0.0426 | 0.4557 | 0 | 5.7s | 72.73% |
| 5 | — | `06163c156ed7` | `06163c156ed7` | `06163c156ed7` | 0.4491 | 0.1344 | 0.3043 | -0.0491 | 0.4491 | 0 | 5.1s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — radon_boundary

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `dd6b2601d568` | `dd6b2601d568` | 0.2480 | 0.2028 | -0.0452 | Regressed |
| 5 | `dd6b2601d568` | `dd6b2601d568` | 0.4147 | 0.5425 | +0.1278 | Improved |
| 6 | `dd6b2601d568` | `dd6b2601d568` | 0.9782 | 0.9507 | -0.0275 | Regressed |
| 9 | `dd6b2601d568` | `dd6b2601d568` | 0.2130 | 0.4144 | +0.2014 | Improved |
| 10 | `dd6b2601d568` | `dd6b2601d568` | 0.2595 | 0.3809 | +0.1214 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `dd6b2601d568` | `dd6b2601d568` | 1.5s | 18.18% |

Total winner changes: **1**.
Search completed in **8.6s** wall-clock time.

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
- Poor matches (Winner IoU < 0.5000): `3`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `dd6b2601d568` | `dd6b2601d568` | 0.2028 | Poor match; Regressed |
| 6 | `dd6b2601d568` | `dd6b2601d568` | 0.9507 | Regressed |
| 9 | `dd6b2601d568` | `dd6b2601d568` | 0.4144 | Poor match |
| 10 | `dd6b2601d568` | `dd6b2601d568` | 0.3809 | Poor match |

## Calibration Intelligence — radon_boundary

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035620`
- Calibration schema: `1.1`
- Detector: `radon_boundary`
- Detector configuration: `hth-pipeline/config/detectors/radon_boundary.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `dd6b2601d568`
- Recommended parameter short name: `dd6b2601d568`
- Best observed Avg IoU: `0.4983`
- Avg IoU Success: `0.4983`
- Worst Golden Set page (Min IoU): `0.2028`
- Page-to-page StdDev: `0.2509`
- Calibration evidence: `Low`
- Dormant parameters: `angle_limit_degrees, projection_smooth_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 2 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 7m 24s |
| Fully successful parameter sets | 8 (72.7%) |
| Best Avg IoU | 0.4983 |
| Minimum Avg IoU | 0.2986 |
| Avg IoU StdDev | 0.0738 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.5s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 7m 30s | 1.0× |
| Exhaustive | 729 | 100.0% | 7m 30s | 1.0× |
| Non-dormant | 54 | 7.4% | 33.4s | 13.5× |
| Low+ | 54 | 7.4% | 33.4s | 13.5× |
| Moderate+ | 54 | 7.4% | 33.4s | 13.5× |
| Important+ | 18 | 2.5% | 11.1s | 40.5× |
| Critical | 3 | 0.4% | 1.9s | 243.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_peak_prominence` | Critical | 0.9422 | 0.1718 | 33.3% | `1.05` (0.4716), `1.25` (0.4526), `1.6` (0.2998) | current run |
| `edge_percentile` | Important | 0.1278 | 0.0920 | 33.3% | `90` (0.4983), `82` (0.4227), `75` (0.4063) | current run |
| `angle_step_degrees` | Important | 0.0802 | 0.0542 | 50.0% | `1` (0.4605), `0.5` (0.4063) | current run |
| `bbox_padding_fraction` | Moderate | 0.0317 | 0.0286 | 33.3% | `0.016` (0.4334), `0.008` (0.4081), `0` (0.4048) | current run |
| `angle_limit_degrees` | Dormant | 0.0008 | 0.0072 | 50.0% | `8` (0.4227), `4` (0.4155) | current run |
| `projection_smooth_fraction` | Dormant | 0.0008 | 0.0072 | 50.0% | `0.012` (0.4227), `0.006` (0.4155) | current run |

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

`angle_limit_degrees`, `projection_smooth_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `angle_step_degrees` × `bbox_padding_fraction` | 0.1323 | 0.0521 | 11 |
| `minimum_peak_prominence` × `edge_percentile` | 0.9933 | 0.0511 | 11 |
| `angle_step_degrees` × `angle_limit_degrees` | 0.1278 | 0.0477 | 11 |
| `angle_step_degrees` × `projection_smooth_fraction` | 0.1278 | 0.0477 | 11 |
| `minimum_peak_prominence` × `bbox_padding_fraction` | 0.9831 | 0.0409 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.1475 | 0.0000 | 0.2732 | 0.1023 | 72.7% |
| 5 | 0.5174 | 0.4147 | 0.5425 | 0.0352 | 100.0% |
| 6 | 0.9714 | 0.9507 | 0.9871 | 0.0159 | 100.0% |
| 9 | 0.1535 | 0.0000 | 0.4144 | 0.1154 | 72.7% |
| 10 | 0.2907 | 0.0000 | 0.4473 | 0.1845 | 72.7% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="ransac-border-fit-ransac-2"></a>
<details>
<summary><strong>RANSAC Border Fit (`ransac`)</strong></summary>

**Status:** complete

## Run Information — ransac

### Build Provenance

- Run ID: `run-20260820-035646`
- Detector: `ransac`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:46.455809+00:00`
- Finished: `2026-08-20T03:56:49.450486+00:00`
- Wall-clock elapsed: `3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1458`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.75%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
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
| Winner | `HTH-0001` | `f03837084e02` | `7e367fe3bfd5` | `7e367fe3bfd5` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 179 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `7e367fe3bfd5` |
| Parameter Set ID (legacy alias) | `7e367fe3bfd5` |
| Absolute parameter SHA-256 | `86ee436711a970f61c1015f1cfbb0014981cff39793492541ce81c89b5e4527e` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `1fae2a4c2c28979656a81fe9f52981080725d569ad110818560f94e1dffcb4b2` |
| Grid ordinal | `741` |
| Reproducibility | **Fully reproducible** |

#### Exact Parameter Settings

| Parameter | Value |
|---|---|
| `bbox_padding_fraction` | `0.0` |
| `max_trials` | `400` |
| `minimum_bbox_area_fraction` | `0.18` |
| `minimum_mean_inlier_ratio` | `0.45` |
| `minimum_scan_foreground_fraction` | `0.0125` |
| `residual_threshold_fraction` | `0.008` |
| `scan_samples` | `220` |

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
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `7e367fe3bfd5` | `7e367fe3bfd5` | `baseline` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | reference | reference |
| Best** | — | `9647b030702e` | `9647b030702e` | `9647b030702e` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | reference | reference |
| 1 | — | `55356b348cc7` | `55356b348cc7` | `55356b348cc7` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 698 ms | 36.36% |
| 2 | — | `c00244a14f3f` | `c00244a14f3f` | `c00244a14f3f` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 673 ms | 27.27% |
| 3 | — | `6b99d5f448b7` | `6b99d5f448b7` | `6b99d5f448b7` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 870 ms | 45.45% |
| 4 | — | `2080a62a8e2c` | `2080a62a8e2c` | `2080a62a8e2c` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 898 ms | 54.55% |
| 5 | — | `e113c97844b3` | `e113c97844b3` | `e113c97844b3` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 1s | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — ransac

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `7e367fe3bfd5` | `baseline` | 0.0000 | 0.0000 | +0.0000 | Unprocessed |
| 5 | `7e367fe3bfd5` | `baseline` | 0.0000 | 0.0000 | +0.0000 | Unprocessed |
| 6 | `7e367fe3bfd5` | `baseline` | 0.0000 | 0.0000 | +0.0000 | Unprocessed |
| 9 | `7e367fe3bfd5` | `baseline` | 0.0000 | 0.0000 | +0.0000 | Unprocessed |
| 10 | `7e367fe3bfd5` | `baseline` | 0.0000 | 0.0000 | +0.0000 | Unprocessed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **3s** wall-clock time.

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

- Unprocessed pages: `5`
- No polygon found: `0`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `7e367fe3bfd5` | `baseline` | 0.0000 | Unprocessed |
| 5 | `7e367fe3bfd5` | `baseline` | 0.0000 | Unprocessed |
| 6 | `7e367fe3bfd5` | `baseline` | 0.0000 | Unprocessed |
| 9 | `7e367fe3bfd5` | `baseline` | 0.0000 | Unprocessed |
| 10 | `7e367fe3bfd5` | `baseline` | 0.0000 | Unprocessed |

## Calibration Intelligence — ransac

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035646`
- Calibration schema: `1.1`
- Detector: `ransac`
- Detector configuration: `hth-pipeline/config/detectors/ransac.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `7e367fe3bfd5`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.0000`
- Avg IoU Success: `0.0000`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.0000`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `none`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- Calibration did not produce a valid measurement: no evaluated page returned a usable detector candidate.
- The zero Avg IoU values are failure placeholders, not evidence of a flat calibration landscape or dormant parameters.
- Observed detector failure reasons: AttributeError (55).

#### Evidence of ROI

Do not expand or reduce the parameter search yet. Inspect detector inference/debug evidence and restore a valid overlap signal before drawing tuning-ROI conclusions.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 0.8% |
| Est. serial runtime for full parameter set evaluation* | 4m 18s |
| Fully successful parameter sets | 0 (0.0%) |
| Calibration signal | no_valid_measurements |
| Best Avg IoU | 0.0000 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 11 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 11 (100.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

Withheld: effect-size reduction is not meaningful until calibration produces valid positive-overlap measurements.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 10 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="segment-supported-polar-voting-segmentsupportedpolarvote-2"></a>
<details>
<summary><strong>Segment-Supported Polar Voting (`segment_supported_polar_vote`)</strong></summary>

**Status:** complete

## Run Information — segment_supported_polar_vote

### Build Provenance

- Run ID: `run-20260820-035349`
- Detector: `segment_supported_polar_vote`
- Strategy: `exhaustive`
- Pipeline commit: `b432a812fc5d`
- Python: `3.12.0`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:53:49.419955+00:00`
- Finished: `2026-08-20T03:53:56.799319+00:00`
- Wall-clock elapsed: `7.4s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `45361`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — segment_supported_polar_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `abcf4ae9882f` | `4546643c94a4` | `4546643c94a4` | `4546643c94a4` | 0.9470 | 0.8447 | 0.0536 | 0.9470 | 0 | 681 ms |
| Baseline | `HTH-0001` | `abcf4ae9882f` | `92e0158634c3` | `92e0158634c3` | `baseline` | 0.6974 | 0.0000 | 0.3602 | 0.8717 | 1 | 690 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`b432a812fc5d`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `4546643c94a4` |
| Parameter Set ID (legacy alias) | `4546643c94a4` |
| Absolute parameter SHA-256 | `a2e0461565db2bd12a9d15f397a53d241e4232a391a0ec6348aca3ffa6415be6` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 2 |
| Total metric improvements | 4 |
| Parameter sets with improvements | 2 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-multidetector-short-occupancy` | 4 | 96 | 384 | `rh8-al316` | 384 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `92e0158634c3` | `92e0158634c3` | `baseline` | 0.6974 | 0.0000 | 0.3602 | -0.2496 | 0.8717 | 1 | reference | reference |
| Best** | — | `4546643c94a4` | `4546643c94a4` | `4546643c94a4` | 0.9470 | 0.8447 | 0.0536 | +0.0000 | 0.9470 | 0 | reference | reference |
| 1 | — | `c953ea21ba66` | `c953ea21ba66` | `c953ea21ba66` | 0.9236 | 0.8360 | 0.0531 | -0.0235 | 0.9236 | 0 | 5.1s | 63.64% |
| 2 | — | `aba81860e8e3` | `aba81860e8e3` | `aba81860e8e3` | 0.9232 | 0.8360 | 0.0531 | -0.0239 | 0.9232 | 0 | 4.9s | 54.55% |
| 3 | — | `adc752238e83` | `adc752238e83` | `adc752238e83` | 0.9199 | 0.7975 | 0.0675 | -0.0271 | 0.9199 | 0 | 6s | 90.91% |
| 4 | — | `3a37e81cc288` | `3a37e81cc288` | `3a37e81cc288` | 0.9185 | 0.7975 | 0.0667 | -0.0285 | 0.9185 | 0 | 6.1s | 100.00% |
| 5 | — | `1c887604aeaf` | `1c887604aeaf` | `1c887604aeaf` | 0.9178 | 0.7975 | 0.0665 | -0.0292 | 0.9178 | 0 | 5.8s | 72.73% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — segment_supported_polar_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `4546643c94a4` | `4546643c94a4` | 0.7294 | 0.9630 | +0.2336 | Improved |
| 5 | `4546643c94a4` | `4546643c94a4` | 0.0000 | 0.9750 | +0.9750 | Recovered |
| 6 | `4546643c94a4` | `4546643c94a4` | 0.9767 | 1.0000 | +0.0233 | Improved |
| 9 | `4546643c94a4` | `4546643c94a4` | 0.8241 | 0.8447 | +0.0206 | Improved |
| 10 | `4546643c94a4` | `4546643c94a4` | 0.9567 | 0.9525 | -0.0042 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `4546643c94a4` | `4546643c94a4` | 1.4s | 18.18% |

Total winner changes: **1**.
Search completed in **7.4s** wall-clock time.

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
| 10 | `4546643c94a4` | `4546643c94a4` | 0.9525 | Regressed |

## Calibration Intelligence — segment_supported_polar_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035349`
- Calibration schema: `1.1`
- Detector: `segment_supported_polar_vote`
- Detector configuration: `hth-pipeline/config/detectors/segment_supported_polar_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `b432a812fc5dccabd8fc51a0217c42c2625f5b33`
- Source commit: `45654bdf0789c80c5c1a6e453735a40197bc86c0`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `96`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `4546643c94a4`
- Recommended parameter short name: `4546643c94a4`
- Best observed Avg IoU: `0.9470`
- Avg IoU Success: `0.9470`
- Worst Golden Set page (Min IoU): `0.8447`
- Page-to-page StdDev: `0.0536`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 45361 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 8h 34m 7s |
| Fully successful parameter sets | 8 (80.0%) |
| Best Avg IoU | 0.9236 |
| Minimum Avg IoU | 0.6177 |
| Avg IoU StdDev | 0.1066 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.4s (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (20.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 45360 | 100.0% | 8h 34m 13s | 1.0× |
| Exhaustive | 45360 | 100.0% | 8h 34m 13s | 1.0× |
| Non-dormant | 960 | 2.1% | 10m 53s | 47.2× |
| Low+ | 960 | 2.1% | 10m 53s | 47.2× |
| Moderate+ | 960 | 2.1% | 10m 53s | 47.2× |
| Important+ | 960 | 2.1% | 10m 53s | 47.2× |
| Critical | 960 | 2.1% | 10m 53s | 47.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_segment_length_fraction` | Critical | 0.9720 | 0.2658 | 20.0% | `0.03` (0.9234), `0.015` (0.9192), `0.0225` (0.9176) | current run |
| `segment_distance_fraction` | Critical | 0.2596 | 0.1899 | 66.7% | `0.0035` (0.8872), `0.0025` (0.8331), `0.018` (0.6974) | current run |
| `gradient_percentile` | Critical | 0.2022 | 0.1598 | 50.0% | `78` (0.8571), `82` (0.6974) | current run |
| `inner_radius_fraction` | Critical | 0.2022 | 0.1598 | 50.0% | `0.08` (0.8571), `0.12` (0.6974) | current run |
| `minimum_segment_support_fraction` | Critical | 0.2022 | 0.1598 | 50.0% | `0.1` (0.8571), `0.3` (0.6974) | current run |
| `minimum_support_fraction` | Critical | 0.2022 | 0.1598 | 50.0% | `0.2` (0.8571), `0.35` (0.6974) | current run |
| `outer_radius_fraction` | Critical | 0.2022 | 0.1598 | 50.0% | `0.66` (0.8571), `0.7` (0.6974) | current run |
| `ray_count` | Critical | 0.2022 | 0.1598 | 50.0% | `48` (0.8571), `180` (0.6974) | current run |
| `bbox_padding_fraction` | Zombie | 0.0000 | 0.0000 | 100.0% | `0` (0.8412) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_segment_length_fraction` × `segment_distance_fraction` | 1.0000 | 0.0280 | 10 |
| `minimum_segment_length_fraction` × `gradient_percentile` | 1.0000 | 0.0279 | 10 |
| `minimum_segment_length_fraction` × `inner_radius_fraction` | 1.0000 | 0.0279 | 10 |
| `minimum_segment_length_fraction` × `minimum_segment_support_fraction` | 1.0000 | 0.0279 | 10 |
| `minimum_segment_length_fraction` × `minimum_support_fraction` | 1.0000 | 0.0279 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8595 | 0.5828 | 0.9606 | 0.1268 | 100.0% |
| 5 | 0.6483 | 0.0000 | 0.9512 | 0.3800 | 80.0% |
| 6 | 0.9756 | 0.8314 | 0.9951 | 0.0484 | 100.0% |
| 9 | 0.8194 | 0.7975 | 0.8360 | 0.0182 | 100.0% |
| 10 | 0.9029 | 0.8383 | 0.9567 | 0.0266 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="signed-polar-boundary-voting-signedpolarboundaryvote-2"></a>
<details>
<summary><strong>Signed Polar Boundary Voting (`signed_polar_boundary_vote`)</strong></summary>

**Status:** complete

## Run Information — signed_polar_boundary_vote

### Build Provenance

- Run ID: `run-20260820-035646`
- Detector: `signed_polar_boundary_vote`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:56:46.471401+00:00`
- Finished: `2026-08-20T03:56:50.670184+00:00`
- Wall-clock elapsed: `4.2s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `46875`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `0.02%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — signed_polar_boundary_vote

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `a9b4139a73e5` | `8ddbe5f468cd` | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.9717 | 0.9506 | 0.0193 | 0.9717 | 0 | 130 ms |
| Baseline | `HTH-0001` | `a9b4139a73e5` | `839015ab653d` | `839015ab653d` | `baseline` | 0.8483 | 0.7473 | 0.0746 | 0.8483 | 0 | 257 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `8ddbe5f468cd` |
| Parameter Set ID (legacy alias) | `8ddbe5f468cd` |
| Absolute parameter SHA-256 | `d271e15cc6fd4189c8c6d350b04e323d38177022c6d43b7d05f73fcd3a4e1a52` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `839015ab653d` | `839015ab653d` | `baseline` | 0.8483 | 0.7473 | 0.0746 | -0.1235 | 0.8483 | 0 | reference | reference |
| Best** | — | `8ddbe5f468cd` | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.9717 | 0.9506 | 0.0193 | +0.0000 | 0.9717 | 0 | reference | reference |
| 1 | — | `45844b256edd` | `45844b256edd` | `45844b256edd` | 0.8668 | 0.7402 | 0.0759 | -0.1050 | 0.8668 | 0 | 682 ms | 45.45% |
| 2 | — | `78e0a52a25f0` | `78e0a52a25f0` | `78e0a52a25f0` | 0.8664 | 0.7467 | 0.0731 | -0.1053 | 0.8664 | 0 | 933 ms | 72.73% |
| 3 | — | `7da11e12ff8f` | `7da11e12ff8f` | `7da11e12ff8f` | 0.8657 | 0.7532 | 0.0702 | -0.1060 | 0.8657 | 0 | 1.1s | 100.00% |
| 4 | — | `78cd644f1e0b` | `78cd644f1e0b` | `78cd644f1e0b` | 0.8438 | 0.7532 | 0.0581 | -0.1279 | 0.8438 | 0 | 1.1s | 90.91% |
| 5 | — | `b6bfa241e517` | `b6bfa241e517` | `b6bfa241e517` | 0.8431 | 0.7467 | 0.0602 | -0.1286 | 0.8431 | 0 | 832 ms | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — signed_polar_boundary_vote

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.7957 | 0.9684 | +0.1727 | Improved |
| 5 | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.8951 | 0.9930 | +0.0979 | Improved |
| 6 | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.9607 | 0.9952 | +0.0344 | Improved |
| 9 | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.7473 | 0.9516 | +0.2042 | Improved |
| 10 | `8ddbe5f468cd` | `8ddbe5f468cd` | 0.8426 | 0.9506 | +0.1080 | Improved |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `8ddbe5f468cd` | `8ddbe5f468cd` | 388 ms | 18.18% |

Total winner changes: **1**.
Search completed in **4.2s** wall-clock time.

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

## Calibration Intelligence — signed_polar_boundary_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035646`
- Calibration schema: `1.1`
- Detector: `signed_polar_boundary_vote`
- Detector configuration: `hth-pipeline/config/detectors/signed_polar_boundary_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `8ddbe5f468cd`
- Recommended parameter short name: `8ddbe5f468cd`
- Best observed Avg IoU: `0.9717`
- Avg IoU Success: `0.9717`
- Worst Golden Set page (Min IoU): `0.9506`
- Page-to-page StdDev: `0.0193`
- Calibration evidence: `Medium`
- Dormant parameters: `inner_radius_fraction, minimum_support_fraction, outer_radius_fraction, ray_count, bbox_padding_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 5 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 46875 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 1h 41m 2s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8668 |
| Minimum Avg IoU | 0.8229 |
| Avg IoU StdDev | 0.0166 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 388 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 2 (20.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 46875 | 100.0% | 1h 41m 3s | 1.0× |
| Exhaustive | 46875 | 100.0% | 1h 41m 3s | 1.0× |
| Non-dormant | 3 | 0.0% | 388 ms | 15625.0× |
| Low+ | 3 | 0.0% | 388 ms | 15625.0× |
| Moderate+ | 3 | 0.0% | 388 ms | 15625.0× |
| Important+ | 3 | 0.0% | 388 ms | 15625.0× |
| Critical | 3 | 0.0% | 388 ms | 15625.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `polarity` | Critical | 0.8340 | 0.0364 | 33.3% | `absolute` (0.8663), `dark_inside` (0.8431), `bright_inside` (0.8299) | current run |
| `inner_radius_fraction` | Dormant | 0.0050 | 0.0039 | 50.0% | `0.12` (0.8483), `0.1` (0.8444) | current run |
| `minimum_support_fraction` | Dormant | 0.0050 | 0.0039 | 50.0% | `0.35` (0.8483), `0.2` (0.8444) | current run |
| `outer_radius_fraction` | Dormant | 0.0050 | 0.0039 | 50.0% | `0.7` (0.8483), `0.45` (0.8444) | current run |
| `ray_count` | Dormant | 0.0050 | 0.0039 | 50.0% | `180` (0.8483), `72` (0.8444) | current run |
| `bbox_padding_fraction` | Dormant | 0.0003 | 0.0007 | 66.7% | `0` (0.8451), `0.004` (0.8447), `0.002` (0.8444) | current run |
| `gradient_percentile` | Zombie | 0.0000 | 0.0000 | 100.0% | `82` (0.8448) | current run |

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

`inner_radius_fraction`, `minimum_support_fraction`, `outer_radius_fraction`, `ray_count`, `bbox_padding_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `polarity` × `inner_radius_fraction` | 0.9990 | 0.1650 | 10 |
| `polarity` × `minimum_support_fraction` | 0.9990 | 0.1650 | 10 |
| `polarity` × `outer_radius_fraction` | 0.9990 | 0.1650 | 10 |
| `polarity` × `ray_count` | 0.9990 | 0.1650 | 10 |
| `polarity` × `bbox_padding_fraction` | 0.8827 | 0.0487 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8526 | 0.7957 | 0.9006 | 0.0342 | 100.0% |
| 5 | 0.7589 | 0.7313 | 0.8951 | 0.0459 | 100.0% |
| 6 | 0.9381 | 0.9327 | 0.9607 | 0.0086 | 100.0% |
| 9 | 0.8084 | 0.7473 | 0.8681 | 0.0448 | 100.0% |
| 10 | 0.8658 | 0.8232 | 0.9262 | 0.0398 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="star-convex-boundary-optimization-starconvex-2"></a>
<details>
<summary><strong>Star-Convex Boundary Optimization (`star_convex`)</strong></summary>

**Status:** complete

## Run Information — star_convex

### Build Provenance

- Run ID: `run-20260820-035711`
- Detector: `star_convex`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:57:11.457793+00:00`
- Finished: `2026-08-20T03:57:12.232366+00:00`
- Wall-clock elapsed: `775 ms`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `729`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `1.51%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — star_convex

### Result

| Result | Golden Set ID | Detector Config ID* | Family ID** | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `HTH-0001` | `7e9dbd5aa9f5` | `024732f5e631` | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | 0.8179 | 0 | 85 ms |
| Baseline | `HTH-0001` | `7e9dbd5aa9f5` | `f914375ada78` | `f914375ada78` | `baseline` | 0.7756 | 0.3969 | 0.2448 | 0.7756 | 0 | 65 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `024732f5e631` |
| Parameter Set ID (legacy alias) | `024732f5e631` |
| Absolute parameter SHA-256 | `afe359fabb847fffccd2d958ad2a40549c3fa8ea16a39b11c5e76362e4805906` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `cd0f10a566e7e5d6041a22105b54596ba9376cec24b532b3c72458adec6768cc` |
| Grid ordinal | `666` |
| Reproducibility | **Fully reproducible** |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 3 |
| StdDev improvements | 2 |
| Total metric improvements | 6 |
| Parameter sets with improvements | 3 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `f914375ada78` | `f914375ada78` | `baseline` | 0.7756 | 0.3969 | 0.2448 | -0.0422 | 0.7756 | 0 | reference | reference |
| Best** | — | `024732f5e631` | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | +0.0000 | 0.8179 | 0 | reference | reference |
| 1 | — | `095537f3b0cd` | `095537f3b0cd` | `095537f3b0cd` | 0.7981 | 0.5414 | 0.1935 | -0.0198 | 0.7981 | 0 | 225 ms | 27.27% |
| 2 | — | `0d7165269fe3` | `0d7165269fe3` | `0d7165269fe3` | 0.7967 | 0.5268 | 0.2043 | -0.0212 | 0.7967 | 0 | 228 ms | 36.36% |
| 3 | — | `ba17416e0dda` | `ba17416e0dda` | `ba17416e0dda` | 0.7902 | 0.5579 | 0.1749 | -0.0277 | 0.7902 | 0 | 273 ms | 45.45% |
| 4 | — | `53cf691df4c6` | `53cf691df4c6` | `53cf691df4c6` | 0.7662 | 0.3900 | 0.2364 | -0.0517 | 0.7662 | 0 | 375 ms | 90.91% |
| 5 | — | `6f61e79a4b7e` | `6f61e79a4b7e` | `6f61e79a4b7e` | 0.7650 | 0.3960 | 0.2416 | -0.0529 | 0.7650 | 0 | 322 ms | 63.64% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — star_convex

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `024732f5e631` | `024732f5e631` | 0.9881 | 0.9761 | -0.0120 | Regressed |
| 5 | `024732f5e631` | `024732f5e631` | 0.5706 | 0.5367 | -0.0339 | Regressed |
| 6 | `024732f5e631` | `024732f5e631` | 0.3969 | 0.6626 | +0.2657 | Improved |
| 9 | `024732f5e631` | `024732f5e631` | 0.9542 | 0.9523 | -0.0020 | Regressed |
| 10 | `024732f5e631` | `024732f5e631` | 0.9683 | 0.9617 | -0.0066 | Regressed |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `024732f5e631` | `024732f5e631` | 151 ms | 18.18% |

Total winner changes: **1**.
Search completed in **775 ms** wall-clock time.

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
- Regressed pages (Δ IoU < -0.0010): `4`

#### Affected Pages

| Golden Set Page | Family ID | Parameter Set ID | Winner IoU | Problem |
|---:|---|---|---:|---|
| 1 | `024732f5e631` | `024732f5e631` | 0.9761 | Regressed |
| 5 | `024732f5e631` | `024732f5e631` | 0.5367 | Regressed |
| 9 | `024732f5e631` | `024732f5e631` | 0.9523 | Regressed |
| 10 | `024732f5e631` | `024732f5e631` | 0.9617 | Regressed |

## Calibration Intelligence — star_convex

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035711`
- Calibration schema: `1.1`
- Detector: `star_convex`
- Detector configuration: `hth-pipeline/config/detectors/star_convex.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `024732f5e631`
- Recommended parameter short name: `024732f5e631`
- Best observed Avg IoU: `0.8179`
- Avg IoU Success: `0.8179`
- Worst Golden Set page (Min IoU): `0.5367`
- Page-to-page StdDev: `0.1827`
- Calibration evidence: `Medium`
- Dormant parameters: `maximum_radius_fraction`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 1m 1s |
| Fully successful parameter sets | 11 (100.0%) |
| Best Avg IoU | 0.8179 |
| Minimum Avg IoU | 0.7597 |
| Avg IoU StdDev | 0.0191 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 151 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 1m 2s | 1.0× |
| Exhaustive | 729 | 100.0% | 1m 2s | 1.0× |
| Non-dormant | 243 | 33.3% | 20.5s | 3.0× |
| Low+ | 243 | 33.3% | 20.5s | 3.0× |
| Moderate+ | 243 | 33.3% | 20.5s | 3.0× |
| Important+ | 243 | 33.3% | 20.5s | 3.0× |
| Critical | 81 | 11.1% | 6.8s | 9.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `smoothing_window` | Critical | 0.8478 | 0.0376 | 33.3% | `1` (0.8007), `5` (0.7651), `9` (0.7631) | current run |
| `minimum_radius_fraction` | Critical | 0.4494 | 0.0447 | 33.3% | `0.16` (0.8179), `0.1` (0.7756), `0.05` (0.7732) | current run |
| `minimum_support_fraction` | Critical | 0.4494 | 0.0447 | 33.3% | `0.7` (0.8179), `0.55` (0.7756), `0.4` (0.7732) | current run |
| `ray_count` | Critical | 0.4494 | 0.0447 | 33.3% | `360` (0.8179), `180` (0.7756), `90` (0.7732) | current run |
| `bbox_padding_fraction` | Important | 0.0634 | 0.0115 | 33.3% | `0` (0.7822), `0.008` (0.7764), `0.016` (0.7707) | current run |
| `maximum_radius_fraction` | Dormant | 0.0010 | 0.0021 | 50.0% | `0.6` (0.7777), `0.72` (0.7756) | current run |

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

`maximum_radius_fraction`.

Dormant and Zombie are measured effect-size classes scoped to this Golden Set/grid. Zombie parameters may be isolated from normal search only when retained audited domains support explicit revalidation.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `smoothing_window` × `minimum_radius_fraction` | 0.9832 | 0.1354 | 11 |
| `smoothing_window` × `minimum_support_fraction` | 0.9832 | 0.1354 | 11 |
| `smoothing_window` × `ray_count` | 0.9832 | 0.1354 | 11 |
| `smoothing_window` × `bbox_padding_fraction` | 0.9131 | 0.0653 | 11 |
| `smoothing_window` × `maximum_radius_fraction` | 0.8850 | 0.0373 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9730 | 0.9414 | 0.9881 | 0.0134 | 100.0% |
| 5 | 0.5707 | 0.5353 | 0.6026 | 0.0210 | 100.0% |
| 6 | 0.4581 | 0.3702 | 0.6626 | 0.0928 | 100.0% |
| 9 | 0.9323 | 0.8941 | 0.9591 | 0.0240 | 100.0% |
| 10 | 0.9534 | 0.9260 | 0.9726 | 0.0174 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="text-flow-envelope-textflow-2"></a>
<details>
<summary><strong>Text Flow Envelope (`text_flow`)</strong></summary>

**Status:** complete

## Run Information — text_flow

### Build Provenance

- Run ID: `run-20260820-035705`
- Detector: `text_flow`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:57:05.884712+00:00`
- Finished: `2026-08-20T03:57:06.854064+00:00`
- Wall-clock elapsed: `969 ms`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `729`
- Parameter sets evaluated: `11`
- Evaluated sets (% of all possible parameter sets): `1.51%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
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
| Winner | `HTH-0001` | `4ec581e01b4b` | `a2bbfc162f9e` | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | 0.8170 | 4 | 44 ms |
| Baseline | `HTH-0001` | `4ec581e01b4b` | `cd4fbe8ec7d8` | `cd4fbe8ec7d8` | `baseline` | 0.1596 | 0.0000 | 0.3191 | 0.7978 | 4 | 49 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `a2bbfc162f9e` |
| Parameter Set ID (legacy alias) | `a2bbfc162f9e` |
| Absolute parameter SHA-256 | `51558eee645b61618f44e6a1c7b123c2ec7ea681f038f62fb3be19a67e60d957` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `4ba1a84530cf9ff3ddd49fe60cdbcd5175403dce200ecd14c52805d4f0fcdf1a` |
| Grid ordinal | `29` |
| Reproducibility | **Fully reproducible** |

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
| StdDev improvements | 2 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 3 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `cd4fbe8ec7d8` | `cd4fbe8ec7d8` | `baseline` | 0.1596 | 0.0000 | 0.3191 | -0.0038 | 0.7978 | 4 | reference | reference |
| Best** | — | `a2bbfc162f9e` | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | reference | reference |
| 1 | — | `00521cb468c7` | `00521cb468c7` | `00521cb468c7` | 0.1158 | 0.0000 | 0.2316 | -0.0476 | 0.5791 | 4 | 204 ms | 36.36% |
| 2 | — | `1c0b5b0e68d2` | `1c0b5b0e68d2` | `1c0b5b0e68d2` | 0.1158 | 0.0000 | 0.2316 | -0.0476 | 0.5791 | 4 | 322 ms | 72.73% |
| 3 | — | `755592f2b19d` | `755592f2b19d` | `755592f2b19d` | 0.1112 | 0.0000 | 0.2223 | -0.0522 | 0.5558 | 4 | 213 ms | 45.45% |
| 4 | — | `aed529db32b1` | `aed529db32b1` | `aed529db32b1` | 0.1112 | 0.0000 | 0.2223 | -0.0522 | 0.5558 | 4 | 301 ms | 63.64% |
| 5 | — | `8cecb4ddab71` | `8cecb4ddab71` | `8cecb4ddab71` | 0.1068 | 0.0000 | 0.2135 | -0.0566 | 0.5338 | 4 | 153 ms | 27.27% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — text_flow

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.7978 | 0.8170 | +0.0192 | Improved |
| 9 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| 1 (final) | `a2bbfc162f9e` | `a2bbfc162f9e` | 95 ms | 18.18% |

Total winner changes: **1**.
Search completed in **969 ms** wall-clock time.

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
| 1 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 5 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 9 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 10 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.0000 | No polygon found |

## Calibration Intelligence — text_flow

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035705`
- Calibration schema: `1.1`
- Detector: `text_flow`
- Detector configuration: `hth-pipeline/config/detectors/text_flow.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `a2bbfc162f9e`
- Recommended parameter short name: `a2bbfc162f9e`
- Best observed Avg IoU: `0.1634`
- Avg IoU Success: `0.8170`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3268`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `critical, exhaustive, exhaustive_with_zombies, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 11 of 11 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 729 |
| Parameter sets evaluated | 11 |
| Evaluated sets (% of all possible parameter sets) | 1.5% |
| Est. serial runtime for full parameter set evaluation* | 31.4s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.1634 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0582 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 95 ms (18% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (9.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (9.1%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive-with-zombies | 729 | 100.0% | 31.8s | 1.0× |
| Exhaustive | 729 | 100.0% | 31.8s | 1.0× |
| Non-dormant | 144 | 19.8% | 6.3s | 5.1× |
| Low+ | 144 | 19.8% | 6.3s | 5.1× |
| Moderate+ | 144 | 19.8% | 6.3s | 5.1× |
| Important+ | 48 | 6.6% | 2.1s | 15.2× |
| Critical | 48 | 6.6% | 2.1s | 15.2× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

*Contracted-search note: every excluded parameter is pinned to its detector baseline value, so reduced-grid parameter identities are stable across builds. Under the current HTH classification thresholds, `Non-dormant` and `Low+` intentionally resolve to the same parameter domain; both labels are retained for compatibility and possible future policy differentiation.*

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values | Evidence |
|---|---|---:|---:|---:|---|---|
| `minimum_text_coverage_fraction` | Critical | 0.8962 | 0.1243 | 33.3% | `0.04` (0.1243), `0.08` (0.1233), `0.14` (0.0000) | current run |
| `line_join_fraction` | Critical | 0.3343 | 0.0873 | 50.0% | `0.03` (0.1615), `0.018` (0.0742) | current run |
| `maximum_component_area_fraction` | Critical | 0.1425 | 0.0765 | 50.0% | `0.01` (0.1596), `0.005` (0.0831) | current run |
| `minimum_component_area_fraction` | Critical | 0.1425 | 0.0765 | 50.0% | `2e-05` (0.1596), `1e-05` (0.0831) | current run |
| `minimum_line_count` | Critical | 0.1425 | 0.0765 | 50.0% | `3` (0.1596), `2` (0.0831) | current run |
| `bbox_padding_fraction` | Moderate | 0.0399 | 0.0276 | 33.3% | `0.04` (0.0988), `0.02` (0.0955), `0.01` (0.0712) | current run |

#### Parameter Classification

| Classification | Canonical HTH criterion | Engineering interpretation |
|---|---|---|
| Zombie | η² < 0.0005 **and** Avg-IoU range < 0.0005 | Practically indistinguishable from zero in this characterized grid |
| Dormant | η² < 0.005, excluding Zombie | Measurable or potentially measurable, but operationally negligible |
| Low | 0.005 ≤ η² < 0.02 | Small effect |
| Moderate | 0.02 ≤ η² < 0.06 | Meaningful secondary influence |
| Important | 0.06 ≤ η² < 0.14 | Strong influence |
| Critical | η² ≥ 0.14 | Dominant influence |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_text_coverage_fraction` × `line_join_fraction` | 0.9978 | 0.1016 | 11 |
| `minimum_text_coverage_fraction` × `maximum_component_area_fraction` | 0.9431 | 0.0469 | 11 |
| `minimum_text_coverage_fraction` × `minimum_component_area_fraction` | 0.9431 | 0.0469 | 11 |
| `minimum_text_coverage_fraction` × `minimum_line_count` | 0.9431 | 0.0469 | 11 |
| `maximum_component_area_fraction` × `bbox_padding_fraction` | 0.1867 | 0.0442 | 11 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 6 | 0.4502 | 0.0000 | 0.8170 | 0.2912 | 72.7% |
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

- Run ID: `run-20260820-035707`
- Detector: `whitespace_frame`
- Strategy: `exhaustive`
- Pipeline commit: `74333cc2d904`
- Python: `3.12.14`
- OpenCV: `4.14.0`
- Started: `2026-08-20T03:57:07.705379+00:00`
- Finished: `2026-08-20T03:57:08.457481+00:00`
- Wall-clock elapsed: `752 ms`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `730`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `1.37%`
- Configured named profiles: `baseline`

### Outputs

- `RUN-INFO.json` — present
- `parameters.json` — present
- `parameter-provenance.json` — missing
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
| Winner | `HTH-0001` | `485dbaeaff38` | `9ef715dda063` | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 26 ms |

\* **Detector Config ID** is the short SHA-256 of the detector configuration used by this run. It identifies the declared detector settings, while detector implementation identity is pinned by the run's pipeline/source revision (`74333cc2d904`). Exact regression-result reproducibility requires the tuple **detector implementation + parameter set + Golden Set**; matching a parameter SHA alone does not imply identical results across detector-code revisions.

\*\* **Family ID** is the Parameter Set Equivalence Family ID. It is additive provenance: exact Parameter Set IDs remain unchanged. Enrolled equivalence dimensions are replaced only in the hashing payload by `__HTH_EQUIVALENCE_FAMILY_ID__`; that sentinel is never executable detector input. Different exact sets may share a Family ID only through those durably enrolled dimensions.

### Parameter Set Details

This is the exact winning parameter configuration. The short Parameter Set ID is a legacy convenience alias; the full SHA-256 identity is authoritative.

| Identity field | Value |
|---|---|
| Parameter Set Equivalence Family ID | `9ef715dda063` |
| Parameter Set ID (legacy alias) | `9ef715dda063` |
| Absolute parameter SHA-256 | `b8304ad7bfd2854c639b6513841402c045fa9c65d22b6b681e39144f07a7004c` |
| Identity schema | `1` |
| Parameter schema | `1` |
| Grid SHA-256 | `not a grid member` |
| Grid ordinal | `not a grid member` |
| Reproducibility | **Fully reproducible** |

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
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000936` | 8 |

### Top Parameter Sets

| Rank | Last Build | Family ID | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Baseline* | — | `9ef715dda063` | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | reference | reference |
| 1 | — | `f7e0d706deeb` | `f7e0d706deeb` | `f7e0d706deeb` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 64 ms | 20.00% |
| 2 | — | `93f2d7e9ecfa` | `93f2d7e9ecfa` | `93f2d7e9ecfa` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 94 ms | 40.00% |
| 3 | — | `f2b82f6c9e72` | `f2b82f6c9e72` | `f2b82f6c9e72` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 83 ms | 30.00% |
| 4 | — | `051f77f76305` | `051f77f76305` | `051f77f76305` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 106 ms | 50.00% |
| 5 | — | `ecc21ea1857a` | `ecc21ea1857a` | `ecc21ea1857a` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 142 ms | 70.00% |

\* **Baseline** is the detector's default parameter-set configuration.
\*\* **Best** is the historic best-known compatible parameter set prior to this regression run.

**Last Build** is the most recent known prior build that evaluated the exact absolute parameter identity; the current manifest build is intentionally excluded.

Baseline and Best are mandatory evaluated references in every regression and are not assigned numeric search ranks. If either exact reference parameter set is also present in the requested search, it is evaluated once and shown only as the reference row.

## Page Analysis — whitespace_frame

### Golden Set Winner Summary

| Golden Set Page | Family ID | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---|---:|---:|---:|---|
| 1 | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Family ID | Parameter Set ID | Search Time | % Search |
|---:|---|---|---:|---:|
| — | no history | no history | no history | no history |

Total winner changes: **0**.
Search completed in **752 ms** wall-clock time.

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
| 1 | `9ef715dda063` | `baseline` | 0.0000 | No polygon found |
| 5 | `9ef715dda063` | `baseline` | 0.0000 | No polygon found |
| 6 | `9ef715dda063` | `baseline` | 0.0000 | No polygon found |
| 9 | `9ef715dda063` | `baseline` | 0.0000 | No polygon found |
| 10 | `9ef715dda063` | `baseline` | 0.0000 | No polygon found |

## Calibration Intelligence — whitespace_frame

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260820-035707`
- Calibration schema: `1.1`
- Detector: `whitespace_frame`
- Detector configuration: `hth-pipeline/config/detectors/whitespace_frame.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `74333cc2d9046f53acffa85540a2794e65cdf656`
- Source commit: `64f5f3fa38718b5808b2c6a2471e9904d8634477`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

**Search strategy legend:** `exhaustive` covers the current live declared Cartesian space and keeps configured zombie parameters pinned; `exhaustive-with-zombies` deliberately restores retained zombie value domains for revalidation. Effect-size strategies operate on the current live space.

### Detector-Selection Intelligence

- Recommended parameter set: `9ef715dda063`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.0000`
- Avg IoU Success: `0.0000`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.0000`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Configured zombie parameters: `none`
- Available domain spaces: `none`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- Calibration did not produce a valid measurement: no evaluated page returned a usable detector candidate.
- The zero Avg IoU values are failure placeholders, not evidence of a flat calibration landscape or dormant parameters.
- Observed detector failure reasons: border_not_background (50).

#### Evidence of ROI

Do not expand or reduce the parameter search yet. Inspect detector inference/debug evidence and restore a valid overlap signal before drawing tuning-ROI conclusions.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 730 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 1.4% |
| Est. serial runtime for full parameter set evaluation* | 18.7s |
| Fully successful parameter sets | 0 (0.0%) |
| Calibration signal | no_valid_measurements |
| Best Avg IoU | 0.0000 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.0000 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 10 (100.0%) |
| Equivalent-best configurations (within 0.0001) | 10 (100.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

Withheld: effect-size reduction is not meaningful until calibration produces valid positive-overlap measurements.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

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
- Results commit: [7e7b3e8c70ab792907b2748db67088db033f9203](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/commit/7e7b3e8c70ab792907b2748db67088db033f9203).
- Workflow run: [Open workflow run](https://github.com/dlstupka/hth/actions/runs/32330144462).
- Pipeline repository: [dlstupka/hth](https://github.com/dlstupka/hth).
- Results repository: [dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results).
- Calibration index: [calibration-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/7e7b3e8c70ab792907b2748db67088db033f9203/calibration-index.json).
- Runtime index: [runtime-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/7e7b3e8c70ab792907b2748db67088db033f9203/runtime-index.json).
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