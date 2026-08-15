# Evaluating Ontology Matching Techniques for Secure by Design Supplier Assurance

This repository contains the reproducibility evidence and evaluation results produced for an MSc project comparing LogMap, AgreementMakerLight (AML) and BERTMap on MOD Secure by Design and SORA supplier-assurance ontologies.

## Evaluation scope

No validated SbD–SORA reference alignment was available. Therefore, precision, recall and F1-score were not reported for this experiment. The matchers were compared using:

- mapping coverage;
- confidence scores;
- cross-matcher agreement;
- repeatability across three runs;
- execution time;
- qualitative assurance-relevance classification.

Generated and supplementary candidate mappings were manually classified as Full, Partial, Weak or Missing.

## Main results

| Matcher | Generated mappings | Mean runtime (s) | Runtime SD (s) |
|---|---:|---:|---:|
| LogMap | 21 | 8.565 | 0.988 |
| AML | 42 | 22.698 | 2.980 |
| BERTMap | 9 | 1080.597 | 186.087 |

All three matchers produced identical final mapping sets across their three runs.

Nine mappings were shared by all three systems: Activity, Component, Data, Organisation, Programme, Risk, Service, Standard and System.

## Repository contents

- `environment/` — software versions, configurations and ontology checksums
- `reproduction_outputs/LogMap/` — repeated LogMap outputs, logs and runtimes
- `reproduction_outputs/AML/` — repeated AML outputs, logs and runtimes
- `reproduction_outputs/BERTMap/` — configurations, metadata, alignments and evaluation evidence
- `evaluation/` — coverage, classification and cross-matcher comparison results
- `logs/` — supporting execution records

## Important limitations

- The supplied SbD and SORA ontology files are intentionally excluded.
- No SbD–SORA gold-standard alignment existed.
- Supplementary reciprocal candidates are review suggestions and are not treated as matcher-generated mappings or recall.
- Matcher confidence scores are not directly comparable probabilities because each system uses a different scoring method.
- Full HermiT integration checking could not be completed for LogMap because a non-simple SbD property occurred in a maximum-cardinality restriction. Matching was repeated with logical-impact checking disabled.
- BERTMap evaluates classes only and its optional LogMap repair stage was skipped.

## Evidence integrity

The repository retains run-level outputs rather than only aggregate results. `SHA256SUMS.txt` records checksums for the included evidence files.

## Author

Olayemi Oseni  
MSc Cyber Security
