---
layout: page
title: "CLEAR-NLI: Ambiguity in natural language inference"
description: "An ambiguity-annotated corpus for natural language inference, built with a hybrid human–LLM annotation pipeline (NLP & Culture Lab)."
img: assets/img/projects/clear-nli.jpg
importance: 3
category: Completed Research
---

**2025–2026 · NLP & Culture Lab, with Chathuri Jayaweera, E. Kempa, and Dr. Bonnie J. Dorr**

#### The problem

Natural language inference (NLI) asks whether a hypothesis follows from a premise. Most NLI datasets assume each premise–hypothesis pair has one correct label, so when annotators disagree, the disagreement is resolved by majority vote and treated as noise. Often, though, people disagree because the sentence really is ambiguous. In *I saw her duck*, "duck" can be a bird or a movement, and the right label for *She owns a bird* depends on which reading you take.

CLEAR-NLI treats that kind of disagreement as signal. The goal is a resource that lets NLI systems first detect that a pair is ambiguous, then classify the type of ambiguity, and only then make an inference for each reading.

#### What we built

- **A unified ambiguity taxonomy.** We started from existing NLI ambiguity taxonomies and refined them through a pilot annotation study. The result has six broad categories: lexical, referential, structural, quantification and genericity, pragmatic/inferential, and imperfections (typos and malformed text).
- **A hybrid human–LLM annotation pipeline.** Linguistically trained annotators labelled a reference set. LLMs were then compared against that reference set for stability across runs and for agreement with the human labels. The best-aligned setup annotated the rest of the corpus.
- **The corpus.** Nearly 7,000 premise–hypothesis pairs drawn from AMBIENT, LiveNLI, ChaosNLI, and SNLI, each with an ambiguity-type label and alternative interpretations.
- **A classification benchmark.** BERT classifiers that see the alternative interpretations identify the ambiguity type far better than classifiers that see only the premise and hypothesis.

#### My role

- Designed the linguistically grounded ambiguity taxonomy and refined its categories based on pilot annotation results and inter-annotator agreement.
- Developed and revised the annotation guidelines.
- Led the human annotation effort: recruited, trained, and coordinated the annotators.

#### Publication

Jayaweera, C., Zhang, D., Kempa, E., & Dorr, B. J. (under review). CLEAR-NLI: An ambiguity-first corpus for perspectivist natural language inference.
