---
layout: page
title: HiEval
description: Agent-based caption evaluation system — hierarchical, perception-aligned, annotation-free
img: assets/img/hieval.png
importance: 1
category: work
---

## HiEval: An Agent-based Caption Evaluation System

Existing caption evaluation benchmarks mostly rely on surface-level element matching, which aligns poorly with human perception and introduces systematic bias when judging whether a caption fully and accurately describes an image. High-quality evaluation also depends on expensive human annotation.

**HiEval** addresses both problems with a tool-calling VLM agent:

- **Hierarchical, perception-aligned evaluation.** The agent explores an image from coarse to fine (region tree: *ground → subdivide → decompose → match → commit → prune*), recursively matching regions against caption units and producing a 3-dimensional score (P/R/F1, attributes, relations) with a fully explainable decision trace. This mirrors how humans perceive images — from the overall scene down to objects and their interactions — instead of pattern-matching surface elements.
- **Automated, annotation-free evaluation.** The same exploration mechanism automatically produces fine-grained evaluation results and improvement suggestions, delivering high-quality assessment at a fraction of the cost of manual annotation.
- **Objective visual evidence.** To avoid self-validation bias, HiEval grounds its judgment in an independent stack: GroundingDINO + SAM3 for objects and Mask2Former for background/stuff classes, which instance-level models cannot see (backgrounds cover ~38% of ground-truth content in common benchmarks).

**Scale.** The system has been validated on four public benchmarks (CapsBench, CompreCap, CAPTURE, PerceptionRubrics) against four mainstream models (GPT-5.5, Claude Sonnet 4.5, Qwen3.5, Doubao Seed 2.1), evaluating 6600+ captions.
