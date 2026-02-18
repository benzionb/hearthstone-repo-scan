# Repo Crosswalk: 24-Repo Sweep

## Canonical Path Candidates

### Live card + tag reference
- **Primary:** `hs-reference-data` (actively updated deck/card/rule metadata service)
- **Fallback/refresh support:** `hsdata` + `hearthstonejson-client` (raw upstream payloads)
- **ID normalization:** `HearthDb` + `python-hearthstone`

### Patch-override and live config ingestion
- **Primary:** `Hearthstone-Deck-Tracker` (`battlegrounds_tag_overrides` model)
- **Cross-check:** `HSTracker` (`RemoteConfig` and battlegrounds overrides)
- **UI/test hooks:** `firestone` (`bgs-anomalies` services + patch endpoints) when validating integration contracts

### Replay/parsing + conformance corpus
- **Primary:** `python-hslog` + `hs-replay-xml-parser` for normalized state extraction
- **Schema basis:** `hsreplay-xml` + `hs-game-entities` + `hsproto`
- **Replay interpretation alternatives:** `hs-game-converter-csharp-port`, `hearthstone-parser`

### Combat engine
- **Primary runtime baseline:** `api-simulate-battlegrounds-battle` (battle resolver)
- **Historic full-lobby references:** `stone_ground_hearth_battles`, `BGSimulator` (archival only)

### Buy-phase engine scaffold
- No repo provides a complete modern buy-phase engine in isolation.
- Use a bespoke v2 engine fed by `hs-reference-data`, `HearthDb`, and `firestone-data` data layers.

## Recommended Role Assignment

- **core_data_reference:** `hs-reference-data`, `HearthDb`, `hsdata`, `hearthstonejson-client`
- **core_patch_freshness:** `hsdata`, `firestone-data`, `firestone` artifact endpoints
- **state_ingest:** `python-hearthstone`, `python-hslog`, `hs-game-entities`
- **replay_reconstructor:** `hs-replay-xml-parser`, `python-hslog`, `hsreplay-xml`
- **combat_resolver:** `api-simulate-battlegrounds-battle`
- **overlay_grounding:** `Hearthstone-Deck-Tracker`, `HSTracker`, `firestone`
- **legacy_inspiration_only:** `stone_ground_hearth_battles`, `BGSimulator`, `SabberStone`
