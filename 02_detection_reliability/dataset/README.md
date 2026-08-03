# Synthetic evaluation dataset

Three synthetic K-BDS submission files with 30 linked subjects and 27 seeded
defects (+3 traps), used in Phase 5b.

| File | K-BDS type | Data type |
|------|-----------|-----------|
| `KBI_MR_metadata.xlsx` | KBI | Medical imaging (MRI) |
| `KRA_metadata.xlsx` | KRA | Genomic (NGS) |
| `GeNA_metadata.xlsx` | GeNA | Clinical / other |

Regenerate with `../generate_dataset.py`. Ground truth is in
`../seeded_defects_answer_key.csv`.

**All values are synthetic — no real personal data.**
