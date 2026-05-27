---
layout: page
title: pitchclaw
description: LLM-curated calibrated priors for football match outcomes
img:
importance: 2
category: open-source
giscus_comments: false
---

**[github.com/mikkuzne/pitchclaw](https://github.com/mikkuzne/pitchclaw)**

Claude Opus maintains a weekly-rewritten team-strength model; per-fixture predictions output calibrated H/D/A probabilities, and a downstream mechanical filter (`model_prob × odds − 1 > threshold`) flags actionable outcomes. The model is never asked to pick an outcome — it estimates probabilities, deliberation handles calibration, and a deterministic filter selects from there.

```
Weekly evaluate (Opus, after each matchweek)
  inputs:  last week's predictions + actuals + football_model.md
  output:  rewritten football_model.md
        ↓
Per-fixture predict (Opus, T-15m before kickoff)
  inputs:  team stats, model, Elo, odds, XI, H2H, rest
  output:  { H: 0.40, D: 0.25, A: 0.35 } + reasoning
        ↓
Mechanical filter (Python, deterministic)
  for each outcome: EV = p × odds − 1
  if EV > threshold → Telegram notification
```

## Status

EPL 2025/26 season concluded May 2026. The bot ran live for the final ~6 matchweeks. Off-season now; strategy improvements for 2026/27 are in scope. Results from the live run live in `RESULTS.md` in the repo.

## Connective thesis

The pattern — *observe outcomes, update a world model, act on calibrated belief* — is the same loop I use in research and in [ClawGuard](/projects/clawguard/). Football is just a tractable testbed: short feedback cycles, public ground truth, real costs for being wrong.
