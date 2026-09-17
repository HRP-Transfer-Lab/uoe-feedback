# Grading from calibrated competence scores

Version 2.0 | 17 September 2026

## Status and scope

This is the agreed replacement for versions 1.x. Start from the calibrated 0 / 0.5 / 1 subcriterion matrix. Do not introduce an intermediate set of independently judged percentage marks or a separate uplift applied only to the overall.

The sequence is: assess competences independently → calibrate across the cohort → calculate normalised criterion totals → apply university weights → calculate the cohort distribution → derive one common conversion → convert each criterion → calculate the weighted overall → round for reporting.

This method is reusable across assignments. Its statistical conversion is a chosen cohort calibration procedure, not a rule prescribed by the supplied university rubric. The rubric specifies assessment expectations and weights. Do not describe the target mean or SD as a university requirement.

**Migration status:** the existing `RDM_Subcriterion_Percentage_Grades.xlsx`, its CSV and the earlier feedback example were produced under version 1.x. They are historical outputs and must not be used as version 2 results until regenerated. This documentation revision does not itself recalculate those files. The calibrated Stage 1 matrix remains the starting source.

## 1. Fix the assignment configuration

Record:
- Assignment, academic level, rubric and source versions.
- Exact participant IDs and the complete eligible cohort.
- Criterion names, subcriteria, number of subcriteria per criterion, and criterion weights.
- Within-criterion weights if unequal weighting is explicitly required; otherwise use equal weights.
- Target class mean M, target population SD S if specified, and conversion mode.
- Whole-number reporting and tie rules.
- Any applicable institutional caps or penalties, which require an explicitly documented treatment.

The reference grade means the **target cohort mean**, not a minimum grade or a reference student's mark. Do not hard-code 65 or SD 10 for other assignments.

Current RDM configuration: M = 65, S = 10, mean-and-SD conversion, 17 participants, equal subcriterion weights within each criterion. No additional caps or penalties are applied. Preserve the assignment-specific critical-thinking focus.

## 2. Score and calibrate subcriteria

For student i, criterion c and subcriterion j, record x_icj as:
- 1: fully demonstrated through adequate understanding or application.
- 0.5: partially demonstrated.
- 0: not demonstrated.

Naming a concept does not establish competent application. Retain source-specific evidence and reasons for each judgement. These scores are rubric-based assessments, not judgement-free objective measurements.

Score all students independently before inspecting the overall grade distribution. Then compare students receiving different scores on each subcriterion and check consistency. Correct evidenced scoring errors, retain a change log, and freeze the calibrated matrix before conversion. Do not alter scores merely to obtain a preferred grade distribution.

For RDM, assess meta-epistemic reasoning: evidence quality, inference, assumptions, alternative explanations, uncertainty, generalisability, counterarguments and bias/fallacy control. Distinguish topic balance from critical analysis, citation from evidence evaluation, naming Toulmin from applying it, illustrative anecdotes from anecdotal proof, and reasoning type from certainty. Check actual use of the designated Halpern and Dunn core text.

## 3. Calculate criterion totals and distributions

With n_c equally weighted subcriteria:

`T_ic = sum_j(x_icj)`

`C_ic = T_ic / n_c`

T_ic is the raw criterion total. C_ic is the criterion proportion on a common 0–1 scale. Normalisation is essential: a criterion with seven subcriteria must not gain extra weight over one with five.

If authorised within-criterion weights a_cj are unequal, sum them to 1 and use `C_ic = sum_j(a_cj × x_icj)`; retain the unweighted raw total separately.

For each criterion report N, raw-total distribution, minimum, maximum, mean and population SD, plus mean and population SD of C_ic. Retain the individual subcriterion distributions as an audit.

Do not yet interpret a competence proportion as an awarded percentage grade.

## 4. Calculate the university-weighted competence score

Let W_c be the university/assignment criterion weights expressed as decimals, summing to 1.

`R_i = sum_c(W_c × C_ic)`

Apply the weights to the normalised criterion scores, not to unnormalised totals. Do not simply add all subcriterion points or average criteria equally unless the assessment actually specifies equal criterion weights.

This produces one weighted competence score per student on a 0–1 scale.

## 5. Calculate the complete cohort distribution

For N students:

