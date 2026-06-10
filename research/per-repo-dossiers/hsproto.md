# hsproto

## Unabridged research summary
- repo_url: https://github.com/HearthSim/hsproto.git
- org: HearthSim
- role: protocol_schema_reference
- confidence: 0.52
- must_use_for: packet/replay field mapping
- risk_flags: Very old schema snapshot
- capability_scores: live_fidelity=0.59, simulation_coverage=0.02, data_freshness=0.06, parser_strength=0.63, ml_integration=0.17

## Repository-level observed structure
- top directories: blizzard, bnet, bobnetproto, pegasus, spectatorproto
- top files: README.md
- dominant file types: .md

## Readability anchor
> Hearthstone Protos
> ==================
> 
> Protobufs decompiled from the [Hearthstone](http://playhearthstone.com)
> game client. Source code for the decompiler available in
> [HearthSim/proto-extractor](https://github.com/hearthsim/proto-extractor).
> 
> ---
> 
> Version: 13.0.9.28556
> 
> http://hearthsim.info

## Neutral implementation-oriented notes
- This repository is currently mapped for the sweep-defined role above.
- It is best consumed as a subsystem for that role and not as a standalone source for unrelated stages.
- When used in the superhuman stack, keep explicit boundaries: parser/schema/data layer here, state/move engine outside this repo.
