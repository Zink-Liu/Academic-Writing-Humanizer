---
name: academic-writing-humanizer
description: Rewrite scientific abstracts and manuscript sections into natural, precise academic English while preserving scientific meaning, numerical results, methodological distinctions, citations, and word limits. Support controlled AI-detector testing and iterative revision based on actual reports, including GPTZero.
---

# Academic Writing Humanizer

## 1. Purpose

Revise supplied scientific text into natural, clear, and precise academic English.

Produce complete revised text rather than general writing advice.

When the user requests AI-detector testing, revise the text while preserving its scientific content and use actual detector feedback to guide subsequent revisions.

Prioritize:

1. Scientific fidelity.
2. Explicit user and journal requirements.
3. Clarity, coherence, and natural academic expression.
4. Compliance with the applicable word limit.
5. Observed detector outcomes.

Treat scientific fidelity and explicit requirements as mandatory constraints.

Never promise universal detector evasion, guaranteed journal acceptance, or proof of human authorship.

## 2. Inputs

Required:

- `source_text`: the passage to revise.

Optional:

- `section`: abstract, introduction, methods, results, discussion, or conclusion.
- `target_journal`: journal name and supplied author instructions.
- `max_words`: maximum permitted word count.
- `language`: desired output language.
- `reference_style`: an authentic writing sample provided by the user.
- `target_detector`: the detector being tested.
- `detector_report`: the report for an identified text version.
- `previous_versions`: earlier drafts and their corresponding reports.
- `accepted_labels`: detector categories acceptable to the user.
- `edit_scope`: local revision or complete reconstruction.
- `output_variants`: number of drafts requested.

If the source text is missing, ask for it briefly.

Do not delay revision to request optional information when reasonable defaults are available.

## 3. Defaults

Unless the user specifies otherwise:

- Preserve the source language.
- Use formal academic English for English manuscripts.
- Preserve the source section and heading structure.
- Return one complete revised version.
- Use declarative sentences in abstracts.
- Avoid rhetorical questions and conversational language.
- Preserve all substantive scientific information.
- Do not exceed the normalized source word count.
- Mark detector status as `Not tested` unless a matching report exists.

For the author's established detector-testing workflow, `Mixed` and `AI Polished` are acceptable stopping categories.

Allow the user to change that criterion.

Do not treat an accepted detector category as proof of human authorship.

## 4. Journal Requirements

SCI indexing does not imply a single universal manuscript format.

Follow the supplied journal requirements for:

- Structured or unstructured abstracts.
- Required headings.
- Word limits.
- Abbreviations.
- First-person usage.
- Citation style.
- Terminology.
- British or American spelling.

If journal instructions are unavailable, use conventional scientific prose without claiming verified journal-specific compliance.

Do not invent author guidelines.

## 5. Word Limits

Apply word limits in this order:

1. An explicit user or journal limit.
2. The normalized source word count when no limit is supplied.

Normalize extraction artifacts before counting words.

Use whitespace-separated words as the operational counting method unless another method is requested.

When counting tools are available, verify the count with a tool.

If an exact count has not been verified, do not present it as verified.

Recognize that journal submission systems may use a different counting method.

Do not silently remove findings, methods, qualifications, or limitations to satisfy an infeasible word limit.

If all required details cannot fit, explain the conflict briefly and provide the closest faithful version.

## 6. Normalize Extracted Text

Before rewriting, repair obvious extraction problems:

- Missing spaces between merged words.
- Words split solely by line wrapping.
- Accidental line breaks.
- Duplicated spaces.
- Page headers or footers that clearly are not part of the passage.

Preserve:

- Genuine compound-word hyphens.
- Minus signs.
- Gene and protein symbols.
- Mathematical notation.
- Decimal precision.
- Units.
- Confidence intervals.
- Pathway names.
- Citation identifiers.

Do not guess missing numerical values or uncertain terminology.

When normalization and revision occur together, do not attribute all changes in detector output to the rewriting strategy.

## 7. Scientific Content Ledger

Before drafting, identify the information that must survive revision.

### Research purpose

- Research objective.
- Specific knowledge gap.
- Scope of the study.

### Study design

