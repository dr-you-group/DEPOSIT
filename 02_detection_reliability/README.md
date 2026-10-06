# Phase 5b — Detection & Inter-Rater Reliability

Raters independently apply the Stage 2–4 checkpoints to three synthetic K-BDS
submission files that contain **known, seeded defects**, judging each checkpoint
per file as pass / fail / not-applicable and recording evidence for failures.
The script scores detection sensitivity against the answer key and computes
inter-rater agreement.

## Contents
| File | Description |
|------|-------------|
| `detection_reliability.py` | Detection + reliability analysis (Fleiss' κ, Gwet's AC1, bootstrap CIs) |
| `generate_dataset.py` | Script that builds the synthetic dataset and seeds the defects |
| `dataset/` | The three synthetic submission files (see below) |
| `seeded_defects_answer_key.csv` | Ground-truth list of seeded defects |
| `rater_response_template.csv` | Blank response layout |

## The three data types
The dataset uses the original K-BDS submission-form types:

| File | K-BDS type | Data type |
|------|-----------|-----------|
| `KBI_MR_metadata.xlsx` | KBI | Medical imaging (MRI) |
| `KRA_metadata.xlsx` | KRA | Genomic (NGS) |
| `GeNA_metadata.xlsx` | GeNA | Clinical / other health data |

The three files share 30 linked subjects, so the same individual appears across
data types. 27 defects are seeded (17 de-identification, 5 quality, 5
standardization), plus 3 trap values (legitimate pseudonyms that should **not**
be flagged).

## Run
```bash
python detection_reliability.py \
    --responses <responses_dir> \
    --answer-key seeded_defects_answer_key.csv \
    --files KBI,KRA,GeNA
```
`<responses_dir>` holds one `.xlsx` per rater; identity is assigned by file
order (`rater_01`, …). Detection is scored at the defect level (a defect counts
as detected if any rater identifies it in their written evidence).

## Answer-key columns
`defect_id, file, stage, checklist_item_id, field, excel_cell, defect_type,
difficulty, is_trap, description, seeded_value, signature`
— `signature` is a regex matched against a rater's evidence text; `is_trap`
marks the trap rows (excluded from detection scoring).

## Data statement
**All data are synthetic.** Every identifier-like value is fabricated and seeded
as a defect; none are real personal data.

## References
Gwet (2008); Kottner et al. (2011, GRRAS).
