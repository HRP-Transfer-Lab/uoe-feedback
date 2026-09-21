# PNS Research Proposal — Grading from Calibrated Competence Scores

Version 1.1 | 21 September 2026

## Status and scope

This method adapts the RDM calibrated competence approach for the Psychobiology & Neuroscience Research Proposal Report.

Sequence:

**assess competences independently → calibrate across the cohort → calculate normalised criterion totals → apply University criterion weights → calculate the weighted competence distribution → derive one common cohort conversion → convert each criterion → calculate the weighted overall → round for reporting → apply any word-count penalty separately.**

The conversion is an explicit cohort-calibration procedure chosen for this assignment. It is not a University of Essex Online requirement and must not be described as one.

## 1. Assignment configuration

Current PNS July 2026 configuration:

- Stage 1 codes: 0, 0.5, 1
- Target unrounded cohort mean: **M = 67**
- Target population SD: **S = 10**
- Conversion mode: mean-and-SD affine conversion
- Criterion weights:
  - C1 Knowledge and Understanding: 20%
  - C2 Research Methodology and Appropriate Implementation: 20%
  - C3 Ethical Considerations: 20%
  - C4 Criticality: 10%
  - C5 Academic Integrity: 10%
  - C6 Use of Relevant Sources: 10%
  - C7 Structure and Presentation: 10%
- Equal subcriterion weighting within each parent criterion
- Whole-number reporting
- Word-count penalty handled only after academic grading and conversion

If cohort membership, target mean, target SD, criterion weights or calibrated Stage 1 scores change, recalculate the complete conversion.

## 2. Score and calibrate subcriteria

For student i, criterion c and subcriterion j, record x_icj as 1, 0.5 or 0 according to grading_criteria.md.

Score all submissions independently before inspecting the final grade distribution. Then compare papers receiving different scores on each subcriterion and check consistency.

Revise only evidence-based scoring inconsistencies. Do not change Stage 1 codes merely to obtain the desired cohort mean or SD. Freeze the calibrated Stage 1 matrix before conversion.

## 3. Calculate criterion proportions

For each criterion c with n_c equally weighted subcriteria:

T_ic = sum_j(x_icj)

C_ic = T_ic / n_c

Where T_ic is the raw criterion total and C_ic is the normalised criterion proportion on a 0–1 scale.

PNS maxima:
- C1 = 5
- C2 = 6
- C3 = 5
- C4 = 5
- C5 = 4
- C6 = 5
- C7 = 5

Do not interpret C_ic itself as a percentage grade.

## 4. Calculate the University-weighted competence score

Let W_c be the official criterion weights expressed as decimals.

R_i = sum_c(W_c × C_ic)

For this assignment:

R_i = .20C1 + .20C2 + .20C3 + .10C4 + .10C5 + .10C6 + .10C7

R_i is the student's weighted competence score on a 0–1 scale before conversion.

## 5. Calculate the complete cohort distribution

For N eligible students:

mu_R = sum_i(R_i) / N

sigma_R = sqrt(sum_i((R_i - mu_R)^2) / N)

Use the population SD, denominator N, and use the same cohort throughout scoring, conversion and final rounding.

## 6. Derive one common conversion

Current target:
- M = 67
- S = 10

Derive:

b = S / sigma_R

a = M - b × mu_R

Then define one common affine conversion:

f(q) = a + b × q

equivalently:

f(q) = M + b × (q - mu_R)

The parameters a and b are derived once from the complete cohort's weighted overall competence distribution.

Do not:
- derive a separate conversion for each criterion;
- force every criterion to mean 67;
- independently judge criterion percentages after Stage 1;
- add a second overall uplift.

If sigma_R = 0, a positive target SD cannot be produced without inventing differences. Flag this instead of breaking ties artificially.

## 7. Convert each criterion and calculate the overall

Apply exactly the same conversion to each normalised criterion:

P_ic = a + b × C_ic

Then calculate the unrounded processed overall:

G_i = sum_c(W_c × P_ic)

Because the weights sum to 1:

G_i = a + b × R_i

Before rounding this guarantees:
- the weighted converted criterion grades reconcile exactly with G_i;
- the cohort mean of G_i is 67;
- the cohort population SD of G_i is 10;
- overall ordering and exact ties are preserved;
- individual criteria retain their own cohort means and spreads.