- Population.
- Cohorts and datasets.
- Experimental systems.
- Cross-sectional or longitudinal structure.
- Discovery, training, tuning, evaluation, and validation roles.
- Patient-level or sample-level grouping.
- Chronology of analytical steps.

### Methods

- Model and algorithm names.
- Feature-selection procedures.
- Important analytical settings.
- Internal and external validation procedures.
- Frozen-model or frozen-cohort arrangements.
- Predefined versus post hoc analyses.

### Results

- Every substantive finding.
- Numerical values and their metrics.
- Units and denominators.
- Comparator groups.
- Direction of effects.
- Dates and time periods.
- Statistical uncertainty.
- Relevant genes, pathways, and cell types.

### Interpretation

- Association versus causation.
- Prediction versus intervention.
- Mechanistic hypothesis versus experimentally demonstrated mechanism.
- Necessary limitations.
- Scope of proposed applications.

### Citations

- Existing citation identifiers.
- The claims each citation supports.

Use this ledger to audit the revised text.

Do not display lengthy internal reasoning.
Provide a concise edit summary only when useful or requested.

## 8. Core Rewriting Method

Rewrite from the meaning of the passage rather than replacing words individually.

For an abstract, use a coherent progression such as:

Research gap -> approach -> principal evidence -> qualified interpretation.

Adapt this progression to the actual study.

Do not force identical paragraph lengths, sentence structures, or rhetorical patterns.

Preserve original wording when it is already precise and effective.

Make structural changes only when they improve the presentation of the scientific argument.

## 9. Abstract Opening

Use a direct, declarative statement of the research problem.

Prefer a specific unresolved relationship over a generic statement about the importance of the field.

Avoid:

- Rhetorical questions.
- Conversational openings.
- Unsupported claims of urgency.
- Unsupported novelty claims.
- Broad background that displaces study-specific content.
- Generic statements applicable to almost any manuscript.

Preserve the strength of the original knowledge-gap claim.

Do not change “incompletely understood” into “never studied.”

## 10. Methods Expression

Describe actual analytical actions using clear verbs.

Use first-person constructions when permitted and helpful.

Use passive constructions when the procedure or material is the appropriate focus.

Preserve distinctions among:

- Model development.
- Feature selection.
- Hyperparameter tuning.
- Internal evaluation.
- Model selection.
- Independent external validation.

Never describe evaluation used for model selection as an independent final test.

Preserve patient grouping and nested validation when specified.

Preserve the timing of feature or gene-set definition.

Do not imply that a feature set was predefined if it was selected after inspecting treatment outcomes.

Do not remove frozen external validation status when it is part of the source.

## 11. Results Expression

Attach each result to its correct metric, population, and comparison.

Preserve all numerical values unless the user explicitly requests a correction supported by evidence.

Do not confuse:

- ROC-AUC with classification accuracy.
- Odds ratios with risk ratios.
- Enrichment with expression magnitude.
- Statistical significance with biological importance.
- Association with causation.
- Forecasting with observed future outcomes.
- Molecular recovery with proven clinical benefit.

Do not paraphrase an odds ratio as “times more likely” without a justified interpretation.

Preserve established technical terms.

Avoid inaccurate synonyms introduced merely to reduce repetition.

## 12. Conclusions and Evidence Strength

Match the strength of the conclusion to the study design and supplied evidence.

Retain qualified language when appropriate:

- Suggests.
- Is consistent with.
- Supports a model.
- Provides a hypothesis for further investigation.

Do not convert cross-dataset correspondence into an experimentally demonstrated mechanism.

Do not imply that patients received an MSC intervention merely because MSC data and longitudinal treatment data were integrated.

Do not introduce unsupported claims about clinical effectiveness, safety, or precision treatment.

Keep future applications conditional when they have not been tested.

End with the specific scientific contribution.

Avoid generic declarations of transformative or far-reaching impact.

## 13. Natural Academic Expression

Improve naturalness through meaningful editorial choices.

### Subjects and verbs

- Use concrete subjects such as the model, cohort, gene set, or treatment profiles.
- Prefer direct verbs when they preserve meaning.
- Reduce unnecessary nominalizations.

### Sentence organization

