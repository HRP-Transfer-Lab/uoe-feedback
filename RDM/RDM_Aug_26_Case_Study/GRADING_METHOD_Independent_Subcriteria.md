# Independent subcriterion grading with cohort moderation and whole-number reporting

Version 1.3 | 17 September 2026

## Purpose and scope

Assess the quality demonstrated on each subcriterion independently, then apply the assessment's declared weights. Preserve the resulting evidence-based marks. After independent marking, apply the agreed cohort standardisation to the overall marks and report mean-preserving whole-number moderated grades. Retain the independently assessed marks as the evidence record.

This method can be adapted to other modules by replacing the learning outcomes, assignment-specific subcriteria, level descriptors and weights. It does not assume that subcriteria, criteria or overall marks follow a normal distribution.

## 1. Establish the assessment specification

Before marking, record the assignment, academic level, assessment-specific rubric, generic level descriptors, criterion weights, subcriterion weights within criteria, word-limit rules and any authorised penalties or grade ceilings. Fix these before inspecting the resulting grade distribution.

Use institutional descriptors for academic quality and the assignment rubric for what must be demonstrated. Assessment-specific genre requirements take precedence over an inappropriate generic genre assumption: an assigned public-facing blog should not be penalised simply for being a blog.

For the current RDM Case Study, use `grading_criteria.md` and the supplied *University of Essex Online – Undergraduate Grading Criteria NQF Level 5*, Version 1, August 2021. The CLQ grading method concerns a different assignment and is not imported. The supplied Level 5 guidance explicitly states that use of an older APA edition alone should not attract a deduction. Assess substantive citation accuracy and consistency; do not treat unobservable typography in normalised text as a student error.

## 2. Retain the competence record

Stage 1 records 0 = not demonstrated, 0.5 = partially demonstrated and 1 = fully demonstrated for each subcriterion. Preserve the original calibrated record and its source version.

These codes do not map directly to 0%, 50% and 100%. They combine evidence about presence, adequacy, accuracy and application, but do not provide enough resolution for percentage grading. For example, a reading-range code of 0 can mean four relevant sources rather than no reading; a reasoning code of 0 can mean no account of inference or an explicitly incorrect account. Those situations require different quality judgements.

Do not silently redefine the Stage 1 codes as mere coverage. If rereading reveals a substantive coding error, flag a proposed correction separately and preserve the original record.

## 3. Assess each subcriterion independently

Read the relevant evidence in the whole assignment, including Methods and references where appropriate. Assign a percentage mark before applying any weighting. A subcriterion does not receive a higher or lower mark because it carries a larger or smaller weight.

Use five-point increments for provisional subcriterion marks. Apply the relevant Level 5 descriptor to that particular competence. The following condensed anchors guide, rather than replace, the supplied descriptors:

| Mark region | Quality anchor |
| --- | --- |
| 0 | No assessable evidence for the specified competence. Distinguish absence from a flawed attempt. |
| 5–25 | Very limited evidence or serious misunderstanding; select a mark reflecting the extent of relevant material. |
| 30–35 | Weak, fragmentary or largely descriptive treatment; major errors or limited evaluation/application. |
| 40–45 | Basic relevant understanding or application, with significant omissions or inconsistent reasoning. |
| 50–55 | Adequate, reasonably accurate work; some evaluation/application, but limited depth or completeness. |
| 60–65 | Sound, competent and developed work, with appropriate evidence and awareness of relevant limits. |
| 70–75 | Strong, detailed and well-integrated work, with convincing evaluation/application and some independent thinking. |
| 80–85 | Exceptional performance on the specified competence: precise, developed, independently reasoned and attentive to the limits of the evidence. |
| 90–100 | Reserve for unusually outstanding evidence fully supporting this judgement. |

Do not impose an automatic percentage ceiling solely from a Stage 1 code. A partial code caused by a minor formal omission differs from one caused by conceptual weakness. Explain any mark/code combination that might otherwise appear inconsistent. Similarly, a fully demonstrated competence is not automatically exceptional work.

Maintain an audit rationale for each criterion's constituent marks, including specific evidence, omissions and limitations. Record material uncertainty, such as missing original formatting or sources that have not been verified. Do not infer misconduct from stylistic similarity, citation anomalies or AI-related wording.

## 4. Cross-cohort moderation

Compare papers addressing the same subcriterion. Use examples of basic, adequate, sound and strong performance to check that marks reflect comparable evidence. Students with the same Stage 1 code may receive different marks when the work demonstrates different quality; do not introduce differences merely to break ties.

