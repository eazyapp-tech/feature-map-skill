# feature-map — product-area scoping skill

A reusable Claude Code **skill** for co-creating a locked, reasoned feature map with a stakeholder: **gather → sort → spar → write once.**

> Born from a real product-scoping series that took six versions because these rules were learned the hard way. The skill is those rules.

## What it does

Turns a product area into one document, written once, not six times. Routes on "feature map", "let's brainstorm features for X", "one door at a time", or any multi-round product-scoping conversation.

The contract it enforces, in priority order:

1. **Gather everything before writing anything.** Input arrives in rounds. Writing between rounds means every round produces a rewrite.
2. **Framing approval is not a go.** "I like this structure" authorizes nothing. Write only on an explicit go on content the stakeholder has seen.
3. **State the complete picture back first** — everything gathered, sorted, and still open, in one message.
4. **Verify every checkable claim before asserting it.** "X already exists" → check the code. "Nobody does this" → search. Both error directions have happened.
5. **Push back once, with reasons. After a ruling, never re-raise.**
6. **The stakeholder's taxonomy wins.** Never merge concepts they keep separate; never rename their concepts.
7. **When they reframe your concern instead of trimming their idea, the reframe is usually the answer.**

Everything gathered gets sorted into **spine** (remove it and the thing stops making sense), **supporting**, **parked** (with the condition that revives it), or **cut** (with the reason) — every placement carrying a justification a stranger could retrace. A mandatory inventory-diff self-review before delivery catches content silently dropped across versions.

## Install

**As a personal skill** (per user):
```bash
cp -R feature-map ~/.claude/skills/
```
Restart Claude Code (or start a new session).

**As a project skill** (shared via a repo):
```bash
cp -R feature-map <your-project>/.claude/skills/
```

## Files

| File | What |
|---|---|
| `feature-map/SKILL.md` | The playbook — contract, 8-step pipeline, and the failure-mode table that produced each rule. |
| `feature-map/learnings.md` | Living file. Read before starting; append whenever a correction lands. |

## Where it sits

`feature-map` is the altitude **above** `feature-design-pipeline`, and they chain:

- **feature-map** decides what exists and why — portfolio level, with the stakeholder, in rounds.
- **feature-design-pipeline** then takes ONE spine or supporting item to engineer-ready design docs.

Do not use the pipeline to scope an area, and do not use this skill to deep-design one feature.

## Adapting it

The contract and pipeline are system-agnostic. RentOk specifics are the register rules named in step 1 (plain language, no em dashes, requirements only, no build-state commentary, no code references) and the persistence recipe in step 8. Swap those for your team's.
