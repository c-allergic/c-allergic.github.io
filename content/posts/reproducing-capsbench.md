+++
title = "Reproducing CapsBench: What Makes a Good Caption Evaluator?"
date = 2026-05-11T00:00:00+08:00
draft = false
tags = ["caption-evaluation", "benchmarking", "generative-models"]
categories = ["Research"]
description = "Initial findings from reproducing PGV3's CapsBench and what they reveal about the state of automated caption evaluation."
+++

## Why Caption Evaluation Matters

Automated image captioning has come a long way, but evaluation hasn't kept up. Standard metrics like BLEU, METEOR, and CIDEr were designed for reference-based machine translation — they weren't built to capture the nuanced quality dimensions of modern generative captioners. More recent metrics like CLIPScore and RefCLIPScore improve on alignment but still miss fine-grained issues like hallucination, style appropriateness, and factual grounding.

## CapsBench: A Closer Look

[PGV3](https://arxiv.org/abs/2409.10695)'s **CapsBench** is one of the most comprehensive efforts to benchmark caption evaluation metrics. It tests evaluators across multiple dimensions: object hallucination, attribute accuracy, relationship correctness, and more. I've been reproducing CapsBench to understand its strengths and — more importantly — where it breaks down.

## Early Observations

From my reproduction and ablation experiments, a few patterns are emerging:

- **Hallucination detection is still the weak spot.** Even strong VLM-based evaluators can be fooled by plausible-sounding but incorrect captions.
- **Reference quality matters enormously.** Small changes in how ground-truth captions are sourced or filtered can flip rankings.
- **No single metric dominates.** Different evaluators excel on different dimensions — there's no silver bullet.

## What's Next

These findings motivate a more principled approach to caption evaluation. I'm working toward a framework that:

1. Disentangles orthogonal quality dimensions (accuracy, style, diversity, faithfulness)
2. Uses targeted probes rather than aggregate correlation scores
3. Accounts for reference quality and annotation noise explicitly

If you're interested in this space, check out my survey on [generation model evaluation](https://github.com/c-allergic/awesome-generation-model-evaluation) — contributions and discussions are always welcome.
