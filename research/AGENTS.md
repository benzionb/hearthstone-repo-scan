> **Created:** 2026-02-18
> **Last updated:** 2026-02-18
> **Purpose:** Capture how the 24-repo sweep supports superhuman Battlegrounds goals, including buy-phase and live-data pathways, and keep this aligned to `repo-crosswalk.md`.

# Repo Utility Across Stack Phases (including Buy-Phase and Live Data)

This note summarizes the broader utility of the researched repositories for the overall superhuman Battlegrounds stack:
- Full-lobby simulation
- Replay/conformance
- Coaching/inference
- Evaluation, benchmarking, and future RL/self-play expansion
- Buy-phase execution and live-data ingestion

## Why this matters

The earlier architecture treats this as a full stack, not a move picker. Buy-phase and live-data are core foundations, not excluded priorities.
- `superhuman-hearthstone-battlegrounds/research/2026-02-18-superhuman-bg-program-synthesis.md`
- `superhuman-hearthstone-battlegrounds/research/2026-02-18-superhuman-bg-architecture-and-compute.md`
- `superhuman-hearthstone-battlegrounds/research/2026-02-18-superhuman-bg-repo-evidence-and-benchmarking.md`

## Crosswalk alignment check

Compared against `research/repo-crosswalk.md`, this file is mostly consistent:
- Canonical rule stack mapped to `hs-reference-data`, `hsdata`, `hearthstonejson-client`, and `HearthDb`.
- Patch overrides mapped to `Hearthstone-Deck-Tracker`, `HSTracker`, and `firestone`.
- Replay/parsing mapped to `python-hslog`, `hs-replay-xml-parser`, and `hsreplay-xml`.
- Combat mapped to `api-simulate-battlegrounds-battle` + archived full-lobby references.
- Explicitly preserves the documented gap: no current repo gives a modern standalone buy-phase engine.
- Explicitly keeps buy-phase and live-data as required, not excluded, inputs to the stack.

Remaining adjustment needed for strict consistency:
- The file should be updated automatically as `corpus-index.json` confidence/role values evolve.

## Practical use by category

### 1) Live-state ingestion / coaching loop (sim-to-real)
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/DeepBattler`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/Hearthstone-Deck-Tracker`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/HSTracker`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/firestone`

Use for live log/event capture, in-client state semantics, UX prompting patterns, and state-surface flows for real-time recommendation engines.
- Why this is buy-phase relevant: informs what players can and cannot do in tavern timing windows, and provides the real-state feedback loop for state drift detection.
- Why this is live-data relevant: highest-confidence path for live ingestion, but needs platform-normalization and versioned parsers.

### 2) Canonical rules / patch metadata layer
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/hs-reference-data`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/firestone-data`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/hsdata`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/hearthstonejson-client`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/HearthDb`

Use for canonical IDs, card/minion definitions, patch metadata, override ingestion, and long-lived provenance.
- Why this is buy-phase relevant: this is the only practical metadata foundation for card pool, rarity bands, tribe and cost rules, and core action legality baseline.
- Why this is live-data relevant: supports patch/version tagging and override verification for live updates.
- What this gives: stable metadata source and deterministic IDs.
- What it doesn't fully give: complete live patch semantics by itself.

### 3) Replay + parsing + telemetry for training/eval data
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/python-hslog`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/hs-replay-xml-parser`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/hsreplay-xml`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/hs-game-converter-csharp-port`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/python-hearthstone`

Use for fixture extraction, schema stabilization, replay replayability, and reproducible model evaluation sets.
- Why this is buy-phase relevant: creates reference fixtures for conformance tests on tavern legality and action effects.
- Why this is live-data relevant: gives deterministic backfills for validating log-driven state signals before/after live capture.
- What this gives: deterministic fixture extraction and schema normalization.
- What it doesn't fully give: patch-aware live patch correction without external overrides.

### 4) Combat + full-lobby behavior (with buy-phase interactions)
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/api-simulate-battlegrounds-battle`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/BGSimulator`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/stone_ground_hearth_battles`

Use for combat oracles, elimination/round sequencing, and full-lobby architecture references.
- Why this is buy-phase relevant: provides reference behavior for phase transitions and post-buy resolution effects.
- Why this is live-data relevant: useful for validating simulated outcomes against observed match progression when replay/log traces are available.
- What these repo(s) gives: strong combat resolution behavior and historical full-lobby flow examples.
- What they don't fully give: current turn-by-turn tavern-phase parity.

### 5) Evaluation and protocol support
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/coliseum`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/hsproto`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/hs-game-entities`

Use for visualization/debugging, serialization consistency, and model-facing state contracts.

### 6) Low-leverage / archive-first repos
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/UnityPack`
- `/Users/zion_1/Projects/Hearthstone Research/bg_repo_scan/SabberStone`

Use only when deeper extraction or very specific legacy parity comparison is needed.

## Research takeaway

The existing corpus supports the whole superhuman stack well: state acquisition, patching, replay data, combat scoring, and coaching integration. The remaining gap remains not “lack of source material,” but **unifying it behind a versioned, deterministic simulation contract**.

## Repo-ordered priority for future execution

1. `hs-reference-data` (primary source model) and `HearthDb`
2. `Hearthstone-Deck-Tracker` + `HSTracker` (overrides + live-state flow)
3. `python-hslog` + `hs-replay-xml-parser` (dataset and conformance backbone)
4. `api-simulate-battlegrounds-battle` (combat oracle)
5. `BGSimulator` / `stone_ground_hearth_battles` (full-lobby references only)
6. DeepBattler (operational copilot patterning)

## Adjustments to keep it fit for the current plan

- Convert priority references to include current-confidence buckets from `research/corpus-index.json` (especially to avoid over-prioritizing low-confidence repos).
- Keep the “what this repo gives / does not fully give” notes inside each practical category only.
- Keep this file as a high-level research summary only; do not treat repo-specific `AGENTS.md` files as a substitute for this file.
