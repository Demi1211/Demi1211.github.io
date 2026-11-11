---
layout: page
title: "Dissertation: Why do L1 and L2 readers differ?"
description: "Testing the Shallow Structure Hypothesis against retrieval interference by building each account into GPT-2 and comparing the resulting surprisal with L1 and L2 reading times."
img: assets/img/projects/dissertation.jpg
importance: 0
category: Ongoing Research
---

**Proposal approved, 2026 · Advisor: Dr. Edith Kaan · Committee: Dr. Jonathan R. Brennan (University of Michigan), Dr. Julian Grove, Dr. Stefanie Wulff, and Dr. Bonnie J. Dorr (UF Computer & Information Science & Engineering)**

#### The question

Adult second-language (L2) speakers can know a grammar well and still process sentences differently from first-language (L1) speakers in real time. Two accounts place this difference in different parts of processing:

- **The Shallow Structure Hypothesis** (Clahsen & Felser): L2 speakers do build hierarchical syntax, but they rely on it less strongly during online comprehension.
- **The interference account** (Cunnings): L2 syntactic representations are intact, but when a dependency has to be resolved (a verb finding its subject, a reflexive finding its antecedent), L2 speakers give more weight to non-structural cues such as gender or number. A feature-matching but structurally wrong noun then competes more strongly for retrieval.

Both accounts are usually stated in words, so it is hard to tell which pattern of reading times each one actually predicts. My dissertation builds each account into a neural language model and asks which one better predicts the human data.

#### Approach

The base model is GPT-2 Small, with its weights frozen. Its word-by-word surprisal is a well-established predictor of reading time.

- **Weaker syntax (α).** Using Penn Treebank sentences, I estimate the parts of GPT-2's hidden states that encode structural information: dependency relations, depth, and clause boundaries. I find these with iterative linear probes (INLP), one layer at a time. Then I scale that component down step by step (α = 1, .75, .50, .25, 0) and leave the rest of the representation untouched. Control interventions on random and part-of-speech subspaces check that any effect is specifically syntactic.
- **Stronger cue match (r).** At a retrieval site, I shift the model's attention between the grammatical target and a competing distractor, according to which one matches the retrieval cue. The total attention on the two stays the same.

#### Data

Both interventions are evaluated on published self-paced reading studies:

- **Alaskar & Cunnings (2025):** subject–verb agreement and reflexives, with large L1 English and Arabic–English L2 groups. Grammaticality is crossed with whether a distractor noun matches in number or gender.
- **Omaki & Schulz (2011):** filler–gap dependencies and relative-clause islands, with L1 English readers and Spanish–English L2 readers.

Hierarchical regression models will test whether surprisal from each modified model explains L1–L2 reading-time differences beyond unmodified GPT-2 surprisal and lexical predictors. If neither intervention improves on the unmodified model, that is a result too.

#### Related work

The naturalistic-listening EEG data from the [*Little Prince* project]({{ '/projects/0_project/' | relative_url }}) carry the same question from controlled reading into continuous listening. One example is dropped subjects in Spanish, where a competing discourse referent may make retrieval harder for L2 listeners.

#### Funding

NSF BCS-2518248.
