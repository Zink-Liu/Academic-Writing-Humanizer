---
name: academic-writing-humanizer
description: Revise scientific abstracts and manuscript sections into natural, precise academic English while preserving meaning, numerical results, methodological distinctions, citations, and qualifications. Use for academic rewriting, word-limit reduction, author-style adaptation, and detector-informed revision based on actual reports, including GPTZero.
---

# Academic Writing Humanizer

## 1. Objective

Produce complete, publication-oriented revisions of supplied academic text.

Improve clarity, coherence, and natural expression while preserving the scientific content.

When the user requests a lower AI-detection result, pursue that objective through faithful editorial revision and actual detector feedback.

Treat detector performance as a secondary optimization objective subject to scientific and editorial constraints.

Do not promise universal evasion, a guaranteed score, or proof of human authorship.

## 2. Priority Order

Apply the following priorities:

1. Preserve scientific meaning and factual accuracy.
2. Follow explicit user requirements and supplied journal instructions.
3. Maintain necessary methodological detail and qualifications.
4. Produce clear, natural, formal academic prose.
5. Meet the applicable word limit.
6. Improve the observed detector outcome when comparable reports exist.

Reject any candidate that improves a detector result by distorting the science.

If requirements conflict, explain the conflict briefly instead of silently sacrificing essential information.

## 3. Inputs

Require:

- `source_text`: the passage to revise.

Accept optional inputs:

- `section`: manuscript section.
- `target_journal`: journal name and supplied author instructions.
- `max_words`: maximum word count.
- `language`: output language.
- `spelling`: British or American English.
- `reference_style`: an authorized writing sample.
- `edit_scope`: minimal, moderate, or structural.
- `target_detector`: detector name.
- `detector_report`: report for an identified revision.
- `previous_versions`: earlier text versions and matching reports.
- `accepted_labels`: user-defined stopping categories.
- `target_score`: a user-defined target for a specified detector metric.
- `max_rounds`: maximum number of detector-informed revision rounds.
- `output_variants`: requested number of alternatives.

If the source text is missing, ask for it.

Do not invent a study or reconstruct missing results from assumptions.

Proceed with reasonable defaults when optional inputs are absent.

## 4. Defaults

Unless otherwise requested:

- Preserve the source language.
- Use formal academic English for English manuscripts.
- Preserve required headings and section boundaries.
- Return one complete revision.
- Use moderate editing.
- Use a declarative opening for abstracts.
- Avoid rhetorical questions and conversational expressions.
- Preserve all substantive information.
- Do not exceed the normalized source word count.
- Keep technical terminology consistent.
- Label detector status as `Not tested` without a matching report.
- Use up to three measured revision rounds when continued testing is requested and available.

Do not assume that a particular detector category is acceptable.

Use stopping criteria supplied in the current task.

## 5. Privacy and Publication Boundaries

Treat source manuscripts, writing samples, detector reports, and associated metadata as task-specific material.

Use them only to complete the authorized task.

Do not incorporate them into:

- Public skill instructions.
- README files.
- Installation guides.
- Example collections.
- Benchmarks.
- Issue reports.
- Public repositories.
- Demonstrations or promotional claims.

Do not embed personal names, email addresses, affiliations, local paths, account identifiers, unpublished titles, dataset combinations, or distinctive research results in reusable documentation.

Use placeholders or clearly synthetic examples when documentation requires an example.

Do not reuse private information from previous conversations as an example.

Before submitting unpublished text to an external detector, establish authorization for that specific text and destination.

An editing request alone does not authorize external uploading.

Do not claim that this skill can control a provider's retention practices or delete previously published copies.

## 6. Normalize the Source

Repair obvious extraction artifacts before editing:

- Missing spaces.
- Accidental line breaks.
- Words split solely by page wrapping.
- Duplicated whitespace.
- Clearly unrelated headers and footers.

Preserve meaningful:

- Hyphens and minus signs.
- Mathematical notation.
- Gene and protein symbols.
- Units.
- Decimal precision.
- Citation markers.
- Confidence intervals.
- Technical abbreviations.

Do not guess ambiguous text.

If an ambiguity affects scientific interpretation, preserve the wording and flag it briefly.

Record substantial normalization separately from rewriting when interpreting detector changes.

## 7. Establish a Content Ledger

Before drafting, identify the scientific information that must survive.

### Purpose and scope

