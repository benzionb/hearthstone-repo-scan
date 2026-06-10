> **Created:** 2026-06-11
> **Last updated:** 2026-06-11
> **Purpose:** Fresh pass over this Feb-2026 research corpus against the June-2026 SuperBG revival (plan: `Vault/2.3 specs/2026-06-10-superbg-revival-plan.md`). Records what the sweep got right, what's superseded, the workspace cleanup, and two upstream-vanished archival warnings.

# Corpus Relevance — June 2026 Revival Pass

## Verdict on the Feb 2026 sweep

The sweep's core conclusion was **correct and is now vindicated**: no OSS buy-phase engine exists, build bespoke, delegate combat to `api-simulate-battlegrounds-battle`, and use the Firestone data ecosystem as the only live current-patch reference source. SuperBG implemented exactly this — except in TypeScript rather than the recommended Python 3.11.

**Still valid:**
- Version-drift + override-precedence risks (risk-map.md) — now apply to the npm release cadence of `@firestone-hs/*` at each Blizzard patch
- Legacy sims (BGSimulator, stone_ground_hearth_battles, SabberStone) are archival/inspiration only
- Log-based ingestion over tracker/overlay coupling — `tools/bg_log_reader.py` does exactly this, and it's the right base for the Phase-4 <300ms local coach
- DeepBattler as LLM-copilot prior art — newly relevant for Phase 2 (benchmark baseline) and Phase 4 (coach UX)

**Superseded:**
- Python 3.11 buy-phase engine → built in TS (`superbg/src/env/`)
- python-hslog as primary ingestion → bespoke `bg_log_reader.py` (per-action capture as of June 2026)
- patch_manifest from hsdata + HDT overrides → versioned npm consumption of `@firestone-hs/reference-data`
- "combat pass-through until a native layer" → delegation via npm is the permanent design
- HSReplay-XML parsing cluster → Phase 3 is VOD/vision-based imitation, not replay-XML

## ⚠️ Upstream-vanished archival assets (do NOT delete these clones)

| Clone | Status | Why it matters |
|-------|--------|----------------|
| `api-simulate-battlegrounds-battle` | **GitHub repo 404** (SSH+HTTPS, both names) | The npm package `@firestone-hs/simulate-bgs-battle` is still actively published (1.1.717, 2026-06-03) but ships **dist-only JS**. This local clone (v1.1.684, Feb 11, depth-1 shallow — no history) is the only surviving TypeScript **source** of the combat engine SuperBG delegates to. ARCHIVED 2026-06-11: pushed to github.com/benzionb/simulate-bgs-battle-mirror (private) and restore-tested bundle at research/archives/. |
| `firestone-data` | **Remote dead** | Firestone static backend data (patches.json, AI decks). Smaller stakes, but not re-clonable. |

## Workspace cleanup (2026-06-11)

- **Dossiers rescued:** the per-repo dossiers existed only as gitignored `AGENTS.md` files inside each clone (the export step documented in README never ran). All 24 are now committed under `research/per-repo-dossiers/`.
- **Deleted (14 repos, ~3.6GB, each verified re-clonable via `ls-remote` before deletion):** hs-reference-data (2.8G, duplicated by npm), firestone (268M, master unchanged since clone), hsdata (196M), hs-replay-xml-parser (97M), hs-reference-data-parser, SabberStone, hs-game-converter-csharp-port, coliseum, hearthstone-parser, HearthDb, UnityPack, BGSimulator, hsproto, hs-game-entities, hsreplay-xml, hearthstonejson-client.
- **Kept (~250MB working set):** api-simulate-battlegrounds-battle + firestone-data (archival, dead upstreams), DeepBattler + Hearthstone-Deck-Tracker (Phase-4 prior art + plugin API), HSTracker (only maintained macOS tracker — pulled current), python-hearthstone + python-hslog (perception lineage — pulled current), stone_ground_hearth_battles (only BG RL training harness reference, Phase 3).

## DeepBattler notes for Phases 2 & 4 (read before building the coach)

Architecture: HDT C# plugin reads the tracker's entity model → change-detected LLM-friendly JSON snapshots dropped to disk (`game_state.json`, per-turn folders) → Python agent file-watches, injects state + a ~390-line static strategy prompt into Gemini Live / o1-mini → advice via WPF overlay file-watching `agent_output.txt`.

**Lift:** the minimal LLM-friendly state JSON schema (names + natural-language card text); the file-drop + watcher IPC decoupling (simple, debuggable; the LLM is the latency bottleneck, not IPC); per-turn snapshot folder layout as an episode format for Phase-3 imitation data; static-strategy-prompt + injected-state as the Phase-2 LLM benchmark baseline.

**Avoid:** tracker-process perception coupling (stay on Power.log); rebuilding the LLM session per state change; HP-delta-only rewards; and DeepBattler's biggest blind spot — **it never models opponents at all** (no boards, no HP). SuperBG's obs already does; keep it that way in the coach schema.

Note: DeepBattler upstream is dormant (HEAD Nov 2025) — the local copy is effectively final.
