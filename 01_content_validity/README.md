# Phase 5a — Content Validity (CVI)

Nine independent experts rated the 94 platform-neutral checkpoints in Stages 2–4
on three criteria: **relevance** (4-point), **clarity** (4-point), and
**essentiality** (E/U/N). This script computes the content-validity indices from
those ratings.

## Outputs
- **I-CVI** — item-level content validity index (relevance, clarity)
- **S-CVI/Ave** and **S-CVI/UA** — scale-level (averaging and universal-agreement)
- **modified kappa (κ\*)** — chance-corrected agreement (Polit, Beck & Owen 2007)
- **CVR** — content validity ratio (Lawshe 1975), reported descriptively
- a per-item results CSV

## Run
```bash
python cvi_analysis.py --input <ratings_dir> --out results_cvi.csv
```
`<ratings_dir>` holds one `.xlsx` per expert. Rater identity is assigned from
file order (`rater_01`, `rater_02`, …), so no personal names enter the output.

Each workbook has a `평정폼` sheet with columns:
`No | Stage | Dimension | Sub-dimension | Checkpoint(EN) | Checkpoint(KR) | Relevance | Clarity | Essentiality | Comment`.
Relevance/Clarity ratings of 3–4 are treated as endorsement.

## References
Lynn (1986); Lawshe (1975); Polit & Beck (2006); Polit, Beck & Owen (2007).
