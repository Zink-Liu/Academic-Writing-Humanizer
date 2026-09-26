# Academic-Writing-Humanizer
An AI skill for natural academic rewriting that preserves scientific meaning, data, and citations. In one exploratory abstract test, GPTZero reported 1% AI probability with an uncertain mixed classification. Results are preliminary and may not generalize.


# Academic Writing Humanizer

**Natural academic English with scientific precision.**

Academic Writing Humanizer is a reusable AI skill for improving the clarity, flow, and natural expression of scientific writing while preserving its original meaning.

It provides detailed instructions for revising abstracts and manuscript sections, with particular attention to numerical accuracy, methodological precision, appropriate interpretation, and word limits.

The project is open for use and feedback. The skill will be refined through continued use, reported issues, and ongoing updates.

## Overview

Good academic writing communicates complex ideas clearly without changing the evidence behind them. Rewriting should preserve the research question, analytical methods, findings, and limitations while making the text easier to follow.

Academic Writing Humanizer guides an AI assistant through this process. It encourages meaningful revisions to sentence structure and information flow while maintaining the formal register expected in scientific manuscripts.

Here, “humanizer” refers to natural, context-sensitive expression. The aim is clear and precise writing that reflects the substance of the research.

## Features

- **Natural academic expression:** Improve readability, sentence structure, and transitions while maintaining a professional tone.
- **Scientific fidelity:** Preserve the original meaning, research scope, and strength of evidence.
- **Numerical accuracy:** Retain statistical results, sample sizes, units, confidence intervals, and other quantitative details.
- **Methodological precision:** Preserve distinctions between training, model selection, cross-validation, and independent validation.
- **Word-limit control:** Follow the requested maximum length without silently removing essential information.
- **Citation consistency:** Keep citations associated with the claims they support.
- **Flexible revision:** Support complete rewrites, focused edits, and refinement of an existing version.
- **Optional detector feedback:** Incorporate user-provided AI-text detection reports into subsequent revisions without inventing results.

## Repository Contents

| File | Description |
|---|---|
| [`SKILL.md`](./SKILL.md) | Complete skill instructions and revision checks |
| [`README.md`](./README.md) | Project introduction, usage examples, and contribution guidance |

The skill is an instruction file for an AI assistant. This repository does not currently provide a standalone application or an automatic connection to an AI-text detector.

## Getting Started

### Manual use

1. Open [`SKILL.md`](./SKILL.md).
2. Copy the instructions into your AI assistant.
3. Provide the text you want to revise.
4. Specify the manuscript section, word limit, and any journal requirements.
5. Review the revised text against the original.

If your assistant supports loading skill files, use its supported installation method to load `SKILL.md`.

### Basic example

```text
Apply the Academic Writing Humanizer skill to the text below.

Section: Abstract
Language: English
Style: Formal academic English
Maximum length: 250 words
Output: One complete revised version

Preserve all scientific claims, numerical results,
methodological details, citations, and necessary qualifications.

Improve clarity, sentence structure, and information flow.
Use a declarative opening.
Do not introduce new findings or strengthen causal claims.

Source text:
[Paste your text here]
```

### Focused revision

```text
Apply the Academic Writing Humanizer skill.

Revise this Discussion section for clarity and natural
academic expression.

Preserve the interpretation, citations, and limitations.
Reduce repetition and improve transitions.
Keep technical terms consistent.
Do not increase the original word count.

Source text:
[Paste your text here]
```

### Journal-specific revision

```text
Apply the Academic Writing Humanizer skill.

Target journal: [Journal name]
Section: [Manuscript section]
Maximum length: [Word limit]

Follow these journal requirements:
[Paste the relevant requirements]

Preserve the scientific content and return one complete revision.
Flag any requirement that cannot be met without losing
essential information.

Source text:
[Paste your text here]
```

## Rewriting Principles

### Preserve the science

The source text determines what the revision may claim. The skill must preserve the research objective, study design, analytical sequence, findings, and limits of interpretation.

It must not add unsupported explanations, invent references, or convert a tentative interpretation into an established conclusion.

### Improve structure before replacing vocabulary

Natural expression depends on how ideas are organized and connected. The skill prioritizes clear subjects, precise verbs, logical progression, and appropriate emphasis.

Technical terminology remains consistent wherever alternative wording could introduce ambiguity.

### Maintain an academic register

Revisions should remain suitable for a scientific manuscript. The skill avoids unnecessary rhetorical questions, conversational fillers, exaggerated language, and deliberately introduced errors.

Sentence length and structure should follow the content rather than an artificial pattern.

### Respect statistical and methodological distinctions

The skill must preserve differences between:

- Association and causation.
- Statistical significance and practical importance.
- Accuracy and ROC-AUC.
- Odds ratios and risk ratios.
- Model selection and independent evaluation.
- Exploratory findings and confirmatory conclusions.

### Keep conclusions proportional to the evidence

The conclusion should state what the results support. Computational findings, observational associations, and mechanistic hypotheses must retain their appropriate qualifications.

### Follow the requested length

An explicit word limit takes priority. When no limit is supplied, the default is to avoid exceeding the normalized source length.

If the requested length cannot accommodate essential scientific information, the assistant should explain the conflict rather than silently removing important details.

## Optional AI-Detector Feedback

Users may provide detector reports when requesting further revisions. The skill can use these reports as feedback while continuing to prioritize scientific accuracy and writing quality.

For useful comparisons, provide:

- The exact revision that was scanned.
- The detector name.
- The displayed classification.
- Any reported probability.
- The scan date and model version, if available.

```text
The attached detector report corresponds to revision R1.

Detector: [Name]
Classification: [Exact displayed label]
Probability: [If provided]

Revise the text while preserving its scientific meaning,
academic tone, and word limit.

Do not claim an improved detector result until the revised
text has actually been tested.
```

Detector outcomes can vary across texts, services, and versions. The skill does not guarantee a particular classification, and an untested revision should remain labeled as untested.

## Reviewing the Output

Before using a revised passage, check that:

- Numerical values and units match the source.
- Methods and validation procedures are described correctly.
- Citations still support the associated statements.
- Important findings and qualifications remain present.
- No unsupported claims have been introduced.
- The requested structure and word limit have been followed.

Journal-specific instructions take precedence over general stylistic preferences. Authors remain responsible for the final manuscript and applicable AI-use disclosure requirements.

## Feedback and Contributions

Try the skill with your own writing and share suggestions through GitHub Issues.

Useful feedback includes unclear instructions, awkward phrasing, missed word limits, altered scientific meaning, inconsistent terminology, and suggestions for additional writing contexts.

When reporting an issue, include the relevant instruction, the observed problem, and the behavior you expected. A short, anonymized or synthetic passage is sufficient; you do not need to share unpublished or confidential material.

Contributions that improve scientific fidelity, usability, documentation, or revision quality are welcome.

## Ongoing Development

The skill will be updated incrementally in response to practical use and community feedback.

Planned areas of refinement include:

- More precise guidance for different manuscript sections.
- Better handling of strict word limits.
- Stronger checks for methodological and statistical wording.
- Improved consistency across longer passages.
- Clearer support for journal-specific requirements.
- More useful handling of user-provided detector feedback.

## Project Status

**Available for use and actively evolving.**

Start with `SKILL.md`, apply it to your writing, and share what works and what needs improvement. Future updates will refine the instructions while keeping scientific accuracy and natural academic expression at the center of the project.