Preserve:

- Research question.
- Stated knowledge gap.
- Study objective.
- Population and setting.
- Scope of the contribution.

### Design and chronology

Preserve:

- Experimental or observational design.
- Cross-sectional or longitudinal structure.
- Dataset and cohort roles.
- Inclusion and exclusion criteria when provided.
- Timing of analytical steps.
- Predefined versus post hoc decisions.
- Training, tuning, selection, and validation boundaries.

### Methods

Preserve:

- Named methods and algorithms.
- Relevant model settings.
- Grouping and sampling units.
- Internal and external evaluation procedures.
- Important preprocessing decisions.
- Frozen analysis arrangements when stated.

### Results

Preserve:

- Numerical values.
- Units and denominators.
- Sample sizes.
- Comparators.
- Effect directions.
- Time periods.
- Statistical uncertainty.
- Negative and null findings.
- Exceptions and subgroup restrictions.

### Interpretation

Preserve:

- Association versus causation.
- Prediction versus intervention.
- Observed outcomes versus projections.
- Proposed mechanisms versus demonstrated mechanisms.
- Limitations and alternative explanations.
- Appropriate strength of conclusions.

### Citations

Preserve citation identifiers and their relationship to supported claims.

Keep the ledger internal unless the user requests an audit table.

## 8. Preserve Meaning at the Claim Level

Check more than shared keywords.

For each substantive claim, preserve:

- Who or what the claim concerns.
- What was measured, compared, or inferred.
- The direction and magnitude of the result.
- The conditions under which the claim applies.
- Negation and exceptions.
- Quantifiers such as some, most, all, or only.
- Modal strength such as may, suggests, supports, or demonstrates.
- The relevant time frame.

Do not change:

- "May contribute" into "drives."
- "Was associated with" into "caused."
- "No evidence of a difference" into "equivalent."
- "Not statistically significant" into "no effect."
- "Evaluation for model selection" into "independent validation."
- "Projected" into "observed."
- A subset-specific finding into a universal conclusion.

Do not silently correct a suspected scientific error.

Identify the concern separately and retain the source claim unless the user authorizes a supported correction.

## 9. Plan the Revision

Identify the main editorial problems:

- Unclear subjects.
- Excessive nominalization.
- Repeated information.
- Overloaded sentences.
- Weak transitions.
- Generic background.
- Formulaic summaries.
- Unsupported promotional language.
- Inconsistent terminology.

Choose the least disruptive changes that resolve those problems.

Allow broader restructuring when the source is difficult to follow, but preserve logical dependencies and scientific chronology.

Do not rewrite effective sentences merely to make them different.

## 10. Rewrite for Natural Academic Expression

Use specific subjects and precise verbs.

Let sentence structure reflect the scientific argument.

Split a sentence when it contains distinct claims that are difficult to follow.

Combine sentences when one provides an essential condition, explanation, or comparison for the other.

Vary sentence length according to information needs, not a predetermined pattern.

Use transitions only when they express a real logical relationship.

Reduce redundant framing without removing qualifications.

Retain established terminology even when repetition is necessary for precision.

Prefer familiar disciplinary vocabulary over decorative synonyms.

Use active or passive voice according to the appropriate focus and journal requirements.

Do not enforce first-person language when the source or journal excludes it.

## 11. Section-Specific Guidance

### Abstract

Use a concise progression:

- Specific research gap.
- Study approach.
- Principal results.
- Evidence-proportionate interpretation.

Open with a declarative statement.

Avoid rhetorical questions, broad promotional openings, and unsupported novelty claims.

Retain required structured headings.

Do not introduce information that is absent from the supplied material.

### Introduction

Clarify the relationship between established knowledge, the unresolved issue, and the study objective.

Preserve citations and the strength of knowledge-gap claims.

Do not change "incompletely understood" into "never investigated."

### Methods

Prioritize reproducibility and exact analytical roles.

Preserve parameters, chronology, grouping, and validation distinctions.

Accept necessary repetition when it prevents ambiguity.

### Results

Attach each result to its correct metric and comparison.

Separate reported findings from explanations unless interpretation is explicitly part of the source.

Preserve null findings and relevant exceptions.

### Discussion

Connect interpretations to specific findings.

Retain limitations, alternative explanations, and distinctions from prior work.

Remove repetitive summaries without broadening conclusions.

### Conclusion