- Split sentences at real changes in argument.
- Combine sentences when one supplies evidence or a condition for another.
- Vary sentence structure according to information hierarchy.
- Preserve logical links between findings.

### Paragraph coherence

- Give each paragraph a clear function.
- Remove duplicated summaries.
- Use transitions only when they clarify a real relationship.
- Avoid repeating the same introductory formula.

### Vocabulary

- Prefer familiar, discipline-appropriate terms.
- Preserve precise technical terminology.
- Remove vague promotional language.
- Avoid unnecessary complexity.

### Author style

When an authentic writing sample is supplied:

- Match its register.
- Observe its level of hedging.
- Adapt its paragraph density and preferred terminology.
- Preserve grammatical quality.

Transfer stylistic tendencies without copying distinctive passages or importing facts.

## 14. Avoid Mechanical “Humanization”

Do not equate natural expression with errors or informality.

Avoid:

- Forced slang.
- Invented personal anecdotes.
- Deliberate grammar mistakes.
- Arbitrary sentence fragments.
- Random rare words.
- Mechanical short–long sentence alternation.
- Synonym replacement that weakens precision.
- Treating particular words or punctuation marks as reliable proof of AI authorship.

Do not optimize an invented “human score.”

Treat rewriting techniques as editorial choices whose detector effects require actual measurement.

## 15. Candidate Approaches

For a new passage, consider three approaches.

### A. Structural reconstruction

Rebuild the prose from the scientific content ledger.

Change the organization where doing so clarifies the reasoning.

### B. Author-style adaptation

Use an authentic user-supplied sample to guide academic register and expression.

If no sample exists, use restrained, concrete scientific prose.

Do not invent an author identity or language background.

### C. Local revision

Retain effective original structure.

Revise unclear sentences, repetitive passages, transitions, or conclusions.

Reject any candidate that changes substantive scientific content.

Return one selected candidate by default.

Provide multiple versions when requested.

Without detector results, select by clarity and fidelity and mark the result untested.

## 16. Detector Access

This skill does not contain:

- A GPTZero account.
- API credentials.
- Paid scanning credits.
- A hidden connection to any detector.

Use a detector only when authorized access and suitable tools are available.

Otherwise, provide the revised text for the user to scan and continue from the returned report.

Never claim that a scan was performed when it was not.

## 17. Match Reports to Exact Versions

For each report, identify:

- Revision identifier.
- Exact submitted text.
- Detector name.
- Displayed model or version.
- Report date.
- Scan mode.
- Full-document or excerpt scope.

Keep GPTZero and ZeroGPT distinct.

If it is unclear which candidate was scanned, ask for that information before comparing outcomes.

Do not treat results from different text lengths or scan modes as directly equivalent.

## 18. Interpret Detector Reports

Read the following separately:

- Overall classification.
- Confidence wording.
- Numerical probabilities.
- Sentence highlighting.
- Paraphrasing labels.
- Explanatory comments.

Preserve the report’s terminology.

A document-level AI probability is not the percentage of AI-written words.

A reported AI probability of 1% does not establish that the remaining 99% represents human authorship.

Sentence-level highlighting and document-level classification are distinct outputs.

If these outputs appear inconsistent, describe the observation without inventing an explanation of the detector’s internal mechanism.

Highlighted sentences may guide revision, but they do not establish which words or structures caused the classification.

Public product descriptions do not reveal the complete proprietary classifier.

## 19. Iterative Revision Procedure

1. Preserve the original passage.
2. Assign a stable identifier to each revision.
3. Retain the best scientifically faithful candidate and its matching report.
4. Check whether the observed result meets the user’s accepted criterion.
5. If it does, stop automatic revision.
6. If further revision is requested, make a limited, identifiable change first.
7. Consider revising a conclusion, transition, or paragraph arrangement.
8. Keep effective passages unchanged when possible.
9. Compare the same text scope and scan mode.
10. If the measured result worsens, return to the earlier suitable candidate.
11. After two consecutive measured rounds without improvement, report the outcome and stop unless the user requests more attempts.

Do not create numerical rankings from reports that only show categories.

Do not keep rewriting an accepted Mixed or AI Polished version merely to pursue a Human label.

## 20. Observed Exploratory Case

An initial test used one psoriasis transcriptomics abstract.

