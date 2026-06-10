---
layout: about
title: about
permalink: /
subtitle: Senior Applied Scientist, <a href="https://aws.amazon.com/" target="_blank">Amazon AWS</a> · AI Security and Observability.

profile:
  align: right
  image:
  more_info: >
    <p>New York, NY</p>
    <p>mikkuzne [at] gmail.com</p>

selected_papers: false
social: true

announcements:
  enabled: true
  scrollable: true
  limit: 5

latest_posts:
  enabled: false
  scrollable: true
  limit: 3
---

My current focus is **securing AI agents at AWS**, along three connected threads: detection models over agent runtime traces (Amazon Bedrock AgentCore) that surface **intent deviation and policy violations** — prompt injection being one driver — conditioned on an agent's historical behavior and context; extending detections **below the application layer** with OS signals (eBPF, system logs), verifying what an agent actually did rather than what its trace claims; and **auto-detecting agentic workloads** in dynamic environments — the idea behind [ClawGuard](/projects/clawguard/). Before that I tech-led an embedding model for audit logs, now in production for Amazon GuardDuty: learning representations of security entities (IPs, APIs, usernames) from dynamic audit data and cutting customer-facing false positives by 20–30%.

A single thread connects what I do: **LLM workflows that learn from dynamic environments** — observe outcomes, update a world model, act on calibrated belief. The same loop shows up in my research (STARS alignment work accepted at SPIGM @ ICML 2026, earlier robust SSL for tabular data, extreme classification at NeurIPS) and in the open-source projects I build on the side.

PhD from MIPT in Computer Science (2016); earlier work at Yahoo! Research on extreme multi-label classification and multimodal retrieval for ads. See [publications](/publications/) for the full list or grab the [CV](/cv/).

---

## Built with Claude

- **[ClawGuard](/projects/clawguard/)**  ·  [github.com/mikkuzne/clawguard](https://github.com/mikkuzne/clawguard) — AI workload observer. Watches what local agents are doing on your machine (processes, network, parent chains) and never blocks or modifies anything itself. A small LLM loop maintains a live world model in place of hand-written rules.
- **[apparty](/projects/apparty/)**  ·  [github.com/mikkuzne/apparty](https://github.com/mikkuzne/apparty) — Telegram bot that builds sandboxed web apps on demand. An Anthropic tool-use agent writes the code; `bwrap` isolates it; `/why <id>` has a second model narrate what the agent did, in plain English.
- **[pitchclaw](/projects/pitchclaw/)**  ·  [github.com/mikkuzne/pitchclaw](https://github.com/mikkuzne/pitchclaw) — LLM-curated calibrated priors for football match outcomes. Claude maintains a weekly-rewritten team-strength model; a downstream mechanical filter flags actionable outcomes from calibrated probabilities.