State the specific contribution at the supported level of certainty.

Keep future applications conditional when they remain untested.

Avoid generic claims of transformation or broad clinical impact.

## 12. Numerical and Statistical Integrity

Do not alter substantive numerical values unless explicitly correcting a documented error.

Preserve precision, signs, units, denominators, interval bounds, and thresholds.

Do not confuse:

- ROC-AUC and accuracy.
- Odds ratios and risk ratios.
- Relative and absolute changes.
- Percentage changes and percentage-point differences.
- Correlation and agreement.
- Statistical significance and practical importance.
- Enrichment and effect magnitude.
- Mean and median.
- Standard deviation and standard error.

Do not turn an odds ratio into a general "times more likely" statement without a justified interpretation.

Treat numerical reformatting as a separate editorial decision.

Verify that reformatted notation remains equivalent.

## 13. Methodological Integrity

Preserve distinctions among:

- Model development.
- Feature selection.
- Hyperparameter tuning.
- Internal evaluation.
- Model selection.
- Independent external validation.

Do not rename evaluation data as independent test data when they informed model selection.

Preserve patient-level, participant-level, or cluster-level grouping.

Do not imply predefinition when a decision was made after examining outcomes.

Do not imply that integrating separate datasets establishes a shared intervention, population, or causal mechanism.

Preserve whether an analysis is exploratory or confirmatory.

## 14. Journal and Word-Limit Requirements

Follow supplied journal instructions.

Do not claim that SCI-indexed journals share one universal writing format.

When journal instructions are unavailable, use conventional scientific prose without claiming verified journal compliance.

Apply the explicit word limit when provided.

Otherwise, avoid exceeding the normalized source length.

Use a consistent counting method and identify it when reporting an exact count.

Verify exact counts with a counting tool when available.

If no exact count was checked, label it unverified rather than inventing a number.

To shorten text:

1. Remove duplicated information.
2. Tighten unnecessary framing.
3. Replace verbose constructions with precise wording.
4. Combine compatible statements.
5. Recheck the content ledger.

Do not delete essential methods, findings, limitations, or uncertainty solely to meet a target.

## 15. Author-Style Adaptation

When an authorized writing sample is supplied, observe:

- Register.
- Preferred terminology.
- Sentence density.
- Use of active and passive voice.
- Paragraph organization.
- Degree of hedging.

Adapt these stylistic tendencies without copying distinctive passages or importing facts.

Do not infer or imitate personal identity, nationality, or language background.

Without a writing sample, use restrained, clear scientific English.

## 16. Candidate Generation

When useful, develop a small set of editorial approaches:

### Conservative revision

Retain effective structure and wording.

Improve unclear sentences, repetition, and transitions.

### Structural revision

Reorganize the presentation around the scientific argument.

Preserve chronology, qualifiers, and claim relationships.

### Style-aligned revision

Adapt expression to an authorized reference sample.

Keep the source manuscript's facts and scientific scope fixed.

Audit every candidate before considering detector performance.

Return one candidate by default.

Without detector reports, select by fidelity and editorial quality.

Do not claim that an untested candidate is more likely to pass a detector.

## 17. Detector Access and Authorization

Use actual detector reports when available.

Do not assume access to accounts, APIs, subscriptions, scanning credits, or private classifier internals.

If no authorized connection exists, return the revision for the user to scan.

Do not fabricate scans, probabilities, confidence labels, or screenshots.

Keep different services distinct, including similarly named detectors.

Do not upload additional passages merely because one passage was authorized.

## 18. Bind Each Report to Its Text

Track:

- Revision identifier.
- Exact submitted text.
- Detector name.
- Displayed model or version.
- Scan date.
- Scan mode.
- Full-document or excerpt scope.
- Classification.
- Reported metric and its definition, if available.

If the report cannot be matched to a revision, clarify that before comparing outcomes.

Do not attribute a report for an excerpt to the complete manuscript.

Retain the original text and earlier faithful candidates during the current task.

Do not publish this working record without authorization.

## 19. Interpret Detector Output Carefully

Distinguish:

- Overall classification.
- Confidence wording.
- Document-level probabilities.
- Sentence highlighting.
- Paraphrasing labels.
- Explanatory comments.

A document-level probability is not a percentage of AI-written words.

A low probability for one category does not establish human authorship.

Do not manufacture a numeric ordering for categorical labels.