`mu_R = sum_i(R_i) / N`

`sigma_R = sqrt(sum_i((R_i − mu_R)^2) / N)`

Use population SD, denominator N. Include exactly the same students throughout scoring, conversion and rounding. Use full precision.

## 6. Derive one common conversion

For a target mean M and positive target SD S:

`b = S / sigma_R`

`a = M − b × mu_R`

Define the common affine conversion:

`f(q) = a + b × q = M + b × (q − mu_R)`

The parameters are derived once from the **weighted overall competence distribution**, not separately from each criterion's distribution. Do not centre each criterion on its own mean or impose the same SD on every criterion.

If sigma_R = 0, a positive target SD cannot be obtained by this conversion without inventing differences. Flag the issue rather than breaking ties artificially.

If another assignment specifies only a target mean, use mean-only conversion:
`b = 100`, `a = M − 100 × mu_R`.
This retains the original spread expressed in percentage points. Do not silently impose SD 10.

## 7. Convert each criterion, then calculate the overall

Apply exactly the same a and b to every criterion:

`P_ic = a + b × C_ic`

P_ic is the converted criterion percentage. It is calculated before multiplying it by the criterion weight. The weights determine its contribution, not an extra per-criterion multiplier inside the conversion. Changing weights does, however, change the overall cohort distribution and therefore requires recalculating a and b.

Calculate the processed overall:

`G_i = sum_c(W_c × P_ic)`

Because the weights sum to 1:

`G_i = sum_c(W_c × (a + b × C_ic)) = a + b × R_i`.

Therefore:
- The converted criterion grades reconcile exactly with the processed overall before rounding.
- The complete cohort's unrounded overall mean is M.
- Its unrounded population SD is S in mean-and-SD mode.
- A positive slope preserves overall ordering and ties.
- Each criterion retains its own mean and spread: mean(P_c) = a + b × mean(C_c), and SD(P_c) = b × SD(C_c).
- Distribution shape is preserved. No criterion or overall distribution is forced to be normal.

Do not add a second moderation adjustment to G_i. Do not reuse the previous independently judged percentage marks.

Keep subcriterion scores in their original 0 / 0.5 / 1 form. The required percentage outputs are criterion and overall grades. Applying the affine formula to individual codes would produce converted index values, including a potentially non-zero value for code 0; do not mislabel these as newly demonstrated competence or independent quality marks.

## 8. Check the bounds and interpretation

Check every converted criterion and overall against 0–100 before reporting. A target mean/SD can produce out-of-range values in another cohort. Do not clip silently: clipping can break exact reconciliation and the target moments. Review the agreed parameters or document a different constrained method if bounds fail.

The conversion is relative to this cohort. A criterion score of 1 does not automatically become 100%, and the conversion cannot recover distinctions lost in the three-level scoring system. Equal criterion proportions receive equal converted grades. A high converted grade does not alone establish every qualitative feature of a university descriptor.

Do not claim that the target mean and SD uniquely establish educationally correct grades. The affine rule and targets are explicit calibration choices. Any institutional caps, penalties or alternative transformation must be reconciled separately with the target constraints; they are not part of this implementation.

## 9. Round only at the reporting stage

Retain full precision for all criterion averages, conversion parameters and weighted calculations. Display criterion percentages as whole numbers using nearest-integer rounding, halves upwards. The stored criterion values remain unrounded.

For final whole-number overall grades H_i with exact target mean M, use mean-preserving largest-remainder rounding:
1. Set F_i = floor(G_i) and r_i = G_i − F_i.
2. Calculate target total T = N × M; it must be an integer for an exact integer solution.
3. Calculate K = T − sum_i(F_i).
4. Round up the K largest remainders; leave the others rounded down.
5. Check sum(H_i) = T and mean(H_i) = M.

This is cohort-wide rounding, not ordinary independent rounding and not a second substantive uplift. It minimises squared rounding error among floor/ceiling allocations meeting the total. Population SD may change slightly; report its actual post-rounding value.

For equal remainders use ascending exact participant ID for reproducibility, but flag any allocation that would split identical underlying overall grades. Equal treatment of ties and an exact integer total can conflict. Do not claim both requirements are satisfied unless checked. If T is non-integer, seek an explicit revised target or rounding rule rather than silently approximating it.

