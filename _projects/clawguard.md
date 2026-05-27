---
layout: page
title: ClawGuard
description: AI workload observer — watches what local agents are doing, never blocks
img:
importance: 1
category: open-source
giscus_comments: false
---

**[github.com/mikkuzne/clawguard](https://github.com/mikkuzne/clawguard)**

Everyone is running AI agents now — Cursor, Copilot, local LLMs, MCP servers, coding assistants. These tools read files, execute commands, make network calls, install plugins. Nobody has visibility into what they are actually doing at the OS level.

ClawGuard sits on your machine and observes. It monitors process execution, network connections, and application behavior — but it never kills processes, blocks connections, executes commands, or modifies anything on the host. It reads OS state and writes only to its own state directory (`~/.clawguard/`).

## How it works

Three components, no fixed schedule:

- **Collector** (every 15 s, no LLM, zero cost) — snapshots processes, connections, apps; enriches new processes (codesign, lsof, parent chain, DNS); detects 8 deviation types against a `known.json` world model; builds session trees for agent process forests; emits per-session events (spawn, exit, LLM connection).
- **Reactive path** (Haiku, ~$0.001 per event) — when the collector sees something unknown, it stubs it immediately to silence repeats and judges whether it's suspicious enough to become a finding.
- **Three-phase sweep** (Sonnet, on demand) — wakes itself when new findings or unclassified stubs appear; each phase only receives the data it needs.

The collector is free; the LLM is only paid when there is genuinely something new to think about.

## Connective thesis

ClawGuard is the open-source incarnation of an idea that runs through my research: **agentic systems should be observable at the OS level, and a small LLM loop maintaining a live world model is a workable substitute for hand-written detection rules**.