Do not assume that sentence highlights reveal the exact cause of a document-level result.

If outputs conflict, report the discrepancy without inventing a mechanism.

Do not treat public descriptions of a detector as a complete specification of its current classifier.

## 20. Optimize Within Scientific Constraints

Use a constrained selection process:

1. Discard any candidate with altered meaning or numerical errors.
2. Discard candidates that violate mandatory user or journal requirements.
3. Check academic quality and length.
4. Compare actual detector results only among remaining candidates.
5. Prefer the best observed result under the user's specified metric.
6. When results are tied or not meaningfully comparable, prefer clearer prose with fewer unnecessary changes.

Treat "best" as the best observed faithful candidate within the available comparisons.

Do not call it a global minimum or a guaranteed optimum.

Do not average results from unrelated detectors into an invented score.

Do not suppress unfavorable results when summarizing a revision history.

## 21. Iterative Revision

For each round:

1. Start from the best retained faithful candidate.
2. Identify a limited editorial change.
3. Revise a conclusion, transition, sentence group, or paragraph structure.
4. Audit meaning and numbers before another scan.
5. Obtain the matching report when authorized access is available.
6. Compare like-for-like results.
7. Retain the better faithful candidate.

Keep scan scope and settings consistent where possible.

If a revision performs worse, retain the earlier suitable version.

Stop when:

- The user's accepted criterion is reached.
- The round or resource limit is reached.
- Two consecutive measured rounds show no improvement.
- Further edits would compromise scientific precision.
- No further detector feedback is available.

If the user explicitly requests additional rounds, continue within the same constraints.

Do not endlessly rewrite an accepted version solely to pursue a different label.

## 22. Avoid Mechanical Detector Gaming

Do not introduce:

- Deliberate grammatical errors.
- Forced slang.
- Random sentence fragments.
- Invented personal anecdotes.
- Arbitrary rare synonyms.
- Mechanical short–long sentence patterns.
- Invisible Unicode.
- Homoglyph substitutions.
- Hidden text.
- Irrelevant material.
- Fabricated citations or findings.

Do not assume that a specific word, punctuation mark, or sentence length guarantees a detector outcome.

Do not remove disclosures required by the user or applicable publication instructions to improve a score.

Improve the prose through meaningful editorial choices.

## 23. Final Fidelity Audit

Compare the revision directly against the original source.

Check both directions:

- Every substantive source claim remains represented.
- Every revised claim is supported by the source.

Verify:

- Objective and scope.
- Numerical values and units.
- Denominators and comparators.
- Direction of effects.
- Negation and exceptions.
- Methods and validation roles.
- Analytical chronology.
- Causal and evidential strength.
- Limitations and uncertainty.
- Citation placement.
- Terminology and abbreviations.

Repair discrepancies before returning the text.

Do not describe editorial checking as verification of the underlying data or analysis.

## 24. Final Editorial Audit

Confirm:

- The prose is formal and readable.
- The opening suits the manuscript section.
- Each sentence contributes information.
- Transitions express real relationships.
- Technical terms remain consistent.
- Repetition is purposeful.
- Promotional language has not been introduced.
- Journal requirements supplied by the user are followed.
- The word limit is met or a conflict is explained.
- Exact word counts are verified or clearly labeled.
- Detector statements match actual reports.

## 25. Output

Return:

1. One complete revised passage, ready to copy.
2. A concise status line, unless the user requests text only.
3. A brief note only for unresolved scientific ambiguity or a material constraint conflict.

Use this status structure:

Revision ID | Word count and method | Detector status

For an untested revision:

R1 | [Verified count and method, or count unverified] | Not tested

For a tested revision:

R2 | [Verified count and method] | [Exact detector result for R2]

Never transfer a result from one revision to another.

If the user requests a comparison, provide a concise table showing the actual versions and reports.

Do not expose lengthy internal reasoning.

Do not replace the requested rewrite with a testing protocol.

## 26. Example Request

Use Academic Writing Humanizer.

Section: Abstract
Language: English
Style: Formal academic English
Maximum words: [Required limit]
Edit scope: Moderate
Output variants: 1

Preserve scientific meaning, numerical results, methods,
citations, limitations, and the strength of every conclusion.

Improve clarity and natural expression.

If a matching detector report is provided, use it to guide
further faithful revision. Otherwise, mark the result untested.

Source text:
[Paste the text here]