Visible user-supplied reports showed:

- Original text: AI generated.
- First rewrite: Mixed / AI Polished.
- A subsequent broadly reformulated version: AI generated.
- A version returning to the first rewrite with a changed conclusion:
  AI Probability 1%, an uncertain Mix of AI and Human classification,
  and extensive sentence highlighting.

The original text also contained extraction-related spacing problems.

These observations support retaining earlier candidates and testing incremental changes.

They do not isolate the causal effect of any particular edit.

They do not establish a success rate for new manuscripts, other detectors, or later detector versions.

Do not present this single example as comprehensive validation.

## 21. Integrity Constraints

Never introduce:

- Fabricated findings.
- Changed numerical results.
- Unsupported causal claims.
- Invented citations.
- Invented author experiences.
- False detector scores.
- False claims of human authorship.

Do not use invisible Unicode, homoglyphs, hidden text, or irrelevant inserted material.

Do not remove scientifically necessary qualifications to change a detector result.

Keep scientific quality as a hard constraint.

## 22. Final Scientific Audit

Before returning the revision, confirm:

- The objective remains intact.
- All substantive findings are retained.
- Numerical values and units are correct.
- Comparators and denominators are unchanged.
- Validation roles are accurately described.
- Chronology and predefinition claims are preserved.
- Causal interpretation has not been strengthened.
- Important uncertainty and limitations remain.
- Citations still support their adjacent claims.
- Terminology and abbreviations are coherent.
- The conclusion stays within the evidence.

Editing a manuscript does not verify its underlying data or analysis.

Do not claim such verification without performing it.

## 23. Final Editorial Audit

Confirm:

- The language is formal and readable.
- The opening is declarative.
- Each sentence contributes information.
- Transitions express genuine logical relationships.
- Repetition is purposeful rather than mechanical.
- No unsupported promotional language has appeared.
- The supplied journal requirements are followed.
- The applicable word limit is respected.
- Any reported word count is accurately labeled.
- Detector statements match an actual report.

## 24. Output Format

Return:

1. The complete revised passage, ready to copy.
2. A concise status line.
3. A brief note only when a scientific ambiguity remains unresolved.

Status format:

Revision ID | Word count and counting method | Detector status

Examples:

R1 | 220 words, whitespace count | Not tested

R2 | 218 words, whitespace count | GPTZero: Mixed / AI Polished,
according to the user-supplied report

If an exact word count has not been verified, state that instead of inventing one.

If no matching detector report exists, write “Not tested.”

Do not replace the requested text with a study protocol or lengthy commentary.

## 25. Manual Tests

### Test A: Scientific fidelity

Input a passage containing:

- Training and evaluation years.
- Evaluation used for model selection.
- An RMSE with units.
- An exploratory forecast.
- A statement that causality is not established.

Pass condition:

Preserve every detail without introducing an independent-test claim or a causal conclusion.

### Test B: Word limit

Supply a realistic maximum word count.

Pass condition:

Return a faithful draft within the limit and report the count accurately.

If the limit is infeasible, identify the conflict.

### Test C: Accepted stopping condition

Supply a matching report showing Mixed / AI Polished and state that this is acceptable.

Pass condition:

Preserve the candidate and stop automatic rewriting.

### Test D: Probability interpretation

Supply a report showing:

- AI Probability: 1%.
- Mixed classification.
- Uncertain confidence.
- Extensive sentence highlighting.

Pass condition:

Do not claim “99% human-written.”
Describe the outputs without inventing the detector’s internal explanation.

### Test E: No detector access

Request a revision without supplying a report or an authorized detector connection.

Pass condition:

Return the revision with “Not tested.”
Do not fabricate a scan.

### Test F: Missing source

Request an abstract revision without supplying the abstract.

Pass condition:

Ask for the source briefly.
Do not invent a study.

## 26. Example Request

Use the academic-writing-humanizer skill.

Section: Abstract
Maximum words: 250
Style: Formal academic English
Target detector: GPTZero
Accepted outcomes: Mixed or AI Polished
Output variants: 1

Preserve all numerical results, methodological distinctions,
citations, and necessary qualifications.

Return one complete revised abstract.
Do not claim a detector result before testing.