For this critical-thinking assignment, pay particular attention to evaluating evidence rather than counting citations, inferential strength rather than topic balance, actual framework application rather than naming it, and illustrative anecdotes rather than anecdotes presented as proof. Distinguish reasoning type from the strength or certainty of its conclusion.

Review apparent contradictions and unusual scores against the source. Revise marks only where a substantive rationale supports the revision. Do not use the desired overall distribution as the reason for a revision.

## 5. Apply the weights after marking

Let M_ij be student i's percentage mark for subcriterion j. Let a_cj be the within-criterion weight, summing to 1 within criterion c. Let W_c be the criterion weight, summing to 1 across criteria.

Criterion mark: C_ic = sum_j(a_cj × M_ij).

Overall assessed mark: G_i = sum_c(W_c × C_ic).

Equal within-criterion weights give C_ic = mean of its subcriterion marks. Do not round constituent or criterion values before aggregation. Display student marks as whole numbers, rounding criterion averages and the assessed overall to the nearest integer for presentation only (halves upwards). Retain full precision internally and use it for aggregation and moderation. Distribution statistics retain decimals. A five-point input scale does not require five-point criterion means or overall totals.

Only apply institutional penalties or overall caps when they have been explicitly established for this assessment. Record them separately from subcriterion marks and avoid double-counting. Do not borrow caps from the CLQ assignment. This implementation applies no additional overall caps or penalties.

## 6. Describe the observed cohort distribution

Report N, mean, population SD, minimum and maximum for each subcriterion, each criterion and the assessed overall mark. Retain different means and variances across subcriteria. Do not create a spread where the evidence supports equal marks.

The overall variance depends on covariance as well as individual variability: Var(G) = sum_j(w_j² Var(M_j)) + 2 sum_(j<k)(w_j w_k Cov(M_j,M_k)), where w_j = W_c × a_cj.

## 7. Overall moderation to the agreed cohort target

Record the assignment-specific reference mean (mu_target) and moderation mode in the grade-sheet configuration. The reference mean is the target class mean, not a benchmark student's grade. The present cohort uses 65; another assignment may use a different agreed value. Do not infer or reuse a target without an assignment-specific instruction.

If a target population SD (sigma_target) is also agreed, use mean-and-SD standardisation:

G_standardised_i = mu_target + sigma_target × (G_i − cohort_mean(G)) / population_SD(G).

If only a target mean is agreed for another assignment, use a mean shift instead: G_standardised_i = G_i + mu_target − cohort_mean(G). This preserves the original SD before rounding. Do not silently impose SD 10 on an assignment that specifies only a mean. The zero-SD restriction below applies to mean-and-SD standardisation; a mean shift remains defined for a constant cohort.

For this cohort, the agreed mode is mean-and-SD standardisation, with mu_target = 65 and sigma_target = 10. This transformation preserves ordering, ties and relative differences. It gives exactly those moments before rounding, provided the original overall SD is positive. It does not make a non-normal distribution normal.

The user has adopted this transformation for the moderated overall grades. Retain the full-precision standardised result alongside the independently assessed overall, then calculate the whole-number **moderated overall** using the rule below. The moderated overall is the adjusted grade for inspection. It does not equal the weighted sum of unchanged subcriterion marks; the difference is an explicit overall moderation adjustment. Do not change evidence-based subcriterion marks to reconstruct it.

If the original SD is zero, mean-and-SD standardisation is undefined and should remain unavailable. If transformed values lie outside 0–100, flag them; do not silently clip them, because clipping changes the moments. Use the same students in the mean, SD and transformation. Use the population denominator N consistently.

Rank-normal transformation is not part of this method. Neither subcriteria nor the overall distribution are forced to be normal. If a future assessment adopts rank-normalisation, document it as a distinct norm-referenced procedure.

## 8. Mean-preserving whole-number rounding

Subcriterion percentage marks are already integers in five-point steps. Display criterion averages and the independently assessed overall as whole numbers, while retaining the unrounded values in the calculation. Stage 1 codes remain 0, 0.5 and 1 because they are competence codes, not percentage marks.

For the final moderated overall, ordinary independent rounding can move the class mean away from its target. Use the largest-remainder procedure instead:

1. Let S_i be each full-precision standardised overall. Set F_i = floor(S_i) and r_i = S_i − F_i.
2. Set the required class total T = N × target mean. This must be an integer for an exact whole-number solution.
3. Calculate K = T − sum(F_i).
4. Round up the K scores with the largest fractional remainders; leave the others rounded down. Thus H_i = F_i + 1 for those K students and H_i = F_i otherwise.
5. Check sum(H_i) = T, mean(H_i) = target mean, all H_i are integers within 0–100, and ordering is not reversed.

