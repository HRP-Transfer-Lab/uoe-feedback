# Student feedback instructions

Version 1.0 | 17 September 2026

Use these instructions after independent scoring, cross-cohort calibration, percentage marking and any agreed overall moderation are complete. For the calculations, follow [the grading method](GRADING_METHOD_Independent_Subcriteria.md). Stage 1 remains a separate competence-scoring stage and does not produce feedback.

## Assignment configuration and authoritative inputs

Read the assignment rubric, the student's complete submission, the latest grade-sheet row and its evidence audit before drafting. Match the exact participant ID; never rely on row position alone. Record the grade-sheet version or repository commit used for a feedback batch.

The reference grade is the **target cohort mean**, not a reference student's mark or a minimum individual grade. Read it from the current assignment configuration. Do not hard-code 65 across modules. Likewise, use the assignment's declared criterion weights, criterion count, academic level and target SD or moderation mode.

Current RDM configuration:
- Rubric: `grading_criteria.md`.
- Grade sheet: `RDM_Subcriterion_Percentage_Grades.xlsx`; the CSV is its rounded reporting export.
- Target cohort mean: 65. Target population SD before integer rounding: 10.
- Weights: Knowledge and Understanding 25%; Critical Analysis and Evaluation 25%; Application of Theory to Persuasive Blog Writing 25%; Presentation and Academic Conventions 10%; Reading and Referencing 15%.
- Moderation: standardise full-precision assessed overall marks, then use mean-preserving whole-number rounding.
- Final overall source: **Moderated overall**, not **Assessed overall** or the rounded display of the pre-rounding standardised score.

## Use the hard numbers faithfully

For each main criterion heading, use the independently assessed criterion average from the grade sheet, displayed as a whole-number percentage. In the CSV these are `C1 percentage` through `C5 percentage`. Do not reconstruct them from prose or estimate them from the overall mark.

Read every underlying subcriterion mark and rationale internally. Use these to determine the emphasis and specificity of the narrative. Do not display subcriterion codes, headings, individual marks, competence codes or a scoring table to the student. Discuss the relevant concepts naturally within the main criterion paragraph.

The moderated overall is a separate cohort adjustment. It need not equal the weighted average of the displayed criterion marks. Do not inflate criterion marks, invent stronger evidence, suppress weaknesses or rewrite the intellectual judgement to make the adjusted overall appear to arise directly from those criterion marks.

If the reference mean changes, recalculate the complete cohort and mean-preserving rounding before regenerating affected feedback. Never add an estimated uplift to one student's mark, standardise a selected subset, or recalculate from rounded CSV values. Use the workbook's full-precision calculations. A change of target alone changes the numerical overall and moderation explanation, not the evidence-based criterion narrative.

If a score and the source evidence conflict, flag the issue for moderation and update the authoritative grade sheet first. Do not silently change a mark in feedback.

## Required student-facing format

Write **600–800 words in total**, including headings and bullets. Use this order:

1. Exact participant ID.
2. **Strengths**: exactly three concise, specific bullets.
3. **Areas for Improvement**: exactly three concise, actionable bullets.
4. One heading for each main criterion, in rubric order, containing only its title and whole-number grade, for example `### Knowledge and Understanding — 59%`.
5. Under each criterion heading, one connected narrative paragraph synthesising the underlying subcriteria. No subheadings, checklists or tables within these sections.
6. `### Overall grade — [moderated overall]%`, followed by an **80–120 word** overall summary.

The overall summary should identify the central achievement, the most important next steps, and include this brief explanation when overall moderation applies: “The overall grade includes the agreed cohort moderation; the criterion grades above represent the independent assessment before that adjustment.”

If moderation is not used for another assignment, omit that explanation and label the overall according to that assignment's configuration.

## Narrative quality and evidence

Address the student as “you”, use British English and avoid contractions. Include occasional concise encouragement where supported, such as “Good work here” or “You have done this well”. Keep praise proportionate to the actual evidence.

Explain what the student did, why it matters and how to improve it. Use examples from their own work, including particular claims, distinctions, evidence comparisons, argumentative choices or presentation features. A title, topic or grade alone is not enough to personalise feedback.

Internally consider every subcriterion; combine related observations into a coherent paragraph rather than reproducing the rubric as a list. Explain any material omission that substantially lowers a criterion mark, even where other aspects are strong. Hide the subcriterion scoring structure, not the substantive reason for the judgement.

For RDM, treat the topic as a vehicle for critical thinking. Reward evaluation of evidence quality, inference, assumptions, alternative explanations, uncertainty and generalisability. Do not equate balanced coverage with critical analysis, citations with evidence evaluation, or naming Toulmin with applying it. Distinguish illustrative anecdotes from anecdotal proof, reasoning type from certainty, and the designated Halpern and Dunn text from substitute sources.

Do not invent citation errors, formatting defects, source verification or misconduct findings. When original formatting is unavailable, express that limitation without treating it as a demonstrated student error. Do not penalise an assigned blog for lacking the style of a conventional academic essay.

## Final checks

- Verify the exact ID, all criterion grades and the moderated overall against the current authoritative row.
- Confirm the current cohort target and moderation mode; the example's 65 and 10 are not universal defaults.
- Confirm 600–800 words, exactly three bullets in each opening section, one paragraph per main criterion and an 80–120 word overall summary.
- Confirm no visible subcriterion labels, marks, competence codes or tables.
- Check that every evaluative claim is supported by the submission or recorded audit and that the advice is actionable.
- Retain existing manual-review flags and the distinction between assessed and moderated grades.
- Drafting or committing a feedback file does not itself authorise sending it to a student or publishing it in the learning platform.

## Worked example

[Participant_555059_assignsubmission_file](FEEDBACK_EXAMPLE_Participant_555059.md) illustrates the approved format and level of specificity. Its criterion grades are 59, 73, 73, 73 and 72; its moderated overall is 75 under the current 65/10 configuration.

The example is a snapshot of this student's evidence and grade-sheet version, not boilerplate for other students. Do not copy its claims, weaknesses or marks into another report. Analysis, instructions and example files outside participant submission folders are not student submissions.
