# HTH-0001 Canonical Normalization

> Canonical complete collection normalization. Axis-aligned framing with conservative Hough deskew on pages that pass every safety gate. Gross page orientation is preserved.

## Result

- Status: `complete`
- Policy: `axis-aligned-detector-envelope-v1+hough-lines-conservative-v1`
- Pages normalized: `929`
- Detector evidence: `doc_ufcn_page_mask` / `97a2ae7f3db4`
- Canonical preprocess build: `555e935db9df90c0ea451622dee8f597a11e6ffc190cf34d73a06ea547b379b5`
- Canonical preprocess result: `ecf8f0d3a4746c7c83adc9bd786aca10740a4478114271f706402c24a7539c4f`
- Normalization identity: `7b955c1d7582c4db2a2d613d9100579c2f7851cd817331a35dab209122830ef9`
- Canonical normalization result: `d0fb2998d1cfcef91f6c6469ff9223184243aedebb85bf1746ab13b8c1d26e80`
- Pages conservatively deskewed: `12`
- Pages preserved without resampling: `917`

## Review artifact

Download and extract the review artifact, then open `index.html` locally. The red rectangle is the exact half-open crop boundary; the normalized panel shows the final policy output.
