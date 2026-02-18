# Risk Map (24-Repo Sweep)

## High Risk (Blocking)

- **No single canonical buy-phase source:** no repo provides a complete, live-maintained full buy-phase engine with manifest-ready patch semantics.
- **Version drift:** overlay/replay ecosystems are fast-moving and can silently shift anomalies, tribes, and tier constraints without semantic tagging in parsers.
- **Stale legacy simulators:** `stone_ground_hearth_battles` and `BGSimulator` are historical baselines, not reliable current patch engines.

## Medium Risk (Manage)

- **Data-format mismatch:** parser schemas differ across ecosystems (`hsreplay-xml`, `python-hslog`, `hs-game-entities`, custom C# parsers).
- **Cross-platform telemetry stack coupling:** HDT overlays (`DeepBattler`, `HSTracker`) and native app stacks are hard to run as serverless or Linux-native services.
- **Override precedence ambiguity:** `battlegrounds_tag_overrides` from HDT/Firestone families and internal rule files can conflict.

## Low Risk (Informational)

- **Legacy code reuse value:** deterministic components from `api-simulate-battlegrounds-battle` and `stone_ground_hearth_battles` are useful for architecture patterning.
- **Protocol compatibility:** `hsproto`/`hsreplay-xml` are stable schema references for long-lived replay interoperability.

## Mitigations

- Enforce manifest hash + source provenance on every fixture (`manifest_hash`, `reference_snapshot`, `override_snapshot`).
- Version and pin manifest/override inputs in CI and replay conformance artifacts.
- Keep legacy repositories as read-only reference only, and treat outputs as unit-test fixtures.
