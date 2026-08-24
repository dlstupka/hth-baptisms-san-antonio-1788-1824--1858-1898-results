# HTH — San Antonio Baptisms 1788–1824, 1858–1898 — Results

This repository contains the persistent **analysis, calibration, preprocessing, and research outputs** produced by the [Hidden Texas History (HTH)](https://github.com/dlstupka/hth) framework for the **San Antonio Baptism Records, 1788–1824 and 1858–1898** collection.

It is intentionally separate from both the HTH software repository and the archival source repository. This separation preserves the distinction between **source evidence**, **software and methodology**, and **derived research results**.

## Related repositories

### HTH framework

**[dlstupka/hth](https://github.com/dlstupka/hth)**

The HTH source/development repository contains the processing framework, document detectors, calibration and regression infrastructure, execution optimizer, workflows, tests, documentation, and research tooling used to produce and validate the material stored here.

HTH is designed to turn difficult archival source material into reproducible, reviewable research evidence while preserving source identity and provenance.

### Archival source collection

**[dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898](https://github.com/dlstupka/hth-baptisms-san-antonio-1788-1824--1858-1898)**

This is the source repository for the collection analyzed here.

The archival images themselves are maintained independently from these derived results so that processing and research outputs can always be traced back to an identifiable source collection and source revision.

## Purpose of this repository

HTH treats generated research evidence as something worth preserving rather than as disposable build output.

This repository therefore serves as the persistent record of processing and analysis performed against the collection. Depending on the stage of research, it contains material including:

- document and physical-page analysis;
- detector calibration and regression evidence;
- learned-detector evidence;
- execution-optimizer and parallelism results;
- parameter provenance and calibration intelligence;
- production preprocessing outputs and metadata;
- test and validation results;
- reports and review material;
- OCR and future transcription outputs;
- translations, indexes, citations, and research notes as those stages mature.

Machine-generated results are committed here by HTH workflows so that important calibration and research history survives individual workflow runs.

## Repository organization

| Path | Purpose |
| --- | --- |
| `analysis/` | Production document/page analysis and derived review material |
| `citations/` | Citation outputs and supporting data |
| `execution-optimizer/` | Detector execution-optimization results |
| `indexes/` | Generated research and processing indexes |
| `learned-evidence/` | Persisted evidence from learned/model-backed detectors |
| `metadata/` | Collection and production metadata |
| `models/` | Model-related processing evidence and results |
| `ocr/` | OCR outputs |
| `reports/` | Human-readable calibration, regression, and processing reports |
| `research-notes/` | Research notes associated with the collection |
| `source-documents/` | Source-document-specific calibration and analysis intelligence |
| `test/` | Test/preprocessing and validation results kept separate from production |
| `transcriptions/` | Transcription outputs |
| `translations/` | Translation outputs |

Top-level indexes provide machine-readable entry points into persisted HTH intelligence, including calibration, detector, optimizer, parallelism, parameter-provenance, and runtime information.

## Provenance model

The three repositories have deliberately different responsibilities:

```text
archival source repository
        ↓
 immutable source release + manifest + SHA-256 identity
        ↓
       HTH
 software + detectors + calibration + processing methodology
        ↓
 this results repository
 analysis + calibration intelligence + production/research outputs
