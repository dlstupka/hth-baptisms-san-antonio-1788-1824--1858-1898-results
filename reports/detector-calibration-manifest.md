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
    - [Polar Boundary Voting (`polar_boundary_vote`)](#polar-boundary-voting-polarboundaryvote)
    - [Adaptive Radial Edge Search (`adaptive_radial_edge`)](#adaptive-radial-edge-search-adaptiveradialedge)
    - [Radial Edge Search (`radial_edge`)](#radial-edge-search-radialedge)
    - [Gradient Boundary Voting (`gradient_vote`)](#gradient-boundary-voting-gradientvote)
    - [GrabCut Segmentation (`grabcut`)](#grabcut-segmentation-grabcut)
    - [Contour Quadrilateral (`contour_quad`)](#contour-quadrilateral-contourquad)
    - [Cross-Edge Contour (`cross_edge_contour`)](#cross-edge-contour-crossedgecontour)
    - [Contour + Projection (`contour_projection`)](#contour-projection-contourprojection)
    - [Edge-Supported Contour (`edge_contour`)](#edge-supported-contour-edgecontour)
    - [Contour + GrabCut (`contour_grabcut`)](#contour-grabcut-contourgrabcut)
    - [Contour + Components (`contour_components`)](#contour-components-contourcomponents)
    - [Contour Envelope (`contour`)](#contour-envelope-contour)
    - [Distance Transform Detector (`distance_transform`)](#distance-transform-detector-distancetransform)
    - [Star-Convex Boundary Optimization (`star_convex`)](#star-convex-boundary-optimization-starconvex)
    - [GrabCut + Contour (`grabcut_contour`)](#grabcut-contour-grabcutcontour)
    - [Connected Components (`components`)](#connected-components-components)
    - [RANSAC Border Fit (`ransac`)](#ransac-border-fit-ransac)
    - [Line Segment Detector (`lsd`)](#line-segment-detector-lsd)
    - [Convex Hull Detector (`convex_hull`)](#convex-hull-detector-convexhull)
    - [Border Energy Validator (`border_energy`)](#border-energy-validator-borderenergy)
    - [Distance-Transform Rectangle Proposal (`distance_transform_rect`)](#distance-transform-rectangle-proposal-distancetransformrect)
    - [Hough Line Borders (`hough`)](#hough-line-borders-hough)
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
    - [Adaptive Radial Edge Search (`adaptive_radial_edge`)](#adaptive-radial-edge-search-adaptiveradialedge-2)
    - [Border Energy Validator (`border_energy`)](#border-energy-validator-borderenergy-2)
    - [Connected Components (`components`)](#connected-components-components-2)
    - [Consensus Quadrilateral (`consensus_quad`)](#consensus-quadrilateral-consensusquad-2)
    - [Contour Envelope (`contour`)](#contour-envelope-contour-2)
    - [Contour + Components (`contour_components`)](#contour-components-contourcomponents-2)
    - [Contour + GrabCut (`contour_grabcut`)](#contour-grabcut-contourgrabcut-2)
    - [Contour + Projection (`contour_projection`)](#contour-projection-contourprojection-2)
    - [Contour Quadrilateral (`contour_quad`)](#contour-quadrilateral-contourquad-2)
    - [Convex Hull Detector (`convex_hull`)](#convex-hull-detector-convexhull-2)
    - [Cross-Edge Contour (`cross_edge_contour`)](#cross-edge-contour-crossedgecontour-2)
    - [Distance Transform Detector (`distance_transform`)](#distance-transform-detector-distancetransform-2)
    - [Distance-Transform Rectangle Proposal (`distance_transform_rect`)](#distance-transform-rectangle-proposal-distancetransformrect-2)
    - [Edge-Supported Contour (`edge_contour`)](#edge-supported-contour-edgecontour-2)
    - [GrabCut Segmentation (`grabcut`)](#grabcut-segmentation-grabcut-2)
    - [GrabCut + Contour (`grabcut_contour`)](#grabcut-contour-grabcutcontour-2)
    - [Gradient Boundary Voting (`gradient_vote`)](#gradient-boundary-voting-gradientvote-2)
    - [Hough Line Borders (`hough`)](#hough-line-borders-hough-2)
    - [Joint Rectangle Voting (`joint_rectangle_vote`)](#joint-rectangle-voting-jointrectanglevote-2)
    - [Line Segment Detector (`lsd`)](#line-segment-detector-lsd-2)
    - [Polar Boundary Voting (`polar_boundary_vote`)](#polar-boundary-voting-polarboundaryvote-2)
    - [Radial Edge Search (`radial_edge`)](#radial-edge-search-radialedge-2)
    - [Radon Boundary Projection (`radon_boundary`)](#radon-boundary-projection-radonboundary-2)
    - [RANSAC Border Fit (`ransac`)](#ransac-border-fit-ransac-2)
    - [Star-Convex Boundary Optimization (`star_convex`)](#star-convex-boundary-optimization-starconvex-2)
    - [Text Flow Envelope (`text_flow`)](#text-flow-envelope-textflow-2)
    - [Whitespace Frame (`whitespace_frame`)](#whitespace-frame-whitespaceframe-2)
- [Engineering Continuous Improvement](#engineering-continuous-improvement)
  - [Calibration Intelligence Persistence](#calibration-intelligence-persistence)
  - [Runtime Intelligence Persistence](#runtime-intelligence-persistence)
  - [Engineering Notes](#engineering-notes)

</details>


**Detectors evaluated:** 27

<a id="source-document"></a>
## Source document

- **Document:** Baptisms: San Antonio. Baptism Records 1788–1824, 1858–1898
- **Images:** 929

[↑ Back to Navigation](#table-of-contents)

<a id="detector-recommendation-for-this-golden-set"></a>
## Detector Recommendation for this Golden Set

- **Recommended detector:** Polar Boundary Voting
- **Detector short name:** Polar Boundary Vote
- **Detector ID:** `polar_boundary_vote`
- **Best observed Avg IoU:** `0.9678`
- **Worst Golden Set page (Min IoU):** `0.9425`
- **Page-to-page StdDev:** `0.0182`
- **Role:** `Generator`
- **Engineering Recommendation:** Retain this detector as the current Golden Set recommendation. Additional tuning should be driven by unresolved page failures, late winner changes, or a plausible untested parameter region rather than by search expansion alone.

**Recommendation basis:**

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 2 of 6 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

This recommendation is specific to the evaluated Golden Set and parameter grid and should be revisited when the Golden Set, parameter grid, or source document changes.

[↑ Back to Navigation](#table-of-contents)

<a id="ranked-detector-smoke-test-results"></a>
## Ranked Detector Smoke Test Results

| Rank | Detector | Detector ID | Role | Golden Set ID | Status | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Parameter Sets | Eval Rate | Doc Time | Run Elapsed |
|---:|---|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | Polar Boundary Voting | `polar_boundary_vote` | Generator | `HTH-0001` | complete | `cd967f93437d` | `cd967f93437d` | 0.9678 | 0.9425 | 0.0182 | 0.9678 | 0 | 729 | 1.278 pg/s | 12m 7s | 8.9s |
| 2 | Adaptive Radial Edge Search | `adaptive_radial_edge` | Generator | `HTH-0001` | complete | `5010d5b46516` | `5010d5b46516` | 0.9599 | 0.9440 | 0.0114 | 0.9599 | 0 | 6562 | 0.0853 pg/s | 3h 1m 27s | 45m 27s |
| 3 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | complete | `5f802d0c469d` | `5f802d0c469d` | 0.9547 | 0.9432 | 0.0104 | 0.9547 | 0 | 6562 | 10.64 pg/s | 1m 27s | 3m 52s |
| 4 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | complete | `736327fcfb98` | `736327fcfb98` | 0.9250 | 0.7525 | 0.0869 | 0.9250 | 0 | 6562 | 18.38 pg/s | 50.5s | 6.4s |
| 5 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | complete | `f33aa4421393` | `f33aa4421393` | 0.9137 | 0.7378 | 0.0886 | 0.9137 | 0 | 13122 | 0.1448 pg/s | 1h 46m 54s | 6h 23m 40s |
| 6 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | complete | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | 0.8874 | 0 | 1062882 | 12.52 pg/s | 1m 14s | 10h 40m 34s |
| 7 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | complete | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 6562 | 23.42 pg/s | 39.7s | 3m 28s |
| 8 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | complete | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 6562 | 10.92 pg/s | 1m 25s | 7m 22s |
| 9 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | complete | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 13123 | 4.823 pg/s | 3m 13s | 1m 8s |
| 10 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | complete | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 6562 | 0.1764 pg/s | 1h 27m 47s | 3h 9m 30s |
| 11 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | complete | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | 19684 | 83.60 pg/s | 11.1s | 3m 48s |
| 12 | Contour Envelope | `contour` | Generator | `HTH-0001` | complete | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | 1458 | 145.59 pg/s | 6.4s | 4.6s |
| 13 | Distance Transform Detector | `distance_transform` | Generator | `HTH-0001` | complete | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | 0.8388 | 0 | 2187 | 2.026 pg/s | 7m 39s | 28.6s |
| 14 | Star-Convex Boundary Optimization | `star_convex` | Generator | `HTH-0001` | complete | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | 0.8179 | 0 | 729 | 1.314 pg/s | 11m 47s | 7.2s |
| 15 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | complete | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 10 | 0.0716 pg/s | 3h 36m 9s | 4m 14s |
| 16 | Connected Components | `components` | Generator | `HTH-0001` | complete | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | 0.7897 | 0 | 19683 | 237.69 pg/s | 3.9s | 40.8s |
| 17 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | complete | `9647b030702e` | `9647b030702e` | 0.7541 | 0.3558 | 0.2541 | 0.7541 | 0 | 1458 | 4.771 pg/s | 3m 15s | 1m 31s |
| 18 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | complete | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | 0.9222 | 1 | 2187 | 13.20 pg/s | 1m 10s | 59s |
| 19 | Convex Hull Detector | `convex_hull` | Generator | `HTH-0001` | complete | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | 0.9156 | 1 | 2187 | 28.47 pg/s | 32.6s | 2s |
| 20 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | complete | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | 0.9063 | 1 | 6562 | 9.159 pg/s | 1m 41s | 3m 59s |
| 21 | Distance-Transform Rectangle Proposal | `distance_transform_rect` | Generator | `HTH-0001` | complete | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | 0.7243 | 0 | 729 | 12.21 pg/s | 1m 16s | 1.2s |
| 22 | Hough Line Borders | `hough` | Generator | `HTH-0001` | complete | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | 0.7563 | 1 | 2188 | 3.685 pg/s | 4m 12s | 3m 4s |
| 23 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | complete | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | 0.9213 | 2 | 243 | 3.487 pg/s | 4m 26s | 21.3s |
| 24 | Radon Boundary Projection | `radon_boundary` | Generator | `HTH-0001` | complete | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | 0.4983 | 0 | 729 | 2.105 pg/s | 7m 21s | 10.4s |
| 25 | Joint Rectangle Voting | `joint_rectangle_vote` | Generator | `HTH-0001` | complete | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | 0.9899 | 4 | 2187 | 2.223 pg/s | 6m 58s | 21.7s |
| 26 | Text Flow Envelope | `text_flow` | Generator | `HTH-0001` | complete | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | 0.8170 | 4 | 729 | 10.06 pg/s | 1m 32s | 3.3s |
| 27 | Whitespace Frame | `whitespace_frame` | Generator | `HTH-0001` | complete | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 730 | 721.81 pg/s | 1.3s | 1.3s |

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

| Rank | Detector | Detector ID | Role | Golden Set ID | Date | Build* | Est. Serial Runtime** | Parameter Set ID | Parameter Sets | Search Type | Successful Parameter Sets | Best Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Δ Baseline Avg IoU | Near-best Coverage (Basin) | Equivalent Best Configurations | Calibration Evidence | Approval Level |
|---:|---|---|---|---|---|---|---:|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---|
| **1** | **Polar Boundary Voting** | **`polar_boundary_vote`** | **Generator** | **`HTH-0001`** | **2026-08-12** | **[#327](https://github.com/dlstupka/hth/actions/runs/31614759801)** | **8.9s** | **`cd967f93437d`** | **729** | **exhaustive** | **100.0%** | **0.9678** | **0.9425** | **0.0182** | **0.9678** | **0** | **+0.0832** | **0.8%** | **0.4%** | **Medium** | **Recommended** |
| 2 | Adaptive Radial Edge Search | `adaptive_radial_edge` | Generator | `HTH-0001` | 2026-08-07 | [#241](https://github.com/dlstupka/hth/actions/runs/31142095265) | 45m 27s | `5010d5b46516` | 6562 | exhaustive | 100.0% | 0.9599 | 0.9440 | 0.0114 | 0.9599 | 0 | +0.0270 | 0.1% | 0.1% | Medium | Recommended |
| 3 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | 2026-08-10 | [#295](https://github.com/dlstupka/hth/actions/runs/31424176107) | 3m 52s | `5f802d0c469d` | 6562 | exhaustive | 100.0% | 0.9547 | 0.9432 | 0.0104 | 0.9547 | 0 | +0.0044 | 1.2% | 1.2% | High | Approved |
| 4 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | 2026-08-10 | [#300](https://github.com/dlstupka/hth/actions/runs/31436321510) | 6.4s | `736327fcfb98` | 6562 | exhaustive | 79.4% | 0.9250 | 0.7525 | 0.0869 | 0.9250 | 0 | +0.0368 | 8.6% | 1.2% | Medium | Recommended |
| 5 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | 2026-08-10 | [#290](https://github.com/dlstupka/hth/actions/runs/31424169237) | 6h 23m 40s | `f33aa4421393` | 13122 | exhaustive | 95.7% | 0.9137 | 0.7378 | 0.0886 | 0.9137 | 0 | +0.1006 | 0.0% | 0.0% | Medium | Recommended |
| 6 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | 2026-08-10 | [#287](https://github.com/dlstupka/hth/actions/runs/31424165043) | 10h 40m 34s | `49095b866d0d` | 1062882 | exhaustive | 33.3% | 0.8874 | 0.7589 | 0.0731 | 0.8874 | 0 | +0.0105 | 15.5% | 5.3% | Medium | Recommended |
| 7 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | 2026-08-10 | [#285](https://github.com/dlstupka/hth/actions/runs/31424162073) | 3h 9m 30s | `3eec8a03f1de` | 6562 | exhaustive | 100.0% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 100.0% | 100.0% | High | Approved |
| 8 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | 2026-08-10 | [#286](https://github.com/dlstupka/hth/actions/runs/31424163624) | 7m 22s | `0cd13eb1a471` | 6562 | exhaustive | 100.0% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 92.6% | 92.6% | High | Approved |
| 9 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | 2026-08-10 | [#288](https://github.com/dlstupka/hth/actions/runs/31424166301) | 3m 28s | `a5450e58ec9e` | 6562 | exhaustive | 29.6% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 29.6% | 29.6% | Medium | Recommended |
| 10 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | 2026-08-10 | [#301](https://github.com/dlstupka/hth/actions/runs/31437186835) | 1m 8s | `4e5bc37a649a` | 13123 | exhaustive | 12.3% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.3377 | 8.6% | 8.6% | Medium | Recommended |
| 11 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | 2026-08-10 | [#284](https://github.com/dlstupka/hth/actions/runs/31424160561) | 3m 48s | `14818b491952` | 19684 | exhaustive | 100.0% | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | +0.0000 | 100.0% | 100.0% | High | Approved |
| 12 | Contour Envelope | `contour` | Generator | `HTH-0001` | 2026-08-10 | [#283](https://github.com/dlstupka/hth/actions/runs/31424159190) | 4.6s | `7aed2fc501c5` | 1458 | exhaustive | 50.0% | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | +0.1776 | 1.9% | 1.9% | Medium | Recommended |
| 13 | Distance Transform Detector | `distance_transform` | Generator | `HTH-0001` | 2026-08-12 | [#322](https://github.com/dlstupka/hth/actions/runs/31606269618) | 28.6s | `e66a7546e1a7` | 2187 | exhaustive | 51.2% | 0.8388 | 0.5001 | 0.1745 | 0.8388 | 0 | +0.0795 | 6.6% | 6.6% | Medium | Recommended |
| 14 | Star-Convex Boundary Optimization | `star_convex` | Generator | `HTH-0001` | 2026-08-12 | [#328](https://github.com/dlstupka/hth/actions/runs/31614832224) | 7.2s | `024732f5e631` | 729 | exhaustive | 100.0% | 0.8179 | 0.5367 | 0.1827 | 0.8179 | 0 | +0.0422 | 0.4% | 0.4% | Medium | Recommended |
| 15 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | 2026-08-12 | [#330](https://github.com/dlstupka/hth/actions/runs/31632454296) | 4m 14s | `3817f226228a` | 10 | smoke | 100.0% | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | +0.0000 | 10.0% | 10.0% | Medium | Provisional |
| 16 | Connected Components | `components` | Generator | `HTH-0001` | 2026-08-10 | [#281](https://github.com/dlstupka/hth/actions/runs/31424156590) | 40.8s | `f1929c8e2655` | 19683 | exhaustive | 75.8% | 0.7897 | 0.5725 | 0.1665 | 0.7897 | 0 | +0.0712 | 0.8% | 0.8% | Medium | Recommended |
| 17 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | 2026-08-10 | [#296](https://github.com/dlstupka/hth/actions/runs/31424177450) | 1m 31s | `9647b030702e` | 1458 | exhaustive | 5.3% | 0.7541 | 0.3558 | 0.2541 | 0.7541 | 0 | +0.0710 | 0.4% | 0.4% | Medium | Recommended |
| 18 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | 2026-08-10 | [#294](https://github.com/dlstupka/hth/actions/runs/31424174875) | 59s | `7546c5067527` | 2187 | exhaustive | 0.0% | 0.7378 | 0.0000 | 0.3721 | 0.9222 | 1 | +0.1964 | 1.2% | 0.4% | Medium | Recommended |
| 19 | Convex Hull Detector | `convex_hull` | Generator | `HTH-0001` | 2026-08-12 | [#321](https://github.com/dlstupka/hth/actions/runs/31606215160) | 2s | `04fd0a6e4bc2` | 2187 | exhaustive | 0.0% | 0.7325 | 0.0000 | 0.3683 | 0.9156 | 1 | +0.0692 | 6.6% | 6.6% | Medium | Recommended |
| 20 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | 2026-08-10 | [#278](https://github.com/dlstupka/hth/actions/runs/31423513220) | 3m 59s | `74e2112aac01` | 6562 | exhaustive | 0.0% | 0.7250 | 0.0000 | 0.3651 | 0.9063 | 1 | +0.1708 | 19.8% | 19.8% | Medium | Recommended |
| 21 | Distance-Transform Rectangle Proposal | `distance_transform_rect` | Generator | `HTH-0001` | 2026-08-12 | [#326](https://github.com/dlstupka/hth/actions/runs/31614704921) | 1.2s | `0a8482550c35` | 729 | exhaustive | 9.9% | 0.7243 | 0.4499 | 0.2245 | 0.7243 | 0 | +0.0896 | 0.8% | 0.8% | Medium | Recommended |
| 22 | Hough Line Borders | `hough` | Generator | `HTH-0001` | 2026-08-10 | [#293](https://github.com/dlstupka/hth/actions/runs/31424173458) | 3m 4s | `c2c117479e3f` | 2188 | exhaustive | 0.0% | 0.6050 | 0.0000 | 0.3217 | 0.7563 | 1 | +0.1266 | 0.0% | 0.0% | Medium | Recommended |
| 23 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | 2026-08-10 | [#282](https://github.com/dlstupka/hth/actions/runs/31424157793) | 21.3s | `f387da7ebb7e` | 243 | exhaustive | 0.0% | 0.5528 | 0.0000 | 0.4526 | 0.9213 | 2 | +0.0015 | 9.9% | 4.9% | Medium | Recommended |
| 24 | Radon Boundary Projection | `radon_boundary` | Generator | `HTH-0001` | 2026-08-12 | [#331](https://github.com/dlstupka/hth/actions/runs/31633124269) | 10.4s | `dd6b2601d568` | 729 | exhaustive | 58.0% | 0.4983 | 0.2028 | 0.2509 | 0.4983 | 0 | +0.0756 | 1.2% | 1.2% | Medium | Recommended |
| 25 | Joint Rectangle Voting | `joint_rectangle_vote` | Generator | `HTH-0001` | 2026-08-12 | [#334](https://github.com/dlstupka/hth/actions/runs/31634399929) | 21.7s | `5c9509e05f14` | 2187 | exhaustive | 0.0% | 0.1980 | 0.0000 | 0.3960 | 0.9899 | 4 | +0.1980 | 1.2% | 1.2% | Medium | Recommended |
| 26 | Text Flow Envelope | `text_flow` | Generator | `HTH-0001` | 2026-08-12 | [#332](https://github.com/dlstupka/hth/actions/runs/31633231735) | 3.3s | `a2bbfc162f9e` | 729 | exhaustive | 0.0% | 0.1634 | 0.0000 | 0.3268 | 0.8170 | 4 | +0.0038 | 4.7% | 4.7% | Medium | Recommended |
| 27 | Whitespace Frame | `whitespace_frame` | Generator | `HTH-0001` | 2026-08-12 | [#333](https://github.com/dlstupka/hth/actions/runs/31633282476) | 1.3s | `9ef715dda063` | 730 | exhaustive | 0.0% | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | +0.0000 | 100.0% | 100.0% | Medium | Recommended |

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
- **Build*:** `#run` links open GitHub Actions logs and artifacts and expire according to repository retention; the calibration data persists in [calibration-intelligence.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/e3c677bf4406a7a7668251a0ad73510c60046eed/source-documents/baptisms-san-antonio-baptism-records-1788-1824-1858-1898/golden-sets/hth-0001/135c0ff57687/calibrations/polar_boundary_vote/run-20260812-155410/calibration-intelligence.json).
- **Est. Serial Runtime\*\*:** Estimated single-detector serial runtime derived from recorded regression evidence; actual wall time varies with parallelism and scheduling.

[↑ Back to Navigation](#table-of-contents)

<a id="per-detector-calibration-reports"></a>
<details open>
<summary><h3>Per-Detector Calibration Reports</h3></summary>


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
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 729 (100.0%) |
| Best Avg IoU | 0.9678 |
| Minimum Avg IoU | 0.8176 |
| Avg IoU StdDev | 0.0470 |
| Winner stabilized after | 341 parameter sets |
| Winner stabilized | 4.1s (47% of search) |
| Near-best coverage (basin; within 0.0010) | 6 (0.8%) |
| Equivalent-best configurations (within 0.0001) | 3 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 47m 31s | 1.0× |
| Non-dormant | 81 | 11.1% | 5m 17s | 9.0× |
| Low+ | 81 | 11.1% | 5m 17s | 9.0× |
| Moderate+ | 27 | 3.7% | 1m 46s | 27.0× |
| Important+ | 3 | 0.4% | 11.7s | 243.0× |
| Critical | 3 | 0.4% | 11.7s | 243.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `outer_radius_fraction` | Critical | 0.8387 | 0.1046 | 33.3% | `0.6` (0.9297), `0.7` (0.8660), `0.82` (0.8251) |
| `bbox_padding_fraction` | Moderate | 0.0722 | 0.0308 | 33.3% | `0` (0.8899), `0.008` (0.8717), `0.016` (0.8592) |
| `gradient_percentile` | Moderate | 0.0455 | 0.0243 | 33.3% | `90` (0.8868), `82` (0.8715), `72` (0.8625) |
| `ray_count` | Low | 0.0073 | 0.0099 | 66.7% | `90` (0.8786), `180` (0.8734), `360` (0.8688) |
| `inner_radius_fraction` | Dormant | 0.0008 | 0.0029 | 33.3% | `0.12` (0.8746), `0.06` (0.8745), `0.18` (0.8717) |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8736), `0.35` (0.8736), `0.5` (0.8736) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`inner_radius_fraction`, `minimum_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_radius_fraction` × `bbox_padding_fraction` | 0.9269 | 0.0882 | 729 |
| `outer_radius_fraction` × `gradient_percentile` | 0.8926 | 0.0539 | 729 |
| `bbox_padding_fraction` × `gradient_percentile` | 0.1186 | 0.0464 | 729 |
| `outer_radius_fraction` × `ray_count` | 0.8486 | 0.0099 | 729 |
| `gradient_percentile` × `ray_count` | 0.0540 | 0.0085 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8628 | 0.7782 | 0.9819 | 0.0661 | 100.0% |
| 5 | 0.9109 | 0.8699 | 0.9942 | 0.0449 | 100.0% |
| 6 | 0.9444 | 0.9327 | 0.9753 | 0.0131 | 100.0% |
| 9 | 0.7901 | 0.7134 | 0.9473 | 0.0738 | 100.0% |
| 10 | 0.8597 | 0.7940 | 0.9543 | 0.0545 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="adaptive-radial-edge-search-adaptiveradialedge"></a>
<details>
<summary><strong>Adaptive Radial Edge Search (`adaptive_radial_edge`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 10 of 16 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 6562 (100.0%) |
| Best Avg IoU | 0.9599 |
| Minimum Avg IoU | 0.7978 |
| Avg IoU StdDev | 0.0408 |
| Winner stabilized after | 6294 parameter sets |
| Winner stabilized | 44m 25s (96% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (0.1%) |
| Equivalent-best configurations (within 0.0001) | 4 (0.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 4d 10h 48m 38s | 1.0× |
| Non-dormant | 729 | 11.1% | 11h 51m 58s | 9.0× |
| Low+ | 729 | 11.1% | 11h 51m 58s | 9.0× |
| Moderate+ | 9 | 0.1% | 8m 47s | 729.1× |
| Important+ | 9 | 0.1% | 8m 47s | 729.1× |
| Critical | 3 | 0.0% | 2m 56s | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `maximum_radius_fraction` | Critical | 0.7054 | 0.0796 | 33.3% | `0.72` (0.9245), `0.82` (0.9079), `0.62` (0.8449) |
| `minimum_radius_fraction` | Important | 0.1095 | 0.0318 | 33.3% | `0.24` (0.9110), `0.18` (0.8872), `0.12` (0.8792) |
| `maximum_refined_sides` | Low | 0.0257 | 0.0157 | 33.3% | `4` (0.8994), `2` (0.8944), `1` (0.8837) |
| `gaussian_sigma` | Low | 0.0123 | 0.0099 | 33.3% | `1.2` (0.8959), `1.8` (0.8954), `0.8` (0.8861) |
| `gradient_percentile` | Low | 0.0059 | 0.0075 | 33.3% | `70` (0.8967), `82` (0.8916), `90` (0.8892) |
| `refined_angle_step_degrees` | Low | 0.0054 | 0.0072 | 33.3% | `0.5` (0.8965), `1.5` (0.8917), `1` (0.8892) |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.35` (0.9329) |
| `coarse_angle_step_degrees` | Dormant | 0.0001 | 0.0000 | 0.0% | `3` (0.9329) |
| `maximum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.98` (0.9329) |
| `minimum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.18` (0.9329) |
| `minimum_ray_support` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.45` (0.9329) |
| `ray_count` | Dormant | 0.0001 | 0.0000 | 0.0% | `120` (0.9329) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `coarse_angle_step_degrees`, `maximum_area_fraction`, `minimum_area_fraction`, `minimum_ray_support`, `ray_count`, `rectangularity_weight`, `support_weight`, `side_assignment_tolerance_fraction`, `weak_side_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_radius_fraction` × `minimum_radius_fraction` | 0.8317 | 0.1263 | 6562 |
| `maximum_radius_fraction` × `gaussian_sigma` | 0.7381 | 0.0327 | 6562 |
| `maximum_radius_fraction` × `maximum_refined_sides` | 0.7334 | 0.0280 | 6562 |
| `minimum_radius_fraction` × `maximum_refined_sides` | 0.1371 | 0.0276 | 6562 |
| `maximum_radius_fraction` × `gradient_percentile` | 0.7223 | 0.0168 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8986 | 0.8114 | 0.9732 | 0.0435 | 100.0% |
| 5 | 0.9409 | 0.8344 | 0.9923 | 0.0506 | 100.0% |
| 6 | 0.8058 | 0.6268 | 0.9968 | 0.0989 | 100.0% |
| 9 | 0.8929 | 0.7202 | 0.9557 | 0.0587 | 100.0% |
| 10 | 0.9242 | 0.7940 | 0.9717 | 0.0463 | 100.0% |

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
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 6562 (100.0%) |
| Best Avg IoU | 0.9547 |
| Minimum Avg IoU | 0.7683 |
| Avg IoU StdDev | 0.0475 |
| Winner stabilized after | 5671 parameter sets |
| Winner stabilized | 3m 12s (86% of search) |
| Near-best coverage (basin; within 0.0010) | 81 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 81 (1.2%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 51m 24s | 1.0× |
| Non-dormant | 81 | 1.2% | 38.1s | 81.0× |
| Low+ | 81 | 1.2% | 38.1s | 81.0× |
| Moderate+ | 81 | 1.2% | 38.1s | 81.0× |
| Important+ | 9 | 0.1% | 4.2s | 729.1× |
| Critical | 3 | 0.0% | 1.4s | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `maximum_radius_fraction` | Critical | 0.5353 | 0.0794 | 33.3% | `0.72` (0.9102), `0.82` (0.8970), `0.62` (0.8308) |
| `ray_count` | Important | 0.1759 | 0.0486 | 33.3% | `96` (0.9023), `144` (0.8820), `64` (0.8537) |
| `minimum_radius_fraction` | Moderate | 0.0329 | 0.0190 | 33.3% | `0.24` (0.8915), `0.12` (0.8741), `0.18` (0.8725) |
| `gaussian_sigma` | Moderate | 0.0317 | 0.0185 | 33.3% | `1.8` (0.8859), `1.2` (0.8847), `0.8` (0.8674) |
| `gradient_percentile` | Dormant | 0.0009 | 0.0033 | 100.0% | `70` (0.8814), `90` (0.8785), `82` (0.8781) |
| `area_weight` | Dormant | 0.0003 | 0.0000 | 0.0% | `0.35` (0.9503) |
| `maximum_area_fraction` | Dormant | 0.0003 | 0.0000 | 0.0% | `0.98` (0.9503) |
| `minimum_area_fraction` | Dormant | 0.0003 | 0.0000 | 0.0% | `0.18` (0.9503) |
| `minimum_ray_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8794), `0.3` (0.8793), `0.6` (0.8793) |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8794), `0.1` (0.8793), `0.3` (0.8793) |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8794), `0.35` (0.8793), `0.55` (0.8793) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`gradient_percentile`, `area_weight`, `maximum_area_fraction`, `minimum_area_fraction`, `minimum_ray_support`, `rectangularity_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_radius_fraction` × `ray_count` | 0.7189 | 0.1837 | 6562 |
| `maximum_radius_fraction` × `gaussian_sigma` | 0.6420 | 0.1068 | 6562 |
| `ray_count` × `gaussian_sigma` | 0.2413 | 0.0654 | 6562 |
| `maximum_radius_fraction` × `minimum_radius_fraction` | 0.5921 | 0.0568 | 6562 |
| `minimum_radius_fraction` × `gaussian_sigma` | 0.0696 | 0.0366 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8720 | 0.7578 | 0.9562 | 0.0645 | 100.0% |
| 5 | 0.9350 | 0.7703 | 0.9856 | 0.0585 | 100.0% |
| 6 | 0.8153 | 0.4831 | 0.9432 | 0.1066 | 100.0% |
| 9 | 0.8629 | 0.7134 | 0.9575 | 0.0821 | 100.0% |
| 10 | 0.9115 | 0.7960 | 0.9623 | 0.0534 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="gradient-boundary-voting-gradientvote"></a>
<details>
<summary><strong>Gradient Boundary Voting (`gradient_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 6 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 5212 (79.4%) |
| Best Avg IoU | 0.9250 |
| Minimum Avg IoU | 0.7327 |
| Avg IoU StdDev | 0.0560 |
| Winner stabilized after | 3567 parameter sets |
| Winner stabilized | 3.3s (54% of search) |
| Near-best coverage (basin; within 0.0010) | 567 (8.6%) |
| Equivalent-best configurations (within 0.0001) | 81 (1.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 29m 45s | 1.0× |
| Non-dormant | 243 | 3.7% | 1m 6s | 27.0× |
| Low+ | 243 | 3.7% | 1m 6s | 27.0× |
| Moderate+ | 27 | 0.4% | 7.3s | 243.0× |
| Important+ | 9 | 0.1% | 2.4s | 729.1× |
| Critical | 9 | 0.1% | 2.4s | 729.1× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `border_search_fraction` | Critical | 0.3545 | 0.0768 | 33.3% | `0.35` (0.9191), `0.42` (0.8565), `0.47` (0.8423) |
| `minimum_span_fraction` | Critical | 0.3266 | 0.0679 | 100.0% | `0.35` (0.8953), `0.45` (0.8953), `0.55` (0.8274) |
| `gaussian_sigma` | Moderate | 0.0304 | 0.0239 | 33.3% | `1.8` (0.8841), `1.2` (0.8736), `0.8` (0.8602) |
| `central_band_fraction` | Low | 0.0080 | 0.0117 | 100.0% | `1` (0.8775), `0.86` (0.8748), `0.7` (0.8657) |
| `vote_smooth_fraction` | Low | 0.0015 | 0.0048 | 100.0% | `0.02` (0.8757), `0.012` (0.8713), `0.006` (0.8709) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.8882) |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `gradient_percentile` | Dormant | 0.0000 | 0.0000 | 100.0% | `82` (0.8727), `70` (0.8727), `90` (0.8727) |
| `minimum_vote_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.16` (0.8727), `0.08` (0.8727), `0.25` (0.8727) |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.8727), `0.45` (0.8727), `0.65` (0.8727) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `minimum_area_fraction`, `rectangularity_weight`, `gradient_percentile`, `minimum_vote_support`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `border_search_fraction` × `minimum_span_fraction` | 0.8462 | 0.4917 | 6562 |
| `border_search_fraction` × `gaussian_sigma` | 0.4019 | 0.0474 | 6562 |
| `minimum_span_fraction` × `gaussian_sigma` | 0.3612 | 0.0346 | 6562 |
| `gaussian_sigma` × `central_band_fraction` | 0.0484 | 0.0179 | 6562 |
| `gaussian_sigma` × `vote_smooth_fraction` | 0.0434 | 0.0130 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9508 | 0.8680 | 0.9621 | 0.0239 | 100.0% |
| 5 | 0.5111 | 0.0000 | 0.7534 | 0.2745 | 79.4% |
| 6 | 0.9888 | 0.9879 | 0.9889 | 0.0004 | 100.0% |
| 9 | 0.9522 | 0.8466 | 0.9612 | 0.0299 | 100.0% |
| 10 | 0.9604 | 0.9592 | 0.9611 | 0.0006 | 100.0% |

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
| Fully successful parameter sets | 12559 (95.7%) |
| Best Avg IoU | 0.9137 |
| Minimum Avg IoU | 0.4353 |
| Avg IoU StdDev | 0.0677 |
| Winner stabilized after | 5035 parameter sets |
| Winner stabilized | 2h 27m 7s (38% of search) |
| Near-best coverage (basin; within 0.0010) | 5 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 5 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13122 | 100.0% | 5d 5h 49m 57s | 1.0× |
| Non-dormant | 486 | 3.7% | 4h 39m 38s | 27.0× |
| Low+ | 486 | 3.7% | 4h 39m 38s | 27.0× |
| Moderate+ | 81 | 0.6% | 46m 36s | 162.0× |
| Important+ | 27 | 0.2% | 15m 32s | 486.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `erosion_iterations` | Important | 0.1940 | 0.0707 | 66.7% | `1` (0.7945), `2` (0.7751), `0` (0.7238) |
| `border_fraction` | Important | 0.1635 | 0.0602 | 33.3% | `0.01` (0.8031), `0.03` (0.7474), `0.02` (0.7429) |
| `grabcut_iterations` | Important | 0.1276 | 0.0555 | 33.3% | `5` (0.7862), `3` (0.7765), `1` (0.7307) |
| `erosion_kernel_fraction` | Moderate | 0.0789 | 0.0459 | 66.7% | `0.0075` (0.7897), `0.015` (0.7600), `0.025` (0.7437) |
| `close_kernel_fraction` | Low | 0.0197 | 0.0215 | 33.3% | `0.01` (0.7726), `0.02` (0.7697), `0.035` (0.7511) |
| `close_iterations` | Low | 0.0083 | 0.0124 | 50.0% | `1` (0.7707), `2` (0.7583) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0008 | 66.7% | `0.02` (0.7650), `0.04` (0.7643), `0.07` (0.7642) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0006 | 66.7% | `0.1` (0.7648), `0.07` (0.7645), `0.15` (0.7642) |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0002 | 100.0% | `0.018` (0.7646), `0.01` (0.7645), `0.03` (0.7644) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_contour_area_fraction`, `minimum_bbox_area_fraction`, `polygon_epsilon_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `erosion_iterations` × `border_fraction` | 0.4075 | 0.2135 | 13122 |
| `border_fraction` × `grabcut_iterations` | 0.3016 | 0.1382 | 13122 |
| `erosion_iterations` × `grabcut_iterations` | 0.3254 | 0.1314 | 13122 |
| `erosion_iterations` × `erosion_kernel_fraction` | 0.3050 | 0.1110 | 13122 |
| `border_fraction` × `erosion_kernel_fraction` | 0.2618 | 0.0983 | 13122 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9022 | 0.0000 | 0.9904 | 0.1865 | 96.7% |
| 5 | 0.5519 | 0.2980 | 0.9755 | 0.1027 | 100.0% |
| 6 | 0.5038 | 0.0000 | 0.8217 | 0.1794 | 98.7% |
| 9 | 0.9308 | 0.8522 | 0.9433 | 0.0288 | 100.0% |
| 10 | 0.9337 | 0.8355 | 0.9661 | 0.0228 | 100.0% |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `merge_fragmented_contours` | Critical | 0.7000 | 0.1995 | 50.0% | `true` (0.8241), `false` (0.6246) |
| `epsilon_max_fraction` | Critical | 0.2737 | 0.1323 | 66.7% | `0.04` (0.7685), `0.06` (0.7685), `0.025` (0.6362) |
| `close_kernel_fraction` | Dormant | 0.0001 | 0.0027 | 100.0% | `0.018` (0.7260), `0.008` (0.7237), `0` (0.7233) |
| `close_iterations` | Dormant | 0.0001 | 0.0025 | 100.0% | `2` (0.7259), `1` (0.7238), `0` (0.7233) |
| `edge_support_weight` | Dormant | 0.0001 | 0.0024 | 100.0% | `0.25` (0.7256), `0.15` (0.7242), `0.1` (0.7233) |
| `edge_support_dilation_fraction` | Dormant | 0.0001 | 0.0022 | 100.0% | `0.008` (0.7256), `0.004` (0.7240), `0.002` (0.7234) |
| `area_weight` | Dormant | 0.0001 | 0.0021 | 100.0% | `0.25` (0.7255), `0.35` (0.7242), `0.45` (0.7234) |
| `angle_weight` | Dormant | 0.0000 | 0.0012 | 100.0% | `0.3` (0.7249), `0.2` (0.7244), `0.1` (0.7237) |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.004` (0.7244), `0.008` (0.7244), `0.012` (0.7244) |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 100.0% | `13` (0.7244), `5` (0.7244), `9` (0.7244) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.06` (0.7244), `0.12` (0.7244), `0.2` (0.7244) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.7244), `0.55` (0.7244), `0.7` (0.7244) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_polarity_consistency` | Critical | 0.9288 | 0.4950 | 50.0% | `0.55` (0.8768), `0.5` (0.8600), `0.65` (0.6676) |
| `sample_offset_fraction` | Low | 0.0296 | 0.0744 | 100.0% | `0.008` (0.6613), `0.014` (0.6612), `0.004` (0.5869) |
| `minimum_cross_edge_contrast` | Low | 0.0015 | 0.0170 | 100.0% | `0.045` (0.6422), `0.02` (0.6421), `0.08` (0.6252) |
| `contour_weight` | Dormant | 0.0002 | 0.0000 | 100.0% | `0.45` (0.8768) |
| `polarity_weight` | Dormant | 0.0002 | 0.0000 | 100.0% | `0.15` (0.8768) |
| `contrast_weight` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.4` (0.6366), `0.3` (0.6365), `0.5` (0.6365) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.04` (0.6366), `0.03` (0.6365), `0.06` (0.6365) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.12` (0.6366), `0.08` (0.6365), `0.18` (0.6365) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.55` (0.6366), `0.45` (0.6365), `0.7` (0.6365) |
| `samples_per_edge` | Dormant | 0.0000 | 0.0001 | 100.0% | `48` (0.6366), `24` (0.6365), `72` (0.6365) |

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

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `projection_threshold_block_fraction` | Important | 0.1600 | 0.0183 | 100.0% | `0.05` (0.8768), `0.08` (0.8768), `0.12` (0.8586) |
| `projection_weight` | Moderate | 0.0933 | 0.0152 | 100.0% | `0.2` (0.8768), `0.3` (0.8738), `0.4` (0.8616) |
| `projection_threshold_c` | Moderate | 0.0400 | 0.0091 | 100.0% | `13` (0.8738), `5` (0.8738), `9` (0.8646) |
| `projection_margin_fraction` | Low | 0.0133 | 0.0061 | 100.0% | `0.06` (0.8738), `0.1` (0.8707), `0.03` (0.8677) |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8768) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 100.0% | `9` (0.8768) |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 100.0% | `true` (0.8768) |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_edge_support` | Critical | 0.3207 | 0.3412 | 66.7% | `0.05` (0.6504), `0.12` (0.4293), `0.2` (0.3092) |
| `edge_support_dilation_fraction` | Important | 0.1807 | 0.2557 | 100.0% | `0.01` (0.5775), `0.006` (0.4895), `0.003` (0.3218) |
| `minimum_segment_length_fraction` | Important | 0.1417 | 0.2229 | 33.3% | `0.03` (0.5908), `0.06` (0.4301), `0.1` (0.3679) |
| `lsd_scale` | Important | 0.1119 | 0.1922 | 66.7% | `0.6` (0.5390), `0.8` (0.5031), `1` (0.3468) |
| `lsd_refine_mode` | Moderate | 0.0518 | 0.1136 | 100.0% | `none` (0.5197), `std` (0.4062) |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.5392) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.5392) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.5392) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.5392) |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.5392) |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 0.0% | `9` (0.5392) |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 0.0% | `true` (0.5392) |

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

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `agreement_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) |
| `contour_epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768), `0.06` (0.8768) |
| `contour_minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768), `0.18` (0.8768) |
| `contour_minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768), `0.7` (0.8768) |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768) |
| `grabcut_border_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.01` (0.8768), `0.02` (0.8768), `0.03` (0.8768) |
| `grabcut_erosion_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8768) |
| `grabcut_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8768), `3` (0.8768), `5` (0.8768) |
| `grabcut_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.25` (0.8768), `0.35` (0.8768) |
| `minimum_agreement_iou` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.3` (0.8768), `0.5` (0.8768) |
| `require_grabcut` | Dormant | 0.0000 | 0.0000 | 100.0% | `false` (0.8768) |

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

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `component_close_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.004` (0.8617), `0.012` (0.8617), `0.008` (0.8617) |
| `component_dilate_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.008` (0.8617), `0.025` (0.8617), `0.015` (0.8617) |
| `component_merge_gap_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.06` (0.8617), `0.035` (0.8617) |
| `component_minimum_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.0008` (0.8617), `0.003` (0.8617), `0.0015` (0.8617) |
| `component_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.25` (0.8617), `0.55` (0.8617), `0.4` (0.8617) |
| `epsilon_max_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8617), `0.06` (0.8617), `0.04` (0.8617) |
| `minimum_component_score` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.12` (0.8617), `0.05` (0.8617) |
| `minimum_contour_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.08` (0.8617), `0.18` (0.8617), `0.12` (0.8617) |
| `minimum_rectangularity` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.45` (0.8617), `0.7` (0.8617), `0.55` (0.8617) |
| `angle_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.15` (0.8617) |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.25` (0.8617) |
| `close_iterations` | Dormant | 0.0001 | 0.0000 | 100.0% | `1` (0.8617) |

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

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `merge_fragmented_contours` | Critical | 0.9954 | 0.1691 | 50.0% | `true` (0.8377), `false` (0.6686) |
| `bbox_padding_fraction` | Low | 0.0023 | 0.0091 | 33.3% | `0.005` (0.7565), `0` (0.7555), `0.015` (0.7474) |
| `close_iterations` | Dormant | 0.0004 | 0.0035 | 33.3% | `2` (0.7555), `0` (0.7519), `1` (0.7519) |
| `close_kernel_fraction` | Dormant | 0.0004 | 0.0035 | 33.3% | `0.018` (0.7555), `0` (0.7519), `0.008` (0.7519) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.06` (0.7531), `0.12` (0.7531), `0.2` (0.7531) |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.7531), `0.018` (0.7531), `0.035` (0.7531) |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.7531), `0.25` (0.7531), `0.4` (0.7531) |

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

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `distance_threshold_fraction` | Critical | 0.5293 | 0.1276 | 33.3% | `0.1` (0.8039), `0.18` (0.7195), `0.3` (0.6763) |
| `minimum_core_area_fraction` | Important | 0.1010 | 0.0534 | 100.0% | `0.004` (0.7545), `0.01` (0.7442), `0.025` (0.7011) |
| `minimum_rectangularity` | Moderate | 0.0335 | 0.0283 | 100.0% | `0.35` (0.7427), `0.5` (0.7427), `0.7` (0.7144) |
| `minimum_component_core_overlap` | Moderate | 0.0319 | 0.0289 | 66.7% | `0.03` (0.7438), `0.08` (0.7410), `0.16` (0.7149) |
| `close_kernel_fraction` | Low | 0.0160 | 0.0215 | 100.0% | `0.016` (0.7421), `0.008` (0.7371), `0` (0.7205) |
| `bbox_padding_fraction` | Low | 0.0042 | 0.0102 | 33.3% | `0` (0.7367), `0.008` (0.7364), `0.016` (0.7266) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0004 | 100.0% | `0.1` (0.7335), `0.16` (0.7331), `0.24` (0.7331) |

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

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `smoothing_window` | Critical | 0.6484 | 0.0365 | 33.3% | `1` (0.8009), `9` (0.7645), `5` (0.7644) |
| `maximum_radius_fraction` | Moderate | 0.0970 | 0.0150 | 33.3% | `0.6` (0.7822), `0.72` (0.7803), `0.84` (0.7673) |
| `bbox_padding_fraction` | Moderate | 0.0312 | 0.0084 | 33.3% | `0` (0.7797), `0.008` (0.7788), `0.016` (0.7713) |
| `ray_count` | Low | 0.0171 | 0.0065 | 33.3% | `360` (0.7804), `180` (0.7755), `90` (0.7739) |
| `minimum_radius_fraction` | Low | 0.0053 | 0.0034 | 33.3% | `0.16` (0.7788), `0.05` (0.7756), `0.1` (0.7754) |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.7766), `0.55` (0.7766), `0.7` (0.7766) |

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

<a id="grabcut-contour-grabcutcontour"></a>
<details>
<summary><strong>GrabCut + Contour (`grabcut_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 5 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 354295 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 286d 5h 30m |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8130 |
| Minimum Avg IoU | 0.7986 |
| Avg IoU StdDev | 0.0039 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 354295 | 100.0% | 286d 5h 41m 38s | 1.0× |
| Non-dormant | 6144 | 1.7% | 4d 23h 7m 50s | 57.7× |
| Low+ | 6144 | 1.7% | 4d 23h 7m 50s | 57.7× |
| Moderate+ | 6144 | 1.7% | 4d 23h 7m 50s | 57.7× |
| Important+ | 3072 | 0.9% | 2d 11h 33m 55s | 115.3× |
| Critical | 512 | 0.1% | 9h 55m 39s | 692.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `contour_minimum_area_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.12` (0.8130), `0.08` (0.8005) |
| `contour_minimum_rectangularity` | Critical | 0.9408 | 0.0125 | 50.0% | `0.55` (0.8130), `0.45` (0.8005) |
| `grabcut_border_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.02` (0.8130), `0.01` (0.8005) |
| `grabcut_close_kernel_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.02` (0.8130), `0.01` (0.8005) |
| `grabcut_erosion_kernel_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.015` (0.8130), `0.008` (0.8005) |
| `grabcut_iterations` | Critical | 0.9408 | 0.0125 | 50.0% | `3` (0.8130), `1` (0.8005) |
| `grabcut_minimum_contour_area_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.04` (0.8130), `0.02` (0.8005) |
| `grabcut_polygon_epsilon_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.018` (0.8130), `0.01` (0.8005) |
| `minimum_agreement_iou` | Critical | 0.9408 | 0.0125 | 50.0% | `0.15` (0.8130), `0.05` (0.8005) |
| `contour_epsilon_max_fraction` | Dormant | 0.8467 | 0.0000 | 100.0% | `0.04` (0.8130) |
| `contour_weight` | Dormant | 0.8467 | 0.0000 | 100.0% | `0.2` (0.8130) |
| `grabcut_close_iterations` | Dormant | 0.8467 | 0.0000 | 100.0% | `1` (0.8130) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_epsilon_max_fraction`, `contour_weight`, `grabcut_close_iterations`, `grabcut_erosion_iterations`, `grabcut_minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9589 | 0.9499 | 0.9617 | 0.0047 | 100.0% |
| 5 | 0.5492 | 0.5486 | 0.5532 | 0.0014 | 100.0% |
| 6 | 0.6045 | 0.5974 | 0.6683 | 0.0213 | 100.0% |
| 9 | 0.9432 | 0.9422 | 0.9433 | 0.0003 | 100.0% |
| 10 | 0.9530 | 0.9447 | 0.9540 | 0.0028 | 100.0% |

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

Calibration evidence basis: complete exhaustive coverage, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `morphology_dilate_fraction` | Critical | 0.4776 | 0.0693 | 33.3% | `0.03` (0.7658), `0.015` (0.7266), `0.008` (0.6965) |
| `merge_gap_fraction` | Moderate | 0.0940 | 0.0269 | 66.7% | `0.06` (0.7474), `0.035` (0.7209), `0.02` (0.7206) |
| `minimum_selected_area_fraction` | Moderate | 0.0620 | 0.0217 | 100.0% | `0.02` (0.7369), `0.04` (0.7369), `0.07` (0.7152) |
| `minimum_component_area_fraction` | Moderate | 0.0371 | 0.0179 | 33.3% | `0.00075` (0.7408), `0.0015` (0.7253), `0.003` (0.7229) |
| `bbox_padding_fraction` | Moderate | 0.0362 | 0.0183 | 33.3% | `0` (0.7373), `0.005` (0.7328), `0.015` (0.7189) |
| `merge_area_ratio` | Low | 0.0259 | 0.0161 | 33.3% | `0.01` (0.7372), `0.02` (0.7306), `0.05` (0.7211) |
| `morphology_close_fraction` | Low | 0.0120 | 0.0096 | 100.0% | `0.016` (0.7360), `0.004` (0.7265), `0.008` (0.7265) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.7297), `0.12` (0.7296), `0.18` (0.7296) |
| `minimum_component_area_px` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.7296), `25` (0.7296), `50` (0.7296) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_mean_inlier_ratio` | Critical | 0.7489 | 0.2487 | 33.3% | `0.25` (0.6889), `0.45` (0.6430), `0.65` (0.4402) |
| `residual_threshold_fraction` | Important | 0.1372 | 0.1114 | 33.3% | `0.014` (0.6523), `0.008` (0.5789), `0.004` (0.5408) |
| `bbox_padding_fraction` | Low | 0.0021 | 0.0129 | 33.3% | `0` (0.5956), `0.008` (0.5937), `0.016` (0.5827) |
| `minimum_bbox_area_fraction` | Dormant | 0.0002 | 0.0033 | 100.0% | `0.1` (0.5918), `0.18` (0.5918), `0.28` (0.5885) |
| `scan_samples` | Dormant | 0.0001 | 0.0031 | 33.3% | `220` (0.5919), `320` (0.5914), `140` (0.5888) |
| `minimum_scan_foreground_fraction` | Dormant | 0.0001 | 0.0028 | 33.3% | `0.02` (0.5917), `0.0125` (0.5915), `0.008` (0.5889) |
| `max_trials` | Dormant | 0.0000 | 0.0001 | 100.0% | `200` (0.5907), `400` (0.5906) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `refine_mode` | Critical | 0.2730 | 0.2038 | 33.3% | `none` (0.5940), `adv` (0.3902), `std` (0.3902) |
| `minimum_length_fraction` | Important | 0.2059 | 0.1926 | 100.0% | `0.08` (0.5347), `0.14` (0.4975), `0.22` (0.3421) |
| `outer_percentile` | Important | 0.1380 | 0.1568 | 33.3% | `5` (0.5197), `10` (0.4918), `20` (0.3629) |
| `scale` | Moderate | 0.0428 | 0.0888 | 66.7% | `0.6` (0.4944), `0.8` (0.4743), `1` (0.4056) |
| `bbox_padding_fraction` | Low | 0.0012 | 0.0138 | 33.3% | `0` (0.4628), `0.005` (0.4624), `0.015` (0.4490) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0004 | 100.0% | `0.08` (0.4584), `0.1` (0.4580), `0.15` (0.4580) |
| `axis_angle_tolerance_degrees` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.4581), `18` (0.4581), `28` (0.4581) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_solidity` | Critical | 0.3159 | 0.0595 | 66.7% | `0.35` (0.6854), `0.55` (0.6854), `0.75` (0.6260) |
| `minimum_fragment_area_fraction` | Moderate | 0.0301 | 0.0211 | 33.3% | `0.0015` (0.6769), `0.0002` (0.6641), `0.0005` (0.6558) |
| `bbox_padding_fraction` | Low | 0.0213 | 0.0174 | 33.3% | `0` (0.6732), `0.008` (0.6679), `0.016` (0.6558) |
| `close_iterations` | Dormant | 0.0000 | 0.0003 | 100.0% | `0` (0.6657), `1` (0.6657), `2` (0.6654) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0003 | 100.0% | `0` (0.6657), `0.008` (0.6657), `0.016` (0.6654) |
| `minimum_hull_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.6656), `0.16` (0.6656), `0.24` (0.6656) |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.012` (0.6656), `0.025` (0.6656), `0.05` (0.6656) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_side_consistency` | Critical | 0.5951 | 0.2495 | 33.3% | `0.3` (0.6554), `0.45` (0.5542), `0.6` (0.4059) |
| `band_fraction` | Important | 0.1173 | 0.1102 | 100.0% | `0.015` (0.5985), `0.008` (0.5287), `0.004` (0.4883) |
| `gaussian_sigma` | Low | 0.0252 | 0.0459 | 100.0% | `1.8` (0.5683), `0.8` (0.5248), `1.2` (0.5224) |
| `minimum_border_energy` | Low | 0.0020 | 0.0127 | 100.0% | `0.1` (0.5427), `0.05` (0.5427), `0.18` (0.5301) |
| `consistency_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.15` (0.5542) |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.45` (0.5542) |
| `energy_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.5385), `0.3` (0.5385), `0.5` (0.5385) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.5385), `0.03` (0.5385), `0.06` (0.5385) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.5385), `0.08` (0.5385), `0.2` (0.5385) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.5385), `0.45` (0.5385), `0.7` (0.5385) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `proposal_expansion_fraction` | Moderate | 0.0415 | 0.0184 | 33.3% | `0.06` (0.6160), `0.12` (0.6149), `0.22` (0.5975) |
| `minimum_mask_coverage` | Moderate | 0.0411 | 0.0199 | 33.3% | `0.06` (0.6210), `0.12` (0.6064), `0.22` (0.6011) |
| `minimum_core_area_fraction` | Low | 0.0204 | 0.0126 | 66.7% | `0.002` (0.6137), `0.006` (0.6137), `0.015` (0.6011) |
| `distance_threshold_fraction` | Low | 0.0192 | 0.0140 | 33.3% | `0.18` (0.6168), `0.3` (0.6090), `0.1` (0.6027) |
| `bbox_padding_fraction` | Low | 0.0018 | 0.0042 | 33.3% | `0.016` (0.6114), `0.008` (0.6099), `0` (0.6072) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.6095), `0.14` (0.6095), `0.22` (0.6095) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `outer_percentile` | Critical | 0.7748 | 0.2317 | 33.3% | `5` (0.5231), `10` (0.4474), `20` (0.2914) |
| `minimum_length_fraction` | Moderate | 0.0386 | 0.0495 | 33.3% | `0.12` (0.4402), `0.2` (0.4311), `0.3` (0.3907) |
| `maximum_gap_fraction` | Moderate | 0.0311 | 0.0437 | 33.3% | `0.09` (0.4373), `0.055` (0.4312), `0.025` (0.3935) |
| `canny_low_threshold` | Low | 0.0273 | 0.0443 | 33.3% | `40` (0.4423), `25` (0.4217), `65` (0.3980) |
| `hough_threshold_fraction` | Low | 0.0063 | 0.0211 | 33.3% | `0.035` (0.4320), `0.055` (0.4190), `0.08` (0.4109) |
| `bbox_padding_fraction` | Low | 0.0047 | 0.0182 | 33.3% | `0.015` (0.4305), `0.005` (0.4191), `0` (0.4124) |
| `minimum_bbox_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.1` (0.4784) |
| `axis_angle_tolerance_degrees` | Dormant | 0.0000 | 0.0009 | 33.3% | `12` (0.4210), `22` (0.4209), `32` (0.4201) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `maximum_mean_corner_distance_fraction` | Critical | 0.3999 | 0.1235 | 66.7% | `0.025` (0.4887), `0.04` (0.4887), `0.015` (0.3651) |
| `minimum_polygon_iou` | Critical | 0.3999 | 0.1235 | 66.7% | `0.8` (0.4887), `0.9` (0.4887), `0.95` (0.3651) |
| `edge_contour_weight` | Dormant | 0.0000 | 0.0014 | 33.3% | `0.25` (0.4483), `0.5` (0.4474), `0.75` (0.4468) |
| `contour_quad_weight` | Dormant | 0.0000 | 0.0013 | 66.7% | `0.75` (0.4480), `0.5` (0.4478), `0.25` (0.4467) |
| `minimum_consensus_confidence` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.4475), `0.2` (0.4475), `0.35` (0.4475) |

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

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `projection_smooth_fraction` | Critical | 0.5794 | 0.2089 | 33.3% | `0.006` (0.4154), `0.012` (0.3870), `0.024` (0.2065) |
| `minimum_peak_prominence` | Critical | 0.3666 | 0.1633 | 66.7% | `1.05` (0.3959), `1.25` (0.3804), `1.6` (0.2326) |
| `edge_percentile` | Low | 0.0056 | 0.0205 | 33.3% | `90` (0.3491), `75` (0.3312), `82` (0.3286) |
| `angle_limit_degrees` | Low | 0.0040 | 0.0185 | 100.0% | `12` (0.3447), `8` (0.3380), `4` (0.3262) |
| `bbox_padding_fraction` | Low | 0.0036 | 0.0178 | 33.3% | `0.016` (0.3444), `0.008` (0.3378), `0` (0.3267) |
| `angle_step_degrees` | Dormant | 0.0001 | 0.0036 | 66.7% | `0.5` (0.3382), `2` (0.3361), `1` (0.3346) |

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
| Winner stabilized after | 2146 parameter sets |
| Winner stabilized | 20.9s (98% of search) |
| Near-best coverage (basin; within 0.0010) | 27 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 27 (1.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 1h 21m 59s | 1.0× |
| Non-dormant | 81 | 3.7% | 3m 2s | 27.0× |
| Low+ | 81 | 3.7% | 3m 2s | 27.0× |
| Moderate+ | 9 | 0.4% | 20.2s | 243.0× |
| Important+ | 9 | 0.4% | 20.2s | 243.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `canny_high` | Important | 0.1758 | 0.0643 | 33.3% | `220` (0.0643), `100` (0.0140), `150` (0.0000) |
| `hough_threshold` | Important | 0.1758 | 0.0643 | 33.3% | `120` (0.0643), `80` (0.0140), `50` (0.0000) |
| `canny_low` | Low | 0.0100 | 0.0140 | 100.0% | `30` (0.0354), `50` (0.0214), `80` (0.0214) |
| `axis_tolerance_degrees` | Low | 0.0024 | 0.0069 | 33.3% | `12` (0.0284), `18` (0.0284), `6` (0.0215) |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0009 | 33.3% | `0` (0.0265), `0.008` (0.0262), `0.016` (0.0256) |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0261), `0.16` (0.0261), `0.24` (0.0261) |
| `minimum_side_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0261), `0.18` (0.0261), `0.3` (0.0261) |

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
| Winner stabilized after | 70 parameter sets |
| Winner stabilized | 2.6s (10% of search) |
| Near-best coverage (basin; within 0.0010) | 34 (4.7%) |
| Equivalent-best configurations (within 0.0001) | 34 (4.7%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 6m 2s | 1.0× |
| Non-dormant | 243 | 33.3% | 2m 1s | 3.0× |
| Low+ | 243 | 33.3% | 2m 1s | 3.0× |
| Moderate+ | 81 | 11.1% | 40.3s | 9.0× |
| Important+ | 9 | 1.2% | 4.5s | 81.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_line_count` | Important | 0.2257 | 0.0613 | 100.0% | `2` (0.1082), `3` (0.1082), `5` (0.0469) |
| `maximum_component_area_fraction` | Important | 0.1129 | 0.0434 | 100.0% | `0.02` (0.1167), `0.005` (0.0733), `0.01` (0.0733) |
| `minimum_text_coverage_fraction` | Moderate | 0.0879 | 0.0383 | 100.0% | `0.04` (0.1005), `0.08` (0.1005), `0.14` (0.0623) |
| `line_join_fraction` | Moderate | 0.0610 | 0.0367 | 33.3% | `0.05` (0.1051), `0.03` (0.0897), `0.018` (0.0685) |
| `bbox_padding_fraction` | Low | 0.0027 | 0.0077 | 33.3% | `0.04` (0.0919), `0.02` (0.0873), `0.01` (0.0842) |
| `minimum_component_area_fraction` | Dormant | 0.0007 | 0.0035 | 66.7% | `1e-05` (0.0889), `2e-05` (0.0889), `5e-05` (0.0854) |

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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `background_threshold` | Dormant | 0.0000 | 0.0000 | 100.0% | `235` (0.0000), `245` (0.0000), `250` (0.0000) |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.0000), `0.008` (0.0000), `0.016` (0.0000) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.004` (0.0000), `0.01` (0.0000), `0.02` (0.0000) |
| `maximum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.9` (0.0000), `0.96` (0.0000), `0.98` (0.0000) |
| `minimum_border_background_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.0000), `0.55` (0.0000), `0.7` (0.0000) |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0000), `0.18` (0.0000), `0.28` (0.0000) |

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
| Detector runs completed | 27 of 27 | Successful detector regressions completed out of those scheduled. |
| Parameter sets evaluated | 1192908 | Total detector parameter configurations evaluated across all runs. |
| Golden Set page evaluations | 5964540 | Parameter sets multiplied by evaluated Golden Set pages. |
| Aggregate detector runtime | 21h 35m 14s | Sum of detector wall-clock runtimes; this is not the elapsed time experienced by the user. |
| Regression wall-clock span | 5d 17h 4m 50s | Earliest detector start through latest detector finish. |
| Effective detector concurrency | 0.16× | Aggregate detector runtime divided by regression wall-clock span. |
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
| Execution recommendation basis | runtime-index coherent build 31632454296 (27/27 detectors) |
| Pipeline start stagger | 0m |
| Runtime intelligence | `runtime-index.json` |
| Parallelism intelligence | `parallelism-index.json` |
| Calibration intelligence | `calibration-index.json` |

Detector pipelines pull continuously from one shared queue. Once a detector finishes, that pipeline immediately loads the next queued detector until the queue is empty.

| Queue | Detector | Pipeline | Estimated Runtime | Scheduling Basis |
|---:|---|---:|---:|---|
| 1 | GrabCut Segmentation (`grabcut`) | 1 | 6m 29s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 2 | Contour + GrabCut (`contour_grabcut`) | 2 | 4m 19s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 3 | GrabCut + Contour (`grabcut_contour`) | 3 | 4m 14s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 4 | Contour Quadrilateral (`contour_quad`) | 4 | 43.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 5 | Hough Line Borders (`hough`) | 4 | 30.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 6 | Consensus Quadrilateral (`consensus_quad`) | 4 | 23.4s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 7 | Contour + Projection (`contour_projection`) | 4 | 18.4s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 8 | Adaptive Radial Edge Search (`adaptive_radial_edge`) | 4 | 14.8s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 9 | Border Energy Validator (`border_energy`) | 4 | 12.9s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 10 | Joint Rectangle Voting (`joint_rectangle_vote`) | 4 | 12.3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 11 | Cross-Edge Contour (`cross_edge_contour`) | 4 | 11s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 12 | Edge-Supported Contour (`edge_contour`) | 4 | 9.7s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 13 | Line Segment Detector (`lsd`) | 4 | 8.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 14 | Distance Transform Detector (`distance_transform`) | 4 | 7.3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 15 | Radon Boundary Projection (`radon_boundary`) | 4 | 6s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 16 | Contour + Components (`contour_components`) | 4 | 5.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 17 | RANSAC Border Fit (`ransac`) | 4 | 3.5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 18 | Polar Boundary Voting (`polar_boundary_vote`) | 4 | 3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 19 | Star-Convex Boundary Optimization (`star_convex`) | 4 | 2.6s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 20 | Radial Edge Search (`radial_edge`) | 4 | 2.4s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 21 | Connected Components (`components`) | 4 | 1.9s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 22 | Text Flow Envelope (`text_flow`) | 4 | 1.5s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 23 | Convex Hull Detector (`convex_hull`) | 4 | 1.3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 24 | Gradient Boundary Voting (`gradient_vote`) | 4 | 1.3s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 25 | Distance-Transform Rectangle Proposal (`distance_transform_rect`) | 4 | 1.2s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 26 | Whitespace Frame (`whitespace_frame`) | 4 | 1.1s | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |
| 27 | Contour Envelope (`contour`) | 4 | 997 ms | runtime-index:mode+strategy+threads+dimension+golden-set+runner:score=126 |

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
| Exhaustive | 41d 12h 12m 13s |
| Non-dormant | 1d 59m 56s |
| Critical only | 13h 40m 1s |

\* Estimates scale each detector's measured runtime to the selected effect-size domain, apply the normal bounded shard plan, and simulate shard-level LPT placement across the recommended detector pipelines. Effect-group fallback remains active when a detector has no parameter sets in the requested group.

The reports below preserve the complete manifest, winner, baseline, calibration statistics, page analysis, and output inventory for each detector run.

[↑ Back to Navigation](#table-of-contents)

<a id="per-detector-regression-reports"></a>
<details open>
<summary><h3>Per-Detector Regression Reports</h3></summary>


[↑ Back to Navigation](#table-of-contents)

<a id="adaptive-radial-edge-search-adaptiveradialedge-2"></a>
<details>
<summary><strong>Adaptive Radial Edge Search (`adaptive_radial_edge`)</strong></summary>

**Status:** complete

## Run Information — adaptive_radial_edge

### Build Provenance

- Run ID: `run-20260807-024337`
- Detector: `adaptive_radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `fe8b3ad30d2b`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-07T02:43:37.359519+00:00`
- Finished: `2026-08-07T03:29:04.447203+00:00`
- Wall-clock elapsed: `45m 27s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

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
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — adaptive_radial_edge

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `5010d5b46516` | `5010d5b46516` | 0.9599 | 0.9440 | 0.0114 | 0.9599 | 0 | 58.6s |
| Baseline | `a132c2ac5e87` | `baseline` | 0.9329 | 0.8817 | 0.0344 | 0.9329 | 0 | 311 ms |

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
| Avg IoU improvements | 17 |
| Minimum IoU improvements | 5 |
| StdDev improvements | 7 |
| Total metric improvements | 29 |
| Parameter sets with improvements | 25 |
| Winner changes | 17 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 1 | 192 | 192 | `rh8-al97` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `5010d5b46516` | `5010d5b46516` | 0.9599 | 0.9440 | 0.0114 | +0.0000 | 0.9599 | 0 | 44m 25s | 95.93% |
| 2 | `1d2294489ce9` | `1d2294489ce9` | 0.9599 | 0.9440 | 0.0114 | +0.0000 | 0.9599 | 0 | 44m 28s | 96.04% |
| 3 | `21f3dd1c2b25` | `21f3dd1c2b25` | 0.9599 | 0.9440 | 0.0114 | +0.0000 | 0.9599 | 0 | 44m 34s | 96.33% |
| 4 | `27b17406868e` | `27b17406868e` | 0.9599 | 0.9440 | 0.0114 | +0.0000 | 0.9599 | 0 | 44m 29s | 96.08% |
| 5 | `f57ce0314a73` | `f57ce0314a73` | 0.9585 | 0.9327 | 0.0159 | -0.0013 | 0.9585 | 0 | 44m 40s | 96.57% |

## Page Analysis — adaptive_radial_edge

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `5010d5b46516` | 0.8817 | 0.9732 | +0.0915 | Improved |
| 5 | `5010d5b46516` | 0.9752 | 0.9727 | -0.0026 | Regressed |
| 6 | `5010d5b46516` | 0.9046 | 0.9440 | +0.0394 | Improved |
| 9 | `5010d5b46516` | 0.9480 | 0.9547 | +0.0066 | Improved |
| 10 | `5010d5b46516` | 0.9548 | 0.9548 | -0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 13 | `60fdd8b52754` | 43m | 92.17% |
| 14 | `de08abc2aae0` | 43m 8s | 92.56% |
| 15 | `19cf9dfb86e8` | 43m 24s | 93.31% |
| 16 | `850d2e9d4ff3` | 44m 20s | 95.72% |
| 17 (final) | `5010d5b46516` | 44m 25s | 95.93% |

Total winner changes: **17**.
Search completed in **45m 27s** wall-clock time.

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 5 | `5010d5b46516` | 0.9727 | Regressed |

## Calibration Intelligence — adaptive_radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260807-024337`
- Calibration schema: `1.1`
- Detector: `adaptive_radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/adaptive_radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `fe8b3ad30d2bca0c7eaee962efafbc7734377e19`
- Source commit: `6c13fee959c637aeb11c74cda7000b767e98ee45`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `192`

### Detector-Selection Intelligence

- Recommended parameter set: `5010d5b46516`
- Recommended parameter short name: `5010d5b46516`
- Best observed Avg IoU: `0.9599`
- Avg IoU Success: `0.9599`
- Worst Golden Set page (Min IoU): `0.9440`
- Page-to-page StdDev: `0.0114`
- Calibration evidence: `Medium`
- Dormant parameters: `area_weight, coarse_angle_step_degrees, maximum_area_fraction, minimum_area_fraction, minimum_ray_support, ray_count, rectangularity_weight, support_weight, side_assignment_tolerance_fraction, weak_side_support_fraction`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 10 of 16 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 6562 (100.0%) |
| Best Avg IoU | 0.9599 |
| Minimum Avg IoU | 0.7978 |
| Avg IoU StdDev | 0.0408 |
| Winner stabilized after | 6294 parameter sets |
| Winner stabilized | 44m 25s (96% of search) |
| Near-best coverage (basin; within 0.0010) | 4 (0.1%) |
| Equivalent-best configurations (within 0.0001) | 4 (0.1%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 4d 10h 48m 38s | 1.0× |
| Non-dormant | 729 | 11.1% | 11h 51m 58s | 9.0× |
| Low+ | 729 | 11.1% | 11h 51m 58s | 9.0× |
| Moderate+ | 9 | 0.1% | 8m 47s | 729.1× |
| Important+ | 9 | 0.1% | 8m 47s | 729.1× |
| Critical | 3 | 0.0% | 2m 56s | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `maximum_radius_fraction` | Critical | 0.7054 | 0.0796 | 33.3% | `0.72` (0.9245), `0.82` (0.9079), `0.62` (0.8449) |
| `minimum_radius_fraction` | Important | 0.1095 | 0.0318 | 33.3% | `0.24` (0.9110), `0.18` (0.8872), `0.12` (0.8792) |
| `maximum_refined_sides` | Low | 0.0257 | 0.0157 | 33.3% | `4` (0.8994), `2` (0.8944), `1` (0.8837) |
| `gaussian_sigma` | Low | 0.0123 | 0.0099 | 33.3% | `1.2` (0.8959), `1.8` (0.8954), `0.8` (0.8861) |
| `gradient_percentile` | Low | 0.0059 | 0.0075 | 33.3% | `70` (0.8967), `82` (0.8916), `90` (0.8892) |
| `refined_angle_step_degrees` | Low | 0.0054 | 0.0072 | 33.3% | `0.5` (0.8965), `1.5` (0.8917), `1` (0.8892) |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.35` (0.9329) |
| `coarse_angle_step_degrees` | Dormant | 0.0001 | 0.0000 | 0.0% | `3` (0.9329) |
| `maximum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.98` (0.9329) |
| `minimum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.18` (0.9329) |
| `minimum_ray_support` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.45` (0.9329) |
| `ray_count` | Dormant | 0.0001 | 0.0000 | 0.0% | `120` (0.9329) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `coarse_angle_step_degrees`, `maximum_area_fraction`, `minimum_area_fraction`, `minimum_ray_support`, `ray_count`, `rectangularity_weight`, `support_weight`, `side_assignment_tolerance_fraction`, `weak_side_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_radius_fraction` × `minimum_radius_fraction` | 0.8317 | 0.1263 | 6562 |
| `maximum_radius_fraction` × `gaussian_sigma` | 0.7381 | 0.0327 | 6562 |
| `maximum_radius_fraction` × `maximum_refined_sides` | 0.7334 | 0.0280 | 6562 |
| `minimum_radius_fraction` × `maximum_refined_sides` | 0.1371 | 0.0276 | 6562 |
| `maximum_radius_fraction` × `gradient_percentile` | 0.7223 | 0.0168 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8986 | 0.8114 | 0.9732 | 0.0435 | 100.0% |
| 5 | 0.9409 | 0.8344 | 0.9923 | 0.0506 | 100.0% |
| 6 | 0.8058 | 0.6268 | 0.9968 | 0.0989 | 100.0% |
| 9 | 0.8929 | 0.7202 | 0.9557 | 0.0587 | 100.0% |
| 10 | 0.9242 | 0.7940 | 0.9717 | 0.0463 | 100.0% |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | 0.9063 | 1 | 546 ms |
| Baseline | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | 0.9237 | 2 | 257 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `74e2112aac01` | `74e2112aac01` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 2.5s | 0.87% |
| 2 | `e6a92aa03adc` | `e6a92aa03adc` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 2.5s | 0.94% |
| 3 | `10122ecc688c` | `10122ecc688c` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 3s | 1.11% |
| 4 | `495c895fab0e` | `495c895fab0e` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 4.3s | 1.69% |
| 5 | `20154950810f` | `20154950810f` | 0.7250 | 0.0000 | 0.3651 | +0.0000 | 0.9063 | 1 | 4.1s | 1.60% |

## Page Analysis — border_energy

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `74e2112aac01` | 0.0000 | 0.8542 | +0.8542 | Recovered |
| 5 | `74e2112aac01` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `74e2112aac01` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `74e2112aac01` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `74e2112aac01` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 6 | `74e2112aac01` | 0.0000 | No polygon found |

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

### Detector-Selection Intelligence

- Recommended parameter set: `74e2112aac01`
- Recommended parameter short name: `74e2112aac01`
- Best observed Avg IoU: `0.7250`
- Avg IoU Success: `0.9063`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3651`
- Calibration evidence: `Medium`
- Dormant parameters: `consistency_weight, contour_weight, energy_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_side_consistency` | Critical | 0.5951 | 0.2495 | 33.3% | `0.3` (0.6554), `0.45` (0.5542), `0.6` (0.4059) |
| `band_fraction` | Important | 0.1173 | 0.1102 | 100.0% | `0.015` (0.5985), `0.008` (0.5287), `0.004` (0.4883) |
| `gaussian_sigma` | Low | 0.0252 | 0.0459 | 100.0% | `1.8` (0.5683), `0.8` (0.5248), `1.2` (0.5224) |
| `minimum_border_energy` | Low | 0.0020 | 0.0127 | 100.0% | `0.1` (0.5427), `0.05` (0.5427), `0.18` (0.5301) |
| `consistency_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.15` (0.5542) |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.45` (0.5542) |
| `energy_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.5385), `0.3` (0.5385), `0.5` (0.5385) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.5385), `0.03` (0.5385), `0.06` (0.5385) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.5385), `0.08` (0.5385), `0.2` (0.5385) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.5385), `0.45` (0.5385), `0.7` (0.5385) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | 0.7897 | 0 | 21 ms |
| Baseline | `4e09dc84fa8a` | `baseline` | 0.7185 | 0.2413 | 0.2967 | 0.7185 | 0 | 17 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `f1929c8e2655` | `f1929c8e2655` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 578 ms | 1.27% |
| 2 | `6a55e49277e7` | `6a55e49277e7` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 630 ms | 1.40% |
| 3 | `62e19d69cdf6` | `62e19d69cdf6` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 660 ms | 1.46% |
| 4 | `966b20b76507` | `966b20b76507` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 688 ms | 1.53% |
| 5 | `9230a0393357` | `9230a0393357` | 0.7897 | 0.5725 | 0.1665 | +0.0000 | 0.7897 | 0 | 741 ms | 1.68% |

## Page Analysis — components

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `f1929c8e2655` | 0.9734 | 0.9533 | -0.0201 | Regressed |
| 5 | `f1929c8e2655` | 0.4973 | 0.5725 | +0.0752 | Improved |
| 6 | `f1929c8e2655` | 0.2413 | 0.6018 | +0.3605 | Improved |
| 9 | `f1929c8e2655` | 0.9314 | 0.9018 | -0.0296 | Regressed |
| 10 | `f1929c8e2655` | 0.9491 | 0.9192 | -0.0299 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `732d1fd40ae7` | 101 ms | 0.01% |
| 2 | `b6a644d99d2e` | 102 ms | 0.01% |
| 3 (final) | `2f8c682579f8` | 204 ms | 0.28% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `f1929c8e2655` | 0.9533 | Regressed |
| 9 | `f1929c8e2655` | 0.9018 | Regressed |
| 10 | `f1929c8e2655` | 0.9192 | Regressed |

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

### Detector-Selection Intelligence

- Recommended parameter set: `f1929c8e2655`
- Recommended parameter short name: `f1929c8e2655`
- Best observed Avg IoU: `0.7897`
- Avg IoU Success: `0.7897`
- Worst Golden Set page (Min IoU): `0.5725`
- Page-to-page StdDev: `0.1665`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, minimum_component_area_px`
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

Calibration evidence basis: complete exhaustive coverage, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `morphology_dilate_fraction` | Critical | 0.4776 | 0.0693 | 33.3% | `0.03` (0.7658), `0.015` (0.7266), `0.008` (0.6965) |
| `merge_gap_fraction` | Moderate | 0.0940 | 0.0269 | 66.7% | `0.06` (0.7474), `0.035` (0.7209), `0.02` (0.7206) |
| `minimum_selected_area_fraction` | Moderate | 0.0620 | 0.0217 | 100.0% | `0.02` (0.7369), `0.04` (0.7369), `0.07` (0.7152) |
| `minimum_component_area_fraction` | Moderate | 0.0371 | 0.0179 | 33.3% | `0.00075` (0.7408), `0.0015` (0.7253), `0.003` (0.7229) |
| `bbox_padding_fraction` | Moderate | 0.0362 | 0.0183 | 33.3% | `0` (0.7373), `0.005` (0.7328), `0.015` (0.7189) |
| `merge_area_ratio` | Low | 0.0259 | 0.0161 | 33.3% | `0.01` (0.7372), `0.02` (0.7306), `0.05` (0.7211) |
| `morphology_close_fraction` | Low | 0.0120 | 0.0096 | 100.0% | `0.016` (0.7360), `0.004` (0.7265), `0.008` (0.7265) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.7297), `0.12` (0.7296), `0.18` (0.7296) |
| `minimum_component_area_px` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.7296), `25` (0.7296), `50` (0.7296) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | 0.9213 | 2 | 1.4s |
| Baseline | `dce471449373` | `baseline` | 0.5513 | 0.0000 | 0.4513 | 0.9188 | 2 | 571 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 4.9s | 16.53% |
| 2 | `d3afdfd96e35` | `d3afdfd96e35` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 4.9s | 15.70% |
| 3 | `a00dcf94f01e` | `a00dcf94f01e` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 4.9s | 17.36% |
| 4 | `855195437d31` | `855195437d31` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 7.7s | 32.23% |
| 5 | `99d0beb98285` | `99d0beb98285` | 0.5528 | 0.0000 | 0.4526 | +0.0000 | 0.9213 | 2 | 7.7s | 33.88% |

## Page Analysis — consensus_quad

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `f387da7ebb7e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `f387da7ebb7e` | 0.8616 | 0.8616 | +0.0000 | Unchanged |
| 6 | `f387da7ebb7e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `f387da7ebb7e` | 0.9647 | 0.9636 | -0.0011 | Regressed |
| 10 | `f387da7ebb7e` | 0.9302 | 0.9386 | +0.0085 | Improved |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `a0704ed94d82` | 4.5s | 15.29% |
| 2 (final) | `d3afdfd96e35` | 4.9s | 15.70% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `f387da7ebb7e` | 0.0000 | No polygon found |
| 6 | `f387da7ebb7e` | 0.0000 | No polygon found |
| 9 | `f387da7ebb7e` | 0.9636 | Regressed |

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

### Detector-Selection Intelligence

- Recommended parameter set: `f387da7ebb7e`
- Recommended parameter short name: `f387da7ebb7e`
- Best observed Avg IoU: `0.5528`
- Avg IoU Success: `0.9213`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4526`
- Calibration evidence: `Medium`
- Dormant parameters: `edge_contour_weight, contour_quad_weight, minimum_consensus_confidence`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `maximum_mean_corner_distance_fraction` | Critical | 0.3999 | 0.1235 | 66.7% | `0.025` (0.4887), `0.04` (0.4887), `0.015` (0.3651) |
| `minimum_polygon_iou` | Critical | 0.3999 | 0.1235 | 66.7% | `0.8` (0.4887), `0.9` (0.4887), `0.95` (0.3651) |
| `edge_contour_weight` | Dormant | 0.0000 | 0.0014 | 33.3% | `0.25` (0.4483), `0.5` (0.4474), `0.75` (0.4468) |
| `contour_quad_weight` | Dormant | 0.0000 | 0.0013 | 66.7% | `0.75` (0.4480), `0.5` (0.4478), `0.25` (0.4467) |
| `minimum_consensus_confidence` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.4475), `0.2` (0.4475), `0.35` (0.4475) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | 34 ms |
| Baseline | `6019a18e4c4e` | `baseline` | 0.6722 | 0.0000 | 0.3846 | 0.8403 | 1 | 9 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 468 ms | 10.30% |
| 2 | `fe1e051ea449` | `fe1e051ea449` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 478 ms | 10.64% |
| 3 | `bf0386f44c6e` | `bf0386f44c6e` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 492 ms | 11.05% |
| 4 | `2cbcf16dd63a` | `2cbcf16dd63a` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 890 ms | 21.28% |
| 5 | `3fe11d0f3e41` | `3fe11d0f3e41` | 0.8498 | 0.5457 | 0.1589 | +0.0000 | 0.8498 | 0 | 907 ms | 21.69% |

## Page Analysis — contour

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `7aed2fc501c5` | 0.9648 | 0.9734 | +0.0086 | Improved |
| 5 | `7aed2fc501c5` | 0.4784 | 0.5457 | +0.0673 | Improved |
| 6 | `7aed2fc501c5` | 0.0000 | 0.8392 | +0.8392 | Recovered |
| 9 | `7aed2fc501c5` | 0.9585 | 0.9390 | -0.0195 | Regressed |
| 10 | `7aed2fc501c5` | 0.9593 | 0.9517 | -0.0076 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `a20447ccca1e` | 79 ms | 0.21% |
| 2 | `2f4c8ab8f1e0` | 85 ms | 0.48% |
| 3 | `a577ea13a69c` | 460 ms | 10.02% |
| 4 (final) | `7aed2fc501c5` | 468 ms | 10.30% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 9 | `7aed2fc501c5` | 0.9390 | Regressed |
| 10 | `7aed2fc501c5` | 0.9517 | Regressed |

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

### Detector-Selection Intelligence

- Recommended parameter set: `7aed2fc501c5`
- Recommended parameter short name: `7aed2fc501c5`
- Best observed Avg IoU: `0.8498`
- Avg IoU Success: `0.8498`
- Worst Golden Set page (Min IoU): `0.5457`
- Page-to-page StdDev: `0.1589`
- Calibration evidence: `Medium`
- Dormant parameters: `close_iterations, close_kernel_fraction, minimum_contour_area_fraction, polygon_epsilon_fraction, rectangularity_weight`
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

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `merge_fragmented_contours` | Critical | 0.9954 | 0.1691 | 50.0% | `true` (0.8377), `false` (0.6686) |
| `bbox_padding_fraction` | Low | 0.0023 | 0.0091 | 33.3% | `0.005` (0.7565), `0` (0.7555), `0.015` (0.7474) |
| `close_iterations` | Dormant | 0.0004 | 0.0035 | 33.3% | `2` (0.7555), `0` (0.7519), `1` (0.7519) |
| `close_kernel_fraction` | Dormant | 0.0004 | 0.0035 | 33.3% | `0.018` (0.7555), `0` (0.7519), `0.008` (0.7519) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.06` (0.7531), `0.12` (0.7531), `0.2` (0.7531) |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.7531), `0.018` (0.7531), `0.035` (0.7531) |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.7531), `0.25` (0.7531), `0.4` (0.7531) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | 60 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | unknown | unknown |
| 2 | `6931e3aea38a` | `6931e3aea38a` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 255 ms | 0.01% |
| 3 | `4339c3f69581` | `4339c3f69581` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 258 ms | 0.02% |
| 4 | `91d7206d1476` | `91d7206d1476` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 287 ms | 0.05% |
| 5 | `81a0687b7bc1` | `81a0687b7bc1` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0.8617 | 0 | 264 ms | 0.02% |

## Page Analysis — contour_components

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.8540 | 0.8540 | +0.0000 | Unchanged |
| 5 | `baseline` | 0.8616 | 0.8616 | +0.0000 | Unchanged |
| 6 | `baseline` | 0.7572 | 0.7572 | +0.0000 | Unchanged |
| 9 | `baseline` | 0.9636 | 0.9636 | +0.0000 | Unchanged |
| 10 | `baseline` | 0.8719 | 0.8719 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

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

### Detector-Selection Intelligence

- Recommended parameter set: `14818b491952`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8617`
- Avg IoU Success: `0.8617`
- Worst Golden Set page (Min IoU): `0.7572`
- Page-to-page StdDev: `0.0655`
- Calibration evidence: `High`
- Dormant parameters: `component_close_fraction, component_dilate_fraction, component_merge_gap_fraction, component_minimum_area_fraction, component_weight, epsilon_max_fraction, minimum_component_score, minimum_contour_area_fraction, minimum_rectangularity, angle_weight, area_weight, close_iterations, close_kernel_fraction, component_bbox_padding_fraction, component_merge_area_ratio, component_minimum_area_px, component_minimum_bbox_area_fraction, component_minimum_selected_area_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight`
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

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `component_close_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.004` (0.8617), `0.012` (0.8617), `0.008` (0.8617) |
| `component_dilate_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.008` (0.8617), `0.025` (0.8617), `0.015` (0.8617) |
| `component_merge_gap_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.06` (0.8617), `0.035` (0.8617) |
| `component_minimum_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.0008` (0.8617), `0.003` (0.8617), `0.0015` (0.8617) |
| `component_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.25` (0.8617), `0.55` (0.8617), `0.4` (0.8617) |
| `epsilon_max_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8617), `0.06` (0.8617), `0.04` (0.8617) |
| `minimum_component_score` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.02` (0.8617), `0.12` (0.8617), `0.05` (0.8617) |
| `minimum_contour_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.08` (0.8617), `0.18` (0.8617), `0.12` (0.8617) |
| `minimum_rectangularity` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.45` (0.8617), `0.7` (0.8617), `0.55` (0.8617) |
| `angle_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.15` (0.8617) |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.25` (0.8617) |
| `close_iterations` | Dormant | 0.0001 | 0.0000 | 100.0% | `1` (0.8617) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 28.3s |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | unknown | unknown |
| 2 | `42fc63229bb3` | `42fc63229bb3` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 38.7s | 0.08% |
| 3 | `72f0d747f696` | `72f0d747f696` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 53.5s | 0.20% |
| 4 | `d4633ac4cc93` | `d4633ac4cc93` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 38.2s | 0.02% |
| 5 | `e35f2d10bf3d` | `e35f2d10bf3d` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 56.9s | 0.26% |

## Page Analysis — contour_grabcut

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

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

### Detector-Selection Intelligence

- Recommended parameter set: `3eec8a03f1de`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `High`
- Dormant parameters: `agreement_weight, contour_epsilon_max_fraction, contour_minimum_area_fraction, contour_minimum_rectangularity, contour_weight, grabcut_border_fraction, grabcut_erosion_kernel_fraction, grabcut_iterations, grabcut_weight, minimum_agreement_iou, require_grabcut`
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

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `agreement_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) |
| `contour_epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768), `0.06` (0.8768) |
| `contour_minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768), `0.18` (0.8768) |
| `contour_minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768), `0.7` (0.8768) |
| `contour_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8768) |
| `grabcut_border_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.01` (0.8768), `0.02` (0.8768), `0.03` (0.8768) |
| `grabcut_erosion_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8768) |
| `grabcut_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8768), `3` (0.8768), `5` (0.8768) |
| `grabcut_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.25` (0.8768), `0.35` (0.8768) |
| `minimum_agreement_iou` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.3` (0.8768), `0.5` (0.8768) |
| `require_grabcut` | Dormant | 0.0000 | 0.0000 | 100.0% | `false` (0.8768) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 458 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | unknown | unknown |
| 2 | `172304831b2e` | `172304831b2e` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.6s | 0.18% |
| 3 | `b71b6267963a` | `b71b6267963a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.5s | 0.14% |
| 4 | `8c229faefd09` | `8c229faefd09` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.6s | 0.17% |
| 5 | `3315664f787d` | `3315664f787d` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.5s | 0.15% |

## Page Analysis — contour_projection

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

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

### Detector-Selection Intelligence

- Recommended parameter set: `0cd13eb1a471`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `High`
- Dormant parameters: `angle_weight, area_weight, close_iterations, close_kernel_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_projection_score, minimum_rectangularity`
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

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `projection_threshold_block_fraction` | Important | 0.1600 | 0.0183 | 100.0% | `0.05` (0.8768), `0.08` (0.8768), `0.12` (0.8586) |
| `projection_weight` | Moderate | 0.0933 | 0.0152 | 100.0% | `0.2` (0.8768), `0.3` (0.8738), `0.4` (0.8616) |
| `projection_threshold_c` | Moderate | 0.0400 | 0.0091 | 100.0% | `13` (0.8738), `5` (0.8738), `9` (0.8646) |
| `projection_margin_fraction` | Low | 0.0133 | 0.0061 | 100.0% | `0.06` (0.8738), `0.1` (0.8707), `0.03` (0.8677) |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8768) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8768) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8768) |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 100.0% | `9` (0.8768) |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 100.0% | `true` (0.8768) |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8768) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | 0.8874 | 0 | 399 ms |
| Baseline | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 206 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `49095b866d0d` | `49095b866d0d` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 57.3s | 0.16% |
| 2 | `fe0372f03bb1` | `fe0372f03bb1` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 58.5s | 0.16% |
| 3 | `b75e8d4f5261` | `b75e8d4f5261` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 58.7s | 0.16% |
| 4 | `1d74604d7956` | `1d74604d7956` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 59.2s | 0.16% |
| 5 | `c542268fe001` | `c542268fe001` | 0.8874 | 0.7589 | 0.0731 | +0.0000 | 0.8874 | 0 | 59.4s | 0.16% |

## Page Analysis — contour_quad

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `49095b866d0d` | 0.8542 | 0.9069 | +0.0527 | Improved |
| 5 | `49095b866d0d` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `49095b866d0d` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `49095b866d0d` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `49095b866d0d` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 (final) | `fe6f0b79695c` | 320 ms | 0.00% |

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

### Detector-Selection Intelligence

- Recommended parameter set: `49095b866d0d`
- Recommended parameter short name: `49095b866d0d`
- Best observed Avg IoU: `0.8874`
- Avg IoU Success: `0.8874`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0731`
- Calibration evidence: `Medium`
- Dormant parameters: `close_kernel_fraction, close_iterations, edge_support_weight, edge_support_dilation_fraction, area_weight, angle_weight, epsilon_min_fraction, epsilon_steps, minimum_contour_area_fraction, minimum_rectangularity, rectangularity_weight`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `merge_fragmented_contours` | Critical | 0.7000 | 0.1995 | 50.0% | `true` (0.8241), `false` (0.6246) |
| `epsilon_max_fraction` | Critical | 0.2737 | 0.1323 | 66.7% | `0.04` (0.7685), `0.06` (0.7685), `0.025` (0.6362) |
| `close_kernel_fraction` | Dormant | 0.0001 | 0.0027 | 100.0% | `0.018` (0.7260), `0.008` (0.7237), `0` (0.7233) |
| `close_iterations` | Dormant | 0.0001 | 0.0025 | 100.0% | `2` (0.7259), `1` (0.7238), `0` (0.7233) |
| `edge_support_weight` | Dormant | 0.0001 | 0.0024 | 100.0% | `0.25` (0.7256), `0.15` (0.7242), `0.1` (0.7233) |
| `edge_support_dilation_fraction` | Dormant | 0.0001 | 0.0022 | 100.0% | `0.008` (0.7256), `0.004` (0.7240), `0.002` (0.7234) |
| `area_weight` | Dormant | 0.0001 | 0.0021 | 100.0% | `0.25` (0.7255), `0.35` (0.7242), `0.45` (0.7234) |
| `angle_weight` | Dormant | 0.0000 | 0.0012 | 100.0% | `0.3` (0.7249), `0.2` (0.7244), `0.1` (0.7237) |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.004` (0.7244), `0.008` (0.7244), `0.012` (0.7244) |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 100.0% | `13` (0.7244), `5` (0.7244), `9` (0.7244) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.06` (0.7244), `0.12` (0.7244), `0.2` (0.7244) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.7244), `0.55` (0.7244), `0.7` (0.7244) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | 0.9156 | 1 | 176 ms |
| Baseline | `74f5cad7945a` | `baseline` | 0.6633 | 0.0000 | 0.3670 | 0.8291 | 1 | 12 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `04fd0a6e4bc2` | `04fd0a6e4bc2` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 280 ms | 7.69% |
| 2 | `7fe4e99339c2` | `7fe4e99339c2` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 320 ms | 10.93% |
| 3 | `58b1b96bcfa4` | `58b1b96bcfa4` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 340 ms | 12.26% |
| 4 | `f9049ebaa534` | `f9049ebaa534` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 327 ms | 11.21% |
| 5 | `ae8e0d8d384d` | `ae8e0d8d384d` | 0.7325 | 0.0000 | 0.3683 | +0.0000 | 0.9156 | 1 | 337 ms | 11.85% |

## Page Analysis — convex_hull

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `04fd0a6e4bc2` | 0.8668 | 0.8668 | +0.0000 | Unchanged |
| 5 | `04fd0a6e4bc2` | 0.5316 | 0.8776 | +0.3460 | Improved |
| 6 | `04fd0a6e4bc2` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `04fd0a6e4bc2` | 0.9585 | 0.9585 | +0.0000 | Unchanged |
| 10 | `04fd0a6e4bc2` | 0.9593 | 0.9593 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 (final) | `c9b4a5f645ab` | 151 ms | 0.05% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 6 | `04fd0a6e4bc2` | 0.0000 | No polygon found |

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

### Detector-Selection Intelligence

- Recommended parameter set: `04fd0a6e4bc2`
- Recommended parameter short name: `04fd0a6e4bc2`
- Best observed Avg IoU: `0.7325`
- Avg IoU Success: `0.9156`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3683`
- Calibration evidence: `Medium`
- Dormant parameters: `close_iterations, close_kernel_fraction, minimum_hull_area_fraction, polygon_epsilon_fraction`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_solidity` | Critical | 0.3159 | 0.0595 | 66.7% | `0.35` (0.6854), `0.55` (0.6854), `0.75` (0.6260) |
| `minimum_fragment_area_fraction` | Moderate | 0.0301 | 0.0211 | 33.3% | `0.0015` (0.6769), `0.0002` (0.6641), `0.0005` (0.6558) |
| `bbox_padding_fraction` | Low | 0.0213 | 0.0174 | 33.3% | `0` (0.6732), `0.008` (0.6679), `0.016` (0.6558) |
| `close_iterations` | Dormant | 0.0000 | 0.0003 | 100.0% | `0` (0.6657), `1` (0.6657), `2` (0.6654) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0003 | 100.0% | `0` (0.6657), `0.008` (0.6657), `0.016` (0.6654) |
| `minimum_hull_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.6656), `0.16` (0.6656), `0.24` (0.6656) |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.012` (0.6656), `0.025` (0.6656), `0.05` (0.6656) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 214 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | unknown | unknown |
| 2 | `0bd97323ddd6` | `0bd97323ddd6` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 679 ms | 0.08% |
| 3 | `491385b9c30f` | `491385b9c30f` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 722 ms | 0.14% |
| 4 | `3f36d70252ce` | `3f36d70252ce` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 661 ms | 0.05% |
| 5 | `ebfb7feac827` | `ebfb7feac827` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.2s | 0.40% |

## Page Analysis — cross_edge_contour

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.8542 | 0.8542 | +0.0000 | Unchanged |
| 5 | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `baseline` | 0.7589 | 0.7589 | +0.0000 | Unchanged |
| 9 | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `9739acebc0a5` | 641 ms | 0.02% |
| 2 (final) | `0474de95ff10` | 659 ms | 0.03% |

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

### Detector-Selection Intelligence

- Recommended parameter set: `a5450e58ec9e`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Medium`
- Dormant parameters: `contour_weight, polarity_weight, contrast_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity, samples_per_edge`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_polarity_consistency` | Critical | 0.9288 | 0.4950 | 50.0% | `0.55` (0.8768), `0.5` (0.8600), `0.65` (0.6676) |
| `sample_offset_fraction` | Low | 0.0296 | 0.0744 | 100.0% | `0.008` (0.6613), `0.014` (0.6612), `0.004` (0.5869) |
| `minimum_cross_edge_contrast` | Low | 0.0015 | 0.0170 | 100.0% | `0.045` (0.6422), `0.02` (0.6421), `0.08` (0.6252) |
| `contour_weight` | Dormant | 0.0002 | 0.0000 | 100.0% | `0.45` (0.8768) |
| `polarity_weight` | Dormant | 0.0002 | 0.0000 | 100.0% | `0.15` (0.8768) |
| `contrast_weight` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.4` (0.6366), `0.3` (0.6365), `0.5` (0.6365) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.04` (0.6366), `0.03` (0.6365), `0.06` (0.6365) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.12` (0.6366), `0.08` (0.6365), `0.18` (0.6365) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0001 | 100.0% | `0.55` (0.6366), `0.45` (0.6365), `0.7` (0.6365) |
| `samples_per_edge` | Dormant | 0.0000 | 0.0001 | 100.0% | `48` (0.6366), `24` (0.6365), `72` (0.6365) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | 0.8388 | 0 | 2.5s |
| Baseline | `8b59bc493e1f` | `baseline` | 0.7593 | 0.4357 | 0.2472 | 0.7593 | 0 | 283 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `e66a7546e1a7` | `e66a7546e1a7` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 2.15% |
| 2 | `8e57ff70b94c` | `8e57ff70b94c` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 4.39% |
| 3 | `d0c1acdb2940` | `d0c1acdb2940` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 2.70% |
| 4 | `9e2cea4f0e56` | `9e2cea4f0e56` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 4.85% |
| 5 | `ae46f8953bd6` | `ae46f8953bd6` | 0.8388 | 0.5001 | 0.1745 | +0.0000 | 0.8388 | 0 | 5.1s | 3.71% |

## Page Analysis — distance_transform

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `e66a7546e1a7` | 0.9648 | 0.9734 | +0.0086 | Improved |
| 5 | `e66a7546e1a7` | 0.4784 | 0.5001 | +0.0217 | Improved |
| 6 | `e66a7546e1a7` | 0.4357 | 0.8475 | +0.4118 | Improved |
| 9 | `e66a7546e1a7` | 0.9585 | 0.9276 | -0.0309 | Regressed |
| 10 | `e66a7546e1a7` | 0.9593 | 0.9454 | -0.0139 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `823d0ace1a0f` | 3.1s | 0.09% |
| 2 (final) | `677a2d78be31` | 4.4s | 0.46% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 9 | `e66a7546e1a7` | 0.9276 | Regressed |
| 10 | `e66a7546e1a7` | 0.9454 | Regressed |

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

### Detector-Selection Intelligence

- Recommended parameter set: `e66a7546e1a7`
- Recommended parameter short name: `e66a7546e1a7`
- Best observed Avg IoU: `0.8388`
- Avg IoU Success: `0.8388`
- Worst Golden Set page (Min IoU): `0.5001`
- Page-to-page StdDev: `0.1745`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction`
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

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `distance_threshold_fraction` | Critical | 0.5293 | 0.1276 | 33.3% | `0.1` (0.8039), `0.18` (0.7195), `0.3` (0.6763) |
| `minimum_core_area_fraction` | Important | 0.1010 | 0.0534 | 100.0% | `0.004` (0.7545), `0.01` (0.7442), `0.025` (0.7011) |
| `minimum_rectangularity` | Moderate | 0.0335 | 0.0283 | 100.0% | `0.35` (0.7427), `0.5` (0.7427), `0.7` (0.7144) |
| `minimum_component_core_overlap` | Moderate | 0.0319 | 0.0289 | 66.7% | `0.03` (0.7438), `0.08` (0.7410), `0.16` (0.7149) |
| `close_kernel_fraction` | Low | 0.0160 | 0.0215 | 100.0% | `0.016` (0.7421), `0.008` (0.7371), `0` (0.7205) |
| `bbox_padding_fraction` | Low | 0.0042 | 0.0102 | 33.3% | `0` (0.7367), `0.008` (0.7364), `0.016` (0.7266) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0004 | 100.0% | `0.1` (0.7335), `0.16` (0.7331), `0.24` (0.7331) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | 0.7243 | 0 | 410 ms |
| Baseline | `e04459bcb474` | `baseline` | 0.6347 | 0.0000 | 0.3534 | 0.7933 | 1 | 32 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `0a8482550c35` | `0a8482550c35` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 836 ms | 82.01% |
| 2 | `43eedb6484a7` | `43eedb6484a7` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 881 ms | 98.21% |
| 3 | `b42ab476afc9` | `b42ab476afc9` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 844 ms | 84.75% |
| 4 | `1ce89ec0c98a` | `1ce89ec0c98a` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 810 ms | 74.45% |
| 5 | `7e13cb642dbe` | `7e13cb642dbe` | 0.7243 | 0.4499 | 0.2245 | +0.0000 | 0.7243 | 0 | 791 ms | 70.47% |

## Page Analysis — distance_transform_rect

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `0a8482550c35` | 0.8697 | 0.9520 | +0.0823 | Improved |
| 5 | `0a8482550c35` | 0.4937 | 0.4499 | -0.0438 | Regressed |
| 6 | `0a8482550c35` | 0.0000 | 0.4523 | +0.4523 | Recovered |
| 9 | `0a8482550c35` | 0.8916 | 0.8884 | -0.0032 | Regressed |
| 10 | `0a8482550c35` | 0.9183 | 0.8788 | -0.0395 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 3 | `5638d44f7565` | 544 ms | 14.42% |
| 4 | `e74ab4635629` | 685 ms | 30.49% |
| 5 | `42564449a7c9` | 759 ms | 62.77% |
| 6 | `cacd39184a6d` | 778 ms | 67.31% |
| 7 (final) | `7e13cb642dbe` | 791 ms | 70.47% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 5 | `0a8482550c35` | 0.4499 | Poor match; Regressed |
| 6 | `0a8482550c35` | 0.4523 | Poor match |
| 9 | `0a8482550c35` | 0.8884 | Regressed |
| 10 | `0a8482550c35` | 0.8788 | Regressed |

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

### Detector-Selection Intelligence

- Recommended parameter set: `0a8482550c35`
- Recommended parameter short name: `0a8482550c35`
- Best observed Avg IoU: `0.7243`
- Avg IoU Success: `0.7243`
- Worst Golden Set page (Min IoU): `0.4499`
- Page-to-page StdDev: `0.2245`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `proposal_expansion_fraction` | Moderate | 0.0415 | 0.0184 | 33.3% | `0.06` (0.6160), `0.12` (0.6149), `0.22` (0.5975) |
| `minimum_mask_coverage` | Moderate | 0.0411 | 0.0199 | 33.3% | `0.06` (0.6210), `0.12` (0.6064), `0.22` (0.6011) |
| `minimum_core_area_fraction` | Low | 0.0204 | 0.0126 | 66.7% | `0.002` (0.6137), `0.006` (0.6137), `0.015` (0.6011) |
| `distance_threshold_fraction` | Low | 0.0192 | 0.0140 | 33.3% | `0.18` (0.6168), `0.3` (0.6090), `0.1` (0.6027) |
| `bbox_padding_fraction` | Low | 0.0018 | 0.0042 | 33.3% | `0.016` (0.6114), `0.008` (0.6099), `0` (0.6072) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.6095), `0.14` (0.6095), `0.22` (0.6095) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 1s |
| Baseline | `cc91b22426bb` | `baseline` | 0.5392 | 0.0000 | 0.4417 | 0.8986 | 2 | 392 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.5s | 0.21% |
| 2 | `723797320a20` | `723797320a20` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 1.5s | 0.15% |
| 3 | `45f853e88afb` | `45f853e88afb` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 2s | 1.14% |
| 4 | `d3cfbe72a64d` | `d3cfbe72a64d` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 7s | 8.53% |
| 5 | `79f1c310cb10` | `79f1c310cb10` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | 8s | 10.11% |

## Page Analysis — edge_contour

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `4e5bc37a649a` | 0.0000 | 0.8542 | +0.8542 | Recovered |
| 5 | `4e5bc37a649a` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `4e5bc37a649a` | 0.0000 | 0.7589 | +0.7589 | Recovered |
| 9 | `4e5bc37a649a` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `4e5bc37a649a` | 0.8703 | 0.9454 | +0.0751 | Improved |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `335dc91690c9` | 1.1s | 0.01% |
| 2 (final) | `ff097da4d65f` | 1.3s | 0.02% |

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

### Detector-Selection Intelligence

- Recommended parameter set: `4e5bc37a649a`
- Recommended parameter short name: `4e5bc37a649a`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Medium`
- Dormant parameters: `angle_weight, area_weight, close_iterations, close_kernel_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight, edge_support_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_edge_support` | Critical | 0.3207 | 0.3412 | 66.7% | `0.05` (0.6504), `0.12` (0.4293), `0.2` (0.3092) |
| `edge_support_dilation_fraction` | Important | 0.1807 | 0.2557 | 100.0% | `0.01` (0.5775), `0.006` (0.4895), `0.003` (0.3218) |
| `minimum_segment_length_fraction` | Important | 0.1417 | 0.2229 | 33.3% | `0.03` (0.5908), `0.06` (0.4301), `0.1` (0.3679) |
| `lsd_scale` | Important | 0.1119 | 0.1922 | 66.7% | `0.6` (0.5390), `0.8` (0.5031), `1` (0.3468) |
| `lsd_refine_mode` | Moderate | 0.0518 | 0.1136 | 100.0% | `none` (0.5197), `std` (0.4062) |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.5392) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.5392) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.5392) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.5392) |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.5392) |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 0.0% | `9` (0.5392) |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 0.0% | `true` (0.5392) |

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

- Run ID: `run-20260811-020009`
- Detector: `grabcut`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T19:36:27.706580+00:00`
- Finished: `2026-08-11T02:00:07.695621+00:00`
- Wall-clock elapsed: `6h 23m 40s`
- Est. serial runtime: `4d 33m 16s`
- Effective acceleration: `15.10×`

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
- `raw/results.csv` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — grabcut

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `f33aa4421393` | `f33aa4421393` | 0.9137 | 0.7378 | 0.0886 | 0.9137 | 0 | 34.5s |
| Baseline | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 28.3s |

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
| Winner changes | 8 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 4 | 4 | 16 | `rh8-al323` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `f33aa4421393` | `f33aa4421393` | 0.9137 | 0.7378 | 0.0886 | +0.0000 | 0.9137 | 0 | 2h 27m 7s | 38.37% |
| 2 | `186fbda445d1` | `186fbda445d1` | 0.9137 | 0.7378 | 0.0886 | +0.0000 | 0.9137 | 0 | 4h 43s | 62.82% |
| 3 | `cde08eda0c81` | `cde08eda0c81` | 0.9137 | 0.7378 | 0.0886 | +0.0000 | 0.9137 | 0 | 4h 52m 42s | 76.37% |
| 4 | `e0ac09baec7d` | `e0ac09baec7d` | 0.9137 | 0.7378 | 0.0886 | +0.0000 | 0.9137 | 0 | 4h 52m 43s | 76.37% |
| 5 | `b2c33e3b1b43` | `b2c33e3b1b43` | 0.9137 | 0.7378 | 0.0886 | +0.0000 | 0.9137 | 0 | 4h 53m 16s | 76.50% |

## Page Analysis — grabcut

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `f33aa4421393` | 0.9568 | 0.9578 | +0.0010 | Improved |
| 5 | `f33aa4421393` | 0.5532 | 0.9755 | +0.4223 | Improved |
| 6 | `f33aa4421393` | 0.6683 | 0.7378 | +0.0695 | Improved |
| 9 | `f33aa4421393` | 0.9422 | 0.9433 | +0.0010 | Improved |
| 10 | `f33aa4421393` | 0.9447 | 0.9540 | +0.0093 | Improved |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 4 | `5688fcb360f6` | 2m 23s | 0.40% |
| 5 | `65f08eea1718` | 6m 27s | 1.41% |
| 6 | `a132166e70ed` | 46m 51s | 11.94% |
| 7 | `5d8c60bfebaf` | 56m 44s | 14.56% |
| 8 (final) | `f33aa4421393` | 2h 27m 7s | 38.37% |

Total winner changes: **8**.
Search completed in **6h 23m 40s** wall-clock time.

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

- Calibration run ID: `run-20260811-020009`
- Calibration schema: `1.1`
- Detector: `grabcut`
- Detector configuration: `hth-pipeline/config/detectors/grabcut.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `86aa6ee46881cce7c90bce30e96fffe9f9e3db2e`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `4`

### Detector-Selection Intelligence

- Recommended parameter set: `f33aa4421393`
- Recommended parameter short name: `f33aa4421393`
- Best observed Avg IoU: `0.9137`
- Avg IoU Success: `0.9137`
- Worst Golden Set page (Min IoU): `0.7378`
- Page-to-page StdDev: `0.0886`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_contour_area_fraction, minimum_bbox_area_fraction, polygon_epsilon_fraction`
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
| Fully successful parameter sets | 12559 (95.7%) |
| Best Avg IoU | 0.9137 |
| Minimum Avg IoU | 0.4353 |
| Avg IoU StdDev | 0.0677 |
| Winner stabilized after | 5035 parameter sets |
| Winner stabilized | 2h 27m 7s (38% of search) |
| Near-best coverage (basin; within 0.0010) | 5 (0.0%) |
| Equivalent-best configurations (within 0.0001) | 5 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13122 | 100.0% | 5d 5h 49m 57s | 1.0× |
| Non-dormant | 486 | 3.7% | 4h 39m 38s | 27.0× |
| Low+ | 486 | 3.7% | 4h 39m 38s | 27.0× |
| Moderate+ | 81 | 0.6% | 46m 36s | 162.0× |
| Important+ | 27 | 0.2% | 15m 32s | 486.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `erosion_iterations` | Important | 0.1940 | 0.0707 | 66.7% | `1` (0.7945), `2` (0.7751), `0` (0.7238) |
| `border_fraction` | Important | 0.1635 | 0.0602 | 33.3% | `0.01` (0.8031), `0.03` (0.7474), `0.02` (0.7429) |
| `grabcut_iterations` | Important | 0.1276 | 0.0555 | 33.3% | `5` (0.7862), `3` (0.7765), `1` (0.7307) |
| `erosion_kernel_fraction` | Moderate | 0.0789 | 0.0459 | 66.7% | `0.0075` (0.7897), `0.015` (0.7600), `0.025` (0.7437) |
| `close_kernel_fraction` | Low | 0.0197 | 0.0215 | 33.3% | `0.01` (0.7726), `0.02` (0.7697), `0.035` (0.7511) |
| `close_iterations` | Low | 0.0083 | 0.0124 | 50.0% | `1` (0.7707), `2` (0.7583) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0008 | 66.7% | `0.02` (0.7650), `0.04` (0.7643), `0.07` (0.7642) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0006 | 66.7% | `0.1` (0.7648), `0.07` (0.7645), `0.15` (0.7642) |
| `polygon_epsilon_fraction` | Dormant | 0.0000 | 0.0002 | 100.0% | `0.018` (0.7646), `0.01` (0.7645), `0.03` (0.7644) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_contour_area_fraction`, `minimum_bbox_area_fraction`, `polygon_epsilon_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `erosion_iterations` × `border_fraction` | 0.4075 | 0.2135 | 13122 |
| `border_fraction` × `grabcut_iterations` | 0.3016 | 0.1382 | 13122 |
| `erosion_iterations` × `grabcut_iterations` | 0.3254 | 0.1314 | 13122 |
| `erosion_iterations` × `erosion_kernel_fraction` | 0.3050 | 0.1110 | 13122 |
| `border_fraction` × `erosion_kernel_fraction` | 0.2618 | 0.0983 | 13122 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9022 | 0.0000 | 0.9904 | 0.1865 | 96.7% |
| 5 | 0.5519 | 0.2980 | 0.9755 | 0.1027 | 100.0% |
| 6 | 0.5038 | 0.0000 | 0.8217 | 0.1794 | 98.7% |
| 9 | 0.9308 | 0.8522 | 0.9433 | 0.0288 | 100.0% |
| 10 | 0.9337 | 0.8355 | 0.9661 | 0.0228 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-contour-grabcutcontour-2"></a>
<details>
<summary><strong>GrabCut + Contour (`grabcut_contour`)</strong></summary>

**Status:** complete

## Run Information — grabcut_contour

### Build Provenance

- Run ID: `run-20260812-192509`
- Detector: `grabcut_contour`
- Strategy: `exhaustive`
- Pipeline commit: `eea9070116fb`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-12T19:25:09.933327+00:00`
- Finished: `2026-08-12T19:29:23.721839+00:00`
- Wall-clock elapsed: `4m 14s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `354295`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.00%`
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

## Results — grabcut_contour

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 1m 10s |

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
| Winner changes | 0 |
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000493` | 8 |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | +0.0000 | 0.8130 | 0 | unknown | unknown |
| 2 | `2a39748afbe3` | `2a39748afbe3` | 0.8011 | 0.5492 | 0.1867 | -0.0119 | 0.8011 | 0 | 2m 25s | 33.33% |
| 3 | `ea911909ef98` | `ea911909ef98` | 0.8011 | 0.5492 | 0.1867 | -0.0119 | 0.8011 | 0 | 2m 29s | 44.44% |
| 4 | `47e727acc335` | `47e727acc335` | 0.8010 | 0.5486 | 0.1869 | -0.0120 | 0.8010 | 0 | 3m 6s | 55.56% |
| 5 | `8a86732de560` | `8a86732de560` | 0.8010 | 0.5486 | 0.1869 | -0.0120 | 0.8010 | 0 | 3m 8s | 66.67% |

## Page Analysis — grabcut_contour

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.9568 | 0.9568 | +0.0000 | Unchanged |
| 5 | `baseline` | 0.5532 | 0.5532 | +0.0000 | Unchanged |
| 6 | `baseline` | 0.6683 | 0.6683 | +0.0000 | Unchanged |
| 9 | `baseline` | 0.9422 | 0.9422 | +0.0000 | Unchanged |
| 10 | `baseline` | 0.9447 | 0.9447 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

Total winner changes: **0**.
Search completed in **4m 14s** wall-clock time.

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

## Calibration Intelligence — grabcut_contour

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-192509`
- Calibration schema: `1.1`
- Detector: `grabcut_contour`
- Detector configuration: `hth-pipeline/config/detectors/grabcut_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `eea9070116fb1cce18838ae0b338cc7b2b4ba8ab`
- Source commit: `f868b94a18b07efbb83c536fff3eb17e93b807e6`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `3817f226228a`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8130`
- Avg IoU Success: `0.8130`
- Worst Golden Set page (Min IoU): `0.5532`
- Page-to-page StdDev: `0.1692`
- Calibration evidence: `Medium`
- Dormant parameters: `contour_epsilon_max_fraction, contour_weight, grabcut_close_iterations, grabcut_erosion_iterations, grabcut_minimum_bbox_area_fraction`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 5 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 354295 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 286d 5h 30m |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8130 |
| Minimum Avg IoU | 0.7986 |
| Avg IoU StdDev | 0.0039 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 354295 | 100.0% | 286d 5h 41m 38s | 1.0× |
| Non-dormant | 6144 | 1.7% | 4d 23h 7m 50s | 57.7× |
| Low+ | 6144 | 1.7% | 4d 23h 7m 50s | 57.7× |
| Moderate+ | 6144 | 1.7% | 4d 23h 7m 50s | 57.7× |
| Important+ | 3072 | 0.9% | 2d 11h 33m 55s | 115.3× |
| Critical | 512 | 0.1% | 9h 55m 39s | 692.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `contour_minimum_area_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.12` (0.8130), `0.08` (0.8005) |
| `contour_minimum_rectangularity` | Critical | 0.9408 | 0.0125 | 50.0% | `0.55` (0.8130), `0.45` (0.8005) |
| `grabcut_border_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.02` (0.8130), `0.01` (0.8005) |
| `grabcut_close_kernel_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.02` (0.8130), `0.01` (0.8005) |
| `grabcut_erosion_kernel_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.015` (0.8130), `0.008` (0.8005) |
| `grabcut_iterations` | Critical | 0.9408 | 0.0125 | 50.0% | `3` (0.8130), `1` (0.8005) |
| `grabcut_minimum_contour_area_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.04` (0.8130), `0.02` (0.8005) |
| `grabcut_polygon_epsilon_fraction` | Critical | 0.9408 | 0.0125 | 50.0% | `0.018` (0.8130), `0.01` (0.8005) |
| `minimum_agreement_iou` | Critical | 0.9408 | 0.0125 | 50.0% | `0.15` (0.8130), `0.05` (0.8005) |
| `contour_epsilon_max_fraction` | Dormant | 0.8467 | 0.0000 | 100.0% | `0.04` (0.8130) |
| `contour_weight` | Dormant | 0.8467 | 0.0000 | 100.0% | `0.2` (0.8130) |
| `grabcut_close_iterations` | Dormant | 0.8467 | 0.0000 | 100.0% | `1` (0.8130) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_epsilon_max_fraction`, `contour_weight`, `grabcut_close_iterations`, `grabcut_erosion_iterations`, `grabcut_minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9589 | 0.9499 | 0.9617 | 0.0047 | 100.0% |
| 5 | 0.5492 | 0.5486 | 0.5532 | 0.0014 | 100.0% |
| 6 | 0.6045 | 0.5974 | 0.6683 | 0.0213 | 100.0% |
| 9 | 0.9432 | 0.9422 | 0.9433 | 0.0003 | 100.0% |
| 10 | 0.9530 | 0.9447 | 0.9540 | 0.0028 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="gradient-boundary-voting-gradientvote-2"></a>
<details>
<summary><strong>Gradient Boundary Voting (`gradient_vote`)</strong></summary>

**Status:** complete

## Run Information — gradient_vote

### Build Provenance

- Run ID: `run-20260810-215932`
- Detector: `gradient_vote`
- Strategy: `exhaustive`
- Pipeline commit: `9d1ea15025c1`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T21:59:25.257806+00:00`
- Finished: `2026-08-10T21:59:31.621834+00:00`
- Wall-clock elapsed: `6.4s`
- Est. serial runtime: `28m 50s`
- Effective acceleration: `271.79×`

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

## Results — gradient_vote

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `736327fcfb98` | `736327fcfb98` | 0.9250 | 0.7525 | 0.0869 | 0.9250 | 0 | 272 ms |
| Baseline | `5660d66df3d1` | `baseline` | 0.8882 | 0.5684 | 0.1603 | 0.8882 | 0 | 13 ms |

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
| Winner changes | 10 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile-legacy-workload` | 9 | 42 | 378 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `736327fcfb98` | `736327fcfb98` | 0.9250 | 0.7525 | 0.0869 | +0.0000 | 0.9250 | 0 | 3.3s | 54.37% |
| 2 | `d1203eaaf707` | `d1203eaaf707` | 0.9250 | 0.7525 | 0.0869 | +0.0000 | 0.9250 | 0 | 3.3s | 54.67% |
| 3 | `e462ec76763d` | `e462ec76763d` | 0.9250 | 0.7525 | 0.0869 | +0.0000 | 0.9250 | 0 | 3.3s | 55.07% |
| 4 | `cb1421f8bc5f` | `cb1421f8bc5f` | 0.9250 | 0.7525 | 0.0869 | +0.0000 | 0.9250 | 0 | 3.4s | 55.95% |
| 5 | `58f9cff63db6` | `58f9cff63db6` | 0.9250 | 0.7525 | 0.0869 | +0.0000 | 0.9250 | 0 | 3.5s | 58.88% |

## Page Analysis — gradient_vote

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `736327fcfb98` | 0.9613 | 0.9613 | +0.0000 | Unchanged |
| 5 | `736327fcfb98` | 0.5684 | 0.7525 | +0.1841 | Improved |
| 6 | `736327fcfb98` | 0.9889 | 0.9889 | +0.0000 | Unchanged |
| 9 | `736327fcfb98` | 0.9612 | 0.9612 | +0.0000 | Unchanged |
| 10 | `736327fcfb98` | 0.9611 | 0.9611 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 6 | `82311fa07668` | 908 ms | 3.35% |
| 7 | `afd3b0172658` | 961 ms | 3.73% |
| 8 | `a8be0082a8aa` | 2.3s | 29.37% |
| 9 | `ddfaaed64461` | 2.5s | 31.66% |
| 10 (final) | `abce85e968d6` | 4.4s | 76.92% |

Total winner changes: **10**.
Search completed in **6.4s** wall-clock time.

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

## Calibration Intelligence — gradient_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-215932`
- Calibration schema: `1.1`
- Detector: `gradient_vote`
- Detector configuration: `hth-pipeline/config/detectors/gradient_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `9d1ea15025c12e64648a2b8d479acfc9c7a71ea5`
- Source commit: `59e257fee25b81c0e1ad284dd97117c09881906a`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `42`

### Detector-Selection Intelligence

- Recommended parameter set: `736327fcfb98`
- Recommended parameter short name: `736327fcfb98`
- Best observed Avg IoU: `0.9250`
- Avg IoU Success: `0.9250`
- Worst Golden Set page (Min IoU): `0.7525`
- Page-to-page StdDev: `0.0869`
- Calibration evidence: `Medium`
- Dormant parameters: `area_weight, minimum_area_fraction, rectangularity_weight, gradient_percentile, minimum_vote_support, support_weight`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 6 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.

#### Evidence of ROI

The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | complete exhaustive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 5212 (79.4%) |
| Best Avg IoU | 0.9250 |
| Minimum Avg IoU | 0.7327 |
| Avg IoU StdDev | 0.0560 |
| Winner stabilized after | 3567 parameter sets |
| Winner stabilized | 3.3s (54% of search) |
| Near-best coverage (basin; within 0.0010) | 567 (8.6%) |
| Equivalent-best configurations (within 0.0001) | 81 (1.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 29m 45s | 1.0× |
| Non-dormant | 243 | 3.7% | 1m 6s | 27.0× |
| Low+ | 243 | 3.7% | 1m 6s | 27.0× |
| Moderate+ | 27 | 0.4% | 7.3s | 243.0× |
| Important+ | 9 | 0.1% | 2.4s | 729.1× |
| Critical | 9 | 0.1% | 2.4s | 729.1× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `border_search_fraction` | Critical | 0.3545 | 0.0768 | 33.3% | `0.35` (0.9191), `0.42` (0.8565), `0.47` (0.8423) |
| `minimum_span_fraction` | Critical | 0.3266 | 0.0679 | 100.0% | `0.35` (0.8953), `0.45` (0.8953), `0.55` (0.8274) |
| `gaussian_sigma` | Moderate | 0.0304 | 0.0239 | 33.3% | `1.8` (0.8841), `1.2` (0.8736), `0.8` (0.8602) |
| `central_band_fraction` | Low | 0.0080 | 0.0117 | 100.0% | `1` (0.8775), `0.86` (0.8748), `0.7` (0.8657) |
| `vote_smooth_fraction` | Low | 0.0015 | 0.0048 | 100.0% | `0.02` (0.8757), `0.012` (0.8713), `0.006` (0.8709) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.8882) |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `gradient_percentile` | Dormant | 0.0000 | 0.0000 | 100.0% | `82` (0.8727), `70` (0.8727), `90` (0.8727) |
| `minimum_vote_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.16` (0.8727), `0.08` (0.8727), `0.25` (0.8727) |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.8727), `0.45` (0.8727), `0.65` (0.8727) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `minimum_area_fraction`, `rectangularity_weight`, `gradient_percentile`, `minimum_vote_support`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `border_search_fraction` × `minimum_span_fraction` | 0.8462 | 0.4917 | 6562 |
| `border_search_fraction` × `gaussian_sigma` | 0.4019 | 0.0474 | 6562 |
| `minimum_span_fraction` × `gaussian_sigma` | 0.3612 | 0.0346 | 6562 |
| `gaussian_sigma` × `central_band_fraction` | 0.0484 | 0.0179 | 6562 |
| `gaussian_sigma` × `vote_smooth_fraction` | 0.0434 | 0.0130 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9508 | 0.8680 | 0.9621 | 0.0239 | 100.0% |
| 5 | 0.5111 | 0.0000 | 0.7534 | 0.2745 | 79.4% |
| 6 | 0.9888 | 0.9879 | 0.9889 | 0.0004 | 100.0% |
| 9 | 0.9522 | 0.8466 | 0.9612 | 0.0299 | 100.0% |
| 10 | 0.9604 | 0.9592 | 0.9611 | 0.0006 | 100.0% |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | 0.7563 | 1 | 1.4s |
| Baseline | `7078053f309d` | `baseline` | 0.4784 | 0.0000 | 0.2851 | 0.5981 | 1 | 1.4s |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `c2c117479e3f` | `c2c117479e3f` | 0.6050 | 0.0000 | 0.3217 | +0.0000 | 0.7563 | 1 | 2m 28s | 79.33% |
| 2 | `d2207b5c0b61` | `d2207b5c0b61` | 0.6040 | 0.0000 | 0.3210 | -0.0010 | 0.7550 | 1 | 2m 12s | 67.95% |
| 3 | `16967597e3b6` | `16967597e3b6` | 0.6039 | 0.0000 | 0.3215 | -0.0011 | 0.7549 | 1 | 2m 28s | 79.38% |
| 4 | `bf183b1707fd` | `bf183b1707fd` | 0.6038 | 0.0000 | 0.3209 | -0.0012 | 0.7547 | 1 | 2m 13s | 68.54% |
| 5 | `7a75b3e87104` | `7a75b3e87104` | 0.6022 | 0.0000 | 0.3206 | -0.0028 | 0.7528 | 1 | 2m 13s | 68.72% |

## Page Analysis — hough

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `c2c117479e3f` | 0.6261 | 0.8347 | +0.2086 | Improved |
| 5 | `c2c117479e3f` | 0.3071 | 0.5446 | +0.2375 | Improved |
| 6 | `c2c117479e3f` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `c2c117479e3f` | 0.7370 | 0.8188 | +0.0819 | Improved |
| 10 | `c2c117479e3f` | 0.7221 | 0.8270 | +0.1049 | Improved |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `ed3e6fe9ea40` | 2.7s | 0.05% |
| 2 | `d2ef0aec6694` | 2.8s | 0.64% |
| 3 | `0dd1e07cee62` | 4.4s | 1.28% |
| 4 | `a28d5dc71704` | 4.5s | 1.33% |
| 5 (final) | `07a0b3ac190f` | 7.5s | 2.61% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 6 | `c2c117479e3f` | 0.0000 | No polygon found |

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

### Detector-Selection Intelligence

- Recommended parameter set: `c2c117479e3f`
- Recommended parameter short name: `c2c117479e3f`
- Best observed Avg IoU: `0.6050`
- Avg IoU Success: `0.7563`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3217`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, axis_angle_tolerance_degrees`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `outer_percentile` | Critical | 0.7748 | 0.2317 | 33.3% | `5` (0.5231), `10` (0.4474), `20` (0.2914) |
| `minimum_length_fraction` | Moderate | 0.0386 | 0.0495 | 33.3% | `0.12` (0.4402), `0.2` (0.4311), `0.3` (0.3907) |
| `maximum_gap_fraction` | Moderate | 0.0311 | 0.0437 | 33.3% | `0.09` (0.4373), `0.055` (0.4312), `0.025` (0.3935) |
| `canny_low_threshold` | Low | 0.0273 | 0.0443 | 33.3% | `40` (0.4423), `25` (0.4217), `65` (0.3980) |
| `hough_threshold_fraction` | Low | 0.0063 | 0.0211 | 33.3% | `0.035` (0.4320), `0.055` (0.4190), `0.08` (0.4109) |
| `bbox_padding_fraction` | Low | 0.0047 | 0.0182 | 33.3% | `0.015` (0.4305), `0.005` (0.4191), `0` (0.4124) |
| `minimum_bbox_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.1` (0.4784) |
| `axis_angle_tolerance_degrees` | Dormant | 0.0000 | 0.0009 | 33.3% | `12` (0.4210), `22` (0.4209), `32` (0.4201) |

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

- Run ID: `run-20260812-194828`
- Detector: `joint_rectangle_vote`
- Strategy: `exhaustive`
- Pipeline commit: `eea9070116fb`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T19:48:06.077148+00:00`
- Finished: `2026-08-12T19:48:27.774379+00:00`
- Wall-clock elapsed: `21.7s`
- Est. serial runtime: `2h 50s`
- Effective acceleration: `334.15×`

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | 0.9899 | 4 | 2.2s |
| Baseline | `697c22dd549f` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 318 ms |

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
| Winner changes | 3 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile` | 23 | 16 | 368 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `5c9509e05f14` | `5c9509e05f14` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 20.9s | 98.17% |
| 2 | `3d84cd0a9026` | `3d84cd0a9026` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 7.2s | 22.96% |
| 3 | `d2dea9b84b6e` | `d2dea9b84b6e` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 14.6s | 61.21% |
| 4 | `1e66b0603099` | `1e66b0603099` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 7.3s | 23.97% |
| 5 | `951741938aa2` | `951741938aa2` | 0.1980 | 0.0000 | 0.3960 | +0.0000 | 0.9899 | 4 | 20.4s | 92.09% |

## Page Analysis — joint_rectangle_vote

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `5c9509e05f14` | 0.0000 | 0.9899 | +0.9899 | Recovered |
| 9 | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `5c9509e05f14` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `33e5d98deed8` | 3s | 0.23% |
| 2 | `f92acb2f7e94` | 3s | 0.27% |
| 3 (final) | `96cfce540225` | 6.8s | 19.76% |

Total winner changes: **3**.
Search completed in **21.7s** wall-clock time.

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `5c9509e05f14` | 0.0000 | No polygon found |
| 5 | `5c9509e05f14` | 0.0000 | No polygon found |
| 9 | `5c9509e05f14` | 0.0000 | No polygon found |
| 10 | `5c9509e05f14` | 0.0000 | No polygon found |

## Calibration Intelligence — joint_rectangle_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-194828`
- Calibration schema: `1.1`
- Detector: `joint_rectangle_vote`
- Detector configuration: `hth-pipeline/config/detectors/joint_rectangle_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `eea9070116fb1cce18838ae0b338cc7b2b4ba8ab`
- Source commit: `c2aad916f809d85e77d1d4f7f581fb9ef56fa2d6`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `16`

### Detector-Selection Intelligence

- Recommended parameter set: `5c9509e05f14`
- Recommended parameter short name: `5c9509e05f14`
- Best observed Avg IoU: `0.1980`
- Avg IoU Success: `0.9899`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3960`
- Calibration evidence: `Medium`
- Dormant parameters: `bbox_padding_fraction, minimum_area_fraction, minimum_side_support`
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
| Winner stabilized after | 2146 parameter sets |
| Winner stabilized | 20.9s (98% of search) |
| Near-best coverage (basin; within 0.0010) | 27 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 27 (1.2%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 1h 21m 59s | 1.0× |
| Non-dormant | 81 | 3.7% | 3m 2s | 27.0× |
| Low+ | 81 | 3.7% | 3m 2s | 27.0× |
| Moderate+ | 9 | 0.4% | 20.2s | 243.0× |
| Important+ | 9 | 0.4% | 20.2s | 243.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `canny_high` | Important | 0.1758 | 0.0643 | 33.3% | `220` (0.0643), `100` (0.0140), `150` (0.0000) |
| `hough_threshold` | Important | 0.1758 | 0.0643 | 33.3% | `120` (0.0643), `80` (0.0140), `50` (0.0000) |
| `canny_low` | Low | 0.0100 | 0.0140 | 100.0% | `30` (0.0354), `50` (0.0214), `80` (0.0214) |
| `axis_tolerance_degrees` | Low | 0.0024 | 0.0069 | 33.3% | `12` (0.0284), `18` (0.0284), `6` (0.0215) |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0009 | 33.3% | `0` (0.0265), `0.008` (0.0262), `0.016` (0.0256) |
| `minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0261), `0.16` (0.0261), `0.24` (0.0261) |
| `minimum_side_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0261), `0.18` (0.0261), `0.3` (0.0261) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | 0.9222 | 1 | 379 ms |
| Baseline | `b2df04f4e947` | `baseline` | 0.5414 | 0.0000 | 0.4436 | 0.9023 | 2 | 332 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 7.9s | 18.57% |
| 2 | `05a653fabdd0` | `05a653fabdd0` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 8.1s | 18.76% |
| 3 | `497528ffc236` | `497528ffc236` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 8.2s | 18.89% |
| 4 | `24a5a18c61f3` | `24a5a18c61f3` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 8.7s | 19.76% |
| 5 | `97f5383e66cd` | `97f5383e66cd` | 0.7378 | 0.0000 | 0.3721 | +0.0000 | 0.9222 | 1 | 8.7s | 19.99% |

## Page Analysis — lsd

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `7546c5067527` | 0.8955 | 0.9102 | +0.0147 | Improved |
| 5 | `7546c5067527` | 0.0000 | 0.9850 | +0.9850 | Recovered |
| 6 | `7546c5067527` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `7546c5067527` | 0.8475 | 0.8400 | -0.0075 | Regressed |
| 10 | `7546c5067527` | 0.9641 | 0.9537 | -0.0103 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `0bd9251e7f32` | 570 ms | 0.05% |
| 2 | `1b2cebd68deb` | 622 ms | 0.32% |
| 3 (final) | `7546c5067527` | 7.9s | 18.57% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 6 | `7546c5067527` | 0.0000 | No polygon found |
| 9 | `7546c5067527` | 0.8400 | Regressed |
| 10 | `7546c5067527` | 0.9537 | Regressed |

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

### Detector-Selection Intelligence

- Recommended parameter set: `7546c5067527`
- Recommended parameter short name: `7546c5067527`
- Best observed Avg IoU: `0.7378`
- Avg IoU Success: `0.9222`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3721`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, axis_angle_tolerance_degrees`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `refine_mode` | Critical | 0.2730 | 0.2038 | 33.3% | `none` (0.5940), `adv` (0.3902), `std` (0.3902) |
| `minimum_length_fraction` | Important | 0.2059 | 0.1926 | 100.0% | `0.08` (0.5347), `0.14` (0.4975), `0.22` (0.3421) |
| `outer_percentile` | Important | 0.1380 | 0.1568 | 33.3% | `5` (0.5197), `10` (0.4918), `20` (0.3629) |
| `scale` | Moderate | 0.0428 | 0.0888 | 66.7% | `0.6` (0.4944), `0.8` (0.4743), `1` (0.4056) |
| `bbox_padding_fraction` | Low | 0.0012 | 0.0138 | 33.3% | `0` (0.4628), `0.005` (0.4624), `0.015` (0.4490) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0004 | 100.0% | `0.08` (0.4584), `0.1` (0.4580), `0.15` (0.4580) |
| `axis_angle_tolerance_degrees` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.4581), `18` (0.4581), `28` (0.4581) |

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

<a id="polar-boundary-voting-polarboundaryvote-2"></a>
<details>
<summary><strong>Polar Boundary Voting (`polar_boundary_vote`)</strong></summary>

**Status:** complete

## Run Information — polar_boundary_vote

### Build Provenance

- Run ID: `run-20260812-155410`
- Detector: `polar_boundary_vote`
- Strategy: `exhaustive`
- Pipeline commit: `4f49196091a4`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T15:54:00.712731+00:00`
- Finished: `2026-08-12T15:54:09.604942+00:00`
- Wall-clock elapsed: `8.9s`
- Est. serial runtime: `40m 22s`
- Effective acceleration: `272.38×`

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

## Results — polar_boundary_vote

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `cd967f93437d` | `cd967f93437d` | 0.9678 | 0.9425 | 0.0182 | 0.9678 | 0 | 3.9s |
| Baseline | `91ecb91a68da` | `baseline` | 0.8846 | 0.8109 | 0.0467 | 0.8846 | 0 | 48 ms |

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
| `preferred-hardware-profile` | 13 | 29 | 377 | `rh8-al319` | 384 |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `cd967f93437d` | `cd967f93437d` | 0.9678 | 0.9425 | 0.0182 | +0.0000 | 0.9678 | 0 | 4.1s | 46.84% |
| 2 | `52758d19b01b` | `52758d19b01b` | 0.9678 | 0.9425 | 0.0182 | +0.0000 | 0.9678 | 0 | 4.1s | 44.92% |
| 3 | `7eacb65c300d` | `7eacb65c300d` | 0.9678 | 0.9425 | 0.0182 | +0.0000 | 0.9678 | 0 | 4.3s | 53.30% |
| 4 | `21908c0f7b95` | `21908c0f7b95` | 0.9668 | 0.9473 | 0.0162 | -0.0010 | 0.9668 | 0 | 2.4s | 31.87% |
| 5 | `b415644b159d` | `b415644b159d` | 0.9668 | 0.9473 | 0.0162 | -0.0010 | 0.9668 | 0 | 2.3s | 25.55% |

## Page Analysis — polar_boundary_vote

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `cd967f93437d` | 0.8861 | 0.9819 | +0.0957 | Improved |
| 5 | `cd967f93437d` | 0.8986 | 0.9925 | +0.0938 | Improved |
| 6 | `cd967f93437d` | 0.9560 | 0.9688 | +0.0128 | Improved |
| 9 | `cd967f93437d` | 0.8109 | 0.9425 | +0.1316 | Improved |
| 10 | `cd967f93437d` | 0.8713 | 0.9533 | +0.0820 | Improved |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 3 | `3ed8c2ba4281` | 1.2s | 0.41% |
| 4 | `a848f8d6c1d3` | 1.2s | 0.55% |
| 5 | `be950390744a` | 1.2s | 0.96% |
| 6 | `cc5b8803e2f2` | 2.1s | 11.13% |
| 7 (final) | `52758d19b01b` | 4.1s | 44.92% |

Total winner changes: **7**.
Search completed in **8.9s** wall-clock time.

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

## Calibration Intelligence — polar_boundary_vote

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-155410`
- Calibration schema: `1.1`
- Detector: `polar_boundary_vote`
- Detector configuration: `hth-pipeline/config/detectors/polar_boundary_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `4f49196091a44d5ca7cfe2269ab7c5a207f6336f`
- Source commit: `b184338c29c994b4feaf0e9a2915a1855897f4fb`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `29`

### Detector-Selection Intelligence

- Recommended parameter set: `cd967f93437d`
- Recommended parameter short name: `cd967f93437d`
- Best observed Avg IoU: `0.9678`
- Avg IoU Success: `0.9678`
- Worst Golden Set page (Min IoU): `0.9425`
- Page-to-page StdDev: `0.0182`
- Calibration evidence: `Medium`
- Dormant parameters: `inner_radius_fraction, minimum_support_fraction`
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
| All possible parameter sets | 729 |
| Parameter sets evaluated | 729 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 729 (100.0%) |
| Best Avg IoU | 0.9678 |
| Minimum Avg IoU | 0.8176 |
| Avg IoU StdDev | 0.0470 |
| Winner stabilized after | 341 parameter sets |
| Winner stabilized | 4.1s (47% of search) |
| Near-best coverage (basin; within 0.0010) | 6 (0.8%) |
| Equivalent-best configurations (within 0.0001) | 3 (0.4%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 47m 31s | 1.0× |
| Non-dormant | 81 | 11.1% | 5m 17s | 9.0× |
| Low+ | 81 | 11.1% | 5m 17s | 9.0× |
| Moderate+ | 27 | 3.7% | 1m 46s | 27.0× |
| Important+ | 3 | 0.4% | 11.7s | 243.0× |
| Critical | 3 | 0.4% | 11.7s | 243.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `outer_radius_fraction` | Critical | 0.8387 | 0.1046 | 33.3% | `0.6` (0.9297), `0.7` (0.8660), `0.82` (0.8251) |
| `bbox_padding_fraction` | Moderate | 0.0722 | 0.0308 | 33.3% | `0` (0.8899), `0.008` (0.8717), `0.016` (0.8592) |
| `gradient_percentile` | Moderate | 0.0455 | 0.0243 | 33.3% | `90` (0.8868), `82` (0.8715), `72` (0.8625) |
| `ray_count` | Low | 0.0073 | 0.0099 | 66.7% | `90` (0.8786), `180` (0.8734), `360` (0.8688) |
| `inner_radius_fraction` | Dormant | 0.0008 | 0.0029 | 33.3% | `0.12` (0.8746), `0.06` (0.8745), `0.18` (0.8717) |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8736), `0.35` (0.8736), `0.5` (0.8736) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`inner_radius_fraction`, `minimum_support_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_radius_fraction` × `bbox_padding_fraction` | 0.9269 | 0.0882 | 729 |
| `outer_radius_fraction` × `gradient_percentile` | 0.8926 | 0.0539 | 729 |
| `bbox_padding_fraction` × `gradient_percentile` | 0.1186 | 0.0464 | 729 |
| `outer_radius_fraction` × `ray_count` | 0.8486 | 0.0099 | 729 |
| `gradient_percentile` × `ray_count` | 0.0540 | 0.0085 | 729 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8628 | 0.7782 | 0.9819 | 0.0661 | 100.0% |
| 5 | 0.9109 | 0.8699 | 0.9942 | 0.0449 | 100.0% |
| 6 | 0.9444 | 0.9327 | 0.9753 | 0.0131 | 100.0% |
| 9 | 0.7901 | 0.7134 | 0.9473 | 0.0738 | 100.0% |
| 10 | 0.8597 | 0.7940 | 0.9543 | 0.0545 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="radial-edge-search-radialedge-2"></a>
<details>
<summary><strong>Radial Edge Search (`radial_edge`)</strong></summary>

**Status:** complete

## Run Information — radial_edge

### Build Provenance

- Run ID: `run-20260810-200011`
- Detector: `radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `0ccc635b9a94`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-10T20:00:11.418064+00:00`
- Finished: `2026-08-10T20:04:03.394252+00:00`
- Wall-clock elapsed: `3m 52s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

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
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results — radial_edge

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `5f802d0c469d` | `5f802d0c469d` | 0.9547 | 0.9432 | 0.0104 | 0.9547 | 0 | 470 ms |
| Baseline | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | 0.9503 | 0 | 51 ms |

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
| Avg IoU improvements | 2 |
| Minimum IoU improvements | 1 |
| StdDev improvements | 2 |
| Total metric improvements | 5 |
| Parameter sets with improvements | 3 |
| Winner changes | 2 |
| Baseline surpassed | yes |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 1 | 16 | 16 | `rh8-al319` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `5f802d0c469d` | `5f802d0c469d` | 0.9547 | 0.9432 | 0.0104 | +0.0000 | 0.9547 | 0 | 3m 12s | 86.43% |
| 2 | `ea1cc4a45824` | `ea1cc4a45824` | 0.9547 | 0.9432 | 0.0104 | +0.0000 | 0.9547 | 0 | 3m 12s | 86.45% |
| 3 | `d8c93dbf215f` | `d8c93dbf215f` | 0.9547 | 0.9432 | 0.0104 | +0.0000 | 0.9547 | 0 | 3m 12s | 86.50% |
| 4 | `ab412ed2c6d3` | `ab412ed2c6d3` | 0.9547 | 0.9432 | 0.0104 | +0.0000 | 0.9547 | 0 | 3m 12s | 86.47% |
| 5 | `89566be90a8c` | `89566be90a8c` | 0.9547 | 0.9432 | 0.0104 | +0.0000 | 0.9547 | 0 | 3m 12s | 86.48% |

## Page Analysis — radial_edge

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `5f802d0c469d` | 0.9466 | 0.9457 | -0.0009 | Unchanged |
| 5 | `5f802d0c469d` | 0.9742 | 0.9727 | -0.0015 | Regressed |
| 6 | `5f802d0c469d` | 0.9384 | 0.9432 | +0.0048 | Improved |
| 9 | `5f802d0c469d` | 0.9340 | 0.9545 | +0.0205 | Improved |
| 10 | `5f802d0c469d` | 0.9582 | 0.9574 | -0.0009 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `0d096306baa6` | 2m 28s | 64.21% |
| 2 (final) | `5f802d0c469d` | 3m 12s | 86.43% |

Total winner changes: **2**.
Search completed in **3m 52s** wall-clock time.

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 5 | `5f802d0c469d` | 0.9727 | Regressed |

## Calibration Intelligence — radial_edge

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260810-200011`
- Calibration schema: `1.1`
- Detector: `radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `0ccc635b9a943e9d1b51eebf1d64706001971da3`
- Source commit: `71e4c7704e77fb55d220b547c2443c186fb4b8f1`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `16`

### Detector-Selection Intelligence

- Recommended parameter set: `5f802d0c469d`
- Recommended parameter short name: `5f802d0c469d`
- Best observed Avg IoU: `0.9547`
- Avg IoU Success: `0.9547`
- Worst Golden Set page (Min IoU): `0.9432`
- Page-to-page StdDev: `0.0104`
- Calibration evidence: `High`
- Dormant parameters: `gradient_percentile, area_weight, maximum_area_fraction, minimum_area_fraction, minimum_ray_support, rectangularity_weight, support_weight`
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
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 6562 |
| Evaluated sets (% of all possible parameter sets) | 100.0% |
| Est. serial runtime for full parameter set evaluation* | complete |
| Fully successful parameter sets | 6562 (100.0%) |
| Best Avg IoU | 0.9547 |
| Minimum Avg IoU | 0.7683 |
| Avg IoU StdDev | 0.0475 |
| Winner stabilized after | 5671 parameter sets |
| Winner stabilized | 3m 12s (86% of search) |
| Near-best coverage (basin; within 0.0010) | 81 (1.2%) |
| Equivalent-best configurations (within 0.0001) | 81 (1.2%) |
| Calibration Evidence | High |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 51m 24s | 1.0× |
| Non-dormant | 81 | 1.2% | 38.1s | 81.0× |
| Low+ | 81 | 1.2% | 38.1s | 81.0× |
| Moderate+ | 81 | 1.2% | 38.1s | 81.0× |
| Important+ | 9 | 0.1% | 4.2s | 729.1× |
| Critical | 3 | 0.0% | 1.4s | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `maximum_radius_fraction` | Critical | 0.5353 | 0.0794 | 33.3% | `0.72` (0.9102), `0.82` (0.8970), `0.62` (0.8308) |
| `ray_count` | Important | 0.1759 | 0.0486 | 33.3% | `96` (0.9023), `144` (0.8820), `64` (0.8537) |
| `minimum_radius_fraction` | Moderate | 0.0329 | 0.0190 | 33.3% | `0.24` (0.8915), `0.12` (0.8741), `0.18` (0.8725) |
| `gaussian_sigma` | Moderate | 0.0317 | 0.0185 | 33.3% | `1.8` (0.8859), `1.2` (0.8847), `0.8` (0.8674) |
| `gradient_percentile` | Dormant | 0.0009 | 0.0033 | 100.0% | `70` (0.8814), `90` (0.8785), `82` (0.8781) |
| `area_weight` | Dormant | 0.0003 | 0.0000 | 0.0% | `0.35` (0.9503) |
| `maximum_area_fraction` | Dormant | 0.0003 | 0.0000 | 0.0% | `0.98` (0.9503) |
| `minimum_area_fraction` | Dormant | 0.0003 | 0.0000 | 0.0% | `0.18` (0.9503) |
| `minimum_ray_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8794), `0.3` (0.8793), `0.6` (0.8793) |
| `rectangularity_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.2` (0.8794), `0.1` (0.8793), `0.3` (0.8793) |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.8794), `0.35` (0.8793), `0.55` (0.8793) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`gradient_percentile`, `area_weight`, `maximum_area_fraction`, `minimum_area_fraction`, `minimum_ray_support`, `rectangularity_weight`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `maximum_radius_fraction` × `ray_count` | 0.7189 | 0.1837 | 6562 |
| `maximum_radius_fraction` × `gaussian_sigma` | 0.6420 | 0.1068 | 6562 |
| `ray_count` × `gaussian_sigma` | 0.2413 | 0.0654 | 6562 |
| `maximum_radius_fraction` × `minimum_radius_fraction` | 0.5921 | 0.0568 | 6562 |
| `minimum_radius_fraction` × `gaussian_sigma` | 0.0696 | 0.0366 | 6562 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8720 | 0.7578 | 0.9562 | 0.0645 | 100.0% |
| 5 | 0.9350 | 0.7703 | 0.9856 | 0.0585 | 100.0% |
| 6 | 0.8153 | 0.4831 | 0.9432 | 0.1066 | 100.0% |
| 9 | 0.8629 | 0.7134 | 0.9575 | 0.0821 | 100.0% |
| 10 | 0.9115 | 0.7960 | 0.9623 | 0.0534 | 100.0% |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | 0.4983 | 0 | 2.4s |
| Baseline | `f26bbb16c7b6` | `baseline` | 0.4227 | 0.2130 | 0.2863 | 0.4227 | 0 | 181 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `dd6b2601d568` | `dd6b2601d568` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 2.9s | 6.46% |
| 2 | `2576db79d995` | `2576db79d995` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 7.4s | 64.84% |
| 3 | `7e45c62ce0a0` | `7e45c62ce0a0` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 5.7s | 49.04% |
| 4 | `75b9c212c0c0` | `75b9c212c0c0` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 8.7s | 83.10% |
| 5 | `bd0668adeb01` | `bd0668adeb01` | 0.4983 | 0.2028 | 0.2509 | +0.0000 | 0.4983 | 0 | 4.5s | 30.22% |

## Page Analysis — radon_boundary

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `dd6b2601d568` | 0.2480 | 0.2028 | -0.0452 | Regressed |
| 5 | `dd6b2601d568` | 0.4147 | 0.5425 | +0.1278 | Improved |
| 6 | `dd6b2601d568` | 0.9782 | 0.9507 | -0.0275 | Regressed |
| 9 | `dd6b2601d568` | 0.2130 | 0.4144 | +0.2014 | Improved |
| 10 | `dd6b2601d568` | 0.2595 | 0.3809 | +0.1214 | Improved |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `4586c6c3690c` | 2.4s | 0.27% |
| 2 | `c8902d013cc7` | 2.5s | 0.82% |
| 3 | `6635a2bca65b` | 2.6s | 1.79% |
| 4 | `d7abaf98543e` | 2.8s | 5.49% |
| 5 (final) | `dd6b2601d568` | 2.9s | 6.46% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `dd6b2601d568` | 0.2028 | Poor match; Regressed |
| 6 | `dd6b2601d568` | 0.9507 | Regressed |
| 9 | `dd6b2601d568` | 0.4144 | Poor match |
| 10 | `dd6b2601d568` | 0.3809 | Poor match |

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

### Detector-Selection Intelligence

- Recommended parameter set: `dd6b2601d568`
- Recommended parameter short name: `dd6b2601d568`
- Best observed Avg IoU: `0.4983`
- Avg IoU Success: `0.4983`
- Worst Golden Set page (Min IoU): `0.2028`
- Page-to-page StdDev: `0.2509`
- Calibration evidence: `Medium`
- Dormant parameters: `angle_step_degrees`
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

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `projection_smooth_fraction` | Critical | 0.5794 | 0.2089 | 33.3% | `0.006` (0.4154), `0.012` (0.3870), `0.024` (0.2065) |
| `minimum_peak_prominence` | Critical | 0.3666 | 0.1633 | 66.7% | `1.05` (0.3959), `1.25` (0.3804), `1.6` (0.2326) |
| `edge_percentile` | Low | 0.0056 | 0.0205 | 33.3% | `90` (0.3491), `75` (0.3312), `82` (0.3286) |
| `angle_limit_degrees` | Low | 0.0040 | 0.0185 | 100.0% | `12` (0.3447), `8` (0.3380), `4` (0.3262) |
| `bbox_padding_fraction` | Low | 0.0036 | 0.0178 | 33.3% | `0.016` (0.3444), `0.008` (0.3378), `0` (0.3267) |
| `angle_step_degrees` | Dormant | 0.0001 | 0.0036 | 66.7% | `0.5` (0.3382), `2` (0.3361), `1` (0.3346) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `9647b030702e` | `9647b030702e` | 0.7541 | 0.3558 | 0.2541 | 0.7541 | 0 | 1s |
| Baseline | `7e367fe3bfd5` | `baseline` | 0.6831 | 0.0000 | 0.3806 | 0.8539 | 1 | 42 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `9647b030702e` | `9647b030702e` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 16s | 85.31% |
| 2 | `d212abf22eb8` | `d212abf22eb8` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 16s | 85.52% |
| 3 | `90823a3ef18b` | `90823a3ef18b` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 16s | 85.72% |
| 4 | `4375bb0ee3a5` | `4375bb0ee3a5` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 17s | 86.82% |
| 5 | `7352e2e44471` | `7352e2e44471` | 0.7541 | 0.3558 | 0.2541 | +0.0000 | 0.7541 | 0 | 1m 17s | 87.30% |

## Page Analysis — ransac

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `9647b030702e` | 0.9665 | 0.9738 | +0.0072 | Improved |
| 5 | `9647b030702e` | 0.5289 | 0.5490 | +0.0202 | Improved |
| 6 | `9647b030702e` | 0.0000 | 0.3558 | +0.3558 | Recovered |
| 9 | `9647b030702e` | 0.9550 | 0.9373 | -0.0177 | Regressed |
| 10 | `9647b030702e` | 0.9652 | 0.9546 | -0.0106 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 6 | `e5a2730e1b8e` | 34.5s | 40.97% |
| 7 | `f70957e5e192` | 43.8s | 52.02% |
| 8 | `f256461b1f0e` | 52.9s | 63.01% |
| 9 | `6f60c05601a6` | 1m 16s | 84.83% |
| 10 (final) | `9647b030702e` | 1m 16s | 85.31% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 6 | `9647b030702e` | 0.3558 | Poor match |
| 9 | `9647b030702e` | 0.9373 | Regressed |
| 10 | `9647b030702e` | 0.9546 | Regressed |

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

### Detector-Selection Intelligence

- Recommended parameter set: `9647b030702e`
- Recommended parameter short name: `9647b030702e`
- Best observed Avg IoU: `0.7541`
- Avg IoU Success: `0.7541`
- Worst Golden Set page (Min IoU): `0.3558`
- Page-to-page StdDev: `0.2541`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, scan_samples, minimum_scan_foreground_fraction, max_trials`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_mean_inlier_ratio` | Critical | 0.7489 | 0.2487 | 33.3% | `0.25` (0.6889), `0.45` (0.6430), `0.65` (0.4402) |
| `residual_threshold_fraction` | Important | 0.1372 | 0.1114 | 33.3% | `0.014` (0.6523), `0.008` (0.5789), `0.004` (0.5408) |
| `bbox_padding_fraction` | Low | 0.0021 | 0.0129 | 33.3% | `0` (0.5956), `0.008` (0.5937), `0.016` (0.5827) |
| `minimum_bbox_area_fraction` | Dormant | 0.0002 | 0.0033 | 100.0% | `0.1` (0.5918), `0.18` (0.5918), `0.28` (0.5885) |
| `scan_samples` | Dormant | 0.0001 | 0.0031 | 33.3% | `220` (0.5919), `320` (0.5914), `140` (0.5888) |
| `minimum_scan_foreground_fraction` | Dormant | 0.0001 | 0.0028 | 33.3% | `0.02` (0.5917), `0.0125` (0.5915), `0.008` (0.5889) |
| `max_trials` | Dormant | 0.0000 | 0.0001 | 100.0% | `200` (0.5907), `400` (0.5906) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | 0.8179 | 0 | 3.8s |
| Baseline | `f914375ada78` | `baseline` | 0.7756 | 0.3969 | 0.2448 | 0.7756 | 0 | 46 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `024732f5e631` | `024732f5e631` | 0.8179 | 0.5367 | 0.1827 | +0.0000 | 0.8179 | 0 | 6.8s | 98.76% |
| 2 | `d1a67626e1a7` | `d1a67626e1a7` | 0.8179 | 0.5367 | 0.1827 | +0.0000 | 0.8179 | 0 | 5.7s | 74.31% |
| 3 | `fa97b23311b2` | `fa97b23311b2` | 0.8179 | 0.5367 | 0.1827 | +0.0000 | 0.8179 | 0 | 6.6s | 95.88% |
| 4 | `9e7c1f9b7e79` | `9e7c1f9b7e79` | 0.8166 | 0.5344 | 0.1825 | -0.0013 | 0.8166 | 0 | 6.2s | 82.97% |
| 5 | `ef8cc5554d87` | `ef8cc5554d87` | 0.8166 | 0.5344 | 0.1825 | -0.0013 | 0.8166 | 0 | 6.4s | 86.81% |

## Page Analysis — star_convex

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `024732f5e631` | 0.9881 | 0.9761 | -0.0120 | Regressed |
| 5 | `024732f5e631` | 0.5706 | 0.5367 | -0.0339 | Regressed |
| 6 | `024732f5e631` | 0.3969 | 0.6626 | +0.2657 | Improved |
| 9 | `024732f5e631` | 0.9542 | 0.9523 | -0.0020 | Regressed |
| 10 | `024732f5e631` | 0.9683 | 0.9617 | -0.0066 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 7 | `05bb5aa0b671` | 5.3s | 67.72% |
| 8 | `8b82548b32eb` | 5.3s | 68.54% |
| 9 | `e7bf7814121d` | 5.4s | 68.96% |
| 10 | `7ecd223a15dc` | 5.5s | 70.60% |
| 11 (final) | `d1a67626e1a7` | 5.7s | 74.31% |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `024732f5e631` | 0.9761 | Regressed |
| 5 | `024732f5e631` | 0.5367 | Regressed |
| 9 | `024732f5e631` | 0.9523 | Regressed |
| 10 | `024732f5e631` | 0.9617 | Regressed |

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

### Detector-Selection Intelligence

- Recommended parameter set: `024732f5e631`
- Recommended parameter short name: `024732f5e631`
- Best observed Avg IoU: `0.8179`
- Avg IoU Success: `0.8179`
- Worst Golden Set page (Min IoU): `0.5367`
- Page-to-page StdDev: `0.1827`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_support_fraction`
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

Calibration evidence basis: complete exhaustive coverage, high fully-successful-set rate, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `smoothing_window` | Critical | 0.6484 | 0.0365 | 33.3% | `1` (0.8009), `9` (0.7645), `5` (0.7644) |
| `maximum_radius_fraction` | Moderate | 0.0970 | 0.0150 | 33.3% | `0.6` (0.7822), `0.72` (0.7803), `0.84` (0.7673) |
| `bbox_padding_fraction` | Moderate | 0.0312 | 0.0084 | 33.3% | `0` (0.7797), `0.008` (0.7788), `0.016` (0.7713) |
| `ray_count` | Low | 0.0171 | 0.0065 | 33.3% | `360` (0.7804), `180` (0.7755), `90` (0.7739) |
| `minimum_radius_fraction` | Low | 0.0053 | 0.0034 | 33.3% | `0.16` (0.7788), `0.05` (0.7756), `0.1` (0.7754) |
| `minimum_support_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.7766), `0.55` (0.7766), `0.7` (0.7766) |

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

- Run ID: `run-20260812-193345`
- Detector: `text_flow`
- Strategy: `exhaustive`
- Pipeline commit: `eea9070116fb`
- Python: `3.12.0`
- OpenCV: `5.0.0`
- Started: `2026-08-12T19:33:45.978076+00:00`
- Finished: `2026-08-12T19:33:49.301325+00:00`
- Wall-clock elapsed: `3.3s`
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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | 0.8170 | 4 | 497 ms |
| Baseline | `cd4fbe8ec7d8` | `baseline` | 0.1596 | 0.0000 | 0.3191 | 0.7978 | 4 | 19 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `a2bbfc162f9e` | `a2bbfc162f9e` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.6s | 9.62% |
| 2 | `919f35cbc4af` | `919f35cbc4af` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.6s | 21.70% |
| 3 | `e127c712c18d` | `e127c712c18d` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.6s | 46.57% |
| 4 | `a83d7e03757b` | `a83d7e03757b` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.6s | 13.74% |
| 5 | `5caa04c23d75` | `5caa04c23d75` | 0.1634 | 0.0000 | 0.3268 | +0.0000 | 0.8170 | 4 | 2.6s | 44.92% |

## Page Analysis — text_flow

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `a2bbfc162f9e` | 0.7978 | 0.8170 | +0.0192 | Improved |
| 9 | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `a2bbfc162f9e` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 (final) | `62c477aa5166` | 2.1s | 1.51% |

Total winner changes: **1**.
Search completed in **3.3s** wall-clock time.

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 5 | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 9 | `a2bbfc162f9e` | 0.0000 | No polygon found |
| 10 | `a2bbfc162f9e` | 0.0000 | No polygon found |

## Calibration Intelligence — text_flow

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260812-193345`
- Calibration schema: `1.1`
- Detector: `text_flow`
- Detector configuration: `hth-pipeline/config/detectors/text_flow.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `eea9070116fb1cce18838ae0b338cc7b2b4ba8ab`
- Source commit: `bc61332b0eaeae8c80ead3757bcd931691bd297b`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `384`

### Detector-Selection Intelligence

- Recommended parameter set: `a2bbfc162f9e`
- Recommended parameter short name: `a2bbfc162f9e`
- Best observed Avg IoU: `0.1634`
- Avg IoU Success: `0.8170`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3268`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_component_area_fraction`
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
| Winner stabilized after | 70 parameter sets |
| Winner stabilized | 2.6s (10% of search) |
| Near-best coverage (basin; within 0.0010) | 34 (4.7%) |
| Equivalent-best configurations (within 0.0001) | 34 (4.7%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 729 | 100.0% | 6m 2s | 1.0× |
| Non-dormant | 243 | 33.3% | 2m 1s | 3.0× |
| Low+ | 243 | 33.3% | 2m 1s | 3.0× |
| Moderate+ | 81 | 11.1% | 40.3s | 9.0× |
| Important+ | 9 | 1.2% | 4.5s | 81.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_line_count` | Important | 0.2257 | 0.0613 | 100.0% | `2` (0.1082), `3` (0.1082), `5` (0.0469) |
| `maximum_component_area_fraction` | Important | 0.1129 | 0.0434 | 100.0% | `0.02` (0.1167), `0.005` (0.0733), `0.01` (0.0733) |
| `minimum_text_coverage_fraction` | Moderate | 0.0879 | 0.0383 | 100.0% | `0.04` (0.1005), `0.08` (0.1005), `0.14` (0.0623) |
| `line_join_fraction` | Moderate | 0.0610 | 0.0367 | 33.3% | `0.05` (0.1051), `0.03` (0.0897), `0.018` (0.0685) |
| `bbox_padding_fraction` | Low | 0.0027 | 0.0077 | 33.3% | `0.04` (0.0919), `0.02` (0.0873), `0.01` (0.0842) |
| `minimum_component_area_fraction` | Dormant | 0.0007 | 0.0035 | 66.7% | `1e-05` (0.0889), `2e-05` (0.0889), `5e-05` (0.0854) |

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

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 5 | 7 ms |

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

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `9ef715dda063` | `baseline` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | unknown | unknown |
| 2 | `f7e0d706deeb` | `f7e0d706deeb` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 826 ms | 64.75% |
| 3 | `93f2d7e9ecfa` | `93f2d7e9ecfa` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 826 ms | 68.45% |
| 4 | `f2b82f6c9e72` | `f2b82f6c9e72` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 826 ms | 72.02% |
| 5 | `051f77f76305` | `051f77f76305` | 0.0000 | 0.0000 | 0.0000 | +0.0000 | 0.0000 | 5 | 823 ms | 62.14% |

## Page Analysis — whitespace_frame

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 6 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 10 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `baseline` | 0.0000 | No polygon found |
| 5 | `baseline` | 0.0000 | No polygon found |
| 6 | `baseline` | 0.0000 | No polygon found |
| 9 | `baseline` | 0.0000 | No polygon found |
| 10 | `baseline` | 0.0000 | No polygon found |

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

### Detector-Selection Intelligence

- Recommended parameter set: `9ef715dda063`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.0000`
- Avg IoU Success: `0.0000`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.0000`
- Calibration evidence: `Medium`
- Dormant parameters: `background_threshold, bbox_padding_fraction, close_kernel_fraction, maximum_page_area_fraction, minimum_border_background_fraction, minimum_page_area_fraction`
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

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `background_threshold` | Dormant | 0.0000 | 0.0000 | 100.0% | `235` (0.0000), `245` (0.0000), `250` (0.0000) |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.0000), `0.008` (0.0000), `0.016` (0.0000) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.004` (0.0000), `0.01` (0.0000), `0.02` (0.0000) |
| `maximum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.9` (0.0000), `0.96` (0.0000), `0.98` (0.0000) |
| `minimum_border_background_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.0000), `0.55` (0.0000), `0.7` (0.0000) |
| `minimum_page_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.1` (0.0000), `0.18` (0.0000), `0.28` (0.0000) |

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
- Results commit: [e3c677bf4406a7a7668251a0ad73510c60046eed](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/commit/e3c677bf4406a7a7668251a0ad73510c60046eed).
- Workflow run: [Open workflow run](https://github.com/dlstupka/hth/actions/runs/31635165152).
- Pipeline repository: [dlstupka/hth](https://github.com/dlstupka/hth).
- Results repository: [dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results).
- Calibration index: [calibration-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/e3c677bf4406a7a7668251a0ad73510c60046eed/calibration-index.json).
- Runtime index: [runtime-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/e3c677bf4406a7a7668251a0ad73510c60046eed/runtime-index.json).
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