**Rounding reconciliation:** exact weighted reconciliation holds for the unrounded converted criteria and unrounded G_i. It is not guaranteed for the displayed integer criterion grades and H_i. Do not promise exact equality between rounded displayed components and the final integer total. Achieving that additional constraint would require a separately specified joint rounding procedure; it is not the default method.

## 10. Current RDM university rubric and weights

Source: supplied **University of Essex Online – Undergraduate Grading Criteria NQF Level 5**, **Version 1 – August 2021**, file `L5 Assignment Grading Criteria (1)(1).pdf`. Its introduction notes that weights can vary between assessments.

| Assignment criterion | University category | Weight | Subcriteria | Source page |
| --- | --- | ---: | ---: | --- |
| C1 Knowledge and Understanding | Knowledge and understanding of the subject area / conceptual issues | 25% | 5 | 1 |
| C2 Critical Analysis and Evaluation | Critical Analysis and Evaluation | 25% | 6 | 2 |
| C3 Application of Theory to Persuasive Blog Writing | Application of theory to practice and/or real-world example | 25% | 5 | 1–2 |
| C4 Presentation and Academic Conventions | Presentation Style and Structure | 10% | 7 | 3–4 |
| C5 Reading and Referencing | Reading and Referencing | 15% | 6 | 3 |

Match categories by meaning, not their printed order. These weights sum to 100%. Equal within-criterion weighting is the declared implementation, not explicitly required by that university document. The university rubric does not prescribe mean 65 or SD 10. Do not import the different CLQ assignment's weights, ceilings or stepped overall-mark rules.

## 11. Worked conversion from the original RDM matrix

For Participant_555059_assignsubmission_file:

| Criterion | Raw total | Maximum | C_ic | Converted P_ic |
| --- | ---: | ---: | ---: | ---: |
| C1 | 4 | 5 | 0.8 | 66.984303 |
| C2 | 6 | 6 | 1.0 | 81.116895 |
| C3 | 5 | 5 | 1.0 | 81.116895 |
| C4 | 7 | 7 | 1.0 | 81.116895 |
| C5 | 6 | 6 | 1.0 | 81.116895 |

For all 17 students in the original calibrated matrix:
- mu_R = 0.7719187675070028.
- sigma_R = 0.14151685628279917.
- M = 65 and S = 10.
- b = 70.66296031913382.
- a = M − b × mu_R (calculate at full precision).

For this student R_i = 0.95 and G_i = **77.5837470652351**. The university-weighted sum of the five converted criterion grades gives this same result. Four criterion grades are identical because all four original proportions equal 1.

The complete unrounded cohort has mean 65 and population SD 10. Converted criterion values in this cohort range from approximately 22.23 to 81.12, within bounds. Final whole-number overall grades must still be allocated using the full-cohort rounding procedure, not inferred from this one-student example. Recalculate these statistics from the current source matrix if any scores or cohort membership change.

## 12. Deliverables, audit and feedback

The grade sheet must include exact participant IDs, all original subcriterion codes, criterion raw totals, normalised criterion scores, converted criterion percentages, weighted raw competence R_i, full-precision processed overall G_i, and final reported integer H_i. Retain weights, target configuration, a, b, cohort statistics and rounding remainders visibly for audit.

Verify completeness, allowed input codes, denominators, weight sums, source versions, bounds, ordering/ties, full-precision weighted reconciliation, target moments and final integer total. Never derive new conversions from already rounded outputs.

Use [FEEDBACK_INSTRUCTIONS.md](FEEDBACK_INSTRUCTIONS.md). Feedback remains 600–800 words, exactly three Strengths and three Areas for Improvement bullets, one narrative paragraph beneath each main criterion title and whole-number converted grade, and an 80–120 word overall summary with the final processed grade. Hide subcriterion labels and numerical codes, while explaining their substantive implications.

Changing M, S, weights, cohort membership or assessed codes requires recalculating the entire conversion and rounding allocation. Update all affected criterion and overall grades in feedback. Preserve evidence-specific judgements; do not invent stronger work because a converted percentage increases.

Retain the prior grade sheet and example as historical records until replaced with verified version 2 outputs. The original Stage 1 competence matrix is not superseded by this method.