This minimises total squared rounding error among floor/ceiling allocations with the required total. A few scores above .5 can round down, or scores below .5 can round up, to preserve the mean. Resolve equal remainders in ascending participant-ID order for reproducibility. If this would split identical underlying overall scores, flag the tie for manual review: equal treatment of ties and an exact integer total can conflict. If the target total is non-integer, the transformed scores are outside bounds, or mean-and-SD standardisation is requested with original SD zero, do not silently manufacture a solution; review the target or constraints.

For this cohort N = 17 and target mean = 65, so the required total is **1,105**. Ordinary nearest-integer rounding gives 1,107. Largest-remainder rounding instead gives exactly 1,105. Participant_555077_assignsubmission_file and Participant_555078_assignsubmission_file round down rather than up compared with ordinary rounding. No tied underlying scores require adjudication.

The pre-rounding population SD is exactly 10. Integer rounding will generally change it slightly, and the observed post-rounding SD must be reported. Exact mean 65 takes priority over exact SD 10 at the final integer stage. No normal distribution is imposed.

## 9. Deliverables and checks

Provide one row per participant with all subcriterion percentage marks, criterion means, assessed weighted overall mark, standardised overall before final rounding, and whole-number moderated overall. Retain the unrounded calculations and rounding remainders in the workbook for audit. Preserve exact participant IDs. Include the competence codes, mark rationales, source identifiers and moderation flags as supporting material.

Check participant completeness, allowed mark increments, weights summing to 1, arithmetic, population-SD calculations, ties, unrounded reconciliation, and the separation of assessed and moderated marks, and the exact integer class total. Record any final rounding convention explicitly. Treat outputs as provisional for inspection until the identified moderation questions are resolved; do not publish grades or student feedback automatically.

## 10. Generate student-facing feedback from the final grade sheet

Follow [FEEDBACK_INSTRUCTIONS.md](FEEDBACK_INSTRUCTIONS.md) for each student. Use the current exact participant row and evidence audit: report only main criterion titles and whole-number grades, with one connected paragraph under each. Keep subcriterion codes, titles and marks internal. Start with exactly three Strengths and three Areas for Improvement bullets. End with the moderated overall grade and an 80–120 word summary. Keep the complete response within 600–800 words.

The independent criterion grades and moderated overall must be copied from the final grade sheet. Explain the overall adjustment briefly; do not alter the criterion narrative to rationalise a statistical uplift. If the target mean, SD, weights, cohort membership or assessed marks change, recalculate the full cohort and its integer allocation first, then regenerate affected feedback. Do not calculate from rounded CSV summaries.

Use [the worked example](FEEDBACK_EXAMPLE_Participant_555059.md) as a format and tone reference only. It is based on grade-sheet commit 3eb01ffef991465d2fdf3c682ca8fac7eee00c88, with criterion grades 59, 73, 73, 73 and 72, and moderated overall 75. Other students require their own evidence and grades.

## Current RDM Case Study configuration

| Criterion | Criterion weight | Number of subcriteria | Weight of each subcriterion in overall mark |
| --- | ---: | ---: | ---: |
| C1 Knowledge and Understanding | 25% | 5 | 5% |
| C2 Critical Analysis and Evaluation | 25% | 6 | 25% / 6 |
| C3 Application of Theory to Persuasive Blog Writing | 25% | 5 | 5% |
| C4 Presentation and Academic Conventions | 10% | 7 | 10% / 7 |
| C5 Reading and Referencing | 15% | 6 | 2.5% |

All subcriteria within each criterion are equally weighted. Each percentage mark is assessed independently of these weights. Equal within-criterion weighting is the declared implementation of the Case Study subcriteria; it is not explicitly prescribed by the supplied university document.

For the exact mapping to the supplied university rubric, source pages and a worked weighted calculation, see [University rubric and weights in the feedback instructions](FEEDBACK_INSTRUCTIONS.md#university-rubric-weights-and-the-distinction-from-cohort-moderation). For Participant_555059_assignsubmission_file the university-weighted independent mark is 69.369047619... (69% rounded); 75% is the separately moderated overall. The supplied university rubric does not establish a target mean/SD or authorise cohort normalisation. Do not represent the user-selected moderation as a university requirement or as verified institutional approval.

Sources: the repository Case Study rubric; supplied Level 5 descriptors; calibrated Stage 1 workbook; and the user's agreed independent-marking, overall moderation and whole-number reporting instructions. The uploaded Level 5 document is the source used for this calibration, not a claim about subsequently revised institutional policy.
