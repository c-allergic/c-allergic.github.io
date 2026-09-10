---
layout: page
title: Long-Horizon Agent Trajectory Data-Synthesis Pipeline
description: Benchmark analysis informing how to synthesize long-horizon agent trajectories
importance: 2
category: work
---

## Long-Horizon Agent Trajectory Data-Synthesis Pipeline

*Collaborator · DeepWisdom · ongoing*

Training long-horizon agents requires large amounts of **synthetic trajectory data** — but how should such data be generated, and how hard should the resulting tasks be? I contributed the **benchmark and evaluation research** that grounds this design.

**My contribution:**

- **Comparative benchmark analysis.** I surveyed and compared mainstream long-horizon agent benchmarks, distilling (i) how each synthesizes its trajectory data, and (ii) how their test tasks differ in complexity — along axes such as number of steps, context handling, tool use, and environment.
- **Design guidance for the pipeline.** Based on that analysis — covering 12+ synthetic-trajectory works — I identified where existing benchmarks fall short, in particular in **data scale** and **real-execution environments**, and used these gaps to inform how the pipeline should generate longer-horizon, more realistic trajectory data.
