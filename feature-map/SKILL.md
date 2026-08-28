---
name: feature-map
description: Co-create a locked, reasoned feature map (or any major product/design doc) with Sanchay through gather → sort → spar → write-once. Use when scoping a product area, a "door", a module family, or any doc built from rounds of stakeholder input where features must be sorted (spine/supporting/parked/cut) with recorded reasons. Trigger on "feature map", "let's brainstorm features for X", "one door at a time", "same style as the Open for All doc", or any multi-round product-scoping conversation. Born from the TAR-06 Open for All sessions (Aug 2026), which took 6 versions because these rules were learned the hard way.
---

# Feature Map Playbook

Turn a product area into one locked, reasoned document, written once, not six times.

**Read `learnings.md` in this folder before starting. Append to it whenever a correction lands.**

## The contract (non-negotiable, in priority order)

1. **Gather everything before writing anything.** The user gives input in rounds. Writing between rounds is the whack-a-mole failure: every round then produces a rewrite. Hold everything in a running inventory until rounds are done.
2. **Framing approval is not a go.** "I like this structure" authorizes nothing. Write the deliverable only when the user has seen the actual content plan (or prose for key sections) and explicitly said go.
3. **State the complete picture back first.** One message: everything gathered, everything sorted, every open question. The user rules; then write.
4. **Verify every checkable claim before asserting it.** "X already exists" → check the codebase. "Nobody does this" → search the web. Both directions of error happened in the source sessions and both were caught only by checking.
5. **Push back once, with reasons. After a ruling, never re-raise.** Raising a concern is diligence; raising it twice after a ruling is not listening. Exception: genuinely new information.
6. **The user's taxonomy wins.** Do not merge things they keep separate (police verification is not "background checks"). Do not rename their concepts.
7. **When the user reframes your concern instead of trimming their idea, the reframe is usually the answer.** Recognize it, adopt it, move on.

## The pipeline

### 1. Ground
Load project memory and every prior doc in the family. Note the register rules in force (for RentOk: plain language, no em dashes, requirements only, no build-state commentary in design docs, no code references). Establish where truth lives and where the doc will be persisted.

### 2. Gather (no writing)
Run the brainstorm. Expand, critique, and extend the user's ideas, several steps beyond what they said, never just transcribing. Keep a running inventory in a scratch file: every feature, ruling, vignette, phrase the user liked. This inventory is the completeness check later. Rounds end when the user says so, not when it feels done.

### 3. Sort, with reasons
Classify everything: **spine** (remove it and the thing stops making sense) · **supporting** (strengthens the spine, ships without changing the thesis) · **parked** (good idea, wrong dependencies; name the condition that revives it) · **cut** (name the reason). Every placement carries a written justification a stranger could retrace. Heroes are positioned as heroes: if the user says a feature is the USP, the doc must read that way.

### 4. Spar
Present the sorted picture plus your genuine positions (recommendations first, reasons attached). Ask only questions whose answers change the doc. Log every ruling. Loop with the user until nothing is unruled.

### 5. Structure around the customer's life
Organize by the customer's moments (found it, started, living with it, being known, moving on), not by your abstract logic. Chains and loops earn one short "why this holds together" section at most. Name cross-cutting mechanics separately (the door-3 examples: the tool ends where the workflow begins · login gates the result never the discovery · every artifact carries the name).

### 6. Write once
Only on an explicit content-go. Match the register rules exactly. Open decisions get logged inside the doc, owned, not lost.

### 7. Fresh-eyes self-review (mandatory, before delivering)
- **Inventory diff**: every gathered item is present or deliberately absent, nothing silently dropped across versions (the door-3 doc lost its own acquisition thesis for two versions this way).
- Duplication, misplaced sections (does each feature live in the moment where the customer meets it?), register violations (`grep` for em dashes and build-state phrases), contradictions with rulings.
- Fix inline, list what was found and fixed when delivering.

### 8. Persist
Repo commit + push, vault mirror, project memory updated (decisions + version + commit hash), file sent to the user. Same doc family, same conventions, every time.

## Relationship to other skills

`feature-map` is the altitude above `feature-design-pipeline`, and they chain: the map decides what exists and why (portfolio level, with the stakeholder, in rounds); the pipeline then takes ONE spine/supporting item to engineer-ready design docs. When a map is locked, the natural next invocation for any single item is `feature-design-pipeline`. Do not use the pipeline to scope an area, and do not use this skill to deep-design one feature.

## Failure modes that created this skill

| Failure | Cost | Rule |
|---|---|---|
| Wrote after framing approval | Full rewrite | #2 |
| Wrote between input rounds | 6 versions | #1 |
| Content silently dropped across rewrites | Lost the acquisition thesis for 2 versions | Step 7 inventory diff |
| Build-state leaked into requirements doc | User had to make a standing rule | Step 1 register |
| Re-raised a ruled concern (privacy) | Trust erosion, wasted round | #5 |
| Merged user-separate concepts | Correction round | #6 |
| Asserted without checking (both "it needs building" and "nobody does this") | Two public corrections | #4 |
