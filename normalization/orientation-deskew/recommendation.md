## Normalization recommendation

**Recommended for a validation run:** Keep every page in its existing gross orientation and straighten only clearly tilted pages using conservative line evidence.

- Suggested policy: `hough-lines-conservative-v1`
- Gross page orientation: preserve as-is
- Expected sample impact: `8` of `79` sampled pages
- Activation: a researcher must explicitly choose the recommended policy when starting normalization

### Automated evidence checks

- Passed: `sample_size`
- Passed: `hough_mean_confidence`
- Passed: `hough_confidence_advantage`
- Passed: `hough_not_boundary_limited`
- Passed: `observed_corrections_within_policy_bound`

The evidence and machine-readable policy were preserved automatically. The run artifact adds contact sheets for optional visual review; no production pixels were changed.

**Next step:** review the recommendation, then start collection normalization. Its default prepared-recommendation option is the explicit approval to apply this policy; choose axis-aligned-only to preserve cropped pixels.
