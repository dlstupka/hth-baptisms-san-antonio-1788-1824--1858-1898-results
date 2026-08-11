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
    - [Contour + Projection (`contour_projection`)](#contour-projection-contourprojection)
    - [Contour Quadrilateral (`contour_quad`)](#contour-quadrilateral-contourquad)
    - [Contour + GrabCut (`contour_grabcut`)](#contour-grabcut-contourgrabcut)
    - [Contour + Components (`contour_components`)](#contour-components-contourcomponents)
    - [Contour Envelope (`contour`)](#contour-envelope-contour)
    - [GrabCut Segmentation (`grabcut`)](#grabcut-segmentation-grabcut)
    - [GrabCut + Contour (`grabcut_contour`)](#grabcut-contour-grabcutcontour)
    - [Gradient Boundary Voting (`gradient_vote`)](#gradient-boundary-voting-gradientvote)
    - [RANSAC Border Fit (`ransac`)](#ransac-border-fit-ransac)
    - [Connected Components (`components`)](#connected-components-components)
    - [Line Segment Detector (`lsd`)](#line-segment-detector-lsd)
    - [Border Energy Validator (`border_energy`)](#border-energy-validator-borderenergy)
    - [Hough Line Borders (`hough`)](#hough-line-borders-hough)
    - [Cross-Edge Contour (`cross_edge_contour`)](#cross-edge-contour-crossedgecontour)
    - [Consensus Quadrilateral (`consensus_quad`)](#consensus-quadrilateral-consensusquad)
    - [Edge-Supported Contour (`edge_contour`)](#edge-supported-contour-edgecontour)
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

| Rank | Detector | Detector ID | Role | Golden Set ID | Status | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Parameter Sets | Eval Rate | Doc Time | Run Elapsed |
|---:|---|---|---|---|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | Adaptive Radial Edge Search | `adaptive_radial_edge` | Generator | `HTH-0001` | complete | `5010d5b46516` | `5010d5b46516` | 0.9599 | 0.9440 | 0.0114 | 0.9599 | 0 | 6562 | 0.0853 pg/s | 3h 1m 27s | 45m 27s |
| 2 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | complete | `5f802d0c469d` | `5f802d0c469d` | 0.9547 | 0.9432 | 0.0104 | 0.9547 | 0 | 6562 | 10.64 pg/s | 1m 27s | 3m 52s |
| 3 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | complete | `0cd13eb1a471` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 6562 | 10.92 pg/s | 1m 25s | 7m 22s |
| 4 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | complete | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 10 | 4.653 pg/s | 3m 20s | 36.3s |
| 5 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | complete | `3eec8a03f1de` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 6562 | 0.1764 pg/s | 1h 27m 47s | 3h 9m 30s |
| 6 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | complete | `14818b491952` | `baseline` | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | 19684 | 83.60 pg/s | 11.1s | 3m 48s |
| 7 | Contour Envelope | `contour` | Generator | `HTH-0001` | complete | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | 1458 | 145.59 pg/s | 6.4s | 4.6s |
| 8 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | complete | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 10 | 0.0844 pg/s | 3h 3m 27s | 6m 1s |
| 9 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | complete | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 10 | 0.0785 pg/s | 3h 17m 14s | 3m 56s |
| 10 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | complete | `dfbdcf4e5b70` | `dfbdcf4e5b70` | 0.7746 | 0.0000 | 0.3875 | 0.9683 | 1 | 6562 | 28.15 pg/s | 33s | 6.4s |
| 11 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | complete | `9647b030702e` | `9647b030702e` | 0.7541 | 0.3558 | 0.2541 | 0.7541 | 0 | 1458 | 4.771 pg/s | 3m 15s | 1m 31s |
| 12 | Connected Components | `components` | Generator | `HTH-0001` | complete | `2f8c682579f8` | `2f8c682579f8` | 0.6827 | 0.0000 | 0.3773 | 0.8534 | 1 | 19683 | 145.10 pg/s | 6.4s | 40.8s |
| 13 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | complete | `7546c5067527` | `7546c5067527` | 0.5902 | 0.0000 | 0.4448 | 0.7378 | 1 | 2187 | 13.20 pg/s | 1m 10s | 59s |
| 14 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | complete | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | 0.9237 | 2 | 6562 | 19.45 pg/s | 47.8s | 3m 59s |
| 15 | Hough Line Borders | `hough` | Generator | `HTH-0001` | complete | `07a0b3ac190f` | `07a0b3ac190f` | 0.5013 | 0.0000 | 0.4095 | 0.8355 | 2 | 2188 | 2.953 pg/s | 5m 15s | 3m 4s |
| 16 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | complete | `0474de95ff10` | `0474de95ff10` | 0.3818 | 0.0000 | 0.4677 | 0.9546 | 3 | 6562 | 11.32 pg/s | 1m 22s | 3m 28s |
| 17 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | complete | `f387da7ebb7e` | `f387da7ebb7e` | 0.3317 | 0.0000 | 0.4430 | 0.5528 | 2 | 243 | 3.487 pg/s | 4m 26s | 21.3s |
| 18 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | complete | `f4cb24ecb33b` | `f4cb24ecb33b` | 0.1928 | 0.0000 | 0.3855 | 0.9638 | 4 | 13123 | 3.486 pg/s | 4m 27s | 1m 8s |

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

| Rank | Detector | Detector ID | Role | Golden Set ID | Date | Build* | Est. Serial Runtime** | Parameter Set ID | Parameter Sets | Search Type | Successful Parameter Sets | Best Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Δ Baseline Avg IoU | Near-best Coverage (Basin) | Equivalent Best Configurations | Calibration Evidence | Approval Level |
|---:|---|---|---|---|---|---|---:|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---|
| **1** | **Adaptive Radial Edge Search** | **`adaptive_radial_edge`** | **Generator** | **`HTH-0001`** | **2026-08-07** | **[#241](https://github.com/dlstupka/hth/actions/runs/31142095265)** | **45m 27s** | **`5010d5b46516`** | **6562** | **exhaustive** | **100.0%** | **0.9599** | **0.9440** | **0.0114** | **0.9599** | **0** | **+0.0270** | **0.1%** | **0.1%** | **Medium** | **Recommended** |
| 2 | Radial Edge Search | `radial_edge` | Generator | `HTH-0001` | 2026-08-10 | [#295](https://github.com/dlstupka/hth/actions/runs/31424176107) | 3m 52s | `5f802d0c469d` | 6562 | exhaustive | 100.0% | 0.9547 | 0.9432 | 0.0104 | 0.9547 | 0 | +0.0044 | 1.2% | 1.2% | High | Approved |
| 3 | Contour + GrabCut | `contour_grabcut` | Hybrid (Contour Quad + GrabCut) | `HTH-0001` | 2026-08-10 | [#285](https://github.com/dlstupka/hth/actions/runs/31424162073) | 3h 9m 30s | `3eec8a03f1de` | 6562 | exhaustive | 100.0% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 100.0% | 100.0% | High | Approved |
| 4 | Contour + Projection | `contour_projection` | Hybrid (Contour Quad + Projection) | `HTH-0001` | 2026-08-10 | [#286](https://github.com/dlstupka/hth/actions/runs/31424163624) | 7m 22s | `0cd13eb1a471` | 6562 | exhaustive | 100.0% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 92.6% | 92.6% | High | Approved |
| 5 | Contour Quadrilateral | `contour_quad` | Generator | `HTH-0001` | 2026-08-11 | [#304](https://github.com/dlstupka/hth/actions/runs/31445390047) | 36.3s | `bea942a4969a` | 10 | smoke | 10.0% | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | +0.0000 | 10.0% | 10.0% | Low | Provisional |
| 6 | Contour + Components | `contour_components` | Hybrid (Contour Quad + Components) | `HTH-0001` | 2026-08-10 | [#284](https://github.com/dlstupka/hth/actions/runs/31424160561) | 3m 48s | `14818b491952` | 19684 | exhaustive | 100.0% | 0.8617 | 0.7572 | 0.0655 | 0.8617 | 0 | +0.0000 | 100.0% | 100.0% | High | Approved |
| 7 | Contour Envelope | `contour` | Generator | `HTH-0001` | 2026-08-10 | [#283](https://github.com/dlstupka/hth/actions/runs/31424159190) | 4.6s | `7aed2fc501c5` | 1458 | exhaustive | 50.0% | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | +0.3120 | 1.9% | 1.9% | Medium | Recommended |
| 8 | GrabCut Segmentation | `grabcut` | Generator | `HTH-0001` | 2026-08-11 | [#304](https://github.com/dlstupka/hth/actions/runs/31445390047) | 6m 1s | `018d128420cb` | 10 | smoke | 100.0% | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | +0.0000 | 10.0% | 10.0% | Medium | Provisional |
| 9 | GrabCut + Contour | `grabcut_contour` | Hybrid (GrabCut + Contour Quad) | `HTH-0001` | 2026-08-11 | [#304](https://github.com/dlstupka/hth/actions/runs/31445390047) | 3m 56s | `3817f226228a` | 10 | smoke | 100.0% | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | +0.0000 | 10.0% | 10.0% | Medium | Provisional |
| 10 | Gradient Boundary Voting | `gradient_vote` | Generator | `HTH-0001` | 2026-08-10 | [#300](https://github.com/dlstupka/hth/actions/runs/31436321510) | 6.4s | `dfbdcf4e5b70` | 6562 | exhaustive | 79.4% | 0.7746 | 0.0000 | 0.3875 | 0.9683 | 1 | -0.1136 | 11.1% | 0.8% | Medium | Recommended |
| 11 | RANSAC Border Fit | `ransac` | Generator | `HTH-0001` | 2026-08-10 | [#296](https://github.com/dlstupka/hth/actions/runs/31424177450) | 1m 31s | `9647b030702e` | 1458 | exhaustive | 5.3% | 0.7541 | 0.3558 | 0.2541 | 0.7541 | 0 | +0.2076 | 0.4% | 0.4% | Medium | Recommended |
| 12 | Connected Components | `components` | Generator | `HTH-0001` | 2026-08-10 | [#281](https://github.com/dlstupka/hth/actions/runs/31424156590) | 40.8s | `2f8c682579f8` | 19683 | exhaustive | 75.8% | 0.6827 | 0.0000 | 0.3773 | 0.8534 | 1 | -0.0358 | 2.3% | 2.3% | Medium | Recommended |
| 13 | Line Segment Detector | `lsd` | Generator | `HTH-0001` | 2026-08-10 | [#294](https://github.com/dlstupka/hth/actions/runs/31424174875) | 59s | `7546c5067527` | 2187 | exhaustive | 0.0% | 0.5902 | 0.0000 | 0.4448 | 0.7378 | 1 | +0.2654 | 1.2% | 0.4% | Medium | Recommended |
| 14 | Border Energy Validator | `border_energy` | Hybrid (Contour Quad + Border Energy) | `HTH-0001` | 2026-08-10 | [#278](https://github.com/dlstupka/hth/actions/runs/31423513220) | 3m 59s | `e38a975d1436` | 6562 | exhaustive | 0.0% | 0.5542 | 0.0000 | 0.4538 | 0.9237 | 2 | +0.0000 | 58.0% | 58.0% | Medium | Recommended |
| 15 | Hough Line Borders | `hough` | Generator | `HTH-0001` | 2026-08-10 | [#293](https://github.com/dlstupka/hth/actions/runs/31424173458) | 3m 4s | `07a0b3ac190f` | 2188 | exhaustive | 0.0% | 0.5013 | 0.0000 | 0.4095 | 0.8355 | 2 | +0.0229 | 0.1% | 0.0% | Medium | Recommended |
| 16 | Cross-Edge Contour | `cross_edge_contour` | Hybrid (Contour Quad + Cross-Edge Validation) | `HTH-0001` | 2026-08-10 | [#288](https://github.com/dlstupka/hth/actions/runs/31424166301) | 3m 28s | `0474de95ff10` | 6562 | exhaustive | 29.6% | 0.3818 | 0.0000 | 0.4677 | 0.9546 | 3 | -0.4950 | 33.3% | 33.3% | Medium | Recommended |
| 17 | Consensus Quadrilateral | `consensus_quad` | Hybrid (Contour Quad + Edge Contour) | `HTH-0001` | 2026-08-10 | [#282](https://github.com/dlstupka/hth/actions/runs/31424157793) | 21.3s | `f387da7ebb7e` | 243 | exhaustive | 0.0% | 0.3317 | 0.0000 | 0.4430 | 0.5528 | 2 | +0.0009 | 9.9% | 4.9% | Medium | Recommended |
| 18 | Edge-Supported Contour | `edge_contour` | Hybrid (Contour Quad + LSD) | `HTH-0001` | 2026-08-10 | [#301](https://github.com/dlstupka/hth/actions/runs/31437186835) | 1m 8s | `f4cb24ecb33b` | 13123 | exhaustive | 12.3% | 0.1928 | 0.0000 | 0.3855 | 0.9638 | 4 | -0.3464 | 27.8% | 27.8% | Medium | Recommended |

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
- **Build*:** `#run` links open GitHub Actions logs and artifacts and expire according to repository retention; the calibration data persists in [calibration-intelligence.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/f79bfb107b2c16d9e2ee041a7be3669bd4cb39a9/source-documents/baptisms-san-antonio-baptism-records-1788-1824-1858-1898/golden-sets/hth-0001/135c0ff57687/calibrations/adaptive_radial_edge/run-20260807-024337/calibration-intelligence.json).
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
| Est. serial runtime for full parameter set evaluation* | 13d 5h 15m 34s |
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
| Exhaustive | 1062882 | 100.0% | 13d 5h 15m 44s | 1.0× |
| Non-dormant | 12288 | 1.2% | 3h 40m 4s | 86.5× |
| Low+ | 12288 | 1.2% | 3h 40m 4s | 86.5× |
| Moderate+ | 12288 | 1.2% | 3h 40m 4s | 86.5× |
| Important+ | 2048 | 0.2% | 36m 41s | 519.0× |
| Critical | 2048 | 0.2% | 36m 41s | 519.0× |

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
| Est. serial runtime for full parameter set evaluation* | 8d 23h 46m |
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
| Exhaustive | 13122 | 100.0% | 8d 23h 55m 52s | 1.0× |
| Non-dormant | 576 | 4.4% | 9h 28m 42s | 22.8× |
| Low+ | 576 | 4.4% | 9h 28m 42s | 22.8× |
| Moderate+ | 576 | 4.4% | 9h 28m 42s | 22.8× |
| Important+ | 576 | 4.4% | 9h 28m 42s | 22.8× |
| Critical | 192 | 1.5% | 3h 9m 34s | 68.3× |

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
| Est. serial runtime for full parameter set evaluation* | 261d 4h 19m 44s |
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
| Exhaustive | 354295 | 100.0% | 261d 4h 30m 21s | 1.0× |
| Non-dormant | 6144 | 1.7% | 4d 12h 42m 19s | 57.7× |
| Low+ | 6144 | 1.7% | 4d 12h 42m 19s | 57.7× |
| Moderate+ | 6144 | 1.7% | 4d 12h 42m 19s | 57.7× |
| Important+ | 3072 | 0.9% | 2d 6h 21m 9s | 115.3× |
| Critical | 512 | 0.1% | 9h 3m 32s | 692.0× |

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
| Best Avg IoU | 0.9683 |
| Minimum Avg IoU | 0.8419 |
| Avg IoU StdDev | 0.0329 |
| Winner stabilized after | 5158 parameter sets |
| Winner stabilized | 4.5s (79% of search) |
| Near-best coverage (basin; within 0.0010) | 729 (11.1%) |
| Equivalent-best configurations (within 0.0001) | 54 (0.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 19m 26s | 1.0× |
| Non-dormant | 243 | 3.7% | 43.2s | 27.0× |
| Low+ | 243 | 3.7% | 43.2s | 27.0× |
| Moderate+ | 9 | 0.1% | 1.6s | 729.1× |
| Important+ | 3 | 0.0% | 533 ms | 2187.3× |
| Critical | 3 | 0.0% | 533 ms | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_span_fraction` | Critical | 0.5315 | 0.0510 | 33.3% | `0.55` (0.9462), `0.35` (0.8953), `0.45` (0.8953) |
| `gaussian_sigma` | Moderate | 0.0430 | 0.0149 | 66.7% | `1.8` (0.9175), `1.2` (0.9166), `0.8` (0.9026) |
| `border_search_fraction` | Low | 0.0248 | 0.0126 | 66.7% | `0.35` (0.9191), `0.42` (0.9111), `0.47` (0.9066) |
| `central_band_fraction` | Low | 0.0192 | 0.0099 | 100.0% | `1` (0.9157), `0.86` (0.9153), `0.7` (0.9058) |
| `vote_smooth_fraction` | Low | 0.0011 | 0.0024 | 100.0% | `0.006` (0.9138), `0.012` (0.9116), `0.02` (0.9114) |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.25` (0.8882) |
| `minimum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `rectangularity_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `gradient_percentile` | Dormant | 0.0000 | 0.0000 | 100.0% | `70` (0.9123), `90` (0.9123), `82` (0.9123) |
| `minimum_vote_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.9123), `0.25` (0.9123), `0.16` (0.9123) |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.9123), `0.65` (0.9123), `0.55` (0.9123) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `minimum_area_fraction`, `rectangularity_weight`, `gradient_percentile`, `minimum_vote_support`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_span_fraction` × `border_search_fraction` | 0.8314 | 0.2999 | 6562 |
| `gaussian_sigma` × `central_band_fraction` | 0.0956 | 0.0526 | 6562 |
| `minimum_span_fraction` × `gaussian_sigma` | 0.5805 | 0.0490 | 6562 |
| `gaussian_sigma` × `border_search_fraction` | 0.0687 | 0.0257 | 6562 |
| `minimum_span_fraction` × `central_band_fraction` | 0.5510 | 0.0196 | 6562 |

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
| Best Avg IoU | 0.8534 |
| Minimum Avg IoU | 0.6696 |
| Avg IoU StdDev | 0.0417 |
| Winner stabilized after | 55 parameter sets |
| Winner stabilized | 204 ms (0% of search) |
| Near-best coverage (basin; within 0.0010) | 450 (2.3%) |
| Equivalent-best configurations (within 0.0001) | 450 (2.3%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19683 | 100.0% | 11m 18s | 1.0× |
| Non-dormant | 2187 | 11.1% | 1m 15s | 9.0× |
| Low+ | 2187 | 11.1% | 1m 15s | 9.0× |
| Moderate+ | 27 | 0.1% | 930 ms | 729.0× |
| Important+ | 9 | 0.0% | 310 ms | 2187.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_selected_area_fraction` | Important | 0.2282 | 0.0424 | 100.0% | `0.07` (0.7982), `0.04` (0.7561), `0.02` (0.7558) |
| `morphology_dilate_fraction` | Important | 0.1138 | 0.0337 | 33.3% | `0.008` (0.7890), `0.03` (0.7658), `0.015` (0.7553) |
| `bbox_padding_fraction` | Moderate | 0.0417 | 0.0200 | 33.3% | `0` (0.7783), `0.005` (0.7735), `0.015` (0.7583) |
| `morphology_close_fraction` | Low | 0.0148 | 0.0108 | 100.0% | `0.004` (0.7736), `0.008` (0.7736), `0.016` (0.7629) |
| `merge_gap_fraction` | Low | 0.0084 | 0.0083 | 100.0% | `0.035` (0.7729), `0.02` (0.7725), `0.06` (0.7646) |
| `merge_area_ratio` | Low | 0.0062 | 0.0071 | 66.7% | `0.01` (0.7747), `0.05` (0.7679), `0.02` (0.7675) |
| `minimum_component_area_fraction` | Low | 0.0029 | 0.0055 | 100.0% | `0.0015` (0.7727), `0.003` (0.7702), `0.00075` (0.7672) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0003 | 100.0% | `0.12` (0.7701), `0.18` (0.7701), `0.08` (0.7699) |
| `minimum_component_area_px` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.7700), `25` (0.7700), `50` (0.7700) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `minimum_component_area_px`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_selected_area_fraction` × `morphology_dilate_fraction` | 0.4573 | 0.2291 | 19683 |
| `morphology_dilate_fraction` × `morphology_close_fraction` | 0.1701 | 0.0563 | 19683 |
| `morphology_dilate_fraction` × `bbox_padding_fraction` | 0.1561 | 0.0423 | 19683 |
| `minimum_selected_area_fraction` × `bbox_padding_fraction` | 0.2703 | 0.0421 | 19683 |
| `morphology_dilate_fraction` × `merge_gap_fraction` | 0.1387 | 0.0249 | 19683 |

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

<a id="border-energy-validator-borderenergy"></a>
<details>
<summary><strong>Border Energy Validator (`border_energy`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 6 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 6562 of 6562 parameter configurations.

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
| Best Avg IoU | 0.9237 |
| Minimum Avg IoU | 0.8618 |
| Avg IoU StdDev | 0.0132 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 3808 (58.0%) |
| Equivalent-best configurations (within 0.0001) | 3808 (58.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 28m 7s | 1.0× |
| Non-dormant | 81 | 1.2% | 20.8s | 81.0× |
| Low+ | 81 | 1.2% | 20.8s | 81.0× |
| Moderate+ | 27 | 0.4% | 6.9s | 243.0× |
| Important+ | 3 | 0.0% | 771 ms | 2187.3× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_side_consistency` | Important | 0.2251 | 0.0150 | 100.0% | `0.45` (0.9237), `0.3` (0.9134), `0.6` (0.9087) |
| `gaussian_sigma` | Moderate | 0.0650 | 0.0076 | 100.0% | `0.8` (0.9199), `1.8` (0.9134), `1.2` (0.9124) |
| `band_fraction` | Moderate | 0.0576 | 0.0077 | 100.0% | `0.015` (0.9192), `0.008` (0.9152), `0.004` (0.9114) |
| `minimum_border_energy` | Low | 0.0021 | 0.0013 | 100.0% | `0.18` (0.9161), `0.1` (0.9148), `0.05` (0.9148) |
| `consistency_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.15` (0.9237) |
| `contour_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.45` (0.9237) |
| `energy_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.9152), `0.3` (0.9152), `0.5` (0.9152) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.9152), `0.03` (0.9152), `0.06` (0.9152) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.9152), `0.08` (0.9152), `0.2` (0.9152) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.9152), `0.45` (0.9152), `0.7` (0.9152) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consistency_weight`, `contour_weight`, `energy_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_side_consistency` × `band_fraction` | 0.5534 | 0.3282 | 6562 |
| `minimum_side_consistency` × `gaussian_sigma` | 0.3788 | 0.1537 | 6562 |
| `gaussian_sigma` × `band_fraction` | 0.1777 | 0.1127 | 6562 |
| `band_fraction` × `minimum_border_energy` | 0.0640 | 0.0063 | 6562 |
| `minimum_side_consistency` × `minimum_border_energy` | 0.2315 | 0.0063 | 6562 |

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
| Best Avg IoU | 0.8355 |
| Minimum Avg IoU | 0.2981 |
| Avg IoU StdDev | 0.1270 |
| Winner stabilized after | 57 parameter sets |
| Winner stabilized | 7.5s (3% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (0.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2188 | 100.0% | 1h 1m 44s | 1.0× |
| Non-dormant | 729 | 33.3% | 20m 34s | 3.0× |
| Low+ | 729 | 33.3% | 20m 34s | 3.0× |
| Moderate+ | 9 | 0.4% | 15.2s | 243.1× |
| Important+ | 3 | 0.1% | 5.1s | 729.3× |
| Critical | 3 | 0.1% | 5.1s | 729.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `outer_percentile` | Critical | 0.7563 | 0.2624 | 33.3% | `5` (0.7257), `10` (0.6515), `20` (0.4633) |
| `maximum_gap_fraction` | Moderate | 0.0406 | 0.0617 | 66.7% | `0.09` (0.6412), `0.055` (0.6199), `0.025` (0.5795) |
| `canny_low_threshold` | Low | 0.0300 | 0.0524 | 33.3% | `65` (0.6362), `25` (0.6207), `40` (0.5838) |
| `minimum_length_fraction` | Low | 0.0142 | 0.0370 | 33.3% | `0.12` (0.6313), `0.2` (0.6151), `0.3` (0.5943) |
| `bbox_padding_fraction` | Low | 0.0032 | 0.0175 | 33.3% | `0.015` (0.6226), `0.005` (0.6129), `0` (0.6051) |
| `axis_angle_tolerance_degrees` | Low | 0.0018 | 0.0130 | 66.7% | `12` (0.6194), `22` (0.6148), `32` (0.6064) |
| `hough_threshold_fraction` | Dormant | 0.0007 | 0.0072 | 66.7% | `0.08` (0.6182), `0.035` (0.6114), `0.055` (0.6110) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.1` (0.5981) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`hough_threshold_fraction`, `minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_percentile` × `maximum_gap_fraction` | 0.7997 | 0.0434 | 2188 |
| `maximum_gap_fraction` × `canny_low_threshold` | 0.0818 | 0.0412 | 2188 |
| `outer_percentile` × `canny_low_threshold` | 0.7906 | 0.0343 | 2188 |
| `canny_low_threshold` × `minimum_length_fraction` | 0.0497 | 0.0198 | 2188 |
| `maximum_gap_fraction` × `minimum_length_fraction` | 0.0595 | 0.0189 | 2188 |

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

<a id="cross-edge-contour-crossedgecontour"></a>
<details>
<summary><strong>Cross-Edge Contour (`cross_edge_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 7 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 4617 of 6562 parameter configurations.

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
| Best Avg IoU | 0.9546 |
| Minimum Avg IoU | 0.8768 |
| Avg IoU StdDev | 0.0313 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 659 ms (0% of search) |
| Near-best coverage (basin; within 0.0010) | 2187 (33.3%) |
| Equivalent-best configurations (within 0.0001) | 2187 (33.3%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 48m 17s | 1.0× |
| Non-dormant | 36 | 0.5% | 15.9s | 182.3× |
| Low+ | 36 | 0.5% | 15.9s | 182.3× |
| Moderate+ | 4 | 0.1% | 1.8s | 1640.5× |
| Important+ | 4 | 0.1% | 1.8s | 1640.5× |
| Critical | 4 | 0.1% | 1.8s | 1640.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_polarity_consistency` | Critical | 0.9541 | 0.0778 | 25.0% | `0.8` (0.9546), `0.65` (0.9112), `0.5` (0.8801) |
| `sample_offset_fraction` | Low | 0.0154 | 0.0082 | 100.0% | `0.004` (0.9208), `0.014` (0.9126), `0.008` (0.9126) |
| `minimum_cross_edge_contrast` | Low | 0.0024 | 0.0033 | 100.0% | `0.08` (0.9175), `0.02` (0.9142), `0.045` (0.9142) |
| `contour_weight` | Dormant | 0.0002 | 0.0000 | 0.0% | `0.45` (0.8768) |
| `polarity_weight` | Dormant | 0.0002 | 0.0000 | 0.0% | `0.15` (0.8768) |
| `contrast_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.3` (0.9153), `0.5` (0.9153), `0.4` (0.9153) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.9153), `0.06` (0.9153), `0.04` (0.9153) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.9153), `0.18` (0.9153), `0.12` (0.9153) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.9153), `0.7` (0.9153), `0.55` (0.9153) |
| `samples_per_edge` | Dormant | 0.0000 | 0.0000 | 100.0% | `24` (0.9153), `72` (0.9153), `48` (0.9153) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_weight`, `polarity_weight`, `contrast_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `samples_per_edge`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_polarity_consistency` × `sample_offset_fraction` | 0.9781 | 0.0240 | 6562 |
| `sample_offset_fraction` × `minimum_cross_edge_contrast` | 0.0227 | 0.0073 | 6562 |
| `minimum_polarity_consistency` × `minimum_cross_edge_contrast` | 0.9614 | 0.0073 | 6562 |

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

<a id="edge-supported-contour-edgecontour"></a>
<details>
<summary><strong>Edge-Supported Contour (`edge_contour`)</strong></summary>

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 13 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
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
| Best Avg IoU | 0.9638 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.1763 |
| Winner stabilized after | 125 parameter sets |
| Winner stabilized | 1.9s (1% of search) |
| Near-best coverage (basin; within 0.0010) | 3645 (27.8%) |
| Equivalent-best configurations (within 0.0001) | 3645 (27.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13123 | 100.0% | 5h 13m 43s | 1.0× |
| Non-dormant | 54 | 0.4% | 1m 17s | 243.0× |
| Low+ | 54 | 0.4% | 1m 17s | 243.0× |
| Moderate+ | 9 | 0.1% | 12.9s | 1458.1× |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `lsd_scale` | Moderate | 0.0537 | 0.0881 | 100.0% | `0.8` (0.9140), `0.6` (0.9110), `1` (0.8259) |
| `minimum_segment_length_fraction` | Moderate | 0.0301 | 0.0650 | 100.0% | `0.03` (0.9054), `0.06` (0.9051), `0.1` (0.8404) |
| `lsd_refine_mode` | Low | 0.0284 | 0.0595 | 100.0% | `none` (0.9133), `std` (0.8539) |
| `minimum_edge_support` | Low | 0.0038 | 0.0263 | 100.0% | `0.05` (0.8953), `0.12` (0.8865), `0.2` (0.8690) |
| `edge_support_dilation_fraction` | Dormant | 0.0007 | 0.0104 | 100.0% | `0.01` (0.8874), `0.003` (0.8864), `0.006` (0.8770) |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.8986) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.8986) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.8986) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.8986) |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.8986) |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 0.0% | `9` (0.8986) |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 0.0% | `true` (0.8986) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`edge_support_dilation_fraction`, `angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`, `edge_support_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `lsd_scale` × `minimum_segment_length_fraction` | 0.1688 | 0.1152 | 13123 |
| `lsd_scale` × `lsd_refine_mode` | 0.1444 | 0.0907 | 13123 |
| `minimum_segment_length_fraction` × `lsd_refine_mode` | 0.0986 | 0.0685 | 13123 |
| `lsd_scale` × `minimum_edge_support` | 0.1142 | 0.0606 | 13123 |
| `minimum_segment_length_fraction` × `minimum_edge_support` | 0.0691 | 0.0390 | 13123 |

#### Page Sensitivity

| Golden Set Page | Avg IoU | Min IoU | Max IoU | StdDev | Success rate |
|---:|---:|---:|---:|---:|---:|
| 1 | 0.2478 | 0.0000 | 0.8542 | 0.3877 | 29.0% |
| 5 | 0.4735 | 0.0000 | 0.8618 | 0.4288 | 54.9% |
| 6 | 0.0937 | 0.0000 | 0.7589 | 0.2496 | 12.3% |
| 9 | 0.9281 | 0.0000 | 0.9638 | 0.1820 | 96.3% |
| 10 | 0.5717 | 0.0000 | 0.9454 | 0.4278 | 64.2% |

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
| Parameter sets evaluated | 105988 | Total detector parameter configurations evaluated across all runs. |
| Golden Set page evaluations | 529940 | Parameter sets multiplied by evaluated Golden Set pages. |
| Aggregate detector runtime | 4h 35m 54s | Sum of detector wall-clock runtimes; this is not the elapsed time experienced by the user. |
| Regression wall-clock span | 3d 21h 38m 31s | Earliest detector start through latest detector finish. |
| Effective detector concurrency | 0.05× | Aggregate detector runtime divided by regression wall-clock span. |
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
| 1 | Border Energy Validator (`border_energy`) | 1 | unknown | single-detector |
| 1 | Connected Components (`components`) | 1 | unknown | single-detector |
| 1 | Contour Envelope (`contour`) | 1 | unknown | single-detector |
| 1 | Consensus Quadrilateral (`consensus_quad`) | 1 | unknown | single-detector |
| 1 | Contour + Components (`contour_components`) | 1 | unknown | single-detector |
| 1 | Contour + GrabCut (`contour_grabcut`) | 1 | unknown | single-detector |
| 1 | Contour + Projection (`contour_projection`) | 1 | unknown | single-detector |
| 1 | Cross-Edge Contour (`cross_edge_contour`) | 1 | unknown | single-detector |
| 1 | Hough Line Borders (`hough`) | 1 | unknown | single-detector |
| 1 | Line Segment Detector (`lsd`) | 1 | unknown | single-detector |
| 1 | Radial Edge Search (`radial_edge`) | 1 | unknown | single-detector |
| 1 | RANSAC Border Fit (`ransac`) | 1 | unknown | single-detector |
| 1 | Gradient Boundary Voting (`gradient_vote`) | 1 | unknown | single-detector |
| 1 | Edge-Supported Contour (`edge_contour`) | 1 | unknown | single-detector |
| 1 | GrabCut Segmentation (`grabcut`) | 1 | 6m 22s | runtime-index:mode+strategy+dimension+golden-set:score=108 |
| 3 | GrabCut + Contour (`grabcut_contour`) | 3 | 4m 7s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |
| 5 | Contour Quadrilateral (`contour_quad`) | 4 | 37.1s | runtime-index:mode+strategy+threads+dimension+golden-set:score=124 |

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
| Exhaustive | 146d 21h 42m 45s |
| Non-dormant | 2d 13h 41m 20s |
| Critical only | 10h 33m 41s |

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
| Baseline | `a132c2ac5e87` | `baseline` | 0.9329 | 0.8817 | 0.0344 | 0.9329 | 0 | 312 ms |

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
| Winner | `e38a975d1436` | `baseline` | 0.5542 | 0.0000 | 0.4538 | 0.9237 | 2 | 257 ms |

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
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 2 | 8 | 16 | `rh8-al325` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `e38a975d1436` | `baseline` | 0.9237 | 0.8618 | 0.0444 | +0.3695 | 0.9237 | 2 | unknown | unknown |
| 2 | `ee832909df97` | `ee832909df97` | 0.9237 | 0.8618 | 0.0444 | +0.3695 | 0.9237 | 2 | 815 ms | 0.14% |
| 3 | `66d5d1766542` | `66d5d1766542` | 0.9237 | 0.8618 | 0.0444 | +0.3695 | 0.9237 | 2 | 818 ms | 0.17% |
| 4 | `d4b93ff23f99` | `d4b93ff23f99` | 0.9237 | 0.8618 | 0.0444 | +0.3695 | 0.9237 | 2 | 799 ms | 0.09% |
| 5 | `120c3f0e2ab3` | `120c3f0e2ab3` | 0.9237 | 0.8618 | 0.0444 | +0.3695 | 0.9237 | 2 | 800 ms | 0.11% |

## Page Analysis — border_energy

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
- No polygon found: `2`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `0`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `baseline` | 0.0000 | No polygon found |
| 6 | `baseline` | 0.0000 | No polygon found |

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

- Recommended parameter set: `e38a975d1436`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.5542`
- Avg IoU Success: `0.9237`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4538`
- Calibration evidence: `Medium`
- Dormant parameters: `consistency_weight, contour_weight, energy_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity`
- Available domain spaces: `exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 6 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 6562 of 6562 parameter configurations.

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
| Best Avg IoU | 0.9237 |
| Minimum Avg IoU | 0.8618 |
| Avg IoU StdDev | 0.0132 |
| Winner stabilized after | unknown parameter sets |
| Winner stabilized | unknown (unknown of search) |
| Near-best coverage (basin; within 0.0010) | 3808 (58.0%) |
| Equivalent-best configurations (within 0.0001) | 3808 (58.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 28m 7s | 1.0× |
| Non-dormant | 81 | 1.2% | 20.8s | 81.0× |
| Low+ | 81 | 1.2% | 20.8s | 81.0× |
| Moderate+ | 27 | 0.4% | 6.9s | 243.0× |
| Important+ | 3 | 0.0% | 771 ms | 2187.3× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_side_consistency` | Important | 0.2251 | 0.0150 | 100.0% | `0.45` (0.9237), `0.3` (0.9134), `0.6` (0.9087) |
| `gaussian_sigma` | Moderate | 0.0650 | 0.0076 | 100.0% | `0.8` (0.9199), `1.8` (0.9134), `1.2` (0.9124) |
| `band_fraction` | Moderate | 0.0576 | 0.0077 | 100.0% | `0.015` (0.9192), `0.008` (0.9152), `0.004` (0.9114) |
| `minimum_border_energy` | Low | 0.0021 | 0.0013 | 100.0% | `0.18` (0.9161), `0.1` (0.9148), `0.05` (0.9148) |
| `consistency_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.15` (0.9237) |
| `contour_weight` | Dormant | 0.0001 | 0.0000 | 100.0% | `0.45` (0.9237) |
| `energy_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.4` (0.9152), `0.3` (0.9152), `0.5` (0.9152) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.04` (0.9152), `0.03` (0.9152), `0.06` (0.9152) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.12` (0.9152), `0.08` (0.9152), `0.2` (0.9152) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.55` (0.9152), `0.45` (0.9152), `0.7` (0.9152) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`consistency_weight`, `contour_weight`, `energy_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_side_consistency` × `band_fraction` | 0.5534 | 0.3282 | 6562 |
| `minimum_side_consistency` × `gaussian_sigma` | 0.3788 | 0.1537 | 6562 |
| `gaussian_sigma` × `band_fraction` | 0.1777 | 0.1127 | 6562 |
| `band_fraction` × `minimum_border_energy` | 0.0640 | 0.0063 | 6562 |
| `minimum_side_consistency` × `minimum_border_energy` | 0.2315 | 0.0063 | 6562 |

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
| Winner | `2f8c682579f8` | `2f8c682579f8` | 0.6827 | 0.0000 | 0.3773 | 0.8534 | 1 | 34 ms |
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
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 2 | 8 | 16 | `rh8-al320` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `2f8c682579f8` | `2f8c682579f8` | 0.8534 | 0.5429 | 0.1796 | +0.1707 | 0.8534 | 1 | 204 ms | 0.28% |
| 2 | `2f1b49365337` | `2f1b49365337` | 0.8534 | 0.5429 | 0.1796 | +0.1707 | 0.8534 | 1 | 206 ms | 0.28% |
| 3 | `a24239cc8a0c` | `a24239cc8a0c` | 0.8534 | 0.5429 | 0.1796 | +0.1707 | 0.8534 | 1 | 367 ms | 0.69% |
| 4 | `f71ef0973059` | `f71ef0973059` | 0.8534 | 0.5429 | 0.1796 | +0.1707 | 0.8534 | 1 | 525 ms | 1.11% |
| 5 | `35bccfbf6115` | `35bccfbf6115` | 0.8534 | 0.5429 | 0.1796 | +0.1707 | 0.8534 | 1 | 533 ms | 1.14% |

## Page Analysis — components

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `2f8c682579f8` | 0.9734 | 0.9734 | -0.0000 | Unchanged |
| 5 | `2f8c682579f8` | 0.4973 | 0.5429 | +0.0455 | Improved |
| 6 | `2f8c682579f8` | 0.2413 | 0.0000 | -0.2413 | No polygon found |
| 9 | `2f8c682579f8` | 0.9314 | 0.9429 | +0.0115 | Improved |
| 10 | `2f8c682579f8` | 0.9491 | 0.9543 | +0.0052 | Improved |

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
- No polygon found: `1`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 6 | `2f8c682579f8` | 0.0000 | No polygon found; Regressed |

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

- Recommended parameter set: `2f8c682579f8`
- Recommended parameter short name: `2f8c682579f8`
- Best observed Avg IoU: `0.6827`
- Avg IoU Success: `0.8534`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3773`
- Calibration evidence: `Medium`
- Dormant parameters: `minimum_bbox_area_fraction, minimum_component_area_px`
- Available domain spaces: `exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

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
| Best Avg IoU | 0.8534 |
| Minimum Avg IoU | 0.6696 |
| Avg IoU StdDev | 0.0417 |
| Winner stabilized after | 55 parameter sets |
| Winner stabilized | 204 ms (0% of search) |
| Near-best coverage (basin; within 0.0010) | 450 (2.3%) |
| Equivalent-best configurations (within 0.0001) | 450 (2.3%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 19683 | 100.0% | 11m 18s | 1.0× |
| Non-dormant | 2187 | 11.1% | 1m 15s | 9.0× |
| Low+ | 2187 | 11.1% | 1m 15s | 9.0× |
| Moderate+ | 27 | 0.1% | 930 ms | 729.0× |
| Important+ | 9 | 0.0% | 310 ms | 2187.0× |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_selected_area_fraction` | Important | 0.2282 | 0.0424 | 100.0% | `0.07` (0.7982), `0.04` (0.7561), `0.02` (0.7558) |
| `morphology_dilate_fraction` | Important | 0.1138 | 0.0337 | 33.3% | `0.008` (0.7890), `0.03` (0.7658), `0.015` (0.7553) |
| `bbox_padding_fraction` | Moderate | 0.0417 | 0.0200 | 33.3% | `0` (0.7783), `0.005` (0.7735), `0.015` (0.7583) |
| `morphology_close_fraction` | Low | 0.0148 | 0.0108 | 100.0% | `0.004` (0.7736), `0.008` (0.7736), `0.016` (0.7629) |
| `merge_gap_fraction` | Low | 0.0084 | 0.0083 | 100.0% | `0.035` (0.7729), `0.02` (0.7725), `0.06` (0.7646) |
| `merge_area_ratio` | Low | 0.0062 | 0.0071 | 66.7% | `0.01` (0.7747), `0.05` (0.7679), `0.02` (0.7675) |
| `minimum_component_area_fraction` | Low | 0.0029 | 0.0055 | 100.0% | `0.0015` (0.7727), `0.003` (0.7702), `0.00075` (0.7672) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0003 | 100.0% | `0.12` (0.7701), `0.18` (0.7701), `0.08` (0.7699) |
| `minimum_component_area_px` | Dormant | 0.0000 | 0.0000 | 100.0% | `10` (0.7700), `25` (0.7700), `50` (0.7700) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`minimum_bbox_area_fraction`, `minimum_component_area_px`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_selected_area_fraction` × `morphology_dilate_fraction` | 0.4573 | 0.2291 | 19683 |
| `morphology_dilate_fraction` × `morphology_close_fraction` | 0.1701 | 0.0563 | 19683 |
| `morphology_dilate_fraction` × `bbox_padding_fraction` | 0.1561 | 0.0423 | 19683 |
| `minimum_selected_area_fraction` × `bbox_padding_fraction` | 0.2703 | 0.0421 | 19683 |
| `morphology_dilate_fraction` × `merge_gap_fraction` | 0.1387 | 0.0249 | 19683 |

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
| Winner | `f387da7ebb7e` | `f387da7ebb7e` | 0.3317 | 0.0000 | 0.4430 | 0.5528 | 2 | 1.4s |
| Baseline | `dce471449373` | `baseline` | 0.3308 | 0.0000 | 0.4418 | 0.5513 | 2 | 572 ms |

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
| 1 | `f387da7ebb7e` | `f387da7ebb7e` | 0.5528 | 0.0000 | 0.4526 | +0.2211 | 0.5528 | 2 | 4.9s | 16.53% |
| 2 | `d3afdfd96e35` | `d3afdfd96e35` | 0.5528 | 0.0000 | 0.4526 | +0.2211 | 0.5528 | 2 | 4.9s | 15.70% |
| 3 | `a00dcf94f01e` | `a00dcf94f01e` | 0.5528 | 0.0000 | 0.4526 | +0.2211 | 0.5528 | 2 | 4.9s | 17.36% |
| 4 | `855195437d31` | `855195437d31` | 0.5528 | 0.0000 | 0.4526 | +0.2211 | 0.5528 | 2 | 7.7s | 32.23% |
| 5 | `99d0beb98285` | `99d0beb98285` | 0.5528 | 0.0000 | 0.4526 | +0.2211 | 0.5528 | 2 | 7.7s | 33.88% |

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
- Best observed Avg IoU: `0.3317`
- Avg IoU Success: `0.5528`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4430`
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
| Winner | `7aed2fc501c5` | `7aed2fc501c5` | 0.8498 | 0.5457 | 0.1589 | 0.8498 | 0 | 35 ms |
| Baseline | `6019a18e4c4e` | `baseline` | 0.5378 | 0.0000 | 0.4366 | 0.6722 | 1 | 9 ms |

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

- Run ID: `run-20260811-001637`
- Detector: `contour_quad`
- Strategy: `exhaustive`
- Pipeline commit: `6d781d53e399`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-11T00:16:37.132357+00:00`
- Finished: `2026-08-11T00:17:13.440564+00:00`
- Wall-clock elapsed: `36.3s`
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

## Results — contour_quad

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 1.1s |

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

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000445` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `bea942a4969a` | `baseline` | 0.8768 | 0.7589 | 0.0734 | +0.0000 | 0.8768 | 0 | unknown | unknown |
| 2 | `34f9c8482c2a` | `34f9c8482c2a` | 0.7045 | 0.0000 | 0.3597 | -0.1724 | 0.8806 | 1 | 1.7s | 33.33% |
| 3 | `52a859d3db22` | `52a859d3db22` | 0.7045 | 0.0000 | 0.3597 | -0.1724 | 0.8806 | 1 | 2s | 44.44% |
| 4 | `4d07d3594663` | `4d07d3594663` | 0.7045 | 0.0000 | 0.3597 | -0.1724 | 0.8806 | 1 | 2.7s | 77.78% |
| 5 | `adb14cea60cf` | `adb14cea60cf` | 0.7045 | 0.0000 | 0.3597 | -0.1724 | 0.8806 | 1 | 3.1s | 88.89% |

## Page Analysis — contour_quad

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
Search completed in **36.3s** wall-clock time.

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

## Calibration Intelligence — contour_quad

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260811-001637`
- Calibration schema: `1.1`
- Detector: `contour_quad`
- Detector configuration: `hth-pipeline/config/detectors/contour_quad.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `6d781d53e3995fb245164310fe370bd3ffa552b5`
- Source commit: `76fd2515c40813be0fd36d1e32d8b6ad48c5cf13`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `bea942a4969a`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8768`
- Avg IoU Success: `0.8768`
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
| Est. serial runtime for full parameter set evaluation* | 13d 5h 15m 34s |
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
| Exhaustive | 1062882 | 100.0% | 13d 5h 15m 44s | 1.0× |
| Non-dormant | 12288 | 1.2% | 3h 40m 4s | 86.5× |
| Low+ | 12288 | 1.2% | 3h 40m 4s | 86.5× |
| Moderate+ | 12288 | 1.2% | 3h 40m 4s | 86.5× |
| Important+ | 2048 | 0.2% | 36m 41s | 519.0× |
| Critical | 2048 | 0.2% | 36m 41s | 519.0× |

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
| Winner | `0474de95ff10` | `0474de95ff10` | 0.3818 | 0.0000 | 0.4677 | 0.9546 | 3 | 442 ms |
| Baseline | `a5450e58ec9e` | `baseline` | 0.8768 | 0.7589 | 0.0734 | 0.8768 | 0 | 214 ms |

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
| 1 | `0474de95ff10` | `0474de95ff10` | 0.9546 | 0.9454 | 0.0092 | +0.5728 | 0.9546 | 3 | 659 ms | 0.03% |
| 2 | `085e78898621` | `085e78898621` | 0.9546 | 0.9454 | 0.0092 | +0.5728 | 0.9546 | 3 | 710 ms | 0.11% |
| 3 | `00deca1b6ff8` | `00deca1b6ff8` | 0.9546 | 0.9454 | 0.0092 | +0.5728 | 0.9546 | 3 | 1.1s | 0.32% |
| 4 | `ef376e2f7b6c` | `ef376e2f7b6c` | 0.9546 | 0.9454 | 0.0092 | +0.5728 | 0.9546 | 3 | 1.1s | 0.26% |
| 5 | `43b9dfeec6ac` | `43b9dfeec6ac` | 0.9546 | 0.9454 | 0.0092 | +0.5728 | 0.9546 | 3 | 1.1s | 0.35% |

## Page Analysis — cross_edge_contour

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `0474de95ff10` | 0.8542 | 0.0000 | -0.8542 | No polygon found |
| 5 | `0474de95ff10` | 0.8618 | 0.0000 | -0.8618 | No polygon found |
| 6 | `0474de95ff10` | 0.7589 | 0.0000 | -0.7589 | No polygon found |
| 9 | `0474de95ff10` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `0474de95ff10` | 0.9454 | 0.9454 | +0.0000 | Unchanged |

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
- No polygon found: `3`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `3`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `0474de95ff10` | 0.0000 | No polygon found; Regressed |
| 5 | `0474de95ff10` | 0.0000 | No polygon found; Regressed |
| 6 | `0474de95ff10` | 0.0000 | No polygon found; Regressed |

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

- Recommended parameter set: `0474de95ff10`
- Recommended parameter short name: `0474de95ff10`
- Best observed Avg IoU: `0.3818`
- Avg IoU Success: `0.9546`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4677`
- Calibration evidence: `Medium`
- Dormant parameters: `contour_weight, polarity_weight, contrast_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity, samples_per_edge`
- Available domain spaces: `critical, exhaustive, important_plus, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 7 of 10 measured parameters were dormant and may be omitted from a source-specific follow-up search.
- Detector failed on at least one Golden Set page for 4617 of 6562 parameter configurations.

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
| Best Avg IoU | 0.9546 |
| Minimum Avg IoU | 0.8768 |
| Avg IoU StdDev | 0.0313 |
| Winner stabilized after | 2 parameter sets |
| Winner stabilized | 659 ms (0% of search) |
| Near-best coverage (basin; within 0.0010) | 2187 (33.3%) |
| Equivalent-best configurations (within 0.0001) | 2187 (33.3%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 48m 17s | 1.0× |
| Non-dormant | 36 | 0.5% | 15.9s | 182.3× |
| Low+ | 36 | 0.5% | 15.9s | 182.3× |
| Moderate+ | 4 | 0.1% | 1.8s | 1640.5× |
| Important+ | 4 | 0.1% | 1.8s | 1640.5× |
| Critical | 4 | 0.1% | 1.8s | 1640.5× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_polarity_consistency` | Critical | 0.9541 | 0.0778 | 25.0% | `0.8` (0.9546), `0.65` (0.9112), `0.5` (0.8801) |
| `sample_offset_fraction` | Low | 0.0154 | 0.0082 | 100.0% | `0.004` (0.9208), `0.014` (0.9126), `0.008` (0.9126) |
| `minimum_cross_edge_contrast` | Low | 0.0024 | 0.0033 | 100.0% | `0.08` (0.9175), `0.02` (0.9142), `0.045` (0.9142) |
| `contour_weight` | Dormant | 0.0002 | 0.0000 | 0.0% | `0.45` (0.8768) |
| `polarity_weight` | Dormant | 0.0002 | 0.0000 | 0.0% | `0.15` (0.8768) |
| `contrast_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.3` (0.9153), `0.5` (0.9153), `0.4` (0.9153) |
| `epsilon_max_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.03` (0.9153), `0.06` (0.9153), `0.04` (0.9153) |
| `minimum_contour_area_fraction` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.9153), `0.18` (0.9153), `0.12` (0.9153) |
| `minimum_rectangularity` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.9153), `0.7` (0.9153), `0.55` (0.9153) |
| `samples_per_edge` | Dormant | 0.0000 | 0.0000 | 100.0% | `24` (0.9153), `72` (0.9153), `48` (0.9153) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`contour_weight`, `polarity_weight`, `contrast_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`, `samples_per_edge`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_polarity_consistency` × `sample_offset_fraction` | 0.9781 | 0.0240 | 6562 |
| `sample_offset_fraction` × `minimum_cross_edge_contrast` | 0.0227 | 0.0073 | 6562 |
| `minimum_polarity_consistency` × `minimum_cross_edge_contrast` | 0.9614 | 0.0073 | 6562 |

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
| Winner | `f4cb24ecb33b` | `f4cb24ecb33b` | 0.1928 | 0.0000 | 0.3855 | 0.9638 | 4 | 1.4s |
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
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile-legacy-workload` | 20 | 19 | 380 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `f4cb24ecb33b` | `f4cb24ecb33b` | 0.9638 | 0.9638 | 0.0000 | +0.7710 | 0.9638 | 4 | 1.9s | 0.95% |
| 2 | `0327dae6227c` | `0327dae6227c` | 0.9638 | 0.9638 | 0.0000 | +0.7710 | 0.9638 | 4 | 2s | 1.04% |
| 3 | `37eccd49586d` | `37eccd49586d` | 0.9638 | 0.9638 | 0.0000 | +0.7710 | 0.9638 | 4 | 3.1s | 2.81% |
| 4 | `2ecf42319231` | `2ecf42319231` | 0.9638 | 0.9638 | 0.0000 | +0.7710 | 0.9638 | 4 | 2.1s | 1.27% |
| 5 | `2c6172dd6e94` | `2c6172dd6e94` | 0.9638 | 0.9638 | 0.0000 | +0.7710 | 0.9638 | 4 | 3s | 2.71% |

## Page Analysis — edge_contour

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `f4cb24ecb33b` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 5 | `f4cb24ecb33b` | 0.8618 | 0.0000 | -0.8618 | No polygon found |
| 6 | `f4cb24ecb33b` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `f4cb24ecb33b` | 0.9638 | 0.9638 | +0.0000 | Unchanged |
| 10 | `f4cb24ecb33b` | 0.8703 | 0.0000 | -0.8703 | No polygon found |

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
- No polygon found: `4`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `2`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 1 | `f4cb24ecb33b` | 0.0000 | No polygon found |
| 5 | `f4cb24ecb33b` | 0.0000 | No polygon found; Regressed |
| 6 | `f4cb24ecb33b` | 0.0000 | No polygon found |
| 10 | `f4cb24ecb33b` | 0.0000 | No polygon found; Regressed |

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

- Recommended parameter set: `f4cb24ecb33b`
- Recommended parameter short name: `f4cb24ecb33b`
- Best observed Avg IoU: `0.1928`
- Avg IoU Success: `0.9638`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3855`
- Calibration evidence: `Medium`
- Dormant parameters: `edge_support_dilation_fraction, angle_weight, area_weight, close_iterations, close_kernel_fraction, epsilon_min_fraction, epsilon_steps, merge_fragmented_contours, rectangularity_weight, edge_support_weight, epsilon_max_fraction, minimum_contour_area_fraction, minimum_rectangularity`
- Available domain spaces: `exhaustive, low_plus, moderate_plus, non_dormant`

### Calibration Analysis

All conclusions are specific to the evaluated Golden Set and configured parameter grid.

#### Detector Summary

- The detector has a measurable but not singular near-best coverage (basin) within the evaluated grid.
- 13 of 17 measured parameters were dormant and may be omitted from a source-specific follow-up search.
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
| Best Avg IoU | 0.9638 |
| Minimum Avg IoU | 0.0000 |
| Avg IoU StdDev | 0.1763 |
| Winner stabilized after | 125 parameter sets |
| Winner stabilized | 1.9s (1% of search) |
| Near-best coverage (basin; within 0.0010) | 3645 (27.8%) |
| Equivalent-best configurations (within 0.0001) | 3645 (27.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 13123 | 100.0% | 5h 13m 43s | 1.0× |
| Non-dormant | 54 | 0.4% | 1m 17s | 243.0× |
| Low+ | 54 | 0.4% | 1m 17s | 243.0× |
| Moderate+ | 9 | 0.1% | 12.9s | 1458.1× |
| Important+ | 0 | 0.0% | 0 ms | unavailable |
| Critical | 0 | 0.0% | 0 ms | unavailable |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `lsd_scale` | Moderate | 0.0537 | 0.0881 | 100.0% | `0.8` (0.9140), `0.6` (0.9110), `1` (0.8259) |
| `minimum_segment_length_fraction` | Moderate | 0.0301 | 0.0650 | 100.0% | `0.03` (0.9054), `0.06` (0.9051), `0.1` (0.8404) |
| `lsd_refine_mode` | Low | 0.0284 | 0.0595 | 100.0% | `none` (0.9133), `std` (0.8539) |
| `minimum_edge_support` | Low | 0.0038 | 0.0263 | 100.0% | `0.05` (0.8953), `0.12` (0.8865), `0.2` (0.8690) |
| `edge_support_dilation_fraction` | Dormant | 0.0007 | 0.0104 | 100.0% | `0.01` (0.8874), `0.003` (0.8864), `0.006` (0.8770) |
| `angle_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.2` (0.8986) |
| `area_weight` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.25` (0.8986) |
| `close_iterations` | Dormant | 0.0000 | 0.0000 | 0.0% | `1` (0.8986) |
| `close_kernel_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.8986) |
| `epsilon_min_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.008` (0.8986) |
| `epsilon_steps` | Dormant | 0.0000 | 0.0000 | 0.0% | `9` (0.8986) |
| `merge_fragmented_contours` | Dormant | 0.0000 | 0.0000 | 0.0% | `true` (0.8986) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`edge_support_dilation_fraction`, `angle_weight`, `area_weight`, `close_iterations`, `close_kernel_fraction`, `epsilon_min_fraction`, `epsilon_steps`, `merge_fragmented_contours`, `rectangularity_weight`, `edge_support_weight`, `epsilon_max_fraction`, `minimum_contour_area_fraction`, `minimum_rectangularity`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `lsd_scale` × `minimum_segment_length_fraction` | 0.1688 | 0.1152 | 13123 |
| `lsd_scale` × `lsd_refine_mode` | 0.1444 | 0.0907 | 13123 |
| `minimum_segment_length_fraction` × `lsd_refine_mode` | 0.0986 | 0.0685 | 13123 |
| `lsd_scale` × `minimum_edge_support` | 0.1142 | 0.0606 | 13123 |
| `minimum_segment_length_fraction` × `minimum_edge_support` | 0.0691 | 0.0390 | 13123 |

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

- Run ID: `run-20260811-001607`
- Detector: `grabcut`
- Strategy: `exhaustive`
- Pipeline commit: `6d781d53e399`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-11T00:16:07.218440+00:00`
- Finished: `2026-08-11T00:22:07.869378+00:00`
- Wall-clock elapsed: `6m 1s`
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

## Results — grabcut

### Result

| Result | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Avg IoU Success | Failures | Evaluation Time |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Winner | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 59.2s |

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

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000445` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `018d128420cb` | `baseline` | 0.8130 | 0.5532 | 0.1692 | +0.0000 | 0.8130 | 0 | unknown | unknown |
| 2 | `71c8fb00da00` | `71c8fb00da00` | 0.7443 | 0.3729 | 0.2583 | -0.0688 | 0.7443 | 0 | 4m 44s | 55.56% |
| 3 | `c4569ce5ec31` | `c4569ce5ec31` | 0.7443 | 0.3729 | 0.2583 | -0.0688 | 0.7443 | 0 | 4m 48s | 66.67% |
| 4 | `f5a2acd172d1` | `f5a2acd172d1` | 0.7409 | 0.3560 | 0.2633 | -0.0721 | 0.7409 | 0 | 5m 25s | 77.78% |
| 5 | `5a4694bf2661` | `5a4694bf2661` | 0.7409 | 0.3560 | 0.2633 | -0.0721 | 0.7409 | 0 | 5m 29s | 88.89% |

## Page Analysis — grabcut

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
Search completed in **6m 1s** wall-clock time.

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

## Calibration Intelligence — grabcut

This run generated the same machine-readable calibration intelligence used by the multi-detector smoke regression. The conclusions remain specific to this Golden Set and configured parameter grid.

### Calibration Identity

- Calibration run ID: `run-20260811-001607`
- Calibration schema: `1.1`
- Detector: `grabcut`
- Detector configuration: `hth-pipeline/config/detectors/grabcut.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `6d781d53e3995fb245164310fe370bd3ffa552b5`
- Source commit: `76fd2515c40813be0fd36d1e32d8b6ad48c5cf13`
- Requested search strategy: `exhaustive`
- Resolved search strategy: `exhaustive`
- Strategy fallback: `none`
- Configured threads: `2`

### Detector-Selection Intelligence

- Recommended parameter set: `018d128420cb`
- Recommended parameter short name: `baseline`
- Best observed Avg IoU: `0.8130`
- Avg IoU Success: `0.8130`
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
| Est. serial runtime for full parameter set evaluation* | 8d 23h 46m |
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
| Exhaustive | 13122 | 100.0% | 8d 23h 55m 52s | 1.0× |
| Non-dormant | 576 | 4.4% | 9h 28m 42s | 22.8× |
| Low+ | 576 | 4.4% | 9h 28m 42s | 22.8× |
| Moderate+ | 576 | 4.4% | 9h 28m 42s | 22.8× |
| Important+ | 576 | 4.4% | 9h 28m 42s | 22.8× |
| Critical | 192 | 1.5% | 3h 9m 34s | 68.3× |

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

## Run Information — grabcut_contour

### Build Provenance

- Run ID: `run-20260811-001607`
- Detector: `grabcut_contour`
- Strategy: `exhaustive`
- Pipeline commit: `6d781d53e399`
- Python: `3.12.13`
- OpenCV: `5.0.0`
- Started: `2026-08-11T00:16:07.223218+00:00`
- Finished: `2026-08-11T00:20:02.741263+00:00`
- Wall-clock elapsed: `3m 56s`
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
| Winner | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | 0.8130 | 0 | 1m 4s |

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
| `auto` | 4 | 2 | 8 | `GitHub Actions 1000000445` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `3817f226228a` | `baseline` | 0.8130 | 0.5532 | 0.1692 | +0.0000 | 0.8130 | 0 | unknown | unknown |
| 2 | `2a39748afbe3` | `2a39748afbe3` | 0.8011 | 0.5492 | 0.1867 | -0.0119 | 0.8011 | 0 | 2m 17s | 44.44% |
| 3 | `ea911909ef98` | `ea911909ef98` | 0.8011 | 0.5492 | 0.1867 | -0.0119 | 0.8011 | 0 | 2m 14s | 33.33% |
| 4 | `47e727acc335` | `47e727acc335` | 0.8010 | 0.5486 | 0.1869 | -0.0120 | 0.8010 | 0 | 2m 50s | 55.56% |
| 5 | `8a86732de560` | `8a86732de560` | 0.8010 | 0.5486 | 0.1869 | -0.0120 | 0.8010 | 0 | 2m 56s | 66.67% |

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
Search completed in **3m 56s** wall-clock time.

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

- Calibration run ID: `run-20260811-001607`
- Calibration schema: `1.1`
- Detector: `grabcut_contour`
- Detector configuration: `hth-pipeline/config/detectors/grabcut_contour.json`
- Golden Set configuration: `hth-pipeline/config/golden_set.json`
- Golden Set SHA-256: `135c0ff576876ef8911296e2502193ed20d159799079a4f8a58994854fcbba8e`
- Pipeline commit: `6d781d53e3995fb245164310fe370bd3ffa552b5`
- Source commit: `76fd2515c40813be0fd36d1e32d8b6ad48c5cf13`
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
| Est. serial runtime for full parameter set evaluation* | 261d 4h 19m 44s |
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
| Exhaustive | 354295 | 100.0% | 261d 4h 30m 21s | 1.0× |
| Non-dormant | 6144 | 1.7% | 4d 12h 42m 19s | 57.7× |
| Low+ | 6144 | 1.7% | 4d 12h 42m 19s | 57.7× |
| Moderate+ | 6144 | 1.7% | 4d 12h 42m 19s | 57.7× |
| Important+ | 3072 | 0.9% | 2d 6h 21m 9s | 115.3× |
| Critical | 512 | 0.1% | 9h 3m 32s | 692.0× |

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
| Winner | `dfbdcf4e5b70` | `dfbdcf4e5b70` | 0.7746 | 0.0000 | 0.3875 | 0.9683 | 1 | 178 ms |
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
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `preferred-hardware-profile-legacy-workload` | 9 | 42 | 378 | `rh8-al318` | 384 |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `dfbdcf4e5b70` | `dfbdcf4e5b70` | 0.9683 | 0.9611 | 0.0119 | +0.1937 | 0.9683 | 1 | 4.5s | 78.62% |
| 2 | `6969414c18d3` | `6969414c18d3` | 0.9683 | 0.9611 | 0.0119 | +0.1937 | 0.9683 | 1 | 4.7s | 82.14% |
| 3 | `e395ec80ac85` | `e395ec80ac85` | 0.9683 | 0.9611 | 0.0119 | +0.1937 | 0.9683 | 1 | 4.7s | 81.88% |
| 4 | `d65d872b74ef` | `d65d872b74ef` | 0.9683 | 0.9611 | 0.0119 | +0.1937 | 0.9683 | 1 | 4.8s | 84.32% |
| 5 | `5d03636ee3a1` | `5d03636ee3a1` | 0.9683 | 0.9611 | 0.0119 | +0.1937 | 0.9683 | 1 | 4.7s | 82.88% |

## Page Analysis — gradient_vote

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `dfbdcf4e5b70` | 0.9613 | 0.9618 | +0.0005 | Unchanged |
| 5 | `dfbdcf4e5b70` | 0.5684 | 0.0000 | -0.5684 | No polygon found |
| 6 | `dfbdcf4e5b70` | 0.9889 | 0.9889 | +0.0000 | Unchanged |
| 9 | `dfbdcf4e5b70` | 0.9612 | 0.9612 | +0.0000 | Unchanged |
| 10 | `dfbdcf4e5b70` | 0.9611 | 0.9611 | +0.0000 | Unchanged |

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
- No polygon found: `1`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 5 | `dfbdcf4e5b70` | 0.0000 | No polygon found; Regressed |

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

- Recommended parameter set: `dfbdcf4e5b70`
- Recommended parameter short name: `dfbdcf4e5b70`
- Best observed Avg IoU: `0.7746`
- Avg IoU Success: `0.9683`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.3875`
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
| Best Avg IoU | 0.9683 |
| Minimum Avg IoU | 0.8419 |
| Avg IoU StdDev | 0.0329 |
| Winner stabilized after | 5158 parameter sets |
| Winner stabilized | 4.5s (79% of search) |
| Near-best coverage (basin; within 0.0010) | 729 (11.1%) |
| Equivalent-best configurations (within 0.0001) | 54 (0.8%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 6562 | 100.0% | 19m 26s | 1.0× |
| Non-dormant | 243 | 3.7% | 43.2s | 27.0× |
| Low+ | 243 | 3.7% | 43.2s | 27.0× |
| Moderate+ | 9 | 0.1% | 1.6s | 729.1× |
| Important+ | 3 | 0.0% | 533 ms | 2187.3× |
| Critical | 3 | 0.0% | 533 ms | 2187.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, broad near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `minimum_span_fraction` | Critical | 0.5315 | 0.0510 | 33.3% | `0.55` (0.9462), `0.35` (0.8953), `0.45` (0.8953) |
| `gaussian_sigma` | Moderate | 0.0430 | 0.0149 | 66.7% | `1.8` (0.9175), `1.2` (0.9166), `0.8` (0.9026) |
| `border_search_fraction` | Low | 0.0248 | 0.0126 | 66.7% | `0.35` (0.9191), `0.42` (0.9111), `0.47` (0.9066) |
| `central_band_fraction` | Low | 0.0192 | 0.0099 | 100.0% | `1` (0.9157), `0.86` (0.9153), `0.7` (0.9058) |
| `vote_smooth_fraction` | Low | 0.0011 | 0.0024 | 100.0% | `0.006` (0.9138), `0.012` (0.9116), `0.02` (0.9114) |
| `area_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.25` (0.8882) |
| `minimum_area_fraction` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `rectangularity_weight` | Dormant | 0.0001 | 0.0000 | 0.0% | `0.2` (0.8882) |
| `gradient_percentile` | Dormant | 0.0000 | 0.0000 | 100.0% | `70` (0.9123), `90` (0.9123), `82` (0.9123) |
| `minimum_vote_support` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.08` (0.9123), `0.25` (0.9123), `0.16` (0.9123) |
| `support_weight` | Dormant | 0.0000 | 0.0000 | 100.0% | `0.45` (0.9123), `0.65` (0.9123), `0.55` (0.9123) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`area_weight`, `minimum_area_fraction`, `rectangularity_weight`, `gradient_percentile`, `minimum_vote_support`, `support_weight`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `minimum_span_fraction` × `border_search_fraction` | 0.8314 | 0.2999 | 6562 |
| `gaussian_sigma` × `central_band_fraction` | 0.0956 | 0.0526 | 6562 |
| `minimum_span_fraction` × `gaussian_sigma` | 0.5805 | 0.0490 | 6562 |
| `gaussian_sigma` × `border_search_fraction` | 0.0687 | 0.0257 | 6562 |
| `minimum_span_fraction` × `central_band_fraction` | 0.5510 | 0.0196 | 6562 |

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
| Winner | `07a0b3ac190f` | `07a0b3ac190f` | 0.5013 | 0.0000 | 0.4095 | 0.8355 | 2 | 1.7s |
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
| Baseline surpassed | no |

### Preferred Execution Shape

The regression execution shape selected for this detector run is recorded here so the calibration result can be interpreted without returning to build provenance.

| Source | Pipelines | Threads / pipeline | Allocated | Runner | Runner budget |
|---|---:|---:|---:|---|---:|
| `unknown (legacy record)` | 2 | 8 | 16 | `rh8-al319` | unknown |

### Top Parameter Sets

| Rank | Parameter Set ID | Parameter Short Name | Avg IoU | Min IoU | StdDev | Δ Avg IoU | Avg IoU Success | Failures | Discovery Time | Search Space % |
|---:|---|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | `07a0b3ac190f` | `07a0b3ac190f` | 0.8355 | 0.8198 | 0.0137 | +0.3342 | 0.8355 | 2 | 7.5s | 2.61% |
| 2 | `fed31080e222` | `fed31080e222` | 0.8350 | 0.8238 | 0.0114 | +0.3337 | 0.8350 | 2 | 25.9s | 12.53% |
| 3 | `db0ff8ba80f9` | `db0ff8ba80f9` | 0.8348 | 0.8198 | 0.0128 | +0.3335 | 0.8348 | 2 | 8.8s | 2.97% |
| 4 | `a909d18a793c` | `a909d18a793c` | 0.8344 | 0.8136 | 0.0208 | +0.3331 | 0.8344 | 3 | 2m 39s | 86.05% |
| 5 | `d3611ac4b698` | `d3611ac4b698` | 0.8344 | 0.8136 | 0.0208 | +0.3331 | 0.8344 | 3 | 2m 37s | 84.87% |

## Page Analysis — hough

### Golden Set Winner Summary

| Golden Set Page | Parameter Set ID | Baseline | Winner | Δ IoU | Status |
|---:|---|---:|---:|---:|---|
| 1 | `07a0b3ac190f` | 0.6261 | 0.8532 | +0.2271 | Improved |
| 5 | `07a0b3ac190f` | 0.3071 | 0.0000 | -0.3071 | No polygon found |
| 6 | `07a0b3ac190f` | 0.0000 | 0.0000 | +0.0000 | No polygon found |
| 9 | `07a0b3ac190f` | 0.7370 | 0.8198 | +0.0829 | Improved |
| 10 | `07a0b3ac190f` | 0.7221 | 0.8335 | +0.1114 | Improved |

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
- No polygon found: `2`
- Zero overlap: `0`
- Poor matches (Winner IoU < 0.5000): `0`
- Regressed pages (Δ IoU < -0.0010): `1`

#### Affected Pages

| Golden Set Page | Parameter Set ID | Winner IoU | Problem |
|---:|---|---:|---|
| 5 | `07a0b3ac190f` | 0.0000 | No polygon found; Regressed |
| 6 | `07a0b3ac190f` | 0.0000 | No polygon found |

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

- Recommended parameter set: `07a0b3ac190f`
- Recommended parameter short name: `07a0b3ac190f`
- Best observed Avg IoU: `0.5013`
- Avg IoU Success: `0.8355`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4095`
- Calibration evidence: `Medium`
- Dormant parameters: `hough_threshold_fraction, minimum_bbox_area_fraction`
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
| Best Avg IoU | 0.8355 |
| Minimum Avg IoU | 0.2981 |
| Avg IoU StdDev | 0.1270 |
| Winner stabilized after | 57 parameter sets |
| Winner stabilized | 7.5s (3% of search) |
| Near-best coverage (basin; within 0.0010) | 3 (0.1%) |
| Equivalent-best configurations (within 0.0001) | 1 (0.0%) |
| Calibration Evidence | Medium |

\* **Serial-runtime note:** Long parameter-set estimates assume a single-threaded serial run at the measured detector page rate. Actual wall time varies with parallelization, worker count, scheduling overhead, and parameter-dependent runtime.

#### Parameter Set Domain Space Reduction

| Effect Size Group | Parameter Sets | % All Sets | New Time Est* | Set Reduction Factor |
|---|---:|---:|---:|---:|
| Exhaustive | 2188 | 100.0% | 1h 1m 44s | 1.0× |
| Non-dormant | 729 | 33.3% | 20m 34s | 3.0× |
| Low+ | 729 | 33.3% | 20m 34s | 3.0× |
| Moderate+ | 9 | 0.4% | 15.2s | 243.1× |
| Important+ | 3 | 0.1% | 5.1s | 729.3× |
| Critical | 3 | 0.1% | 5.1s | 729.3× |

\* Uses the same serial measured-page-rate assumptions as the Calibration Landscape serial-runtime estimate.

Calibration evidence basis: complete exhaustive coverage, many parameter sets failed at least one page, narrow near-best basin.

#### Parameter Influence

Influence uses one-way η² over Avg IoU. It measures association within this configured grid; it does not establish causation.

| Parameter | Classification | η² | Avg-IoU range | Near-best value coverage | Best observed values |
|---|---|---:|---:|---:|---|
| `outer_percentile` | Critical | 0.7563 | 0.2624 | 33.3% | `5` (0.7257), `10` (0.6515), `20` (0.4633) |
| `maximum_gap_fraction` | Moderate | 0.0406 | 0.0617 | 66.7% | `0.09` (0.6412), `0.055` (0.6199), `0.025` (0.5795) |
| `canny_low_threshold` | Low | 0.0300 | 0.0524 | 33.3% | `65` (0.6362), `25` (0.6207), `40` (0.5838) |
| `minimum_length_fraction` | Low | 0.0142 | 0.0370 | 33.3% | `0.12` (0.6313), `0.2` (0.6151), `0.3` (0.5943) |
| `bbox_padding_fraction` | Low | 0.0032 | 0.0175 | 33.3% | `0.015` (0.6226), `0.005` (0.6129), `0` (0.6051) |
| `axis_angle_tolerance_degrees` | Low | 0.0018 | 0.0130 | 66.7% | `12` (0.6194), `22` (0.6148), `32` (0.6064) |
| `hough_threshold_fraction` | Dormant | 0.0007 | 0.0072 | 66.7% | `0.08` (0.6182), `0.035` (0.6114), `0.055` (0.6110) |
| `minimum_bbox_area_fraction` | Dormant | 0.0000 | 0.0000 | 0.0% | `0.1` (0.5981) |

#### Dormant Parameters

These parameters had no material measured effect on Avg IoU for this Golden Set and grid:

`hough_threshold_fraction`, `minimum_bbox_area_fraction`.

Dormant parameters may be omitted from future searches for this Golden Set, but should be re-evaluated when the Golden Set changes.

#### Parameter Interactions

Pairwise interaction importance is exploratory and estimated from a deterministic sample.

| Parameters | Pair η² | Incremental importance | Sample size |
|---|---:|---:|---:|
| `outer_percentile` × `maximum_gap_fraction` | 0.7997 | 0.0434 | 2188 |
| `maximum_gap_fraction` × `canny_low_threshold` | 0.0818 | 0.0412 | 2188 |
| `outer_percentile` × `canny_low_threshold` | 0.7906 | 0.0343 | 2188 |
| `canny_low_threshold` × `minimum_length_fraction` | 0.0497 | 0.0198 | 2188 |
| `maximum_gap_fraction` × `minimum_length_fraction` | 0.0595 | 0.0189 | 2188 |

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
| Winner | `7546c5067527` | `7546c5067527` | 0.5902 | 0.0000 | 0.4448 | 0.7378 | 1 | 379 ms |
| Baseline | `b2df04f4e947` | `baseline` | 0.3248 | 0.0000 | 0.4341 | 0.5414 | 2 | 333 ms |

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
| 1 | `7546c5067527` | `7546c5067527` | 0.7378 | 0.0000 | 0.3721 | +0.1476 | 0.7378 | 1 | 7.9s | 18.57% |
| 2 | `05a653fabdd0` | `05a653fabdd0` | 0.7378 | 0.0000 | 0.3721 | +0.1476 | 0.7378 | 1 | 8.1s | 18.76% |
| 3 | `497528ffc236` | `497528ffc236` | 0.7378 | 0.0000 | 0.3721 | +0.1476 | 0.7378 | 1 | 8.2s | 18.89% |
| 4 | `24a5a18c61f3` | `24a5a18c61f3` | 0.7378 | 0.0000 | 0.3721 | +0.1476 | 0.7378 | 1 | 8.7s | 19.76% |
| 5 | `97f5383e66cd` | `97f5383e66cd` | 0.7378 | 0.0000 | 0.3721 | +0.1476 | 0.7378 | 1 | 8.7s | 19.99% |

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
- Best observed Avg IoU: `0.5902`
- Avg IoU Success: `0.7378`
- Worst Golden Set page (Min IoU): `0.0000`
- Page-to-page StdDev: `0.4448`
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
| Baseline | `d593fad7aeea` | `baseline` | 0.9503 | 0.9340 | 0.0145 | 0.9503 | 0 | 52 ms |

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
| Baseline | `7e367fe3bfd5` | `baseline` | 0.5465 | 0.0000 | 0.4365 | 0.6831 | 1 | 42 ms |

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
- Results commit: [f79bfb107b2c16d9e2ee041a7be3669bd4cb39a9](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/commit/f79bfb107b2c16d9e2ee041a7be3669bd4cb39a9).
- Workflow run: [Open workflow run](https://github.com/dlstupka/hth/actions/runs/31446837015).
- Pipeline repository: [dlstupka/hth](https://github.com/dlstupka/hth).
- Results repository: [dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results).
- Calibration index: [calibration-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/f79bfb107b2c16d9e2ee041a7be3669bd4cb39a9/calibration-index.json).
- Runtime index: [runtime-index.json](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898-results/blob/f79bfb107b2c16d9e2ee041a7be3669bd4cb39a9/runtime-index.json).
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