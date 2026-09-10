---
layout: page
title: Image-Caption Evaluation Agent
description: The caption-precision gate of a high-quality image-text data synthesis pipeline — hierarchical, perception-aligned, reference-free
img: assets/img/hieval.png
importance: 1
category: work
---

## Image-Caption Evaluation Agent (HiEval)

*Developer · Prof. Jiaheng Wei's Group (HKUST-GZ) · Huawei Collaboration · ongoing*

High-quality image-text data synthesis depends on being able to tell **whether a caption precisely and completely describes its image**. Existing caption evaluation benchmarks mostly rely on surface-level element matching, which aligns poorly with human perception and introduces systematic bias; high-quality evaluation also depends on expensive human annotation.

**My contribution** is the caption-precision gate of the pipeline: an agent-based evaluation module that decides whether a generated caption is accurate and complete enough to enter the curated training set.

- **First use of an agent system for this task.** The agent explores an image **hierarchically, from coarse to fine**, in a way that mirrors human perception: it decomposes the scene, subdivides regions, and verifies the caption layer by layer — instead of matching surface elements.
- **Reference-free evaluation.** Because the agent grounds the caption's textual units (objects, attributes, relations) in the image itself, a caption can be judged **without any human-written reference**.
- **Scene-graph reconstruction works well.** The hierarchical decomposition reconstructs an interpretable scene graph of the image, which reliably exposes **hallucinated and attribute-mismatched** captions — with an explainable trace of how each judgement was reached.

The module therefore cuts annotation cost while raising data quality: only image-faithful captions flow downstream.
