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
    - [Adaptive Radial Edge Search (`adaptive_radial_edge`)](#adaptive-radial-edge-search-adaptiveradialedge)
    - [Radial Edge Search (`radial_edge`)](#radial-edge-search-radialedge)
    - [Gradient Boundary Voting (`gradient_vote`)](#gradient-boundary-voting-gradientvote)
    - [Edge-Supported Contour (`edge_contour`)](#edge-supported-contour-edgecontour)
    - [Contour Quadrilateral (`contour_quad`)](#contour-quadrilateral-contourquad)
    - [Cross-Edge Contour (`cross_edge_contour`)](#cross-edge-contour-crossedgecontour)
    - [Contour + Projection (`contour_projection`)](#contour-projection-contourprojection)
    - [Contour + GrabCut (`contour_grabcut`)](#contour-grabcut-contourgrabcut)
    - [Contour + Components (`contour_components`)](#contour-components-contourcomponents)
    - [Contour Envelope (`contour`)](#contour-envelope-contour)
    - [GrabCut Segmentation (`grabcut`)](#grabcut-segmentation-grabcut)
    - [GrabCut + Contour (`grabcut_contour`)](#grabcut-contour-grabcutcontour)
    - [Connected Components (`components`)](#connected-components-components)
    - [Line Segment Detector (`lsd`)](#line-segment-detector-lsd)
    - [RANSAC Border Fit (`ransac`)](#ransac-border-fit-ransac)
    - [Hough Line Borders (`hough`)](#hough-line-borders-hough)
    - [Border Energy Validator (`border_energy`)](#border-energy-validator-borderenergy)
    - [Consensus Quadrilateral (`consensus_quad`)](#consensus-quadrilateral-consensusquad)
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
    - [Cross-Edge Contour (`cross_edge_contour`)](#cross-edge-contour-crossedgecontour-2)
    - [Edge-Supported Contour (`edge_contour`)](#edge-supported-contour-edgecontour-2)
    - [GrabCut Segmentation (`grabcut`)](#grabcut-segmentation-grabcut-2)
    - [GrabCut + Contour (`grabcut_contour`)](#grabcut-contour-grabcutcontour-2)
    - [Gradient Boundary Voting (`gradient_vote`)](#gradient-boundary-voting-gradientvote-2)
    - [Hough Line Borders (`hough`)](#hough-line-borders-hough-2)
    - [Line Segment Detector (`lsd`)](#line-segment-detector-lsd-2)
    - [Radial Edge Search (`radial_edge`)](#radial-edge-search-radialedge-2)
    - [RANSAC Border Fit (`ransac`)](#ransac-border-fit-ransac-2)
- [Engineering Continuous Improvement](#engineering-continuous-improvement)
  - [Calibration Intelligence Persistence](#calibration-intelligence-persistence)
  - [Runtime Intelligence Persistence](#runtime-intelligence-persistence)
  - [Engineering Notes](#engineering-notes)

</details>


**Detectors evaluated:** 18

<a id="source-document"></a>
## Source document

- **Document:** Baptisms: San Antonio. Baptism Records 1788–1824, 1858–1898
- **Images:** 929

[↑ Back to Navigation](#table-of-contents)

<a id="detector-recommendation-for-this-golden-set"></a>
## Detector Recommendation for this Golden Set

- **Recommended detector:** Adaptive Radial Edge Search
- **Detector short name:** Adaptive Radial
- **Detector ID:** `adaptive_radial_edge`
- **Best observed Avg IoU:** `0.9599`
- **Worst Golden Set page (Min IoU):** `0.9440`
- **Page-to-page StdDev:** `0.0114`
- **Role:** `Generator`
- **Engineering Recommendation:** Retain this detector as the current Golden Set recommendation. Additional tuning should be driven by unresolved page failures, late winner changes, or a plausible untested parameter region rather than by search expansion alone.

**Recommendation basis:**

- The near-best coverage (basin) is narrow, so detector quality depends strongly on selecting a small part of the configured grid.
- 10 of 16 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- The configured grid is fully characterized for this Golden Set; continue detector work only if the resulting quality or failure pattern remains operationally inadequate.

This recommendation is specific to the evaluated Golden Set and parameter grid and should be revisited when the Golden Set, parameter grid, or source document changes.

[↑ Back to Navigation](#table-of-contents)

<a id="ranked-detector-smoke-test-results"></a>
## Ranked Detector Smoke Test Results

| Rank | Detector | Detector ID | Role | Golden Set ID | Status | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Parameter Sets | Eval Rate | Doc Time | Run Elapsed |
|---:|---|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | Adaptive Radial Edge Search | `adaptive_radial_edge` | Generator | `HTH-0001` | complete | `5010d5b46516` | `5010d5b46516` | 0.9599 | 0.9440 | 0.0114 | 0 | 6562 | 0.0853 pg/s | 3h 1m 27s | 45m 27s |
| 2 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | complete | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | 0 | 10 | 33.35 pg/s | 27.9s | 2.5s |
| 3 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | complete | `5d83cf42b823` | `5d83cf42b823` | 0.9056 | 0.7501 | 0.0877 | 0 | 10 | 41.32 pg/s | 22.5s | 2s |
| 4 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | complete | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | 0 | 10 | 4.926 pg/s | 3m 9s | 7.9s |
| 5 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | complete | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0 | 10 | 4.132 pg/s | 3m 45s | 39.1s |
| 6 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | complete | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0 | 10 | 3.024 pg/s | 5m 7s | 12.1s |
| 7 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | complete | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0 | 10 | 1.776 pg/s | 8m 43s | 20.2s |
| 8 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | complete | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0 | 10 | 0.0787 pg/s | 3h 16m 46s | 4m 5s |
| 9 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | complete | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0 | 10 | 20.02 pg/s | 46.4s | 4.2s |
| 10 | Contour Envelope | `contour` | Generator | `HTH-0001` | complete | `0bf3c1624426` | `0bf3c1624426` | 0.8392 | 0.4919 | 0.1797 | 0 | 10 | 71.02 pg/s | 13.1s | 1.7s |
| 11 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | complete | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0 | 10 | 0.0851 pg/s | 3h 1m 54s | 6m 4s |
| 12 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | complete | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0 | 10 | 0.0816 pg/s | 3h 9m 51s | 3m 55s |
| 13 | Connected Components | `components` | Generator | `HTH-0001` | complete | `7eb87978bb9a` | `7eb87978bb9a` | 0.7794 | 0.5504 | 0.1789 | 0 | 10 | 32.92 pg/s | 28.2s | 3.3s |
| 14 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | complete | `7b8b1aaee481` | `7b8b1aaee481` | 0.7368 | 0.0000 | 0.3714 | 1 | 10 | 5.546 pg/s | 2m 48s | 6.5s |
| 15 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | complete | `55356b348cc7` | `55356b348cc7` | 0.6849 | 0.0000 | 0.3801 | 1 | 10 | 10.70 pg/s | 1m 27s | 4.3s |
| 16 | Hough Line Borders | `hough` | Generator | `HTH-0001` | complete | `d2ef0aec6694` | `d2ef0aec6694` | 0.5661 | 0.0000 | 0.3407 | 1 | 10 | 0.7481 pg/s | 20m 42s | 30.3s |
| 17 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | complete | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | 2 | 10 | 3.207 pg/s | 4m 50s | 11.9s |
| 18 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | complete | `dce471449373` | `baseline` | 0.5513 | 0.0000 | 0.4513 | 2 | 10 | 1.370 pg/s | 11m 18s | 21.5s |

[↑ Back to Navigation](#table-of-contents)

<a id="metric-definitions"></a>
### Metric Definitions

- **Avg IoU:** Arithmetic mean of a detector winner's page IoUs across the Golden Set; this is the primary ranking metric.
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

| Rank | Detector | Detector ID | Role | Golden Set ID | Date | Build* | Est. Serial Runtime** | Parameter Set ID | Parameter Sets | Search Type | Successful Parameter Sets | Best Avg IoU | Min IoU | StdDev | Failures | Δ Baseline Avg IoU | Near-best Coverage (Basin) | Equivalent Best Configurations | Calibration Evidence | Approval Level |
|---:|---|---|---|---|---|---|---:|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---|---|
| **1** | **Adaptive Radial Edge Search** | **`adaptive_radial_edge`** | **Generator** | **`HTH-0001`** | **2026-08-07** | **[#241](https://github.com/dlstupka/hth/actions/runs/31142095265)** | **45m 27s** | **`5010d5b46516`** | **6562** | **exhaustive** | **100.0%** | **0.9599** | **0.9440** | **0.0114** | **0** | **+0.0270** | **0.1%** | **0.1%** | **Medium** | **Recommended** |
| 2 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 2.5s | `d593fad7aeea` | 10 | smoke | 100.0% | 0.9503 | 0.9340 | 0.0145 | 0 | +0.0000 | 10.0% | 10.0% | Medium | Provisional |
| 3 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 2s | `5d83cf42b823` | 10 | smoke | 100.0% | 0.9056 | 0.7501 | 0.0877 | 0 | +0.0175 | 90.0% | 90.0% | Medium | Provisional |
| 4 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 4m 5s | `3eec8a03f1de` | 10 | smoke | 100.0% | 0.8768 | 0.7589 | 0.0734 | 0 | +0.0000 | 100.0% | 100.0% | Medium | Provisional |
| 5 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 20.2s | `0cd13eb1a471` | 10 | smoke | 100.0% | 0.8768 | 0.7589 | 0.0734 | 0 | +0.0000 | 100.0% | 100.0% | Medium | Provisional |
| 6 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 39.1s | `bea942a4969a` | 10 | smoke | 10.0% | 0.8768 | 0.7589 | 0.0734 | 0 | +0.0000 | 10.0% | 10.0% | Low | Provisional |
| 7 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 12.1s | `a5450e58ec9e` | 10 | smoke | 40.0% | 0.8768 | 0.7589 | 0.0734 | 0 | +0.0000 | 40.0% | 40.0% | Low | Provisional |
| 8 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 7.9s | `4e5bc37a649a` | 10 | smoke | 30.0% | 0.8768 | 0.7589 | 0.0734 | 0 | +0.3377 | 30.0% | 30.0% | Low | Provisional |
| 9 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 4.2s | `14818b491952` | 10 | smoke | 100.0% | 0.8617 | 0.7572 | 0.0655 | 0 | +0.0000 | 100.0% | 100.0% | Medium | Provisional |
| 10 | Contour Envelope | `contour` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 1.7s | `0bf3c1624426` | 10 | smoke | 40.0% | 0.8392 | 0.4919 | 0.1797 | 0 | +0.1670 | 10.0% | 10.0% | Low | Provisional |
| 11 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 6m 4s | `018d128420cb` | 10 | smoke | 100.0% | 0.8130 | 0.5532 | 0.1692 | 0 | +0.0000 | 10.0% | 10.0% | Medium | Provisional |
| 12 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 3m 55s | `3817f226228a` | 10 | smoke | 100.0% | 0.8130 | 0.5532 | 0.1692 | 0 | +0.0000 | 10.0% | 10.0% | Medium | Provisional |
| 13 | Connected Components | `components` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 3.3s | `7eb87978bb9a` | 10 | smoke | 100.0% | 0.7794 | 0.5504 | 0.1789 | 0 | +0.0609 | 30.0% | 30.0% | Medium | Provisional |
| 14 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 6.5s | `7b8b1aaee481` | 10 | smoke | 0.0% | 0.7368 | 0.0000 | 0.3714 | 1 | +0.1954 | 30.0% | 30.0% | Low | Provisional |
| 15 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 4.3s | `55356b348cc7` | 10 | smoke | 0.0% | 0.6849 | 0.0000 | 0.3801 | 1 | +0.0017 | 30.0% | 30.0% | Low | Provisional |
| 16 | Hough Line Borders | `hough` | Generator | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 30.3s | `d2ef0aec6694` | 10 | smoke | 0.0% | 0.5661 | 0.0000 | 0.3407 | 1 | +0.0877 | 10.0% | 10.0% | Low | Provisional |
| 17 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 11.9s | `e38a975d1436` | 10 | smoke | 0.0% | 0.5542 | 0.0000 | 0.4538 | 2 | +0.0000 | 70.0% | 70.0% | Low | Provisional |
| 18 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | 2026-08-09 | [#260](https://github.com/dlstupka/hth/actions/runs/31290716711) | 21.5s | `dce471449373` | 10 | smoke | 0.0% | 0.5513 | 0.0000 | 0.4513 | 2 | +0.0000 | 10.0% | 10.0% | Low | Provisional |

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
- **Build*:** `#run` links open GitHub Actions logs and artifacts and expire according to repository retention; the calibration data persists in [calibration-intelligence.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/00d6e89ed3f9144dda94a9a56c505bfbf3c1592d/source-documents/baptisms-san-antonio-baptism-records-1788-1824-1858-1898/golden-sets/hth-0001/135c0ff57687/calibrations/adaptive_radial_edge/run-20260807-024337/calibration-intelligence.json).
- **Est. Serial Runtime\*\*:** Estimated single-detector serial runtime derived from recorded regression evidence; actual wall time varies with parallelism and scheduling.

[↑ Back to Navigation](#table-of-contents)

<a id="per-detector-calibration-reports"></a>
<details open>
<summary><h3>Per-Detector Calibration Reports</h3></summary>


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

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 3 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 16m 22s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9503 |
| Minimum Avg IoU | 0.8156 |
| Avg IoU StdDev | 0.0404 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 16m 24s | 1.0× |
| Non-dormant | 576 | 8.8% | 1m 26s | 11.4× |
| Low+ | 576 | 8.8% | 1m 26s | 11.4× |
| Moderate+ | 576 | 8.8% | 1m 26s | 11.4× |
| Important+ | 576 | 8.8% | 1m 26s | 11.4× |
| Critical | 64 | 1.0% | 9.6s | 102.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `gaussian_sigma` | Critical | 1.0000 | 0.1347 | 50.0% | `1.2` (0.9503), `0.8` (0.8156) |
| `gradient_percentile` | Critical | 1.0000 | 0.1347 | 50.0% | `82` (0.9503), `70` (0.8156) |
| `maximum_radius_fraction` | Critical | 1.0000 | 0.1347 | 50.0% | `0.72` (0.9503), `0.62` (0.8156) |
| `minimum_radius_fraction` | Critical | 1.0000 | 0.1347 | 50.0% | `0.18` (0.9503), `0.12` (0.8156) |
| `minimum_ray_support` | Critical | 1.0000 | 0.1347 | 50.0% | `0.45` (0.9503), `0.3` (0.8156) |
| `ray_count` | Critical | 1.0000 | 0.1347 | 50.0% | `96` (0.9503), `64` (0.8156) |
| `area_weight` | Dormant | 0.9000 | 0.0000 | 100.0% | `0.35` (0.9503) |
| `maximum_area_fraction` | Dormant | 0.9000 | 0.0000 | 100.0% | `0.98` (0.9503) |
| `minimum_area_fraction` | Dormant | 0.9000 | 0.0000 | 100.0% | `0.18` (0.9503) |
| `rectangularity_weight` | Important | 0.1667 | 0.0337 | 33.3% | `0.2` (0.8493), `0.1` (0.8156), `0.3` (0.8156) |
| `support_weight` | Important | 0.1667 | 0.0337 | 33.3% | `0.45` (0.8493), `0.35` (0.8156), `0.55` (0.8156) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `maximum_area_fraction`, `minimum_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8080 | 0.7926 | 0.9466 | 0.0462 | 100.0% |
| 5 | 0.9106 | 0.9035 | 0.9742 | 0.0212 | 100.0% |
| 6 | 0.7691 | 0.7503 | 0.9384 | 0.0565 | 100.0% |
| 9 | 0.8311 | 0.8197 | 0.9340 | 0.0343 | 100.0% |
| 10 | 0.8265 | 0.8118 | 0.9582 | 0.0439 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="gradient-boundary-voting-gradientvote"></a>
<details>
<summary><strong>Gradient Boundary Voting (`gradient_vote`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- 3 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 13m 13s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9056 |
| Minimum Avg IoU | 0.8882 |
| Avg IoU StdDev | 0.0052 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 204 ms (22% of search) |
| Near-best coverage (basin; within 0.0010) | 9 (90.0%) |
| Equivalent-best configurations (within 0.0001) | 9 (90.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 13m 14s | 1.0× |
| Non-dormant | 576 | 8.8% | 1m 10s | 11.4× |
| Low+ | 576 | 8.8% | 1m 10s | 11.4× |
| Moderate+ | 576 | 8.8% | 1m 10s | 11.4× |
| Important+ | 576 | 8.8% | 1m 10s | 11.4× |
| Critical | 64 | 1.0% | 7.7s | 102.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `border_search_fraction` | Critical | 1.0000 | 0.0175 | 50.0% | `0.35` (0.9056), `0.42` (0.8882) |
| `central_band_fraction` | Critical | 1.0000 | 0.0175 | 50.0% | `0.7` (0.9056), `0.86` (0.8882) |
| `gaussian_sigma` | Critical | 1.0000 | 0.0175 | 50.0% | `0.8` (0.9056), `1.2` (0.8882) |
| `gradient_percentile` | Critical | 1.0000 | 0.0175 | 50.0% | `70` (0.9056), `82` (0.8882) |
| `minimum_vote_support` | Critical | 1.0000 | 0.0175 | 50.0% | `0.08` (0.9056), `0.16` (0.8882) |
| `vote_smooth_fraction` | Critical | 1.0000 | 0.0175 | 50.0% | `0.006` (0.9056), `0.012` (0.8882) |
| `area_weight` | Dormant | 0.9000 | 0.0000 | 0.0% | `0.25` (0.8882) |
| `minimum_area_fraction` | Dormant | 0.9000 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `rectangularity_weight` | Dormant | 0.9000 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `minimum_span_fraction` | Important | 0.1667 | 0.0044 | 100.0% | `0.35` (0.9056), `0.55` (0.9056), `0.45` (0.9013) |
| `support_weight` | Important | 0.1667 | 0.0044 | 100.0% | `0.45` (0.9056), `0.65` (0.9056), `0.55` (0.9013) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `minimum_area_fraction`, `rectangularity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8782 | 0.8690 | 0.9613 | 0.0277 | 100.0% |
| 5 | 0.7319 | 0.5684 | 0.7501 | 0.0545 | 100.0% |
| 6 | 0.9889 | 0.9889 | 0.9889 | 0.0000 | 100.0% |
| 9 | 0.9602 | 0.9601 | 0.9612 | 0.0003 | 100.0% |
| 10 | 0.9601 | 0.9600 | 0.9611 | 0.0003 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="edge-supported-contour-edgecontour"></a>
<details>
<summary><strong>Edge-Supported Contour (`edge_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 9 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 7 of 10 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 13123 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 3h 41m 50s |
| Fully successful parameter sets | 3 (30.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.1928 |
| Avg IoU StdDev | 0.2762 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 2.7s (11% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (30.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (30.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13123 | 100.0% | 3h 42m | 1.0× |
| Non-dormant | 384 | 2.9% | 6m 30s | 34.2× |
| Low+ | 384 | 2.9% | 6m 30s | 34.2× |
| Moderate+ | 3 | 0.0% | 3s | 4374.3× |
| Important+ | 3 | 0.0% | 3s | 4374.3× |
| Critical | 3 | 0.0% | 3s | 4374.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_edge_support` | Critical | 0.9702 | 0.6841 | 33.3% | `0.05` (0.8768), `0.12` (0.4086), `0.2` (0.1928) |
| `edge_support_dilation_fraction` | Low | 0.0044 | 0.0609 | 50.0% | `0.006` (0.5392), `0.003` (0.4782) |
| `epsilon_max_fraction` | Low | 0.0044 | 0.0609 | 50.0% | `0.04` (0.5392), `0.03` (0.4782) |
| `lsd_refine_mode` | Low | 0.0044 | 0.0609 | 50.0% | `std` (0.5392), `none` (0.4782) |
| `lsd_scale` | Low | 0.0044 | 0.0609 | 50.0% | `0.8` (0.5392), `0.6` (0.4782) |
| `minimum_contour_area_fraction` | Low | 0.0044 | 0.0609 | 50.0% | `0.12` (0.5392), `0.08` (0.4782) |
| `minimum_rectangularity` | Low | 0.0044 | 0.0609 | 50.0% | `0.55` (0.5392), `0.45` (0.4782) |
| `minimum_segment_length_fraction` | Low | 0.0044 | 0.0609 | 50.0% | `0.06` (0.5392), `0.03` (0.4782) |
| `angle_weight` | Dormant | 0.0039 | 0.0000 | 0.0% | `0.2` (0.5392) |
| `area_weight` | Dormant | 0.0039 | 0.0000 | 0.0% | `0.25` (0.5392) |
| `close_iterations` | Dormant | 0.0039 | 0.0000 | 0.0% | `1` (0.5392) |
| `close_kernel_fraction` | Dormant | 0.0039 | 0.0000 | 0.0% | `0.008` (0.5392) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`, `edge_support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_edge_support` × `edge_support_dilation_fraction` | 1.0000 | 0.0298 | 10 |
| `minimum_edge_support` × `epsilon_max_fraction` | 1.0000 | 0.0298 | 10 |
| `minimum_edge_support` × `lsd_refine_mode` | 1.0000 | 0.0298 | 10 |
| `minimum_edge_support` × `lsd_scale` | 1.0000 | 0.0298 | 10 |
| `minimum_edge_support` × `minimum_contour_area_fraction` | 1.0000 | 0.0298 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.2563 | 0.0000 | 0.8542 | 0.3915 | 30.0% |
| 5 | 0.6032 | 0.0000 | 0.8618 | 0.3949 | 70.0% |
| 6 | 0.2277 | 0.0000 | 0.7589 | 0.3478 | 30.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.3707 | 0.0000 | 0.9454 | 0.4544 | 40.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="contour-quadrilateral-contourquad"></a>
<details>
<summary><strong>Contour Quadrilateral (`contour_quad`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 9 of 10 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1062882 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 14d 21h 16m 44s |
| Fully successful parameter sets | 1 (10.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.5632 |
| Avg IoU StdDev | 0.1005 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1062882 | 100.0% | 14d 21h 16m 56s | 1.0× |
| Non-dormant | 12288 | 1.2% | 4h 7m 50s | 86.5× |
| Low+ | 12288 | 1.2% | 4h 7m 50s | 86.5× |
| Moderate+ | 12288 | 1.2% | 4h 7m 50s | 86.5× |
| Important+ | 2048 | 0.2% | 41m 18s | 519.0× |
| Critical | 2048 | 0.2% | 41m 18s | 519.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `merge_fragmented_contours` | Critical | 0.7646 | 0.1757 | 50.0% | `true` (0.7389), `false` (0.5632) |
| `angle_weight` | Critical | 0.5609 | 0.2508 | 50.0% | `0.2` (0.8768), `0.1` (0.6260) |
| `area_weight` | Critical | 0.5609 | 0.2508 | 50.0% | `0.35` (0.8768), `0.25` (0.6260) |
| `close_iterations` | Critical | 0.5609 | 0.2508 | 50.0% | `1` (0.8768), `0` (0.6260) |
| `close_kernel_fraction` | Critical | 0.5609 | 0.2508 | 50.0% | `0.008` (0.8768), `0` (0.6260) |
| `epsilon_max_fraction` | Critical | 0.5609 | 0.2508 | 50.0% | `0.04` (0.8768), `0.025` (0.6260) |
| `epsilon_min_fraction` | Critical | 0.5609 | 0.2508 | 50.0% | `0.008` (0.8768), `0.004` (0.6260) |
| `epsilon_steps` | Critical | 0.5609 | 0.2508 | 50.0% | `9` (0.8768), `5` (0.6260) |
| `minimum_contour_area_fraction` | Critical | 0.5609 | 0.2508 | 50.0% | `0.12` (0.8768), `0.06` (0.6260) |
| `minimum_rectangularity` | Critical | 0.5609 | 0.2508 | 50.0% | `0.55` (0.8768), `0.45` (0.6260) |
| `rectangularity_weight` | Critical | 0.5609 | 0.2508 | 50.0% | `0.3` (0.8768), `0.2` (0.6260) |
| `edge_support_weight` | Moderate | 0.0441 | 0.0431 | 50.0% | `0.15` (0.6769), `0.1` (0.6338) |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `merge_fragmented_contours` × `angle_weight` | 1.0000 | 0.2354 | 10 |
| `merge_fragmented_contours` × `area_weight` | 1.0000 | 0.2354 | 10 |
| `merge_fragmented_contours` × `close_iterations` | 1.0000 | 0.2354 | 10 |
| `merge_fragmented_contours` × `close_kernel_fraction` | 1.0000 | 0.2354 | 10 |
| `merge_fragmented_contours` × `epsilon_max_fraction` | 1.0000 | 0.2354 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8806 | 0.8542 | 0.9069 | 0.0263 | 100.0% |
| 5 | 0.0862 | 0.0000 | 0.8618 | 0.2585 | 10.0% |
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
- 2 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
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
| Est. serial runtime for full parameter set evaluation* | 3h 34s |
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
| Exhaustive | 6562 | 100.0% | 3h 50s | 1.0× |
| Non-dormant | 768 | 11.7% | 21m 10s | 8.5× |
| Low+ | 768 | 11.7% | 21m 10s | 8.5× |
| Moderate+ | 256 | 3.9% | 7m 3s | 25.6× |
| Important+ | 256 | 3.9% | 7m 3s | 25.6× |
| Critical | 4 | 0.1% | 6.6s | 1640.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_polarity_consistency` | Critical | 1.0000 | 0.4950 | 50.0% | `0.5` (0.8768), `0.55` (0.8768), `0.65` (0.5527) |
| `epsilon_max_fraction` | Important | 0.1503 | 0.2730 | 100.0% | `0.04` (0.8768), `0.03` (0.6038) |
| `minimum_contour_area_fraction` | Important | 0.1503 | 0.2730 | 100.0% | `0.12` (0.8768), `0.08` (0.6038) |
| `minimum_cross_edge_contrast` | Important | 0.1503 | 0.2730 | 100.0% | `0.045` (0.8768), `0.02` (0.6038) |
| `minimum_rectangularity` | Important | 0.1503 | 0.2730 | 100.0% | `0.55` (0.8768), `0.45` (0.6038) |
| `sample_offset_fraction` | Important | 0.1503 | 0.2730 | 100.0% | `0.008` (0.8768), `0.004` (0.6038) |
| `samples_per_edge` | Important | 0.1503 | 0.2730 | 100.0% | `48` (0.8768), `24` (0.6038) |
| `contour_weight` | Dormant | 0.1353 | 0.0000 | 100.0% | `0.45` (0.8768) |
| `polarity_weight` | Dormant | 0.1353 | 0.0000 | 100.0% | `0.15` (0.8768) |
| `contrast_weight` | Low | 0.0251 | 0.0683 | 100.0% | `0.4` (0.6720), `0.3` (0.6038), `0.5` (0.6038) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_weight`, `polarity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

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
- Every measured parameter was dormant for this Golden Set and grid.
- Most parameter sets evaluated every Golden Set page successfully.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Further parameter tuning has low expected ROI for this source; improvement would more likely require an algorithmic change or a broader Golden Set.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 5h 7m 30s |
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
| Exhaustive | 6562 | 100.0% | 5h 7m 58s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `epsilon_max_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768) |
| `minimum_contour_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768) |
| `minimum_rectangularity` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768) |
| `projection_margin_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.06` (0.8768) |
| `projection_threshold_block_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.05` (0.8768), `0.08` (0.8768) |
| `projection_threshold_c` | Dormant | 1.0000 | 0.0000 | 100.0% | `5` (0.8768), `9` (0.8768) |
| `minimum_projection_score` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.05` (0.8768), `0.08` (0.8768), `0.15` (0.8768) |
| `projection_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) |
| `angle_weight` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.2` (0.8768) |
| `area_weight` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.25` (0.8768) |
| `close_iterations` | Dormant | 0.1000 | 0.0000 | 100.0% | `1` (0.8768) |
| `close_kernel_fraction` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.008` (0.8768) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `projection_margin_fraction`, `projection_threshold_block_fraction`, `projection_threshold_c`, `minimum_projection_score`, `projection_weight`, `angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`.

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
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 4d 19h 38m 28s |
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
| Exhaustive | 6562 | 100.0% | 4d 19h 49m 4s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `contour_epsilon_max_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768) |
| `contour_minimum_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768) |
| `contour_minimum_rectangularity` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768) |
| `grabcut_border_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.01` (0.8768), `0.02` (0.8768) |
| `grabcut_iterations` | Dormant | 1.0000 | 0.0000 | 100.0% | `1` (0.8768), `3` (0.8768) |
| `minimum_agreement_iou` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.3` (0.8768) |
| `agreement_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) |
| `grabcut_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.25` (0.8768), `0.35` (0.8768) |
| `contour_weight` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.45` (0.8768) |
| `grabcut_erosion_kernel_fraction` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.015` (0.8768) |
| `require_grabcut` | Dormant | 0.1000 | 0.0000 | 100.0% | `false` (0.8768) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_epsilon_max_fraction`, `contour_minimum_area_fraction`, `contour_minimum_rectangularity`, `grabcut_border_fraction`, `grabcut_iterations`, `minimum_agreement_iou`, `agreement_weight`, `grabcut_weight`, `contour_weight`, `grabcut_erosion_kernel_fraction`, `require_grabcut`.

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
| Search coverage | partial / adaptive |
| All possible parameter sets | 19684 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 1h 21m 54s |
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
| Exhaustive | 19684 | 100.0% | 1h 21m 57s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `component_close_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617), `0.004` (0.8617) |
| `component_dilate_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8617), `0.008` (0.8617) |
| `component_merge_gap_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.035` (0.8617), `0.02` (0.8617) |
| `component_minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.0015` (0.8617), `0.0008` (0.8617) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8617), `0.03` (0.8617) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.8617), `0.08` (0.8617) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.8617), `0.45` (0.8617) |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8617) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8617) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8617) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617) |
| `component_bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.8617) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`component_close_fraction`, `component_dilate_fraction`, `component_merge_gap_fraction`, `component_minimum_area_fraction`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `component_bbox_padding_fraction`, `component_merge_area_ratio`, `component_minimum_area_px`, `component_minimum_bbox_area_fraction`, `component_minimum_selected_area_fraction`, `component_weight`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `minimum_component_score`, `rectangularity_weight`.

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

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 2 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 6 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.7% |
| Est. serial runtime for full parameter set evaluation* | 1m 42s |
| Fully successful parameter sets | 4 (40.0%) |
| Best Avg IoU | 0.8392 |
| Minimum Avg IoU | 0.6586 |
| Avg IoU StdDev | 0.0818 |
| Winner stabilized after | 4 parameter sets |
| Winner stabilized | 195 ms (44% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1458 | 100.0% | 1m 43s | 1.0× |
| Non-dormant | 48 | 3.3% | 3.4s | 30.4× |
| Low+ | 48 | 3.3% | 3.4s | 30.4× |
| Moderate+ | 16 | 1.1% | 1.1s | 91.1× |
| Important+ | 2 | 0.1% | 141 ms | 729.0× |
| Critical | 2 | 0.1% | 141 ms | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `merge_fragmented_contours` | Critical | 0.9976 | 0.1668 | 50.0% | `true` (0.8365), `false` (0.6697) |
| `minimum_contour_area_fraction` | Moderate | 0.0684 | 0.0713 | 50.0% | `0.06` (0.7435), `0.12` (0.6722) |
| `polygon_epsilon_fraction` | Moderate | 0.0684 | 0.0713 | 50.0% | `0.008` (0.7435), `0.018` (0.6722) |
| `rectangularity_weight` | Moderate | 0.0542 | 0.0389 | 50.0% | `0.1` (0.7519), `0.25` (0.7130) |
| `bbox_padding_fraction` | Low | 0.0067 | 0.0189 | 33.3% | `0.015` (0.7462), `0` (0.7379), `0.005` (0.7273) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.7364) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.7364) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_iterations`, `close_kernel_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `rectangularity_weight` × `bbox_padding_fraction` | 0.0903 | 0.0361 | 10 |
| `minimum_contour_area_fraction` × `rectangularity_weight` | 0.0874 | 0.0191 | 10 |
| `polygon_epsilon_fraction` × `rectangularity_weight` | 0.0874 | 0.0191 | 10 |
| `minimum_contour_area_fraction` × `bbox_padding_fraction` | 0.0873 | 0.0189 | 10 |
| `polygon_epsilon_fraction` × `bbox_padding_fraction` | 0.0873 | 0.0189 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9651 | 0.9533 | 0.9734 | 0.0070 | 100.0% |
| 5 | 0.4903 | 0.4784 | 0.5178 | 0.0149 | 100.0% |
| 6 | 0.3357 | 0.0000 | 0.8763 | 0.4114 | 40.0% |
| 9 | 0.9413 | 0.9018 | 0.9585 | 0.0215 | 100.0% |
| 10 | 0.9494 | 0.9200 | 0.9593 | 0.0150 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-segmentation-grabcut"></a>
<details>
<summary><strong>GrabCut Segmentation (`grabcut`)</strong></summary>

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
| All possible parameter sets | 13122 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 8d 21h 56m 30s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8130 |
| Minimum Avg IoU | 0.7091 |
| Avg IoU StdDev | 0.0275 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13122 | 100.0% | 8d 22h 6m 17s | 1.0× |
| Non-dormant | 576 | 4.4% | 9h 23m 54s | 22.8× |
| Low+ | 576 | 4.4% | 9h 23m 54s | 22.8× |
| Moderate+ | 576 | 4.4% | 9h 23m 54s | 22.8× |
| Important+ | 576 | 4.4% | 9h 23m 54s | 22.8× |
| Critical | 192 | 1.5% | 3h 7m 58s | 68.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `border_fraction` | Critical | 0.7772 | 0.0809 | 50.0% | `0.02` (0.8130), `0.01` (0.7322) |
| `close_kernel_fraction` | Critical | 0.7772 | 0.0809 | 50.0% | `0.02` (0.8130), `0.01` (0.7322) |
| `erosion_iterations` | Critical | 0.7772 | 0.0809 | 50.0% | `1` (0.8130), `0` (0.7322) |
| `erosion_kernel_fraction` | Critical | 0.7772 | 0.0809 | 50.0% | `0.015` (0.8130), `0.0075` (0.7322) |
| `grabcut_iterations` | Critical | 0.7772 | 0.0809 | 50.0% | `3` (0.8130), `1` (0.7322) |
| `minimum_bbox_area_fraction` | Critical | 0.7772 | 0.0809 | 50.0% | `0.1` (0.8130), `0.07` (0.7322) |
| `polygon_epsilon_fraction` | Critical | 0.3445 | 0.0367 | 33.3% | `0.018` (0.7595), `0.01` (0.7320), `0.03` (0.7228) |
| `minimum_contour_area_fraction` | Important | 0.1706 | 0.0239 | 33.3% | `0.04` (0.7542), `0.02` (0.7317), `0.07` (0.7303) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.7402) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_iterations`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9612 | 0.9568 | 0.9617 | 0.0015 | 100.0% |
| 5 | 0.3782 | 0.3516 | 0.5532 | 0.0588 | 100.0% |
| 6 | 0.4656 | 0.3305 | 0.6683 | 0.0922 | 100.0% |
| 9 | 0.9432 | 0.9422 | 0.9433 | 0.0003 | 100.0% |
| 10 | 0.9530 | 0.9447 | 0.9540 | 0.0028 | 100.0% |

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
| Est. serial runtime for full parameter set evaluation* | 251d 9h 32m 25s |
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
| Exhaustive | 354295 | 100.0% | 251d 9h 42m 38s | 1.0× |
| Non-dormant | 6144 | 1.7% | 4d 8h 38m 1s | 57.7× |
| Low+ | 6144 | 1.7% | 4d 8h 38m 1s | 57.7× |
| Moderate+ | 6144 | 1.7% | 4d 8h 38m 1s | 57.7× |
| Important+ | 3072 | 0.9% | 2d 4h 19m | 115.3× |
| Critical | 512 | 0.1% | 8h 43m 10s | 692.0× |

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
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 49m 48s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.7794 |
| Minimum Avg IoU | 0.7185 |
| Avg IoU StdDev | 0.0245 |
| Winner stabilized after | 3 parameter sets |
| Winner stabilized | 433 ms (33% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (30.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (30.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19683 | 100.0% | 49m 50s | 1.0× |
| Non-dormant | 576 | 2.9% | 1m 27s | 34.2× |
| Low+ | 576 | 2.9% | 1m 27s | 34.2× |
| Moderate+ | 576 | 2.9% | 1m 27s | 34.2× |
| Important+ | 192 | 1.0% | 29.2s | 102.5× |
| Critical | 192 | 1.0% | 29.2s | 102.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `morphology_dilate_fraction` | Critical | 0.6250 | 0.0497 | 33.3% | `0.03` (0.7794), `0.015` (0.7597), `0.008` (0.7298) |
| `merge_area_ratio` | Critical | 0.2680 | 0.0423 | 50.0% | `0.01` (0.7609), `0.02` (0.7185) |
| `merge_gap_fraction` | Critical | 0.2680 | 0.0423 | 50.0% | `0.02` (0.7609), `0.035` (0.7185) |
| `minimum_bbox_area_fraction` | Critical | 0.2680 | 0.0423 | 50.0% | `0.08` (0.7609), `0.12` (0.7185) |
| `minimum_component_area_fraction` | Critical | 0.2680 | 0.0423 | 50.0% | `0.00075` (0.7609), `0.0015` (0.7185) |
| `minimum_component_area_px` | Critical | 0.2680 | 0.0423 | 50.0% | `10` (0.7609), `25` (0.7185) |
| `minimum_selected_area_fraction` | Critical | 0.2680 | 0.0423 | 50.0% | `0.02` (0.7609), `0.04` (0.7185) |
| `morphology_close_fraction` | Moderate | 0.0448 | 0.0106 | 100.0% | `0.016` (0.7609), `0.004` (0.7609), `0.008` (0.7503) |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.7566) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`bbox_padding_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `morphology_dilate_fraction` × `merge_area_ratio` | 1.0000 | 0.3750 | 10 |
| `morphology_dilate_fraction` × `merge_gap_fraction` | 1.0000 | 0.3750 | 10 |
| `morphology_dilate_fraction` × `minimum_bbox_area_fraction` | 1.0000 | 0.3750 | 10 |
| `morphology_dilate_fraction` × `minimum_component_area_fraction` | 1.0000 | 0.3750 | 10 |
| `morphology_dilate_fraction` × `minimum_component_area_px` | 1.0000 | 0.3750 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9673 | 0.9533 | 0.9734 | 0.0092 | 100.0% |
| 5 | 0.5497 | 0.4973 | 0.5725 | 0.0211 | 100.0% |
| 6 | 0.3984 | 0.2352 | 0.5504 | 0.1363 | 100.0% |
| 9 | 0.9260 | 0.9018 | 0.9429 | 0.0165 | 100.0% |
| 10 | 0.9417 | 0.9192 | 0.9543 | 0.0149 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="line-segment-detector-lsd"></a>
<details>
<summary><strong>Line Segment Detector (`lsd`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 32m 43s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7368 |
| Minimum Avg IoU | 0.5414 |
| Avg IoU StdDev | 0.0570 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.8s (22% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (30.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (30.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 32m 52s | 1.0× |
| Non-dormant | 288 | 13.2% | 4m 20s | 7.6× |
| Low+ | 288 | 13.2% | 4m 20s | 7.6× |
| Moderate+ | 288 | 13.2% | 4m 20s | 7.6× |
| Important+ | 288 | 13.2% | 4m 20s | 7.6× |
| Critical | 32 | 1.5% | 28.8s | 68.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `axis_angle_tolerance_degrees` | Critical | 0.9797 | 0.1880 | 50.0% | `10` (0.7294), `18` (0.5414) |
| `minimum_length_fraction` | Critical | 0.9797 | 0.1880 | 50.0% | `0.08` (0.7294), `0.14` (0.5414) |
| `outer_percentile` | Critical | 0.9797 | 0.1880 | 50.0% | `5` (0.7294), `10` (0.5414) |
| `refine_mode` | Critical | 0.9797 | 0.1880 | 50.0% | `none` (0.7294), `std` (0.5414) |
| `scale` | Critical | 0.9797 | 0.1880 | 50.0% | `0.6` (0.7294), `0.8` (0.5414) |
| `minimum_bbox_area_fraction` | Important | 0.1633 | 0.0470 | 100.0% | `0.08` (0.7294), `0.15` (0.7294), `0.1` (0.6824) |
| `bbox_padding_fraction` | Important | 0.1433 | 0.0510 | 33.3% | `0.005` (0.7368), `0.015` (0.7174), `0` (0.6858) |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8973 | 0.8828 | 0.9095 | 0.0105 | 100.0% |
| 5 | 0.8746 | 0.0000 | 0.9782 | 0.2916 | 90.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8338 | 0.8091 | 0.8475 | 0.0164 | 100.0% |
| 10 | 0.9474 | 0.9209 | 0.9641 | 0.0175 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="ransac-border-fit-ransac"></a>
<details>
<summary><strong>RANSAC Border Fit (`ransac`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.7% |
| Est. serial runtime for full parameter set evaluation* | 11m 16s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.6849 |
| Minimum Avg IoU | 0.6732 |
| Avg IoU StdDev | 0.0049 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 647 ms (11% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (30.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (30.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1458 | 100.0% | 11m 21s | 1.0× |
| Non-dormant | 288 | 19.8% | 2m 15s | 5.1× |
| Low+ | 288 | 19.8% | 2m 15s | 5.1× |
| Moderate+ | 3 | 0.2% | 1.4s | 486.0× |
| Important+ | 3 | 0.2% | 1.4s | 486.0× |
| Critical | 3 | 0.2% | 1.4s | 486.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `bbox_padding_fraction` | Critical | 0.9909 | 0.0112 | 33.3% | `0` (0.6844), `0.008` (0.6831), `0.016` (0.6732) |
| `max_trials` | Low | 0.0277 | 0.0027 | 50.0% | `400` (0.6831), `200` (0.6804) |
| `minimum_mean_inlier_ratio` | Low | 0.0277 | 0.0027 | 50.0% | `0.45` (0.6831), `0.25` (0.6804) |
| `minimum_scan_foreground_fraction` | Low | 0.0277 | 0.0027 | 50.0% | `0.0125` (0.6831), `0.008` (0.6804) |
| `residual_threshold_fraction` | Low | 0.0277 | 0.0027 | 50.0% | `0.008` (0.6831), `0.004` (0.6804) |
| `scan_samples` | Low | 0.0277 | 0.0027 | 50.0% | `220` (0.6831), `140` (0.6804) |
| `minimum_bbox_area_fraction` | Low | 0.0046 | 0.0007 | 100.0% | `0.18` (0.6811), `0.1` (0.6804), `0.28` (0.6804) |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `bbox_padding_fraction` × `max_trials` | 1.0000 | 0.0091 | 10 |
| `bbox_padding_fraction` × `minimum_mean_inlier_ratio` | 1.0000 | 0.0091 | 10 |
| `bbox_padding_fraction` × `minimum_scan_foreground_fraction` | 1.0000 | 0.0091 | 10 |
| `bbox_padding_fraction` × `residual_threshold_fraction` | 1.0000 | 0.0091 | 10 |
| `bbox_padding_fraction` × `scan_samples` | 1.0000 | 0.0091 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9713 | 0.9665 | 0.9770 | 0.0043 | 100.0% |
| 5 | 0.5547 | 0.5289 | 0.5768 | 0.0178 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9327 | 0.9029 | 0.9553 | 0.0217 | 100.0% |
| 10 | 0.9446 | 0.9196 | 0.9652 | 0.0176 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="hough-line-borders-hough"></a>
<details>
<summary><strong>Hough Line Borders (`hough`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 8 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2188 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 4h 2m 37s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5661 |
| Minimum Avg IoU | 0.3084 |
| Avg IoU StdDev | 0.0963 |
| Winner stabilized after | 4 parameter sets |
| Winner stabilized | 16.3s (44% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2188 | 100.0% | 4h 3m 44s | 1.0× |
| Non-dormant | 288 | 13.2% | 32m 5s | 7.6× |
| Low+ | 288 | 13.2% | 32m 5s | 7.6× |
| Moderate+ | 3 | 0.1% | 20.1s | 729.3× |
| Important+ | 3 | 0.1% | 20.1s | 729.3× |
| Critical | 3 | 0.1% | 20.1s | 729.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `outer_percentile` | Critical | 0.9920 | 0.2393 | 33.3% | `5` (0.5571), `10` (0.4874), `20` (0.3177) |
| `axis_angle_tolerance_degrees` | Low | 0.0053 | 0.0234 | 50.0% | `22` (0.4784), `12` (0.4551) |
| `canny_low_threshold` | Low | 0.0053 | 0.0234 | 50.0% | `40` (0.4784), `25` (0.4551) |
| `hough_threshold_fraction` | Low | 0.0053 | 0.0234 | 50.0% | `0.055` (0.4784), `0.035` (0.4551) |
| `maximum_gap_fraction` | Low | 0.0053 | 0.0234 | 50.0% | `0.055` (0.4784), `0.025` (0.4551) |
| `minimum_length_fraction` | Low | 0.0053 | 0.0234 | 50.0% | `0.2` (0.4784), `0.12` (0.4551) |
| `minimum_bbox_area_fraction` | Dormant | 0.0048 | 0.0000 | 0.0% | `0.1` (0.4784) |
| `bbox_padding_fraction` | Low | 0.0035 | 0.0128 | 33.3% | `0.015` (0.4660), `0` (0.4541), `0.005` (0.4532) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_percentile` × `axis_angle_tolerance_degrees` | 0.9932 | 0.0012 | 10 |
| `outer_percentile` × `canny_low_threshold` | 0.9932 | 0.0012 | 10 |
| `outer_percentile` × `hough_threshold_fraction` | 0.9932 | 0.0012 | 10 |
| `outer_percentile` × `maximum_gap_fraction` | 0.9932 | 0.0012 | 10 |
| `outer_percentile` × `minimum_length_fraction` | 0.9932 | 0.0012 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.6600 | 0.4658 | 0.8453 | 0.1360 | 100.0% |
| 5 | 0.2116 | 0.0000 | 0.3411 | 0.1399 | 70.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.6923 | 0.4958 | 0.8136 | 0.1221 | 100.0% |
| 10 | 0.7231 | 0.5805 | 0.8305 | 0.0921 | 100.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="border-energy-validator-borderenergy"></a>
<details>
<summary><strong>Border Energy Validator (`border_energy`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 2 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 2h 50m 16s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5542 |
| Minimum Avg IoU | 0.3651 |
| Avg IoU StdDev | 0.0866 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 7 (70.0%) |
| Equivalent-best configurations (within 0.0001) | 7 (70.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 2h 50m 32s | 1.0× |
| Non-dormant | 576 | 8.8% | 14m 58s | 11.4× |
| Low+ | 576 | 8.8% | 14m 58s | 11.4× |
| Moderate+ | 192 | 2.9% | 4m 59s | 34.2× |
| Important+ | 3 | 0.0% | 4.7s | 2187.3× |
| Critical | 3 | 0.0% | 4.7s | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_side_consistency` | Critical | 1.0000 | 0.1891 | 66.7% | `0.3` (0.5542), `0.45` (0.5542), `0.6` (0.3651) |
| `band_fraction` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.008` (0.5542), `0.004` (0.4912) |
| `epsilon_max_fraction` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.04` (0.5542), `0.03` (0.4912) |
| `gaussian_sigma` | Moderate | 0.0476 | 0.0630 | 100.0% | `1.2` (0.5542), `0.8` (0.4912) |
| `minimum_border_energy` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.1` (0.5542), `0.05` (0.4912) |
| `minimum_contour_area_fraction` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.12` (0.5542), `0.08` (0.4912) |
| `minimum_rectangularity` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.55` (0.5542), `0.45` (0.4912) |
| `consistency_weight` | Dormant | 0.0429 | 0.0000 | 100.0% | `0.15` (0.5542) |
| `contour_weight` | Dormant | 0.0429 | 0.0000 | 100.0% | `0.45` (0.5542) |
| `energy_weight` | Low | 0.0079 | 0.0158 | 100.0% | `0.4` (0.5069), `0.3` (0.4912), `0.5` (0.4912) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consistency_weight`, `contour_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.6618 | 0.0000 | 0.9454 | 0.4332 | 70.0% |

</details>

[↑ Back to Navigation](#table-of-contents)

<a id="consensus-quadrilateral-consensusquad"></a>
<details>
<summary><strong>Consensus Quadrilateral (`consensus_quad`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 243 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 4.1% |
| Est. serial runtime for full parameter set evaluation* | 14m 10s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5513 |
| Minimum Avg IoU | 0.3651 |
| Avg IoU StdDev | 0.0558 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 243 | 100.0% | 14m 47s | 1.0× |
| Non-dormant | 72 | 29.6% | 4m 23s | 3.4× |
| Low+ | 72 | 29.6% | 4m 23s | 3.4× |
| Moderate+ | 72 | 29.6% | 4m 23s | 3.4× |
| Important+ | 72 | 29.6% | 4m 23s | 3.4× |
| Critical | 8 | 3.3% | 29.2s | 30.4× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `contour_quad_weight` | Critical | 1.0000 | 0.1860 | 50.0% | `0.5` (0.5513), `0.25` (0.3653) |
| `maximum_mean_corner_distance_fraction` | Critical | 1.0000 | 0.1860 | 50.0% | `0.025` (0.5513), `0.015` (0.3653) |
| `minimum_polygon_iou` | Critical | 1.0000 | 0.1860 | 50.0% | `0.9` (0.5513), `0.8` (0.3653) |
| `minimum_consensus_confidence` | Important | 0.1667 | 0.0465 | 33.3% | `0.2` (0.4118), `0.1` (0.3653), `0.35` (0.3653) |
| `edge_contour_weight` | Important | 0.1651 | 0.0464 | 33.3% | `0.5` (0.4116), `0.75` (0.3654), `0.25` (0.3653) |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_consensus_confidence` × `edge_contour_weight` | 0.4434 | 0.2767 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.8619 | 0.8616 | 0.8624 | 0.0004 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9644 | 0.9636 | 0.9647 | 0.0005 | 100.0% |
| 10 | 0.0930 | 0.0000 | 0.9302 | 0.2791 | 10.0% |

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
| Detector runs completed | 18 of 18 | Successful detector regressions completed out of those scheduled. |
| Parameter sets evaluated | 6732 | Total detector parameter configurations evaluated across all runs. |
| Golden Set page evaluations | 33660 | Parameter sets multiplied by evaluated Golden Set pages. |
| Aggregate detector runtime | 1h 2m 19s | Sum of detector wall-clock runtimes; this is not the elapsed time experienced by the user. |
| Regression wall-clock span | 2d 39s | Earliest detector start through latest detector finish. |
| Effective detector concurrency | 0.02× | Aggregate detector runtime divided by regression wall-clock span. |
| Detector pipelines | mixed | Maximum concurrent detector regressions used by this build. |
| Loading strategy | LPT | Strategy used to order the shared detector queue. |
| Pipeline stagger | 0m | Delay between initial pipeline starts; replacement loads begin immediately. |
| Source-document images | 929 | Total images recorded for the source document. |

[↑ Back to Navigation](#table-of-contents)

<a id="regression-execution-and-detector-queueing"></a>
### Regression Execution and Detector Queueing

| Setting | Value |
|---|---|
| Detector pipelines | mixed |
| Detector loading strategy | LPT |
| Threads per detector regression | mixed |
| Pipeline start stagger | 0m |
| Runtime intelligence | `runtime-index.json` |
| Parallelism intelligence | `parallelism-index.json` |
| Calibration intelligence | `calibration-index.json` |

Detector pipelines pull continuously from one shared queue. Once a detector finishes, that pipeline immediately loads the next queued detector until the queue is empty.

| Queue | Detector | Pipeline | Estimated Runtime | Scheduling Basis |
|---:|---|---:|---:|---|
| 1 | Adaptive Radial Edge Search (`adaptive_radial_edge`) | 1 | unknown | single-detector |
| 1 | GrabCut Segmentation (`grabcut`) | 1 | 5m 59s | runtime-index:mode+strategy+dimension+golden-set:score=108 |
| 2 | GrabCut + Contour (`grabcut_contour`) | 2 | 4m 7s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 3 | Contour + GrabCut (`contour_grabcut`) | 4 | 3m 51s | runtime-index:mode+strategy+dimension+golden-set:score=108 |
| 4 | Hough Line Borders (`hough`) | 3 | 41.2s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 5 | Contour Quadrilateral (`contour_quad`) | 3 | 37.1s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 6 | Consensus Quadrilateral (`consensus_quad`) | 3 | 19s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 7 | Contour + Projection (`contour_projection`) | 3 | 13.6s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 8 | Border Energy Validator (`border_energy`) | 3 | 10.4s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 10 | Cross-Edge Contour (`cross_edge_contour`) | 3 | 8.3s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 11 | Edge-Supported Contour (`edge_contour`) | 3 | 6.3s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 12 | Line Segment Detector (`lsd`) | 3 | 5s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 13 | Contour + Components (`contour_components`) | 3 | 3.1s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 14 | RANSAC Border Fit (`ransac`) | 3 | 2.5s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 15 | Radial Edge Search (`radial_edge`) | 3 | 2.1s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 16 | Connected Components (`components`) | 3 | 1.9s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 17 | Gradient Boundary Voting (`gradient_vote`) | 3 | 1.2s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 18 | Contour Envelope (`contour`) | 3 | 863 ms | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |

Queue order reflects the selected loading strategy. LPT schedules the longest estimated detector work first, FIFO preserves configured detector order, and Ranked uses historical detector quality.

[↑ Back to Navigation](#table-of-contents)

<a id="regression-recommendations-summary"></a>
### Regression Recommendations Summary

#### Execution Configuration

| Setting | Recommended | Basis |
|---|---|---|
| Detector pipelines | 4 | Current HTH default for multi-detector regressions. |
| Detector loading | LPT | Reduces the slow-detector tail by loading historically longest regressions first. |
| Threads per detector regression | mixed | Preserve the current measured setting until runtime history supports a different thread recommendation. |
| Startup stagger | 0m | Avoids idle startup time unless runner contention requires a stagger. |

#### Estimated Runtime

| All-Detector Regression Scope | Estimated Wall Time* |
|---|---:|
| Exhaustive | 152d 19h 16m 20s |
| Non-dormant | 4d 15h 2m 4s |
| Critical only | 2d 10h 8m 13s |

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

## Run Information

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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `5010d5b46516` | `5010d5b46516` | 0.9599 | 0.9440 | 0.0114 | 0 | 58.6s |
| Baseline | `a132c2ac5e87` | `baseline` | 0.9329 | 0.8817 | 0.0344 | 0 | 312 ms |

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

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `5010d5b46516` | `5010d5b46516` | 0.9599 | 0.9440 | 0.0114 | +0.0000 | 0 | 44m 25s | 95.93% |
| 2 | `1d2294489ce9` | `1d2294489ce9` | 0.9599 | 0.9440 | 0.0114 | +0.0000 | 0 | 44m 28s | 96.04% |
| 3 | `21f3dd1c2b25` | `21f3dd1c2b25` | 0.9599 | 0.9440 | 0.0114 | +0.0000 | 0 | 44m 34s | 96.33% |
| 4 | `27b17406868e` | `27b17406868e` | 0.9599 | 0.9440 | 0.0114 | +0.0000 | 0 | 44m 29s | 96.08% |
| 5 | `f57ce0314a73` | `f57ce0314a73` | 0.9585 | 0.9327 | 0.0159 | -0.0013 | 0 | 44m 40s | 96.57% |

## Page Analysis

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

## Calibration Intelligence

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

## Run Information

### Build Provenance

- Run ID: `run-20260809-024011`
- Detector: `border_energy`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:40:11.618875+00:00`
- Finished: `2026-08-09T02:40:23.486568+00:00`
- Wall-clock elapsed: `11.9s`
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
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | 2 | 1.6s |

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
| StdDev improvements | 1 |
| Total metric improvements | 1 |
| Parameter sets with improvements | 1 |
| Winner changes | 0 |
| Baseline surpassed | no |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | +0.0000 | 2 | unknown | unknown |
| 2 | `ee832909df97` | `ee832909df97` | 0.5542 | 0.0000 | 0.4538 | +0.0000 | 2 | 3.5s | 22.22% |
| 3 | `24d1f88af992` | `24d1f88af992` | 0.5542 | 0.0000 | 0.4538 | +0.0000 | 2 | 3.4s | 11.11% |
| 4 | `66d5d1766542` | `66d5d1766542` | 0.5542 | 0.0000 | 0.4538 | +0.0000 | 2 | 5.5s | 44.44% |
| 5 | `d051925a3a6c` | `d051925a3a6c` | 0.5542 | 0.0000 | 0.4538 | +0.0000 | 2 | 4.9s | 33.33% |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `baseline` | 0.8618 | 0.8618 | +0.0000 | Unchanged |
| 6 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `baseline` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `baseline` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

Total winner changes: **0**.
Search completed in **11.9s** wall-clock time.

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
- No polygon found: `2`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `baseline` | 0.0000 | No polygon found |
| 6 | `baseline` | 0.0000 | No polygon found |

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024011`
- Calibration schema: `1.1`
- Detector: `border_energy`
- Detector configuration: `hth-pipeline/config/detectors/border_energy.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `e38a975d1436`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.5542`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4538`
- Calibration evidence: `Low`
- Dormant parameters: `consistency_weight, contour_weight`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 2 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 2h 50m 16s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5542 |
| Minimum Avg IoU | 0.3651 |
| Avg IoU StdDev | 0.0866 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 7 (70.0%) |
| Equivalent-best configurations (within 0.0001) | 7 (70.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 2h 50m 32s | 1.0× |
| Non-dormant | 576 | 8.8% | 14m 58s | 11.4× |
| Low+ | 576 | 8.8% | 14m 58s | 11.4× |
| Moderate+ | 192 | 2.9% | 4m 59s | 34.2× |
| Important+ | 3 | 0.0% | 4.7s | 2187.3× |
| Critical | 3 | 0.0% | 4.7s | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_side_consistency` | Critical | 1.0000 | 0.1891 | 66.7% | `0.3` (0.5542), `0.45` (0.5542), `0.6` (0.3651) |
| `band_fraction` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.008` (0.5542), `0.004` (0.4912) |
| `epsilon_max_fraction` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.04` (0.5542), `0.03` (0.4912) |
| `gaussian_sigma` | Moderate | 0.0476 | 0.0630 | 100.0% | `1.2` (0.5542), `0.8` (0.4912) |
| `minimum_border_energy` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.1` (0.5542), `0.05` (0.4912) |
| `minimum_contour_area_fraction` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.12` (0.5542), `0.08` (0.4912) |
| `minimum_rectangularity` | Moderate | 0.0476 | 0.0630 | 100.0% | `0.55` (0.5542), `0.45` (0.4912) |
| `consistency_weight` | Dormant | 0.0429 | 0.0000 | 100.0% | `0.15` (0.5542) |
| `contour_weight` | Dormant | 0.0429 | 0.0000 | 100.0% | `0.45` (0.5542) |
| `energy_weight` | Low | 0.0079 | 0.0158 | 100.0% | `0.4` (0.5069), `0.3` (0.4912), `0.5` (0.4912) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consistency_weight`, `contour_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.8618 | 0.8618 | 0.8618 | 0.0000 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.6618 | 0.0000 | 0.9454 | 0.4332 | 70.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="connected-components-components-2"></a>
<details>
<summary><strong>Connected Components (`components`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-024137`
- Detector: `components`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:41:37.469625+00:00`
- Finished: `2026-08-09T02:41:40.814065+00:00`
- Wall-clock elapsed: `3.3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `19683`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.05%`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `7eb87978bb9a` | `7eb87978bb9a` | 0.7794 | 0.5504 | 0.1789 | 0 | 153 ms |
| Baseline | `4e09dc84fa8a` | `baseline` | 0.7185 | 0.2413 | 0.2967 | 0 | 130 ms |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Connected-component envelope | Primary | Generates a page-region hypothesis from grouped foreground components. |
| Morphological grouping | Supporting | Controls how fragmented marks are joined before envelope extraction. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 3 |
| Minimum IoU improvements | 2 |
| StdDev improvements | 3 |
| Total metric improvements | 8 |
| Parameter sets with improvements | 3 |
| Winner changes | 3 |
| Baseline surpassed | yes |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `7eb87978bb9a` | `7eb87978bb9a` | 0.7794 | 0.5504 | 0.1789 | +0.0000 | 0 | 433 ms | 33.33% |
| 2 | `2a180d02de36` | `2a180d02de36` | 0.7794 | 0.5504 | 0.1789 | +0.0000 | 0 | 608 ms | 55.56% |
| 3 | `b6a644d99d2e` | `b6a644d99d2e` | 0.7794 | 0.5504 | 0.1789 | +0.0000 | 0 | 921 ms | 100.00% |
| 4 | `04ff9a0c7a86` | `04ff9a0c7a86` | 0.7734 | 0.4617 | 0.2201 | -0.0060 | 0 | 346 ms | 22.22% |
| 5 | `732d1fd40ae7` | `732d1fd40ae7` | 0.7734 | 0.4617 | 0.2201 | -0.0060 | 0 | 654 ms | 66.67% |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `7eb87978bb9a` | 0.9734 | 0.9533 | -0.0201 | Regressed |
| 5 | `7eb87978bb9a` | 0.4973 | 0.5725 | +0.0752 | Improved |
| 6 | `7eb87978bb9a` | 0.2413 | 0.5504 | +0.3091 | Improved |
| 9 | `7eb87978bb9a` | 0.9314 | 0.9018 | -0.0296 | Regressed |
| 10 | `7eb87978bb9a` | 0.9491 | 0.9192 | -0.0299 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `9482fe4b59f2` | 286 ms | 11.11% |
| 2 | `04ff9a0c7a86` | 346 ms | 22.22% |
| 3 (final) | `7eb87978bb9a` | 433 ms | 33.33% |

Total winner changes: **3**.
Search completed in **3.3s** wall-clock time.

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

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `7eb87978bb9a` | 0.9533 | Regressed |
| 9 | `7eb87978bb9a` | 0.9018 | Regressed |
| 10 | `7eb87978bb9a` | 0.9192 | Regressed |

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024137`
- Calibration schema: `1.1`
- Detector: `components`
- Detector configuration: `hth-pipeline/config/detectors/components.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `7eb87978bb9a`
- Recommended parameter short name: `7eb87978bb9a`
- Best observed Avg IoU: `0.7794`
- Worst Golden Set page (Min IoU): `0.5504`
- Page-to-page StdDev: `0.1789`
- Calibration evidence: `Medium`
- Dormant parameters: `bbox_padding_fraction`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

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
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 49m 48s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.7794 |
| Minimum Avg IoU | 0.7185 |
| Avg IoU StdDev | 0.0245 |
| Winner stabilized after | 3 parameter sets |
| Winner stabilized | 433 ms (33% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (30.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (30.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19683 | 100.0% | 49m 50s | 1.0× |
| Non-dormant | 576 | 2.9% | 1m 27s | 34.2× |
| Low+ | 576 | 2.9% | 1m 27s | 34.2× |
| Moderate+ | 576 | 2.9% | 1m 27s | 34.2× |
| Important+ | 192 | 1.0% | 29.2s | 102.5× |
| Critical | 192 | 1.0% | 29.2s | 102.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `morphology_dilate_fraction` | Critical | 0.6250 | 0.0497 | 33.3% | `0.03` (0.7794), `0.015` (0.7597), `0.008` (0.7298) |
| `merge_area_ratio` | Critical | 0.2680 | 0.0423 | 50.0% | `0.01` (0.7609), `0.02` (0.7185) |
| `merge_gap_fraction` | Critical | 0.2680 | 0.0423 | 50.0% | `0.02` (0.7609), `0.035` (0.7185) |
| `minimum_bbox_area_fraction` | Critical | 0.2680 | 0.0423 | 50.0% | `0.08` (0.7609), `0.12` (0.7185) |
| `minimum_component_area_fraction` | Critical | 0.2680 | 0.0423 | 50.0% | `0.00075` (0.7609), `0.0015` (0.7185) |
| `minimum_component_area_px` | Critical | 0.2680 | 0.0423 | 50.0% | `10` (0.7609), `25` (0.7185) |
| `minimum_selected_area_fraction` | Critical | 0.2680 | 0.0423 | 50.0% | `0.02` (0.7609), `0.04` (0.7185) |
| `morphology_close_fraction` | Moderate | 0.0448 | 0.0106 | 100.0% | `0.016` (0.7609), `0.004` (0.7609), `0.008` (0.7503) |
| `bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.7566) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`bbox_padding_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `morphology_dilate_fraction` × `merge_area_ratio` | 1.0000 | 0.3750 | 10 |
| `morphology_dilate_fraction` × `merge_gap_fraction` | 1.0000 | 0.3750 | 10 |
| `morphology_dilate_fraction` × `minimum_bbox_area_fraction` | 1.0000 | 0.3750 | 10 |
| `morphology_dilate_fraction` × `minimum_component_area_fraction` | 1.0000 | 0.3750 | 10 |
| `morphology_dilate_fraction` × `minimum_component_area_px` | 1.0000 | 0.3750 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9673 | 0.9533 | 0.9734 | 0.0092 | 100.0% |
| 5 | 0.5497 | 0.4973 | 0.5725 | 0.0211 | 100.0% |
| 6 | 0.3984 | 0.2352 | 0.5504 | 0.1363 | 100.0% |
| 9 | 0.9260 | 0.9018 | 0.9429 | 0.0165 | 100.0% |
| 10 | 0.9417 | 0.9192 | 0.9543 | 0.0149 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="consensus-quadrilateral-consensusquad-2"></a>
<details>
<summary><strong>Consensus Quadrilateral (`consensus_quad`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-023924`
- Detector: `consensus_quad`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:39:24.716957+00:00`
- Finished: `2026-08-09T02:39:46.245948+00:00`
- Wall-clock elapsed: `21.5s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `243`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `4.12%`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `dce471449373` | `baseline` | 0.5513 | 0.0000 | 0.4513 | 2 | 3.6s |

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
| Avg IoU improvements | 0 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 2 |
| Total metric improvements | 2 |
| Parameter sets with improvements | 2 |
| Winner changes | 0 |
| Baseline surpassed | no |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `dce471449373` | `baseline` | 0.5513 | 0.0000 | 0.4513 | +0.0000 | 2 | unknown | unknown |
| 2 | `48c503656d02` | `48c503656d02` | 0.3654 | 0.0000 | 0.4487 | -0.1859 | 3 | 18.2s | 88.89% |
| 3 | `957153998277` | `957153998277` | 0.3654 | 0.0000 | 0.4487 | -0.1859 | 3 | 17.6s | 77.78% |
| 4 | `1752e509b03b` | `1752e509b03b` | 0.3654 | 0.0000 | 0.4487 | -0.1859 | 3 | 20.2s | 100.00% |
| 5 | `0c4cd99b53b0` | `0c4cd99b53b0` | 0.3653 | 0.0000 | 0.4485 | -0.1860 | 3 | 7.2s | 11.11% |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `baseline` | 0.8616 | 0.8616 | +0.0000 | Unchanged |
| 6 | `baseline` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `baseline` | 0.9647 | 0.9647 | +0.0000 | Unchanged |
| 10 | `baseline` | 0.9302 | 0.9302 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

Total winner changes: **0**.
Search completed in **21.5s** wall-clock time.

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
- No polygon found: `2`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `baseline` | 0.0000 | No polygon found |
| 6 | `baseline` | 0.0000 | No polygon found |

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-023924`
- Calibration schema: `1.1`
- Detector: `consensus_quad`
- Detector configuration: `hth-pipeline/config/detectors/consensus_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `dce471449373`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.5513`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4513`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 243 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 4.1% |
| Est. serial runtime for full parameter set evaluation* | 14m 10s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5513 |
| Minimum Avg IoU | 0.3651 |
| Avg IoU StdDev | 0.0558 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 243 | 100.0% | 14m 47s | 1.0× |
| Non-dormant | 72 | 29.6% | 4m 23s | 3.4× |
| Low+ | 72 | 29.6% | 4m 23s | 3.4× |
| Moderate+ | 72 | 29.6% | 4m 23s | 3.4× |
| Important+ | 72 | 29.6% | 4m 23s | 3.4× |
| Critical | 8 | 3.3% | 29.2s | 30.4× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `contour_quad_weight` | Critical | 1.0000 | 0.1860 | 50.0% | `0.5` (0.5513), `0.25` (0.3653) |
| `maximum_mean_corner_distance_fraction` | Critical | 1.0000 | 0.1860 | 50.0% | `0.025` (0.5513), `0.015` (0.3653) |
| `minimum_polygon_iou` | Critical | 1.0000 | 0.1860 | 50.0% | `0.9` (0.5513), `0.8` (0.3653) |
| `minimum_consensus_confidence` | Important | 0.1667 | 0.0465 | 33.3% | `0.2` (0.4118), `0.1` (0.3653), `0.35` (0.3653) |
| `edge_contour_weight` | Important | 0.1651 | 0.0464 | 33.3% | `0.5` (0.4116), `0.75` (0.3654), `0.25` (0.3653) |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_consensus_confidence` × `edge_contour_weight` | 0.4434 | 0.2767 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 5 | 0.8619 | 0.8616 | 0.8624 | 0.0004 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9644 | 0.9636 | 0.9647 | 0.0005 | 100.0% |
| 10 | 0.0930 | 0.0000 | 0.9302 | 0.2791 | 10.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-envelope-contour-2"></a>
<details>
<summary><strong>Contour Envelope (`contour`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-024146`
- Detector: `contour`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:41:46.794892+00:00`
- Finished: `2026-08-09T02:41:48.514976+00:00`
- Wall-clock elapsed: `1.7s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1458`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.69%`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `0bf3c1624426` | `0bf3c1624426` | 0.8392 | 0.4919 | 0.1797 | 0 | 71 ms |
| Baseline | `6019a18e4c4e` | `baseline` | 0.6722 | 0.0000 | 0.3846 | 1 | 38 ms |

### Detector Evidence

**Role:** Generator

| Evidence source | Function | Interpretation |
|---|---|---|
| Contour geometry | Primary | Generates page-region hypotheses from thresholded contours. |
| Fragment merging | Supporting | Attempts to recover page boundaries split across multiple contours. |

### Regression Statistics for Detector Calibration

| Statistic | Count |
|---|---:|
| Avg IoU improvements | 2 |
| Minimum IoU improvements | 3 |
| StdDev improvements | 3 |
| Total metric improvements | 8 |
| Parameter sets with improvements | 3 |
| Winner changes | 2 |
| Baseline surpassed | yes |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `0bf3c1624426` | `0bf3c1624426` | 0.8392 | 0.4919 | 0.1797 | +0.0000 | 0 | 195 ms | 44.44% |
| 2 | `a20447ccca1e` | `a20447ccca1e` | 0.8364 | 0.4784 | 0.1870 | -0.0028 | 0 | 118 ms | 11.11% |
| 3 | `160333f7751d` | `160333f7751d` | 0.8364 | 0.4784 | 0.1870 | -0.0028 | 0 | 346 ms | 88.89% |
| 4 | `e0ad87b12d87` | `e0ad87b12d87` | 0.8338 | 0.5178 | 0.1600 | -0.0054 | 0 | 266 ms | 66.67% |
| 5 | `6019a18e4c4e` | `baseline` | 0.6722 | 0.0000 | 0.3846 | -0.1670 | 1 | unknown | unknown |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `0bf3c1624426` | 0.9648 | 0.9734 | +0.0086 | Improved |
| 5 | `0bf3c1624426` | 0.4784 | 0.4919 | +0.0135 | Improved |
| 6 | `0bf3c1624426` | 0.0000 | 0.8392 | +0.8392 | Recovered |
| 9 | `0bf3c1624426` | 0.9585 | 0.9390 | -0.0195 | Regressed |
| 10 | `0bf3c1624426` | 0.9593 | 0.9526 | -0.0067 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `a20447ccca1e` | 118 ms | 11.11% |
| 2 (final) | `0bf3c1624426` | 195 ms | 44.44% |

Total winner changes: **2**.
Search completed in **1.7s** wall-clock time.

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
- Poor matches (Winner IoU < 0.5000): `1`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 5 | `0bf3c1624426` | 0.4919 | Poor match |
| 9 | `0bf3c1624426` | 0.9390 | Regressed |
| 10 | `0bf3c1624426` | 0.9526 | Regressed |

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024146`
- Calibration schema: `1.1`
- Detector: `contour`
- Detector configuration: `hth-pipeline/config/detectors/contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `0bf3c1624426`
- Recommended parameter short name: `0bf3c1624426`
- Best observed Avg IoU: `0.8392`
- Worst Golden Set page (Min IoU): `0.4919`
- Page-to-page StdDev: `0.1797`
- Calibration evidence: `Low`
- Dormant parameters: `close_iterations, close_kernel_fraction`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 2 of 7 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 6 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.7% |
| Est. serial runtime for full parameter set evaluation* | 1m 42s |
| Fully successful parameter sets | 4 (40.0%) |
| Best Avg IoU | 0.8392 |
| Minimum Avg IoU | 0.6586 |
| Avg IoU StdDev | 0.0818 |
| Winner stabilized after | 4 parameter sets |
| Winner stabilized | 195 ms (44% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1458 | 100.0% | 1m 43s | 1.0× |
| Non-dormant | 48 | 3.3% | 3.4s | 30.4× |
| Low+ | 48 | 3.3% | 3.4s | 30.4× |
| Moderate+ | 16 | 1.1% | 1.1s | 91.1× |
| Important+ | 2 | 0.1% | 141 ms | 729.0× |
| Critical | 2 | 0.1% | 141 ms | 729.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `merge_fragmented_contours` | Critical | 0.9976 | 0.1668 | 50.0% | `true` (0.8365), `false` (0.6697) |
| `minimum_contour_area_fraction` | Moderate | 0.0684 | 0.0713 | 50.0% | `0.06` (0.7435), `0.12` (0.6722) |
| `polygon_epsilon_fraction` | Moderate | 0.0684 | 0.0713 | 50.0% | `0.008` (0.7435), `0.018` (0.6722) |
| `rectangularity_weight` | Moderate | 0.0542 | 0.0389 | 50.0% | `0.1` (0.7519), `0.25` (0.7130) |
| `bbox_padding_fraction` | Low | 0.0067 | 0.0189 | 33.3% | `0.015` (0.7462), `0` (0.7379), `0.005` (0.7273) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.7364) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.7364) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_iterations`, `close_kernel_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `rectangularity_weight` × `bbox_padding_fraction` | 0.0903 | 0.0361 | 10 |
| `minimum_contour_area_fraction` × `rectangularity_weight` | 0.0874 | 0.0191 | 10 |
| `polygon_epsilon_fraction` × `rectangularity_weight` | 0.0874 | 0.0191 | 10 |
| `minimum_contour_area_fraction` × `bbox_padding_fraction` | 0.0873 | 0.0189 | 10 |
| `polygon_epsilon_fraction` × `bbox_padding_fraction` | 0.0873 | 0.0189 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9651 | 0.9533 | 0.9734 | 0.0070 | 100.0% |
| 5 | 0.4903 | 0.4784 | 0.5178 | 0.0149 | 100.0% |
| 6 | 0.3357 | 0.0000 | 0.8763 | 0.4114 | 40.0% |
| 9 | 0.9413 | 0.9018 | 0.9585 | 0.0215 | 100.0% |
| 10 | 0.9494 | 0.9200 | 0.9593 | 0.0150 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="contour-components-contourcomponents-2"></a>
<details>
<summary><strong>Contour + Components (`contour_components`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-024118`
- Detector: `contour_components`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:41:18.435550+00:00`
- Finished: `2026-08-09T02:41:22.602170+00:00`
- Wall-clock elapsed: `4.2s`
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
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0 | 251 ms |

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

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0 | unknown | unknown |
| 2 | `6931e3aea38a` | `6931e3aea38a` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0 | 570 ms | 11.11% |
| 3 | `d6a2096d57a6` | `d6a2096d57a6` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0 | 802 ms | 22.22% |
| 4 | `4339c3f69581` | `4339c3f69581` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0 | 956 ms | 33.33% |
| 5 | `2cd41c1cfd70` | `2cd41c1cfd70` | 0.8617 | 0.7572 | 0.0655 | +0.0000 | 0 | 1.1s | 44.44% |

## Page Analysis

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
Search completed in **4.2s** wall-clock time.

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

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024118`
- Calibration schema: `1.1`
- Detector: `contour_components`
- Detector configuration: `hth-pipeline/config/detectors/contour_components.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `14818b491952`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8617`
- Worst Golden Set page (Min IoU): `0.7572`
- Page-to-page StdDev: `0.0655`
- Calibration evidence: `Medium`
- Dormant parameters: `component_close_fraction, component_dilate_fraction, component_merge_gap_fraction, component_minimum_area_fraction, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity, angle_weight, area_weight, close_iterations, close_kernel_fraction, component_bbox_padding_fraction, component_merge_area_ratio, component_minimum_area_px, component_minimum_bbox_area_fraction, component_minimum_selected_area_fraction, component_weight, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, minimum_component_score, rectangularity_weight`
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
| Search coverage | partial / adaptive |
| All possible parameter sets | 19684 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 1h 21m 54s |
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
| Exhaustive | 19684 | 100.0% | 1h 21m 57s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `component_close_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617), `0.004` (0.8617) |
| `component_dilate_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.015` (0.8617), `0.008` (0.8617) |
| `component_merge_gap_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.035` (0.8617), `0.02` (0.8617) |
| `component_minimum_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.0015` (0.8617), `0.0008` (0.8617) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.8617), `0.03` (0.8617) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.8617), `0.08` (0.8617) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.8617), `0.45` (0.8617) |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.15` (0.8617) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.25` (0.8617) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.8617) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.008` (0.8617) |
| `component_bbox_padding_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0` (0.8617) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`component_close_fraction`, `component_dilate_fraction`, `component_merge_gap_fraction`, `component_minimum_area_fraction`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `component_bbox_padding_fraction`, `component_merge_area_ratio`, `component_minimum_area_px`, `component_minimum_bbox_area_fraction`, `component_minimum_selected_area_fraction`, `component_weight`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `minimum_component_score`, `rectangularity_weight`.

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

## Run Information

### Build Provenance

- Run ID: `run-20260809-023811`
- Detector: `contour_grabcut`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:38:11.882978+00:00`
- Finished: `2026-08-09T02:42:16.684854+00:00`
- Wall-clock elapsed: `4m 5s`
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
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0 | 1m 4s |

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

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | unknown | unknown |
| 2 | `42fc63229bb3` | `42fc63229bb3` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 1m 50s | 22.22% |
| 3 | `cb5795c42bd3` | `cb5795c42bd3` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 1m 40s | 11.11% |
| 4 | `a3d42053b548` | `a3d42053b548` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 2m 28s | 33.33% |
| 5 | `0fb98d4d4330` | `0fb98d4d4330` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 2m 36s | 44.44% |

## Page Analysis

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
Search completed in **4m 5s** wall-clock time.

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

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-023811`
- Calibration schema: `1.1`
- Detector: `contour_grabcut`
- Detector configuration: `hth-pipeline/config/detectors/contour_grabcut.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `3eec8a03f1de`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Medium`
- Dormant parameters: `contour_epsilon_max_fraction, contour_minimum_area_fraction, contour_minimum_rectangularity, grabcut_border_fraction, grabcut_iterations, minimum_agreement_iou, agreement_weight, grabcut_weight, contour_weight, grabcut_erosion_kernel_fraction, require_grabcut`
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
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 4d 19h 38m 28s |
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
| Exhaustive | 6562 | 100.0% | 4d 19h 49m 4s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `contour_epsilon_max_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768) |
| `contour_minimum_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768) |
| `contour_minimum_rectangularity` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768) |
| `grabcut_border_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.01` (0.8768), `0.02` (0.8768) |
| `grabcut_iterations` | Dormant | 1.0000 | 0.0000 | 100.0% | `1` (0.8768), `3` (0.8768) |
| `minimum_agreement_iou` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.3` (0.8768) |
| `agreement_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) |
| `grabcut_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.15` (0.8768), `0.25` (0.8768), `0.35` (0.8768) |
| `contour_weight` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.45` (0.8768) |
| `grabcut_erosion_kernel_fraction` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.015` (0.8768) |
| `require_grabcut` | Dormant | 0.1000 | 0.0000 | 100.0% | `false` (0.8768) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_epsilon_max_fraction`, `contour_minimum_area_fraction`, `contour_minimum_rectangularity`, `grabcut_border_fraction`, `grabcut_iterations`, `minimum_agreement_iou`, `agreement_weight`, `grabcut_weight`, `contour_weight`, `grabcut_erosion_kernel_fraction`, `require_grabcut`.

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

## Run Information

### Build Provenance

- Run ID: `run-20260809-023948`
- Detector: `contour_projection`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:39:48.491136+00:00`
- Finished: `2026-08-09T02:40:08.683769+00:00`
- Wall-clock elapsed: `20.2s`
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
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0 | 2.8s |

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

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | unknown | unknown |
| 2 | `172304831b2e` | `172304831b2e` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 5.7s | 11.11% |
| 3 | `06593bf5afce` | `06593bf5afce` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 7s | 22.22% |
| 4 | `07cc1ff1c71c` | `07cc1ff1c71c` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 8.7s | 33.33% |
| 5 | `8d75cf39600c` | `8d75cf39600c` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 10.7s | 44.44% |

## Page Analysis

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
Search completed in **20.2s** wall-clock time.

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

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-023948`
- Calibration schema: `1.1`
- Detector: `contour_projection`
- Detector configuration: `hth-pipeline/config/detectors/contour_projection.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `0cd13eb1a471`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Medium`
- Dormant parameters: `epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity, projection_margin_fraction, projection_threshold_block_fraction, projection_threshold_c, minimum_projection_score, projection_weight, angle_weight, area_weight, close_iterations, close_kernel_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight`
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
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 5h 7m 30s |
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
| Exhaustive | 6562 | 100.0% | 5h 7m 58s | 1.0× |
| Non-dormant | 0 | 0.0% | 0 ms | unavailable |
| Low+ | 0 | 0.0% | 0 ms | unavailable |
| Moderate+ | 0 | 0.0% | 0 ms | unavailable |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `epsilon_max_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.04` (0.8768) |
| `minimum_contour_area_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.08` (0.8768), `0.12` (0.8768) |
| `minimum_rectangularity` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.45` (0.8768), `0.55` (0.8768) |
| `projection_margin_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.03` (0.8768), `0.06` (0.8768) |
| `projection_threshold_block_fraction` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.05` (0.8768), `0.08` (0.8768) |
| `projection_threshold_c` | Dormant | 1.0000 | 0.0000 | 100.0% | `5` (0.8768), `9` (0.8768) |
| `minimum_projection_score` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.05` (0.8768), `0.08` (0.8768), `0.15` (0.8768) |
| `projection_weight` | Dormant | 1.0000 | 0.0000 | 100.0% | `0.2` (0.8768), `0.3` (0.8768), `0.4` (0.8768) |
| `angle_weight` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.2` (0.8768) |
| `area_weight` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.25` (0.8768) |
| `close_iterations` | Dormant | 0.1000 | 0.0000 | 100.0% | `1` (0.8768) |
| `close_kernel_fraction` | Dormant | 0.1000 | 0.0000 | 100.0% | `0.008` (0.8768) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `projection_margin_fraction`, `projection_threshold_block_fraction`, `projection_threshold_c`, `minimum_projection_score`, `projection_weight`, `angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`.

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

<a id="contour-quadrilateral-contourquad-2"></a>
<details>
<summary><strong>Contour Quadrilateral (`contour_quad`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-023843`
- Detector: `contour_quad`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:38:43.305822+00:00`
- Finished: `2026-08-09T02:39:22.416829+00:00`
- Wall-clock elapsed: `39.1s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1062882`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0 | 1.2s |

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
| Winner changes | 0 |
| Baseline surpassed | no |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | unknown | unknown |
| 2 | `34f9c8482c2a` | `34f9c8482c2a` | 0.7045 | 0.0000 | 0.3597 | -0.1724 | 1 | 1.8s | 22.22% |
| 3 | `52a859d3db22` | `52a859d3db22` | 0.7045 | 0.0000 | 0.3597 | -0.1724 | 1 | 2.5s | 55.56% |
| 4 | `4d07d3594663` | `4d07d3594663` | 0.7045 | 0.0000 | 0.3597 | -0.1724 | 1 | 3.2s | 77.78% |
| 5 | `adb14cea60cf` | `adb14cea60cf` | 0.7045 | 0.0000 | 0.3597 | -0.1724 | 1 | 3.5s | 100.00% |

## Page Analysis

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
Search completed in **39.1s** wall-clock time.

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

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-023843`
- Calibration schema: `1.1`
- Detector: `contour_quad`
- Detector configuration: `hth-pipeline/config/detectors/contour_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `bea942a4969a`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 9 of 10 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1062882 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.0% |
| Est. serial runtime for full parameter set evaluation* | 14d 21h 16m 44s |
| Fully successful parameter sets | 1 (10.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.5632 |
| Avg IoU StdDev | 0.1005 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1062882 | 100.0% | 14d 21h 16m 56s | 1.0× |
| Non-dormant | 12288 | 1.2% | 4h 7m 50s | 86.5× |
| Low+ | 12288 | 1.2% | 4h 7m 50s | 86.5× |
| Moderate+ | 12288 | 1.2% | 4h 7m 50s | 86.5× |
| Important+ | 2048 | 0.2% | 41m 18s | 519.0× |
| Critical | 2048 | 0.2% | 41m 18s | 519.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `merge_fragmented_contours` | Critical | 0.7646 | 0.1757 | 50.0% | `true` (0.7389), `false` (0.5632) |
| `angle_weight` | Critical | 0.5609 | 0.2508 | 50.0% | `0.2` (0.8768), `0.1` (0.6260) |
| `area_weight` | Critical | 0.5609 | 0.2508 | 50.0% | `0.35` (0.8768), `0.25` (0.6260) |
| `close_iterations` | Critical | 0.5609 | 0.2508 | 50.0% | `1` (0.8768), `0` (0.6260) |
| `close_kernel_fraction` | Critical | 0.5609 | 0.2508 | 50.0% | `0.008` (0.8768), `0` (0.6260) |
| `epsilon_max_fraction` | Critical | 0.5609 | 0.2508 | 50.0% | `0.04` (0.8768), `0.025` (0.6260) |
| `epsilon_min_fraction` | Critical | 0.5609 | 0.2508 | 50.0% | `0.008` (0.8768), `0.004` (0.6260) |
| `epsilon_steps` | Critical | 0.5609 | 0.2508 | 50.0% | `9` (0.8768), `5` (0.6260) |
| `minimum_contour_area_fraction` | Critical | 0.5609 | 0.2508 | 50.0% | `0.12` (0.8768), `0.06` (0.6260) |
| `minimum_rectangularity` | Critical | 0.5609 | 0.2508 | 50.0% | `0.55` (0.8768), `0.45` (0.6260) |
| `rectangularity_weight` | Critical | 0.5609 | 0.2508 | 50.0% | `0.3` (0.8768), `0.2` (0.6260) |
| `edge_support_weight` | Moderate | 0.0441 | 0.0431 | 50.0% | `0.15` (0.6769), `0.1` (0.6338) |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `merge_fragmented_contours` × `angle_weight` | 1.0000 | 0.2354 | 10 |
| `merge_fragmented_contours` × `area_weight` | 1.0000 | 0.2354 | 10 |
| `merge_fragmented_contours` × `close_iterations` | 1.0000 | 0.2354 | 10 |
| `merge_fragmented_contours` × `close_kernel_fraction` | 1.0000 | 0.2354 | 10 |
| `merge_fragmented_contours` × `epsilon_max_fraction` | 1.0000 | 0.2354 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8806 | 0.8542 | 0.9069 | 0.0263 | 100.0% |
| 5 | 0.0862 | 0.0000 | 0.8618 | 0.2585 | 10.0% |
| 6 | 0.3795 | 0.0000 | 0.7589 | 0.3795 | 50.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.9454 | 0.9454 | 0.9454 | 0.0000 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="cross-edge-contour-crossedgecontour-2"></a>
<details>
<summary><strong>Cross-Edge Contour (`cross_edge_contour`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-024044`
- Detector: `cross_edge_contour`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:40:44.800072+00:00`
- Finished: `2026-08-09T02:40:56.910568+00:00`
- Wall-clock elapsed: `12.1s`
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
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0 | 1.7s |

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

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | unknown | unknown |
| 2 | `0bd97323ddd6` | `0bd97323ddd6` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 3.8s | 22.22% |
| 3 | `5417f7a84576` | `5417f7a84576` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 3.5s | 11.11% |
| 4 | `491385b9c30f` | `491385b9c30f` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 5.5s | 44.44% |
| 5 | `5e7bbad85e3f` | `5e7bbad85e3f` | 0.5527 | 0.0000 | 0.4528 | -0.3241 | 2 | 5.3s | 33.33% |

## Page Analysis

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
Search completed in **12.1s** wall-clock time.

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

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024044`
- Calibration schema: `1.1`
- Detector: `cross_edge_contour`
- Detector configuration: `hth-pipeline/config/detectors/cross_edge_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `a5450e58ec9e`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Low`
- Dormant parameters: `contour_weight, polarity_weight`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 2 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
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
| Est. serial runtime for full parameter set evaluation* | 3h 34s |
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
| Exhaustive | 6562 | 100.0% | 3h 50s | 1.0× |
| Non-dormant | 768 | 11.7% | 21m 10s | 8.5× |
| Low+ | 768 | 11.7% | 21m 10s | 8.5× |
| Moderate+ | 256 | 3.9% | 7m 3s | 25.6× |
| Important+ | 256 | 3.9% | 7m 3s | 25.6× |
| Critical | 4 | 0.1% | 6.6s | 1640.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_polarity_consistency` | Critical | 1.0000 | 0.4950 | 50.0% | `0.5` (0.8768), `0.55` (0.8768), `0.65` (0.5527) |
| `epsilon_max_fraction` | Important | 0.1503 | 0.2730 | 100.0% | `0.04` (0.8768), `0.03` (0.6038) |
| `minimum_contour_area_fraction` | Important | 0.1503 | 0.2730 | 100.0% | `0.12` (0.8768), `0.08` (0.6038) |
| `minimum_cross_edge_contrast` | Important | 0.1503 | 0.2730 | 100.0% | `0.045` (0.8768), `0.02` (0.6038) |
| `minimum_rectangularity` | Important | 0.1503 | 0.2730 | 100.0% | `0.55` (0.8768), `0.45` (0.6038) |
| `sample_offset_fraction` | Important | 0.1503 | 0.2730 | 100.0% | `0.008` (0.8768), `0.004` (0.6038) |
| `samples_per_edge` | Important | 0.1503 | 0.2730 | 100.0% | `48` (0.8768), `24` (0.6038) |
| `contour_weight` | Dormant | 0.1353 | 0.0000 | 100.0% | `0.45` (0.8768) |
| `polarity_weight` | Dormant | 0.1353 | 0.0000 | 100.0% | `0.15` (0.8768) |
| `contrast_weight` | Low | 0.0251 | 0.0683 | 100.0% | `0.4` (0.6720), `0.3` (0.6038), `0.5` (0.6038) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_weight`, `polarity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

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

<a id="edge-supported-contour-edgecontour-2"></a>
<details>
<summary><strong>Edge-Supported Contour (`edge_contour`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-024059`
- Detector: `edge_contour`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:40:59.513187+00:00`
- Finished: `2026-08-09T02:41:07.383197+00:00`
- Wall-clock elapsed: `7.9s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `13123`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.08%`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | 0 | 1s |
| Baseline | `cc91b22426bb` | `baseline` | 0.5392 | 0.0000 | 0.4417 | 2 | 1.7s |

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

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `4e5bc37a649a` | `4e5bc37a649a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 2.7s | 11.11% |
| 2 | `3f9b315b2a2d` | `3f9b315b2a2d` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 2.8s | 22.22% |
| 3 | `06aecf5b236a` | `06aecf5b236a` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0 | 3.5s | 33.33% |
| 4 | `cc91b22426bb` | `baseline` | 0.5392 | 0.0000 | 0.4417 | -0.3377 | 2 | unknown | unknown |
| 5 | `466c3d5add05` | `466c3d5add05` | 0.3651 | 0.0000 | 0.4483 | -0.5117 | 3 | 3.7s | 44.44% |

## Page Analysis

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
| 1 (final) | `4e5bc37a649a` | 2.7s | 11.11% |

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
- Regressed pages (Δ IoU < -0.0010): `0`

No problem pages were identified.

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024059`
- Calibration schema: `1.1`
- Detector: `edge_contour`
- Detector configuration: `hth-pipeline/config/detectors/edge_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `4e5bc37a649a`
- Recommended parameter short name: `4e5bc37a649a`
- Best observed Avg IoU: `0.8768`
- Worst Golden Set page (Min IoU): `0.7589`
- Page-to-page StdDev: `0.0734`
- Calibration evidence: `Low`
- Dormant parameters: `angle_weight, area_weight, close_iterations, close_kernel_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight, edge_support_weight`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 9 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 7 of 10 parameter configurations.
- Avg IoU varies widely across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 13123 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 3h 41m 50s |
| Fully successful parameter sets | 3 (30.0%) |
| Best Avg IoU | 0.8768 |
| Minimum Avg IoU | 0.1928 |
| Avg IoU StdDev | 0.2762 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 2.7s (11% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (30.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (30.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13123 | 100.0% | 3h 42m | 1.0× |
| Non-dormant | 384 | 2.9% | 6m 30s | 34.2× |
| Low+ | 384 | 2.9% | 6m 30s | 34.2× |
| Moderate+ | 3 | 0.0% | 3s | 4374.3× |
| Important+ | 3 | 0.0% | 3s | 4374.3× |
| Critical | 3 | 0.0% | 3s | 4374.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_edge_support` | Critical | 0.9702 | 0.6841 | 33.3% | `0.05` (0.8768), `0.12` (0.4086), `0.2` (0.1928) |
| `edge_support_dilation_fraction` | Low | 0.0044 | 0.0609 | 50.0% | `0.006` (0.5392), `0.003` (0.4782) |
| `epsilon_max_fraction` | Low | 0.0044 | 0.0609 | 50.0% | `0.04` (0.5392), `0.03` (0.4782) |
| `lsd_refine_mode` | Low | 0.0044 | 0.0609 | 50.0% | `std` (0.5392), `none` (0.4782) |
| `lsd_scale` | Low | 0.0044 | 0.0609 | 50.0% | `0.8` (0.5392), `0.6` (0.4782) |
| `minimum_contour_area_fraction` | Low | 0.0044 | 0.0609 | 50.0% | `0.12` (0.5392), `0.08` (0.4782) |
| `minimum_rectangularity` | Low | 0.0044 | 0.0609 | 50.0% | `0.55` (0.5392), `0.45` (0.4782) |
| `minimum_segment_length_fraction` | Low | 0.0044 | 0.0609 | 50.0% | `0.06` (0.5392), `0.03` (0.4782) |
| `angle_weight` | Dormant | 0.0039 | 0.0000 | 0.0% | `0.2` (0.5392) |
| `area_weight` | Dormant | 0.0039 | 0.0000 | 0.0% | `0.25` (0.5392) |
| `close_iterations` | Dormant | 0.0039 | 0.0000 | 0.0% | `1` (0.5392) |
| `close_kernel_fraction` | Dormant | 0.0039 | 0.0000 | 0.0% | `0.008` (0.5392) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`, `edge_support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_edge_support` × `edge_support_dilation_fraction` | 1.0000 | 0.0298 | 10 |
| `minimum_edge_support` × `epsilon_max_fraction` | 1.0000 | 0.0298 | 10 |
| `minimum_edge_support` × `lsd_refine_mode` | 1.0000 | 0.0298 | 10 |
| `minimum_edge_support` × `lsd_scale` | 1.0000 | 0.0298 | 10 |
| `minimum_edge_support` × `minimum_contour_area_fraction` | 1.0000 | 0.0298 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.2563 | 0.0000 | 0.8542 | 0.3915 | 30.0% |
| 5 | 0.6032 | 0.0000 | 0.8618 | 0.3949 | 70.0% |
| 6 | 0.2277 | 0.0000 | 0.7589 | 0.3478 | 30.0% |
| 9 | 0.9638 | 0.9638 | 0.9638 | 0.0000 | 100.0% |
| 10 | 0.3707 | 0.0000 | 0.9454 | 0.4544 | 40.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-segmentation-grabcut-2"></a>
<details>
<summary><strong>GrabCut Segmentation (`grabcut`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-023811`
- Detector: `grabcut`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:38:11.882391+00:00`
- Finished: `2026-08-09T02:44:15.875026+00:00`
- Wall-clock elapsed: `6m 4s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `13122`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.08%`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0 | 58.7s |

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
| Winner changes | 0 |
| Baseline surpassed | no |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | +0.0000 | 0 | unknown | unknown |
| 2 | `71c8fb00da00` | `71c8fb00da00` | 0.7443 | 0.3729 | 0.2583 | -0.0688 | 0 | 4m 46s | 55.56% |
| 3 | `c4569ce5ec31` | `c4569ce5ec31` | 0.7443 | 0.3729 | 0.2583 | -0.0688 | 0 | 4m 49s | 66.67% |
| 4 | `f5a2acd172d1` | `f5a2acd172d1` | 0.7409 | 0.3560 | 0.2633 | -0.0721 | 0 | 5m 28s | 77.78% |
| 5 | `5a4694bf2661` | `5a4694bf2661` | 0.7409 | 0.3560 | 0.2633 | -0.0721 | 0 | 5m 32s | 88.89% |

## Page Analysis

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
Search completed in **6m 4s** wall-clock time.

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

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-023811`
- Calibration schema: `1.1`
- Detector: `grabcut`
- Detector configuration: `hth-pipeline/config/detectors/grabcut.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `018d128420cb`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8130`
- Worst Golden Set page (Min IoU): `0.5532`
- Page-to-page StdDev: `0.1692`
- Calibration evidence: `Medium`
- Dormant parameters: `close_iterations`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

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
| All possible parameter sets | 13122 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.1% |
| Est. serial runtime for full parameter set evaluation* | 8d 21h 56m 30s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.8130 |
| Minimum Avg IoU | 0.7091 |
| Avg IoU StdDev | 0.0275 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13122 | 100.0% | 8d 22h 6m 17s | 1.0× |
| Non-dormant | 576 | 4.4% | 9h 23m 54s | 22.8× |
| Low+ | 576 | 4.4% | 9h 23m 54s | 22.8× |
| Moderate+ | 576 | 4.4% | 9h 23m 54s | 22.8× |
| Important+ | 576 | 4.4% | 9h 23m 54s | 22.8× |
| Critical | 192 | 1.5% | 3h 7m 58s | 68.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `border_fraction` | Critical | 0.7772 | 0.0809 | 50.0% | `0.02` (0.8130), `0.01` (0.7322) |
| `close_kernel_fraction` | Critical | 0.7772 | 0.0809 | 50.0% | `0.02` (0.8130), `0.01` (0.7322) |
| `erosion_iterations` | Critical | 0.7772 | 0.0809 | 50.0% | `1` (0.8130), `0` (0.7322) |
| `erosion_kernel_fraction` | Critical | 0.7772 | 0.0809 | 50.0% | `0.015` (0.8130), `0.0075` (0.7322) |
| `grabcut_iterations` | Critical | 0.7772 | 0.0809 | 50.0% | `3` (0.8130), `1` (0.7322) |
| `minimum_bbox_area_fraction` | Critical | 0.7772 | 0.0809 | 50.0% | `0.1` (0.8130), `0.07` (0.7322) |
| `polygon_epsilon_fraction` | Critical | 0.3445 | 0.0367 | 33.3% | `0.018` (0.7595), `0.01` (0.7320), `0.03` (0.7228) |
| `minimum_contour_area_fraction` | Important | 0.1706 | 0.0239 | 33.3% | `0.04` (0.7542), `0.02` (0.7317), `0.07` (0.7303) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 100.0% | `1` (0.7402) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`close_iterations`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9612 | 0.9568 | 0.9617 | 0.0015 | 100.0% |
| 5 | 0.3782 | 0.3516 | 0.5532 | 0.0588 | 100.0% |
| 6 | 0.4656 | 0.3305 | 0.6683 | 0.0922 | 100.0% |
| 9 | 0.9432 | 0.9422 | 0.9433 | 0.0003 | 100.0% |
| 10 | 0.9530 | 0.9447 | 0.9540 | 0.0028 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="grabcut-contour-grabcutcontour-2"></a>
<details>
<summary><strong>GrabCut + Contour (`grabcut_contour`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-023811`
- Detector: `grabcut_contour`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:38:11.882902+00:00`
- Finished: `2026-08-09T02:42:07.212580+00:00`
- Wall-clock elapsed: `3m 55s`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0 | 1m 1s |

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

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | +0.0000 | 0 | unknown | unknown |
| 2 | `2a39748afbe3` | `2a39748afbe3` | 0.8011 | 0.5492 | 0.1867 | -0.0119 | 0 | 2m 12s | 33.33% |
| 3 | `ea911909ef98` | `ea911909ef98` | 0.8011 | 0.5492 | 0.1867 | -0.0119 | 0 | 2m 13s | 44.44% |
| 4 | `47e727acc335` | `47e727acc335` | 0.8010 | 0.5486 | 0.1869 | -0.0120 | 0 | 2m 50s | 55.56% |
| 5 | `8a86732de560` | `8a86732de560` | 0.8010 | 0.5486 | 0.1869 | -0.0120 | 0 | 2m 50s | 66.67% |

## Page Analysis

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
Search completed in **3m 55s** wall-clock time.

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

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-023811`
- Calibration schema: `1.1`
- Detector: `grabcut_contour`
- Detector configuration: `hth-pipeline/config/detectors/grabcut_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `3817f226228a`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8130`
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
| Est. serial runtime for full parameter set evaluation* | 251d 9h 32m 25s |
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
| Exhaustive | 354295 | 100.0% | 251d 9h 42m 38s | 1.0× |
| Non-dormant | 6144 | 1.7% | 4d 8h 38m 1s | 57.7× |
| Low+ | 6144 | 1.7% | 4d 8h 38m 1s | 57.7× |
| Moderate+ | 6144 | 1.7% | 4d 8h 38m 1s | 57.7× |
| Important+ | 3072 | 0.9% | 2d 4h 19m | 115.3× |
| Critical | 512 | 0.1% | 8h 43m 10s | 692.0× |

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

## Run Information

### Build Provenance

- Run ID: `run-20260809-024142`
- Detector: `gradient_vote`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:41:42.806644+00:00`
- Finished: `2026-08-09T02:41:44.822876+00:00`
- Wall-clock elapsed: `2s`
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
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `5d83cf42b823` | `5d83cf42b823` | 0.9056 | 0.7501 | 0.0877 | 0 | 125 ms |
| Baseline | `5660d66df3d1` | `baseline` | 0.8882 | 0.5684 | 0.1603 | 0 | 72 ms |

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
| StdDev improvements | 1 |
| Total metric improvements | 3 |
| Parameter sets with improvements | 1 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `5d83cf42b823` | `5d83cf42b823` | 0.9056 | 0.7501 | 0.0877 | +0.0000 | 0 | 204 ms | 22.22% |
| 2 | `fa5996f46cde` | `fa5996f46cde` | 0.9056 | 0.7501 | 0.0877 | +0.0000 | 0 | 169 ms | 11.11% |
| 3 | `0c80a84a4f8f` | `0c80a84a4f8f` | 0.9056 | 0.7501 | 0.0877 | +0.0000 | 0 | 236 ms | 33.33% |
| 4 | `87273aef8c82` | `87273aef8c82` | 0.9056 | 0.7501 | 0.0877 | +0.0000 | 0 | 305 ms | 44.44% |
| 5 | `907844a59442` | `907844a59442` | 0.9056 | 0.7501 | 0.0877 | +0.0000 | 0 | 335 ms | 55.56% |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `5d83cf42b823` | 0.9613 | 0.8690 | -0.0923 | Regressed |
| 5 | `5d83cf42b823` | 0.5684 | 0.7501 | +0.1817 | Improved |
| 6 | `5d83cf42b823` | 0.9889 | 0.9889 | +0.0000 | Unchanged |
| 9 | `5d83cf42b823` | 0.9612 | 0.9601 | -0.0011 | Regressed |
| 10 | `5d83cf42b823` | 0.9611 | 0.9600 | -0.0010 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 (final) | `fa5996f46cde` | 169 ms | 11.11% |

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
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `3`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `5d83cf42b823` | 0.8690 | Regressed |
| 9 | `5d83cf42b823` | 0.9601 | Regressed |
| 10 | `5d83cf42b823` | 0.9600 | Regressed |

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024142`
- Calibration schema: `1.1`
- Detector: `gradient_vote`
- Detector configuration: `hth-pipeline/config/detectors/gradient_vote.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `5d83cf42b823`
- Recommended parameter short name: `5d83cf42b823`
- Best observed Avg IoU: `0.9056`
- Worst Golden Set page (Min IoU): `0.7501`
- Page-to-page StdDev: `0.0877`
- Calibration evidence: `Medium`
- Dormant parameters: `area_weight, minimum_area_fraction, rectangularity_weight`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The evaluated calibration landscape is flat: nearly all tested parameter sets are equivalent or near-equivalent.
- 3 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 13m 13s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9056 |
| Minimum Avg IoU | 0.8882 |
| Avg IoU StdDev | 0.0052 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 204 ms (22% of search) |
| Near-best coverage (basin; within 0.0010) | 9 (90.0%) |
| Equivalent-best configurations (within 0.0001) | 9 (90.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 13m 14s | 1.0× |
| Non-dormant | 576 | 8.8% | 1m 10s | 11.4× |
| Low+ | 576 | 8.8% | 1m 10s | 11.4× |
| Moderate+ | 576 | 8.8% | 1m 10s | 11.4× |
| Important+ | 576 | 8.8% | 1m 10s | 11.4× |
| Critical | 64 | 1.0% | 7.7s | 102.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `border_search_fraction` | Critical | 1.0000 | 0.0175 | 50.0% | `0.35` (0.9056), `0.42` (0.8882) |
| `central_band_fraction` | Critical | 1.0000 | 0.0175 | 50.0% | `0.7` (0.9056), `0.86` (0.8882) |
| `gaussian_sigma` | Critical | 1.0000 | 0.0175 | 50.0% | `0.8` (0.9056), `1.2` (0.8882) |
| `gradient_percentile` | Critical | 1.0000 | 0.0175 | 50.0% | `70` (0.9056), `82` (0.8882) |
| `minimum_vote_support` | Critical | 1.0000 | 0.0175 | 50.0% | `0.08` (0.9056), `0.16` (0.8882) |
| `vote_smooth_fraction` | Critical | 1.0000 | 0.0175 | 50.0% | `0.006` (0.9056), `0.012` (0.8882) |
| `area_weight` | Dormant | 0.9000 | 0.0000 | 0.0% | `0.25` (0.8882) |
| `minimum_area_fraction` | Dormant | 0.9000 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `rectangularity_weight` | Dormant | 0.9000 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `minimum_span_fraction` | Important | 0.1667 | 0.0044 | 100.0% | `0.35` (0.9056), `0.55` (0.9056), `0.45` (0.9013) |
| `support_weight` | Important | 0.1667 | 0.0044 | 100.0% | `0.45` (0.9056), `0.65` (0.9056), `0.55` (0.9013) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `minimum_area_fraction`, `rectangularity_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8782 | 0.8690 | 0.9613 | 0.0277 | 100.0% |
| 5 | 0.7319 | 0.5684 | 0.7501 | 0.0545 | 100.0% |
| 6 | 0.9889 | 0.9889 | 0.9889 | 0.0000 | 100.0% |
| 9 | 0.9602 | 0.9601 | 0.9612 | 0.0003 | 100.0% |
| 10 | 0.9601 | 0.9600 | 0.9611 | 0.0003 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="hough-line-borders-hough-2"></a>
<details>
<summary><strong>Hough Line Borders (`hough`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-023811`
- Detector: `hough`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:38:11.882464+00:00`
- Finished: `2026-08-09T02:38:42.192231+00:00`
- Wall-clock elapsed: `30.3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2188`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.46%`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `d2ef0aec6694` | `d2ef0aec6694` | 0.5661 | 0.0000 | 0.3407 | 1 | 6.7s |
| Baseline | `7078053f309d` | `baseline` | 0.4784 | 0.0000 | 0.2851 | 1 | 4.3s |

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
| Avg IoU improvements | 3 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 1 |
| Total metric improvements | 4 |
| Parameter sets with improvements | 4 |
| Winner changes | 3 |
| Baseline surpassed | yes |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `d2ef0aec6694` | `d2ef0aec6694` | 0.5661 | 0.0000 | 0.3407 | +0.0000 | 1 | 16.3s | 44.44% |
| 2 | `217ec1728985` | `217ec1728985` | 0.5556 | 0.0000 | 0.3391 | -0.0105 | 1 | 10.5s | 22.22% |
| 3 | `90e4276c2a1d` | `90e4276c2a1d` | 0.5495 | 0.0000 | 0.3375 | -0.0166 | 1 | 9.6s | 11.11% |
| 4 | `cd10502d9095` | `cd10502d9095` | 0.5030 | 0.0000 | 0.3046 | -0.0631 | 1 | 23s | 66.67% |
| 5 | `96052fb049b9` | `96052fb049b9` | 0.4882 | 0.0000 | 0.3000 | -0.0780 | 1 | 18.7s | 55.56% |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `d2ef0aec6694` | 0.6261 | 0.8453 | +0.2192 | Improved |
| 5 | `d2ef0aec6694` | 0.3071 | 0.3411 | +0.0340 | Improved |
| 6 | `d2ef0aec6694` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `d2ef0aec6694` | 0.7370 | 0.8136 | +0.0767 | Improved |
| 10 | `d2ef0aec6694` | 0.7221 | 0.8305 | +0.1085 | Improved |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `90e4276c2a1d` | 9.6s | 11.11% |
| 2 | `217ec1728985` | 10.5s | 22.22% |
| 3 (final) | `d2ef0aec6694` | 16.3s | 44.44% |

Total winner changes: **3**.
Search completed in **30.3s** wall-clock time.

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
- No polygon found: `1`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `1`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 5 | `d2ef0aec6694` | 0.3411 | Poor match |
| 6 | `d2ef0aec6694` | 0.0000 | No polygon found |

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-023811`
- Calibration schema: `1.1`
- Detector: `hough`
- Detector configuration: `hth-pipeline/config/detectors/hough.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `d2ef0aec6694`
- Recommended parameter short name: `d2ef0aec6694`
- Best observed Avg IoU: `0.5661`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3407`
- Calibration evidence: `Low`
- Dormant parameters: `minimum_bbox_area_fraction`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 1 of 8 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2188 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 4h 2m 37s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.5661 |
| Minimum Avg IoU | 0.3084 |
| Avg IoU StdDev | 0.0963 |
| Winner stabilized after | 4 parameter sets |
| Winner stabilized | 16.3s (44% of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2188 | 100.0% | 4h 3m 44s | 1.0× |
| Non-dormant | 288 | 13.2% | 32m 5s | 7.6× |
| Low+ | 288 | 13.2% | 32m 5s | 7.6× |
| Moderate+ | 3 | 0.1% | 20.1s | 729.3× |
| Important+ | 3 | 0.1% | 20.1s | 729.3× |
| Critical | 3 | 0.1% | 20.1s | 729.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `outer_percentile` | Critical | 0.9920 | 0.2393 | 33.3% | `5` (0.5571), `10` (0.4874), `20` (0.3177) |
| `axis_angle_tolerance_degrees` | Low | 0.0053 | 0.0234 | 50.0% | `22` (0.4784), `12` (0.4551) |
| `canny_low_threshold` | Low | 0.0053 | 0.0234 | 50.0% | `40` (0.4784), `25` (0.4551) |
| `hough_threshold_fraction` | Low | 0.0053 | 0.0234 | 50.0% | `0.055` (0.4784), `0.035` (0.4551) |
| `maximum_gap_fraction` | Low | 0.0053 | 0.0234 | 50.0% | `0.055` (0.4784), `0.025` (0.4551) |
| `minimum_length_fraction` | Low | 0.0053 | 0.0234 | 50.0% | `0.2` (0.4784), `0.12` (0.4551) |
| `minimum_bbox_area_fraction` | Dormant | 0.0048 | 0.0000 | 0.0% | `0.1` (0.4784) |
| `bbox_padding_fraction` | Low | 0.0035 | 0.0128 | 33.3% | `0.015` (0.4660), `0` (0.4541), `0.005` (0.4532) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_percentile` × `axis_angle_tolerance_degrees` | 0.9932 | 0.0012 | 10 |
| `outer_percentile` × `canny_low_threshold` | 0.9932 | 0.0012 | 10 |
| `outer_percentile` × `hough_threshold_fraction` | 0.9932 | 0.0012 | 10 |
| `outer_percentile` × `maximum_gap_fraction` | 0.9932 | 0.0012 | 10 |
| `outer_percentile` × `minimum_length_fraction` | 0.9932 | 0.0012 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.6600 | 0.4658 | 0.8453 | 0.1360 | 100.0% |
| 5 | 0.2116 | 0.0000 | 0.3411 | 0.1399 | 70.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.6923 | 0.4958 | 0.8136 | 0.1221 | 100.0% |
| 10 | 0.7231 | 0.5805 | 0.8305 | 0.0921 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="line-segment-detector-lsd-2"></a>
<details>
<summary><strong>Line Segment Detector (`lsd`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-024109`
- Detector: `lsd`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:41:09.644867+00:00`
- Finished: `2026-08-09T02:41:16.122850+00:00`
- Wall-clock elapsed: `6.5s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `2187`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.46%`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `7b8b1aaee481` | `7b8b1aaee481` | 0.7368 | 0.0000 | 0.3714 | 1 | 905 ms |
| Baseline | `b2df04f4e947` | `baseline` | 0.5414 | 0.0000 | 0.4436 | 2 | 910 ms |

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
| Avg IoU improvements | 2 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 2 |
| Total metric improvements | 4 |
| Parameter sets with improvements | 3 |
| Winner changes | 2 |
| Baseline surpassed | yes |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `7b8b1aaee481` | `7b8b1aaee481` | 0.7368 | 0.0000 | 0.3714 | +0.0000 | 1 | 1.8s | 22.22% |
| 2 | `19a4857c76d8` | `19a4857c76d8` | 0.7368 | 0.0000 | 0.3714 | +0.0000 | 1 | 3.2s | 55.56% |
| 3 | `1b2cebd68deb` | `1b2cebd68deb` | 0.7368 | 0.0000 | 0.3714 | +0.0000 | 1 | 4.4s | 88.89% |
| 4 | `0bd9251e7f32` | `0bd9251e7f32` | 0.7340 | 0.0000 | 0.3695 | -0.0028 | 1 | 1.7s | 11.11% |
| 5 | `2cf82997c714` | `2cf82997c714` | 0.7340 | 0.0000 | 0.3695 | -0.0028 | 1 | 2.6s | 44.44% |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `7b8b1aaee481` | 0.8955 | 0.9095 | +0.0141 | Improved |
| 5 | `7b8b1aaee481` | 0.0000 | 0.9782 | +0.9782 | Recovered |
| 6 | `7b8b1aaee481` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `7b8b1aaee481` | 0.8475 | 0.8409 | -0.0066 | Regressed |
| 10 | `7b8b1aaee481` | 0.9641 | 0.9554 | -0.0086 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 | `0bd9251e7f32` | 1.7s | 11.11% |
| 2 (final) | `7b8b1aaee481` | 1.8s | 22.22% |

Total winner changes: **2**.
Search completed in **6.5s** wall-clock time.

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
| 6 | `7b8b1aaee481` | 0.0000 | No polygon found |
| 9 | `7b8b1aaee481` | 0.8409 | Regressed |
| 10 | `7b8b1aaee481` | 0.9554 | Regressed |

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024109`
- Calibration schema: `1.1`
- Detector: `lsd`
- Detector configuration: `hth-pipeline/config/detectors/lsd.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `7b8b1aaee481`
- Recommended parameter short name: `7b8b1aaee481`
- Best observed Avg IoU: `0.7368`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3714`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 2187 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.5% |
| Est. serial runtime for full parameter set evaluation* | 32m 43s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.7368 |
| Minimum Avg IoU | 0.5414 |
| Avg IoU StdDev | 0.0570 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 1.8s (22% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (30.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (30.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2187 | 100.0% | 32m 52s | 1.0× |
| Non-dormant | 288 | 13.2% | 4m 20s | 7.6× |
| Low+ | 288 | 13.2% | 4m 20s | 7.6× |
| Moderate+ | 288 | 13.2% | 4m 20s | 7.6× |
| Important+ | 288 | 13.2% | 4m 20s | 7.6× |
| Critical | 32 | 1.5% | 28.8s | 68.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `axis_angle_tolerance_degrees` | Critical | 0.9797 | 0.1880 | 50.0% | `10` (0.7294), `18` (0.5414) |
| `minimum_length_fraction` | Critical | 0.9797 | 0.1880 | 50.0% | `0.08` (0.7294), `0.14` (0.5414) |
| `outer_percentile` | Critical | 0.9797 | 0.1880 | 50.0% | `5` (0.7294), `10` (0.5414) |
| `refine_mode` | Critical | 0.9797 | 0.1880 | 50.0% | `none` (0.7294), `std` (0.5414) |
| `scale` | Critical | 0.9797 | 0.1880 | 50.0% | `0.6` (0.7294), `0.8` (0.5414) |
| `minimum_bbox_area_fraction` | Important | 0.1633 | 0.0470 | 100.0% | `0.08` (0.7294), `0.15` (0.7294), `0.1` (0.6824) |
| `bbox_padding_fraction` | Important | 0.1433 | 0.0510 | 33.3% | `0.005` (0.7368), `0.015` (0.7174), `0` (0.6858) |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8973 | 0.8828 | 0.9095 | 0.0105 | 100.0% |
| 5 | 0.8746 | 0.0000 | 0.9782 | 0.2916 | 90.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.8338 | 0.8091 | 0.8475 | 0.0164 | 100.0% |
| 10 | 0.9474 | 0.9209 | 0.9641 | 0.0175 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="radial-edge-search-radialedge-2"></a>
<details>
<summary><strong>Radial Edge Search (`radial_edge`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-024132`
- Detector: `radial_edge`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:41:32.898797+00:00`
- Finished: `2026-08-09T02:41:35.405476+00:00`
- Wall-clock elapsed: `2.5s`
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
- `raw/results.csv` — missing
- `logs/runner-performance.jsonl` — missing
- `reports/summary.json` — present
- `reports/winner-pages.json` — present
- `reports/calibration-intelligence.json` — present
- `reports/rankings.csv` — missing
- `reports/top20.csv` — missing

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | 0 | 151 ms |

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
| Winner changes | 0 |
| Baseline surpassed | no |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | +0.0000 | 0 | unknown | unknown |
| 2 | `fb02c627c7f4` | `fb02c627c7f4` | 0.8156 | 0.7503 | 0.0501 | -0.1347 | 0 | 295 ms | 11.11% |
| 3 | `f333f6e733a0` | `f333f6e733a0` | 0.8156 | 0.7503 | 0.0501 | -0.1347 | 0 | 630 ms | 44.44% |
| 4 | `e60457948fd1` | `e60457948fd1` | 0.8156 | 0.7503 | 0.0501 | -0.1347 | 0 | 422 ms | 22.22% |
| 5 | `b84fd1296870` | `b84fd1296870` | 0.8156 | 0.7503 | 0.0501 | -0.1347 | 0 | 540 ms | 33.33% |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `baseline` | 0.9466 | 0.9466 | +0.0000 | Unchanged |
| 5 | `baseline` | 0.9742 | 0.9742 | +0.0000 | Unchanged |
| 6 | `baseline` | 0.9384 | 0.9384 | +0.0000 | Unchanged |
| 9 | `baseline` | 0.9340 | 0.9340 | +0.0000 | Unchanged |
| 10 | `baseline` | 0.9582 | 0.9582 | +0.0000 | Unchanged |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| — | no history | no history | no history |

Total winner changes: **0**.
Search completed in **2.5s** wall-clock time.

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

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024132`
- Calibration schema: `1.1`
- Detector: `radial_edge`
- Detector configuration: `hth-pipeline/config/detectors/radial_edge.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `d593fad7aeea`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.9503`
- Worst Golden Set page (Min IoU): `0.9340`
- Page-to-page StdDev: `0.0145`
- Calibration evidence: `Medium`
- Dormant parameters: `area_weight, maximum_area_fraction, minimum_area_fraction`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 3 of 11 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Most parameter sets evaluated every Golden Set page successfully.

#### Evidence of ROI

Some calibration ROI may remain, but it should be justified by page-level failures or a plausible untested parameter region.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 6562 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.2% |
| Est. serial runtime for full parameter set evaluation* | 16m 22s |
| Fully successful parameter sets | 10 (100.0%) |
| Best Avg IoU | 0.9503 |
| Minimum Avg IoU | 0.8156 |
| Avg IoU StdDev | 0.0404 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 1 (10.0%) |
| Equivalent-best configurations (within 0.0001) | 1 (10.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 16m 24s | 1.0× |
| Non-dormant | 576 | 8.8% | 1m 26s | 11.4× |
| Low+ | 576 | 8.8% | 1m 26s | 11.4× |
| Moderate+ | 576 | 8.8% | 1m 26s | 11.4× |
| Important+ | 576 | 8.8% | 1m 26s | 11.4× |
| Critical | 64 | 1.0% | 9.6s | 102.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, high fully-successful-set rate, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `gaussian_sigma` | Critical | 1.0000 | 0.1347 | 50.0% | `1.2` (0.9503), `0.8` (0.8156) |
| `gradient_percentile` | Critical | 1.0000 | 0.1347 | 50.0% | `82` (0.9503), `70` (0.8156) |
| `maximum_radius_fraction` | Critical | 1.0000 | 0.1347 | 50.0% | `0.72` (0.9503), `0.62` (0.8156) |
| `minimum_radius_fraction` | Critical | 1.0000 | 0.1347 | 50.0% | `0.18` (0.9503), `0.12` (0.8156) |
| `minimum_ray_support` | Critical | 1.0000 | 0.1347 | 50.0% | `0.45` (0.9503), `0.3` (0.8156) |
| `ray_count` | Critical | 1.0000 | 0.1347 | 50.0% | `96` (0.9503), `64` (0.8156) |
| `area_weight` | Dormant | 0.9000 | 0.0000 | 100.0% | `0.35` (0.9503) |
| `maximum_area_fraction` | Dormant | 0.9000 | 0.0000 | 100.0% | `0.98` (0.9503) |
| `minimum_area_fraction` | Dormant | 0.9000 | 0.0000 | 100.0% | `0.18` (0.9503) |
| `rectangularity_weight` | Important | 0.1667 | 0.0337 | 33.3% | `0.2` (0.8493), `0.1` (0.8156), `0.3` (0.8156) |
| `support_weight` | Important | 0.1667 | 0.0337 | 33.3% | `0.45` (0.8493), `0.35` (0.8156), `0.55` (0.8156) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `maximum_area_fraction`, `minimum_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.8080 | 0.7926 | 0.9466 | 0.0462 | 100.0% |
| 5 | 0.9106 | 0.9035 | 0.9742 | 0.0212 | 100.0% |
| 6 | 0.7691 | 0.7503 | 0.9384 | 0.0565 | 100.0% |
| 9 | 0.8311 | 0.8197 | 0.9340 | 0.0343 | 100.0% |
| 10 | 0.8265 | 0.8118 | 0.9582 | 0.0439 | 100.0% |

</details>


[↑ Back to Navigation](#table-of-contents)

<a id="ransac-border-fit-ransac-2"></a>
<details>
<summary><strong>RANSAC Border Fit (`ransac`)</strong></summary>

**Status:** complete

## Run Information

### Build Provenance

- Run ID: `run-20260809-024126`
- Detector: `ransac`
- Strategy: `exhaustive`
- Pipeline commit: `1ca02d6d575c`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-09T02:41:26.226975+00:00`
- Finished: `2026-08-09T02:41:30.566004+00:00`
- Wall-clock elapsed: `4.3s`
- Est. serial runtime: `unknown`
- Effective acceleration: `unknown`

### Golden Set

- Configuration: `hth-pipeline/config/golden_set.json`
- SHA-256: `135c0ff57687`
- Pages: `5`
- Ordinals: `1, 5, 6, 9, 10`

### Parameter Space

- All possible parameter sets: `1458`
- Parameter sets evaluated: `10`
- Evaluated sets (% of all possible parameter sets): `0.69%`
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

## Results

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|
| Winner | `55356b348cc7` | `55356b348cc7` | 0.6849 | 0.0000 | 0.3801 | 1 | 468 ms |
| Baseline | `7e367fe3bfd5` | `baseline` | 0.6831 | 0.0000 | 0.3806 | 1 | 174 ms |

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
| Avg IoU improvements | 1 |
| Minimum IoU improvements | 0 |
| StdDev improvements | 3 |
| Total metric improvements | 4 |
| Parameter sets with improvements | 3 |
| Winner changes | 1 |
| Baseline surpassed | yes |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | `55356b348cc7` | `55356b348cc7` | 0.6849 | 0.0000 | 0.3801 | +0.0000 | 1 | 647 ms | 11.11% |
| 2 | `2080a62a8e2c` | `2080a62a8e2c` | 0.6849 | 0.0000 | 0.3801 | +0.0000 | 1 | 1.5s | 44.44% |
| 3 | `0183c6040572` | `0183c6040572` | 0.6849 | 0.0000 | 0.3801 | +0.0000 | 1 | 2.9s | 88.89% |
| 4 | `7e367fe3bfd5` | `baseline` | 0.6831 | 0.0000 | 0.3806 | -0.0017 | 1 | unknown | unknown |
| 5 | `c00244a14f3f` | `c00244a14f3f` | 0.6831 | 0.0000 | 0.3742 | -0.0017 | 1 | 982 ms | 22.22% |

## Page Analysis

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `55356b348cc7` | 0.9665 | 0.9717 | +0.0052 | Improved |
| 5 | `55356b348cc7` | 0.5289 | 0.5367 | +0.0078 | Improved |
| 6 | `55356b348cc7` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `55356b348cc7` | 0.9550 | 0.9553 | +0.0003 | Unchanged |
| 10 | `55356b348cc7` | 0.9652 | 0.9606 | -0.0047 | Regressed |

#### Winner History

| Discovery Order | Parameter Set ID | Search Time | % Search |
|---:|---|---:|---:|
| 1 (final) | `55356b348cc7` | 647 ms | 11.11% |

Total winner changes: **1**.
Search completed in **4.3s** wall-clock time.

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
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 6 | `55356b348cc7` | 0.0000 | No polygon found |
| 10 | `55356b348cc7` | 0.9606 | Regressed |

## Calibration Intelligence

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260809-024126`
- Calibration schema: `1.1`
- Detector: `ransac`
- Detector configuration: `hth-pipeline/config/detectors/ransac.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `1ca02d6d575cbaec1f83a0892e7df118f3b692a8`
- Source commit: `192511f2a4a6ac5e5008068c905269677ce482a5`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `55356b348cc7`
- Recommended parameter short name: `55356b348cc7`
- Best observed Avg IoU: `0.6849`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3801`
- Calibration evidence: `Low`
- Dormant parameters: `none`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- No measured parameter was dormant in this calibration sample.
- Detector failed on at least one Golden Set page for 10 of 10 parameter configurations.
- Avg IoU varies very little across the tested parameter sets.

#### Evidence of ROI

Additional tuning may improve reliability, but detector-level ROI should be weighed against stronger alternatives before expanding the search.

#### Calibration Landscape

| Measure | Value |
|---|---:|
| Search coverage | partial / adaptive |
| All possible parameter sets | 1458 |
| Parameter sets evaluated | 10 |
| Evaluated sets (% of all possible parameter sets) | 0.7% |
| Est. serial runtime for full parameter set evaluation* | 11m 16s |
| Fully successful parameter sets | 0 (0.0%) |
| Best Avg IoU | 0.6849 |
| Minimum Avg IoU | 0.6732 |
| Avg IoU StdDev | 0.0049 |
| Winner stabilized after | 1 parameter set |
| Winner stabilized | 647 ms (11% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (30.0%) |
| Equivalent-best configurations (within 0.0001) | 3 (30.0%) |
| Calibration Evidence | Low |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 1458 | 100.0% | 11m 21s | 1.0× |
| Non-dormant | 288 | 19.8% | 2m 15s | 5.1× |
| Low+ | 288 | 19.8% | 2m 15s | 5.1× |
| Moderate+ | 3 | 0.2% | 1.4s | 486.0× |
| Important+ | 3 | 0.2% | 1.4s | 486.0× |
| Critical | 3 | 0.2% | 1.4s | 486.0× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: partial or adaptive search, many parameter sets failed at least one page, broad near-best basin, small calibration sample.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `bbox_padding_fraction` | Critical | 0.9909 | 0.0112 | 33.3% | `0` (0.6844), `0.008` (0.6831), `0.016` (0.6732) |
| `max_trials` | Low | 0.0277 | 0.0027 | 50.0% | `400` (0.6831), `200` (0.6804) |
| `minimum_mean_inlier_ratio` | Low | 0.0277 | 0.0027 | 50.0% | `0.45` (0.6831), `0.25` (0.6804) |
| `minimum_scan_foreground_fraction` | Low | 0.0277 | 0.0027 | 50.0% | `0.0125` (0.6831), `0.008` (0.6804) |
| `residual_threshold_fraction` | Low | 0.0277 | 0.0027 | 50.0% | `0.008` (0.6831), `0.004` (0.6804) |
| `scan_samples` | Low | 0.0277 | 0.0027 | 50.0% | `220` (0.6831), `140` (0.6804) |
| `minimum_bbox_area_fraction` | Low | 0.0046 | 0.0007 | 100.0% | `0.18` (0.6811), `0.1` (0.6804), `0.28` (0.6804) |

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `bbox_padding_fraction` × `max_trials` | 1.0000 | 0.0091 | 10 |
| `bbox_padding_fraction` × `minimum_mean_inlier_ratio` | 1.0000 | 0.0091 | 10 |
| `bbox_padding_fraction` × `minimum_scan_foreground_fraction` | 1.0000 | 0.0091 | 10 |
| `bbox_padding_fraction` × `residual_threshold_fraction` | 1.0000 | 0.0091 | 10 |
| `bbox_padding_fraction` × `scan_samples` | 1.0000 | 0.0091 | 10 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.9713 | 0.9665 | 0.9770 | 0.0043 | 100.0% |
| 5 | 0.5547 | 0.5289 | 0.5768 | 0.0178 | 100.0% |
| 6 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 0.0% |
| 9 | 0.9327 | 0.9029 | 0.9553 | 0.0217 | 100.0% |
| 10 | 0.9446 | 0.9196 | 0.9652 | 0.0176 | 100.0% |

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
- Results commit: [00d6e89ed3f9144dda94a9a56c505bfbf3c1592d](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/commit/00d6e89ed3f9144dda94a9a56c505bfbf3c1592d).
- Workflow run: [Open workflow run](https://github.com/dlstupka/hth/actions/runs/31315329487).
- Pipeline repository: [dlstupka/hth](https://github.com/dlstupka/hth).
- Results repository: [dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results).
- Calibration index: [calibration-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/00d6e89ed3f9144dda94a9a56c505bfbf3c1592d/calibration-index.json).
- Runtime index: [runtime-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/00d6e89ed3f9144dda94a9a56c505bfbf3c1592d/runtime-index.json).
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