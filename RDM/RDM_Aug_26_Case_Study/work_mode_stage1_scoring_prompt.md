# Work Mode Prompt — Stage 1 Cohort Scoring and Calibration

I need you to carry out **Stage 1 of grading calibration** for a cohort of Reasoning & Decision-Making Case Study assignments.

All materials are in this GitHub repository directory:

`HRP-Transfer-Lab/uoe-feedback/RDM/RDM_Aug_26_Case_Study`

Start by reading:

`grading_criteria.md`

Then identify every student submission contained in the `Participant_*_assignsubmission_file` folders. Do not treat `grading_criteria.md`, `SUBMISSIONS_MANIFEST.md`, or any later analysis files as student submissions.

## Purpose of this stage

This is a **critical-thinking assignment**, although students choose a substantive topic such as:

- Vegetarianism vs omnivorism
- AI in education
- Online vs traditional education

The substantive topic is the vehicle for assessing critical-thinking competence. Do not mistake strong topic knowledge or a balanced pros-and-cons discussion for high-level critical analysis.

In particular, Criterion 2 should evaluate the **meta-epistemic quality of the student's thinking**: how they evaluate evidence quality, inferential strength, causal claims, assumptions, alternative explanations, uncertainty, generalisability, counterarguments, biases and fallacies.

## Scoring task

Evaluate **every submission independently against every subcriterion in `grading_criteria.md`**.

Use only:

- `1` = fully demonstrated
- `0.5` = partially demonstrated
- `0` = not demonstrated

Do not award 1 merely because a concept is mentioned. It must be understood or applied adequately.

At this stage:

- **Do not assign percentage marks.**
- **Do not assign UK grade bands.**
- **Do not calculate an overall assignment grade.**
- **Do not write student-facing feedback.**
- **Do not create Strengths / Areas for Improvement yet.**

We are first establishing the distribution of demonstrated competences across the whole cohort.

## Required scoring matrix

For every student, record:

`Participant ID`

Criterion 1:
`C1A C1B C1C C1D C1E`

Criterion 2:
`C2A C2B C2C C2D C2E C2F`

Criterion 3:
`C3A C3B C3C C3D C3E`

Criterion 4:
`C4A C4B C4C C4D C4E C4F C4G`

Criterion 5:
`C5A C5B C5C C5D C5E C5F`

Also calculate for each student:

- Criterion 1 raw point total, maximum 5
- Criterion 2 raw point total, maximum 6
- Criterion 3 raw point total, maximum 5
- Criterion 4 raw point total, maximum 7
- Criterion 5 raw point total, maximum 6

Also calculate a **criterion mean subcriterion score** for each criterion:

`criterion raw total / number of subcriteria`

This produces a common 0–1 scale and lets us compare criteria without yet translating them into marks.

## Cohort-level analysis

Once all papers have been scored, calculate across the complete cohort:

### 1. For each individual subcriterion

- N
- number scoring 0
- number scoring 0.5
- number scoring 1
- mean
- population standard deviation

### 2. For each of the five criteria

- N
- distribution of raw criterion totals
- minimum and maximum
- mean raw criterion total
- population standard deviation of raw criterion totals
- mean criterion score on the common 0–1 scale
- population standard deviation on the 0–1 scale

### 3. Concise cohort summary

Identify:

- which subcriteria appear strongest across the cohort;
- which appear weakest;
- whether any criteria show especially high or low variability;
- any obvious scoring anomalies that should be reviewed manually.

## Calibration pass

After completing the first scoring pass, do a **second cross-cohort calibration pass**.

Compare submissions receiving different scores on the same subcriterion and check that the distinction between `0`, `0.5` and `1` has been applied consistently.

Revise individual scores if necessary before producing the final distributions.

Pay particular attention to:

- distinguishing merely naming a critical-thinking concept from actually applying it;
- distinguishing a balanced topic essay from meta-epistemic critical analysis;
- distinguishing evidence citation from evaluation of evidence quality;
- distinguishing mentioning Toulmin from visibly applying an argumentation framework;
- distinguishing personal examples used illustratively from anecdotal evidence used as proof;
- whether reasoning type and degree of certainty are both identified;
- whether the required Halpern and Dunn core text is actually used rather than substituted by another Halpern source.

## Outputs

Produce three structured outputs:

### 1. Student scoring matrix

One row per participant with every subcriterion score and the five criterion totals/means.

### 2. Subcriterion distribution summary

One row per subcriterion with counts of `0`, `0.5`, `1`, mean and population SD.

### 3. Criterion distribution summary

One row per criterion with the raw-total distribution, mean, population SD, and corresponding 0–1 criterion mean and SD.

Keep the participant IDs exactly as they appear in the repository.

Do not yet produce qualitative feedback or grades. Stop after presenting the calibrated scoring distributions so that I can review the cohort pattern before we decide how to translate these points into criterion marks and overall grades.
