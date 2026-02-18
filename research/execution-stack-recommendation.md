# Execution Stack Recommendation (Post-Sweep)

## Primary Recommendation

1. **Data foundation:**
   - Build a canonical `patch_manifest` from `hs-reference-data` + `hsdata` (raw card set tags/patch IDs) and normalize with override layers from `Hearthstone-Deck-Tracker`.
2. **State reconstruction:**
   - Use `python-hslog` to ingest Power.log/BGS state changes and `hs-replay-xml-parser` for replay-derived fixtures.
3. **Buy-phase engine v2:**
   - Implement deterministic buy-phase runtime (Python 3.11) against the canonical manifest instead of extending legacy `stone_ground_hearth_battles`.
4. **Combat pass-through:**
   - Feed post-buy board states into `api-simulate-battlegrounds-battle` during parity checks until a native combat layer is implemented.
5. **Model loop:**
   - Keep decision loop external (e.g., `bgctl suggest`) and contract output in terms of legal action IDs from v2 legal-action enumerator.
6. **Telemetry/override freshness:**
   - Add scheduled manifest/build refresh job and override diff alarms (`battlegrounds_tag_overrides` + patch version drift alerts).

## What to Build First

- `patch_manifest` generator + schema + hash
- state parser adapters (`python-hslog` + `hs-replay-xml-parser`)
- v2 lobby/buy-state model and deterministic action graph
- legality validation + action application tests on replay-derived fixtures

## What To Ignore in v2 Sprint

- Full adoption of `stone_ground_hearth_battles` as canonical runtime
- Replaying BG UI concerns from `firestone` / `HSTracker` as simulation logic sources

## Why this stack

- Minimizes legacy drift and directly targets patch freshness using explicit manifest + overrides.
- Separates “what is true in live data” (`patch_manifest`, overrides, logs) from “how to execute one turn” (v2 engine).
