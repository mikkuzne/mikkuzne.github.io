---
layout: page
permalink: /cv/
title: cv
nav: true
nav_order: 5
description: Senior Applied Scientist — foundation models for security, LLM alignment, agentic AI.
---

<a class="btn btn-outline-primary" href="/assets/pdf/cv.pdf" target="_blank">📄 Download CV (PDF)</a>

The PDF is the source of truth — it's regenerated from [LaTeX](https://github.com/mikkuzne/mikkuzne.github.io/blob/main/assets/pdf/cv.pdf) and replaces this file each release. The web sections below are an at-a-glance summary; see the PDF for full detail.

---

## Now

**Senior Applied Scientist, Amazon AWS — AI Security and Observability.** *(2022 – present.)*

- Leading **agentic AI security** — detection models on agent runtime traces (Amazon Bedrock AgentCore) that surface intent deviation and policy violations, extended with OS-level signals (eBPF, system logs) and auto-detection of agentic workloads in dynamic environments.
- Co-developed **EV-AUDIT**, a **co-evolutionary red/blue-team** auditing framework for multi-agent systems — attacks and defenses evolve against each other over execution traces. Targets *task hijacking*, where there is no malicious verb to refuse: **31.26% attack success** on a frontier backend where all 22 baseline attacks fail, and a prompt-level defense that holds at negligible utility cost.
- Previously **tech lead of the audit-log foundation model** — shipped to production Sep 2025, cutting customer-facing false positives by **20–30%**. Designed the 10B → 10M diversity-preserving sampling, contrastive fine-tuning for tenant-specific entities (asnOrg, api), multi-signal evaluation, and interpretability tooling.
- Co-designed a memory-efficient hierarchical-log architecture for long-context, high-throughput security workloads.

## Earlier

**Yahoo! Research, New York.** *(2017 – 2021, Research Scientist.)* Contributed to ExtremeText (no-regret hierarchical softmax for extreme multi-label classification), VisualTextRank (unsupervised graph-based content extraction for ad text→image search), and unified multi-task CTR/CVR models that lifted advertising ROI by >10% in online A/B tests.

## Education

- **PhD**, Moscow Institute of Physics and Technology — Computer Science, Mathematical Modeling, 2016.
- **MS with Honors**, MIPT — Applied Mathematics & Physics, 2013.
- **BS with Honors**, MIPT — Applied Mathematics & Physics, 2011.
- **Yandex School of Data Analysis** — Diploma in Data Science, 2012.

## Interests

Agentic AI security · Automated red-teaming & co-evolutionary auditing · Foundation models for logs · Robust / self-supervised learning · Anomaly detection · Representation learning for structured / tabular data · Evaluation & interpretability · LLM alignment.
