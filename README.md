# DEPOSIT — Phase 5 Validation

Analysis code and materials for the quantitative validation (Phase 5) of the
**DEPOSIT** checklist, a FAIR-based framework that helps researchers self-assess
the de-identification, quality, and standardization readiness of biomedical data
before depositing it in a public repository (instantiated for the Korea BioData
Station, K-BDS).

Validation has two parts:

| Folder | Phase | What it evaluates |
|--------|-------|-------------------|
| [`Phase5a_cvi/`](Phase5a_cvi/) | 5a — Content validity | Whether experts judge the checkpoints relevant, clear, and essential (I-CVI, S-CVI, modified κ, CVR) |
| [`Phase5b_detection_reliability/`](Phase5b_detection_reliability/) | 5b — Detection & reliability | Whether raters using the checklist detect seeded defects, and do so consistently (sensitivity, Fleiss' κ, Gwet's AC1) |

## Setup
```bash
pip install -r requirements.txt
```
Each subfolder has its own README with run instructions.

## Data statement
All evaluation data are **synthetic**. The identifiers in the Phase 5b dataset
and answer key are fabricated values seeded as defects — none are real personal
data. Expert/rater response files are not included, as they contain the names of
individual raters; only the aggregate results are reported.

## Citation
If you use these materials, please cite: *[manuscript citation — to be added]*

## License
Code: MIT. Checklist and synthetic data: CC BY 4.0. See `LICENSE`.