The affine conversion preserves the shape of the weighted competence distribution; it does not force normality.

## 7A. Qualitative consistency check after conversion

After the numerical conversion, compare the resulting profile with the evidence-based narrative. This is a **sanity check only** and must not become a second grading mechanism.

Typical interpretation in the current calibration:
- approximately 74–76: strong Distinction profile, generally excellent with only limited or isolated weaknesses;
- approximately 70–73: Distinction-level overall with at least one material criterion weakness;
- approximately 60–69: Merit profile, coherent and viable but with multiple meaningful limitations;
- approximately 50–59: Pass profile, plausible study but with substantial weaknesses in implementation, evidence, ethics or alignment.

Do not manually move a mark to fit these ranges. If there is a striking mismatch, revisit the underlying Stage 1 codes consistently across comparable papers and then rerun the full cohort conversion.

## 8. Bounds and interpretation

Check all converted criterion and overall grades against 0–100.

Do not silently clip out-of-range values. Clipping would break exact reconciliation and target moments. If bounds fail, review the calibration parameters or agree a constrained alternative.

A converted mark is a cohort-calibrated mapping from the evidence-based competence matrix; it does not itself prove every qualitative feature of a University descriptor.

## 9. Whole-number reporting

Retain full precision throughout.

Criterion grades can be displayed to the nearest whole number.

For final whole-number overall grades while preserving an exact mean of 67, use mean-preserving largest-remainder rounding:

1. Set F_i = floor(G_i)
2. Set r_i = G_i - F_i
3. Set target total T = N × 67
4. Calculate K = T - sum_i(F_i)
5. Round up the K largest remainders
6. Leave the others rounded down
7. Verify sum(H_i) = T and mean(H_i) = 67

For exactly equal remainders use ascending exact participant ID as the reproducible tie-break rule, but flag any case where this would split students with identical underlying grades.

The post-rounding SD can differ slightly from 10; report its actual value.

## 10. Word-count penalty

The assignment carries a 10 grade-point penalty if a submission exceeds 2,200 words.

This is not part of Stage 1 competence scoring and not part of the cohort conversion.

Procedure:
1. Calculate academic Stage 1 codes.
2. Calibrate the matrix.
3. Convert to criterion and overall academic grades.
4. Complete whole-number reporting.
5. Record the academically derived grade.
6. If the submission exceeds 2,200 words, subtract 10 grade points.
7. Record the penalty separately.

Final_after_penalty = max(0, H_i - 10)

The target mean of 67 applies to the academically derived pre-penalty grades. The post-penalty cohort mean may therefore differ from 67.

## 11. Required audit outputs

Retain:
- exact participant ID;
- every original 0 / 0.5 / 1 subcriterion code;
- raw criterion totals;
- normalised criterion proportions;
- official criterion weights;
- weighted competence score R_i;
- cohort mu_R and sigma_R;
- target M = 67 and S = 10;
- affine parameters a and b;
- unrounded converted criterion percentages;
- unrounded overall G_i;
- rounding remainder;
- final pre-penalty whole-number grade H_i;
- word count where reliably available;
- penalty flag;
- final post-penalty grade.

Also retain subcriterion and criterion distribution summaries for calibration review.

## 12. Safeguards

- The 67 mean and SD 10 are explicit assignment-calibration choices, not University requirements.
- Stage 1 scoring must be independent of the desired grade distribution.
- Do not reverse-engineer Stage 1 codes from target marks.
- Do not alter evidence-specific judgements because the conversion produces a surprising mark.
- Do not convert each criterion against its own distribution.
- Do not apply an additional uplift after the affine conversion.
- Do not treat a converted mark as evidence of competence that was not present in the submission.
- The target mean of 67 and target population SD of 10 apply to the **full eligible cohort pre-penalty**, not to each student, criterion or small ad-hoc subset.
- When marking a single paper outside the full cohort, do not invent a local rescaling to force it toward 67. Use the existing calibrated criterion marks/conversion where available, or flag that full cohort conversion is required.
- Before student-facing feedback is finalised, recompute the overall directly from the displayed seven criterion percentages using the official 20/20/20/10/10/10/10 weights as an arithmetic cross-check. The displayed criterion marks and displayed overall should reconcile to rounding tolerance.
- If a manual evidence review changes a criterion mark, recalculate the weighted overall; do not preserve an older total.
