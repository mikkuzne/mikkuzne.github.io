---
layout: page
title: apparty
description: Telegram bot that builds sandboxed web apps and narrates its own behavior
img:
importance: 3
category: open-source
giscus_comments: false
---

**[github.com/mikkuzne/apparty](https://github.com/mikkuzne/apparty)**

A Telegram bot that builds small web apps on demand. You describe what you want; an Anthropic tool-use agent writes the code, sandboxes it with `bwrap`, and serves it at a public URL. `/why <build_id>` then has a second model narrate what the agent did, in plain English, so you (or anyone watching) can see what happened and why.

## What it does

- `/build <description>` — agent plans, writes files into a per-build sandbox dir, optionally starts a Python-stdlib backend, returns a shareable URL.
- `/edit <build_id> <change>` — resumes the agent on an existing build.
- `/why <build_id>` — Sonnet narrates what the agent did, in plain English.

Each build is capped at $2.00 of model spend (configurable). The 20 most recent builds per user are kept; older ones (and their backend processes) are auto-deleted.

## Architecture

- **Build agent** — Anthropic tool-use loop with `write_file`, `read_file`, `list_files`, `run_command`, `start_app`, `done` tools. Tracks tokens and cost per build.
- **Sandbox** — `bwrap` wrapper. `run_command` runs with `--unshare-net` (no network). `start_app` shares host network so the proxy can reach the backend. `/home` and `/root` are never bind-mounted, so the bot's `.env` is invisible to sandboxed code.
- **Proxy** — stdlib `ThreadingHTTPServer`; nginx forwards `/builds/` here.

## Connective thesis

Two audiences served by the same product: it generates small useful apps, and the `/why` narrator turns it into an inspectable sandbox for studying how tool-use agents actually behave under cost and time pressure.
